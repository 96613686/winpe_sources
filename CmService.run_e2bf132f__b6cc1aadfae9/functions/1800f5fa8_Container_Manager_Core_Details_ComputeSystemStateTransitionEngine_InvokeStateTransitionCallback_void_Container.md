# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::InvokeStateTransitionCallback(void (*)(Container::Manager::Core::Details::ComputeSystemState const &,long,void *),Container::Manager::Core::Details::ComputeSystemState const &,long,bool,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800f5fa8`
- end: `0x1800f6100`
- name: `?InvokeStateTransitionCallback@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@AEAAXP6AXAEBUComputeSystemState@2345@JPEAX@Z0J_NAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `344`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, char, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800f62d0`
- `0x1800f6828`
- `0x1800f69cc`
- `0x1800f6d10`

## callees

- `0x1800f5fa8`
- `0x1801b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800f5fed`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800f5fed`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800f60e5`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800f60e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f607c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f607c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f604f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f60b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f60cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f604f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f60b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f60cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f5ff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6088`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f5ff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6088`

## pseudocode

```c

```
