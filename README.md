python3.6.3
bootstrap
jquery

-- 源码修改备注
\testGo\manager.py
<!--line4:-->
from gevent import monkey
<!--line7-->
    monkey.patch_all()

\httprunner\init.py
<!--注释以下代码-->
# try:
#     # monkey patch at beginning to avoid RecursionError when running locust.
#     from gevent import monkey; monkey.patch_all()
# except ImportError:
#     pass

\httprunner\report.py  line97-99
    # report_dir_path = os.path.join(os.getcwd(), "reports")
    # 修改保存报告的路径为\testGo\httprunner\tests\testcases\reports
    report_dir_path = os.path.join(os.getcwd(), r"httprunner\tests\testcases\reports")
celery相关
http://docs.celeryproject.org/en/latest/
http://docs.celeryproject.org/en/latest/getting-started/next-steps.html
Automatic naming and relative imports
http://docs.celeryproject.org/en/latest/userguide/tasks.html#task-naming-relative-imports

启动beat若报错： ERROR: Pidfile (celerybeat.pid) already exists
删掉项目下的celerybeat.pid文件即可

mysql安装教程：https://www.cnblogs.com/wishwzp/p/7113403.html