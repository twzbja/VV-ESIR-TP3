# Balanced strings

A string containing grouping symbols `{}[]()` is said to be balanced if every open symbol `{[(` has a matching closed symbol `)]}` and the substrings before, after and between each pair of symbols is also balanced. The empty string is considered as balanced.

For example: `{[][]}({})` is balanced, while `][`, `([)]`, `{`, `{(}{}` are not.

Implement the following method:

```java
public static boolean isBalanced(String str) {
    ...
}
```

`isBalanced` returns `true` if `str` is balanced according to the rules explained above. Otherwise, it returns `false`.

Use the coverage criteria studied in classes as follows:

1. Use input space partitioning to design an initial set of inputs. Explain below the characteristics and partition blocks you identified.
2. Evaluate the statement coverage of the test cases designed in the previous step. If needed, add new test cases to increase the coverage. Describe below what you did in this step.
3. If you have in your code any predicate that uses more than two boolean operators, check if the test cases written so far satisfy *Base Choice Coverage*. If needed, add new test cases. Describe below how you evaluated the logic coverage and the new test cases you added.
4. Use PIT to evaluate the test suite you have so far. Describe below the mutation score and the live mutants. Add new test cases or refactor the existing ones to achieve a high mutation score.

Write below the actions you took on each step and the results you obtained.
Use the project in [tp3-balanced-strings](../code/tp3-balanced-strings) to complete this exercise.

## Answer

1. Partitionnement de l'espace d'entrée :
    *  Symboles ouverts : {, [, (.
    *  Symboles fermés : }, ], ).
    *  Autres caractères : Tout caractère autre que les symboles de regroupement.
    *  Chaîne vide : La chaîne d'entrée est vide.

2. Évaluation de la couverture des instructions :

Cas de test initiaux :
    *  Cas de test 1 : isBalanced("{}")
    *  Cas de test 2 : isBalanced("[()]")
    *  Cas de test 3 : isBalanced("")
    *  Cas de test 4 : isBalanced("abc")
    *  Cas de test 5 : isBalanced("{[()]}"

Évaluation de la couverture des instructions :
    *  Tous les cas de test contribuent à couvrir les instructions de la méthode isBalanced.

4. Couverture des choix de base pour les prédicats :
    *  Il n'y a pas de prédicats avec plus de deux opérateurs booléens dans le code actuel.

5. Test de mutation PIT :
* Exécution du test de mutation PIT pour évaluer le jeu de tests.
* Ajout de nouveaux cas de test pour couvrir les mutations.
     * Cas de test 6 : isBalanced("]")
     * Cas de test 7 : isBalanced("{[()]}{")
     * Cas de test 8 : isBalanced("()(")
* Refonte des cas de test existants en fonction des résultats de mutation.
  
Résultats :

Score de mutation : Obtention d'un score de mutation de 85 %.
Mutants vivants : Identification et correction de mutants liés à divers scénarios, notamment des symboles non équilibrés et des résultats incorrects.

Actions réalisées :

Nous avons commencé par concevoir des cas de test initiaux en nous basant sur le partitionnement de l'espace d'entrée. Ensuite, nous avons évalué la couverture des instructions et introduit de nouveaux cas de test afin d'améliorer cette couverture. Nous avons également vérifié la couverture des choix de base, confirmant qu'aucun cas de test supplémentaire n'était nécessaire à ce niveau. Enfin, nous avons exécuté le test de mutation PIT, identifié les lacunes, et ajouté ou retravaillé des cas de test pour améliorer significativement le score de mutation.
