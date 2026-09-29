# numenys-site

Site vitrine statique de Numenys (numenys.fr), servi par GitHub Pages depuis `main`. L'état et les décisions vivent dans l'auto memory du projet.

## Règles du code
- Pages autonomes, zéro build : HTML/CSS/JS inline par page. Un JS partagé par deux pages est dupliqué volontairement ; on ne crée un fichier commun qu'à partir d'une 3e page qui en a besoin.
- Pas de formulaire de contact.
- Téléphone jamais en clair dans le HTML servi (ni texte, ni `href`, ni JSON-LD) : encodé en base64 dans un script inline, injecté au clic, le `<button>` devient un `<a href="tel:">`. L'email en clair reste le repli sans JavaScript.
- Tout ajout d'un outil de mesure d'audience met à jour la section « Mesure d'audience » des mentions légales dans le même commit.
- CSS copié depuis l'accueil : ne garder dans chaque page que les classes qu'elle utilise.

## Pièges connus
- Le panneau navigateur intégré rend mal les captures de ce site (écran noir, viewport à 0) : vérifier par le DOM et les styles calculés.
- `gh pr merge --delete-branch` échoue depuis un worktree (`main` occupé) : merger, puis `git push origin --delete <branche>`.
