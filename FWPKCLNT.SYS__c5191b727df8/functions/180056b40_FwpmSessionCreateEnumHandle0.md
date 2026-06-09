# FwpmSessionCreateEnumHandle0

- ea: `0x180056b40`
- end: `0x180056bbf`
- name: `FwpmSessionCreateEnumHandle0`
- size: `127`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const FWPM_SESSION_ENUM_TEMPLATE0 *enumTemplate, HANDLE *enumHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180011870`
- `0x180056b40`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180056b52`
- `ntoskrnl!KeGetCurrentIrql` at `0x180056b52`

## string_xrefs

- `0x180056b68`: `FwpmSessionCreateEnumHandle0`
- `0x180056b9e`: `FwppProxySessionCreateEnumHandle`

## pseudocode

```c

```
