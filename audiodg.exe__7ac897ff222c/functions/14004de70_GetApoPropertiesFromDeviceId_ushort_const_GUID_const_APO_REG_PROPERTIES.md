# GetApoPropertiesFromDeviceId(ushort * const,_GUID const &,APO_REG_PROPERTIES *)

- ea: `0x14004de70`
- end: `0x14004df58`
- name: `?GetApoPropertiesFromDeviceId@@YAJQEAGAEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID, const struct _GUID *, struct APO_REG_PROPERTIES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400476e8`

## callees

- `0x140018d0c`
- `0x14003c290`
- `0x14004de70`
- `0x1400690a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004df40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004df40`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x14004def5`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x14004def5`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14004de97`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14004de97`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14004dea6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14004deff`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14004dea6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14004deff`

## pseudocode

```c

```
