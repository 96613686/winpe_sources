# CmsBPlusTable::RebindTreesForFailedTu(CmsTransactionContext *,SmsWritePlan *)

- ea: `0x1400e11f8`
- end: `0x1400e135f`
- name: `?RebindTreesForFailedTu@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAUSmsWritePlan@@@Z`
- size: `359`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400e2070`

## callees

- `0x14007e86c`
- `0x1400b1a10`
- `0x1400e11f8`
- `0x1400f8bd0`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x1400e129d`
- `ntdll!RtlAcquireResourceShared` at `0x1400e129d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e12bb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e12bb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e1304`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e1304`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e1312`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e1312`
- `ntdll!RtlReleaseResource` at `0x1400e1321`
- `ntdll!RtlReleaseResource` at `0x1400e1321`

## pseudocode

```c

```
