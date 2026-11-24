# PFE — Détection par caméra : bibliographie

## 📊 [Ouvrir le tableau des articles](https://tommy1342.github.io/PFE-detection-camera/biblio/)

Tableau interactif de l'état de l'art : tri par colonne, recherche, filtres par thème et par mot-clé, clic sur une ligne pour voir la fiche complète.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `biblio/articles.json` | La liste des articles (les données). C'est le seul fichier à modifier pour ajouter ou mettre à jour un article. |
| `biblio/index.html` | La page qui affiche le tableau. Pas besoin d'y toucher. |

## Ajouter un article

1. Ouvrir `biblio/articles.json`.
2. Copier un bloc `{ ... }` existant, le coller après le dernier, **séparer les blocs par une virgule**.
3. Remplir les champs :

| Champ | Contenu |
|---|---|
| `titre` | Titre de l'article |
| `lien` | URL (DOI, arXiv, PDF…) |
| `annee` | Année de publication |
| `pipeline` | Les grandes étapes de la méthode |
| `quelles_images` | Type d'images (caméra, capteur, conditions…) |
| `combien_images` | Taille du jeu de données et découpage |
| `annotation` | Classes, type d'annotation, outil |
| `pretraitement` | Redimensionnement, normalisation, augmentation… |
| `modele_detection` | Modèle utilisé (ex. YOLOv5s, Faster R-CNN) |
| `transfer_learning` | `oui` ou `non` |
| `entrainement` | Époques, optimiseur, taux d'apprentissage, matériel |
| `validation` | Protocole de validation |
| `resultats` | Résultats chiffrés principaux |
| `limites` | Limites relevées |
| `metriques_collision` | Métriques liées à la collision (TTC, fausses alertes…) |
4. Enregistrer, puis publier :

```
git add .
git commit -m "Ajout d'un article"
git push
```

Le tableau en ligne se met à jour environ une minute après le `push`.

> Si le tableau affiche « Impossible de charger articles.json », il y a une erreur de syntaxe dans le JSON (souvent une virgule en trop ou manquante).

## Voir le tableau en local

Ouvrir `index.html` en double-cliquant ne fonctionne pas (le navigateur bloque la lecture du JSON). Lancer plutôt, depuis le dossier du dépôt :

```
python -m http.server --directory biblio
```

puis ouvrir <http://localhost:8000>.
