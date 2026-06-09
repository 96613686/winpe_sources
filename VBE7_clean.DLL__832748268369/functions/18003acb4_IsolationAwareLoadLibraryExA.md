# IsolationAwareLoadLibraryExA

- ea: `0x18003acb4`
- end: `0x18003ad4e`
- name: `IsolationAwareLoadLibraryExA`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003b2ec`
- `0x180056aa8`
- `0x18006556c`
- `0x1800a51b8`
- `0x1800b0b60`
- `0x1800b0d68`
- `0x180379244`

## callees

- `0x180001644`
- `0x18003acb4`
- `0x180379380`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003ad16`
- `KERNEL32!GetLastError` at `0x180380a32`
- `KERNEL32!GetLastError` at `0x18003ad16`
- `KERNEL32!GetLastError` at `0x180380a32`
- `KERNEL32!SetLastError` at `0x18003ad35`
- `KERNEL32!SetLastError` at `0x180380a50`
- `KERNEL32!SetLastError` at `0x18003ad35`
- `KERNEL32!SetLastError` at `0x180380a50`
- `KERNEL32!DeactivateActCtx` at `0x18003ad29`
- `KERNEL32!DeactivateActCtx` at `0x180380a44`
- `KERNEL32!DeactivateActCtx` at `0x18003ad29`
- `KERNEL32!DeactivateActCtx` at `0x180380a44`
- `KERNEL32!LoadLibraryExA` at `0x18003acfc`
- `KERNEL32!LoadLibraryExA` at `0x18003acfc`

## pseudocode

```c

```
