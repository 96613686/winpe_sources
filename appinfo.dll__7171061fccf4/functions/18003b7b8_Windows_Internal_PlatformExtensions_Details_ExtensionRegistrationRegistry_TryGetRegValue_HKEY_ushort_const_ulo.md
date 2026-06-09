# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x18003b7b8`
- end: `0x18003b812`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `90`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, DWORD, void *pvData, unsigned int *pcbData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180037060`

## callees

- `0x180018dbc`
- `0x18003b7b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b7dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b7dc`

## string_xrefs

- `0x18003b7f6`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c

```
