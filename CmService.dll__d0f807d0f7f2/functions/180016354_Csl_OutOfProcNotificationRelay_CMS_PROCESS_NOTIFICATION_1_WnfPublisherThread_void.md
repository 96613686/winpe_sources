# Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::WnfPublisherThread(void)

- ea: `0x180016354`
- end: `0x18001653a`
- name: `?WnfPublisherThread@?$OutOfProcNotificationRelay@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@AEAAXXZ`
- size: `486`
- prototype: `__int64 __fastcall(PCONDITION_VARIABLE ConditionVariable)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016540`

## callees

- `0x18000a10c`
- `0x180016354`
- `0x180016718`

## import_xrefs

- `ntdll!RtlWaitForWnfMetaNotification` at `0x1800163d7`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x1800163d7`
- `ntdll!RtlPublishWnfStateData` at `0x1800164b3`
- `ntdll!RtlPublishWnfStateData` at `0x1800164b3`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001641b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001641b`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18001648d`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18001648d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001636d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800163fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001636d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800163fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001639a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001647d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800164f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001639a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001647d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800164f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001642f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001642f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800163a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800163a8`

## string_xrefs

- `0x180016516`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
