# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x180038d88`
- end: `0x180038de6`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `94`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180033fc8`

## callees

- `0x180018530`
- `0x180038d88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038da9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038da9`

## string_xrefs

- `0x180038dc9`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c

```
