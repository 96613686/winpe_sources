# WctGetSmbInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005df68`
- end: `0x18005e14b`
- name: `?WctGetSmbInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `483`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *lpInBuffer, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x18001fe24`
- `0x18002bed4`
- `0x180050db0`
- `0x18005df68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e0c7`
- `ntdll!NtCreateFile` at `0x18005e074`
- `ntdll!NtCreateFile` at `0x18005e074`
- `ntdll!RtlNtStatusToDosError` at `0x18005e080`
- `ntdll!RtlNtStatusToDosError` at `0x18005e080`
- `ntdll!RtlInitUnicodeString` at `0x18005e008`
- `ntdll!RtlInitUnicodeString` at `0x18005e008`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005e0bd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005e0bd`

## pseudocode

```c

```
