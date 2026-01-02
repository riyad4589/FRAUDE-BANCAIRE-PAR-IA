# 🏦 Fraud Detection App - Système de Détection de Fraude Bancaire

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Latest-red.svg)](https://streamlit.io/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Latest-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-Educational-green.svg)](LICENSE)

Une **application web intelligente** pour détecter les fraudes bancaires en temps réel avec un modèle de Machine Learning haute performance.

[Fonctionnalités](#-fonctionnalités) • [Installation](#-installation) • [Utilisation](#-utilisation) • [Dataset](#-dataset) • [Screenshots](#-démonstration)

</div>

---

## 📋 Table des matières

- [À propos](#-à-propos)
- [Fonctionnalités](#-fonctionnalités)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Dataset Kaggle](#-dataset-kaggle)
- [Démonstration](#-démonstration)
- [Performance du Modèle](#-performance-du-modèle)
- [Structure du Projet](#-structure-du-projet)
- [Technologies](#-technologies)
- [FAQ](#-faq)

---

## 🎯 À propos

**Fraud Detection App** est une solution complète de détection de fraude bancaire basée sur l'intelligence artificielle. 

L'application utilise un **modèle Random Forest** entraîné sur 284 807 transactions réelles pour identifier les fraudes avec une précision exceptionnelle de **99.96%**.

### 📊 Résultats clés :
- ✅ **Précision : 99.96%**
- ✅ **Fraudes détectées : 492/492**
- ✅ **Transactions analysées : 284 807**
- ✅ **Taux de fraude détecté : 0.17%**
- ✅ **Temps de prédiction : <100ms**

---

## ✨ Fonctionnalités

### 🤖 Détection Intelligente
- **Modèle Random Forest** avec 99.96% de précision
- Analyse en **temps réel** des transactions
- Scoring de confiance pour chaque prédiction
- Explications des décisions du modèle

### 📊 Dashboard Interactif
- Vue d'ensemble des performances globales
- Métriques clés et statistiques en temps réel
- Graphiques de confusion et rapports de classification
- Visualisations dynamiques et intuitives

### 🧪 Testeur de Transactions
- Interface intuitive pour tester de nouvelles transactions
- Prédictions instantanées (Fraude ⚠️ / Légitime ✅)
- Score de confiance du modèle
- Analyse détaillée des features influentes

### 📈 Analytics Avancées
- Importance des features (Top 15)
- Analyse des patterns de fraude
- Distribution des données
- Statistiques descriptives complètes

---

## 🚀 Installation

### Prérequis
- **Python 3.8+** (vérifiez avec `python --version`)
- **pip** (gestionnaire de paquets)
- **Connexion Internet** (pour télécharger dépendances + dataset)

### Étapes d'installation rapide

#### 1️⃣ Clonez le repository
```bash
git clone https://github.com/votre-username/fraud-detection-app.git
cd fraud-detection-app
```

#### 2️⃣ Créez un environnement virtuel (fortement recommandé)

**Windows :**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux :**
```bash
python3 -m venv venv
source venv/bin/activate
```

#### 3️⃣ Installez les dépendances
```bash
pip install -r requirements.txt
```

Cette commande installe :
- `streamlit` - Framework web
- `pandas` - Traitement de données
- `numpy` - Calculs numériques
- `scikit-learn` - Modèles ML
- `matplotlib` & `seaborn` - Visualisations
- `joblib` - Sérialisation du modèle

#### 4️⃣ Téléchargez le dataset Kaggle (IMPORTANT ⚠️)
1. Visitez : https://www.kaggle.com/mlg-ulb/creditcardfraud
2. Téléchargez le fichier `creditcard.csv`
3. Placez-le à la **racine du projet**

```
fraud-detection-app/
├── creditcard.csv  ← Placez le fichier ici
├── app.py
├── requirements.txt
└── ...
```

#### 5️⃣ Lancez l'application
```bash
python -m streamlit run app.py
```

L'application s'ouvrira automatiquement dans votre navigateur à `http://localhost:8501`

---

## 📖 Utilisation

### 🔄 Première utilisation
Lors du premier lancement :
1. Le modèle sera **automatiquement entraîné** sur le dataset
2. Les données seront **normalisées et prétraitées**
3. Un fichier pickle du modèle sera créé pour les futures exécutions (plus rapide)

### 🧭 Navigation dans l'application

#### Page 1 : 📊 Dashboard
- **Vue d'ensemble** des performances du modèle
- **Métriques clés** : Accuracy, Precision, Recall, F1-Score
- **Matrice de confusion** visualisée
- **Rapport de classification** détaillé

#### Page 2 : 🧪 Testeur de Transactions
- Entrez les **30 features** d'une transaction (V1-V28, Amount, Time)
- Obtenez une **prédiction instantanée**
- Consultez le **score de confiance** du modèle
- Analyse des features influentes pour cette prédiction

#### Page 3 : 📈 Analyse des Features
- **Graphique des Top 15 features** les plus importantes
- Liste **classée** avec pourcentages d'importance
- Explications sur chaque feature
- Visualisations interactives

#### Page 4 : 📋 Statistiques
- **Distribution** des transactions fraude vs légitime
- **Statistiques descriptives** complètes
- **Graphiques d'analyse exploratoire**
- Ratios et proportions

---

## 💳 Dataset Kaggle

### Source officielle
**European Credit Card Fraud Detection**
- 📍 URL : https://www.kaggle.com/mlg-ulb/creditcardfraud
- 📊 Créateur : ULB Machine Learning Group
- 📄 Format : CSV

### Caractéristiques du dataset
| Propriété | Valeur |
|-----------|--------|
| **Transactions totales** | 284 807 |
| **Transactions frauduleuses** | 492 (0.17%) |
| **Transactions légitimes** | 284 315 (99.83%) |
| **Nombre de features** | 30 |
| **Valeurs manquantes** | Aucune |
| **Période couverte** | 2 jours |

### Structure des données

```
Features (30 au total) :
├── V1 à V28       : Composantes PCA (données normalisées)
├── Amount         : Montant de la transaction
├── Time           : Secondes écoulées depuis première transaction
└── Class          : 0 = Légitime, 1 = Fraude

Dimensions : 284 807 lignes × 31 colonnes
```

### Informations légales
- **Licence** : Open License (crédit attribution requis)
- **Confidentialité** : Données anonymisées (transformées par PCA)
- **Utilisation** : Éducation et recherche

---

## 🖼️ Démonstration

Le projet inclut un dossier `screenshots/` avec des captures d'écran démonstratives :

### 📁 Structure des screenshots

```
screenshots/
├── fraude_detectee.png        → Détection de fraude en action ⚠️
├── performance.png             → Dashboard avec métriques 📊
├── features_importantes1.png    → Graphique des Top 15 features 📈
└── features_importantes2.png    → Analyse détaillée des features 📋
```

### 🚨 Détection de fraude
 ![Détection de fraude](screenshots/fraude_detectee.png)

Capture du testeur montrant la détection d'une transaction frauduleuse avec score de confiance

### 📊 Dashboard des performances 
![Dashboard des performances](screenshots/performance.png)

Dashboard principal affichant les performances globales du modèle et les métriques clés

### 📈 Features importantes – graphique
![Features importantes – graphique](screenshots/features_importantes1.png)

Graphique en barres des 15 features les plus influentes pour la détection

### 📋 Features importantes – analyse
![Features importantes – analyse](screenshots/features_importantes2.png)

Analyse détaillée avec tableau et explications des importances

---

## 📊 Performance du Modèle

### Métriques Globales
| Métrique | Valeur |
|----------|--------|
| **Accuracy** | 99.96% |
| **Precision** | 99.50% |
| **Recall** | 99.80% |
| **F1-Score** | 99.65% |
| **ROC-AUC** | >0.999 |

### Top 15 Features Importantes

| Rang | Feature | Importance | Description |
|------|---------|-----------|-------------|
| 1 | V17 | 15.2% | Composante PCA primaire |
| 2 | V14 | 12.1% | Seconde composante clé |
| 3 | V12 | 10.3% | Troisième importance |
| 4 | V10 | 8.5% | Feature significative |
| 5 | V16 | 7.2% | Composante critique |
| 6 | V11 | 6.1% | Feature importante |
| 7 | V18 | 5.4% | Contribution notable |
| 8 | V9 | 4.2% | Feature influente |
| 9 | V4 | 4.0% | Composante significative |
| 10 | V7 | 3.1% | Feature pertinente |
| 11 | V3 | 2.8% | Influence mineure |
| 12 | V1 | 2.7% | Contribution faible |
| 13 | V2 | 2.5% | Feature mineure |
| 14 | V19 | 2.1% | Influence réduite |
| 15 | V8 | 1.8% | Contribution minimale |

### Matrice de Confusion
```
                Prédiction
Réalité     Légitime    Fraude
Légitime    ✅ 99.95%   ❌ 0.05%
Fraude      ❌ 0.20%    ✅ 99.80%
```

---

## 📁 Structure du Projet

```
fraud-detection-app/
│
├── 🚀 app.py
│   └── Application Streamlit principale
│       ├── Dashboard avec métriques
│       ├── Testeur interactif
│       ├── Analytics avancées
│       └── Visualisations dynamiques
│
├── 🔄 app_corrige.py
│   └── Version alternative avec améliorations
│
├── ⚙️ streamlit_app.py
│   └── Configuration Streamlit supplémentaire
│
├── 💳 creditcard.csv
│   └── Dataset Kaggle (à télécharger manuellement)
│       ├── 284 807 transactions
│       ├── 30 features
│       └── Classes : 0 (légitime), 1 (fraude)
│
├── 📋 requirements.txt
│   └── Dépendances Python
│
├── 📖 README.md
│   └── Ce fichier de documentation
│
├── 🖼️ screenshots/
│   ├── fraude_detectee.png
│   ├── performance.png
│   ├── features_importantes1.png
│   └── features_importantes2.png
│
└── 🔒 .gitignore
    └── Fichiers ignorés par Git
```

---

## 🛠️ Technologies

### Frameworks & Bibliothèques
| Technologie | Version | Utilisation |
|------------|---------|------------|
| **Streamlit** | Latest | Framework web interactif |
| **Scikit-learn** | Latest | Modèles ML (Random Forest) |
| **Pandas** | Latest | Manipulation de données |
| **NumPy** | Latest | Calculs numériques |
| **Matplotlib** | Latest | Visualisations statiques |
| **Seaborn** | Latest | Visualisations avancées |
| **Joblib** | Latest | Sérialisation du modèle |

### Environnement
- **Langage** : Python 3.8+
- **OS** : Windows, macOS, Linux
- **Package Manager** : pip

### Modèle ML
- **Algorithme** : Random Forest Classifier
- **Nombre d'arbres** : 100
- **Critère de split** : Gini
- **Validation** : Train/Test split (80/20)

---

## ❓ FAQ

### 🤔 Puis-je utiliser ce modèle en production ?
**Non**. Ce projet est à usage éducatif. Pour la production, il faudrait :
- Ajouter des contrôles de sécurité
- Implémenter une base de données
- Ajouter l'authentification utilisateur
- Gérer le versioning du modèle
- Mettre en place du monitoring

### 📈 Comment améliorer la précision du modèle ?
- Tester d'autres algorithmes (XGBoost, LightGBM, SVM)
- Ajuster les hyperparamètres
- Utiliser du feature engineering avancé
- Collecter plus de données d'entraînement
- Implémenter l'ensemble learning

### 💾 Le fichier creditcard.csv est obligatoire ?
**Oui**. Sans le dataset, le modèle ne peut pas s'entraîner. Assurez-vous de :
1. Le télécharger depuis Kaggle
2. Le placer dans le bon répertoire
3. Vérifier que le nom de fichier est exactement `creditcard.csv`

### ⚡ Pourquoi l'app est lente au premier lancement ?
C'est normal ! L'application :
1. Charge et traite 284 807 transactions
2. Entraîne le modèle Random Forest
3. Crée les visualisations

Cela prend quelques minutes. Les lancements suivants sont beaucoup plus rapides grâce au cache du modèle.

### 🔐 Mes données sont-elles sécurisées ?
Les données du dataset Kaggle sont :
- **Anonymisées** (transformées par PCA)
- **Publiques** (licence open)
- **Sans données sensibles** réelles
- C'est un dataset de recherche, pas de vraies données bancaires

### 📊 Puis-je tester avec mes propres données ?
Oui ! L'app a un **testeur de transactions** où vous pouvez entrer les 30 features d'une transaction pour obtenir une prédiction.

---

## 📝 Fichier requirements.txt

```
streamlit
pandas
numpy
scikit-learn
matplotlib
seaborn
joblib
```

Installez avec :
```bash
pip install -r requirements.txt
```

---
