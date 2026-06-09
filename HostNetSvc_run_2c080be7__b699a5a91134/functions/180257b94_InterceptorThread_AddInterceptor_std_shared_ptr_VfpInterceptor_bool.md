# InterceptorThread::AddInterceptor(std::shared_ptr<VfpInterceptor>,bool)

- ea: `0x180257b94`
- end: `0x180257d50`
- name: `?AddInterceptor@InterceptorThread@@QEAAPEAXV?$shared_ptr@VVfpInterceptor@@@std@@_N@Z`
- size: `444`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18025031c`

## callees

- `0x18005f59c`
- `0x180061240`
- `0x18007e864`
- `0x1800860d0`
- `0x18009a7c0`
- `0x180257b94`
- `0x1802b7010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180257be4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180257be4`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180257c8e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180257c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180257ca5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180257ca5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180257bb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180257bb2`

## string_xrefs

- `0x180257d0e`: `onecore\vm\dv\net\hns\service\common\vfp\src\interceptorthread.cpp`
- `0x180257d3e`: `onecore\vm\dv\net\hns\service\common\vfp\src\interceptorthread.cpp`
- `0x180257d07`: `Unable to create VFP interceptor thread for switch`

## pseudocode

```c

```
