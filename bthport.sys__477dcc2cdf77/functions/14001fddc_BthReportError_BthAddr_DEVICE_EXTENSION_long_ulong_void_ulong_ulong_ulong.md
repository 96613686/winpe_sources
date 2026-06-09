# BthReportError_BthAddr(DEVICE_EXTENSION *,long,ulong,void *,ulong,ulong,ulong)

- ea: `0x14001fddc`
- end: `0x14001ffe1`
- name: `?BthReportError_BthAddr@@YAXPEAUDEVICE_EXTENSION@@JKPEAXKKK@Z`
- size: `517`
- prototype: `void(struct DEVICE_EXTENSION *, int, unsigned int, void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `20`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14002d5a4`
- `0x140037780`
- `0x14003a890`
- `0x140042460`
- `0x14004a0c0`
- `0x14005d8b0`
- `0x1400a42e0`
- `0x1400a45f0`
- `0x1400a58e8`
- `0x1400a629c`
- `0x1400c66a0`
- `0x140150dd0`
- `0x1401511a0`
- `0x1401523a0`
- `0x140154b20`
- `0x140156f10`
- `0x1401b92c0`
- `0x1401f6300`
- `0x1401f8f90`
- `0x1401fdd08`

## callees

- `0x14000abf4`
- `0x14001fbbc`
- `0x14001fddc`
- `0x140020414`
- `0x1400272a4`
- `0x140165540`
- `0x140165640`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14001fe8d`
- `ntoskrnl!IoFreeWorkItem` at `0x14001fe8d`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001fe50`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001fe50`
- `ntoskrnl!IoQueueWorkItem` at `0x14001ff1b`
- `ntoskrnl!IoQueueWorkItem` at `0x14001ff1b`
- `ntoskrnl!ExAllocatePool2` at `0x14001fe76`
- `ntoskrnl!ExAllocatePool2` at `0x14001feb5`
- `ntoskrnl!ExAllocatePool2` at `0x14001fe76`
- `ntoskrnl!ExAllocatePool2` at `0x14001feb5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001fe24`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001fe24`

## pseudocode

```c

```
