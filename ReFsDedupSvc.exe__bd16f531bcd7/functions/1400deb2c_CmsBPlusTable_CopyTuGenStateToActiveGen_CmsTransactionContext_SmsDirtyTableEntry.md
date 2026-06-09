# CmsBPlusTable::CopyTuGenStateToActiveGen(CmsTransactionContext *,SmsDirtyTableEntry *)

- ea: `0x1400deb2c`
- end: `0x1400dec95`
- name: `?CopyTuGenStateToActiveGen@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsDirtyTableEntry@@@Z`
- size: `361`
- prototype: `void __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct SmsDirtyTableEntry *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400dc9f0`

## callees

- `0x140004be0`
- `0x1400cd9d4`
- `0x1400cda38`
- `0x1400deb2c`
- `0x140106794`
- `0x1401b9010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400deb86`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400deb86`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400debf4`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400debf4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400dec02`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400dec02`

## pseudocode

```c

```
