# Container::Manager::Core::Details::HostIdleMonitor::CheckStopHostIdleSubscription(Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800d3368`
- end: `0x1800d34bc`
- name: `?CheckStopHostIdleSubscription@HostIdleMonitor@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d3568`
- `0x1800d3670`

## callees

- `0x180043bfc`
- `0x1800d3368`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800d34a6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800d34a6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800d3395`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800d3395`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d3443`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d3443`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d33ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d3477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d3492`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d33ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d3477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d3492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3406`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3425`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d33a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d344f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d33a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d344f`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x1800d3417`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x1800d3417`

## pseudocode

```c

```
