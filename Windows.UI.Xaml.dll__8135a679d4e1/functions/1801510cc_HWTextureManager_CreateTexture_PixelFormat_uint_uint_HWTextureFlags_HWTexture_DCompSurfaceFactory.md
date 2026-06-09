# HWTextureManager::CreateTexture(PixelFormat,uint,uint,HWTextureFlags,HWTexture * *,DCompSurfaceFactory *)

- ea: `0x1801510cc`
- end: `0x18015180e`
- name: `?CreateTexture@HWTextureManager@@QEAAJW4PixelFormat@@IIW4HWTextureFlags@@PEAPEAVHWTexture@@PEAVDCompSurfaceFactory@@@Z`
- size: `1858`
- prototype: `HRESULT __fastcall(HWTextureManager *this, PixelFormat pixelFormat, unsigned int widthWithoutGutters, unsigned int heightWithoutGutters, HWTextureFlags flags, HWTexture **ppTexture, DCompSurfaceFactory *pChildDevice)`
- caller_count: `9`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1801546b0`
- `0x1801bf6d8`
- `0x1803cc9e0`
- `0x1805f3334`
- `0x180656e58`
- `0x1806cb8fc`
- `0x180786108`
- `0x1807aee18`
- `0x180a17a00`

## callees

- `0x180004bc0`
- `0x180004d2c`
- `0x180070c4c`
- `0x180131190`
- `0x180150504`
- `0x180150a10`
- `0x180150c90`
- `0x180150f60`
- `0x1801510cc`
- `0x180151cbc`
- `0x1801a2b20`
- `0x1801df610`
- `0x180275e6c`
- `0x1802f36bc`
- `0x1806877a8`
- `0x180687890`
- `0x1806f7b00`
- `0x18070696c`
- `0x18076e59c`
- `0x18076e7fc`
- `0x18076e864`
- `0x1809e38b4`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180151199`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180151199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801511a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801511a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180151790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801517fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180151790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801517fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180151253`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18015137d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180151253`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18015137d`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180151541`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180151552`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180151541`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180151552`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18015174a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18015174a`

## pseudocode

```c

```
