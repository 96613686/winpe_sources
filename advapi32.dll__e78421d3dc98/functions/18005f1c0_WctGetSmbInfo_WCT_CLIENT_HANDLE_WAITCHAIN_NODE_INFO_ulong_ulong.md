# WctGetSmbInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005f1c0`
- end: `0x18005f3a4`
- name: `?WctGetSmbInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `484`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *lpInBuffer, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18005e660`

## callees

- `0x18003ac90`
- `0x18003b57c`
- `0x18003b748`
- `0x18005ddd0`
- `0x18005f1c0`
- `0x180065090`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18005f2cc`
- `ntdll!NtCreateFile` at `0x18005f2cc`
- `ntdll!RtlNtStatusToDosError` at `0x18005f2d8`
- `ntdll!RtlNtStatusToDosError` at `0x18005f2d8`
- `ntdll!RtlInitUnicodeString` at `0x18005f260`
- `ntdll!RtlInitUnicodeString` at `0x18005f260`
- `KERNEL32!GetLastError` at `0x18005f31f`
- `KERNEL32!GetLastError` at `0x18005f31f`
- `KERNEL32!DeviceIoControl` at `0x18005f315`
- `KERNEL32!DeviceIoControl` at `0x18005f315`

## pseudocode

```c

```
