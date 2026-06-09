# GetSerialNumberForDiskByNumberAlloc(uchar * *,unsigned __int64 *,ulong)

- ea: `0x180216bec`
- end: `0x180216e59`
- name: `?GetSerialNumberForDiskByNumberAlloc@@YAJPEAPEAEPEA_KK@Z`
- size: `621`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18021709c`

## callees

- `0x180008570`
- `0x18000a927`
- `0x180011d94`
- `0x180216bec`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180216dab`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180216dab`
- `KERNEL32!DeviceIoControl` at `0x180216ce2`
- `KERNEL32!DeviceIoControl` at `0x180216d69`
- `KERNEL32!DeviceIoControl` at `0x180216ce2`
- `KERNEL32!DeviceIoControl` at `0x180216d69`
- `KERNEL32!CreateFileW` at `0x180216c6d`
- `KERNEL32!CreateFileW` at `0x180216c6d`
- `KERNEL32!GetProcessHeap` at `0x180216d20`
- `KERNEL32!GetProcessHeap` at `0x180216db9`
- `KERNEL32!GetProcessHeap` at `0x180216e1c`
- `KERNEL32!GetProcessHeap` at `0x180216d20`
- `KERNEL32!GetProcessHeap` at `0x180216db9`
- `KERNEL32!GetProcessHeap` at `0x180216e1c`
- `KERNEL32!HeapAlloc` at `0x180216d2e`
- `KERNEL32!HeapAlloc` at `0x180216dc7`
- `KERNEL32!HeapAlloc` at `0x180216d2e`
- `KERNEL32!HeapAlloc` at `0x180216dc7`
- `KERNEL32!CloseHandle` at `0x180216e11`
- `KERNEL32!CloseHandle` at `0x180216e11`
- `KERNEL32!GetLastError` at `0x180216c7c`
- `KERNEL32!GetLastError` at `0x180216cec`
- `KERNEL32!GetLastError` at `0x180216c7c`
- `KERNEL32!GetLastError` at `0x180216cec`
- `KERNEL32!HeapFree` at `0x180216e2a`
- `KERNEL32!HeapFree` at `0x180216e2a`

## pseudocode

```c

```
