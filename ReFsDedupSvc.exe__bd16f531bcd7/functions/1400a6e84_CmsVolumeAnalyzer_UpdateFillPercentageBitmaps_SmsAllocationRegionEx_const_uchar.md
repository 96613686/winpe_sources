# CmsVolumeAnalyzer::UpdateFillPercentageBitmaps(SmsAllocationRegionEx const &,uchar)

- ea: `0x1400a6e84`
- end: `0x1400a6f8c`
- name: `?UpdateFillPercentageBitmaps@CmsVolumeAnalyzer@@QEAAXAEBUSmsAllocationRegionEx@@E@Z`
- size: `264`
- prototype: `void __fastcall(CmsVolumeAnalyzer *__hidden this, const struct SmsAllocationRegionEx *, unsigned __int8)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1400a407c`
- `0x1400cd064`
- `0x140111a40`
- `0x140114a3c`

## callees

- `0x140091594`
- `0x1400a6e84`
- `0x1400a6f94`
- `0x1400a7094`

## import_xrefs

- `ntdll!RtlAreBitsClear` at `0x1400a6f05`
- `ntdll!RtlAreBitsClear` at `0x1400a6f05`
- `ntdll!RtlAreBitsSet` at `0x1400a6f21`
- `ntdll!RtlAreBitsSet` at `0x1400a6f21`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400a6ed4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400a6ed4`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400a6f7e`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400a6f7e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400a6f4f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400a6f4f`

## pseudocode

```c

```
