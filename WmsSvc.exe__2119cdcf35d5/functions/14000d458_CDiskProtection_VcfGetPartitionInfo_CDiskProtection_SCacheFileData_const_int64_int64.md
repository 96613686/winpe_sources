# CDiskProtection::VcfGetPartitionInfo(CDiskProtection::SCacheFileData const *,__int64 *,__int64 *)

- ea: `0x14000d458`
- end: `0x14000d76a`
- name: `?VcfGetPartitionInfo@CDiskProtection@@IEAAJPEBUSCacheFileData@1@PEA_J1@Z`
- size: `786`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this, const struct CDiskProtection::SCacheFileData *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000c87c`

## callees

- `0x14000d458`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000d73a`
- `KERNEL32!CloseHandle` at `0x14000d73a`
- `KERNEL32!CreateFileW` at `0x14000d511`
- `KERNEL32!CreateFileW` at `0x14000d511`
- `KERNEL32!DeviceIoControl` at `0x14000d611`
- `KERNEL32!DeviceIoControl` at `0x14000d65e`
- `KERNEL32!DeviceIoControl` at `0x14000d611`
- `KERNEL32!DeviceIoControl` at `0x14000d65e`
- `KERNEL32!GetLastError` at `0x14000d524`
- `KERNEL32!GetLastError` at `0x14000d66c`
- `KERNEL32!GetLastError` at `0x14000d524`
- `KERNEL32!GetLastError` at `0x14000d66c`
- `KERNEL32!IsDebuggerPresent` at `0x14000d57f`
- `KERNEL32!IsDebuggerPresent` at `0x14000d6c7`
- `KERNEL32!IsDebuggerPresent` at `0x14000d57f`
- `KERNEL32!IsDebuggerPresent` at `0x14000d6c7`

## pseudocode

```c

```
