# BackgroundTaskScheduler::Scheduler::SignalEventOnCompletionOfCurrentTasks(void *,BackgroundTaskScheduler::SchedulingMode)

- ea: `0x1800b3684`
- end: `0x1800b383e`
- name: `?SignalEventOnCompletionOfCurrentTasks@Scheduler@BackgroundTaskScheduler@@QEAAXPEAXUSchedulingMode@2@@Z`
- size: `442`
- prototype: `void __high(void *, struct BackgroundTaskScheduler::SchedulingMode)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fa870`

## callees

- `0x18000ac20`
- `0x18000be34`
- `0x180013140`
- `0x1800148b4`
- `0x18004dc60`
- `0x1800688f4`
- `0x1800b3684`
- `0x1800b3844`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b3763`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b3763`
- `msvcp_win!_Cnd_signal` at `0x1800b37f6`
- `msvcp_win!_Cnd_signal` at `0x1800b37f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b3801`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b3801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b36f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b36f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b36f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b36f9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b3724`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b3724`

## pseudocode

```c

```
