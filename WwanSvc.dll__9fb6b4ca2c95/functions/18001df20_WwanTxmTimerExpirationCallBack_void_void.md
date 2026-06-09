# WwanTxmTimerExpirationCallBack(void *,void *)

- ea: `0x18001df20`
- end: `0x18001e2c4`
- name: `?WwanTxmTimerExpirationCallBack@@YAXPEAX0@Z`
- size: `932`
- prototype: `void __fastcall(struct _GUID *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012300`
- `0x1800131dc`
- `0x180014f1c`
- `0x180015d6c`
- `0x18001d5e8`
- `0x18001dde4`
- `0x18001df20`
- `0x18001e358`
- `0x18001e5b0`
- `0x18001e834`
- `0x18005b980`
- `0x1800862e0`
- `0x1800b6adc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dfcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e1ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dfcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e1ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e263`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e28d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001df8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001df8c`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001e17c`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001e285`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001e17c`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001e285`

## string_xrefs

- `0x18001df53`: `ERROR: service not running or shutting down.`
- `0x18001e0d1`: `Transaction is already marked as completed`
- `0x18001e067`: `TX timed out: code %d setQueryType %d txHandle 0x%p. WwanCreateAsyncRspEvent() returns null. `

## pseudocode

```c

```
