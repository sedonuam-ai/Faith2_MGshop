# M.G. SHOP — Gestion Stock & Ventes

Application web installable (PWA), avec logo, fonctionnant **hors connexion** après la première visite.
Toutes les données (stock, ventes, historique) restent enregistrées **uniquement sur le téléphone** de l'utilisateur (aucun serveur, aucun compte).

## 1. Mettre le site sur GitHub Pages (gratuit)

1. Créez un compte sur https://github.com si vous n'en avez pas.
2. Créez un nouveau dépôt (repository) — par exemple `mg-shop`. Cochez "Public".
3. Mettez **tous les fichiers de ce dossier** (`index.html`, `manifest.json`, `service-worker.js`, et le dossier `icons/`) à la racine du dépôt :
   - soit en les glissant-déposant sur la page GitHub ("Add file" → "Upload files"),
   - soit avec `git` :
     ```
     git init
     git add .
     git commit -m "M.G. SHOP"
     git branch -M main
     git remote add origin https://github.com/VOTRE-NOM/mg-shop.git
     git push -u origin main
     ```
4. Dans le dépôt : **Settings → Pages**.
5. Sous "Build and deployment" → "Source", choisissez **Deploy from a branch**.
6. Branche : `main`, dossier : `/ (root)`. Cliquez **Save**.
7. Attendez 1 à 2 minutes. Votre site sera disponible à l'adresse :
   `https://VOTRE-NOM.github.io/mg-shop/`

## 2. Installer l'application sur le téléphone

### Android (Chrome)
1. Ouvrez `https://VOTRE-NOM.github.io/mg-shop/` dans Chrome.
2. Un bandeau "Ajouter à l'écran d'accueil" apparaît (sinon : menu ⋮ → **Installer l'application**).
3. Confirmez. L'icône **M.G. SHOP** apparaît sur l'écran d'accueil, comme une vraie application.

### iPhone (Safari)
1. Ouvrez le lien dans Safari.
2. Bouton Partager (carré avec flèche) → **Sur l'écran d'accueil**.
3. Confirmez.

## 3. Utilisation hors connexion

- La **première ouverture** doit se faire avec internet (pour télécharger l'application une fois).
- Ensuite, l'application fonctionne **sans connexion** : ouvrez-la comme n'importe quelle app installée.
- Un bandeau "Mode hors connexion" s'affiche en haut quand le téléphone n'a pas de réseau — c'est normal, l'app continue de fonctionner.

## 4. Mettre à jour l'application plus tard

Si vous modifiez `index.html` (ou tout autre fichier) et republiez sur GitHub :
- Ouvrez `service-worker.js` et changez `mgshop-cache-v1` en `mgshop-cache-v2` (incrémentez le numéro).
- Republiez sur GitHub. Les téléphones téléchargeront automatiquement la nouvelle version au prochain accès internet.

## 5. Sauvegarde des données

Les données sont stockées dans la mémoire du navigateur (localStorage) **sur chaque téléphone individuellement**.
- Si vous désinstallez l'app ou effacez les données du navigateur, l'historique est perdu.
- Cette version ne synchronise pas entre plusieurs téléphones : chaque appareil a ses propres données.
- Si vous avez besoin d'une synchronisation multi-appareils (plusieurs vendeurs, un seul stock partagé), cela demande une base de données en ligne — dites-le moi et je peux préparer cette évolution.
