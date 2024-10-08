# my installing steps for aider.chat and groq.com

remark: i have a windows machine.

## already installed a old python version ?

remark: i had already installed a old python version

first i uninstall this old version

and: later on my installation i had problems with installing pipx

later I got this error message:

'No Python at ...' then

here the tip: 

first remove directory ~\\.local\pipx

## install python latest release

install from https://www.python.org/

after that in the System / Apps / Installed Apps

you will find Python and Phyton Launcher

each in its latest Version

## install pipx

this to have a isolated installation of aider-chat

https://pipx.pypa.io/stable/

https://pipx.pypa.io/stable/#on-windows

in a git bash in your project working dir

(may replace py with python)

```
py -m pip install --user pipx
// now a warning is displayed: pipx is not in the path
// change to this installation dir of the warning message
// if installed from python.org
cd ~/AppData/Roaming/Python/Python312/Scripts
// or if installed from Microsoft Store
cd ~\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.12_xxx\LocalCache\local-packages\Python312\Scripts
// this add this directory to the environment variable PATH
pipx.exe ensurepath
```

try if pipx.exe work now

may you can check your environment variable PATH,

it should have a entry to the Scripts directory,

and in this directory there should be pipx.exe

in a new git bash
```
// show all installations with pipx, current a empty list
pipx.exe list
```

## install aider with pipx

https://aider.chat/docs/install/pipx.html

in a new git bash
```
// runs about 1 min
pipx.exe install aider-chat
// show installed aider-chat and some additional infos about some directories
pipx.exe list
```

## upgrade aider with pipx

if at start of aider --...

is asking to install a updated version of aider this way:
```
Newer aider version v0.nn.n is available. To upgrade, run: ... pip ...
```

then anser
```
Run pip install?
```
with 'n' (no).

Upgrade it with pipx:

in a new git bash
```
pipx list
pipx upgrade aider-chat
```

it answer with
```
⚠️  Overwriting file ~\.local\bin\aider.exe with ~\pipx\venvs\aider-chat\Scripts\aider.exe
upgraded package aider-chat from 0.nn.n to 0.nn.n (location: ~\pipx\venvs\aider-chat)
```

with
```
pipx list
```
you see the upgraded aider-chat

## initialize interactive help for aider with pipx

TODO: figure out how to install with pipx

does not work:
```
pipx install aider-chat[help] --extra-index-url https://download.pytorch.org/whl/cpu
```

## connect aider-chat with a llm via groq.com

get your API key from
https://console.groq.com

select from
https://aider.chat/docs/leaderboards/
a llm that fit your needs

may limits are relevant
https://console.groq.com/settings/limits

and billing / plan
https://console.groq.com/settings/billing

in the directory of your working project

make sure you have a git repo there

then prepare a .env file with content similar to .env.example :

```
GROQ_API_KEY=<yourGroqKey>
```
this replaces the manual need of
```
export GROQ_API_KEY=<yourGroqKey> each time
```

open Visual Studio Code and open the directory of your working project

in Visual Studio Code open a terminal - i open a bash

in this bash in Visual Studio Code in the directory of your working project
```
// no more export, key is in .env file
// export GROQ_API_KEY=<yourGroqKey>
// aider help
aider --help
// run aider with Groq and i.e. Lama/3 :
aider --model groq/llama-3.1-70b-versatile
```

answer in the same git bash terminal:
```
Add .aider* to .gitignore (recommended)? y
Added .aider* to .gitignore
Aider v0.49.1
Models: Model: groq/llama-3.1-70b-versatile with diff edit format
Git repo: .git with 3 files
Repo-map: disabled
VSCode terminal detected, pretty output has been disabled.
Use /help <question> for help, run "aider --help" to see cmd line args
───────────────────────────────────────────────────────────────────────────────────
> /help
/add                 Add files to the chat so GPT can edit them or review them in detail
/add-clipboard-image Add an image from the clipboard to the chat
/ask                 Ask questions about the code base without editing any files
/chat-mode           Switch to a new chat mode
...
```

## work with aider-chat

Aider supports commands from within the chat, which all start with /.

### first helpful links for aider-chat

Tips: https://aider.chat/docs/usage/tips.html

Chat modes: https://aider.chat/docs/usage/modes.html

In-chat commands: https://aider.chat/docs/usage/commands.html

Tutorial videos: https://aider.chat/docs/usage/tutorials.html

Specifying coding conventions: https://aider.chat/docs/usage/conventions.html

Linting and testing: https://aider.chat/docs/usage/lint-test.html

Aider LLM Leaderboards: https://aider.chat/docs/leaderboards/

### first helpful links for groq.com

get your API key from
https://console.groq.com

select from
https://aider.chat/docs/leaderboards/
a llm that fit your needs

may limits are relevant
https://console.groq.com/settings/limits

and billing / plan
https://console.groq.com/settings/billing

### selecting a JavaScript framework or UI library for building scalable web apps (out of focus of this, may later relevant)

 https://todomvc.com/
