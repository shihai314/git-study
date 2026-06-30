# git-advanced

## 一、git配置

### 1. .gitignore

#### 强制添加.gitignore 忽略的文件
	
	git add -f <file name>
	
#### 查看.gitignore策略生效行号
	
	git check-ignore -v <file name>
	
### 2. 换行符

* CR:carriage return回车，光标到首行，'\r'=return
* LF:line feed换行，光标下移一行，'\n'=newline
* linux:换行\n
* windows:换行\r\n
* MAC OS:换行\r

#### 提交时转换为LF，检出时转换为CRLF，默认设置不用修改，Git时linux配置
	git config --global core.autocrlf true
	
#### 允许提交包含混合换行符的文件
	
	git config --global core.safecrlf false
	
### 3.别名

#### 以图形的方式打印Git提交日志

	git log -pretty=gormat:'%h %ad | %s%d' -graph -date=short
	
#### 设置别名

	git config --global alias.ci commit
	
## 二、git协议

### 1.本地协议

#### 克隆本地仓库
	
	git clone /c/wd/test.git

#### 克隆本地仓库，不建议使用file://

	git clone /file:///c/wd/test.git
	
#### 添加远程仓库的链接

	git remote add origin /c/wd/test.git
	
### 2.HTTP协议

#### 克隆远程仓库

	git clone https://github.com/shihai314/test.git

#### 添加远程仓库的链接

	git remote add origin https://github.com/shihai314/test.git
	
### 3.SSH协议

#### 克隆远程仓库，一般写成简短的命令

	git clone ssh://git@github.com/shihai314/test.git
	git clone git@github.com:shihai314/test.git

#### 添加远程仓库的链接

	git remote add origin git@github.com:shihai314/test.git

#### 生成RSA密钥对
	ssh-Keygen -t rsa -C "your email"
	
#### 在Github网站添加公钥

#### 使用SSH协议，克隆仓库或者添加远程链接

## 三、Git基本操作

### 1.新Git命令

#### git命令信息
	git
	
#### 查看全部git子命令

	git help -a
	
#### 逐行查看文件的修改历史

	git blame <file name>
	
#### 从第100行开始，到110行。逐行查看文件的修改历史

	git blame -L 100,10 <file name>
	

#### 列出打算清除的档案

	git clean -n
	
#### 真正的删除

	git clean -f
	
#### 连.gitignore 中忽略的档案也清除

	git clean -x
