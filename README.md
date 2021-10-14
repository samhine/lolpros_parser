[![PyPi](https://img.shields.io/pypi/v/lolpros-parser)](https://pypi.org/project/lolpros-parser/)
[![Downloads](https://pepy.tech/badge/lolpros-parser)](https://pepy.tech/project/lolpros-parser)

# lolpros_parser

Small library for pulling player data from https://lolpros.gg/ external API.

## Installation

Using `pip`:
```commandline
pip install lolpros-parser
```

## Usage

Full functionality can be found within the [method definition file](https://github.com/samhine/lolpros-parser/tree/main/lolpros_parser/parser.py).

```python
import lolpros_parser

# Grab list of summoner names for a player
player = "Chemera"
print(lolpros_parser.get_player_summoner_names(player))
# >> ["Chemera"]

# Grab list of summoner info for a player
print(lolpros_parser.get_player_summoner_info(player))
# >> [{'uuid': '86b3f764-5dbe-4230-a32c-d8f246636771', ...} ...]

# Grab ranking history for a particular summoner UUID
summoner_uuid = "86b3f764-5dbe-4230-a32c-d8f246636771"
print(lolpros_parser.get_summoner_rankings(summoner_uuid, months=3))
# >> [{
#   "score":2504,
#   "created_at":"2021-09-14T00:04:27+00:00",
#   "tier":"40_platinum",
#   "ranking":1,
#   "league_points":100,
#   "wins":3,
#   "losses":8,
#   "season":"season_11"
#   },
#   ...
# ]  

# Grab players and their role for a given team
print(lolpros_parser.get_players_by_team("Resolve"))
# >> [
#   {'role': 'support', 'name': 'fgg'}, 
#   {'role': 'jungle', 'name': 'sof'}, 
#   {'role': 'top', 'name': 'kaylem'},
#   ...
# ]
```

## Feature Request

Please feel free to raise an issue requesting a feature, or create a PR to implement one yourself.

