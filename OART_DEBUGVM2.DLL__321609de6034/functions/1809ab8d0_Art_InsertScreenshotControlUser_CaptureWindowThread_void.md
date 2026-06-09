# Art::InsertScreenshotControlUser::CaptureWindowThread(void *)

- ea: `0x1809ab8d0`
- end: `0x1809aba35`
- name: `?CaptureWindowThread@InsertScreenshotControlUser@Art@@SAKPEAX@Z`
- size: `357`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000ee3c`
- `0x18000eea8`
- `0x1809ab8d0`

## import_xrefs

- `KERNEL32!Sleep` at `0x1809ab993`
- `KERNEL32!Sleep` at `0x1809ab993`
- `KERNEL32!ExitThread` at `0x1809aba2e`
- `KERNEL32!ExitThread` at `0x1809aba2e`
- `GDI32!BitBlt` at `0x1809aba1d`
- `GDI32!BitBlt` at `0x1809aba1d`
- `USER32!PrintWindow` at `0x1809ab9a6`
- `USER32!PrintWindow` at `0x1809ab9a6`
- `USER32!IsIconic` at `0x1809ab9b6`
- `USER32!IsIconic` at `0x1809ab9b6`
- `USER32!SendMessageTimeoutW` at `0x1809ab97e`
- `USER32!SendMessageTimeoutW` at `0x1809ab97e`
- `USER32!GetWindowDC` at `0x1809ab9cb`
- `USER32!GetWindowDC` at `0x1809ab9cb`
- `USER32!GetWindowRect` at `0x1809ab9dc`
- `USER32!GetWindowRect` at `0x1809ab9dc`
- `USER32!RegisterWindowMessageW` at `0x1809ab933`
- `USER32!RegisterWindowMessageW` at `0x1809ab933`
- `ole32!CoUninitialize` at `0x1809aba26`
- `ole32!CoUninitialize` at `0x1809aba26`
- `ole32!CoInitialize` at `0x1809ab8ee`
- `ole32!CoInitialize` at `0x1809ab8ee`

## pseudocode

```c

```
