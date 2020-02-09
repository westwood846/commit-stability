# Commit Stability

How stable are your commits? When you're developing on a feature branch, how
many or the line changes you made made it into the final pull request?

This tool calculates, for a given commit range, how many percent of the
individual line changes are present at the last commit, compared to the first.
If the score (given in percent) is low, you might wanna rebase your commits.

## Usage

For now clone this repo and add the executable to your path:

```bash
git clone git@github.com:westwood846/commit-stability.git
cd commit-stability
npm install
ln -s $(pwd)/commit-stability /usr/bin/ # or similar
cd /path/to/some/repo
commit-stability . master feature-branch
# >>>
# { logEntriesStats: { insertions: 229, deletions: 4 },
#   diffStats: { insertions: 224, deletions: 0 },
#   stability: 0.9613733905579399 }
```

Currently does not work with histories that include merge commits, gotta find a
way how to deal with those.
