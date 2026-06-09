# CThreadLocalObject::GetData(CNoTrackObject * (*)(void))

- ea: `0x180012590`
- end: `0x1800126d9`
- name: `?GetData@CThreadLocalObject@@QEAAPEAVCNoTrackObject@@P6APEAV2@XZ@Z`
- size: `329`
- prototype: `struct CNoTrackObject *__fastcall(CThreadLocalObject *__hidden this, struct CNoTrackObject *(*)(void))`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800b5e08`

## callees

- `0x180012590`
- `0x1800136f0`
- `0x18001f110`
- `0x18002d800`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180012652`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180012652`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800125e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800125e2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001266a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001266a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012609`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012687`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012609`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012687`

## pseudocode

```c

```
