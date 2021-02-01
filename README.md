# note-git
给工作中遇到的git腾个地儿

## `git cherry--pick <commit-id>`
将指定的提交(commit) 应用于 其他branch
阮一封的blog：http://www.ruanyifeng.com/blog/2020/04/git-cherry-pick.html

基本命令：       
```shell
git checkout <将要应用于的branch>

git cherry-pick <commit-id>
```

1. 两个不同的需求开发分支(branch-a, branch-b)，其中发现2个分支中有可复用/ 或依赖的新开发的模块，那么可以使用此命令
>> branch-a 昨天开发了一个基础模块basic module，假设提交的commit-id是：commit-id-aas-asdf-24-34-2-2343
>> branch-b 今天发现branch-a已经开发了basic module，但是basic module 并不是一两句代码的事儿，自行开发还得花时间
>> 
```shell 
git checkout branch-b

git cherry-pick commit-id-aas-asdf-24-34-2-2343
```


2. 用作代码备份：1个需求按照模块开发完事儿了，突然得知某个模块有变更，不在此次上线范围，代码删了就可惜了
>> 新建一个分支，将不上线的模块代码的commit 拷贝过来
