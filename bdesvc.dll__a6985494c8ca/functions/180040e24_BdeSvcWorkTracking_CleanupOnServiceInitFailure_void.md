# BdeSvcWorkTracking::CleanupOnServiceInitFailure(void)

- ea: `0x180040e24`
- end: `0x180040f1a`
- name: `?CleanupOnServiceInitFailure@BdeSvcWorkTracking@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180045640`

## callees

- `0x180009f30`
- `0x180040e24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040e67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040e67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ebe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ebe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180040e94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180040e94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180040e7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180040e7a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040ea8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040ea8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040ed6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040ed6`

## pseudocode

```c

```
