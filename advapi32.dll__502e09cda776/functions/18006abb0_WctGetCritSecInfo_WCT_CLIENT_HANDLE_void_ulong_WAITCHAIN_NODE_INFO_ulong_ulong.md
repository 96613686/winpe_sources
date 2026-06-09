# WctGetCritSecInfo(_WCT_CLIENT_HANDLE *,void *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18006abb0`
- end: `0x18006ad3c`
- name: `?WctGetCritSecInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXKPEAU_WAITCHAIN_NODE_INFO@@PEAK3@Z`
- size: `396`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *, void *, unsigned int, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18006ae08`

## callees

- `0x18003fb18`
- `0x18003fd04`
- `0x18006abb0`
- `0x18006c2cc`

## import_xrefs

- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18006acf6`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18006acf6`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18006ac46`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18006ac46`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18006ac1a`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18006ac1a`
- `ntdll!RtlNtStatusToDosError` at `0x18006ac58`
- `ntdll!RtlNtStatusToDosError` at `0x18006ac58`
- `KERNEL32!CloseHandle` at `0x18006accc`
- `KERNEL32!CloseHandle` at `0x18006ace2`
- `KERNEL32!CloseHandle` at `0x18006accc`
- `KERNEL32!CloseHandle` at `0x18006ace2`

## pseudocode

```c

```
