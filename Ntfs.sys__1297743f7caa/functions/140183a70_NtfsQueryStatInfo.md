# NtfsQueryStatInfo

- ea: `0x140183a70`
- end: `0x14018420c`
- name: `NtfsQueryStatInfo`
- size: `1948`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64, __int64, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14017ba70`
- `0x140182310`
- `0x140182c80`

## callees

- `0x140025a40`
- `0x140059740`
- `0x14017e510`
- `0x140183a70`
- `0x14018a8a0`
- `0x1401ba674`

## import_xrefs

- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140183e61`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140183e61`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140184199`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140184199`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140183d5e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140183d5e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140183da0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140183da0`
- `ntoskrnl!SeAccessCheck` at `0x140183dee`
- `ntoskrnl!SeAccessCheck` at `0x140183dee`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140183e85`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140183e85`
- `ntoskrnl!ExReleasePushLockEx` at `0x140183d94`
- `ntoskrnl!ExReleasePushLockEx` at `0x140183d94`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140183afa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140183afa`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183ecf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183fd6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140184049`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401841d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aaaab`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183ecf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183fd6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140184049`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401841d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aaaab`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183ea6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183f94`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14018400d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183ea6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183f94`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14018400d`

## pseudocode

```c

```
