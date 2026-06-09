# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::IsTargetedChildProcessCreate(_EVENT_RECORD const &)

- ea: `0x180018214`
- end: `0x180018340`
- name: `?IsTargetedChildProcessCreate@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@IEAA_NAEBU_EVENT_RECORD@@@Z`
- size: `300`
- prototype: `bool(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter *__hidden this, const struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f2f0`

## callees

- `0x180018214`
- `0x18003d864`
- `0x180041fac`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180018249`
- `VCRUNTIME140!memcmp` at `0x180018249`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001830c`
- `KERNEL32!ReleaseSRWLockShared` at `0x180018319`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001830c`
- `KERNEL32!ReleaseSRWLockShared` at `0x180018319`
- `KERNEL32!AcquireSRWLockShared` at `0x1800182a8`
- `KERNEL32!AcquireSRWLockShared` at `0x1800182a8`

## pseudocode

```c

```
