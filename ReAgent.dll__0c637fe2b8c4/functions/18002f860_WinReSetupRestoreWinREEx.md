# WinReSetupRestoreWinREEx

- ea: `0x18002f860`
- end: `0x18002f977`
- name: `WinReSetupRestoreWinREEx`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x1800103f4`
- `0x18002cab4`
- `0x18002f860`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002f95b`
- `KERNEL32!GetLastError` at `0x18002f95b`
- `KERNEL32!SetLastError` at `0x18002f8c2`
- `KERNEL32!SetLastError` at `0x18002f8c2`
- `KERNEL32!GetFileAttributesW` at `0x18002f8cd`
- `KERNEL32!GetFileAttributesW` at `0x18002f8cd`

## string_xrefs

- `0x18002f899`: `backup directory: %s`
- `0x18002f8b0`: `BackupDirectory is NULL`
- `0x18002f8d8`: `BackupDirectory does not exist`

## pseudocode

```c

```
