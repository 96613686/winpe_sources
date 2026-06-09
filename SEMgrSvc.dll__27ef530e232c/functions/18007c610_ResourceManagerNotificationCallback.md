# ResourceManagerNotificationCallback

- ea: `0x18007c610`
- end: `0x18007c76e`
- name: `ResourceManagerNotificationCallback`
- size: `350`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800049a0`
- `0x18007c610`
- `0x18008b778`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c748`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c748`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c647`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c647`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c73e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c73e`
- `RMCLIENT!RmReleaseResources` at `0x18007c6a6`
- `RMCLIENT!RmReleaseResources` at `0x18007c6a6`
- `RMCLIENT!RmGetNotification` at `0x18007c686`
- `RMCLIENT!RmGetNotification` at `0x18007c686`

## pseudocode

```c

```
