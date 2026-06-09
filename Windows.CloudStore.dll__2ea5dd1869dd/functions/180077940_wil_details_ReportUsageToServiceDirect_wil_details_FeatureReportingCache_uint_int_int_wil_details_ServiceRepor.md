# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180077940`
- end: `0x180077d1c`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `988`
- prototype: `int __high(struct wil_details_FeatureReportingCache *, unsigned int, int, int, enum wil_details_ServiceReportingKind, unsigned int, unsigned __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1801a78ac`

## callees

- `0x180044ad4`
- `0x1800467d0`
- `0x180074d64`
- `0x1800778b4`
- `0x1800778f8`
- `0x180077940`
- `0x1800b3e94`
- `0x180127230`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolTimer` at `0x180077b2c`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolTimer` at `0x180077b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077b43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077b43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077b55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077c92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077b55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077c92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180077aa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180077ba1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180077aa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180077ba1`

## pseudocode

```c

```
