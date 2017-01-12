# git_memo
## config
```shell
git config {option}
```
## checkout remote branch to local branch
```shell
git checkout -b {local_branch_name} {origin/remote_branch_name}
```

## Line Break CRLF 16/8/19
```shell
git config core.autocrlf
true
git config --global core.autocrlf false
git config core.autocrlf
false
```
* [ref](http://ja.stackoverflow.com/questions/26663/source-tree%E3%81%A7%E6%94%B9%E8%A1%8C%E3%82%B3%E3%83%BC%E3%83%89%E3%81%8C%E8%87%AA%E5%8B%95%E7%9A%84%E3%81%ABcrlf%E3%81%AB%E5%A4%89%E6%8F%9B%E3%81%95%E3%82%8C%E3%81%A6%E3%81%97%E3%81%BE%E3%81%86%E2%86%92%E8%A8%AD%E5%AE%9A%E6%B3%95%E3%81%AF)

## Commands
* ls: git ls-files
* commit back: git rest --hard *hash*
* [Cancdl(Reset) git add](http://qiita.com/nabezokodaikon/items/7ee4900d28d8d863978e)
  - git rest HEAD {file_name}
  - git reset --soft
    *ワークディレクトリの内容はそのままでコミットだけを取り消す*
  - git reset --hard
    *コミット取り消した上でワークディレクトリの内容も書き換える*
* [Push local branch to remote branch](http://sessan.hatenablog.com/entry/2012/06/20/205036)
  - git checkout {local_branch_name}
  - git origin {remote_branch_name}

* [Delete](http://qiita.com/ytkt/items/a2afd6be8e4f06c1ea25)
  - git rm {file_name}
  - git rm -r {dir_name}
  - git rm --cached {file_name} *ファイルを残してgitの管理対象外にする*

* [Stash](http://qiita.com/fukajun/items/41288806e4733cb9c342)
  - git stash (save) ("foovarbuz")
  - git stash save -u
    *with untrack files*
  - git stash list
    - confirm changes: git stash -p
  - git stash show {stash_name}
  - git stash show -p {stash_name}
    *show files diff*
  - git stash show <適用したstash名> -p | git apply -R
    *apply で復活して取り消しいたい場合、git stash show -p パッチ形式で出力、git apply -R でパッチを逆に適用*
  - git stash apply stash@{0}
  - git stash drop stash@{0}
  - git stash pop
    *apply update stash, delete old*
  - git stash pos stash@{N}
    *apply N stash, delele old*

* [Checkout](http://sessan.hatenablog.com/entry/2012/11/04/132746)
  - git branch -a
  - git fetch
  - git checout -b {your_branch_name} {origin/remote_branch_name}
    *-b: automatic branch checkout*

* [Ammend](http://d.hatena.ne.jp/mrgoofy33/20100910/1284069468)
  - git commit --amend -m ''
  **「git commit --amend」を使用した場合、元のコミットを上書きするのではなく、元のコミットを無効にして、新たなコミットを作るという動作**

* [Show log](http://kray.jp/blog/git-why-explanation/)
  - git show HEAD
  - git show HEAD^^
    *最新の2つ前にログを見る HEAD~2 も同じ*
