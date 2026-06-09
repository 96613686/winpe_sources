# SystemSettings::StorageSenseHandlers::CSettingsEnvironmentSingleton::IsDeviceInterfaceAvailable(_GUID const *,bool *)

- ea: `0x1800cb8b8`
- end: `0x1800cb99e`
- name: `?IsDeviceInterfaceAvailable@CSettingsEnvironmentSingleton@StorageSenseHandlers@SystemSettings@@AEAAJPEBU_GUID@@PEA_N@Z`
- size: `230`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CSettingsEnvironmentSingleton *__hidden this, const struct _GUID *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800cbb90`

## callees

- `0x180006e50`
- `0x1800b4f50`
- `0x1800c8d24`
- `0x1800cb8b8`

## import_xrefs

- `DEVOBJ!DevObjGetClassDevs` at `0x1800cb938`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800cb938`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800cb900`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800cb900`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800cb959`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800cb959`

## pseudocode

```c

```
