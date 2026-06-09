# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14006b0a4`
- end: `0x14006b1b3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14006ce70`

## callees

- `0x140069374`
- `0x140069428`
- `0x14006b0a4`
- `0x14006b1f4`
- `0x14006b228`
- `0x14006b260`
- `0x140085010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14006b102`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006b189`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006b102`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006b189`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006b150`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006b19f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006b150`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006b19f`

## pseudocode

```c

```
