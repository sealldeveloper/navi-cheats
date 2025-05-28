# navi-cheats
A repo for cheats with [navi](https://github.com/denisidoro/navi) for offsec and ctf stuff mostly

## Formatting

For cheat's, variables have been lowercase mostly. Read [this](https://github.com/denisidoro/navi/blob/master/docs/cheatsheet/syntax/README.md).

### Windows

For Windows, generally the following variables have these values:

```
$ username: if [[ -f "users.txt" ]]; then cat users.txt; fi
$ username_or_userlist: if [[ -f "users.txt" ]]; then { cat users.txt; ls; }; else ls; fi
$ group: if [[ -f "groups.txt" ]]; then cat groups.txt; fi
$ domain: if [[ -f "domains.txt" ]]; then cat domains.txt; fi
$ dc_ip: if [[ -f "dcip.txt" ]]; then cat dcip.txt; fi
$ password: if [[ -f "passwords.txt" ]]; then cat passwords.txt; fi
$ host_address: if [[ -f "ips.txt" ]]; then cat ips.txt; fi
$ filename: ls
```

To include them in your file, just include `@windows-variables`, and it will automatically include the variables and definitions for you.

The idea is that the folder you are working with will have updated files from your findings (your usernames, the domains, passwords, etc) that the cheat-sheet then reads for auto-suggestion inputs to select/search. The auto-suggest can also be completely ignored as you can still type custom values.

`users.txt` should contain valid usernames.
`groups.txt` should contain valid group names.
`domains.txt` should contain the FQDN of any relevant domains.
`dcip.txt` should contain and DC IPs (this is more for HTB/FullPwn though).
`ips.txt` should contain any IPs of machines.
`passwords.txt` should contain any valid passwords.

### Linux

For Linux, generally the following variables have these values:

```
$ username: if [[ -f "users.txt" ]]; then cat users.txt; fi
$ username_or_userlist: if [[ -f "users.txt" ]]; then { cat users.txt; ls; }; else ls; fi
$ password: if [[ -f "passwords.txt" ]]; then cat passwords.txt; fi
$ host_address: if [[ -f "ips.txt" ]]; then cat ips.txt; fi
$ filename: ls
```

To include them in your file, just include `@linux-variables`, and it will automatically include the variables and definitions for you.

`users.txt` should contain valid usernames.
`ips.txt` should contain any IPs of machines.
`passwords.txt` should contain any valid passwords.

### Web

For Web, generally the following variables have these values:

```
$ seclistdir: (test -d "$HOME/Documents/Wordlists/SecLists/Discovery/Web-Content" && echo "$HOME/Documents/Wordlists/SecLists/Discovery/Web-Content") || (test -d "/usr/share/seclists/Discovery/Web-Content" && echo "/usr/share/seclists/Discovery/Web-Content") || echo "."
$ seclistlist: ls "<seclistdir>"
```

To include them in your file, just include `@web-variables`, and it will automatically include the variables and definitions for you.

If more SecLists directories need to be used, add them to the tested directories in the `seclistdir` in `web-variables`.

### Hash Cracking

For Hash Cracking, generally the following variables have these values:

```
$ passseclistdir: (test -d "$HOME/Documents/Wordlists/SecLists/Passwords/Leaked-Databases" && echo "$HOME/Documents/Wordlists/SecLists/Passwords/Leaked-Databases") || (test -d "/usr/share/seclists/Passwords/Leaked-Databases" && echo "/usr/share/seclists/Passwords/Leaked-Databases") || echo "."
$ passseclistlist: ls "<passseclistdir>"
```

To include them in your file, just include `@hashcracking-variables`, and it will automatically include the variables and definitions for you.

If more SecLists directories need to be used, add them to the tested directories in the `passseclistdir` in `hashcracking-variables`.