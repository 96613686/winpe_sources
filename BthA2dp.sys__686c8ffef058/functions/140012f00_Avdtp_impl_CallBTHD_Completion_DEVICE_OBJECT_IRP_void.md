# Avdtp_impl::CallBTHD_Completion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140012f00`
- end: `0x140012fb6`
- name: `?CallBTHD_Completion@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `182`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012f00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140012f77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012f77`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012f24`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012f24`
- `ntoskrnl!KeSetEvent` at `0x140012f92`
- `ntoskrnl!KeSetEvent` at `0x140012f92`

## pseudocode

```c

```
