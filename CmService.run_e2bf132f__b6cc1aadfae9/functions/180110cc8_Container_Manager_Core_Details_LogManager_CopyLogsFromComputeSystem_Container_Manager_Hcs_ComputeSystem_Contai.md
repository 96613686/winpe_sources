# Container::Manager::Core::Details::LogManager::CopyLogsFromComputeSystem(Container::Manager::Hcs::ComputeSystem &,Container::Manager::Agent::Client::CmAgentConnection &,bool,utl::optional<Csl::Path>)

- ea: `0x180110cc8`
- end: `0x180111783`
- name: `?CopyLogsFromComputeSystem@LogManager@Details@Core@Manager@Container@@QEAAJAEAVComputeSystem@Hcs@45@AEAVCmAgentConnection@Client@Agent@45@_NV?$optional@VPath@Csl@@@utl@@@Z`
- size: `2747`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, Container::Manager::Hcs::ComputeSystem *this@<rdx>, __int64)`
- caller_count: `10`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066ed8`
- `0x18009c770`
- `0x18009d108`
- `0x18009d4fc`
- `0x1800a64d0`
- `0x1800a6be0`
- `0x1800adf44`
- `0x1800e0c8c`
- `0x1800e5600`
- `0x1800efc88`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x180008bf0`
- `0x18000da88`
- `0x180016718`
- `0x180016774`
- `0x18002fae4`
- `0x18002fc34`
- `0x18002fd88`
- `0x180030058`
- `0x180031d3c`
- `0x1800785d4`
- `0x180097924`
- `0x1800ba8a4`
- `0x180110cc8`
- `0x180123250`
- `0x180123878`
- `0x180125384`
- `0x18019320c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180110cf0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180110cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180110dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180110e95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180111101`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801115b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180111746`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180110dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180110e95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180111101`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801115b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180111746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180110cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180110cfc`

## string_xrefs

- `0x180111015`: `C:\Windows\Temp\CMLogs`

## pseudocode

```c

```
