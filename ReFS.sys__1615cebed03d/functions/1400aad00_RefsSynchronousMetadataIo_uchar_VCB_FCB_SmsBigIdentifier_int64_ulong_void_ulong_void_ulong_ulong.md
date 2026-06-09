# RefsSynchronousMetadataIo(uchar,_VCB *,_FCB *,SmsBigIdentifier *,__int64,ulong,void *,ulong *,void *,ulong,ulong)

- ea: `0x1400aad00`
- end: `0x1400ab399`
- name: `?RefsSynchronousMetadataIo@@YAJEPEAU_VCB@@PEAU_FCB@@PEATSmsBigIdentifier@@_JKPEAXPEAK4KK@Z`
- size: `1689`
- prototype: `int(unsigned __int8, struct _VCB *, struct _FCB *, union SmsBigIdentifier *, __int64, unsigned int, void *, unsigned int *, void *, unsigned int, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1400aabdc`
- `0x1400aac78`
- `0x1400ddeb4`
- `0x1400e8584`
- `0x1400f4300`
- `0x1400fc190`
- `0x140291128`
- `0x1402a03fc`
- `0x14032720c`

## callees

- `0x1400aad00`
- `0x1400f4b14`
- `0x140103a28`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400ab10e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400ab10e`
- `ntoskrnl!IoGetStackLimits` at `0x1400ab0c1`
- `ntoskrnl!IoGetStackLimits` at `0x1400ab0c1`
- `ntoskrnl!DbgPrintEx` at `0x1400ab1e3`
- `ntoskrnl!DbgPrintEx` at `0x1400ab2db`
- `ntoskrnl!DbgPrintEx` at `0x1400ab1e3`
- `ntoskrnl!DbgPrintEx` at `0x1400ab2db`
- `ntoskrnl!IoFreeIrp` at `0x1400aae3b`
- `ntoskrnl!IoFreeIrp` at `0x1400ab36d`
- `ntoskrnl!IoFreeIrp` at `0x1400aae3b`
- `ntoskrnl!IoFreeIrp` at `0x1400ab36d`
- `ntoskrnl!IoAllocateMdl` at `0x1400aadc3`
- `ntoskrnl!IoAllocateMdl` at `0x1400aadc3`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400aadf1`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400aadf1`
- `ntoskrnl!IoFreeMdl` at `0x1400aae24`
- `ntoskrnl!IoFreeMdl` at `0x1400ab309`
- `ntoskrnl!IoFreeMdl` at `0x1400aae24`
- `ntoskrnl!IoFreeMdl` at `0x1400ab309`
- `ntoskrnl!MmUnlockPages` at `0x1400ab2f9`
- `ntoskrnl!MmUnlockPages` at `0x1400ab2f9`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400ab15d`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400ab15d`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400aae06`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400aae06`
- `ntoskrnl!IofCallDriver` at `0x1400ab121`
- `ntoskrnl!IofCallDriver` at `0x1400ab121`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400aad66`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400aad66`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ab147`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ab147`
- `ntoskrnl!KeInitializeEvent` at `0x1400aaeb7`
- `ntoskrnl!KeInitializeEvent` at `0x1400aaeb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab34f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab34f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aaf79`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aaf79`

## string_xrefs

- `0x1400ab1d5`: `SynchronousMinstoreIo (readcopy) to Vcb: %p TargetDeviceObject: %p returned unexpected status %08lx (will be reported only once)\n`
- `0x1400ab2a5`: `write`

## pseudocode

```c

```
