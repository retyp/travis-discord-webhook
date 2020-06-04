<p align="center"><a href="https://retyp.app/" target="_blank" rel="noopener noreferrer"><img width="100" src="https://avatars2.githubusercontent.com/u/59448556?s=400&v=4" alt="retyp's logo"></a></p>
  
<p align="center">
  <a href="https://discord.gg/n53UjwQ"><img src="https://img.shields.io/badge/join-our%20discord-7289da.svg" alt="Support"></a>
</p>

<h2 align="center">TRAVIS-DISCORD-WEBHOOK</h2>

---

## Introduction

Simple script shell postant les résultats des builds des différents éléments de [retyp](https://retyp.app) dans le salon #build-status du [discord officiel de retyp](https://discord.gg/n53UjwQ).

## Mise en place

La mise en place est simple et rapide :
* Créer un webhook sur le serveur discord.
* Créer une variable `DISCORD_WEBHOOK_URL` sur Travis aillant pour valeur l'adresse du webhook créé sur discord.

  ![img](https://i.imgur.com/SXcLND7.png)

* Rajouter la configuration suivante dans le fichier `.travis.yml` :

  ```yml
  after_success:
    - wget https://raw.githubusercontent.com/DiscordHooks/travis-ci-discord-webhook/master/send.sh
    - chmod +x send.sh
    - ./send.sh success $DISCORD_WEBHOOK_URL
  after_failure:
    - wget https://raw.githubusercontent.com/DiscordHooks/travis-ci-discord-webhook/master/send.sh
    - chmod +x send.sh
    - ./send.sh failure $DISCORD_WEBHOOK_URL
  ```

## Résultat

<p align="center">
  <img src="https://i.imgur.com/JwKLd4k.png">
  <br>
</p>

---

*Forked from [DiscordHooks/travis-ci-discord-webhook](https://github.com/DiscordHooks/travis-ci-discord-webhook)*