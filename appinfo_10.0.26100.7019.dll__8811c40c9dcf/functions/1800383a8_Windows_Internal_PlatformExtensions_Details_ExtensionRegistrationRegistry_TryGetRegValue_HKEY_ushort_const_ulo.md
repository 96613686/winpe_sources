# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x1800383a8`
- end: `0x180038406`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `94`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180033c58`

## callees

- `0x180018280`
- `0x1800383a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800383c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800383c9`

## string_xrefs

- `0x1800383e9`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c

```
