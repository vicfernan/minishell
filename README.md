# minishell

A small Unix shell written in C for the 42 curriculum.

This project was about rebuilding some basic shell behavior from scratch: parsing commands, handling pipes and redirections, running built-ins, and executing programs through `PATH`.

## What it does

* interactive prompt with `readline`
* built-ins like `echo`, `cd`, `pwd`, `env`, `export`, `unset`, `exit`
* pipes (`|`)
* redirections (`<`, `>`, `>>`, `<<`)
* environment variable expansion
* quote handling

## Run

```bash
make
./minishell
```

On macOS, `readline` may need to be installed first:

```bash
brew install readline
make fclean
make CFLAGS="-Wall -Wextra -I$(brew --prefix readline)/include -g3 -I. -Ilibft/ -Iprintf/" READLINE="-L$(brew --prefix readline)/lib -lreadline"
./minishell
```

## Example

```bash
echo hello
pwd
export TEST=42
echo $TEST
ls | wc -l
cat << EOF
hello
EOF
exit
```

## About this repo

This was a collaborative 42 project. I am using this repo to keep the project runnable and to document it clearly for my portfolio.
