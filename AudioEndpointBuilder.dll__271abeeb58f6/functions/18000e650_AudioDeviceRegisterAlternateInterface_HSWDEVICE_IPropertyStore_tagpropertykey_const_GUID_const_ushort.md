# AudioDeviceRegisterAlternateInterface(HSWDEVICE__ *,IPropertyStore *,_tagpropertykey const &,_GUID const *,ushort * *)

- ea: `0x18000e650`
- end: `0x18000e7ed`
- name: `?AudioDeviceRegisterAlternateInterface@@YAJPEAUHSWDEVICE__@@PEAUIPropertyStore@@AEBU_tagpropertykey@@PEBU_GUID@@PEAPEAG@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct HSWDEVICE__ *, struct IPropertyStore *, const struct _tagpropertykey *, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x18000ceb0`
- `0x18000e650`
- `0x180010da8`
- `0x18003e920`
- `0x180058dbc`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e7c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e7c1`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18000e779`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18000e779`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18000e708`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18000e7b4`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18000e708`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18000e7b4`

## string_xrefs

- `0x18000e6ee`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c

```
