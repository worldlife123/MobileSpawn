# MobileSpawn
This is a Squad mod that enables mobile spawn technique that allows players to spawn close to some vehicles, like in Post Scriptum. This technique is designed to simulate motorized and mechanized squad battle tactics. 

## Description

The vanilla Squad gameplay tend to divide vehicle and infantry. Vehicles and infantries are usually played in different squads, and the communication between them usually relies on the squad leaders, which are inefficient. 

This mod tries to tie vehicle and infantry together by giving vehicles a spawning technique, letting infantry to spawn on mobile vehicles. This technique make the squad battle experience more dynamic and improve vehicle-infantry cooperation gameplay.

Note that supply truck are temporily removed on limited spawn gamemodes, forcing infantry to stick with vehicles. In later versions we may add them back by better combining mobile spawn vehicle and supply line gameplay.

## Technical Information

### Core Classes

- MobileSpawnComponentV2: Mobile spawn technique is implemented with the MobileSpawnComponentV2 object, which is a SceneComponent that can be added to a vehicle. All vehicles that have this component can create a mobile spawn point (BP_MobileTeamSpawn) at the component position when the vehicle is parked and engine off.
- MobileSpawnLimitedComponentV2: Limited Mobile spawn technique is implemented with the MobileSpawnLimitedComponentV2 object, which is also a SceneComponent. All vehicles that have this component can create a limited mobile spawn point (BP_MobileTeamSpawnLimited) at the component position when the vehicle is parked and engine off. The spawn limit will be restored when the vehicle enter the base area.

### Gamemodes
To support limited mobile spawn, custom gamemode is created by altering default PlayerController and HUD to customized ones.

- BP_PlayerController_MSL
- BP_HUD_MSL


### Maps
Currently we've only created a test version on Narva map. 

Maps with "_ms" suffix is using vehicles with team-wide unlimited mobile spawn. "_msl" use vehicles with squad-member-only limited mobile spawn.

Mapnames:
- Narva_AAS_v1_ms
- Narva_AAS_v1_msl

## Usage
Use AdminChangeMap [mapname] to play with Mobile Spawn Vehicles.
