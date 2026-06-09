# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x180038a48`
- end: `0x180038aa6`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `94`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180033d08`

## callees

- `0x180018530`
- `0x180038a48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038a69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038a69`

## string_xrefs

- `0x180038a89`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c

```
