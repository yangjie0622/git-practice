# Git 常用命令速查

## 每天会用到的四条

```bash
git status                      # 看改了哪些文件、在哪个分支
git add .                       # 把改动放进暂存区（. 表示当前目录全部）
git commit -m "说明这次改了什么"   # 存成一个版本
git push                        # 推到远程仓库
```

## 看历史

```bash
git log --oneline --graph       # 一条条提交，带分支线
git diff                        # 还没暂存的改动具体是什么
git diff --staged               # 已经暂存的改动
```

## 分支

```bash
git branch                      # 列出本地分支，* 是当前
git switch -c feature-x         # 新建并切换分支（老写法 git checkout -b）
git switch main                 # 切回主分支
git merge feature-x             # 把 feature-x 合进当前分支
git branch -d feature-x         # 合并后删除分支
```

## 远程

```bash
git remote add origin https://github.com/用户名/仓库名.git
git remote -v                   # 查看已配置的远程地址
git push -u origin main         # 第一次推送，-u 记住上游
git pull                        # 拉取远程更新
```

## 后悔药

```bash
git restore hello.txt           # 丢弃工作区改动（回到上次提交的样子）
git restore --staged hello.txt  # 从暂存区撤出，改动还在
git commit --amend              # 修改上一条提交（补文件或改说明）
git reset --soft HEAD~1         # 撤销上一条提交，改动留在暂存区
```

## 参与别人的开源项目

```bash
# 网页上先 Fork，再下载自己那份
git clone https://github.com/你的用户名/原仓库.git
git switch -c fix-typo
git add . && git commit -m "docs: 修正拼写"
git push origin fix-typo
# 然后网页上 Compare & pull request
```
