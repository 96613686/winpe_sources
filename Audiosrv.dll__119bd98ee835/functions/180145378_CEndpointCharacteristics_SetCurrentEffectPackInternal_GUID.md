# CEndpointCharacteristics::SetCurrentEffectPackInternal(_GUID)

- ea: `0x180145378`
- end: `0x18014562d`
- name: `?SetCurrentEffectPackInternal@CEndpointCharacteristics@@QEAAJU_GUID@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(CEndpointCharacteristics *__hidden this, struct _GUID *Buf2)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bab20`
- `0x18013f3d4`

## callees

- `0x180005a7c`
- `0x18001280c`
- `0x1800237e0`
- `0x18002caac`
- `0x18004579c`
- `0x1800c2fd4`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x180144f28`
- `0x180145378`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801453b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801453b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801454d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18014558b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801455f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801454d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18014558b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801455f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18014553f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18014553f`

## string_xrefs

- `0x1801454af`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180145528`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180145561`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c

```
