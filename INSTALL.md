# 安装依赖
主要参考[手动部署LNMP环境](https://help.aliyun.com/document_detail/97251.html)
* nginx
* 数据库(三个选择一个即可)
    - MySQL：5.5.3 或者更高版本 (因为收费问题，centos 已经不支持)
    - mariadb: 3.10.3
    - SQLite: 3.7.11 或者更高版本
    - PostgreSQL：9.1 或者更高版本
* php 7.2 或者更高版本

## 安装 nginx
安装对应的包
```shell
yum install -y pcre-devel  zlib-devel  openssl openssl-devel nginx
```

添加 nginx 程序运行时使用的用户
```shell
useradd -M -s /sbin/nologin nginx
```

配置 nginx
备份原始配置文件
```shell
cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.bak
```

启动 nginx 服务
```shell
systemctl start nginx 
```

设置开机启动
```shell
systemctl enable nginx
```

## 安装 MySQL
安装对应的包
```shell
yum install -y cmake ncurses-devel mysql
```

#启动 mysql 服务
#```shell
#systemctl start mysqld
#```
#
#设置开机启动
#```shell
#systemctl enable mysqld
#systemctl daemon-reload
#```

## 安装 php
安装对应的包
```shell
yum install -y libxml2-devel libjpeg-turbo-devel freetype-devel libpng-devel gd-devel libcurl-devel php php-fpm php-mbstring 
```
