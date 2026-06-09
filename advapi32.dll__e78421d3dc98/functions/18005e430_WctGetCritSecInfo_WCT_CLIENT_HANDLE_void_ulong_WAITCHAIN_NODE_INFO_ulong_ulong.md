# WctGetCritSecInfo(_WCT_CLIENT_HANDLE *,void *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005e430`
- end: `0x18005e597`
- name: `?WctGetCritSecInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXKPEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `359`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *, void *, unsigned int, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005e660`

## callees

- `0x18003b57c`
- `0x18003b748`
- `0x18005e430`
- `0x18005fa34`

## import_xrefs

- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18005e558`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18005e558`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18005e4c0`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18005e4c0`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18005e49a`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18005e49a`
- `ntdll!RtlNtStatusToDosError` at `0x18005e4cc`
- `ntdll!RtlNtStatusToDosError` at `0x18005e4cc`
- `KERNEL32!CloseHandle` at `0x18005e53a`
- `KERNEL32!CloseHandle` at `0x18005e54a`
- `KERNEL32!CloseHandle` at `0x18005e53a`
- `KERNEL32!CloseHandle` at `0x18005e54a`

## pseudocode

```c

```
