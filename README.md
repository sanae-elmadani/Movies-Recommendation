# Movies-Recommendation
1-Mise en scène 

Les systèmes de recommandation sont une forme spécifique de filtrage de l'information (SI) visant à présenter les éléments d'information (films, musique, livres, news, images, pages Web, etc) qui sont susceptibles d'intéresser l'utilisateur.
L’objectif de ce mini-projet est de créer un système de recommandations de films en se servant de  la librairie MLlib de Spark.

2-Présentation du contexte

L’objectif de ce projet est d’implémenter un système de recommandation qui à partir d’une base de donnée contenant les Ids des utilisateurs, les items et les notes, permet de :

Prédire la note qu’un utilisateur peut attribuer à un film.
Générer les 10 meilleures recommandations de films pour un utilisateurs.
Générer les 10 meilleures recommandations d'utilisateurs pour un film.

3-Les systèmes de recommandation

3-1 Recommandation Sociale ou « Collaboratif Filtering »: Le filtrage collaboratif est une technique utilisée par les systèmes de recommandation.Elle se base sur les événements qui lient les utilisateurs avec les items comme les notes, les likes, le nombre de visites de la page…
3-1-1 les types Le filtrage collaboratif
Memory based qui se base sur le principe de similarité: 
User based: « Les utilisateurs qui sont similaires à vous, ont aimé aussi ... » 
Item based: « Les utilisateurs qui ont aimé ça, ont aimé aussi ... »
Model based qui se base sur la factorisation de matrices: 
SVD Singular Vector Decomposition. 
ALS Alternating Least Square. 
SGD Stochastic Gradient Descent.
3-2-Recommandation objet ou « Content-based »: 
Elle  se base sur les caractéristiques des users/items: 
En gros, elle calcule la corrélation entre les caractéristiques de tous les items pour trouver l’item le plus corrélé avec l’item sélectionné. 
3-3 Justification de choix d’algorithme ALS:

On ne peut pas utiliser le content based vu qu’on n’a pas les caractéristiques des utilisateurs ou des items. 
Le Collaboratif filtering, Memory based est très coûteux vu qu’il calcule la corrélation entre tous les utilisateurs et entre tous les items à chaque fois qu’on a des nouvelles données.
Pour notre projet nous avons  choisi de travailler avec Le  système de recommandation social “collaboratif filtering, Model based “ car il est plus rapide et pour le choix de l’algorithme nous avons choisi l’algorithme ALS car il est le plus scalable et le bien  documenté. 


4-Solution technique 

Spark est un framework open source de calcul distribué qui se base sur la notion des RDDs (Resilient Distributed Dataset) qui sont des collections des données. Notons que les opérations sur les RDDs suivent implicitement le paradigme “map reduce” .

Spark travaille en mémoire vive ce qui est cent fois plus rapide que Hadoop qui tourne sur disques.Ce qui est nouveau chez Spark, c’est qu’on peut mettre directement des données sur la mémoire cache ce qui réduit énormément le temps d'exécution. 

5-conclusion
La librairie MlLib de spark offre des méthodes d’analyses de données très performantes, notamment la méthode ALS du collaborative filtering, Model based.















