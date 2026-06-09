# winrePublishWnfStateData(_WNF_STATE_NAME,_WNF_TYPE_ID *,void const *,ulong,void * const)

- ea: `0x18001fbc0`
- end: `0x18001fc41`
- name: `?winrePublishWnfStateData@@YAKU_WNF_STATE_NAME@@PEAU_WNF_TYPE_ID@@PEBXKQEAX@Z`
- size: `129`
- prototype: `unsigned int __fastcall(struct _WNF_STATE_NAME, struct _WNF_TYPE_ID *, const void *, unsigned int, void *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800282d4`
- `0x1800295a0`

## callees

- `0x18001fbc0`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001fc27`
- `ntdll!RtlNtStatusToDosError` at `0x18001fc27`
- `KERNEL32!GetLastError` at `0x18001fbe7`
- `KERNEL32!GetLastError` at `0x18001fbe7`
- `KERNEL32!GetProcAddress` at `0x18001fbf9`
- `KERNEL32!GetProcAddress` at `0x18001fbf9`
- `KERNEL32!GetModuleHandleW` at `0x18001fbdc`
- `KERNEL32!GetModuleHandleW` at `0x18001fbdc`

## string_xrefs

- `0x18001fbd5`: `ntdll.dll`

## pseudocode

```c

```
