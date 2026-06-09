# CFspFileSystemOperations::ClearReadOnly(void *)

- ea: `0x1801119ac`
- end: `0x180111b43`
- name: `?ClearReadOnly@CFspFileSystemOperations@@SAJPEAX@Z`
- size: `407`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18010e084`
- `0x18010fd2c`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x1801119ac`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180111a99`
- `ntdll!NtQueryInformationFile` at `0x180111a99`
- `ntdll!NtSetInformationFile` at `0x180111af4`
- `ntdll!NtSetInformationFile` at `0x180111af4`

## string_xrefs

- `0x180111a2b`: `CFspFileSystemOperations::ClearReadOnly`

## pseudocode

```c

```
