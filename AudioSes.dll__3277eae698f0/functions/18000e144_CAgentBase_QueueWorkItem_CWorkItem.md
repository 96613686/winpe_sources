# CAgentBase::QueueWorkItem(CWorkItem *)

- ea: `0x18000e144`
- end: `0x18000e2e1`
- name: `?QueueWorkItem@CAgentBase@@QEAA_NPEAVCWorkItem@@@Z`
- size: `413`
- prototype: `bool __fastcall(CAgentBase *__hidden this, struct CWorkItem *)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009f48`
- `0x18000dab8`
- `0x18000e100`
- `0x18000e658`
- `0x18007886c`
- `0x1800c8c24`
- `0x1800ca23c`
- `0x1800ca298`
- `0x1800ca2f4`

## callees

- `0x18000e144`
- `0x18000e2e8`
- `0x180078fe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e15d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e15d`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000e221`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000e221`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e234`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e1df`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e1df`

## pseudocode

```c

```
