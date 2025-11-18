# Breast Cancer Prediction using Machine Learning

Ce projet reproduit et améliore l'étude présentée dans l'article **"Prediction of Breast Cancer using Machine Learning Approaches"** (Rabiei et al., 2022). L'objectif est de prédire le cancer du sein à partir de données démographiques, cliniques et mammographiques en utilisant différentes approches de machine learning.

##  Résumé de l'article original

- **Base de données** : 5 178 dossiers patients (25% de cas de cancer) avec 24 caractéristiques
- **Algorithmes utilisés** : Random Forest, Gradient Boosting Trees, Multi-Layer Perceptron
- **Optimisation** : Algorithme génétique pour la sélection des hyperparamètres
- **Résultats principaux** :
  - Meilleure performance avec Random Forest (Accuracy: 80%, Sensibilité: 95%)
  - Les caractéristiques mammographiques améliorent les performances des modèles
  - Facteurs les plus importants : antécédents familiaux, antécédents personnels, densité mammaire, âge

##  Objectifs de ce projet

1. Implémenter les modèles de l'article avec des améliorations potentielles
2. Reproduire les résultats et analyser les performances
3. Explorer d'autres approches de machine learning
4. Fournir une base reproductible pour la recherche sur la prédiction du cancer du sein

##  Données

### Caractéristiques utilisées (24 au total)

**Démographiques (11)** :
- Âge, Âge de la ménopause, Première grossesse, Âge des premières règles
- IMC, Allaitement, Activité physique, Éducation
- Événements stressants, Tabagisme, Statut marital

**Laboratoire (9)** :
- Durée pilule contraceptive, Durée THS, Autres cancers personnels
- Antécédents familiaux de cancer, Exposition aux rayons X
- Vitamine D3, Biopsie, Hystérectomie, Antécédents personnels de cancer

**Mammographie (4)** :
- Densité mammaire, Micro-lobulation, Circonscription, Calcifications

### Prétraitement
- Suppression des enregistrements masculins
- Gestion des valeurs manquantes
- Application de SMOTE pour équilibrer les classes
- Validation croisée (K=3) et split train-test (75%-25%)

##  Modèles implémentés

### 1. Random Forest (RF)
- Nombre d'arbres : 151
- Profondeur max : 3, 5, 8
- Min samples split : 5, 10

### 2. Gradient Boosting Trees (GBT)
- Taux d'apprentissage : 0.01-0.2
- Nombre d'estimateurs : 10
- Profondeur max : 3, 5, 8

### 3. Multi-Layer Perceptron (MLP)
- Couches cachées : 10
- Fonctions d'activation : sigmoid, tanh
- Optimiseurs : Adam, SGD
- Taux d'apprentissage : 0.01-0.2

### 4. Optimisation par Algorithme Génétique
- Population : 5
- Enfants par génération : 50
- Générations : 10
- Critère : maximisation de l'accuracy

##  Métriques d'évaluation

- **Accuracy** : Proportion de prédictions correctes
- **Sensibilité** : Capacité à détecter les vrais positifs
- **Spécificité** : Capacité à identifier les vrais négatifs
- **AUC** : Aire sous la courbe ROC

##  Installation et utilisation

```bash
# Cloner le repository
git clone [url-du-repo]
cd breast-cancer-prediction

# Installer les dépendances
pip install -r requirements.txt

# Lancer l'entraînement des modèles
python train_models.py

# Évaluer les performances
python evaluate_models.py
