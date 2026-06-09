# CmsVolumeContainer::SetContainerStationaryVolatile(CmsTransactionContext *,unsigned __int64,bool,_RANGE const *,_RANGE *)

- ea: `0x14000f940`
- end: `0x14000fca6`
- name: `?SetContainerStationaryVolatile@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_K_NPEBU_RANGE@@PEAU3@@Z`
- size: `870`
- prototype: `__int64 __usercall@<rax>(CmsVolumeContainer *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, unsigned __int64@<r8>, bool@<r9b>, const struct _RANGE *, struct _RANGE *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400173c0`
- `0x1400b3a9c`

## callees

- `0x14000f940`
- `0x1400103b0`
- `0x1400108f0`
- `0x140088db0`
- `0x1400a8b90`
- `0x14013be5c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401f88be`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401f88be`
- `ntoskrnl!ExAllocatePool2` at `0x1401f88fa`
- `ntoskrnl!ExAllocatePool2` at `0x1401f88fa`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14000fb00`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14000fb00`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14000fb35`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14000fb35`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000fb1e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000fb1e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000faba`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000faba`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000fa93`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000fa93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc88`

## pseudocode

```c

```
