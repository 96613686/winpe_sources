# Container::Manager::Core::Details::ContainerObject::MapHostDriverStoresToContainer(Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800a3768`
- end: `0x1800a3b44`
- name: `?MapHostDriverStoresToContainer@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, PSRWLOCK *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800b8344`
- `0x1800b9814`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x180016718`
- `0x18002fc34`
- `0x180049508`
- `0x1800785d4`
- `0x1800982a8`
- `0x18009970c`
- `0x18009e154`
- `0x1800a3768`
- `0x1800a4b20`
- `0x1800b8d48`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x1800a3943`
- `ntdll!RtlDoesFileExists_U` at `0x1800a3943`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a37fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a37fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a37c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a382f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a384a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a37c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a382f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a384a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3808`
- `drvstore!DriverStoreEnumNodesW` at `0x1800a37e4`
- `drvstore!DriverStoreEnumNodesW` at `0x1800a37e4`

## string_xrefs

- `0x1800a38ce`: `C:\Windows\System32\HostDriverStore`

## pseudocode

```c

```
