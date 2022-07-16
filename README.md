# DevShell

Shell脚本备忘录

### SSH端口修改配置

注：以下为CentOS 7配置命令

查看当前SSH端口
```
netstat -anp | grep ssh
```

编辑SSH配置文件
```
vim /etc/ssh/sshd_config
```

查看防火墙状态
```
firewall-cmd --state
```
注：若防火墙未开启，可忽略

查看防火墙开放端口
```
firewall-cmd --list-ports
```

防火墙添加开放端口
```
firewall-cmd --zone=public --add-port=13000/tcp --permanent
firewall-cmd --reload
firewall-cmd --zone=public --query-port=13000/tcp
```

重启SSH服务
```
systemctl restart sshd.service
```