# check-ssh-logins
How to check some user/pass throw ssh

## Requirements

sshpass must be installed on host before.

## Prepare files

Prepare ip/host files, for ex. `ips.txt`:

ip/host file `ips.txt`

```
10.1.1.1
host.addr.lan
```

## Usage

```
<_ipList='ip list file'> <_user='user'> <_password='password'> <_logF='log file'> check-ssh-logins
```

where:
- _ipList - file w/ ip/hosts
- _user - user to login
- _password - password of user
- _logF - output log file

## Parameters

In `check-ssh-logins` set needed timeout in `_timeout` var. Default is __60 secs__.

## Example

```
_ipList=./ips.txt _user='root' _password='SomePassword' _logF=./ips.log ./check-ssh-logins
```

Output in `ips.log` will looks like:

```
/i/ checking root@10.1.1.1 w/ password 'SomePassword' ..
uid=0(root) gid=0(root) groups=0(root)
some-host-10-1-1-1
/i/ checking root@host.addr.lan w/ password 'SomePassword' ..
```

If log file __not contains__ lines like `uid` and `hostname` it meens that password is wrong.