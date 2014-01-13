# fish_prompt-syl20bnr

My personal compact yet complete (almost :-)) fish prompt.

## Segments

### pwd: Compact current working directory

The `pwd` segment format is `X:Y(Z)` where:
- `X` is either `home:` or `/:`
- `Y` is the current working path base name (name of the current directory)
- `Z` is the depth of the path starting from `X`

If the `pwd` is `home` then the prompt format is simplified to `home:~` without
the depth.

#### Examples

In home directory:
![home](http://raw2.github.com/syl20bnr/fish_prompt-syl20bnr/master/screenshots/prompt_fish-syl20bnr-home-ranger.png)

Inside a directory in home:
![inside_home](http://raw2.github.com/syl20bnr/fish_prompt-syl20bnr/master/screenshots/prompt_fish-syl20bnr-inside-home.png)

Outside the home directory:
![outside_home](http://raw2.github.com/syl20bnr/fish_prompt-syl20bnr/master/screenshots/prompt_fish-syl20bnr-outside-home.png)

### git

If the current directory is a [git][git] repository then the `pwd` segment is
replaced by the `git` segment (I should know where I am).

The `git` segment format is `XI:Y@Z` where:
- `X` is `git:`
- `I` is the information about the current repository state
- `Y` is the current branch name
- `Z` is the name of the repository

The displayed information `I` is:
- Dirtiness is indicated by a little dot after the branch name.
- Unpushed commits are indicated with up arrows
- The number of unpushed commits is indicated right after the up arrows

#### Examples

Dirty:
![dirty](http://raw2.github.com/syl20bnr/fish_prompt-syl20bnr/master/screenshots/prompt_fish-syl20bnr-git-dirty.png)

Unpushed commits:
![unpushed_commits](http://raw2.github.com/syl20bnr/fish_prompt-syl20bnr/master/screenshots/prompt_fish-syl20bnr-git-ucommit-count.png)

### vi-mode

This segment display the current `vi-mode` if the plugin is used.
See the `[n]` in the previous screenshots.

### end

The color of the end of the prompt depends on the `$status` value of the
last executed command. It is `green` or `red` depending on success or failure
of the last command.

Since I often use [ranger][ranger] and use its `shift+s` key binding to bring
a new shell session, there is discreet indicator when the parent process of the
current shell is a `ranger` process. In this case the end of the prompt is
written twice.
With this indicator I can quickly see if I can `ctrl+d` to end the the current
shell process and go back to the `ranger` process.

### where

The `where` segment format is `X@Y` where:
- `X` is the user name
- `Y` is the host name

This segment is displayed in the right prompt.

## Functions

Some functions come with the theme:
- `toggle_right_prompt` will... toggle the right prompt! (alias: `trp`)

[git]: http://git-scm.com/
[ranger]: http://ranger.nongnu.org/
