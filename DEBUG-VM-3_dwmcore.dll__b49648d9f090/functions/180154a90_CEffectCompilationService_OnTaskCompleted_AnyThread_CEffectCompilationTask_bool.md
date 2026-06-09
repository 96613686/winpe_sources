# CEffectCompilationService::OnTaskCompleted_AnyThread(CEffectCompilationTask *,bool)

- ea: `0x180154a90`
- end: `0x180154b47`
- name: `?OnTaskCompleted_AnyThread@CEffectCompilationService@@AEAAXPEAVCEffectCompilationTask@@_N@Z`
- size: `183`
- prototype: `void __fastcall(CEffectCompilationService *__hidden this, struct CEffectCompilationTask *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801548e4`
- `0x180242368`

## callees

- `0x180154a90`
- `0x180155828`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180154b27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180154b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180154aa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180154aa9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180154b19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180154b19`

## pseudocode

```c

```
