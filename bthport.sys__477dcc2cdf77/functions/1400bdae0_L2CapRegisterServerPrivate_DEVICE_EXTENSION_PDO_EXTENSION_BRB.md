# L2CapRegisterServerPrivate(DEVICE_EXTENSION *,PDO_EXTENSION *,_BRB *)

- ea: `0x1400bdae0`
- end: `0x1400be8d5`
- name: `?L2CapRegisterServerPrivate@@YAJPEAUDEVICE_EXTENSION@@PEAUPDO_EXTENSION@@PEAU_BRB@@@Z`
- size: `3573`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, struct PDO_EXTENSION *, struct _BRB *)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting`

## callers

- `0x14001d31c`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x140006228`
- `0x140006290`
- `0x140006dcc`
- `0x14000764c`
- `0x14000abf4`
- `0x14001c6d0`
- `0x14001ffe8`
- `0x1400266f4`
- `0x1400272a4`
- `0x140027c70`
- `0x140027cc0`
- `0x140028498`
- `0x14004b86c`
- `0x140078444`
- `0x1400bd960`
- `0x1400bdae0`
- `0x1400bf338`
- `0x1400e0b08`
- `0x14015ce38`
- `0x140165540`
- `0x140165580`
- `0x140165940`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x1400be6ec`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400be6ec`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400be80c`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400be80c`
- `ntoskrnl!ObfReferenceObject` at `0x1400be667`
- `ntoskrnl!ObfReferenceObject` at `0x1400be7ca`
- `ntoskrnl!ObfReferenceObject` at `0x1400be667`
- `ntoskrnl!ObfReferenceObject` at `0x1400be7ca`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400be4cf`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400be4cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be244`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be27a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be84e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be244`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be27a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be84e`
- `ntoskrnl!ExAllocatePool2` at `0x1400bddb3`
- `ntoskrnl!ExAllocatePool2` at `0x1400be0fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400be6bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400bddb3`
- `ntoskrnl!ExAllocatePool2` at `0x1400be0fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400be6bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bdec1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bdec1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bdf82`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400be40a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400be5ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bdf82`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400be40a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400be5ad`

## pseudocode

```c

```
