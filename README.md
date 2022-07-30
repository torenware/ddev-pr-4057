# Test Program for PR #4057

This is a trivial PHP page that tests for a Vite server being up and running.  Just start up the candidate ddev binary using the included .ddev/config.yaml, and go to the app's page.

In more detail:

1. git clone https://github.com/torenware/ddev-pr-4057
2. cd ddev-pr-4057
3. Using the built-binary or assets:
   * ddev config (make sure it doesn't clobber the config.yaml file already there; if it does, replace it with the one from my repo).
   * Edit config.yaml to what you believe to be correct.
   * ddev start
   * ddev launch
4. If ddev is healthy. run `ddev launch`, you'll get a test page.  The page tests for the presence of a directory at `VITE_PROJECT_DIR`, and for something listening at `VITE_PRIMARY_PORT`.

As has been pointed out to me by rfay, some amount of manual testing is required to verify features; mocks are useful, but not entirely trustworthy; they're only as good as the tests you do with them. In particular: they do not test what happens when node_modules is absent, which is fairly spectacular.

