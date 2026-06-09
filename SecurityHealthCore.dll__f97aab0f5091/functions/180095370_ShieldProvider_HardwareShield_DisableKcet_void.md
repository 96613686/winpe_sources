# ShieldProvider::HardwareShield::DisableKcet(void)

- ea: `0x180095370`
- end: `0x180095773`
- name: `?DisableKcet@HardwareShield@ShieldProvider@@UEAAJXZ`
- size: `1027`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this)`
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180095780`
- `0x180095790`
- `0x1800957a0`
- `0x1800957b0`
- `0x1800957c0`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180011730`
- `0x1800944bc`
- `0x1800947a0`
- `0x180095370`
- `0x1800adad8`
- `0x1800bcecc`
- `0x1800cf6f8`
- `0x1800db304`
- `0x1800db864`
- `0x1800dd4ec`
- `0x1800de1bc`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800954b6`
- `KERNEL32!GetLastError` at `0x1800954b6`
- `KERNEL32!FreeLibrary` at `0x1800954c4`
- `KERNEL32!FreeLibrary` at `0x180095519`
- `KERNEL32!FreeLibrary` at `0x1800954c4`
- `KERNEL32!FreeLibrary` at `0x180095519`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095742`

## string_xrefs

- `0x18009540a`: `VbsApi.dll`

## pseudocode

```c

```
