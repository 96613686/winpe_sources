# UtilMarkFileForDelete(void *,ulong)

- ea: `0x180098b38`
- end: `0x180098c0a`
- name: `?UtilMarkFileForDelete@@YAXPEAXK@Z`
- size: `210`
- prototype: `void __fastcall(HANDLE FileHandle, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003b590`
- `0x18007d258`

## callees

- `0x180050db0`
- `0x180098b38`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180098b89`
- `ntdll!NtQueryInformationFile` at `0x180098b89`
- `ntdll!NtSetInformationFile` at `0x180098bc4`
- `ntdll!NtSetInformationFile` at `0x180098be7`
- `ntdll!NtSetInformationFile` at `0x180098bc4`
- `ntdll!NtSetInformationFile` at `0x180098be7`

## pseudocode

```c

```
