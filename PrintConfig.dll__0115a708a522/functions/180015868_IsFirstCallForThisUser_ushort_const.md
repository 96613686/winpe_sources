# IsFirstCallForThisUser(ushort const *)

- ea: `0x180015868`
- end: `0x180015ad5`
- name: `?IsFirstCallForThisUser@@YA_NPEBG@Z`
- size: `621`
- prototype: `char __fastcall(LPCWSTR lpValue, struct RegistryHandleRAII *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180015fa4`
- `0x1800161a0`
- `0x1800177b0`

## callees

- `0x180004564`
- `0x18000f830`
- `0x180015868`
- `0x1800197b4`
- `0x180036a4c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800158a5`
- `ADVAPI32!RegCloseKey` at `0x180015921`
- `ADVAPI32!RegCloseKey` at `0x1800159b6`
- `ADVAPI32!RegCloseKey` at `0x1800159cf`
- `ADVAPI32!RegCloseKey` at `0x1800158a5`
- `ADVAPI32!RegCloseKey` at `0x180015921`
- `ADVAPI32!RegCloseKey` at `0x1800159b6`
- `ADVAPI32!RegCloseKey` at `0x1800159cf`
- `ADVAPI32!RegCreateKeyExW` at `0x1800158f5`
- `ADVAPI32!RegCreateKeyExW` at `0x1800158f5`
- `ADVAPI32!RegGetValueW` at `0x18001596c`
- `ADVAPI32!RegGetValueW` at `0x18001596c`

## string_xrefs

- `0x1800158ea`: `Printers\V4ConnectionCacheState`

## pseudocode

```c

```
