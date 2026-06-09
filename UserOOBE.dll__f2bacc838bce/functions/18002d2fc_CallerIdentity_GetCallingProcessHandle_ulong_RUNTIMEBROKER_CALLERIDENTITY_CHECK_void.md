# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18002d2fc`
- end: `0x18002d3b3`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned int, __int64, HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d2d4`
- `0x180044a90`

## callees

- `0x180007134`
- `0x18002d2fc`
- `0x18002d3bc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d367`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002d335`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002d335`

## pseudocode

```c

```
