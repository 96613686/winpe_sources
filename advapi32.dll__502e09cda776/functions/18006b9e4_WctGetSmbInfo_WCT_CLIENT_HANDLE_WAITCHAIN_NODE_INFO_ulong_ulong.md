# WctGetSmbInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18006b9e4`
- end: `0x18006bbe7`
- name: `?WctGetSmbInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `515`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *lpInBuffer, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18006ae08`

## callees

- `0x18003faec`
- `0x18003fb18`
- `0x18003fd04`
- `0x18006a520`
- `0x18006b9e4`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18006baf6`
- `ntdll!NtCreateFile` at `0x18006baf6`
- `ntdll!RtlNtStatusToDosError` at `0x18006bb08`
- `ntdll!RtlNtStatusToDosError` at `0x18006bb08`
- `ntdll!RtlInitUnicodeString` at `0x18006ba84`
- `ntdll!RtlInitUnicodeString` at `0x18006ba84`
- `KERNEL32!GetLastError` at `0x18006bb5b`
- `KERNEL32!GetLastError` at `0x18006bb5b`
- `KERNEL32!DeviceIoControl` at `0x18006bb4b`
- `KERNEL32!DeviceIoControl` at `0x18006bb4b`

## pseudocode

```c

```
