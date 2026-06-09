# CmsVolumeAnalyzer::CompactContainers(CmsTransactionContext *,ulong,uchar *)

- ea: `0x1400a4ba8`
- end: `0x1400a4ebe`
- name: `?CompactContainers@CmsVolumeAnalyzer@@QEAAJPEAVCmsTransactionContext@@KPEAE@Z`
- size: `790`
- prototype: `__int64 __fastcall(CmsVolumeAnalyzer *__hidden this, struct CmsTransactionContext *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a42d8`

## callees

- `0x1400a3310`
- `0x1400a4ba8`
- `0x1400a5454`
- `0x1400a6078`
- `0x1400a7294`

## import_xrefs

- `ntdll!RtlQueryPerformanceCounter` at `0x1400a4c5d`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400a4dbf`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400a4c5d`
- `ntdll!RtlQueryPerformanceCounter` at `0x1400a4dbf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400a4bfb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400a4bfb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400a4c39`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400a4c39`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400a4c47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400a4c47`

## pseudocode

```c

```
