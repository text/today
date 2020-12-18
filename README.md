# td 

Td (today) is command line utility that helps you track your daily activities. Activity record consists of start and stop time range, and text to briefly describe or label that record. By default `td` creates `.td` directory inside your home directory (`$HOME`, `%USERPROFILE%`) where activity records will be stored.

## Installation

Currently you can only build from source code or use `go get` command.

```zsh
% go get github.com/text/td
```

## Usage

Executing `td` command will print current date and all reported activity records for this date.

```zsh
% td
Sunday, December 13, 2020
```

Activity is reported by executing `td` command with non-flag arguments. Non-flag arguments are used as activity text.

```zsh
% td start putting together README.md
```

Following execution of `td` command in the same day will print duration of `putting together README.md` activity.

```zsh
% td
Sunday, December 13, 2020
   15m putting together README.md
```

In case of repeating activity (`reading emails`) you can print total duration of this activity by specifying regular expression `-pattern` matching desired text. Activity included in total duration is highlighted and total duration is printed below all reported activity records.

```zsh
% td -pattern "reading emails"
Sunday, December 13, 2020
   15m putting together README.md
    5m reading emails
   40m playing games
    2h coding
    5m reading emails
------
   10m
```
