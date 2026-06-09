# CmsBlockRefcount::LookupCacheEntry(CmsTransactionContext *,_RANGE const *,uchar,CmsRefcountCacheEntry * &)

- ea: `0x1400cfcf8`
- end: `0x1400cfec0`
- name: `?LookupCacheEntry@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EAEAPEAVCmsRefcountCacheEntry@@@Z`
- size: `456`
- prototype: `__int64 __usercall@<rax>(CmsBlockRefcount *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, unsigned __int8@<r9b>, struct CmsRefcountCacheEntry **)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x1400cf2bc`
- `0x1400cf6dc`
- `0x1400cfec8`

## callees

- `0x14007ec18`
- `0x14007ec4c`
- `0x1400838b4`
- `0x14008c930`
- `0x14008d430`
- `0x14008e220`
- `0x1400b1a10`
- `0x1400cfbf0`
- `0x1400cfcf8`
- `0x1400d03dc`
- `0x1400d0b44`
- `0x1400d1724`
- `0x1400d1f44`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400cfdc1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400cfdc1`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400cfe3a`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400cfe7f`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400cfe3a`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400cfe7f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400cfe48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400cfe8d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400cfe48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400cfe8d`

## pseudocode

```c

```
