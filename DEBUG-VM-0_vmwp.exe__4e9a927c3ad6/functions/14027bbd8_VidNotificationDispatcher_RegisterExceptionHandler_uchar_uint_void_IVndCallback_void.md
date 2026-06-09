# VidNotificationDispatcher::RegisterExceptionHandler(uchar,uint,void *,IVndCallback &,void * &)

- ea: `0x14027bbd8`
- end: `0x14027bdb2`
- name: `?RegisterExceptionHandler@VidNotificationDispatcher@@QEAAJEIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `474`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, void *@<r9>, struct IVndCallback *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402796c0`

## callees

- `0x140040fd8`
- `0x140041a3c`
- `0x140042240`
- `0x1400549dc`
- `0x140078c98`
- `0x14009d7ac`
- `0x1400db3f0`
- `0x14027b4a0`
- `0x14027bbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bc79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bd15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bc79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bd15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bc01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bc01`
- `vid!VidRegisterExceptionHandler` at `0x14027bd05`
- `vid!VidRegisterExceptionHandler` at `0x14027bd05`

## string_xrefs

- `0x14027bda0`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```
