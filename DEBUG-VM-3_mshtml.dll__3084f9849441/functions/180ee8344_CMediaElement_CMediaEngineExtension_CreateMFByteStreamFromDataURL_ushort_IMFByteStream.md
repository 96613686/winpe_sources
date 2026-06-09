# CMediaElement::CMediaEngineExtension::CreateMFByteStreamFromDataURL(ushort *,IMFByteStream * *)

- ea: `0x180ee8344`
- end: `0x180ee876d`
- name: `?CreateMFByteStreamFromDataURL@CMediaEngineExtension@CMediaElement@@IEAAJPEAGPEAPEAUIMFByteStream@@@Z`
- size: `1065`
- prototype: `__int64 __fastcall(CMediaElement::CMediaEngineExtension *__hidden this, unsigned __int16 *, struct IMFByteStream **)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180ee6fd0`

## callees

- `0x1800ad370`
- `0x1801af6e0`
- `0x1801b0510`
- `0x1801bf528`
- `0x1801c0b08`
- `0x1803a9440`
- `0x18057ed34`
- `0x18072880c`
- `0x180844764`
- `0x180edce78`
- `0x180ee8344`
- `0x180f4bdb0`
- `0x180f4be34`
- `0x180f4bf34`
- `0x18105cedc`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180ee8718`
- `KERNEL32!GlobalFree` at `0x180ee8718`
- `KERNEL32!GlobalLock` at `0x180ee847e`
- `KERNEL32!GlobalLock` at `0x180ee847e`
- `KERNEL32!GlobalUnlock` at `0x180ee84cf`
- `KERNEL32!GlobalUnlock` at `0x180ee870a`
- `KERNEL32!GlobalUnlock` at `0x180ee84cf`
- `KERNEL32!GlobalUnlock` at `0x180ee870a`
- `KERNEL32!GlobalAlloc` at `0x180ee8450`
- `KERNEL32!GlobalAlloc` at `0x180ee8450`
- `KERNEL32!GetProcAddress` at `0x180ee8582`
- `KERNEL32!GetProcAddress` at `0x180ee8582`
- `KERNEL32!GetLastError` at `0x180ee8594`
- `KERNEL32!GetLastError` at `0x180ee8594`
- `KERNEL32!LeaveCriticalSection` at `0x180ee83b7`
- `KERNEL32!LeaveCriticalSection` at `0x180ee83ce`
- `KERNEL32!LeaveCriticalSection` at `0x180ee86a3`
- `KERNEL32!LeaveCriticalSection` at `0x180ee86ab`
- `KERNEL32!LeaveCriticalSection` at `0x180ee83b7`
- `KERNEL32!LeaveCriticalSection` at `0x180ee83ce`
- `KERNEL32!LeaveCriticalSection` at `0x180ee86a3`
- `KERNEL32!LeaveCriticalSection` at `0x180ee86ab`
- `KERNEL32!EnterCriticalSection` at `0x180ee837c`
- `KERNEL32!EnterCriticalSection` at `0x180ee8685`
- `KERNEL32!EnterCriticalSection` at `0x180ee837c`
- `KERNEL32!EnterCriticalSection` at `0x180ee8685`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x180ee84ed`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x180ee84ed`

## string_xrefs

- `0x180ee83a1`: `MF_E_SHUTDOWN in create byte stream from data URL.`
- `0x180ee8737`: `new data protocol failed in create byte stream from data URL.`
- `0x180ee8426`: `SetUrl failed in create byte stream from data URL.`
- `0x180ee8472`: `GlobalAlloc failed in create byte stream from data URL.`
- `0x180ee84a0`: `GlobalLock failed in create byte stream from data URL.`
- `0x180ee850d`: `CreateStreamOnHGlobal failed in create byte stream from data URL.`
- `0x180ee85da`: `MFCreateMFByteStreamOnStream failed in create byte stream from data URL.`
- `0x180ee857b`: `MFCreateMFByteStreamOnStream`

## pseudocode

```c

```
