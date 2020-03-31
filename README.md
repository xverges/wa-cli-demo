
Initialise the project.  

```
$ git init
$ wa-cli init
...
The values you have supplied have been added to the .env file
You can set them as environment variables
and enable command completion by running

   set -o allexport; source .env; set +o allexport; eval "$(_WA_CLI_COMPLETE=source_bash wa-cli)"
$ set -o allexport; source .env; set +o allexport; eval "$(_WA_CLI_COMPLETE=source_bash wa-cli)"
$ touch README.md
$ git add .
$ git status
...
	new file:   .gitignore
	new file:   .wa-cli/main_branch.txt
	new file:   README.md
$ git commit -m "Initial commit"
```

Get a skill from a public repo and deploy it.

```
$ wget -P skills https://raw.githubusercontent.com/watson-developer-cloud/community/master/watson-assistant/complex_dialog_tutorial.json
$ wa-cli skills deploy skills/complex_dialog_tutorial.json
$ wa-cli skills list
...
2020-03-19T15:48:04.359Z   f8bc1ed2-7dfa-4f4e-b519-3203947703b1   Watson Assistant tutorial
```

Enable the use of sanboxes for that skill, and commit the decomposed skill.

```
$ wa-cli sandbox init "Watson Assistant tutorial"
$ git add .
$ git status
...
	new file:   waw/Watson Assistant tutorial/counterexamples/IRRELEVANT.csv
	new file:   waw/Watson Assistant tutorial/dialog/dialog.xml
	new file:   waw/Watson Assistant tutorial/entities/menu.csv
...
	new file:   waw/Watson Assistant tutorial/intents/Customer_Care_Appointments.csv
	new file:   waw/Watson Assistant tutorial/intents/Customer_Care_Authorized_User.csv
...
	new file:   waw/Watson Assistant tutorial/meta.json
$ git commit -m "Decomposed Watson Assistant tutorial"
```

