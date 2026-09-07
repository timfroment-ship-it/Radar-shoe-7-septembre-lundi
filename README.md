# Brocante Radar V12

V12 corrige le principal défaut de V11 : le seuil était appliqué à une classification contenant trop de classes. Une vraie Merrell pouvait être première sans dépasser 38 %.

## Nouveau fonctionnement

Chaque zone est classifiée deux fois avec MobileCLIP :

1. **Outdoor ou non** : randonnée/trail vs sneaker casual vs vêtements/sac/objets.
2. **Marque** : Salomon, Merrell, Hoka, La Sportiva, Adidas Terrex, Scarpa ou autre marque outdoor.

Les scores de marque sont donc relatifs à un petit groupe et les seuils par défaut sont beaucoup plus bas : marque 0,20 et écart 0,02.

## Test conseillé avec ta Merrell

1. Mets la Merrell au centre de l'écran.
2. Laisse `Confirmation = 1` pour les essais.
3. Appuie sur **Tester le centre**.
4. Active **Debug ON**.
5. Lis les scores affichés.

Si `MERRELL` apparaît en premier mais sans alerte, baisse encore `Score marque relatif` vers 0,16–0,18 et `Écart` vers 0,00–0,01.

Si `MERRELL` n'apparaît jamais dans les 4 premiers résultats même avec la chaussure bien cadrée, le problème n'est plus le seuil : MobileCLIP ne reconnaît pas assez bien cette paire. Dans ce cas, il faudra passer à un modèle fashion spécialisé ou à une bibliothèque de photos de référence.

## GitHub Pages

Comme V11, un seul fichier est nécessaire : remplace simplement `index.html` par celui de V12. Le fichier désenregistre les anciens service workers et vide les caches web au chargement.
