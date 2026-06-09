# CmsVolumeContainer::RemoveReservedContainer(CmsTransactionContext *,SmsAllocationRegionEx const &,uchar)

- ea: `0x1400c8d8c`
- end: `0x1400c8eae`
- name: `?RemoveReservedContainer@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@AEBUSmsAllocationRegionEx@@E@Z`
- size: `290`
- prototype: `void __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, const struct SmsAllocationRegionEx *, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400cd064`
- `0x140108cd4`

## callees

- `0x1400633bc`
- `0x1400914f0`
- `0x1400c8d8c`
- `0x1400cbf0c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1400c8e34`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400c8e34`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400c8e42`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400c8e42`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400c8dc6`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400c8dc6`

## pseudocode

```c

```
