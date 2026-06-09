# HCI_SetLocalServiceInfo(HCI_INTERFACE *,_IRP *,ulong *)

- ea: `0x14011ff10`
- end: `0x1401204c9`
- name: `?HCI_SetLocalServiceInfo@@YAJPEAUHCI_INTERFACE@@PEAU_IRP@@PEAK@Z`
- size: `1465`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x14001e010`

## callees

- `0x14001dc48`
- `0x1400203a4`
- `0x14006405c`
- `0x1400640fc`
- `0x14011ff10`
- `0x140165540`
- `0x1401de284`
- `0x1401de544`
- `0x1401de80c`
- `0x1401e57b8`
- `0x1402093a8`
- `0x140209540`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x140120150`
- `ntoskrnl!ZwSetValueKey` at `0x1401201cd`
- `ntoskrnl!ZwSetValueKey` at `0x14012020f`
- `ntoskrnl!ZwSetValueKey` at `0x140120252`
- `ntoskrnl!ZwSetValueKey` at `0x1401202ea`
- `ntoskrnl!ZwSetValueKey` at `0x140120333`
- `ntoskrnl!ZwSetValueKey` at `0x140120150`
- `ntoskrnl!ZwSetValueKey` at `0x1401201cd`
- `ntoskrnl!ZwSetValueKey` at `0x14012020f`
- `ntoskrnl!ZwSetValueKey` at `0x140120252`
- `ntoskrnl!ZwSetValueKey` at `0x1401202ea`
- `ntoskrnl!ZwSetValueKey` at `0x140120333`
- `ntoskrnl!ZwClose` at `0x14012004d`
- `ntoskrnl!ZwClose` at `0x1401200c7`
- `ntoskrnl!ZwClose` at `0x1401200d7`
- `ntoskrnl!ZwClose` at `0x14012047b`
- `ntoskrnl!ZwClose` at `0x14012048b`
- `ntoskrnl!ZwClose` at `0x14012004d`
- `ntoskrnl!ZwClose` at `0x1401200c7`
- `ntoskrnl!ZwClose` at `0x1401200d7`
- `ntoskrnl!ZwClose` at `0x14012047b`
- `ntoskrnl!ZwClose` at `0x14012048b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120124`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120199`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401201e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120226`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401202be`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120301`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120124`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120199`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401201e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120226`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401202be`
- `ntoskrnl!RtlInitUnicodeString` at `0x140120301`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140120086`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401203b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140120444`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140120086`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401203b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140120444`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401200b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012010d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401203ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012045b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401200b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012010d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401203ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012045b`

## string_xrefs

- `0x14012018e`: `ServiceName`

## pseudocode

```c

```
