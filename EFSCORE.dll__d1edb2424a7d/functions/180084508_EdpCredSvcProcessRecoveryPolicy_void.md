# EdpCredSvcProcessRecoveryPolicy(void)

- ea: `0x180084508`
- end: `0x180084938`
- name: `?EdpCredSvcProcessRecoveryPolicy@@YAXXZ`
- size: `1072`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041c20`

## callees

- `0x180063730`
- `0x1800637e8`
- `0x180082d60`
- `0x180084508`
- `0x180084a60`
- `0x1800853a4`
- `0x180085614`
- `0x180085ba0`
- `0x1800912c4`
- `0x180095334`
- `0x180096348`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800848c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800848c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800848d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800848d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008480b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008480b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800846c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800848a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800846c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800848a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800846da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800848b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800846da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800848b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800846b5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084898`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800846b5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180084898`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800847dd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800847dd`
- `ntdll!RtlIsMultiSessionSku` at `0x18008455e`
- `ntdll!RtlIsMultiSessionSku` at `0x18008455e`

## pseudocode

```c

```
