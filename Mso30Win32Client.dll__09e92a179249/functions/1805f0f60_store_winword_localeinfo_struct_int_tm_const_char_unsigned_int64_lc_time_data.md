# _store_winword(localeinfo_struct *,int,tm const *,char * *,unsigned __int64 *,__lc_time_data *)

- ea: `0x1805f0f60`
- end: `0x1805f12cd`
- name: `?_store_winword@@YAHPEAUlocaleinfo_struct@@HPEBUtm@@PEAPEADPEA_KPEAU__lc_time_data@@@Z`
- size: `877`
- prototype: `__int64 __fastcall(struct localeinfo_struct *, UINT Msg, WPARAM wParam, LPARAM lParam, unsigned __int64 *, struct __lc_time_data *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180044ad0`
- `0x18009c710`
- `0x180192520`
- `0x180192560`
- `0x1805f0f60`
- `0x1805f12d0`
- `0x18077cec4`
- `0x18087810c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1805f111c`
- `KERNEL32!GlobalAlloc` at `0x1805f111c`
- `KERNEL32!GlobalLock` at `0x1805f112d`
- `KERNEL32!GlobalLock` at `0x1805f112d`
- `KERNEL32!GlobalUnlock` at `0x1805f1152`
- `KERNEL32!GlobalUnlock` at `0x1805f1152`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1805f109d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1805f109d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1805f1230`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1805f128f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1805f1230`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1805f128f`
- `ole32!CreateStreamOnHGlobal` at `0x1805f1164`
- `ole32!CreateStreamOnHGlobal` at `0x1805f1164`
- `ole32!OleInitialize` at `0x1805f1039`
- `ole32!OleInitialize` at `0x1805f1039`
- `ole32!OleUninitialize` at `0x1805f102c`
- `ole32!OleUninitialize` at `0x1805f102c`
- `OLEAUT32!__imp_SysFreeString` at `0x1805f1202`
- `OLEAUT32!__imp_SysFreeString` at `0x1805f1266`
- `OLEAUT32!__imp_SysFreeString` at `0x1805f1202`
- `OLEAUT32!__imp_SysFreeString` at `0x1805f1266`
- `USER32!DefWindowProcW` at `0x1805f12a1`
- `USER32!DefWindowProcW` at `0x1805f12a1`
- `USER32!GetWindowTextW` at `0x1805f10d4`
- `USER32!GetWindowTextW` at `0x1805f10d4`
- `USER32!GetWindowTextLengthW` at `0x1805f1042`
- `USER32!GetWindowTextLengthW` at `0x1805f1042`
- `USER32!SetWindowLongPtrW` at `0x1805f1247`
- `USER32!SetWindowLongPtrW` at `0x1805f1247`
- `USER32!GetWindowLongPtrW` at `0x1805f100e`
- `USER32!GetWindowLongPtrW` at `0x1805f100e`
- `USER32!GetWindowLongW` at `0x1805f0fd6`
- `USER32!GetWindowLongW` at `0x1805f0fee`
- `USER32!GetWindowLongW` at `0x1805f0fd6`
- `USER32!GetWindowLongW` at `0x1805f0fee`
- `USER32!SetWindowLongW` at `0x1805f0ffe`
- `USER32!SetWindowLongW` at `0x1805f0ffe`
- `USER32!SetWindowTextW` at `0x1805f10e4`
- `USER32!SetWindowTextW` at `0x1805f10e4`

## pseudocode

```c

```
