# pIsOfflineOSUpgrade(HKEY__ *,int &)

- ea: `0x18001a32c`
- end: `0x18001a52f`
- name: `?pIsOfflineOSUpgrade@@YAKPEAUHKEY__@@AEAH@Z`
- size: `515`
- prototype: `unsigned int __fastcall(HKEY hkey, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180019240`

## callees

- `0x180001f94`
- `0x180001fa0`
- `0x1800059fc`
- `0x18001a32c`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a47f`
- `msvcrt!_wcsicmp` at `0x18001a47f`
- `ADVAPI32!RegGetValueW` at `0x18001a408`
- `ADVAPI32!RegGetValueW` at `0x18001a44e`
- `ADVAPI32!RegGetValueW` at `0x18001a408`
- `ADVAPI32!RegGetValueW` at `0x18001a44e`

## string_xrefs

- `0x18001a4f7`: `failed to read size from %s [%s] in offline SOFTWARE HIVE: 0x%x`

## pseudocode

```c

```
