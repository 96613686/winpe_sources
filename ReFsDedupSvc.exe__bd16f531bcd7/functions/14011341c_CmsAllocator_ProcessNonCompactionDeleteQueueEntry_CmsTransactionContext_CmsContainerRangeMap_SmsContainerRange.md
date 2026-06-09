# CmsAllocator::ProcessNonCompactionDeleteQueueEntry(CmsTransactionContext *,CmsContainerRangeMap *,_SmsContainerRangeMapListHead *,SmsContainer *,_SmsQuickIndex *,SmsCheckpointContext *)

- ea: `0x14011341c`
- end: `0x1401137b4`
- name: `?ProcessNonCompactionDeleteQueueEntry@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAVCmsContainerRangeMap@@PEAU_SmsContainerRangeMapListHead@@PEAUSmsContainer@@PEAU_SmsQuickIndex@@PEAUSmsCheckpointContext@@@Z`
- size: `920`
- prototype: `__int64 __usercall@<rax>(CmsAllocator *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct CmsContainerRangeMap *@<r8>, struct _SmsContainerRangeMapListHead *@<r9>, struct SmsContainer *, struct _SmsQuickIndex *, struct SmsCheckpointContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140113110`

## callees

- `0x1400633bc`
- `0x14007d9d8`
- `0x14008d844`
- `0x14009c350`
- `0x14011223c`
- `0x14011341c`
- `0x140115fdc`
- `0x1401168f8`
- `0x14012ff84`
- `0x1401313f0`
- `0x1401318e0`
- `0x140137da4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x140113782`
- `ntdll!RtlReleaseSRWLockShared` at `0x140113782`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140113790`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140113790`
- `ntdll!RtlAcquireSRWLockShared` at `0x14011374f`
- `ntdll!RtlAcquireSRWLockShared` at `0x14011374f`

## pseudocode

```c

```
