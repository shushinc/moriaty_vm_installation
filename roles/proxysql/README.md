1. Loginto proxysql for debug
    mysql -u admin -p'YOUR_SECURE_ADMIN_PASSWORD_HERE' -h 127.0.0.1 -P6032 


1. Check for both master and replica health:

mysql -u admin -p'YOUR_SECURE_ADMIN_PASSWORD_HERE' -h 127.0.0.1 -P6032 -e "SELECT hostgroup_id, hostname, status FROM runtime_mysql_servers;"

Example Output: when both master & replica is healthy:
+--------------+-------------+--------+
| hostgroup_id | hostname    | status |
+--------------+-------------+--------+
| 10           | 10.128.0.79 | ONLINE |
| 20           | 10.128.0.71 | ONLINE |
+--------------+-------------+--------+


2. 
mysql -u admin -pYOUR_SECURE_ADMIN_PASSWORD_HERE -h 127.0.0.1 -P6032 -e "SELECT hostgroup_id,hostname,port,status,weight FROM runtime_mysql_servers;"

3.
 mysql -u admin -pYOUR_SECURE_ADMIN_PASSWORD_HERE -h 127.0.0.1 -P6032 -e "SELECT * FROM mysql_replication_hostgroups;"