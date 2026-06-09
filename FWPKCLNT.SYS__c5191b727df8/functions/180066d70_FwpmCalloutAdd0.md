# FwpmCalloutAdd0

- ea: `0x180066d70`
- end: `0x180066e88`
- name: `FwpmCalloutAdd0`
- size: `280`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const FWPM_CALLOUT0 *callout, PSECURITY_DESCRIPTOR sd, UINT32 *id)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180052fe0`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x1800083f8`
- `0x1800086fc`
- `0x180008f10`
- `0x180008f5c`
- `0x180009ca4`
- `0x1800203c0`
- `0x180066d70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180066dab`
- `ntoskrnl!KeGetCurrentIrql` at `0x180066dab`

## pseudocode

```c

```
