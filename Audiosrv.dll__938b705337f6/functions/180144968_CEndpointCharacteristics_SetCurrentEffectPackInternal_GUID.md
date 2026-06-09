# CEndpointCharacteristics::SetCurrentEffectPackInternal(_GUID)

- ea: `0x180144968`
- end: `0x180144c1d`
- name: `?SetCurrentEffectPackInternal@CEndpointCharacteristics@@QEAAJU_GUID@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(CEndpointCharacteristics *__hidden this, struct _GUID *Buf2)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bc670`
- `0x18013f3f0`

## callees

- `0x180005870`
- `0x1800126bc`
- `0x180023690`
- `0x18002c94c`
- `0x180045c2c`
- `0x1800c4b24`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x180144518`
- `0x180144968`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801449a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801449a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180144ac9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180144b7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180144be2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180144ac9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180144b7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180144be2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180144b2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180144b2f`

## string_xrefs

- `0x180144a9f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144b18`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144b51`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c

```
