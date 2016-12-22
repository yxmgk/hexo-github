## 静态博客生成器hexo
+ hexo是一个基于node.js开发的静态博客生成器，可以用来快速创建一个个人博客
+ 安装 
```bash
npm install hexo-cli -g
```
+ hexo init 博客目录名称
	- 该过程需要联网
	- 它有一个基本的博客模板，在github上，需要联网下载
	- 下载完自动执行`npm install`命令来安装依赖包
	- 第一次需要安装
+ cd 博客目录
+ hexo server
	- 在本地启动当前博客，可以在本地实现预览效果：复制running at 后的地址到浏览器中查看
+ 写自己的博客
	- hexo new 文章名称（必须.md文件，此时不管加不加后缀，默认都会给你加上.md解析，所以不用加.md）
+ 生成静态文件
```bash
hexo generate
```
	- 该命令会把所有的md文件以及其他资源生成到public目录中
	- 生成结束之后可以把public丢到web容器中，然后就可以直接访问了，就不需要依赖于hexo了（可以是apache或其他web服务器中即可）

## 将自己的博客放到github线上
### github pages
	- 它提供了一个免费的静态资源托管服务，可以把你的静态资源托管到这个服务上。
+ 在github中新建一个仓库
	- 此时的名字必须是你的账户名.github.io,复制https地址
+ 在blog(你的博客名字)所在位置打开git bash here
+ 复制远程仓库
```bash
git clone https://github.com/yxmgk/yxmgk.github.io.git
```
+ 打开所在文件夹（即你创建的远程仓库名称github.io）,将它内博的.git文件夹复制到你创建的博客文件夹中的public文件夹中
+ 在public文件夹位置，右键打开git bash here
+ 使用git status查看状态
+ 工作区到暂存区
```bash
git add --all
```
+ 暂存区到本地仓库
```bash
git commit -m "描述信息"
```
+ 本地仓库到github上
```bash
git push
```
## 另一种方式
+ 在自己的博客目录文件夹中中打开public文件夹，右键git bash here命令行
+ 初始化一个仓库
```bash
git init
```
+ 使用git status可查看状态
+ 添加工作区所有文件（使用--all或者.都可以）到暂存区
```bash
git add --all
```
+ 添加工作区文件到本地仓库
```bash
git commit -m "描述信息"
```
+ 添加你要push到的远程仓库
```bash
git remote add 别名（好比IP地址起域名，一般使用origin） 你创建的远程仓库的地址
```
+ 将文件push到你的远程仓库，origin表示给该地址起了个名字，master表示主分支
```bash
git push origin master
```

### 注意
+ 删除.git文件夹命令
```bash
rm -rf .git
```