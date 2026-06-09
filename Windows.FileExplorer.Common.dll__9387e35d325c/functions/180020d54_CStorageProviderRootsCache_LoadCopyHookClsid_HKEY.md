# CStorageProviderRootsCache::LoadCopyHookClsid(HKEY__ *)

- ea: `0x180020d54`
- end: `0x180020e23`
- name: `?LoadCopyHookClsid@CStorageProviderRootsCache@@AEAAJPEAUHKEY__@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016fe8`

## callees

- `0x1800077c8`
- `0x180020d54`
- `0x180037780`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x180020dd9`
- `SHCORE!__imp_GUIDFromStringW` at `0x180020dd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020dac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020dac`

## string_xrefs

- `0x180020e06`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180020d87`: `CopyHook`

## pseudocode

```c

```
