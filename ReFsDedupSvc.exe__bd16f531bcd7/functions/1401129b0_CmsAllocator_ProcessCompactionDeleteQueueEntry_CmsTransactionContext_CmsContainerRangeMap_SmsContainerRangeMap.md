# CmsAllocator::ProcessCompactionDeleteQueueEntry(CmsTransactionContext *,CmsContainerRangeMap *,_SmsContainerRangeMapListHead *,_SmsQuickIndex *,SmsContainer *,_SmsContainerAllocationBitmap *,SmsCheckpointContext *)

- ea: `0x1401129b0`
- end: `0x140112ec1`
- name: `?ProcessCompactionDeleteQueueEntry@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@PEAVCmsContainerRangeMap@@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAUSmsContainer@@PEAU_SmsContainerAllocationBitmap@@PEAUSmsCheckpointContext@@@Z`
- size: `1297`
- prototype: `int(CmsAllocator *__hidden this, struct CmsTransactionContext *, struct CmsContainerRangeMap *, struct _SmsContainerRangeMapListHead *, struct _SmsQuickIndex *, struct SmsContainer *, struct _SmsContainerAllocationBitmap *, struct SmsCheckpointContext *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140113110`

## callees

- `0x140004870`
- `0x1400914f0`
- `0x1400c6ee0`
- `0x1400ccee0`
- `0x1400cd27c`
- `0x1400f4170`
- `0x14011223c`
- `0x1401129b0`
- `0x140115fdc`
- `0x1401168f8`
- `0x14012ff84`
- `0x140130c30`
- `0x140131050`
- `0x1401313f0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x140112cd9`
- `ntdll!RtlReleaseSRWLockShared` at `0x140112cd9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140112ce7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140112ce7`
- `ntdll!RtlAcquireSRWLockShared` at `0x140112c81`
- `ntdll!RtlAcquireSRWLockShared` at `0x140112c81`

## pseudocode

```c

```
