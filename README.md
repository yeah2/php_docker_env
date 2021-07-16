# php环境本机搭建

目录结构要求：

位于 /data 目录下，data目录下必须的目录如下图：

├── app

│  ├── docker-compose.yml 

│  ├── nginx_config

│  │  └── site.conf #nginx配置文件，核心配置是这行: fastcgi_pass  fpm:9000;

│  ├── php_config

│  │  └── php.ini

│  └── www.example.com #工程根目录，建议建立软链

└── logs #nginx日志



目录尽量都给全部读写权限，如 logs,  www.example.com 目录

操作步骤：

1、拉本工程代码

2、WSL2 下安装Docker

3、导入自制Docker镜像

4、工程目录软链到 www.example.com

5、启动工程(nginx + fpm)

```
#app 目录下执行
docker-compose up
```

6、绑定 host ，访问  test.admin.example.com

```
#替换<wsl ip> 为wsl实际ip地址。参考命令： ip addr |grep eth0 
<wsl ip> test.admin.example.com test.example.com
```

