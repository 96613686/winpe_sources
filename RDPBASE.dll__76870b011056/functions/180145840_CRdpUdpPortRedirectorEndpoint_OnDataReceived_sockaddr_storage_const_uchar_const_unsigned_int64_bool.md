# CRdpUdpPortRedirectorEndpoint::OnDataReceived(sockaddr_storage const *,uchar const *,unsigned __int64,bool)

- ea: `0x180145840`
- end: `0x180145b1f`
- name: `?OnDataReceived@CRdpUdpPortRedirectorEndpoint@@UEAAXPEBUsockaddr_storage@@PEBE_K_N@Z`
- size: `735`
- prototype: `void __fastcall(CRdpUdpPortRedirectorEndpoint *this, const struct sockaddr_storage *, const unsigned __int8 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180004a94`
- `0x180016ad0`
- `0x1800506ac`
- `0x180125aa0`
- `0x180125db0`
- `0x1801450a8`
- `0x180145840`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180145af4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180145af4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801458d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801458d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801458e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145997`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801458e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145997`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145ad6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x180145956`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x180145956`

## string_xrefs

- `0x180145905`: `UDP port redirector read queue is full, need to block further receives.`

## pseudocode

```c

```
