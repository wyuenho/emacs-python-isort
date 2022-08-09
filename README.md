# emacs-python-isort
Reformat python-mode buffer with isort.


## Usage

``` emacs-lisp
(require 'python-isort)
(add-hook 'python-mode-hook 'python-isort-on-save-mode)
```

## Motivation

There are 2 other packages that integrate `isort` with Emacs -
[py-isort](https://github.com/paetzke/py-isort.el) and
[isortify](https://github.com/pythonic-emacs/isortify). Both of which have not
been maintained for years and violate Emacs convention.

`py-isort` assumes there will always be an executable called `isort` that will
be available on `exec-path`, i.e. the path to the executable is not
configurable, which makes using `isort` in an isolated virtualenv
(e.g. pre-commit and pipx install Python scripts into isolated virtualenvs) for
your project difficult.

`isortify` has a similar problem in which it assumes the `isort` module can
always be found from the Python executable's `sys.path`.

`python-isort` follows the Emacs convention which allows the user to specify the
full path to the desired `isort` executable. This means it plays very well with
other packages in the Emacs ecosystem that follow the convention.


## Copyright
Copyright (C) 2021  Jimmy Yuen Ho Wong
