
发布系统  简单有效的版本发布工具，标准化了从开发环境到测试环境到预发布环境（灰度环境）生产环境的发布流程规范


- 支持gitlab身份验证
- 支持用户权限
- 支持分支过滤
- 支持发布前后执行命令
- 支持忽略文件
- 支持版本历史记录
- 结合cstenv实现灰度、预发布功能，可对上一版本秒回滚


**依赖**

-   gitlab
-   bash(git,rsync,ssh)
-   python2.7(编译后可选)

**配置文件**

默认存放在/etc/pbsys/conf.ini或当前目录下conf.ini  
版本记录配置文件存放在workdirs/vercnf  
conf.ini格式：  

[GITS]  
address = 〈gitlab库地址〉   
addretk = 〈toker〉  
sshport = <ssh端口〉  
brannot	= master,develop 〈不显示的分支〉  

[PATH]  
workdirs = /var/opt/pbsys/repo 〈缓存目录〉  
confdirs = /var/opt/pbsys/config_dir 〈配置目录〉  
excludef = /etc/pbsys/exclude.file 〈忽略文件信息〉  
keysdire = /etc/pbsys/keys 〈key存放目录〉  
deploykf = global_key 〈gitlab的部署key〉  

[SERVER]  
produ_cst.hostname=10.10.10.1 <定义服务器信息>  
produ_cst.username=www  
produ_cst.pkeyfile=rsawww  
produ_cst.password=  
produ_cst.branchpx = release_|pre_  
produ_cst.port=22  

[REPO]


produ_cst_4snewapi_pre-pc.chexiu.cn.projitem=pc.chexiu.cn 〈定义库信息〉  
produ_cst_4snewapi_pre-pc.chexiu.cn.servname=produ_cst  
produ_cst_4snewapi_pre-pc.chexiu.cn.cmdexecu=pwd,chmod +x /data0/data0/htdocs/4snewapi_pre/init
produ_cst_4snewapi_pre-pc.chexiu.cn.syncdirs=/data0/data0/htdocs/4snewapi_pre  
produ_cst_4snewapi_pre-pc.chexiu.cn.permissi=zhujintao,pavle  
produ_cst_4snewapi_pre-pc.chexiu.cn.abgraypt=/data0/data0/abgrays/4snewapi_abgray.ini  

produ_cst_4snewapi-pc.chexiu.cn.projitem=pc.chexiu.cn  
produ_cst_4snewapi-pc.chexiu.cn.servname=produ_cst  
produ_cst_4snewapi-pc.chexiu.cn.cmdexecu=pwd,chmod +x /data0/data0/htdocs/4snewapi/init  
produ_cst_4snewapi-pc.chexiu.cn.syncdirs=/data0/data0/htdocs/4snewapi  
produ_cst_4snewapi-pc.chexiu.cn.permissi=zhujintao  
produ_cst_4snewapi-pc.chexiu.cn.abgraypt=  
produ_cst_4snewapi-pc.chexiu.cn.administ=produ_cst_4snewapi_pre-pc.chexiu.cn  

**使用方法**

 nohup ./pbSys 0.0.0.0:3333 & (default:3001) 


**截图**

![](https://i.imgur.com/dP3Vtdu.png)

![](https://i.imgur.com/vRoy42q.png)
