# **Git Commands**

## **Git Commands for local repositories**

### **git init**
This command turns a directory into an empty Git repository. This is the first step in creating a repository. After running git init, adding and committing files/directories is possible.

Example:
```
cd /Users/vlatko/Workspace/bootcamp/git-init-test 
git init
```

### **git add**
Adds files in the to the staging area for Git. Before a file is available to commit to a repository, the file needs to be added to the Git index (staging area). There are a few different ways to use git add, by adding entire directories, specific files, or all unstaged files.

Example:
```
git add index.html
git add git_add_test
git add .
```

### **git commit**
Record the changes made to the files to a local repository. For easy reference, each commit has a unique ID.

It’s best practice to include a message with each commit explaining the changes made in a commit. Adding a commit message helps to find a particular change or understanding the changes.

Example:
```
git commit -m "Test commit"
```

### **git status**
This command returns the current state of the repository.

_git status_ will return the current working branch. If a file is in the staging area, but not committed, it shows with _git status_. Or, if there are no changes it’ll return _nothing to commit, working directory clean_.

Example:
```
git status
```

### **git config**
With Git, there are many configurations and settings possible. _git config_ is how to assign these settings. Two important settings are user user.name and user.email. These values set what email address and name commits will be from on a local computer. With _git config_, a _--global_ flag is used to write the settings to all repositories on a computer. Without a _--global_ flag settings will only apply to the current repository that you are currently in.

There are many other variables available to edit in _git config_. From editing color outputs to changing the behavior of _git status_.

Example:
```
git config user.email
git config user.name
git config --global user.email "test@email.com"
git config --global user.name "Test Test"
```

### **git branch**
To determine what branch the local repository is on, add a new branch, or delete a branch.

Example:
```
git branch new_test_branch
git branch -a
git branch -r
git branch -d new_test_branch
```

### **git checkout**
To start working in a different branch, use _git checkout_ to switch branches.

Example:
```
git checkout new_test_branch
git checkout -b new_feature_branch
```

### **git merge**
Integrate branches together. _git merge_ combines the changes from one branch to another branch. For example, merge the changes made in a staging branch into the stable branch.

Example:
```
git merge new_feature_branch
```

### **git rebase**
Similar to _git merge_, _git rebase_ also integrate branches together. _git rebase_ takes your entire feature branch and moves it to the tip of the another branch. It creates brand new commits for each commit in the original feature branch.

Example:
```
git rebase new_test_branch
```

## **Git Commands for remote repositories**

### **git remote**
To connect a local repository with a remote repository. A remote repository can have a name set to avoid having to remember the URL of the repository.

Example:
```
git remote add origin git@github.com:fiveagency/java-bootcamp-git-demo.git
git remote -v
```

### **git clone**
To create a local working copy of an existing remote repository, use _git clone_ to copy and download the repository to a computer. Cloning is the equivalent of _git init_ when working with a remote repository. Git will create a directory locally with all files and repository history.

Example:
```
git clone git@github.com:fiveagency/java-bootcamp-git-demo.git
```

### **git pull**
To get the latest version of a repository run _git pull_. This pulls the changes from the remote repository to the local computer.

Example:
```
git pull origin feature/new_test_branch
```

### **git push**
Sends local commits to the remote repository. _git push_ requires two parameters: the remote repository and the branch that the push is for.

Example:
```
git push origin feature/new_test_branch
```

## **Advanced Git Commands**

### **git commit --amend**
We can modify the latest Git commit by simply using the _--amend_ option. It replaces the most recent commit. We can modify the commit message and update the files included in the commit as well. Git considers the amended commit as a new commit.

Example:
```
git commit --amend
git commit --amend --no-edit
```

### **git stash**
To save changes made when they’re not in a state to commit them to a repository. This will store the work and give a clean working directory. For instance, when working on a new feature that’s not complete, but an urgent bug needs attention.

Example:
```
git stash -u
git stash pop
```

### **git log**
To show the chronological commit history for a repository. This helps give context and history for a repository. git log is available immediately on a recently cloned repository to see history.

Example:
```
git log
git log --before="Aug 15"
git log --after="Aug 15"
git log --author="Vlatko Spoljaric"
```
