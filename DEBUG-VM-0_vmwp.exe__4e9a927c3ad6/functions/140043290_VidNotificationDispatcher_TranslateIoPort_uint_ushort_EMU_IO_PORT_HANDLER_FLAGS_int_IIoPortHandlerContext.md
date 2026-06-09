# VidNotificationDispatcher::TranslateIoPort(uint,ushort,EMU_IO_PORT_HANDLER_FLAGS,int,IIoPortHandlerContext * *)

- ea: `0x140043290`
- end: `0x14004359a`
- name: `?TranslateIoPort@VidNotificationDispatcher@@UEAAJIGW4EMU_IO_PORT_HANDLER_FLAGS@@HPEAPEAUIIoPortHandlerContext@@@Z`
- size: `778`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140043144`
- `0x14027abb0`

## callees

- `0x140043290`
- `0x14009d7ac`
- `0x140132940`
- `0x1401ec090`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004332b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004332b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400432fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400432fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043495`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400434c9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400434c9`
- `vid!VidCheckForIoIntercept` at `0x14004354e`
- `vid!VidCheckForIoIntercept` at `0x14004354e`

## string_xrefs

- `0x140043501`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```
