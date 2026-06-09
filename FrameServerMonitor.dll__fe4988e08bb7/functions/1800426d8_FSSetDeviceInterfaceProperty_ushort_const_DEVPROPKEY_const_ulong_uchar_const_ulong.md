# FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)

- ea: `0x1800426d8`
- end: `0x180042761`
- name: `?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z`
- size: `137`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _DEVPROPKEY *, DEVPROPTYPE, unsigned __int8 *const, ULONG PropertyBufferSize)`
- caller_count: `15`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a728`
- `0x180011dc0`
- `0x180012ec4`
- `0x180023b24`
- `0x180026b78`
- `0x180034e88`
- `0x18003533c`
- `0x180035978`
- `0x1800372fc`
- `0x180037824`
- `0x180037e04`
- `0x18003a99c`
- `0x18003b010`
- `0x18003b9a4`
- `0x180042420`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x1800426d8`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042714`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180042714`
- `api-ms-win-devices-config-l1-1-1!CM_Set_Device_Interface_PropertyW` at `0x1800426ff`
- `api-ms-win-devices-config-l1-1-1!CM_Set_Device_Interface_PropertyW` at `0x1800426ff`

## pseudocode

```c

```
