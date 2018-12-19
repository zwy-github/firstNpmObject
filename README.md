1. 在npm网站注册个人npm账户
https://www.npmjs.com/signup

2. 完成注册后进入终端登录个人npm账号
```
$ npm login
```
登陆后可以用
```
$ npm whoami
```
来查看账号是否登陆

3.在github上建立自己的项目，打开终端，选择合适的文件夹，克隆项目，打开项目文件，npm init初始化项目

4.写一个react组件

```
import React, { Component } from 'react';

export default class Button extends Component {
    render() {
        return(
            <div>
                <button>组件按钮</button>
            </div>
        )
    }
}
```
5.最外层建立一个主文件index.js，引入组件

```
import Button from './src/components/Button';

module.exports = {
    Button
}
```
6.新建.babelrc文件

```
{
  "presets": ['react', 'es2015'],
  "plugins": ['transform-react-jsx']
}
```

7.package.json写入

```
"main": "lib/index.js",
  "scripts": {
    "build": "babel src --out-dir lib"
  },
```
项目详情查看：https://github.com/zwy-github/firstNpmObject

 7.在项目里执行 npm run build生成lib文件

 8.可以发布啦

```
$ npm publish
```
9.你可以通过npm install来安装你的组件了

后续：

- 你可以在 https://www.npmjs.com/signup 上查看你的组件

- npm对包名的限制：不能有大写字母/空格/下滑线，不能和已有的名字重复!

- 版本就是项目package.json里面的name和version

- 可以用以下命令删除包
```
$ npm unpublish 包名字 --force
```
- 修改内容后package.json里面的version一定要更新才可以再次发布，执行 $ npm version patch可以自动更新version（npm项目版本管理详情可查看
https://blog.csdn.net/znyaiw/article/details/80199457
）
