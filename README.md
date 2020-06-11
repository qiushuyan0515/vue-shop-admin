# vue-shop-admin

Vue 实战项目：电商管理系统（Element-UI）

### 优化策略

- 生成打包报告
- 第三方库启用 CDN
- elementUI 按需加载
- 路由懒加载
- 首页内容定制

插件 babel-plugin-transform-remove-console 去除 `console语句` 的操作,在 babel.config.js 文件 添加 transform-remove-console

#### 打包报告

1. 通过 vue-cli 命令选项 `vue-cli-service build --report`
2. 通过可视化 UI 面板查看，控制台和分析

#### 不同配置打包

详见 vue.config.js

#### 加载 CDN 资源

import 语法引进的第三方依赖包，最终打包合并在一个文件里，体积过大
通过 webpack 的 externals 节点，配置并加载 外部 CDN 资源

#### 路由的懒加载

打包后，JavaScript 包变得很大，影响页面加载。把不同的路由对应的组件分割成不同的代码块。对应的路由加载对应的组件

1. 安装 @babel/plugin-syntax-dynamic-import 包
2. 在 babel.congfig.js 配置文件中声明该插件
3. 将路由改为按需加载形式

### 通过 node 创建 web 服务器

1. 新建 vue_shop_server 文件夹
2. npm init -y 初始化
3. npm i express -S

#### PM2

1. 在服务器中安装 pm2： npm i pm2 -g
2. 启动项目： pm2 start 脚本 --name 自定义名称
3. 查看运行项目： pm2 ls
4. 重启项目： pm2 restart 自定义名称
5. 停止项目： pm2 stop 自定义名称
6. 删除项目： pm2 delete 自定义名称
