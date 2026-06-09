# VidNotificationDispatcher::RegisterMemoryBlockNotificationHandler(void *,int,void *,IVndCallback &,void * &)

- ea: `0x14003ff24`
- end: `0x140040212`
- name: `?RegisterMemoryBlockNotificationHandler@VidNotificationDispatcher@@QEAAJPEAXH0AEAUIVndCallback@@AEAPEAX@Z`
- size: `750`
- prototype: `__int64 __fastcall(VidNotificationDispatcher *__hidden this, void *, int, void *, struct IVndCallback *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003f470`

## callees

- `0x140021d00`
- `0x14002437c`
- `0x14003ff24`
- `0x140040fd8`
- `0x140041a3c`
- `0x140042240`
- `0x1400549dc`
- `0x140078c98`
- `0x140096740`
- `0x14009d7ac`
- `0x140132d30`
- `0x1401335fc`
- `0x14027b4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003ff88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003ff88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004002c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004002c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003ff4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003ff4d`
- `vid!VidSetMemoryBlockNotificationQueue` at `0x14003ffb5`
- `vid!VidSetMemoryBlockNotificationQueue` at `0x14003ffb5`

## string_xrefs

- `0x140040200`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```
