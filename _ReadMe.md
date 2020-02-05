

```bash

CUR_DIR="$(cd "$(dirname "${BASH_SOURCE:-$0}")"; pwd)"

# ssh-agent に読み込ませる秘密鍵のリスト
SSH_KEYS=( "$HOME/.ssh/bitbucket" "$HOME/.ssh/id_rsa" "$HOME/.ssh/id_rsa_tettekete_github" )

prof_d=bash_profile.d

if [ -d "$CUR_DIR/$prof_d" ]
then
	for item in $(find "$CUR_DIR/$prof_d" -maxdepth 1 -type f -not -name "_*" | sort)
	do
		: "SOURCE @ $item"
		source "$item"
	done
fi


PATH="$PATH":~/bin
```

