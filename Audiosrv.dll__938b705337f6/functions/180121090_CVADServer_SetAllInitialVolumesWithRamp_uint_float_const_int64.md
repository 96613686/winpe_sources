# CVADServer::SetAllInitialVolumesWithRamp(uint,float const *,__int64)

- ea: `0x180121090`
- end: `0x1801211fd`
- name: `?SetAllInitialVolumesWithRamp@CVADServer@@UEAAJIPEBM_J@Z`
- size: `365`
- prototype: `int(CVADServer *__hidden this, unsigned int, const float *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801246e0`

## callees

- `0x1800126bc`
- `0x18001caf8`
- `0x18002ebec`
- `0x1800e82c0`
- `0x180121090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801210e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801210e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801211ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801211ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801211ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801211ea`

## string_xrefs

- `0x18012114a`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x180121166`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1801211c9`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
