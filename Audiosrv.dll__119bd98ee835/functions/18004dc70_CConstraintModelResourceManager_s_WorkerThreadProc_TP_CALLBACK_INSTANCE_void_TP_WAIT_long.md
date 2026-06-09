# CConstraintModelResourceManager::s_WorkerThreadProc(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18004dc70`
- end: `0x18004dce8`
- name: `?s_WorkerThreadProc@CConstraintModelResourceManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `120`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18004dc70`
- `0x18004dcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dcad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dcad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dce1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004dcc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004dcc9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004dc89`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004dc89`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004dc9d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004dc9d`

## pseudocode

```c

```
