0. [使用react技术栈从零开始打造在线个人简历网站（一）](#实战案例介绍)
1. [项目需求分析及组件化规划](#项目需求分析及组件化规划)
2. [搭建项目基础架构（一）](#组件化拆分)
3. [项目架构规划](#项目架构规划)
4. [跑同一个组件](#跑同一个组件)
5. [添加container下各组件并跑通路由](#添加container下各组件并跑通路由)
6. [使用React动画组件实现页面切换的动画和过渡效果](#使用React动画组件实现页面切换的动画和过渡效果)
7. [NavMenu导航组件开发3](#NavMenu导航组件开发3)
8. [实现collapse折叠功能](#实现collapse折叠功能)
9. [实现路由激活状态的样式](#实现路由激活状态的样式)
10. [目录层级调整和项目首页开发](#目录层级调整和项目首页开发)
11. [Project组件开发](#Project组件开发)
12. [Contact组件开发](#Contact组件开发)
#《使用react技术栈从零开始打造在线个人简历网站（一）》

##实战案例介绍
首页、个人介绍、专业技能、项目经验、联系我等内容。预览地址 (zhuchaoyang.github.io)。

##项目过程中会使用的技术点
- 基础的Shell、Chrome浏览器、Atom代码编辑器、Terminal终端、Node.js全局环境
- 最新的ES6/7 新语法特性、Babel编译器的使用和配置
- Git基本操作、NPM和Yarn的使用
- 全新的Webpack2 和 Webpack-dev-server、以及系列插件和loader的配置及使用
- 最新版React、React-dom以及react-addons-css-transition-group动画
- 路由系统React-router
- Axios实现HTTP请求和Promise数据处理
- 目录划分、分层、优良的代码组织方式等项目架构指导


#项目需求分析及组件化规划
>制作一个属于自己的个人简历网站，采用SPA架构进行开发

##需求分析
- 首页开发
	- 公共 layout 部分结合 react-addons-css-transition-group 实现CSS3过渡效果
	- 公共左侧导航组件开发，需要结合使用 react-router 实现前端理由的控制
	- 底部页面切换的过渡组件开发，这个地方
- “关于我”页面、“专业技能”页面、“联系我”页面
	- 主要涉及通用布局组件的封装
	- 以及数据和组件的结合渲染
- “项目经验”页面
	- 功能描述：需要使用Github Open API将Github上的个人信息拉取过来，并结合axios这个库封装公共方法，将数据抓取过来后进行展示
	- 需要利用antd的Timeline组件进行项目展示组件封装，将数据导入展示

##组件化拆分
- 容器型组件（Containers）
	- Home组件
	- About组件
	- Contact组件
	- Skills组件
	- Project组件
- 布局类组件（Layout）
	- NavMenu组件
	- Main组件
- 展示型组件（component）
	- 待定

#搭建项目基础架构（一）
- 虽说基础，但内容很重要
- 实践操作不难，但涉及的技术点很多
- 文档详细，零基础也能跟上

##初始化项目

```
sudu npm install yarn -g
```

```
mkdir react-resume && cd react-resume
git init
touch .gitignore README.md CHANGELOG.md LICENSE
mkdir src && cd src && touch index.html main.js main.css
cd ..
```

##安装依赖包


#项目架构规划
>一个项目写的怎么样，前期的架构很重要

##目录和文件
- src
	- assets 公共静态资源
	- components 展示型组件
	- containers 容器型组件
	- layouts 布局类组件
	- routes 路由
	- redux
	- utils

**组件：一个组件一个文件夹，文件夹内包含组件所有的js、css、json、redux相关的action和reducer等(高内聚，单独管理)**

#跑同一个组件

#添加container下各组件并跑通路由
>目标：实现项目的前端路由

- 首先要完善containers下各个路由
- 修改layout下的App组件
- 配置路由文件

#使用React动画组件实现页面切换的动画和过渡效果
>目标：学习如何使用组件，并且使用css美化应用

- 组件：`react-addons-css-transition-group`
	- 在React组件进入或者离开DOM的时候，它是一种简单地执行CSS过渡和动画的方式。
- 应用到App组件
- 使用CSS3 transition 和 transform 添加过渡效果

#NavMenu导航组件开发3
- 新增fonts图标字体库美化组件展示
- file-loader 和 url-loader安装
- 以及webpack配置
- 组件中增加inconfont
- 优化CSS

#实现collapse折叠功能
- 控制组件的展示是否折叠，其实控制组件的对应状态即可
	- state -> collpase
- 对应的，通过collpase这个state来确定样式className
	- collpase -> className -> 样式

#实现路由激活状态的样式
>本质还是修改`activeClass`

- anrd -> Menu组件
	- selectedKeys 当前选中的菜单项key数组string[]
	- defaultSelectedKeys初始选中的菜单项key数组string[]

- 解析url -> 拿到hash -> hash值作为state传入组件 -> selectedKeys
- 什么时候改变state -> componentDidUpdate

#目录层级调整和项目首页开发

##目录层级
>示例：App组件资源维护

- App
	- index.js
	- index.css
	- test.spec.js
	- mock.json
	- index.less
	- img/
	- action.js
	- constant.js
	- reducer.js

#首页开发

- Home组件
- 组件样式
	- 用到部分CSS3相关的属性和布局方式

#Project组件开发

- 将Github上个人的开源项目的基本信息拉过来展示
- axios -> 一个基于promise的HTTP库
- antd ->TimeLine时间轴组件 & Timeline.Item 组件的应用
- 组件样式优化

#Contact组件开发

- 整体还是偏样式，难度不大
- 会有一些小技巧 & Modal组件的使用
