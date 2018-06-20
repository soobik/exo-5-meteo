# exo-5-meteo
Utilisation d'une API météo.

# Objectifs : 

Dans une page afficher les températures pour la journée actuelle pour les endroits suivants :  Ile de la Réunion, Paris, Marseille, Moscou.

Utiliser l 'API : www.openweathermap.org

/!\ Obligatoire : nodeJS pour récupérer les informations et les transmetre à votre page.



# Exemple pour passer une reponse de requette via une route

```javascript
    var http    = require('http');
    var request  require('request');

    function getResultat(callback){
        //changer url par l'url de la ressource a recuperer.
        var url = "http://";
        
        //appel de la fonction request
        request(url, function(error, response, body) {
            if (!error && response.statusCode == 200) {
                result = JSON.stringify(JSON.parse(body));
                return callback(null, result);
            } else {
                return callback(error, null);
            }
        });
    }

    app.get('/appel', function(req, res) {
    
        getResultat(function(err, data){
            if(!err){
                    res.send(data);
            }
            else{
                  res.send(err);
            }

        });

    });
```
