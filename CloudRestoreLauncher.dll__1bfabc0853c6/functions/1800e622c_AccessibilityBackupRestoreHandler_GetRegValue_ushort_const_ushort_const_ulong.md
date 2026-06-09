# AccessibilityBackupRestoreHandler::GetRegValue(ushort const *,ushort const *,ulong *)

- ea: `0x1800e622c`
- end: `0x1800e62c5`
- name: `?GetRegValue@AccessibilityBackupRestoreHandler@@AEAAJPEBG0PEAK@Z`
- size: `153`
- prototype: `__int64 __fastcall(AccessibilityBackupRestoreHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800e69e0`
- `0x1800e6b70`
- `0x1800e6e30`
- `0x1800e6f84`
- `0x1800e7074`
- `0x1800e712c`

## callees

- `0x18000c6e0`
- `0x1800e622c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800e62a0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800e62a0`
- `ADVAPI32!RegGetValueW` at `0x1800e6277`
- `ADVAPI32!RegGetValueW` at `0x1800e6277`

## pseudocode

```c

```
