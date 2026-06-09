# CEndpointCharacteristics::SetUserSelectedEffectPack(_GUID)

- ea: `0x1800bab20`
- end: `0x1800bad4c`
- name: `?SetUserSelectedEffectPack@CEndpointCharacteristics@@QEAAJU_GUID@@@Z`
- size: `556`
- prototype: `int(CEndpointCharacteristics *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18011c4f0`

## callees

- `0x18000cba0`
- `0x18000e284`
- `0x18001280c`
- `0x1800bab20`
- `0x1800c2fd4`
- `0x1800cbfcc`
- `0x1800ce750`
- `0x180145378`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800baca6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bad34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800baca6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bad34`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bac4c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bad0c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bac4c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bad0c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800babe0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800babe0`

## string_xrefs

- `0x1800bab97`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800bac36`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800bac73`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800bacf6`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c

```
