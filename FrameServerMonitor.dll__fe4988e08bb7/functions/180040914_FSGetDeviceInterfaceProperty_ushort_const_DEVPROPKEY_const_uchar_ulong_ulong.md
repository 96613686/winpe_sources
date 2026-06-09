# FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)

- ea: `0x180040914`
- end: `0x180040a0a`
- name: `?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z`
- size: `246`
- prototype: `signed int __fastcall(LPCWSTR pszDeviceInterface, DEVPROPKEY *PropertyKey, PBYTE PropertyBuffer, ULONG, unsigned int *)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a728`
- `0x180012ec4`
- `0x1800141c4`
- `0x180020a0c`
- `0x180021c8c`
- `0x18002615c`
- `0x180034e88`
- `0x180036290`
- `0x1800372fc`
- `0x180038600`
- `0x18003a99c`
- `0x18003b010`
- `0x18003f6b4`
- `0x180041d3c`
- `0x18004550c`

## callees

- `0x180040914`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800409e5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800409e5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180040987`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800409d0`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180040987`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800409d0`

## pseudocode

```c

```
