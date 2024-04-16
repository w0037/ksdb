# mysql-ksDB

## 特点
mysql-ksDB是一款MySQL数据库管理工具，具有以下特点：

- 支持数据库备份还原和添加数据库功能。
- 自动生成数据库设计文档，支持Markdown格式以及实时预览，并可下载成PDF或Word文件。
- 提供数据表名、注释、自增ID的更改功能，支持优化表、修复表、删除表和清空表操作。
- 允许查看、编辑、新增和复制任意表数据。
- 可执行SQL文件，并查看执行后的数据结果。
- 支持字段名、注释、默认值、排序的修改，可拖拽排序字段，也可删除字段。
- 可连接和管理多个外部数据库，支持通过SSH连接外部数据库，还可导入PEM文件进行连接。
- 提供数据库表保护功能。
- 实现了精细化的权限控制，支持多角色多用户管理。
- 提供查询每个用户操作记录的功能，方便回查。

## 安装步骤
1. 如果未安装PNPM，需要先安装PNPM：
   ```
   npm i pnpm -g
   ```
2. 安装依赖：
   ```
   pnpm i
   ```
3. 导入`data/mysql-ksDB.sql`数据库文件，并修改`src/config/adapter.js`中的数据库配置信息。

## 启动服务
```
npm start
```

## 正式环境部署
```
pm2 start pm2.json
# pm2 reload pm2.json //重新加载
```

## 默认登录信息
- 账号：admin
- 密码：admin 



## 解决PNPM安装缓慢的问题
如果不需要安装电脑版，则删除`package.json`中的以下内容：
```
"electron": "^26.0.0"
```

## 支持SQLite
- 如果需要支持SQLite，执行以下步骤：
  1. 安装SQLite库（可能下载时间较长）：
     ```
     pnpm i think-model-sqlite -s
     ```
  2. 在`src/config/adapter.js`中取消第五行的注释：
     ```
     const sqlite = require('think-model-sqlite');
     ```
  3. 同时取消第49行到55行的注释：
     ```
     // sqlite: {
     //   handle: sqlite, // Adapter handle
     //   path: path.join(think.ROOT_PATH, 'data/sqlite'), // sqlite 保存的目录
     //   database: 'mysql-ksDB', // 数据库名
     //   connectionLimit: 1, // 连接池的连接个数，默认为 1
     //   prefix: 'rt_', // 数据表前缀，如果一个数据库里有多个项目，那项目之间的数据表可以通过前缀来区分
     // }
     ```
  4. 重启程序。



## 开源说明
- 本项目永久免费开源。
- 允许企业和个人单独使用。
- 如用于商业活动或二次开发后发售，请购买相关版权。
- 不提供私下维护工作，如有Bug，请通过[issues](https://gitee.com/prilidianohussey_admin/mysql-ksDBs)提交。
- 请尊重作者的劳动成果。
