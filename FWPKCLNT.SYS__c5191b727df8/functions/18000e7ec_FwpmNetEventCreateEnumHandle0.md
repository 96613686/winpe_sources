# FwpmNetEventCreateEnumHandle0

- ea: `0x18000e7ec`
- end: `0x18000e88f`
- name: `FwpmNetEventCreateEnumHandle0`
- size: `163`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const FWPM_NET_EVENT_ENUM_TEMPLATE0 *enumTemplate, HANDLE *enumHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005976c`

## callees

- `0x180004904`
- `0x180008f10`
- `0x18000e7ec`
- `0x1800674e4`
- `0x180068238`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000e7fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000e7fe`
- `msrpc!NdrClientCall3` at `0x18000e85b`
- `msrpc!NdrClientCall3` at `0x18000e85b`

## string_xrefs

- `0x18000e814`: `FwpmNetEventCreateEnumHandle0`
- `0x18000e86e`: `FwppProxyNetEventCreateEnumHandle`

## pseudocode

```c

```
