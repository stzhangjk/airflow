# 依赖
```
pip install mysqlclient
pip install apache-airflow
pip install apache-airflow[celery]
pip install apache-airflow[mysql]
pip install apache-airflow[redis]
pip install apache-airflow[ssh]
```
## 特别注意
因为tornado新版本由bug导致flower启动不了，需要卸载并安装旧版本
```
pip uninstall tornado 
pip install tornado==5.1.1
```

# 配置
在[airflow配置文件](airflow.cfg)配置了以下项：
```
default_timezone = Asia/Shanghai

sql_alchemy_conn = mysql://root:123456@127.0.0.1/vms_airflow?charset=utf8
executor = CeleryExecutor
broker_url = redis://localhost:6379/0
result_backend = redis://localhost:6379/0

visibility_timeout = 21600
```