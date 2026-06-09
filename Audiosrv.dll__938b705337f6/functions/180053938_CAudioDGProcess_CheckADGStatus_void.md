# CAudioDGProcess::CheckADGStatus(void)

- ea: `0x180053938`
- end: `0x180053b07`
- name: `?CheckADGStatus@CAudioDGProcess@@QEAAJXZ`
- size: `463`
- prototype: `__int64 __fastcall(CAudioDGProcess *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18006068c`

## callees

- `0x1800126bc`
- `0x18004f8c4`
- `0x180053938`
- `0x1800a5358`
- `0x1800b6978`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800539f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800539f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053a1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053a1b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800539e1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800539e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ad9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180053a44`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180053ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180053a44`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180053ab3`

## string_xrefs

- `0x180053974`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053990`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053a53`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053a94`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053af0`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`

## pseudocode

```c

```
