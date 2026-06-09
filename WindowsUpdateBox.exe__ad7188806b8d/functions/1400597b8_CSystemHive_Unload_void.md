# CSystemHive::Unload(void)

- ea: `0x1400597b8`
- end: `0x14005996a`
- name: `?Unload@CSystemHive@@QEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(CSystemHive *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14005aa68`

## callees

- `0x140028980`
- `0x140055d10`
- `0x1400597b8`

## import_xrefs

- `ADVAPI32!RegUnLoadKeyW` at `0x1400597fa`
- `ADVAPI32!RegUnLoadKeyW` at `0x1400597fa`
- `KERNEL32!HeapFree` at `0x1400598c9`
- `KERNEL32!HeapFree` at `0x1400598f7`
- `KERNEL32!HeapFree` at `0x1400598c9`
- `KERNEL32!HeapFree` at `0x1400598f7`
- `KERNEL32!GetProcessHeap` at `0x1400598b5`
- `KERNEL32!GetProcessHeap` at `0x1400598e3`
- `KERNEL32!GetProcessHeap` at `0x1400598b5`
- `KERNEL32!GetProcessHeap` at `0x1400598e3`
- `KERNEL32!GetLastError` at `0x14005981d`
- `KERNEL32!GetLastError` at `0x14005981d`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005989b`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005989b`
- `WDSCORE!CurrentIP` at `0x14005982b`
- `WDSCORE!CurrentIP` at `0x14005982b`

## string_xrefs

- `0x14005993f`: `SeBackupPrivilege`
- `0x140059923`: `SeRestorePrivilege`

## pseudocode

```c

```
