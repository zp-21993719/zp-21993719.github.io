#### 配置Docker镜像源
- 如果不存在/etc/docker/daemon.json这个配置文件，可以直接使用下面的命令：
**创建目录**
~~~
sudo mkdir -p /etc/docker
~~~
写入镜像配置
~~~
sudo tee /etc/docker/daemon.json <<-'EOF'
{
    "registry-mirrors": [
        "https://docker.m.daocloud.io",
        "https://dockerproxy.com",
        "https://docker.mirrors.ustc.edu.cn",
        "https://docker.nju.edu.cn"
    ]
}
EOF
~~~
**重启docker服务**
~~~
sudo systemctl daemon-reload
sudo systemctl restart docker
~~~
-----
- 如果已经存在/etc/docker/daemon.json这个配置文件，手动复制下面的镜像地址加如到配置中：
~~~
"registry-mirrors": [
        "https://docker.m.daocloud.io",
        "https://dockerproxy.com",
        "https://docker.mirrors.ustc.edu.cn",
        "https://docker.nju.edu.cn"
    ]
~~~

**重启Docker服务：**
~~~
sudo systemctl daemon-reload
sudo systemctl restart docker
~~~