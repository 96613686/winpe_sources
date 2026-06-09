# RefsMasterIrpAsyncCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400b6650`
- end: `0x1400b6b99`
- name: `?RefsMasterIrpAsyncCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `1353`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct REFS_IO_CONTEXT *)`
- caller_count: `0`
- callee_count: `23`
- tags: `broker_com_uri`

## callees

- `0x14000a650`
- `0x14000c180`
- `0x14000f090`
- `0x140035da0`
- `0x140047580`
- `0x14005c048`
- `0x140083e60`
- `0x140085ef0`
- `0x1400862c0`
- `0x140089a80`
- `0x1400a73b4`
- `0x1400a9600`
- `0x1400aaba8`
- `0x1400acbf0`
- `0x1400b6480`
- `0x1400b6650`
- `0x1400b9530`
- `0x1400d0fd8`
- `0x1400d266c`
- `0x1400ea864`
- `0x1401034fc`
- `0x140103a28`
- `0x14011b214`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400b66a3`
- `ntoskrnl!KeSetEvent` at `0x1400b66a3`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400b697c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400b697c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400b6716`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400b6b21`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400b6716`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400b6b21`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400b6726`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400b6b31`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400b6726`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400b6b31`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x1400b6a8d`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x1400b6a8d`

## pseudocode

```c

```
