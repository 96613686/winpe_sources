# FveBackupMonitor::GetOsvRecoveryPasswordBackupTypeMaskForUser(CNgscbToken const *,_GUID const *,ulong *)

- ea: `0x180070958`
- end: `0x180070c42`
- name: `?GetOsvRecoveryPasswordBackupTypeMaskForUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEBU_GUID@@PEAK@Z`
- size: `746`
- prototype: `__int64 __fastcall(const struct CNgscbToken *, const struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180033618`
- `0x18003b560`

## callees

- `0x180009f60`
- `0x18001b7f0`
- `0x180021d18`
- `0x180026190`
- `0x180034070`
- `0x180034d28`
- `0x180070674`
- `0x180070958`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180070c02`
- `ntdll!RtlFreeUnicodeString` at `0x180070c02`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070ba6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070ba6`

## pseudocode

```c

```
