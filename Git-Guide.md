# Git & GitHub: Start to Finish

Two situations cover most of what you'll do day to day: putting a brand-new project on GitHub, and sending your latest changes to one that's already there.

## I. First time: a new project

You've got a folder of code on your machine and nothing on GitHub yet.

1. **Turn the folder into a git repository**
   Run this once, inside the project folder.
   ```
   git init
   ```

2. **Stage your files**
   Tells git which files to include in the next commit.
   ```
   git add .
   ```

3. **Make your first commit**
   A commit is a saved snapshot with a short message describing it.
   ```
   git commit -m "Initial commit"
   ```

4. **Create the repo on GitHub**
   On github.com, click `New repository`, name it, and leave it empty — no README, no `.gitignore`. You'll get a repo URL like `https://github.com/you/project.git`.

5. **Point your local repo at GitHub**
   This links your folder to the empty repo you just created.
   ```
   git remote add origin https://github.com/you/project.git
   ```

6. **Name your main branch**
   Modern convention is `main` rather than `master`.
   ```
   git branch -M main
   ```

7. **Push your code up**
   `-u` remembers this remote and branch, so future pushes just need `git push`.
   ```
   git push -u origin main
   ```

## II. Updating an existing project

The repo already exists on GitHub and you've made changes locally.

1. **Check what changed**
   Shows which files are modified, new, or staged.
   ```
   git status
   ```

2. **Pull the latest first**
   Do this before you push, especially if others (or another machine of yours) might have changed the repo — it avoids conflicts.
   ```
   git pull
   ```

3. **Stage your changes**
   Use `git add filename` instead of `.` if you only want to stage specific files.
   ```
   git add .
   ```

4. **Commit with a clear message**
   Describe what changed and why, not just "update".
   ```
   git commit -m "Fix login redirect bug"
   ```

5. **Push to GitHub**
   Sends your commits to the remote repo.
   ```
   git push
   ```

6. **Working on a feature? Use a branch**
   Keeps experimental work separate from `main` until it's ready.
   ```
   git checkout -b feature-name
   git push -u origin feature-name
   ```

---

`git log --oneline` shows your commit history · `git diff` shows unstaged changes before you add them.
