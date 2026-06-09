# Art::InsertScreenshotControlUser::CaptureWindowThread(void *)

- ea: `0x1809a1660`
- end: `0x1809a17c5`
- name: `?CaptureWindowThread@InsertScreenshotControlUser@Art@@SAKPEAX@Z`
- size: `357`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180059bd4`
- `0x180059c40`
- `0x1809a1660`

## import_xrefs

- `KERNEL32!Sleep` at `0x1809a1723`
- `KERNEL32!Sleep` at `0x1809a1723`
- `KERNEL32!ExitThread` at `0x1809a17be`
- `KERNEL32!ExitThread` at `0x1809a17be`
- `GDI32!BitBlt` at `0x1809a17ad`
- `GDI32!BitBlt` at `0x1809a17ad`
- `USER32!PrintWindow` at `0x1809a1736`
- `USER32!PrintWindow` at `0x1809a1736`
- `USER32!IsIconic` at `0x1809a1746`
- `USER32!IsIconic` at `0x1809a1746`
- `USER32!SendMessageTimeoutW` at `0x1809a170e`
- `USER32!SendMessageTimeoutW` at `0x1809a170e`
- `USER32!GetWindowDC` at `0x1809a175b`
- `USER32!GetWindowDC` at `0x1809a175b`
- `USER32!GetWindowRect` at `0x1809a176c`
- `USER32!GetWindowRect` at `0x1809a176c`
- `USER32!RegisterWindowMessageW` at `0x1809a16c3`
- `USER32!RegisterWindowMessageW` at `0x1809a16c3`
- `ole32!CoUninitialize` at `0x1809a17b6`
- `ole32!CoUninitialize` at `0x1809a17b6`
- `ole32!CoInitialize` at `0x1809a167e`
- `ole32!CoInitialize` at `0x1809a167e`

## pseudocode

```c

```
