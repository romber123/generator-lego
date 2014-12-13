# generator-lego

> *generator-lego* 基于gulp的前端工作流


### <a name="top"></a>目录
* [主要功能](#intro)
* [快速开始](#quick-start)
* [文件结构](#file-tree)
* [环境准备](#sys-env)
* [任务说明](#task-dtls)
* [Demo](#show-case)
* [已知问题](#known-issues)
* [License](#license)


### <a name="intro"></a>主要功能 [[⬆]](#top)
这是一个帮助前端开发工程师简化工作的工具，它的主要功能是：

* webserver
* 保存文件时，自动刷新浏览器
* 初始化项目目录结构及文件
* 自动编译sass
* 自动补全css3浏览器前缀
* 支持ejs模板
* 多雪碧图合并、2x拼图
* 压缩图片
* 发布到svn
* 打包


### <a name="quick-start"></a>快速开始 [[⬆]](#top)
提供以下2种获取方式：	

1. npm
	* `npm install -g generator-lego`
	* 在任意空目录执行 `yo lego` 初始化项目

2. Clone the repo
	* `git clone git@github.com:duowan/generator-lego.git`
	* 在克隆目录执行 `npm link` 链接到全局模块的位置
	* 在任意空目录执行 `yo lego` 初始化项目

### <a name="file-tree"></a>文件结构 [[⬆]](#top)
`generator-lego` 初始化和执行任务涉及的文件结构：

```
yourProj/
│
├── package.json                // 项目依赖定义
├── gulp.js                     // 配置任务
│
├── node_modules    			  // `npm install` 拉取依赖包
│
├── src/                        // 开发目录
│    ├── css/                   
│    │   └── global.css         // 经过sass编译后的出口css文件
│    ├── sass/                  // sass源文件
│    ├── img/                   // 仅 Copy 不做操作
│    ├── js/                    // 仅 Copy 不做操作
│    ├── tpl/                   // 仅 Copy 不做操作，用来存放ejs模板
│    └── index.html             
│    
└── dest/                       // 发布目录，执行 `gulp release` 生成
    ├── css/                    
    │   └── global.css
    ├── img/                   
    ├── js/                     
    └── index.html               
```

### <a name="sys-env"></a>环境准备 [[⬆]](#top)
1. Node 环境：*默认此步骤已完成*  （Mac用户建议使用 [Brew] 安装 [Node.js]） 
2. Yeoman环境：`npm install -g yo`
3. Gulp 环境：`npm install -g gulp`
4. 图片编辑环境：
	* `brew install GraphicsMagick`
	* `brew install phantomjs`

### <a name="task-dtls"></a>任务说明 [[⬆]](#top)
#### 初始化项目
* 执行`yo lego:fe`

#### 开发
* `gulp` 创建一个链接，自动检测`src`文件夹下的静态文件，自动刷新。支持sass编译。

#### 构建
* `gulp release` 将静态文件压缩到 `dest/`，该阶段会执行雪碧图合并。

#### 发布
* `gulp publish` 将静态文件提交到svn资源服务器。

#### 打包
* `gulp zip` ，替换构建后代码资源路径为线上路径，将源码和构建后代码压缩成一个zip包。

#### 其他命令参数
1. `gulp [-p <port>] [-w] `
	* `-p` port 的简写，给webserver指定端口号；此参数需要指定参数值作为端口号，如：8080
	* `-w` watch 的简写，检测slice文件夹，自动生成scss样式；此参数不需指定参数值

2. `gulp release [-p <port>] [-t]`
	* `-p` port 的简写，给webserver指定端口号；此参数需要指定参数值作为端口号，如：8080
	* `-t` timestamp 的简写，给css文件的图片请求打上时间戳；此参数不需指定参数值

3. `gulp publish [-m <message>]`
	* `-m` message 的简写，提交的svn的注释；此参数需要指定参数值


### <a name="show-case"></a>Demo [[⬆]](#top)
![showcase01](https://cloud.githubusercontent.com/assets/1762523/4558145/146cf2e4-4edc-11e4-8e21-9d408776a14d.gif)

### <a name="known-issues"></a>已知问题 [[⬆]](#top)


### <a name="license"></a>License [[⬆]](#top)
Released under [MIT] LICENSE


---
[Brew]: http://brew.sh/
[Node.js]: http://nodejs.org/
[yeoman]:http://yeoman.io/
[gulp]:https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md#getting-started
[MIT]: http://rem.mit-license.org/

