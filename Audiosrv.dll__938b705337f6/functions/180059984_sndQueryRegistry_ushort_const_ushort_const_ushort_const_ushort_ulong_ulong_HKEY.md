# sndQueryRegistry(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong &,HKEY__ *)

- ea: `0x180059984`
- end: `0x180059cc4`
- name: `?sndQueryRegistry@@YAHPEBG00PEAGKAEAKPEAUHKEY__@@@Z`
- size: `832`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180059730`

## callees

- `0x180059984`
- `0x180069528`
- `0x1800ae394`
- `0x1800b3ca8`
- `0x1800cf8c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180059bb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180059bb4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059a4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059af6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059bff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059a4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059af6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059bff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059cb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059cb1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180059c1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180059c1b`

## pseudocode

```c

```
