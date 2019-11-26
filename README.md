# 分支说明

master 主分支（主分支负责人专用，合并master-test,用于发布到正式环境）

master-test 测试分支 （测试人员专用，合并master-dev分支，用于测试）

master-dev 开发分支  （开发人员专用，合并需求分支，BUG分支，用于开发）

#### 简称说明

d, demand, 需求

b, bug, BUG

t, temp, 临时

name, 自己给这个分支起的名字，方便自己一看就明白这个需求是做什么的

#### 例如

zhoujun-d1-name  禅道需求1分支

zhoujun-d2-name   禅道需求2分支

zhoujun-d2-name   禅道需求3分支

.............

zhoujun-b1-name   需求1Bug分支

zhoujun-b2-name   需求2Bug分支

zhoujun-b3-name   需求3Bug分支

.....................

临时情况的，比如突然说网页上有文字要修改的
切换到主分支，然后创建临时分支，改好后，通知负责管理主分支的人合并临时分支

zhoujun-t1-name   临时1



# 开发流程

#### 第一步，创建需求分支1
```
git checkout master-dev
git pull
git checkout -b zhoujun-d1-name

```
#### 第二步，修改代码，提交到本地

```
   git status
   git add 指定路径或者文件名  或者 git add .
   git commit -m 'd1-修改日志'
```
#### 第三步，提交到远程
  如果是第一次，使用
  
```
 git push --set-upstream origin zhoujun-d1-name
```

  如果是以后
  
```
git push 
```

#### 第四步，需求做完后，切换到开发分支
```
git checkout master-dev
```
#### 第五步，拉取代码，防止别人修改提交过
```
git pull
```

#### 第六步，合并刚才做的需求

```
git merge zhoujun-d1-name
```

#### 第七步，提交代码，告诉测试可以测试

```
git push
```

# 测试流程

#### 第一步，检出开发分支,并拉取代码

```
git checkout master-dev
git pull

```

#### 第二步，检出测试发分支,并拉取代码

```
git checkout master-test
git pull

```

#### 第三步，合并开发分支代码

```
git merge master-dev
```

#### 提交合并后的代码，提交测试

```
git push
```





# 其他命令


## 将远程git仓库里的指定分支拉取到本地
```
git checkout -b master-test origin/master-test
```
## 删除分支 

```
git branch -d zhoujun-d1-name
```

   




