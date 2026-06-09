# FwpmFilterCreateEnumHandle0

- ea: `0x1800675e0`
- end: `0x180067661`
- name: `FwpmFilterCreateEnumHandle0`
- size: `129`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const FWPM_FILTER_ENUM_TEMPLATE0 *enumTemplate, HANDLE *enumHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180009cec`
- `0x1800675e0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800675f2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800675f2`

## string_xrefs

- `0x180067637`: `FwpmFilterCreateEnumHandle0`
- `0x180067653`: `FwppProxyFilterCreateEnumHandle`

## pseudocode

```c

```
