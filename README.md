# ⛏ TIMES CRAFT — Sauve le mouton !

Jeu éducatif pour apprendre les tables de multiplication, sur le thème Minecraft.
Un zombie avance inexorablement vers ton mouton — réponds vite et juste pour survivre !

![Game Preview](https://img.shields.io/badge/HTML-Single%20File-orange?style=flat-square)
![No Dependencies](https://img.shields.io/badge/Dependencies-Aucune-green?style=flat-square)
![Leaderboard](https://img.shields.io/badge/Leaderboard-Global%20JSONBin-blue?style=flat-square)

---

## 🎮 Fonctionnement du jeu

- Le **zombie avance tout seul** vers le mouton — la partie finit quand il l'atteint
- **Erreur** → le zombie bondit en avant
- **Bonne réponse** → rien (le zombie continue d'avancer, implacable)
- Tous les **10 bonnes réponses** → le zombie accélère (⚡ la jauge de vitesse monte)
- Questions **bonus** aléatoires (table × nombre à 2 chiffres) → bonne réponse = zombie recule !
- Le **mouton devient de plus en plus effrayé** à mesure que le zombie approche

**Deux modes :** QCM (4 choix) ou Frappe libre (clavier/pavé numérique)  
**Tables disponibles :** ×1 à ×10  
**Leaderboard mondial** partagé entre tous les joueurs (JSONBin)

---

## 🚀 Mise en ligne sur GitHub Pages

### 1. Créer le dépôt

```bash
# Crée un nouveau dépôt sur github.com, puis :
git clone https://github.com/TON_USERNAME/times-craft.git
cd times-craft
```

### 2. Déposer le fichier

Copie `tables-minecraft.html` dans le dossier cloné, **renomme-le `index.html`** :

```bash
cp tables-minecraft.html index.html
# ou renomme directement le fichier en index.html
```

### 3. Commit et push

```bash
git add index.html
git commit -m "🎮 Times Craft — jeu tables de multiplication"
git push origin main
```

### 4. Activer GitHub Pages

1. Va sur ton dépôt → onglet **Settings**
2. Section **Pages** dans le menu gauche
3. Source : **Deploy from a branch**
4. Branch : `main` / `(root)`
5. Clique **Save**

⏱ Attends 1–2 minutes, puis ton jeu est accessible à :  
`https://TON_USERNAME.github.io/times-craft/`

---

## 🗂 Structure du projet

```
times-craft/
└── index.html        ← tout le jeu (HTML + CSS + JS en un seul fichier)
```

Pas de `package.json`, pas de build, pas de dépendances. Un seul fichier suffit.

---

## 🏆 Leaderboard global (JSONBin)

Les scores sont stockés sur [JSONBin.io](https://jsonbin.io). La clé API est intégrée directement dans le fichier HTML — c'est normal pour un site statique sans backend.

> ⚠️ Si tu vois des scores aberrants ou veux repartir à zéro : connecte-toi sur jsonbin.io, ouvre ton bin `6a071ea9adc21f119aa499ab` et remets le contenu à `{"scores":[]}`.

Le plan gratuit JSONBin permet **10 000 requêtes/mois** — largement suffisant pour un usage familial.

En cas de panne JSONBin, les scores sont automatiquement sauvegardés en local (localStorage du navigateur) comme fallback.

---

## 🛠 Personnalisation

Tout se règle en haut du `<script>` dans `index.html` :

| Constante | Valeur par défaut | Effet |
|---|---|---|
| `BASE_SPEED` | `0.030` | Vitesse initiale du zombie (% par 100ms) |
| `SPEED_PER_10OK` | `0.015` | Accélération tous les 10 bonnes réponses |
| `MAX_SPEED` | `0.22` | Vitesse maximale du zombie |
| `ERROR_JUMP` | `8` | Bond du zombie en % sur erreur |
| `BONUS_PUSH` | `14` | Recul du zombie en % sur bonus réussi |
| `BONUS_MIN/MAX` | `6` / `13` | Fréquence des questions bonus (en nb de bonnes réponses) |

---

## 📱 Compatibilité

- ✅ Desktop (Chrome, Firefox, Safari, Edge)
- ✅ Mobile / tablette (pavé numérique tactile intégré)
- ✅ Pas besoin d'internet pour jouer (sauf pour le leaderboard et les polices Google Fonts)
