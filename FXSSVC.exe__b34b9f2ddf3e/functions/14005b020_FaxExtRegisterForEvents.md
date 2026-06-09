# FaxExtRegisterForEvents

- ea: `0x14005b020`
- end: `0x14005b1a2`
- name: `FaxExtRegisterForEvents`
- size: `386`
- prototype: `HANDLE __stdcall(HINSTANCE hInst, DWORD dwDeviceId, FAX_ENUM_DEVICE_ID_SOURCE DevIdSrc, LPCWSTR lpcwstrDataGUID, PFAX_EXT_CONFIG_CHANGE lpConfigChangeCallback)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140004b30`
- `0x140004e68`
- `0x1400594ec`
- `0x14005a1c0`
- `0x14005b020`
- `0x140066c9c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14005b0a8`
- `KERNEL32!SetLastError` at `0x14005b0a8`
- `KERNEL32!EnterCriticalSection` at `0x14005b150`
- `KERNEL32!EnterCriticalSection` at `0x14005b150`
- `KERNEL32!LeaveCriticalSection` at `0x14005b18b`
- `KERNEL32!LeaveCriticalSection` at `0x14005b18b`

## pseudocode

```c

```
