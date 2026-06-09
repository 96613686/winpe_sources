# sndQueryRegistry(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong &,HKEY__ *)

- ea: `0x1800594f4`
- end: `0x180059834`
- name: `?sndQueryRegistry@@YAHPEBG00PEAGKAEAKPEAUHKEY__@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, HKEY hkey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800592a0`

## callees

- `0x1800594f4`
- `0x180069098`
- `0x1800ac694`
- `0x1800b1fb8`
- `0x1800cd8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180059724`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180059724`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800595bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059666`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005976f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800595bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059666`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005976f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059821`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005978b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005978b`

## pseudocode

```c

```
