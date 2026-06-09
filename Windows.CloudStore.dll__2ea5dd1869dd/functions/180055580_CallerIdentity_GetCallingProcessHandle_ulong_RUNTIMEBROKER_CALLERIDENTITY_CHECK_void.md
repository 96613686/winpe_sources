# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180055580`
- end: `0x1800556cf`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `335`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054d4c`
- `0x180055240`
- `0x1800f93b0`
- `0x1801017cc`
- `0x180109c10`
- `0x18010f8f0`

## callees

- `0x18000ff48`
- `0x180055580`
- `0x1800558b0`
- `0x1800c8458`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055694`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800555cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800555cc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005567f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005567f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800555b9`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800555b9`

## pseudocode

```c

```
