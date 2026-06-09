# LockscreenBackupRestoreHandler::IsChangingLockImageRestricted(void)

- ea: `0x1800bde54`
- end: `0x1800be003`
- name: `?IsChangingLockImageRestricted@LockscreenBackupRestoreHandler@@AEAA_NXZ`
- size: `431`
- prototype: `bool __fastcall(LockscreenBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800be530`

## callees

- `0x18000c6e0`
- `0x18001003c`
- `0x18001031c`
- `0x1800bbea4`
- `0x1800bde54`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyString` at `0x1800bdfac`
- `policymanager!PolicyManager_GetPolicyString` at `0x1800bdfac`
- `policymanager!PolicyManager_FreeStringValue` at `0x1800bdf84`
- `policymanager!PolicyManager_FreeStringValue` at `0x1800bdf84`
- `ADVAPI32!RegGetValueW` at `0x1800bdee8`
- `ADVAPI32!RegGetValueW` at `0x1800bdee8`
- `SHCORE!SHGetValueW` at `0x1800bdf40`
- `SHCORE!SHGetValueW` at `0x1800bdf40`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800bde86`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800bde9d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800bde86`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800bde9d`

## string_xrefs

- `0x1800bdf18`: `LockScreenImagePath`

## pseudocode

```c

```
