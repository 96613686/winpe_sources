# CmsRestarter::StoreOpenTable(CmsTransactionContext *,_CmsKey const &,SmsOpenTable &&,SmsOpenTable *)

- ea: `0x1400fe464`
- end: `0x1400fe599`
- name: `?StoreOpenTable@CmsRestarter@@AEAAPEAUSmsOpenTable@@PEAVCmsTransactionContext@@AEBU_CmsKey@@$$QEAU2@PEAU2@@Z`
- size: `309`
- prototype: `__int64 __fastcall(CmsRestarter *this, struct CmsTransactionContext *, struct _CmsKey *, SmsOpenTable *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400f7a48`
- `0x1400f7c58`

## callees

- `0x1400f43d4`
- `0x1400f4e9c`
- `0x1400f68fc`
- `0x1400f761c`
- `0x1400f7724`
- `0x1400fd2b8`
- `0x1400fe464`
- `0x1400ff1e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400fe4e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400fe4e1`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400fe556`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400fe556`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400fe564`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400fe564`

## pseudocode

```c

```
