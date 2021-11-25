# GIT<br>
<br>
git checkout -b <branchname>    // creates new branch and checkout<br>
git branch -D <branchname>      // delete branch<br>
git branch -a                   // list all branches<br>
git reset                       // unstage files, add filename if you want to remove specific file<br>
git log --oneline               // all commits <br>
git commit -am 'message'        // shorter way to commit if no new files added, only for modified files<br>
git commit --amend --no-edit    // adding staged files to last commit ,instead of creating new one <br>
<br>
// Fetch from github and overwrite to the latest commit:<br>
git fetch --all<br>
git reset --hard origin/master<br>
git reset --hard 4ef96848e4f8e4f84e98f8e4fe98f49e4f <- commit hash  // reset to specific commit<br>
<br>
git reset --hard origin/<branch_name>                  //discard all local changes and move to first branch<br>
$ git branch | grep -v "main" | xargs git branch -D    //delete all branches except 'main' // can choose few branches: | grep -v "another branch" |<br>
<br>
------------------------------------------------------------------------------------------------------------------<br>
# start using git:<br>
1 create develop branch in github<br>
2 git fetch // fetch changes from remote repo<br>
3 git checkout develop<br>
4 git branch -b branchname -> add changes -> git add . -> git commit -m 'text' -> git push -> git push --set-upstream origin breeze-install<br>
5 this new branch will appear in github so you need to create pull request or merge in to develop branch<br>
6 when working in team ,before creating new feature branch you must pull origin develop to avoid conflicts if somebody changed the code<br>
<br>
# git pull vs git fetch<br>
<br>
<br>
<br>
<br>
# merging conflicts:<br>
if someone made changes on remote repository after you pulled, then if you will make changes on local repo and try to push there will be merging conflict<br>
choose: accept both changes and git push<br>
<br>
# rebase:<br>
advisable to use localy<br>
when commiting changes ,the code from feature branch goes on top of main branch<br>
git rebase main // rebasing feature branch along main branch<br>
git rebase <feature-branch> // if no conflicts rebase feture branch and add all commits on top of main<br>
<br>
# change commit name:<br>
git rebase -i HEAD~(number of commits)<br>
in vim editor press i for editing and write reword then save(esc+:+w+q),then change name of commit and save.<br>
<br>
# delete commit:<br>
git rebase -i HEAD~(number of commits)<br>
in vim editor press i for editing and instead of pick write drop then save(esc+:+w+q),then change name of commit and save.<br>
<br>
# merge(localy):<br>
git checkout -b <branchname><br>
make changes<br>
git add . <br>
git commit -m 'made changes'<br>
git checkout main<br>
git merge --squash <branchname><br>
git commit -m 'merged feature branch to main'<br>
<br>
<br>
