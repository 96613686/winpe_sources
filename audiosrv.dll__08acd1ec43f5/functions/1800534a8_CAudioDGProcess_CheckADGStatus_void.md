# CAudioDGProcess::CheckADGStatus(void)

- ea: `0x1800534a8`
- end: `0x180053677`
- name: `?CheckADGStatus@CAudioDGProcess@@QEAAJXZ`
- size: `463`
- prototype: `__int64 __fastcall(CAudioDGProcess *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800601fc`

## callees

- `0x18001280c`
- `0x18004f434`
- `0x1800534a8`
- `0x1800a4af8`
- `0x1800b4c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053563`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053563`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005358b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005358b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180053551`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180053551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053649`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800535b4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180053623`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800535b4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180053623`

## string_xrefs

- `0x1800534e4`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053500`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x1800535c3`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053604`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180053660`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`

## pseudocode

```c

```
