	```
cp env-example .env
docker-compose up -d nginx mysql redis beanstalkd
```
打开项目的 .env 文件并添加如下配置：
```
DB_HOST=mysql
REDIS_HOST=redis
QUEUE_HOST=beanstalkd
```
在 laradock 父级目录下创建一个与 laradock 同级的 wwwroot 目录，然后在 wwwroot 目录下运行 laravel new project_tyy 命令创建一个新的 Laravel 应用
然后我们需要到 laradock 下编辑 .env 中的 APPLICATION 配置项：
```
APP_CODE_PATH_HOST
APPLICATION=../wwwroot/

```
这样就相当于为 wwwroot 与 Docker 的 /var/www 目录建立了软链接，然后我们修改 laradock/nginx/sites/default.conf 中的映射关系：
```
root /var/www/project_tyy/public
```

```
cd project_tyy
npm install  //安装依赖
```

首先还是通过 Composer 安装一个全新的聊天室应用：
```
 composer create-project laravel/laravel chatroom --prefer-dist
```

参考路径
http://laravelacademy.org/post/7691.html
https://blog.csdn.net/mrzhouxiaofei/article/details/78015473
https://blog.csdn.net/shangyanaf/article/details/79465877
https://blog.csdn.net/weixin_39756851/article/details/78276195?locationNum=3&fps=1
聊天室连接：
http://laravelacademy.org/post/9408.html
