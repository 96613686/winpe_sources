# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)

- ea: `0x1800195f8`
- end: `0x180019659`
- name: `?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z`
- size: `97`
- prototype: `static int(HKEY, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180017034`

## callees

- `0x1800195f8`
- `0x1800232a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001961c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001961c`

## string_xrefs

- `0x18001963c`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c

```
