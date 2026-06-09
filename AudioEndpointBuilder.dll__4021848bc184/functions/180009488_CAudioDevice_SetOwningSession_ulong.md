# CAudioDevice::SetOwningSession(ulong)

- ea: `0x180009488`
- end: `0x180009510`
- name: `?SetOwningSession@CAudioDevice@@QEAAJK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CAudioDevice *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800092fc`
- `0x180009740`

## callees

- `0x180009488`
- `0x180009518`
- `0x180010da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000949d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000949d`

## string_xrefs

- `0x1800094df`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c

```
