# ED_data

<details>
    <summary>Fiche Adum</summary>

### Objectifs :

Faire le ménage, organiser et nettoyer ses données avec ArchiFiltre, Nuage (nextcloud), OpenRefine... :

- Connaître des méthodes d’organisation de données
- Savoir trier ses données
- Connaître des outils de nettoyage de données


### Programme :

- Explorer ses données existantes avec Archifiltre
- Stocker et sauvegarder
- Nettoyer avec OpenRefine

### Equipe pédagogique :

Julien Rabaud, Service Commun de Documentation (SCD) & Pôle Numérique, <julien.rabaud@univ-pau.fr>

### Méthode pédagogique :

Le module alternera entre interventions magistrales et TD d’application sur ordinateur.

### Compétences acquises à l'issue de la formation :

Savoir utiliser un ensemble d’outils techniques de base pour gérer et organiser ses données dans le cadre d’une activité de recherche.

### Langue de l'intervention :

français

### La formation participe à l'objectif suivant :

être directement utile pour la réalisation des travaux personnels de recherche

</details>

(TOC)

## Science Ouverte

### Chez [DORANum](https://doranum.fr/)

- [Comment bien nommer ses fichiers](https://doranum.fr/stockage-archivage/comment-nommer-fichiers_10_13143_wgqw-aa59/)

- [La sauvegarde 3-2-1](https://doranum.fr/stockage-archivage/la-sauvegarde-3-2-1_10_13143_1gdh-tk61/) [video 1'49]


## Avoir Un *Cloud*

### Nuage à l'UPPA

<img src="https://nextcloud.com/wp-content/uploads/2022/10/nextcloud-logo-blue-transparent.svg" width="200" style="display:block;margin-left:auto;margin-right:auto;">

Instance palloise du logiciel [Nextcloud](https://nextcloud.com/)

- <https://nuage.univ-pau.fr>

Télécharger les clients de bureau ou pour mobile : 

- <https://nextcloud.com/install/#install-clients>

### ShareDocs chez Huma-Num

![](https://humanid.huma-num.fr/static/humanid/images/apps/sharedocs.png)

Instance du logiciel [FileRun](https://filerun.com/)

- [Documentation ShareDocs **Stockage**](https://documentation.huma-num.fr/sharedocs-stockage/)
- [Documentation ShareDocs **Traitements**](https://documentation.huma-num.fr/sharedocs-traitement/)

Clients Compatibles (dont les clients *NextCloud*)

- <https://filerun.com/download>

## Archifiltre

![](https://archifiltre.fabrique.social.gouv.fr/app/uploads/2024/07/Aime-par-Chloe-1-e1721076329956-150x150.png)

Archifiltre, développé par des archivistes et pour des archivistes, peut être un excellent outil pour les doctorants qui gèrent une grande quantité de données, notamment dans les disciplines où la collecte, l'organisation et la structuration des fichiers numériques jouent un rôle important.

### Organisation des données de recherche

- **Arborescence des fichiers** : Archifiltre permet de visualiser facilement la structure des dossiers et des fichiers, ce qui est idéal pour identifier les dossiers mal organisés ou les fichiers mal nommés.
- **Création d’un plan d’organisation** : Le logiciel aide à structurer les données selon des logiques claires (par thématiques, chronologies, ou types de données).

### Nettoyage des fichiers

- **Identification des doublons** : En accumulant des données (articles, rapports, bases de données, résultats expérimentaux), il arrive souvent de générer ou de télécharger des fichiers en double. Archifiltre peut détecter ces doublons et les supprimer.
- **Détection des fichiers inutilisés ou obsolètes** : Le logiciel aide à repérer les fichiers inutiles (fichiers temporaires, fichiers corrompus ou versions obsolètes).

### Préparation pour la sauvegarde ou le partage

- **Préparation de versements** : Pour partager des données avec d'autres chercheurs, des institutions, ou pour les déposer dans des archives ouvertes, Archifiltre peut générer des rapports structurés sur l’ensemble des données.
- **Export de rapports** : Les doctorants peuvent documenter leurs fichiers avec des métadonnées pour faciliter leur réutilisation.

### Gestion des grandes quantités de données

- Si un doctorant travaille avec de nombreuses sources (articles, images, données expérimentales, etc.), Archifiltre peut aider à rationaliser la gestion de ces informations et à détecter les déséquilibres (fichiers sur-représentés ou absents).

### Facilitation de la rédaction de la thèse

- Une base de données bien structurée simplifie la recherche d’informations spécifiques lors de la rédaction, évitant de perdre du temps à chercher dans des dossiers désorganisés.

En résumé, Archifiltre peut devenir un allié précieux pour rester organisé, optimiser l’espace de stockage, et préparer des dépôts ou publications selon des normes claires. Si tu es doctorant(e), tu pourrais aussi adapter ses fonctionnalités à tes besoins spécifiques, selon ton domaine d'étude ! 🙂


## Nettoyer des données avec OpenRefine

<img src="https://openrefine.org/img/openrefine_logo.svg" width="200" style="display:block;margin-left:auto;margin-right:auto;">

### Liens

- Télécharger : 

### Exercice

fichier `dirty_data.csv`


#### Description des problèmes dans les données :

- **Nom** : Incohérences dans les espaces, casse (majuscules/minuscules), et doublons possibles.
- **Email** : Des doublons sont présents.
- **Date d'inscription** : Formats de date incohérents et des valeurs manquantes.
- **Pays** : Variations dans la casse et des espaces inutiles.
- **Score** : Contient des valeurs "N/A" au lieu de données numériques.

#### Comment nettoyer ces données avec OpenRefine :

1.  Charger les données :
    
    -   Ouvrir OpenRefine et importer le fichier CSV.

2.  **Nettoyage des colonnes :**
    
    -   **Nom** :
        -   Utiliser `Edit cells > Common transforms > Trim leading and trailing whitespace` pour supprimer les espaces inutiles.
        -   Utiliser `Edit cells > Common transforms > To titlecase` pour harmoniser la casse (première lettre en majuscule).
        -   Vérifier les doublons via `Facet > Text facet`.
    -   **Email** :
        -   Vérifier les doublons via `Facet > Text facet` et identifier les entrées répétées.
    -   **Date d'inscription** :
        -   Convertir les dates en un format uniforme via `Edit cells > Transform` avec une expression comme : `value.replace("/", "-").replace(" ", "-")`.
        -   Traiter les valeurs manquantes via `Facet > Customized facet > Facet by blank` pour les détecter.
    -   **Pays** :
        -   Supprimer les espaces inutiles via `Trim whitespace`.
        -   Uniformiser la casse via `To titlecase`.
    -   **Score** :
        -   Remplacer les valeurs "N/A" par `null` ou une valeur par défaut via `Edit cells > Transform` : `if(value == "N/A", null, value)`.
3.  **Export des données nettoyées :**
    
    -   Une fois terminé, exporte les données nettoyées en cliquant sur `Export > Export to CSV`.


## Pour gérer les Images : Tropy

<img src="https://hn.maisondelarecherche.fr/wp-content/uploads/2017/10/tropy.jpg" width="200" style="display:block;margin-left:auto;margin-right:auto;">


Mon support d'atelier : 