# Git / Github Tips and Tutorials

A collection of tips and tutorials for using Git and Github.

## Github

* The "Bootcamp":
  1. [Set Up Git](https://help.github.com/articles/set-up-git/)
  2. [Create a Repo](https://help.github.com/articles/create-a-repo/)
  3. [Fork a Repo](https://help.github.com/articles/fork-a-repo/)
  4. [Be Social](https://help.github.com/articles/be-social/)
* Github [search results for "organizations"](https://help.github.com/search/?utf8=✓&q=organizations)

## Git

* [Main Webpage](http://git-scm.com) - download `git` and view the documentation.
  * First section: [About Version Control](http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
  * [Cheat Sheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)
  * [Visual Cheat Sheet](http://ndpsoftware.com/git-cheatsheet.html)

### Git Crash Course
The following describes 99% of the git commands that I (Graham) do and should get you started.

First, install git and navigate a terminal (linux/mac) or Git Bash (windows) to the folder where you'd like to put your repo. If you download a repo from github, go to the repo page and look on the right and there should be a box with a command ready to copy and paste, something like

    git clone some-url

This will create a new folder with a local copy of the entire commit history.  
If you'd like to create a new repository, run

    git init


to set up the .git folder, then add the files you want to track (for instance you may want to add the source code/tex files, but the binaries/pdfs don't bother)

    git add file1 file2 ...
    git commit -m "Initial Commit"

This adds the first commit with the message "Initial commit" but you can be more creative if you like.

To use it, make changes to the tracked files then

    git diff

Tells you what has changed in the tracked files since the last commit. I like to do this before I commit to make sure I'm doing the right thing. If you only want to commit certain files, then git add them individually as above, but 99% of the time I'm committing all my changes and run

    git commit -am "Describe your changes here"

The -a means to commit all changed files. Once you have some commits you can view them in text with

    git log

or graphically with (if you have it installed)

    gitk

Branches can be handled by git branch and then git checkout to switch branches

    git branch new-branch-name
    git checkout new-branch-name

If you want to merge branch1 into branch2, then

    git checkout branch2
    git merge branch1

Git is pretty good about figuring out what to do but you may need to manually intervene. Open the conflicted files, make the changes necessary and then commit the result.

To get your changes out into the world, you need to add a remote repository and push your changes. If you cloned your repo from github, then you've already got a remote repository automatically and can run

    git push

Git might complain about some things (since you aren't telling it where to push or what branch to push) but the error message is informative and just do what it says if it appears. If you didn't clone a repo, you need to get the url of the repo and add it as

    git remote add origin repo-url

In that command, origin is the name of the remote and is arbitrary but traditional. This allows you to have multiple remote repositories by giving them different names.
