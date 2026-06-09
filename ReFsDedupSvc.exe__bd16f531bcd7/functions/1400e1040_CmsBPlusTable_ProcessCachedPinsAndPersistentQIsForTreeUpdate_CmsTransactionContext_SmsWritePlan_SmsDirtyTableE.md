# CmsBPlusTable::ProcessCachedPinsAndPersistentQIsForTreeUpdate(CmsTransactionContext *,SmsWritePlan *,SmsDirtyTableEntry *)

- ea: `0x1400e1040`
- end: `0x1400e11f2`
- name: `?ProcessCachedPinsAndPersistentQIsForTreeUpdate@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsWritePlan@@PEAUSmsDirtyTableEntry@@@Z`
- size: `434`
- prototype: `void __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct SmsWritePlan *, struct SmsDirtyTableEntry *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400de68c`

## callees

- `0x1400adfcc`
- `0x1400b06f4`
- `0x1400b1764`
- `0x1400b81a8`
- `0x1400da964`
- `0x1400e1040`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e10b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e10b8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e10e7`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e1195`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e10e7`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e1195`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e10f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e11a3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e10f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e11a3`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400e1158`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400e1158`

## pseudocode

```c

```
