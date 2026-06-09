# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x180042ae0`
- end: `0x180042b3a`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `90`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180040228`

## callees

- `0x18002b748`
- `0x180042ae0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042b04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042b04`

## string_xrefs

- `0x180042b1e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c

```
