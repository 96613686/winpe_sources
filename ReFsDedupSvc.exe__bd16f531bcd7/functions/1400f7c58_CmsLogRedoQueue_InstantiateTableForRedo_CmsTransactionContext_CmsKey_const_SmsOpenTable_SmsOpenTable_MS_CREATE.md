# CmsLogRedoQueue::InstantiateTableForRedo(CmsTransactionContext *,_CmsKey const &,SmsOpenTable *,SmsOpenTable *,_MS_CREATE_DISPOSITION,SmsOpenTable * *)

- ea: `0x1400f7c58`
- end: `0x1400f82c0`
- name: `?InstantiateTableForRedo@CmsLogRedoQueue@@AEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@PEAUSmsOpenTable@@2W4_MS_CREATE_DISPOSITION@@PEAPEAU4@@Z`
- size: `1640`
- prototype: `int __high(struct CmsTransactionContext *, const struct _CmsKey *, struct SmsOpenTable *, struct SmsOpenTable *, enum _MS_CREATE_DISPOSITION, struct SmsOpenTable **)`
- caller_count: `1`
- callee_count: `28`
- tags: `loader_planting`

## callers

- `0x1400f91a8`

## callees

- `0x140004870`
- `0x1400057e0`
- `0x14007dfb0`
- `0x140082fe4`
- `0x140083074`
- `0x140083cc4`
- `0x14008425c`
- `0x140084670`
- `0x140084efc`
- `0x1400a2a8c`
- `0x1400a76d0`
- `0x1400a9b80`
- `0x1400b0860`
- `0x1400e8344`
- `0x1400ed778`
- `0x1400f4a40`
- `0x1400f7560`
- `0x1400f76b8`
- `0x1400f7c58`
- `0x1400fd2b8`
- `0x1400fe464`
- `0x1400ff9d4`
- `0x140100b0c`
- `0x140101318`
- `0x1401025b4`
- `0x140102654`
- `0x140103ed4`
- `0x1401b9010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400f81d9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400f81d9`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f8238`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f8238`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f8246`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f8246`

## pseudocode

```c

```
