# HCI_RegUpdateStoredLinkKeyCodMasks(HCI_INTERFACE *,void *,_KEY_VALUE_PARTIAL_INFORMATION *,uchar,_GUID *)

- ea: `0x1401d1c50`
- end: `0x1401d1ef1`
- name: `?HCI_RegUpdateStoredLinkKeyCodMasks@@YAJPEAUHCI_INTERFACE@@PEAXPEAU_KEY_VALUE_PARTIAL_INFORMATION@@EPEAU_GUID@@@Z`
- size: `673`
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
- `0x1401d1c50`
- `0x140209448`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1da7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1da7`
- `ntoskrnl!ExAllocatePool2` at `0x1401d1d75`
- `ntoskrnl!ExAllocatePool2` at `0x1401d1d75`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d1d22`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d1d22`

## string_xrefs

- `0x1401d1d16`: `Store Link Key COD Masks`

## pseudocode

```c

```
