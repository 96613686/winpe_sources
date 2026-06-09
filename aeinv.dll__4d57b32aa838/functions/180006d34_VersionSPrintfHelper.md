# VersionSPrintfHelper

- ea: `0x180006d34`
- end: `0x1800071cf`
- name: `VersionSPrintfHelper`
- size: `1179`
- prototype: `__int64 __usercall@<rax>(wchar_t *Buffer@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180005624`

## callees

- `0x180006d34`
- `0x1800071d8`
- `0x1800074c0`
- `0x180015eec`
- `0x180029148`
- `0x180059920`
- `0x18005a934`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180006d9c`
- `KERNEL32!GetProcessHeap` at `0x180006d9c`
- `KERNEL32!HeapAlloc` at `0x180006dc0`
- `KERNEL32!HeapAlloc` at `0x180006dc0`
- `KERNEL32!HeapFree` at `0x180006e86`
- `KERNEL32!HeapFree` at `0x180006e86`

## string_xrefs

- `0x180006fac`: `Service Pack %d`

## pseudocode

```c

```
