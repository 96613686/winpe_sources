# VidNotificationDispatcher::RegisterGhciInterceptHandler(uint,void *,IVndCallback &,void * &)

- ea: `0x14027bdb8`
- end: `0x14027bf85`
- name: `?RegisterGhciInterceptHandler@VidNotificationDispatcher@@QEAAJIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `461`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct IVndCallback *@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402796d0`

## callees

- `0x140040fd8`
- `0x140041a3c`
- `0x140042240`
- `0x1400549dc`
- `0x140078c98`
- `0x14009d7ac`
- `0x1400db3f0`
- `0x14027b4a0`
- `0x14027bdb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027be54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027be54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bee8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bde1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bde1`
- `vid!VidRegisterGhciInterceptHandler` at `0x14027bed8`
- `vid!VidRegisterGhciInterceptHandler` at `0x14027bed8`

## string_xrefs

- `0x14027bf73`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```
