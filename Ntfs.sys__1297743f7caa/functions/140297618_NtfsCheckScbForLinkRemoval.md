# NtfsCheckScbForLinkRemoval

- ea: `0x140297618`
- end: `0x140297d6a`
- name: `NtfsCheckScbForLinkRemoval`
- size: `1874`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, CLFS_LSN *plsn2)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140247338`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140031a50`
- `0x14003f358`
- `0x14003f52c`
- `0x1400ffa1c`
- `0x14018dc9c`
- `0x1401dc638`
- `0x14022c85c`
- `0x140297618`

## import_xrefs

- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1402978bd`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x1402978bd`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x1402978d1`
- `ntoskrnl!FsRtlCurrentOplockH` at `0x1402978d1`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402976d3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402976d3`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14029768a`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14029768a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140297ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140297ac7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029793d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140297a7d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029793d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140297a7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297a31`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297ae9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297d21`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297a31`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297ae9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140297d21`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402977b4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402979f8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402977b4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402979f8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14029781d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140297a1e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14029781d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140297a1e`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140297956`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140297956`
- `ntoskrnl!ExRaiseStatus` at `0x140297cef`
- `ntoskrnl!ExRaiseStatus` at `0x140297cef`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402979bd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402979bd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140297a96`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140297a96`

## pseudocode

```c

```
