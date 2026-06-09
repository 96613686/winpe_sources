# WindowsGraphicsDeviceManager::WaitForInitializationThreadCompletion(void)

- ea: `0x180491a58`
- end: `0x180491bef`
- name: `?WaitForInitializationThreadCompletion@WindowsGraphicsDeviceManager@@AEAAJXZ`
- size: `407`
- prototype: `HRESULT __fastcall(WindowsGraphicsDeviceManager *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1804919cc`
- `0x18084288c`

## callees

- `0x180004bc0`
- `0x1802ec53c`
- `0x1803cf970`
- `0x1803cfa14`
- `0x180491a58`
- `0x1806b2e84`
- `0x1806c06e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180491aaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180491aaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180491aba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180491aeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180491aba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180491aeb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180491b92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180491b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180491ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180491ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180491b0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180491b18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180491b0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180491b18`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180491b44`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180491b44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180491bd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180491bd8`

## pseudocode

```c

```
