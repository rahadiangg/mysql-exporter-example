# Mysql Expoter Example

This repository for PoC & explore about MySql exporter for Prometheus

## How to run

First makesure you're already installed docker and docker compose.

```
docker compose up -d
```

### Setup MySql User

The exporter should have a mysql account to query some metrics, so we need to create and grant that user.

```
CREATE USER 'exporter'@'%' IDENTIFIED BY 'mantapdjiwa' WITH MAX_USER_CONNECTIONS 3;
GRANT PROCESS, REPLICATION CLIENT, SELECT ON *.* TO 'exporter'@'%';
```

### Grafana

Login grafana using default user & password ```admin```. After that you should import MySql default dashboard to visulized the data. You can use this dashboard

- https://grafana.com/grafana/dashboards/14057-mysql/
- https://grafana.com/grafana/dashboards/14031-mysql-dashboard/