# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800631ac`
- end: `0x180063295`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180062fa8`

## callees

- `0x180009084`
- `0x1800631ac`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180063224`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180063224`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800631d5`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800631d5`

## pseudocode

```c

```
