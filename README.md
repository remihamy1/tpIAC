# tpIAC

## Objectif
Créer une infrastructure cloud sur GCP pour héberger une application web multi-tier.
2 instance web, accessible en http/https
1 instance de base de données avec un user admin par défaut
1 load balancer pour exposer le traffic sortant des serveur web
Les règles de firewall qui vont bien

## Description du Projet
Vous allez déployer une application web multi-tier en utilisant Terraform. L'infrastructure comprendra les éléments suivants :

### Réseau VPC : Utilisez le vpc-tp
### Sous-réseaux :
Un sous-réseau pour les instances de l'application.
Un sous-réseau pour les instances de la base de données.
Un sous-réseau pour les instances du serveur web.
### Instances de VM :
Plusieurs instances pour le tiers de l'application (par exemple, des serveurs d'application).
Une instance ou plusieurs pour le tiers de la base de données, si nécessaire.
Des instances pour le tiers du serveur web.
### Règles de pare-feu :
Autoriser le trafic SSH, HTTP et HTTPS.
Règles spécifiques pour les communications internes entre les sous-réseaux.
### Load balancer: 
Créez un loadbalancer pour exposer votre traffic à l'exterieur
### Variables :
Nombre d'instances pour chaque tier.
Type de machine à utiliser pour chaque tier.
Création conditionnelle d'instances de base de données.
### Locaux :
Noms des instances dynamiques basés sur les variables.
### Boucles :
Création dynamique d'instances en utilisant des boucles for et count.
### Conditions :
Création conditionnelle de ressources basées sur les variables d'entrée (par exemple, activer ou désactiver la création d'instances de base de données).
#### Détails Techniques
Sous-réseaux : Diviser le VPC en sous-réseaux distincts pour chaque tier de l'application.
### Instances :
Utiliser des boucles pour créer dynamiquement plusieurs instances pour le tiers de l'application et du serveur web.
Utiliser des conditions pour décider de la création d'instances de base de données.
Règles de pare-feu : Définir des règles pour autoriser les connexions SSH (port 22), HTTP (port 80) et HTTPS (port 443).

### Output: 
Pouvoir voir les choses qui ont été créées grâce à un output.tf
