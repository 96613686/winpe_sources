# CmsPinCache::TransferOneCachedPin(CmsTransactionContext *,CmsCachedPin *,CmsBPlusTable *,_LIST_ENTRY *)

- ea: `0x1400b9c20`
- end: `0x1400ba06d`
- name: `?TransferOneCachedPin@CmsPinCache@@QEAAEPEAVCmsTransactionContext@@PEAVCmsCachedPin@@PEAVCmsBPlusTable@@PEAU_LIST_ENTRY@@@Z`
- size: `1101`
- prototype: `unsigned __int8(CmsPinCache *__hidden this, struct CmsTransactionContext *, struct CmsCachedPin *, struct CmsBPlusTable *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1400ad99c`
- `0x1400ba074`

## callees

- `0x14008d2ac`
- `0x1400a2a8c`
- `0x1400b1140`
- `0x1400b135c`
- `0x1400b1764`
- `0x1400b575c`
- `0x1400b7ab8`
- `0x1400b7fc4`
- `0x1400b99b8`
- `0x1400b9c20`
- `0x1400baa38`

## import_xrefs

- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x1400b9ddf`
- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x1400b9ddf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400b9cec`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400b9cec`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b9d4d`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b9f26`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b9f5c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b9d4d`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b9f26`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b9f5c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b9d5b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b9f34`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b9f6a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b9d5b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b9f34`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b9f6a`

## pseudocode

```c

```
