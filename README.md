Description du Dockerfile :

Ce Dockerfile crée une image Docker pour un site web statique en utilisant le serveur Apache. Il est destiné à un projet de site web statique.

Étape 1 : Configuration de l'environnement

L'instruction ENV DEBIAN_FRONTEND=noninteractive configure l'environnement pour une installation non interactive des packages.

Étape 2 : Installation des dépendances

Les commandes apt update && apt install git -y mettent à jour les packages et installent Git.
La commande apt install apache2 -y installe le serveur Apache.

Étape 3 : Configuration du démarrage

La commande CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"] démarre Apache en mode avant-plan.

Étape 4 : Exposition du port

L'instruction EXPOSE 80 indique que le conteneur écoutera sur le port 80.

Étape 5 : Configuration du répertoire de travail

L'instruction WORKDIR /var/www/html définie le répertoire de travail pour les commandes suivantes.

Étape 6 : Configuration du volume

L'instruction VOLUME /var/log/apache2 crée un volume pour stocker les journaux Apache.

Étape 7 : Ajout des fichiers du site web

L'instruction ADD nano.tar.gz /var/www/html ajoute les fichiers du site web depuis une archive compressée.
