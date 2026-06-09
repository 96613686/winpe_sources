# IPsecSaContextUpdate0

- ea: `0x180058ca0`
- end: `0x180058d1f`
- name: `IPsecSaContextUpdate0`
- size: `127`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, UINT64 flags, const IPSEC_SA_CONTEXT1 *newValues)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180010c20`
- `0x180058ca0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180058cb2`
- `ntoskrnl!KeGetCurrentIrql` at `0x180058cb2`

## string_xrefs

- `0x180058cc8`: `IPsecSaContextUpdate0`
- `0x180058cfe`: `FwppProxyBfeIPsecSaContextUpdate`

## pseudocode

```c

```
