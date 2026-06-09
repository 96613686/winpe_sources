# CSecurityData::KdcTicketRenewSpan(void)

- ea: `0x18001d260`
- end: `0x18001d29d`
- name: `?KdcTicketRenewSpan@CSecurityData@@QEAA?AT_LARGE_INTEGER@@XZ`
- size: `61`
- prototype: `union _LARGE_INTEGER __fastcall(CSecurityData *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016148`
- `0x1800216cc`
- `0x1800463bc`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18001d277`
- `ntdll!RtlAcquireResourceShared` at `0x18001d277`
- `ntdll!RtlReleaseResource` at `0x18001d28e`
- `ntdll!RtlReleaseResource` at `0x18001d28e`

## pseudocode

```c

```
