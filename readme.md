<h1 align="center"><code>$ snap-dl</code></h1>

<p align="center">
<a href="https://github.com/tg-z/snap-dl/issues"><img alt="github issues" src="https://img.shields.io/github/issues/tg-z/snap-dl?color=ff69b4"></a>
<a href="https://github.com/tg-z/snap-dl/stargazers"><img alt="github stars" src="https://img.shields.io/github/stars/tg-z/snap-dl?color=ff69b4"></a>
<a href="https://github.com/tg-z/snap-dl/graphs/contributors" alt="contributors">
<img src="https://img.shields.io/github/contributors/tg-z/snap-dl?color=ff69b4"/></a>
</p>

<p align="center">this project was inspired by <a href="https://github.com/ToTheMax/Snapchat-All-Memories-Downloader">Snapchat-All-Memories-Downloader</a> by <a href="https://github.com/ToTheMax">ToTheMax</a>. i wanted to recreate their project in bash because node.js scares me.</p>

<p align="center">
  <a href="#why">why?</a> •
  <a href="#install">install</a> •
  <a href="#usage">usage</a>
</p>

## why
snapchat allows you to takeout your data at any time, but it does not actually download your precious memories by default. in the takeout data, they give you a json file filled with download links for each and every one of your snapchat memories. this is not ideal for people who just want to backup all their memories and don't care about the technical data that snapchat gives you. this script reads the `memories_history.json` file in the `json` folder from your backup and gives you some options depending on what you want to do.

## dependencies
- jq: https://stedolan.github.io/jq/
- wget: https://www.gnu.org/software/wget/
- sed: https://www.gnu.org/software/sed/

## install
```sh
# clone repo
git clone https://github.com/tg-z/snap-dl
# cd into repo
cd snap-dl
# add script to path (optional)
cp snap-dl ~/bin
```

## usage
```sh
# follow this guide on how to get snapchat data
open https://support.snapchat.com/en-US/a/download-my-data/

# login to snapchat to request data
open https://accounts.snapchat.com/

# request snapchat data + wait for email with download link + open to download zipfile
open https://accounts.snapchat.com/accounts/downloadmydata/

# move zipfile to current dir + extract it
cp ~/Downloads/mydata*.zip .

# copy 'memories_history.json' file to snap-dl clone directory
cp mydata_*/json/memories_history.json .

# execute script to setup for download
./snap-dl init

# count how many memories you have
./snap-dl count

# download snapchat memories
./snap-dl download
```
