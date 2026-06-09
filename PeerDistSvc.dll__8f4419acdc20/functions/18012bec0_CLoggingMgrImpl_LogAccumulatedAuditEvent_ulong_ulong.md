# CLoggingMgrImpl::LogAccumulatedAuditEvent(ulong,ulong)

- ea: `0x18012bec0`
- end: `0x18012c040`
- name: `?LogAccumulatedAuditEvent@CLoggingMgrImpl@@AEAAJKK@Z`
- size: `384`
- prototype: `__int64 __fastcall(CLoggingMgrImpl *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012ba20`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x180126710`
- `0x18012bec0`
- `0x18012c048`
- `0x180144882`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012c027`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012c027`
- `AUTHZ!AuthziInitializeAuditParams` at `0x18012bf76`
- `AUTHZ!AuthziInitializeAuditParams` at `0x18012bf76`

## string_xrefs

- `0x18012bf36`: `Security`

## pseudocode

```c

```
