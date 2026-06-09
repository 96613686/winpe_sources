# FaxExtRegisterForEvents

- ea: `0x14005e6c0`
- end: `0x14005e855`
- name: `FaxExtRegisterForEvents`
- size: `405`
- prototype: `HANDLE __stdcall(HINSTANCE hInst, DWORD dwDeviceId, FAX_ENUM_DEVICE_ID_SOURCE DevIdSrc, LPCWSTR lpcwstrDataGUID, PFAX_EXT_CONFIG_CHANGE lpConfigChangeCallback)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140004c78`
- `0x140004fe4`
- `0x14005cabc`
- `0x14005d820`
- `0x14005e6c0`
- `0x14006a9f0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14005e748`
- `KERNEL32!SetLastError` at `0x14005e748`
- `KERNEL32!EnterCriticalSection` at `0x14005e7f6`
- `KERNEL32!EnterCriticalSection` at `0x14005e7f6`
- `KERNEL32!LeaveCriticalSection` at `0x14005e837`
- `KERNEL32!LeaveCriticalSection` at `0x14005e837`

## pseudocode

```c

```
