# UnionFs::UnionFsFilter::PortMessage(void *,void *,ulong,void *,ulong,ulong *)

- ea: `0x14000c280`
- end: `0x14000c941`
- name: `?PortMessage@UnionFsFilter@UnionFs@@SAJPEAX0K0KPEAK@Z`
- size: `1729`
- prototype: `__int64 __fastcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x1400047d4`
- `0x140005504`
- `0x1400055d0`
- `0x140006168`
- `0x1400090f0`
- `0x14000c280`
- `0x14000de84`
- `0x14000e53c`
- `0x14000e83c`
- `0x14000eab0`
- `0x140056974`
- `0x140056c44`
- `0x140056c7c`
- `0x140069a80`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bc40`
- `0x1400a7008`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c624`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c817`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c82d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c624`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c817`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c82d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8c6`

## string_xrefs

- `0x14000c723`: `PUSH: Message Response: CreateConfigureUnion`
- `0x14000c66d`: `PUSH: Message Response: ProcessRemoveUnionMsg`
- `0x14000c6b3`: `usedRemoveResponseSize <= OutputBufferSize - FIELD_OFFSET(UFS_MESSAGE, Buffer)`
- `0x14000c799`: `ORIGIN: Copying to user output buffer`

## pseudocode

```c

```
