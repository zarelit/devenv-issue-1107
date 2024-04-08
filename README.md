# Reproduce issue cachix/devenv#1107

Clone in a directory with spaces:

    git clone https://github.com/zarelit/devenv-issue-1107.git 'test issue 1107'
    cd 'test issue 1107'
    direnv allow
    rustc main.rs

and get the error:

    error: linking with `cc` failed: exit status: 1
      |
      = note: LC_ALL="C" PATH="

When cloned in a directory without spaces this doesn't happen.

    git clone https://github.com/zarelit/devenv-issue-1107.git 'test-issue-1107'
    cd 'test-issue-1107'
    direnv allow
    rustc main.rs