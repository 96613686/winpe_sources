# InvCacheCloseHandle

- ea: `0x180028990`
- end: `0x1800289e6`
- name: `InvCacheCloseHandle`
- size: `86`
- prototype: `__int64 __fastcall(HKEY *P)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010440`
- `0x180010498`
- `0x1800116e0`
- `0x180012dd0`
- `0x180014990`
- `0x180016d90`
- `0x1800173b0`
- `0x180028aa0`

## callees

- `0x180028990`
- `0x18003a1c8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800289d8`
- `ntdll!RtlFreeHeap` at `0x1800289d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289b5`

## pseudocode

```c

```
