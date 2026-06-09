# _store_winword(localeinfo_struct *,int,tm const *,char * *,unsigned __int64 *,__lc_time_data *)

- ea: `0x180874c60`
- end: `0x180874f97`
- name: `?_store_winword@@YAHPEAUlocaleinfo_struct@@HPEBUtm@@PEAPEADPEA_KPEAU__lc_time_data@@@Z_0`
- size: `823`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam, unsigned __int64 *, struct __lc_time_data *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180044ad0`
- `0x18009c710`
- `0x180192520`
- `0x180192560`
- `0x18077cec4`
- `0x180874c60`
- `0x18087810c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x180874e1c`
- `KERNEL32!GlobalAlloc` at `0x180874e1c`
- `KERNEL32!GlobalLock` at `0x180874e2d`
- `KERNEL32!GlobalLock` at `0x180874e2d`
- `KERNEL32!GlobalUnlock` at `0x180874e52`
- `KERNEL32!GlobalUnlock` at `0x180874e52`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180874d9d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180874d9d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180874f03`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180874f59`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180874f03`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180874f59`
- `ole32!CreateStreamOnHGlobal` at `0x180874e64`
- `ole32!CreateStreamOnHGlobal` at `0x180874e64`
- `ole32!OleInitialize` at `0x180874d39`
- `ole32!OleInitialize` at `0x180874d39`
- `ole32!OleUninitialize` at `0x180874d2c`
- `ole32!OleUninitialize` at `0x180874d2c`
- `USER32!DefWindowProcW` at `0x180874f6b`
- `USER32!DefWindowProcW` at `0x180874f6b`
- `USER32!GetWindowTextW` at `0x180874dd4`
- `USER32!GetWindowTextW` at `0x180874dd4`
- `USER32!GetWindowTextLengthW` at `0x180874d42`
- `USER32!GetWindowTextLengthW` at `0x180874d42`
- `USER32!SetWindowLongPtrW` at `0x180874f1a`
- `USER32!SetWindowLongPtrW` at `0x180874f1a`
- `USER32!GetWindowLongPtrW` at `0x180874d0e`
- `USER32!GetWindowLongPtrW` at `0x180874d0e`
- `USER32!GetWindowLongW` at `0x180874cd6`
- `USER32!GetWindowLongW` at `0x180874cee`
- `USER32!GetWindowLongW` at `0x180874cd6`
- `USER32!GetWindowLongW` at `0x180874cee`
- `USER32!SetWindowLongW` at `0x180874cfe`
- `USER32!SetWindowLongW` at `0x180874cfe`
- `USER32!SetWindowTextW` at `0x180874de4`
- `USER32!SetWindowTextW` at `0x180874de4`

## pseudocode

```c

```
