# HCI_RegUpdateEirReservedIds(HCI_INTERFACE *,void *,_KEY_VALUE_PARTIAL_INFORMATION *,uchar,_GUID *)

- ea: `0x1401cb9b4`
- end: `0x1401cbc55`
- name: `?HCI_RegUpdateEirReservedIds@@YAJPEAUHCI_INTERFACE@@PEAXPEAU_KEY_VALUE_PARTIAL_INFORMATION@@EPEAU_GUID@@@Z`
- size: `673`
- prototype: `int(struct HCI_INTERFACE *, void *, struct _KEY_VALUE_PARTIAL_INFORMATION *, unsigned __int8, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1401cbd50`

## callees

- `0x140005608`
- `0x140005690`
- `0x14001be50`
- `0x140165540`
- `0x140165640`
- `0x140165940`
- `0x1401cb9b4`
- `0x140209448`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbb1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbb1d`
- `ntoskrnl!ExAllocatePool2` at `0x1401cbc11`
- `ntoskrnl!ExAllocatePool2` at `0x1401cbc11`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cba83`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cba83`

## pseudocode

```c

```
