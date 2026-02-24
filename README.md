NPC-DealerLib


Description
-----------
Ce script permet de créer facilement des interactions NPC
avec une interface NUI dans un serveur FiveM. Il affiche un
nom, une description, ainsi qu’une liste de boutons
interactifs déclenchant des fonctions côté client.

Le système est léger, modulaire et réutilisable dans
n’importe quelle ressource.

-----------------------------------------------------------

Installation
------------
1. Place le script dans un dossier de ressource FiveM.
2. Ajoute la ressource dans ton server.cfg :
   ensure so_so_npcDealer

-----------------------------------------------------------

Fonction Exportée : CreateNPC
-----------------------------
Cette fonction permet d’ouvrir une interface NPC personnalisée
depuis n’importe quel script.

Syntaxe :
    exports['so_npcDealer']:CreateNPC(name, description, buttons)

Paramètres :
- name (string) : Nom du NPC.
- description (string) : Texte affiché dans l’UI.
- buttons (table) : Liste de boutons au format :
      { "Label", function() ... end }

Exemple :
    exports['so_npcDealer']:CreateNPC("Bob", "Salut !", {
        {"Dire bonjour", function() print("Bonjour !") end},
        {"Quitter", function() print("Au revoir !") end}
    })

-----------------------------------------------------------

Exemple d’utilisation (commande LibTest)
----------------------------------------

RegisterCommand('LibTest', function()
    so:CreateNPC(
        "Juan",
        "Eh frère… j’te cherche depuis tout à l’heure. J’ai besoin de ton truc là...",
        {
            {"Vendre", function() print("vendre") end},
            {"Négocier le prix", function() print("négocier") end},
            {"Refuser", function() print("vente refuser") end}
        }
    )
end)

