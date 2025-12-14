# 🔍 Guide Complet Discord OSINT

> **Documentation complète pour l'investigation et l'analyse de Discord**  
> Ressources, outils et techniques pour la recherche open source

---

## 📖 Table des Matières

- [🎯 Introduction](#-introduction)
- [🏗️ Architecture Discord](#️-architecture-discord)
- [⚙️ Configuration Initiale](#️-configuration-initiale)
- [🛠️ Outils Essentiels](#️-outils-essentiels)
- [🔎 Moteurs de Recherche](#-moteurs-de-recherche)
- [📊 Extraction de Données](#-extraction-de-données)
- [💻 Ressources Développeurs](#-ressources-développeurs)
- [🔐 Codes & Syntaxes](#-codes--syntaxes)
- [🌐 Recherche Avancée](#-recherche-avancée)
- [📚 Ressources Complémentaires](#-ressources-complémentaires)
- [⚠️ Sécurité & Pentesting](#️-sécurité--pentesting)

---

## 🎯 Introduction

Ce guide rassemble une collection exhaustive de ressources pour l'investigation OSINT sur Discord, incluant des outils de recherche, d'analyse et de documentation.

### 🔗 Liens Officiels

| Plateforme | URL |
|------------|-----|
| 🌐 Site officiel | [discord.com](https://discord.com/) |
| 🔑 Restauration d'accès | [discord.com/login](https://discord.com/login) |
| 👨‍💻 Portail développeurs | [discord.com/developers](https://discord.com/developers) |

---

## 🏗️ Architecture Discord

Discord utilise une **architecture client-serveur centralisée** avec les caractéristiques suivantes :

- 🎙️ **Communication** : Audio, vidéo et texte
- 🌐 **Technologie** : WebRTC (Web Real-Time Communication)
- 💻 **Plateformes supportées** :
  - Windows, Linux, macOS
  - Android, iOS
  - Interface web

```
┌─────────────┐      WebSocket/REST      ┌──────────────┐
│   Client    │ ◄──────────────────────► │   Serveur    │
│  (Vous)     │      (Gateway API)        │   Discord    │
└─────────────┘                           └──────────────┘
```

---

## ⚙️ Configuration Initiale

### 🔓 Activer le Mode Développeur

Le mode développeur permet d'accéder aux IDs des utilisateurs, serveurs et messages.

**📝 Étapes d'activation :**

1. Ouvrir Discord
2. Paramètres utilisateur ⚙️
3. Apparence → Paramètres avancés
4. Activer le **Mode Développeur**

**📚 Guides détaillés :**
- [Guide d'activation](https://techswift.org/2020/09/17/how-to-enable-developer-mode-in-discord/)
- [Obtenir votre UserID](https://techswift.org/2020/04/22/how-to-find-your-user-id-on-discord/)

---

## 🛠️ Outils Essentiels

### 🎯 Outils Principaux

| Outil | Description | Lien |
|-------|-------------|------|
| 📅 **Discord ID Creation Date** | Vérifie la date de création d'un compte | [hugo.moe](https://hugo.moe/discord/discord-id-creation-date.html) |
| 💬 **History Tracker** | Exporte l'historique des conversations | [dht.chylex.com](https://dht.chylex.com/) |
| 🔗 **Unfurl** | Analyse et décompose les URLs | [dfir.blog/unfurl](https://dfir.blog/unfurl/) |
| 📸 **Greenshot** | Capture d'écran avancée | [getgreenshot.org](https://getgreenshot.org/) |
| 🗑️ **Undiscord** | Suppression de messages en masse | [GitHub](https://github.com/victornpb/undiscord) |

---

## 🔎 Moteurs de Recherche

### 🖥️ Recherche de Serveurs

| Plateforme | Type | URL |
|------------|------|-----|
| 🔵 **Discord.me** | Annuaire catégorisé | [discord.me/servers](https://discord.me/servers) |
| ⚪ **Discord Official** | Recherche officielle | [discord.com/servers](https://discord.com/servers) |
| 🟣 **Disboard** | Découverte de communautés | [disboard.org](https://disboard.org/) |
| 🟢 **Discadia** | Liste complète | [discadia.com](https://discadia.com/) |
| 🔴 **Discord Center** | Annuaire centralisé | [discord.center](http://discord.center) |
| 🟡 **Discord Portal** | Portail communautaire | [discordportal.com](http://discordportal.com) |
| 🟠 **Discordlist.me** | Liste exhaustive | [discordlist.me](https://discordlist.me/) |
| 🔵 **Discord Tracker** | Statistiques de serveurs | [discord-tracker.ru](https://discord-tracker.ru/) |

### 🤖 Recherche de Bots

| Plateforme | Spécialité | URL |
|------------|-----------|-----|
| 🥇 **Top.gg** | Classement des bots | [top.gg](https://top.gg/) |
| 🤖 **Discord.bots.gg** | Annuaire complet | [discord.bots.gg](https://discord.bots.gg/) |
| 📋 **Discordbotlist** | Liste détaillée | [discordbotlist.com](https://discordbotlist.com/) |
| 🔍 **Ayblisting** | Alternative | [ayblisting.com](https://ayblisting.com/) |

### 👤 Recherche d'Utilisateurs

| Service | Fonctionnalité | URL |
|---------|---------------|-----|
| 🔍 **discord.name** | Recherche par nom | [discord.name](https://discord.name/) |
| 🎯 **DiscordHub** | Recherche avancée | [discordhub.com/user/search](https://discordhub.com/user/search) |
| 🛠️ **Discord Lookup** | Outil de recherche | [GitHub](https://github.com/discordlookup/discordlookup) |

---

## 📊 Extraction de Données

### 📋 Informations Utilisateur Extractibles

Données accessibles depuis un compte Discord authentifié :

```
┌─────────────────────────────────────┐
│  INFORMATIONS PERSONNELLES          │
├─────────────────────────────────────┤
│ 🆔 User ID (unique)                 │
│ 👤 Username & Discriminator         │
│ 🖼️ Photo de profil                  │
│ 🎨 Bannière de profil                │
│ 🏅 Badges & distinctions             │
└─────────────────────────────────────┘

┌─────────────────────────────────────┐
│  INFORMATIONS SERVEUR               │
├─────────────────────────────────────┤
│ 👑 Rôles attribués                   │
│ 📅 Date de création du compte        │
│ 📆 Date d'adhésion (par serveur)     │
│ 🎭 Type de compte                    │
└─────────────────────────────────────┘

┌─────────────────────────────────────┐
│  ACTIVITÉ & STATUT                  │
├─────────────────────────────────────┤
│ 🟢 Statut (En ligne/Hors ligne)     │
│ 💻 Client utilisé (Desktop/Mobile)   │
│ 🎮 Activité en cours                 │
└─────────────────────────────────────┘
```

---

## 💻 Ressources Développeurs

### 📚 Documentation Officielle

| Ressource | Description | Lien |
|-----------|-------------|------|
| 📖 **API Docs** | Documentation complète | [discord.com/developers/docs](https://discord.com/developers/docs/reference) |
| 🌐 **Gateway Docs** | WebSocket & Events | [Gateway API](https://discord.com/developers/docs/topics/gateway) |
| 🔌 **Webhooks** | Intégrations | [Webhooks Guide](https://discord.com/developers/docs/resources/webhook) |

### 🐙 Repositories GitHub

#### 📦 Collections & Ressources

- 🌟 [**awesome-discord**](https://github.com/jacc/awesome-discord) - Collection exhaustive de ressources
- 🏘️ [**awesome-discord-communities**](https://github.com/mhxion/awesome-discord-communities) - Communautés Discord
- 🔍 [**OSINT-Discord-resources**](https://github.com/Dutchosintguy/OSINT-Discord-resources) - Ressources OSINT

#### 💾 Bibliothèques & SDKs

- 📘 [**discord.js**](https://discord.js.org/#/) - Bibliothèque JavaScript
- 🐍 [**discord.py**](https://discordpy.readthedocs.io/en/stable/) - Bibliothèque Python
- 📋 [**Discord API Docs**](https://github.com/discord/discord-api-docs) - Documentation API

#### 🛡️ Sécurité

- ⚠️ [**Discord Scam Links DB**](https://github.com/Discord-AntiScam/scam-links) - Base de liens malveillants
- 🎣 [**Discord Phishing URLs**](https://github.com/Dogino/Discord-Phishing-URLs) - URLs de phishing
- 🔄 [**Actively Maintained Links**](https://github.com/nikolaischunk/discord-phishing-links) - Liste mise à jour

---

## 🔐 Codes & Syntaxes

### 🌐 Codes Gateway (WebSocket)

Les opcodes permettent la communication entre le client et le serveur Discord.

| Code | Nom | Description |
|------|-----|-------------|
| 0 | Dispatch | Événement serveur |
| 1 | Heartbeat | Maintien de connexion |
| 2 | Identify | Identification initiale |
| 7 | Reconnect | Reconnexion demandée |
| 9 | Invalid Session | Session invalide |
| 10 | Hello | Connexion établie |
| 11 | Heartbeat ACK | Heartbeat confirmé |

📖 [Documentation complète](https://discord.com/developers/docs/topics/opcodes-and-status-codes)

### 🏅 Codes de Badges Publics

| Code | Badge | Description |
|------|-------|-------------|
| 1 | 👷 Discord Employee | Employé Discord |
| 2 | 🤝 Partnered Server Owner | Propriétaire serveur partenaire |
| 4 | 🎉 HypeSquad Events | Événements HypeSquad |
| 8 | 🐛 Bug Hunter Level 1 | Chasseur de bugs niveau 1 |
| 64 | 🏠 House Bravery | Maison Bravoure |
| 128 | 🏠 House Brilliance | Maison Brillance |
| 256 | 🏠 House Balance | Maison Équilibre |
| 512 | ⏰ Early Supporter | Supporter précoce |
| 16384 | 🐛 Bug Hunter Level 2 | Chasseur de bugs niveau 2 |
| 131072 | 🔨 Discord Developer | Développeur vérifié |

📖 [Liste complète](https://github.com/Delitefully/DiscordLists/blob/master/flags.md)

---

## 🌐 Recherche Avancée

### 🔍 Syntaxe de Recherche Discord

Utilisez ces filtres dans la barre de recherche Discord :

```
from: @utilisateur          → Messages d'un utilisateur spécifique
mentions: @utilisateur      → Messages mentionnant un utilisateur
has: link | embed | file    → Messages contenant l'élément
before: AAAA-MM-JJ          → Messages avant une date
during: AAAA-MM-JJ          → Messages à une date précise
after: AAAA-MM-JJ           → Messages après une date
in: #canal                  → Messages dans un canal spécifique
```

**💡 Exemples de combinaisons :**

```
from: @John has: link after: 2024-01-01
→ Tous les liens partagés par John depuis janvier 2024

mentions: @Support in: #aide before: 2024-12-01
→ Mentions du support dans #aide avant décembre 2024
```

### 🔎 Google Dorks pour Discord

Remplacez `[USERNAME]` et `[USERID]` par vos cibles :

```
"[USERNAME] discord"                      → Recherche générale
[USERID]                                  → Recherche par ID
[USERNAME]#0000                           → Recherche avec discriminator
"[USERNAME] discord" site:twitter.com     → Recherche sur Twitter
"[USERNAME] discord" site:instagram.com   → Recherche sur Instagram
"[USERNAME] discord" site:github.com      → Recherche sur GitHub
"discord.gg" [USERNAME]                   → Invitations liées
```

**🎯 Recherches avancées :**

```
site:pastebin.com "discord.gg"           → Invitations sur Pastebin
site:github.com "discord token"          → Tokens exposés
inurl:discord site:reddit.com [TOPIC]    → Discussions Reddit
```

---

## 📚 Ressources Complémentaires

### 🔧 Outils Utilitaires

| Outil | Utilité | Lien |
|-------|---------|------|
| 📊 **Discord Status** | État des services | [discordstatus.com](https://discordstatus.com/) |
| 📖 **Discord Wiki** | Documentation communautaire | [discordia.me](https://discordia.me/en/home) |
| 🖼️ **Avatar Viewer** | Visualisation d'avatars | [discordzoom.com](https://discordzoom.com/en/) |
| 🔗 **Dic.gg** | Liens vanity personnalisés | [dsc.gg](https://dsc.gg/) |
| 🎨 **Profile Maker** | Créateur de profils | [discords.com/bio](https://discords.com/bio/profiles) |
| 📋 **Server Templates** | Modèles de serveurs | [discord.style](https://www.discord.style/) |

### 🔍 Outils d'Investigation

| Service | Fonctionnalité | Lien |
|---------|---------------|------|
| 🪝 **Discohook** | Créateur de webhooks | [discohook.org](https://discohook.org) |
| 🔐 **Canary Tokens** | Tokens de traçage | [canarytokens.org](https://canarytokens.org/nest/generate) |
| 📰 **Discord Leaks** | Fuites de conversations | [discordleaks.unicornriot.ninja](https://discordleaks.unicornriot.ninja/) |
| 👤 **Username Search** | Recherche multi-plateformes | [whatsmyname.app](https://whatsmyname.app/) |
| 😊 **Face Finder** | Reconnaissance faciale | [facecheck.id](https://facecheck.id/) |
| 📝 **Log Bot** | Enregistrement d'activités | [quark.bot](https://quark.bot/) |

### 🔗 Intégrations

- 🔌 [**Discord Integrations**](https://www.appypie.com/connect/apps/discord/integrations) - Connexions avec autres services
- 💬 [**Export Comments**](https://exportcomments.com/) - Export de commentaires
- 🔒 [**Discord 3rd Party Clients**](https://github.com/Discord-Client-Encyclopedia-Management/Discord3rdparties) - Clients alternatifs

---

## ⚠️ Sécurité & Pentesting

> **⚠️ AVERTISSEMENT IMPORTANT**  
> Ces ressources sont fournies **uniquement à des fins éducatives** et de recherche en sécurité.  
> Utilisez-les de manière **responsable et éthique**, dans le respect des lois et des conditions d'utilisation de Discord.

### 🔒 Ressources Éducatives

| Type | Description | Lien |
|------|-------------|------|
| 📜 **Console Scripts** | Scripts console Discord | [GitHub](https://github.com/ImLorio/All-Discord-Exploits) |
| 🖼️ **Image Exploit** | Recherche vulnérabilités images | [GitHub](https://github.com/TheonlyIcebear/Discord-Image-Exploit) |
| 💻 **Console Hacks** | Scripts et explications | [GitHub](https://github.com/Discord-Oxygen/Discord-Console-hacks) |
| 📦 **ZeroDiscord** | Collection d'outils NodeJS | [GitHub](https://github.com/cspi-git/ZeroDiscord) |

### 📋 Templates OSINT

- 📄 [**Discord Simple OSINT Template**](https://drive.google.com/file/d/18yU85e7o_11URHRcGlRwRRpQg8rhjWDE) - Template communautaire pour investigations

---

## 📝 Notes Importantes

### ✅ Bonnes Pratiques

- 🔐 Respectez la vie privée des utilisateurs
- ⚖️ Conformez-vous aux lois locales et internationales
- 📜 Suivez les conditions d'utilisation de Discord
- 🎯 Utilisez ces ressources uniquement à des fins légitimes (OSINT, sécurité, recherche)

### ⚠️ Limites Éthiques

- ❌ N'utilisez pas ces outils pour du harcèlement
- ❌ Ne collectez pas de données sans autorisation
- ❌ Ne partagez pas d'informations personnelles sans consentement
- ❌ N'exploitez pas de vulnérabilités à des fins malveillantes

---

## 📜 Licence & Crédits

### 📄 Licence

Ce projet est sous licence **MIT**. Consultez le fichier LICENSE pour plus de détails.

### 🙏 Remerciements

Ce guide compile les ressources de :
- [Discord-and-Telegram-OSINT-references](https://github.com/original-repo)
- [DiscordOSINT](https://github.com/original-repo)
- Communauté OSINT Discord

### 💝 Support

Si ce guide vous est utile, considérez le support du projet original :
[PayPal Donation](https://www.paypal.com/donate/?hosted_button_id=CTY9VF3VLD4BY)

---

<div align="center">

**📅 Dernière mise à jour :** Décembre 2024  
**🔄 Maintenance :** Active  
**📧 Contact :** Pour suggestions et corrections

---

*Ce guide est maintenu à des fins éducatives et de recherche OSINT légitimes.*  
*Utilisez ces ressources de manière responsable et conforme aux lois.*

</div>
