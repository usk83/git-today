# Git-today

Get some fun stats on your code slinging activity.

## Installation

```
npm -g install git-today
```

## Usage

By default `git-today` will search for commits from the author specified in `.gitconfig` for commits in the current directory and spit out a report:

```
git-today
```

Will output:

```
Git stats for last 1 day in ./:
  17 files modified
  220 line insertions
  682 line deletions
 =======================
  -462 net lines
```


## Options

### -a / --author

Specify a different author. Does not need to be a full match, can just be a partial. (ie. "John" would work for "John Smith")

```
git-today -a "Some dude"
```

### -b / --branch

Specify a different branch. Branch must exist or git will complain.

```
git-today -b some-feature
```

### -d / --directories

Runs an aggregate report for multiple directories.

```
git-today -d ~/Dev/node/kongo,~/Dev/node/agenda
```

```
Git stats for last 1 day in all directories specified:
  7 files modified
  11 line insertions
  0 line deletions
 =======================
  -1 net lines
```

### -m / --multi

Used in conjunction with `-d`. Specifies to print each report for the directories instead of one aggregate report

```
git-today -d ~/Dev/node/kongo,~/Dev/node/agenda -m
```

```
Git stats for last 1 day in /Users/ryan/Dev/node/kongo:
  0 files modified
  0 line insertions
  0 line deleitions
 =======================
  0 net lines

Git stats for last 1 day in /Users/ryan/Dev/node/agenda:
  0 files modified
  0 line insertions
  0 line deleitions
 =======================
  0 net lines
```

### -t / --time

Time duration to search within. By default, `1 day`. Takes any [humanInterval](https://github.com/rschmukler/humanInterval)

```
git-today -t "5 days"
```

```
Git stats for last 5 days in ./:
  40 files modified
  742 line insertions
  167 line deleitions
 =======================
  575 net lines
```
