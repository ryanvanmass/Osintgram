# Osintgram 🔎📸

[![version-1.2](https://img.shields.io/badge/version-1.2-green)](https://github.com/Datalux/Osintgram/releases/tag/1.2)
[![GPLv3](https://img.shields.io/badge/license-GPLv3-blue)](https://img.shields.io/badge/license-GPLv3-blue)
[![Python3](https://img.shields.io/badge/language-Python3-red)](https://img.shields.io/badge/language-Python3-red)
[![Telegram](https://img.shields.io/badge/Telegram-Channel-blue.svg)](https://t.me/osintgram)
[![Docker](https://img.shields.io/badge/Docker-Supported-blue)](https://img.shields.io/badge/Docker-Supported-blue)

Osintgram is a **OSINT** tool on Instagram to collect, analyze, and run reconnaissance.

<p align="center">
<img align="center" src=".img/carbon.svg" width="900">
</p>

Disclaimer: **The contributors do not assume any responsibility for the use of this tool**

Warning: It is advisable to **not** use your own/primary account when using this tool.

## Tools and Commands 🧰
### main.py

Osintgram offers an interactive shell to perform analysis on Instagram account of any users by its nickname. You can get:

```text
- addrs           Get all registered addressed by target photos
- captions        Get user's photos captions
- comments        Get total comments of target's posts
- followers       Get target followers
- followings      Get users followed by target
- fwersemail      Get email of target followers
- fwingsemail     Get email of users followed by target
- fwersnumber     Get phone number of target followers
- fwingsnumber    Get phone number of users followed by target
- hashtags        Get hashtags used by target
- info            Get target info
- likes           Get total likes of target's posts
- mediatype       Get user's posts type (photo or video)
- photodes        Get description of target's photos
- photos          Download user's photos in output folder
- propic          Download user's profile picture
- stories         Download user's stories  
- tagged          Get list of users tagged by target
- wcommented      Get a list of user who commented target's photos
- wtagged         Get a list of user who tagged target
```

You can find detailed commands usage [here](doc/COMMANDS.md).

[**Latest version**](https://github.com/Datalux/Osintgram/releases/tag/1.2) |
[Commands](doc/COMMANDS.md) |
[CHANGELOG](doc/CHANGELOG.md)

### AutoDownload.py
Allows you an easy way to automatically download all posts from the target  account

## Installation ⚙️

1. Fork/Clone/Download this repo

    `git clone https://github.com/ryanvanmass/Osintgram.git`

2. Navigate to the directory

    `cd Osintgram`

3. Run `pip3 install -r requirements.txt`

4. Open the `credentials.ini` file in the `config` folder and write your Instagram account username and password in the corresponding fields
    
    Alternatively, you can run the `make setup` command to populate this file for you.

5. Run the main.py script

    `python3 main.py <target username>`
OR
5. run the AutoDownload.py script
    
    `python3 AutoDownload.py <target username>`

## Docker Quick Start 🐳

This section will explain how you can quickly use this image with `Docker`.

### Prerequisites

Before you can use either `Docker`, please ensure you do have the following prerequisites met.

1. **Docker** installed - [link](https://docs.docker.com/get-docker/)
2. **Credentials** configured - This can be done manually or by running the `make setup` command from the root of this repo

**Important**: Your container will fail if you do not do step #3 and configure your credentials
**Note**: By default the container is set up to only run the AutoDownload.py script

### Docker

If docker is installed you can build an image and run this as a container.

Build:

```
docker build -t osintgram .
```

Run:

```
docker run --rm -v "$PWD/output:/home/osintgram/output" osintgram <target>
```

- The `<target>` is the Instagram account you wish to use as your target for recon.
- The required `-i` flag enables an interactive terminal to use commands within the container. [docs](https://docs.docker.com/engine/reference/commandline/run/#assign-name-and-allocate-pseudo-tty---name--it)
- The required `-v` flag mounts a volume between your local filesystem and the container to save to the `./output/` folder. [docs](https://docs.docker.com/engine/reference/commandline/run/#mount-volume--v---read-only)
- The optional `--rm` flag removes the container filesystem on completion to prevent cruft build-up. [docs](https://docs.docker.com/engine/reference/run/#clean-up---rm)
- The optional `-t` flag allocates a pseudo-TTY which allows colored output. [docs](https://docs.docker.com/engine/reference/run/#foreground)

## Here is a list of Osintgram's contributors:

<a href="https://github.com/Datalux/Osintgram/graphs/contributors">
  <img src="https://contributors-img.web.app/image?repo=Datalux/Osintgram" />
</a>

## External library 🔗

[Instagram API](https://github.com/ping/instagram_private_api)
