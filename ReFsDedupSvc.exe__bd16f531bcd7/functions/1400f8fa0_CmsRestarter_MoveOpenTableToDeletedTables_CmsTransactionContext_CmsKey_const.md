# CmsRestarter::MoveOpenTableToDeletedTables(CmsTransactionContext *,_CmsKey const &)

- ea: `0x1400f8fa0`
- end: `0x1400f9113`
- name: `?MoveOpenTableToDeletedTables@CmsRestarter@@AEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CmsRestarter *__hidden this, struct CmsTransactionContext *, const struct _CmsKey *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400fa778`

## callees

- `0x1400f44c4`
- `0x1400f49e0`
- `0x1400f68fc`
- `0x1400f761c`
- `0x1400f8fa0`
- `0x1400fd2b8`
- `0x1400ff7f8`
- `0x1400ff9d4`
- `0x1400ffa58`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400f8fde`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400f8fde`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f90ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f90ce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f90dc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f90dc`

## pseudocode

```c

```
