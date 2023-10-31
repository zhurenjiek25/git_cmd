## 创建git project并提交已有代码

- `cd existing_repo`
- `git remote add origin https://www.jshx-wh.cn:18600/robot/test.git`
- `git checkout -b develop`
- `git add .`
- `git commit -m "first commit"`
- `git push origin develop`

## 拉取git已有远程project并切换分支

- `git clone https://github.com/********`
- `cd existing_repo`
- 查看所有本地与远程分支 `git branch -a`
- `git checkout -b develop origin/develop`

## 添加并提交子模块

- `cd main-project`
- `git submodule add -b branch1 origin https://github.com/******** src/module1`
- `git commit -m "add submodule"`
- `git pull origin develop`
- `git push origin develop`

## 更新子模块

- `cd main-project`
- `git submodule update --init --recursive`

## 删除子模块

- 删除main project 的 .gitmodules 文件中的相关条目，如果需要删除所有子模块， 整个文件需要删除
- 删除main project 的 .git/config 配置项中子模块相关条目
- 删除main project 的 .git/module/* 的子模块目录， 每个子模块对应一个目录，注意只删除对应子模块目录即可
- 删除子模块的目录以及内容
- 删除缓存区子模块相关条目
- `git rm --cached src/module1`
- 提交修改
- `cd main-project`
- `git commit -m "remove submodule module1"`

## 删除子模块，方法2实例

- `git submodule deinit submodule-test`
- `git rm submodule-test`
- `rm -rf .git/modules/submodule-test`
