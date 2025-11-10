# prr-mode

Emacs major mode for editing [`.prr`](https://github.com/danobi/prr) files.

## Installation

### Install command-line tool

First install and configure `prr` using upstream instructions:
- https://github.com/danobi/prr
- https://doc.dxuuu.xyz/prr/

### Install emacs package

Interactively using `package-vc`:

    M-x package-vc-install
    Fetch and install package: https://github.com/rlister/prr-mode

or programmatically:

    (package-vc-install "https://github.com/rlister/prr-mode")

### Alternative install with `use-package`

    (use-package prr-mode
      :straight (:host github :repo "rlister/prr-mode"))

## Configuration

If the `prr` binary is not in your emacs `exec-path`, you can override the location:

    (setq prr-program "~/.cargo/bin/prr")

If you wish, bind the `prr-mode` transient menu to a key:

    (keymap-set prr-mode-map "C-<return>" #'prr-transient)

## Usage

To get a pull request and begin a review:

    M-x prr
    PR: https://github.com/danobi/prr/pull/1

This command will accept any PR format supported by the `prr get` command.

Markup the file as described in the [tutorial](https://doc.dxuuu.xyz/prr/tutorial.html), save the buffer, and submit the review:

    M-x prr-submit

## Integration with other modes

You can use any `outline-mode` commands and keybindings for code folding. For example, use `TAB` to cycle visibility of files and code hunks.

You can browse the current review in a browser:

    M-x prr-browse

Visit the review in a [forge](https://github.com/magit/forge) topic (if installed):

    M-x prr-forge

## Transient menu

You can invoke a menu for all `prr-mode` commands:

    M-x prr-transient

or bind this to a key (see above).
