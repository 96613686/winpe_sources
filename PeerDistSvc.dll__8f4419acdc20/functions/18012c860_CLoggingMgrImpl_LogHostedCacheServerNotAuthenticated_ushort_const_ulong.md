# CLoggingMgrImpl::LogHostedCacheServerNotAuthenticated(ushort const *,ulong)

- ea: `0x18012c860`
- end: `0x18012ca03`
- name: `?LogHostedCacheServerNotAuthenticated@CLoggingMgrImpl@@UEAAJPEBGK@Z`
- size: `419`
- prototype: `__int64 __fastcall(CLoggingMgrImpl *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x180126710`
- `0x18012b4d0`
- `0x18012c048`
- `0x18012c860`
- `0x180144882`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012c9ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012c9ea`
- `AUTHZ!AuthziInitializeAuditParams` at `0x18012c937`
- `AUTHZ!AuthziInitializeAuditParams` at `0x18012c937`

## string_xrefs

- `0x18012c8f5`: `Security`

## pseudocode

```c

```
