## 一.引言
最近舍友极力向我推荐GitKraken（一款可视化git工具），我抵不住"诱惑"，下载尝试，却不料似乎从6.5.0以后，该软件便开始收费(只有7天试用期)。经过不懈搜索和测试，找到了下面的解决办法，分享给大家。
## 二.环境需要
 - Node.js v12 LTS or later
 - yarn
## 三.安装与激活

 1.  **修改电脑hosts文件**(通常在目录C:\Windows\System32\drivers\etc下)
	
        在文件最后一行添加 `127.0.0.1 release.gitkraken.com`以阻止GitKraken自动更新
 2. **安装**[GitKraken7.4.0](https://download.csdn.net/download/shaxiu0213/15767062)并登录
![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c2f6bfab719b40e7af8e36e2cd86c853~tplv-k3u1fbpfcp-zoom-1.image)
登陆后可以在软件最下面看到试用期还剩6天
![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/545251323eef41e7816650fb74331d4d~tplv-k3u1fbpfcp-zoom-1.image)

 3. **安装脚本**(https://github.com/5cr1pt/GitCracken)
 依次执行以下代码（前提是已经配置好了nodejs yarn）
```bash
git clone https://github.com/5cr1pt/GitCracken.git
cd GitCracken/GitCracken/
del yarn.lock
yarn install
yarn build
node dist/bin/gitcracken.js patcher
```
若出现patching done则成功
 

 
![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8b4853aeaae94eff8f864c4c4e5bad4b~tplv-k3u1fbpfcp-zoom-1.image)关闭GitKraken重新打开，NICE！
![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a0242b3ea3294183a9679dbbc7a147b2~tplv-k3u1fbpfcp-zoom-1.image)
## 四.可能存在的问题
目前只测试了7.4.0，之前使用6.5.0会出现报错

`(node:5812) UnhandledPromiseRejectionWarning: Error: ENOENT: no such file or directory, open 'C:\Users\user\AppData\Local\gitkraken\a
pp-7.4.0\resources\app\static\index.js'`
卸载安装7.4.0可解决问题



希望对你有帮助，谢谢！
