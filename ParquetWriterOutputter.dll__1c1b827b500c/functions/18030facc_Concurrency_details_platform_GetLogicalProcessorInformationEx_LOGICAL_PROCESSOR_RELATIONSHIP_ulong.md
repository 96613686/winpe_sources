# Concurrency::details::platform::__GetLogicalProcessorInformationEx(_LOGICAL_PROCESSOR_RELATIONSHIP,ulong *)

- ea: `0x18030facc`
- end: `0x18030fc12`
- name: `?__GetLogicalProcessorInformationEx@platform@details@Concurrency@@YAPEAU_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX@@W4_LOGICAL_PROCESSOR_RELATIONSHIP@@PEAK@Z`
- size: `326`
- prototype: `struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *__fastcall(Concurrency::details::platform *__hidden this, enum _LOGICAL_PROCESSOR_RELATIONSHIP, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180312ba0`

## callees

- `0x1800370f0`
- `0x18030facc`
- `0x1803104c8`
- `0x18032b080`
- `0x180339dd0`
- `0x180358070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18030fb17`
- `KERNEL32!GetLastError` at `0x18030fb66`
- `KERNEL32!GetLastError` at `0x18030fb96`
- `KERNEL32!GetLastError` at `0x18030fbe2`
- `KERNEL32!GetLastError` at `0x18030fb17`
- `KERNEL32!GetLastError` at `0x18030fb66`
- `KERNEL32!GetLastError` at `0x18030fb96`
- `KERNEL32!GetLastError` at `0x18030fbe2`
- `KERNEL32!GetProcAddress` at `0x18030fafc`
- `KERNEL32!GetProcAddress` at `0x18030fafc`
- `KERNEL32!GetModuleHandleW` at `0x18030faec`
- `KERNEL32!GetModuleHandleW` at `0x18030faec`

## string_xrefs

- `0x18030fae5`: `kernel32.dll`

## pseudocode

```c

```
