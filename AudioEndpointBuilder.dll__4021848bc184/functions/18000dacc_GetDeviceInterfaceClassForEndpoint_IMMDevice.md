# GetDeviceInterfaceClassForEndpoint(IMMDevice *)

- ea: `0x18000dacc`
- end: `0x18000dceb`
- name: `?GetDeviceInterfaceClassForEndpoint@@YA?BU_GUID@@PEAUIMMDevice@@@Z`
- size: `543`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr __struct_ptr retstr, struct IMMDevice *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d000`
- `0x180031920`
- `0x1800588e0`

## callees

- `0x18000dacc`
- `0x18003e920`
- `0x180054c38`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000db9c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000db9c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dbc3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dca5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dbc3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dca5`

## string_xrefs

- `0x18000db38`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000db75`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000dc45`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000dc07`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`

## pseudocode

```c

```
