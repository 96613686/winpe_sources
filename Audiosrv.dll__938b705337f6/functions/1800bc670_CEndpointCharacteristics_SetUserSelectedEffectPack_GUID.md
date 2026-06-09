# CEndpointCharacteristics::SetUserSelectedEffectPack(_GUID)

- ea: `0x1800bc670`
- end: `0x1800bc89c`
- name: `?SetUserSelectedEffectPack@CEndpointCharacteristics@@QEAAJU_GUID@@@Z`
- size: `556`
- prototype: `int(CEndpointCharacteristics *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18011c2a0`

## callees

- `0x18000ca50`
- `0x18000e134`
- `0x1800126bc`
- `0x1800bc670`
- `0x1800c4b24`
- `0x1800cdfbc`
- `0x1800d0740`
- `0x180144968`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc7f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc884`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc7f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc884`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bc79c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bc85c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bc79c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bc85c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800bc730`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800bc730`

## string_xrefs

- `0x1800bc6e7`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800bc786`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800bc7c3`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800bc846`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c

```
