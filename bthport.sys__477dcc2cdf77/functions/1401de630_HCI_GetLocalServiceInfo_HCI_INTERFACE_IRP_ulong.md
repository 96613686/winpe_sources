# HCI_GetLocalServiceInfo(HCI_INTERFACE *,_IRP *,ulong *)

- ea: `0x1401de630`
- end: `0x1401de806`
- name: `?HCI_GetLocalServiceInfo@@YAJPEAUHCI_INTERFACE@@PEAU_IRP@@PEAK@Z`
- size: `470`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14001e010`

## callees

- `0x140020414`
- `0x140165540`
- `0x1401de630`
- `0x1401de80c`
- `0x1402093a8`
- `0x140209448`
- `0x140209540`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401de7cf`
- `ntoskrnl!ZwClose` at `0x1401de7cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401de791`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401de791`

## string_xrefs

- `0x1401de786`: `ServiceName`

## pseudocode

```c

```
