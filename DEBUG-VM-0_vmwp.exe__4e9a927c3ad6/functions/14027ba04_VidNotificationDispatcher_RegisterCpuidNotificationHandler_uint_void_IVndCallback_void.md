# VidNotificationDispatcher::RegisterCpuidNotificationHandler(uint,void *,IVndCallback &,void * &)

- ea: `0x14027ba04`
- end: `0x14027bbd1`
- name: `?RegisterCpuidNotificationHandler@VidNotificationDispatcher@@QEAAJIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `461`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct IVndCallback *@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140279650`

## callees

- `0x140040fd8`
- `0x140041a3c`
- `0x140042240`
- `0x1400549dc`
- `0x140078c98`
- `0x14009d7ac`
- `0x1400db3f0`
- `0x14027b4a0`
- `0x14027ba04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027baa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027baa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bb34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027ba2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027ba2d`
- `vid!VidRegisterCpuidHandler` at `0x14027bb24`
- `vid!VidRegisterCpuidHandler` at `0x14027bb24`

## string_xrefs

- `0x14027bbbf`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```
