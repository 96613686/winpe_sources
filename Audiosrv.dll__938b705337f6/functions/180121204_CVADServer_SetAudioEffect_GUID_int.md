# CVADServer::SetAudioEffect(_GUID,int)

- ea: `0x180121204`
- end: `0x1801213e6`
- name: `?SetAudioEffect@CVADServer@@QEAAJU_GUID@@H@Z`
- size: `482`
- prototype: `int(CVADServer *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180124a50`

## callees

- `0x1800126bc`
- `0x18001b3d0`
- `0x1800463cc`
- `0x180073310`
- `0x1800cf8c0`
- `0x1800ecde4`
- `0x180121204`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18012125e`
- `ntdll!EtwEventActivityIdControl` at `0x1801213bb`
- `ntdll!EtwEventActivityIdControl` at `0x18012125e`
- `ntdll!EtwEventActivityIdControl` at `0x1801213bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012126f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012126f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801212d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801213aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801212d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801213aa`

## string_xrefs

- `0x1801212b5`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
