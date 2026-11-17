# MEWFLIX — page de téléchargement

Page publiée sur GitHub Pages : **https://taharhajji.github.io/mewflix/**

Elle liste les fichiers des releases de
[taharhajji/MovixOpenSource](https://github.com/taharhajji/MovixOpenSource/releases) :
Windows (installation + portable), macOS (puce Apple + Intel), Chromebook / Linux (.deb amd64 + arm64)
et Android TV (APK, lien court `is.gd/mewflixtv`), avec l'historique de toutes les versions.

- La liste est lue **en direct** depuis l'API GitHub : une nouvelle release apparaît toute seule, rien à modifier ici.
- Si l'API ne répond pas (limite de 60 requêtes/heure par adresse IP), la page se rabat sur `releases.json`,
  un instantané à rafraîchir de temps en temps :

  ```bash
  gh api repos/taharhajji/MovixOpenSource/releases --paginate > releases.json
  ```

- Les tags `v*` sont les versions ordinateur, `tv-v*` les versions Android TV. La release `tv-v1.0.0` porte le
  fichier servi par le lien court (remplacé à chaque version) et n'est donc pas listée comme une version.
- Fichiers techniques masqués : `latest.yml`, `latest-mac.yml`, `*.blockmap` (utilisés par la mise à jour automatique).

Tester en local : `python -m http.server 5310` dans ce dossier, puis http://localhost:5310.
