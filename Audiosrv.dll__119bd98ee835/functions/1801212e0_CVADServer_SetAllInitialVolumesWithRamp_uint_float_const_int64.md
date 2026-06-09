# CVADServer::SetAllInitialVolumesWithRamp(uint,float const *,__int64)

- ea: `0x1801212e0`
- end: `0x18012144d`
- name: `?SetAllInitialVolumesWithRamp@CVADServer@@UEAAJIPEBM_J@Z`
- size: `365`
- prototype: `int(CVADServer *__hidden this, unsigned int, const float *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180124930`

## callees

- `0x18001280c`
- `0x18001cc48`
- `0x18002ed4c`
- `0x1800e7b40`
- `0x1801212e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801213d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012140a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012143a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801213d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012140a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012143a`

## string_xrefs

- `0x18012139a`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1801213b6`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180121419`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
