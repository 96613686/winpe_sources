# WctGetCritSecInfo(_WCT_CLIENT_HANDLE *,void *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005d2e0`
- end: `0x18005d447`
- name: `?WctGetCritSecInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXKPEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `359`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *, void *, unsigned int, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005d2e0`
- `0x18005eb48`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005d37c`
- `ntdll!RtlNtStatusToDosError` at `0x18005d37c`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18005d34a`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18005d34a`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18005d370`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18005d370`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18005d408`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18005d408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d3ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d3fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d3ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d3fa`

## pseudocode

```c

```
