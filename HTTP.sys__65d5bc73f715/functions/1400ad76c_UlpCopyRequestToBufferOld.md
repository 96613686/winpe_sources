# UlpCopyRequestToBufferOld

- ea: `0x1400ad76c`
- end: `0x1400aead3`
- name: `UlpCopyRequestToBufferOld`
- size: `4967`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PIRP Irp@<rdx>, int, int, char, char, char, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x14003c124`
- `0x1400406a0`

## callees

- `0x14000a350`
- `0x140022610`
- `0x1400518a0`
- `0x140064ff0`
- `0x1400ac010`
- `0x1400ad76c`
- `0x1400aeadc`
- `0x14012812c`
- `0x1401678f0`
- `0x140167940`
- `0x140167c40`
- `0x1401c37f8`
- `0x1401c49c4`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1400aea58`
- `ntoskrnl!ObCloseHandle` at `0x1400aea74`
- `ntoskrnl!ObCloseHandle` at `0x1400aea58`
- `ntoskrnl!ObCloseHandle` at `0x1400aea74`
- `ntoskrnl!ExRaiseStatus` at `0x1400ae536`
- `ntoskrnl!ExRaiseStatus` at `0x1400ae536`
- `ntoskrnl!IoIs32bitProcess` at `0x1400ad7d0`
- `ntoskrnl!IoIs32bitProcess` at `0x1400ad7d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ae7dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ae7dc`
- `ntoskrnl!ExAllocatePool3` at `0x1400ada13`
- `ntoskrnl!ExAllocatePool3` at `0x1400ada13`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aeab1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aeab1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ae7d0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ae7d0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ad7b5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400ad7b5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ae77f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ae77f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ae766`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ae766`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae33e`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae545`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae33e`
- `HAL!KeQueryPerformanceCounter` at `0x1400ae545`

## pseudocode

```c

```
