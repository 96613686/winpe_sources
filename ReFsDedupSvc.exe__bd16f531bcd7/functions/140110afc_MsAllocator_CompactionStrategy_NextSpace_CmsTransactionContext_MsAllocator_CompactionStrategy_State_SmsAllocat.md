# MsAllocator::CompactionStrategy::NextSpace(CmsTransactionContext *,MsAllocator::CompactionStrategy::State *,SmsAllocationContext *,MsAllocator::CompactionStrategy::Context &)

- ea: `0x140110afc`
- end: `0x140110d57`
- name: `?NextSpace@CompactionStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@@Z`
- size: `603`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, struct MsAllocator::CompactionStrategy::State *, struct SmsAllocationContext *, struct MsAllocator::CompactionStrategy::Context *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14010a154`

## callees

- `0x14007da2c`
- `0x14010f118`
- `0x14010f204`
- `0x140110afc`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x140110d13`
- `ntdll!RtlReleaseSRWLockShared` at `0x140110d13`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140110d37`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140110d37`
- `ntdll!RtlAcquireSRWLockShared` at `0x140110b51`
- `ntdll!RtlAcquireSRWLockShared` at `0x140110b51`

## pseudocode

```c

```
