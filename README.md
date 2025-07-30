# simple-tts-robot

A lightweight Linux text-to-speech (TTS) simulator that generates a slow, robotic, echoing voice effect using `espeak` and `sox`. Easy shell scripts with customizable pitch and reverberation. Fully open source. On macOS, some commands may require `sudo` due to system restrictions; Linux usually doesn’t.

## Features

- Slow, robotic, echoing voice effect  
- Customizable pitch and reverberation  
- Minimal dependencies (`espeak`, `sox`)  
- Easy-to-use shell scripts  
- Open source and free to use

## Installation

Make sure you have `espeak` and `sox` installed on your system.

### On Linux (e.g., openSUSE)

```bash
sudo zypper install espeak sox
```
### On macOS

Install with Homebrew (or of the linux):

```bash
brew install espeak sox
```
****Note: Some commands may require sudo on macOS due to system restrictions.****

### Usage

Run the main script with the text you want to speak:

```bash
./tts.sh "Your text goes here"
```
If you want to read text from the clipboard (Linux):

```bash
xclip -o | ./tts.sh
```

Script Example (tts.sh)
```bash
#!/bin/bash
if [ "$#" -eq 0 ]; then
  echo "Usage: $0 \"Text to speak\""
  exit 1
fi

TEXT="$*"
espeak -v en-us -s 160 -p 50 -a 100 "$TEXT"
```

Make sure the script is executable:

```bash
chmod +x robot_tts.sh
```

License

This project is licensed under the MIT License. See the LICENSE file for details.
