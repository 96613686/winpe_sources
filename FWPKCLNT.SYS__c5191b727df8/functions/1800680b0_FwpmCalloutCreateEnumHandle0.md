# FwpmCalloutCreateEnumHandle0

- ea: `0x1800680b0`
- end: `0x18006812f`
- name: `FwpmCalloutCreateEnumHandle0`
- size: `127`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const FWPM_CALLOUT_ENUM_TEMPLATE0 *enumTemplate, HANDLE *enumHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x18000c5d0`
- `0x1800680b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800680c2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800680c2`

## string_xrefs

- `0x1800680d8`: `FwpmCalloutCreateEnumHandle0`
- `0x18006810e`: `FwppProxyCalloutCreateEnumHandle`

## pseudocode

```c

```
