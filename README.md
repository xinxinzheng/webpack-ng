

# BM

## 项目简介
使用 Angularjs 开发的大数据运维管理平台。

## 技术简介
* [Angular](https://angularjs.org/)
* [Gruntjs](http://gruntjs.com/)

## changelog

v.2.2.1

1. 集群扩容
2. 服务安装 节点选择优化
3. 服务安装 配置自动填充 添加配置搜索功能
4. 集群部署 安装失败节点删除bug修复
5. 集群部署 开始部署 确认提示
......

v2.2.0

1. 适配新版UI

v2.1.0.1

1. 修复服务安装自动配置填充bug 
2. 修复组件-节点列表页排序搜索 bug
3. 修复请求列表时间计算错误问题
4. 修复节点详情页无法获取可安装组件的问题
5. 优化服务配置更新提示 
......

v2.1.0

1.修复测试提出的优化与bug

## 目录设计
* `bm_web` angularjs 相关的前端源码
	* `public` 
		* `static`
			- `css` -> less编译后文件
			- `less` -> 开发样式
			- `font` -> 使用字体
			- `img` -> 使用图标
			- `scripts`
				+ `angular` -> angularjs
				+ `config`	-> js 配置
				+ `controllers` -> 控制器
				+ `filter` -> 过滤器
				+ `directive` -> 指令
				+ `service` -> 服务
				+ ...
			- `module` 	-> 第三方库，包含css/js/html等
				+ `echarts`
				+ ....

	* `views`
		- `module` ->功能模块
			+ `AlertManage` -> 告警管理
			+ `ClusterExpand` -> 集群扩容
			+ `ClusterInit` -> 集群初始化
			+ `HostManage` -> 节点管理
			+ `Overview` -> 监控
			+ `ServiceManage` -> 服务管理
			+ `SystemManage` -> 系统管理
		- `component`  -> 组件相关
		- `common` -> 布局相关		
		- `partial`		-> 子模板
	* `web` -> 编译后的目录，直接部署到 nginx 的根目录即可
		- `module`
		- `static`
		- `common`
		- `directive`
		- `partials`
		- `module`
		- `index.html`
		- `login.html`

## 准备

首先保证开发环境中有node（v4.0+）环境，如没有，请[点击安装node](https://nodejs.org/en/)

然后在全局和项目目录同时安装grunt,执行以下代码：

    npm install -g grunt

    npm install -g grunt-cli

    npm install grunt --save-dev

## 开发

在项目根目录下执行：

    npm start

打开浏览器，访问 `http://127.0.0.1:8081/` 

## 编译生成 web 目录

**发布时直接把web下的内容拷贝到部署的网站root即可**

    grunt build

