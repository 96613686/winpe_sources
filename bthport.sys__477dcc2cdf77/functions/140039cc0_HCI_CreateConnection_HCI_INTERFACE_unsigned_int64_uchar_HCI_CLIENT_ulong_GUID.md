# HCI_CreateConnection(HCI_INTERFACE *,unsigned __int64,uchar *,HCI_CLIENT *,ulong,_GUID *)

- ea: `0x140039cc0`
- end: `0x14003a0f9`
- name: `?HCI_CreateConnection@@YAJPEAUHCI_INTERFACE@@_KPEAEPEAUHCI_CLIENT@@KPEAU_GUID@@@Z`
- size: `1081`
- prototype: `int(struct HCI_INTERFACE *, unsigned __int64, unsigned __int8 *, struct HCI_CLIENT *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140120624`

## callees

- `0x140005608`
- `0x140005748`
- `0x140005a64`
- `0x140005b4c`
- `0x140039cc0`
- `0x14003af88`
- `0x14003fc34`
- `0x140042460`
- `0x140092fe8`
- `0x1400a536c`
- `0x14015ce38`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a00d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a00d`
- `ntoskrnl!ExAllocatePool2` at `0x140039e5e`
- `ntoskrnl!ExAllocatePool2` at `0x140039e5e`

## string_xrefs

- `0x140039f69`: `LE connection creation should not be going down legacy path.`

## pseudocode

```c

```
