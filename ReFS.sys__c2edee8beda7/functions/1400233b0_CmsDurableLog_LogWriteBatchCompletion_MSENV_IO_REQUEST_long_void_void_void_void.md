# CmsDurableLog::LogWriteBatchCompletion(_MSENV_IO_REQUEST *,long,void *,void *,void *,void *)

- ea: `0x1400233b0`
- end: `0x1400236ec`
- name: `?LogWriteBatchCompletion@CmsDurableLog@@CAJPEAU_MSENV_IO_REQUEST@@JPEAX111@Z`
- size: `828`
- prototype: `__int64 __fastcall(PVOID P, int, void *, void *, void *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140022ba8`
- `0x140022cd0`
- `0x140022e80`
- `0x1400231c4`
- `0x1400232fc`
- `0x140023394`
- `0x1400233b0`
- `0x140023700`
- `0x140024c60`
- `0x140049050`
- `0x14008bd30`
- `0x1400cbe48`
- `0x140126378`
- `0x14015761c`
- `0x14015f294`
- `0x1401f40a0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14002366d`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002366d`
- `ntoskrnl!KeSetEvent` at `0x1400236c2`
- `ntoskrnl!KeSetEvent` at `0x1400236c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023531`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002354a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023592`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023531`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002354a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023592`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023562`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023574`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400235b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023562`
- `ntoskrnl!KeReleaseSpinLock` at `0x140023574`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400235b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234b3`

## pseudocode

```c

```
