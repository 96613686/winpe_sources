# CVADServer::SetAudioEffect(_GUID,int)

- ea: `0x180121454`
- end: `0x180121636`
- name: `?SetAudioEffect@CVADServer@@QEAAJU_GUID@@H@Z`
- size: `482`
- prototype: `int(CVADServer *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180124ca0`

## callees

- `0x18001280c`
- `0x18001b520`
- `0x180045f3c`
- `0x180072e10`
- `0x1800cd8d0`
- `0x1800ec664`
- `0x180121454`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1801214ae`
- `ntdll!EtwEventActivityIdControl` at `0x18012160b`
- `ntdll!EtwEventActivityIdControl` at `0x1801214ae`
- `ntdll!EtwEventActivityIdControl` at `0x18012160b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801214bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801214bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801215fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801215fa`

## string_xrefs

- `0x180121505`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
