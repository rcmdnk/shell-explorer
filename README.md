# shell-explorer
File explorer made with shell script。

## Installation

On Mac, you can install scripts by [Homebrew](https://github.com/mxcl/homebrew):

    $ brew tap rcmdnk/rcmdnkpac/shell-explorer

You can also use an install script on the web like:

    $ curl -fsSL https://raw.github.com/rcmdnk/shell-explorer/install/install.sh| sh

This will install scripts to `/usr/bin`
and you may be asked root password.

If you want to install other directory, do like:

    $ curl -fsSL https://raw.github.com/rcmdnk/shell-explorer/install/install.sh|  prefix=~/usr/local/ sh

Or, simply download the script and set where you like.

:warning: Install [sentaku](https://github.com/rcmdnk/sentaku), too
if you download directly.

## Usage

### Start shell-explorer

Explore current directory:

    $ se

Start from given directory:

    $ se $HOME/my_dir/

Give the list from stdin:

    $ echo file1 file2 file3|se

Show the content of the file in the right:

    $ se -r

Show the content of the file under the list:

    $ se -u

Help:

    $ se -h

    Usage: ex_explorer.sh [directory] [-aruvC]

    Arguments:
       -a         Show hidden files/directories.
       -r         Show file content in the right.
       -u         Show file content under the list.
       -C         No confirmation at deletion.
       -h         print this help and exit.

### Usage during explorer

* [sentaku](https://github.com/rcmdnk/sentaku) actions:

Key|Action
:-:|:-
n(any number)| Set number. Multi-digit can be used (13, 320, etc...). Used/reset by other key.
k/j, C-p/C-n | Up/Down (if n is given, n-th up/n-th down).
gg/G     | Go to top/bottom. (If n is given, move to n-th candidate.)
C-a/C-e  | Go to the beggining/end.
C-u/C-d  | Half page down/Half page down.
C-b/C-f  | Page up/Page down.
M-v/C-v  | Page up/Page down.
C-i/C-o  | Move the item up/down.
q, C-x   | Quit.
Space    | Select/unselect current line for multi-selection.
         | At Emacs mode or search mode in Vim mode,
         | it selects when space is pushed twice.
C-s      | Start/Stop Visual mode (multi-selection).
v        | Visual mode.
Esc      | At search mode, first Esc takes it back to normal mode
         | with selected words.
         | Second Esc clear search mode.
         | Visual mode is cleared by first Esc.
/        | Search.

shell-explorer actions.

Key|Action
:-:|:-
l| Show contents of selected files with `$VISUAL` (or `less`).
e| Edit selected files with `$EDITOR` (or `vi`).
s| Show details of selected items with `ls -l`.
d| Delete selected items.
p| Exit and print selected items' full paths.
c| Change to a directory under the cursor. (No action for a file.)
Enter|If an item under the cursor is a directory, move to it. Otherwise same as `l`.

* shell-explorer actions:

Key|Action
:-:|:-
l| Show contents of selected files with `$VISUAL` (or `less`).
e| Edit selected files with `$EDITOR` (or `vi`).
s| Show details of selected items with `ls -l`.
d| Delete selected items.
p| Exit and print selected items' full paths.
c| Change to a directory under the cursor. (No action for a file.)
Enter|If an item under the cursor is a directory, move to it. Otherwise same as `l`.
