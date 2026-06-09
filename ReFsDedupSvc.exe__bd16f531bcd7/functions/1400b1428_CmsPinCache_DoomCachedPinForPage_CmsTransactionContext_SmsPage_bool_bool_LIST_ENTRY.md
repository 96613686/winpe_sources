# CmsPinCache::DoomCachedPinForPage(CmsTransactionContext *,SmsPage *,bool,bool,_LIST_ENTRY *)

- ea: `0x1400b1428`
- end: `0x1400b14e9`
- name: `?DoomCachedPinForPage@CmsPinCache@@QEAA_NPEAVCmsTransactionContext@@PEAUSmsPage@@_N2PEAU_LIST_ENTRY@@@Z`
- size: `193`
- prototype: `bool __usercall@<al>(CmsPinCache *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct SmsPage *@<r8>, bool@<r9b>, bool, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400adfcc`
- `0x1400ddb00`

## callees

- `0x1400b135c`
- `0x1400b1428`
- `0x1400b99b8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400b1454`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400b1454`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b14c0`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b14c0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b14ce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b14ce`

## pseudocode

```c

```
