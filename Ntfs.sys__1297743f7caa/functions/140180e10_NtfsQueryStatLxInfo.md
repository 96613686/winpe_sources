# NtfsQueryStatLxInfo

- ea: `0x140180e10`
- end: `0x1401815d0`
- name: `NtfsQueryStatLxInfo`
- size: `1984`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64, DWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14017ba70`
- `0x140182310`
- `0x140182c80`

## callees

- `0x140025a40`
- `0x140059740`
- `0x14017eeb8`
- `0x14017f8c0`
- `0x140180e10`
- `0x1401815d8`
- `0x14018a8a0`
- `0x1401ba674`

## import_xrefs

- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401810d2`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401810d2`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140181542`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140181542`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018115f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018115f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401811a0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401811a0`
- `ntoskrnl!SeAccessCheck` at `0x1401811ef`
- `ntoskrnl!SeAccessCheck` at `0x1401811ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140181194`
- `ntoskrnl!ExReleasePushLockEx` at `0x140181194`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140180ea9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140180ea9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018137f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140181439`
- `ntoskrnl!ExReleaseResourceLite` at `0x140181591`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aa69e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018137f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140181439`
- `ntoskrnl!ExReleaseResourceLite` at `0x140181591`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aa69e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140181343`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401813fd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140181343`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401813fd`

## pseudocode

```c

```
