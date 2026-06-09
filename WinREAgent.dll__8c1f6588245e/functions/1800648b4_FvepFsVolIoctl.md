# FvepFsVolIoctl

- ea: `0x1800648b4`
- end: `0x1800649d9`
- name: `FvepFsVolIoctl`
- size: `293`
- prototype: `__int64 __usercall@<rax>(DWORD dwIoControlCode@<ecx>, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpBytesReturned, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180064a28`

## callees

- `0x1800648b4`
- `0x180064f44`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800649c4`
- `KERNEL32!CloseHandle` at `0x1800649c4`
- `KERNEL32!GetLastError` at `0x180064951`
- `KERNEL32!GetLastError` at `0x1800649a6`
- `KERNEL32!GetLastError` at `0x180064951`
- `KERNEL32!GetLastError` at `0x1800649a6`
- `KERNEL32!CreateFileW` at `0x180064942`
- `KERNEL32!CreateFileW` at `0x180064942`
- `KERNEL32!DeviceIoControl` at `0x18006499c`
- `KERNEL32!DeviceIoControl` at `0x18006499c`

## pseudocode

```c

```
