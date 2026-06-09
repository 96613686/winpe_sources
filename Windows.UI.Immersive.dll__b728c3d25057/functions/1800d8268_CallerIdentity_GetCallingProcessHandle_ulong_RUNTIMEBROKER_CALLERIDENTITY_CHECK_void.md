# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800d8268`
- end: `0x1800d8354`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `236`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a85a0`
- `0x1800d8130`
- `0x1800d81b4`
- `0x1800d8244`
- `0x1800d835c`

## callees

- `0x180013244`
- `0x18002d5e8`
- `0x180034db4`
- `0x1800d8268`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d82ec`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d82ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d82d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d82d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d82fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d82fd`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800d82a1`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800d82a1`

## pseudocode

```c

```
