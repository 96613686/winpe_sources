# HCI_RegUpdateGuaranteedPsms(HCI_INTERFACE *,void *,_KEY_VALUE_PARTIAL_INFORMATION *,uchar,_GUID *)

- ea: `0x1401cc520`
- end: `0x1401cc75e`
- name: `?HCI_RegUpdateGuaranteedPsms@@YAJPEAUHCI_INTERFACE@@PEAXPEAU_KEY_VALUE_PARTIAL_INFORMATION@@EPEAU_GUID@@@Z`
- size: `574`
- prototype: `int(struct HCI_INTERFACE *, void *, struct _KEY_VALUE_PARTIAL_INFORMATION *, unsigned __int8, struct _GUID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140005690`
- `0x14001be50`
- `0x140165540`
- `0x140165640`
- `0x140165940`
- `0x1401cc520`
- `0x140209448`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401cc673`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cc673`
- `ntoskrnl!ExAllocatePool2` at `0x1401cc641`
- `ntoskrnl!ExAllocatePool2` at `0x1401cc641`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cc5f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cc5f2`

## pseudocode

```c

```
