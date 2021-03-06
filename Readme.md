# GitHub informations

## Formating
Help for formating documentation
Link : https://help.github.com/en/categories/writing-on-github#task-lists

My usual commands :
# The largest heading
## The second largest heading
###### The smallest heading

# Basic formating
Link : https://help.github.com/en/articles/basic-writing-and-formatting-syntax

## Highlight special line in code
For highlighting the special line of the code you can create a link like this :
**link_with#L4  //for highlight line 4**

______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________

# GIT commands

![3 zones of git and github](images/github_informations.jpg)

## Initialize a deposit

For initialize a deposit, send this command in a specific directory :
```
git init.
```

## ADD a file in your repository
For adding a file, create a file in your local working directory. After this, send this command for add this file in the roepository :
```
git add Your_file_name
git commit
```

## Clone project

Open in your web browser the project in github that you want to clone.

Copy and paste the link.

![Copy button using for clone project](images/github_commit.png)


To clone project set this command in a specific directory in your computer :
```
git clone copy_paste_link.git
```
## Upload an existing project

When you have finish the modifictaion of your file, you must do theses points
 1. Add on stage
 2. Commit the stage on on local commit
 3. Push the modification on the external server (github)

The command list to do this is :
```
git add file_with_modification 
git commit -m "add informations on the commit"
git push 
```

## Commit a project

After made some program modification or creating some file, you can commit your modifications by sending this command :

```
git commit -m “Information concernig you modification for explanation”
```
Note : For each commit it's really important to explain yours modifications.

## PUSH the update to the server

To send your modification on the external repository, send this command :
```
git push
```

## PULL for update your local repository

To receive the last external modification, send this command :
```
git pull
```

NOTA : Git pull replace your local file and you lose your modification.

## FETCH and MERGE for update your local repository

To receive the last external modification and not affect your local file, send this command :
```
git fetch
git merge //for controle the merge local and distant file.
```

NOTA : Git fetch create a duplicate file. For the gestion of your merge local file and external file, you can use the git merge command. PULL = FETCH + MERGE

## SEE the status of the file
This command see you the status of you file :
```
git status
```

## Make a delivery file (STASH)
To make a temporary saving file after some accidently modification, you can send this command:
```
git stash
```
with this command you backup temporary your modification and you recover your original file after modification.

You ca see these saving temprorary file by using this command :
```
git stash list
```

After that you can create a branch, enter in this branch and send this command to recover your modifications on the 
stash backup :
```
git stash apply
```

if you made a lot of stash bachup and you want recover a specific stash, after sending the "git stash list", you can  recover with this command :
```
git stash apply stash@{0}
```

## Change the message of the last commit
You can change the message on the last commit if you make somes misstakes with this command :
```
git commit --amend -m "Your new message of the last commit"
```

## Deposit a forgotten file in the last commit
If you forget files on your last commit, you can add these file with these commands :
```
git add Your_forgotten_file
git commit --amend --no-edit
```

## CRITICAL ERROR on your last commit
If you push a corrupted file on the public server, you have one possibility for correct the problem with doing this command
```
git revert HEAD^
```
IMPORTANT : With this command you correct you mistake, but you can lose local file if you don't make a backup.

NOTA : ***git reset HEAD*** cancel the change not committed.
NOTA : The difference between Revert and Reset is that Reset go to the last commit without put a commit. And Revert make a commit of the second last commit and forget the bad last commit. For me the best way is to used Revert.

## GIT RESET
There are tree git reset (soft, medium and hard)

The ***reset soft*** put a commit issue of the specific commit when you make some mistake. You don't lose file and the HEAD is not detach.
```
git reset --Soft 
```

The ***reset mixed*** put a commit of the the second last commit or a specific commit. This commit don't modify your current local file. No file wil be delete. But you detach the HEAD.
```
git reset --mixed 
```

The ***reset hard*** should be used with very attention. with this command, the history will be erase after your specific commit that you want tu reset.All the commit and branch associated with this commit will be delete. 
```
git reset specific_commit --hard 
```

NOTA : The difference between Revert and Reset is that Reset go to the last commit without put a commit. And Revert make a commit of the second last commit and forget the bad last commit. For me the best way is to used Revert.

## LOG and JUMP at a specific commit

The git log permit to see the historic of your project by invert saving time. The last commit appear at the beginning.

This command is :
```
git log
```

An another interesting command is ***git reflog***
This command permit to see the SHA identification to allow you to jump in a specific commit if you want to forget some code evolution
The command log to she the SHA of all commit is:
```
git reflog
```

To return at a specific commit, you run the git reflog and note the SHA number. So you can jump at the specific SHA commit if you want to not include a new function. The command is :
```
git checkout SHA_number
```

## SEE the modifications of your files

To see the date, author and modifications of a commit file, you can use this command
```
git blame File_to_see_modification
```

## Git REBASE

The rebase let your historical more readable and more understandable.

IMPORTANT : You never use the rebase on a public deposit, because you lose the historical information.

With ***git rebase interactive*** you can change the historical order with using the SHA number.
For example :
```
git log  //capture the eight digit of the master

git rebase -i eight_digit_SHA_master  
//open an editor for reorganize the commit order by permuting the ligne of the diferent commit

git log //to see the change
```

## Branch

To know information concerning the branch, set this command :
```
git branch
```

For create a branch set this command :
```
git branch branch_name
```

If you accidently create a new brand and you want to delete it, you can send this command.
DELETE a branch :
```
git branch -d Your_branch_name_you_want_to_delete
```

For forcing the branch delete, you can set this command.
***Important: when you use -D, you force the erasement of the file and all history information for this branch.***

```
git branch -D Your_branch_name_you_want_to_force_delete
```

You can control the creation of your branch with sending this command.
The star set your position in the repository
```
git branch
```

For enter in the new branch send this command.
```
git checkout your_branch_name
```
You are now in your virtualy branch. To see the changing branch send the git branch and see that the star is positioning in your new branch.

## CLEAN or ERASE some not important commit

For cleaning some commits, you can use these command :
```
git rebase -i HEAD~2   //for access at the two last commit
drop SHA_file_commit1 commit1       //for deleting the commit1
drop SHA_file_commit2 commit2       //for deleting the commit2
```
You can use these function to clean the history of the deposit.

## CLEAN or ERASE branch
To erase some brand, you can proceed like this :
```
git branch -d branch_to_erase
```

##SQUASH for cleaning your commit
With the squash function, you can concatenate and clean your commit.
Using squash for example like this :
```
git rebase -i HEAD~4  //running and rebase interactive on the last 4 commit
pick 5ed5ab87 add information 1
squash 98efab23 add information 2
squash e53ABC57 add information 3
squash 1a23q5f7 add information 4
```
After these task, git concatenate all information and file in the same commit. That reducte de number of commit.


## GIT bisect debug software
Git offer the possibility to find a bug with the bisect function. To realize this, we indicate to git the commit where they are not problem and the commit where we are  the bug. For example :
```
git log //to knwow the SHA between good and bug commit where we detetct the problem
git bisect start SHA_bug_commit SHA_good_commit  //git navigate on all commits between bug and good and ask us if we detect the problem. 
git bisect good  //if ok
git bisect bad //if problem 
```
At the end git indicate the commit where they are a problem. Now we can start debugging the software.

## ADD external git to your project
The **git submodule** allow to you to include and another git deposit in your project.
To do this you call this function :
```
git submodule add web_link_project_submodule your_specific_local_directory
// this command add the external deposit as a submodule.
// git add a new file .gitmodules that contain the descritpion of the submodule in the project.
```

## git subtree
To push your new submodule on your external github, you can use the subtree function that allow to push the new submodule on your external deposit and remenber the historical of the submodule.
I you copy paste all file manualy you lose the historical of the submodule commit. to do tjis you can write this command :
```
git subtree push -P My_new_submodule_directory git@my_git_server:group/projet.git master
```

______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________

# GIT FLOW

git flow is using to manage a global projet with git

To init the git flow set this command :
```
git flow init 
```

by default, the git create the master and the developement branch. After you can developp some branch for your differents features.
The flow architecture depending of your developement team.

by default git flow propose this architecture, but it's for information :
```
master  o--------------------------------o-----
           \ \ \ \ \                    /
Hot fix     \ \ \ \ o-----------o------/
             \ \ \ \                  /
Developpement \ \ \ o--o---o----o----/
               \ \ \                /
feature1        \ \ o----o-oo-o----/
		 \ \              /
Feature2	  \ o-o--o-o-----/
		   \            / 
Release		    o----------o

```

note : GitFlow was created by Vincent Driessen.

To add a main feature branch you send this command :
```
git flow feature start main
```
With this command you go to the main feature branch


## Git MARKET
Git market was be created in 2017.
They are 5 categories :
 1. Code quality
 2. code analysis
 3. Continue integration
 4. project monitoring and management.
 ______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________

# GITLAB

GitLab is a service that stores repositories using the Git backbone, just like GitHub.

Gitlab has more modern tools than Github. One of GitLab's main competitors is Jenkins.

GitLab include these functionalities :
 1. Test software.
 2. Application packaging.
 3. Continue integration.
 4. Continue deployement.
 5. Monitoring software.
 6. Application security.

Gitlab has these characteristics :
 1. Allows hosting web projects.
 2. Managing source code versions.
 3. Management of the whole development process.
 4. Allows simple collaboration.
 5. Open source and collaborative.
 6. Free.
 7. It is also a solution for businesses.

## CONTINUOUS INTEGRATION

The CI (**Continuous Integration**) allows a faster and less destabilizing code integration, since the code is integrated progressively, at a faster rate than with other development approaches.

With this approach after a commit **CI pipeline** can build, make test and integration test.
With **Continuous Deployement CD** the system can review; taging and make the code in production.

To use the CI and CD, you must open an account on Gitlab.

To configure continuous integration, we must first create in our repository a **.gitlab-ci.yml** file which will list the different tasks to perform. 

When GitLab detects a .gitlab-ci.yml file, it will automatically try to execute the steps with runners.

In the **.yml** file, we will be able to put :
 1. The stages of test
 2. Construction
 3. Deployment
 4. Notification.


______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________
______________________________________________________________________________________________________________________

# Have contributors
On Github, if you want to have more visibility, it's important to answer to the sollicitation of your contributors.

To do this, you can do these tasks :
 1. Answer to the pull request
 2. stick your project (Build stick, vulnarabilities numbers, coverage project...)
 3. Code lisibilities
 4. line numbers of your file
 5. Code understanding
 6. Bugs and issues management



