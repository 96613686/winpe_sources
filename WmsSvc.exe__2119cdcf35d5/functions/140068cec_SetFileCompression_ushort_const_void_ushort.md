# SetFileCompression(ushort const *,void *,ushort)

- ea: `0x140068cec`
- end: `0x140068eb5`
- name: `?SetFileCompression@@YAJPEBGPEAXG@Z`
- size: `457`
- prototype: `int(const unsigned __int16 *, void *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ce14`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140068cec`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140068d0f`
- `KERNEL32!GetFileAttributesW` at `0x140068d0f`
- `KERNEL32!DeviceIoControl` at `0x140068e06`
- `KERNEL32!DeviceIoControl` at `0x140068e06`
- `KERNEL32!GetLastError` at `0x140068d17`
- `KERNEL32!GetLastError` at `0x140068e14`
- `KERNEL32!GetLastError` at `0x140068d17`
- `KERNEL32!GetLastError` at `0x140068e14`
- `KERNEL32!IsDebuggerPresent` at `0x140068d6d`
- `KERNEL32!IsDebuggerPresent` at `0x140068e6b`
- `KERNEL32!IsDebuggerPresent` at `0x140068d6d`
- `KERNEL32!IsDebuggerPresent` at `0x140068e6b`

## string_xrefs

- `0x140068d4a`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068e3e`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068d40`: `SetFileCompression`
- `0x140068e37`: `SetFileCompression`

## pseudocode

```c

```
