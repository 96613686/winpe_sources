# CFspCloudFileSystemOperations::ClearReadOnly(void *)

- ea: `0x180098914`
- end: `0x180098abe`
- name: `?ClearReadOnly@CFspCloudFileSystemOperations@@SAJPEAX@Z`
- size: `426`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180090710`
- `0x1800908d8`
- `0x1800942b0`
- `0x1800950b4`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180098914`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180098a0e`
- `ntdll!NtQueryInformationFile` at `0x180098a0e`
- `ntdll!NtSetInformationFile` at `0x180098a6c`
- `ntdll!NtSetInformationFile` at `0x180098a6c`

## string_xrefs

- `0x18009899d`: `CFspCloudFileSystemOperations::ClearReadOnly`

## pseudocode

```c

```
