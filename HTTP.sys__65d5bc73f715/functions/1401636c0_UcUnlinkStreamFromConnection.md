# UcUnlinkStreamFromConnection

- ea: `0x1401636c0`
- end: `0x140163800`
- name: `UcUnlinkStreamFromConnection`
- size: `320`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400c4960`

## callees

- `0x1401636c0`
- `0x140163968`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1401637bd`
- `ntoskrnl!IofCompleteRequest` at `0x1401637bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163798`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163798`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016378c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016378c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140163710`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140163710`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401636f8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401636f8`

## pseudocode

```c

```
