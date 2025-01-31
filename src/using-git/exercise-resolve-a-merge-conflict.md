# Exercise: resolve a merge conflict

We have created a [public repository](https://github.com/robmoss/gimlb-simple-merge-example) that you can use to try resolving a merge conflict yourself.
This repository includes some example data and a script that performs some basic data analysis.

First, obtain a local copy (a "clone") of this repository by running:

```sh
git clone https://github.com/robmoss/gimlb-simple-merge-example.git
cd gimlb-simple-merge-example
```

## The repository history

You can inspect the repository history by running `git log`.
Some key details to notice are:

1. The first commit created the following files:
   - `README.md`
   - `LICENSE`
   - `analysis/initial_exploration.R`
   - `input_data/data.csv`

2. The second commit created the following file:
   - `outputs/summary.csv`

   This commit has been given the **tag** `first_milestone`.

3. From this `first_milestone` tag, two branches were created:

   - The `feature/second-data-set` branch adds a second data set and updates the analysis script to inspect both data sets.

   - The `feature/calculate-rate-of-change` branch changes which summary statistics are calculated for the original data set.

4. The most recent commit merges both branches back into the `master` branch and resolves any merge conflicts.
   This commit has been given the **tag** `second_milestone`.

## Your task

You will create a new branch which will start at the `first_milestone` tag, and then merge the two feature branches into this new branch, resolving any merge conflicts that arise.
You can then compare your results to the most recent commit on the `master` branch.

1. Create local copies of the two feature branches, by running:

   ```sh
   git checkout feature/second-data-set
   git checkout feature/calculate-rate-of-change
   ```

2. Create a new branch (we'll call it `my-branch`) from the `first_milestone` tag, by running:

   ```sh
   git checkout -b my-branch first_milestone
   ```

3. Merge the `feature/second-data-set` branch into `my-branch`, by running:

   ```sh
   git merge feature/second-data-set
   ```

4. Merge the `feature/calculate-rate-of-change` branch into `my-branch`, by running:

   ```sh
   git merge feature/calculate-rate-of-change
   ```

   This will result in a **merge conflict**, and now you need to decide how to resolve each conflict!
   Once you have resolved the conflicts, create a commit that records all of your changes (see the [previous chapter](how-to-resolve-merge-conflicts.md) for an example).

```admonish tip
You may find it helpful to inspect the commits in each of the feature branches to understand how they have changed the files in which the conflicts have occurred.
```

## Self evaluation

Once you have created a commit that resolves these conflicts, see how similar or different the contents of your commit are to the corresponding commit in the master branch (which has been tagged `second_milestone`).
You can inspect this commit by running:

```sh
git show second_milestone
```

How does your resolution compare to this commit?

```admonish note
You may have resolved the conflicts differently to the `second_milestone` commit, **and that's perfectly fine** as long as they have the same effect.
```
