[![H&D DRS Sources Loog](https://github.com/em-squared/heros-et-dragons-drs/blob/master/docs/.vuepress/public/dragon_binaire.png "H&D DRS Sources")](#)

# Héros & Dragons DRS
Ici se trouvent les sources du Document de Référence Système pour le jeu de rôle Héros & Dragons (H&D).

## Documentation
### Publication
Seuls les contenus soumis à la licence OGL sont publiés. Si des contenus sont manquants, demandez-vous en premier lieu s'ils sont sous licence OGL ou pas.
Exemples :
* Les textes de description et d'ambiance ne sont pas OGL
* Les profils techniques du Livre des monstres ne sont pas OGL. Kobbold Press n'a pas autorisé leur publication après sollicitation. Ne sont autorisés que les Noms, Indice de dangerosité, Références aux pages du livre, éléments de catégorisation (type de créature, environnement, type de donjon).

### Correction de contenu
Si vous relevez des erreurs, il suffit d'éditer le fichier source directement sur Github. Un fork sera automatiquement généré, et vous pourrez effectuer une pull request une fois votre correction commitée. La pull request sera acceptée si elle est valide.
Si vous ne souhaitez pas (ou ne pouvez pas) corriger une erreur vous-même, vous pouvez [créer une issue](https://github.com/em-squared/heros-et-dragons-drs/issues/new) avec le label `documentation`. Soyez le plus précis possible en incluant des liens vers les contenus erronés et les sources des corrections. L'erreur sera corrigée si elle est avérée.

### Développement
Pour travailler sur le projet, vous devrez au préalable télécharger les sources :
```
git clone git@github.com:em-squared/heros-et-dragons-drs.git
```
Puis installer les dépendances :
```
cd heros-et-dragons-drs
yarn install
```
ou
```
cd heros-et-dragons-drs
npm install
```
Et lancer le service en local :
```
yarn dev
```
ou
```
npm run dev
```

### Production
Au vu de la quantité de fichiers à traiter, le build est gourmand en mémoire et en ressource processeur. Sur une configuration moyenne, le build prend un peu moins de 2 minutes, mais peut monter à 5 minutes sur des configurations plus modestes. La consommation mémoire peut monter jusqu'à 5Go. Il faudra donc impérativement augmenter la plage mémoire allouable à Node lors du build :
```
export NODE_OPTIONS=--max-old-space-size=8192
```
Pour compiler le projet en vue d'un déploiement, vous devrez vous assurer qu'il ne contient pas de lien internes morts :
```
yarn check-md
```
ou
```
npm run-script check-md
```
Puis lancer la compilation :
```
yarn build
```
ou
```
npm run build
```
Vous pouvez ensuite tester le site statique compilé en lançant un serveur local :
```
cd docs/.vuepress/dist
python -m SimpleHTTPServer 8081
```
Le site statique sera accessible sur http://localhost:8081

### Version Electron

Il est également possible de wrapper le site via Electron, pour disposer d'une version standalone

#### Lancer l'application en mode developpeur
```
yarn electron-dev
```
ou
```
npm run electron-dev
```

#### Empaquetage de l'application
```
yarn release
```
ou
```
npm run release
```

## Soutien
Si le cœur vous en dit, vous pouvez soutenir le projet sur [Ko-fi](https://ko-fi.com/S6S410PB8). Ça sera grandement apprécié. Le site est entièrement gratuit et ne souffre d'aucune publicité. Aucun revenu n'est donc généré par son biais.

## Licence
Le code source applicatif (hors contenus donc) est sous [licence GPLv3](https://github.com/em-squared/heros-et-dragons-drs/blob/master/LICENSE). Vous êtes donc libres de le copier, le modifier et le redistribuer à condition d'en conserver la licence d'origine.
