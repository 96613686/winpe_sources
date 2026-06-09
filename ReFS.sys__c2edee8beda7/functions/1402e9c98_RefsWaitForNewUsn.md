# RefsWaitForNewUsn

- ea: `0x1402e9c98`
- end: `0x1402ea1a8`
- name: `RefsWaitForNewUsn`
- size: `1296`
- prototype: `__int64 __fastcall(int, int, int, int, char, struct _IRP *, PLARGE_INTEGER, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1402ea1b0`

## callees

- `0x1400862c0`
- `0x140098a20`
- `0x1400a6f70`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x1401f4400`
- `0x1402e9c98`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402e9ebe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402ea057`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402e9ebe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402ea057`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e9e43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e9f89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e9e43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e9f89`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402e9e86`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402e9e86`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e9d96`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402ea088`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e9d96`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402ea088`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e9dac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402ea097`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e9dac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402ea097`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e9dfd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ea0d0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ea0f9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e9dfd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ea0d0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ea0f9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e9e09`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ea0dc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ea105`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e9e09`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ea0dc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402ea105`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e9e6f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e9e6f`
- `ntoskrnl!KeInitializeEvent` at `0x1402e9d73`
- `ntoskrnl!KeInitializeEvent` at `0x1402e9d73`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e9e37`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e9f7d`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e9e37`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e9f7d`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e9edc`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402ea076`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e9edc`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402ea076`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ea116`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ea188`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ea116`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ea188`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402e9ccd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402e9ccd`

## pseudocode

```c

```
