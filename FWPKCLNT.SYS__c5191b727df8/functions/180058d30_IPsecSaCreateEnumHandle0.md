# IPsecSaCreateEnumHandle0

- ea: `0x180058d30`
- end: `0x180058daf`
- name: `IPsecSaCreateEnumHandle0`
- size: `127`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const IPSEC_SA_ENUM_TEMPLATE0 *enumTemplate, HANDLE *enumHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180010c5c`
- `0x180058d30`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180058d42`
- `ntoskrnl!KeGetCurrentIrql` at `0x180058d42`

## string_xrefs

- `0x180058d58`: `IPsecSaCreateEnumHandle0`
- `0x180058d8e`: `FwppProxyBfeIPsecSaCreateEnumHandle`

## pseudocode

```c

```
