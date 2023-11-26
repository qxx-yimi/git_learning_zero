## Git&GitHub&GitLab

~~~shell
# 缺省等同于local
git config --local #只对某个仓库有效
git config --global #对当前用户的所有仓库有效
git config --system #对系统所有用户有效

#显示config配置
git config --list --local
git config --list --global
git config --list --system

#配置用户名和邮件
git config --global user.name 'your_name'
git config --global user.email 'your_email@domain.com'

#建立Git仓库
cd directory
git init     #当前文件夹即为仓库

cd directory
git init your_project #创建新的文件夹，并设置为git仓库
cd your_project

git add filename#将文件从工作区添加到暂存区
git add -u #将已被git管理的文件，全部从工作区添加到暂存区
git add . #将所有文件从工作区添加到暂存区
git commit -m 'some message about this commit' #将文件从暂存区正式commit
git status #查看文件状态

git log #查看当前分支commit记录
git log --oneline #简略显示操作日志
git log -n #最近n条commit
git log --all --graph #以图形化的形式显示所有的分支commit记录
git log branchname #查看该分支的commit记录

git mv oldname newname #文件重命名
git rm filename #删除文件

git branch #查看本地分支
git branch -v #查看本地分支+上次提交的信息
git branch -r #查看远程分支
git branch -a #查看所有分支
git branch newbranch #创建分支
git branch -d branchname #删除分支
git branch -m oldname newname #修改分支名字
git checkout branchname #切换分支
git checkout -b branchname basecommit #创建并切换到新的分支
git checkout commit file #将file恢复到commit时候的内容

gitk #通过图形界面来展示版本历史
gitk --all #显示所有分支的版本历史

git diff commit1 commit2 [-- filename] #比较两个commit的差异
git diff --cached #比较暂存区和最后一次commit的差异
git diff #工作区和暂存区的差异

git commit --amend #修改最新commit的message
git rebase -i fathercommit #reword 修改老旧commit的message
git rebase -i fathercommit #squash 合并相邻的多个commit
git rebase -i fathercommit #squash+调整commit顺序 合并不相邻的多个commit,--root是根
git rebase --continue #继续操作

git reset HEAD #让暂存区恢复成和HEAD的一样
git reset HEAD -- file1 file2 #恢复暂存区中的部分文件与commit中的一致
git reset --hard commit #将版本库恢复到commit，其子节点会被删除
git checkout -- filename #让工作区的文件恢复成暂存区一样

git remote add reponame sshurl #添加远程仓库
git remote -v #查看远程仓库

git push reponame branchname #将branchname向远端推送 --all 推送所有分支
git fetch reponame branchname #拉取reponame的branchname分支
git merge reponame/branchname #合并分支, 新创建一个commit为两个分支的儿子
git pull = git fetch + git merge
~~~



