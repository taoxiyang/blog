---
title: Hexo搭建过程
date: 2019-06-24 16:37:07
tags:
- Hexo
---

### 安装前提

- [Node.js](https://nodejs.org/zh-cn/)
- [git](https://git-scm.com/)

先安装好node和git，安装的过程比较简单

安装好之后，使用npm安装Hexo就可以了

```
npm install hexo-cli -g
```

### 解决npm全局安装的权限问题
注意，这里非常容易报一些权限问题，解决的办法可以参考[npm官方的解决方案](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)
  

1. 在用户的home目录，创建一个文件夹，用于npm全局的安装

	``` 
	$ mkdir ~/.npm-global 
	```
2. 配置npm使用新的目录路径
	
	``` 
	$ npm config set prefix '~/.npm-global 
	```
3. 配置.profile
	
	``` 
	$ export PATH=~/.npm-global/bin:$PATH 
	```
4. 更新系统变量，使配置生效
	
	``` 
	$ source ~/.profile 
	```
5. 测试一下
	
	``` 
	$ npm install -g jshint 
	```
### 创建自己的博客工程

安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```
$ hexo init <folder>
$ cd <folder>
$ npm install
```

生成静态文件  

```
hexo generate
```

启动服务器  
```
hexo server
```

该命令会在[本地4000端](localhost:4000)口启动一个web服务，一切正常的话就能看到如下页面了

{% asset_img blog_init.jpeg This is an example image %}

到此，Hexo的博客就搭建完成了。