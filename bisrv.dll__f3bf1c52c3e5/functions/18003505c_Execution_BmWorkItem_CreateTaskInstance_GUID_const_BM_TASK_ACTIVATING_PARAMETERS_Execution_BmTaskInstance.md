# Execution::BmWorkItem::CreateTaskInstance(_GUID const &,_BM_TASK_ACTIVATING_PARAMETERS *,Execution::BmTaskInstance * *)

- ea: `0x18003505c`
- end: `0x180035391`
- name: `?CreateTaskInstance@BmWorkItem@Execution@@QEAAJAEBU_GUID@@PEAU_BM_TASK_ACTIVATING_PARAMETERS@@PEAPEAVBmTaskInstance@2@@Z`
- size: `821`
- prototype: `__int64 __fastcall(Execution::BmWorkItem *__hidden this, const struct _GUID *, struct _BM_TASK_ACTIVATING_PARAMETERS *, struct Execution::BmTaskInstance **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180067330`

## callees

- `0x18001d4b0`
- `0x18001ef7c`
- `0x1800207dc`
- `0x1800223e0`
- `0x18003505c`
- `0x18003558c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800350a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800350a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800351e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003534b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035362`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800351e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003534b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035362`

## string_xrefs

- `0x1800351ca`: `Task instance {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} already present for work item {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180035283`: `Unable to allocate task instance for work item {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180035324`: `Unable to insert task instance into task instance list for id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`

## pseudocode

```c

```
