# Assistant IA — GitHub Pages + Cloudflare Worker

## Installation

1. Décompresse cette archive.
2. Envoie le contenu du dossier `portfolio-ai-admin` dans la racine de ton dépôt GitHub Pages (garde les sous-dossiers et fichiers ensemble).
3. Attends le déploiement GitHub Pages.
4. Ouvre ton portfolio et teste le bouton **Assistant IA**.

## Configuration

Le widget appelle le Worker Cloudflare configuré dans `admin-config.js` :
`https://portfolio-ai-proxy.rayencheese.workers.dev/`

Le modèle actuel est `gpt-4o-mini`. Pour changer de modèle, modifie la valeur `model` dans `admin-config.js` avec un identifiant accepté par ton fournisseur.

La clé API est configurée dans le Worker, pas dans les fichiers publics du site. Ne publie pas une vraie clé dans GitHub.

## À savoir

- Le Worker doit être déployé et autoriser l’origine `https://testingforsigma.github.io`.
- Le Worker transmet la requête au endpoint Selora compatible OpenAI.
- Les modifications proposées par le widget s’appliquent à la page ouverte et disparaissent au rechargement. Le widget ne crée pas de commit GitHub et ne modifie pas durablement les fichiers hébergés.
- L’éditeur reste limité à certains textes, styles et à l’ajout de sections simples ; il n’exécute pas de code arbitraire.
