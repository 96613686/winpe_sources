# NtfsDefragFileInternal

- ea: `0x14021ec20`
- end: `0x140220b83`
- name: `NtfsDefragFileInternal`
- size: `8035`
- prototype: `__int64 __usercall@<rax>(PVOID Context1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `53`
- tags: ``

## callers

- `0x14022c05c`

## callees

- `0x1400055f0`
- `0x140007670`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000e220`
- `0x1400100b0`
- `0x140010be0`
- `0x140012e70`
- `0x140015b90`
- `0x14001d8f0`
- `0x14001e2f0`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021590`
- `0x140021c30`
- `0x14002b680`
- `0x140030850`
- `0x14003e5b4`
- `0x14004062c`
- `0x1400410a8`
- `0x1400592c0`
- `0x1401231c0`
- `0x1401241f0`
- `0x140125100`
- `0x140137cb0`
- `0x1401403d0`
- `0x1401597b8`
- `0x1401602a0`
- `0x140160ee0`
- `0x140173e00`
- `0x140175270`
- `0x140176eb0`
- `0x1401aab70`
- `0x1401be3e8`
- `0x1401c0130`
- `0x1401cfc68`
- `0x1401d2528`
- `0x1401d2c84`
- `0x1401d2d3c`
- `0x1401e06b0`
- `0x140209960`
- `0x14020f3a0`
- `0x14021aa70`
- `0x14021ec20`
- `0x1402288dc`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14021f673`
- `ntoskrnl!IoAllocateMdl` at `0x14021f673`
- `ntoskrnl!IoFreeMdl` at `0x14022088e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5acd`
- `ntoskrnl!IoFreeMdl` at `0x14022088e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5acd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14021f68f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14021f68f`
- `ntoskrnl!MmMdlPageContentsState` at `0x14021f6a8`
- `ntoskrnl!MmMdlPageContentsState` at `0x14021f6a8`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14021f39c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14021f39c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14022074d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b59d7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14022074d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b59d7`
- `ntoskrnl!KeClearEvent` at `0x14021f8ea`
- `ntoskrnl!KeClearEvent` at `0x14021f8ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021efa0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021f933`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021efa0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021f933`
- `ntoskrnl!KeInitializeEvent` at `0x14021eeb3`
- `ntoskrnl!KeInitializeEvent` at `0x14021eeb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021f6be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14022089f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402208f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5ade`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021f6be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14022089f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402208f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5ade`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5b50`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021ee91`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021f63a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021ee91`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021f63a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021f8c1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fa0f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fb68`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fd07`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b56fc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021f8c1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fa0f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fb68`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fd07`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b56fc`
- `ntoskrnl!CcUnpinData` at `0x14022080f`
- `ntoskrnl!CcUnpinData` at `0x140220834`
- `ntoskrnl!CcUnpinData` at `0x140220859`
- `ntoskrnl!CcUnpinData` at `0x14022080f`
- `ntoskrnl!CcUnpinData` at `0x140220834`
- `ntoskrnl!CcUnpinData` at `0x140220859`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021f905`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021fa2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140220792`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b5716`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b5a1b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021f905`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021fa2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140220792`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b5716`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b5a1b`
- `ntoskrnl!CcFlushCache` at `0x14021ff31`
- `ntoskrnl!CcFlushCache` at `0x14021ff31`

## pseudocode

```c

```
