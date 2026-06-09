# ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)

- ea: `0x180071910`
- end: `0x180071985`
- name: `?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z`
- size: `117`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010fb0`

## callees

- `0x180071910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007196a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007196a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007193f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007193f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071977`

## pseudocode

```c

```
