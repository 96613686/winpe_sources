# BasepGetVolumeNameFromReparsePoint

- ea: `0x1800481f0`
- end: `0x18004869a`
- name: `BasepGetVolumeNameFromReparsePoint`
- size: `1194`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, void *, DWORD cchFilePath)`
- caller_count: `3`
- callee_count: `11`
- tags: `reparse_path, loader_planting`

## callers

- `0x180046310`
- `0x1800464e0`
- `0x180047c90`

## callees

- `0x1800134a0`
- `0x180013ec0`
- `0x1800481f0`
- `0x1800486a0`
- `0x18004873c`
- `0x180048f30`
- `0x180077f90`
- `0x18012eecc`
- `0x180188eb9`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!SbSelectProcedure` at `0x1800483d7`
- `ntdll!SbSelectProcedure` at `0x1800483d7`
- `ntdll!RtlSetLastWin32Error` at `0x1800482f2`
- `ntdll!RtlSetLastWin32Error` at `0x1800484ca`
- `ntdll!RtlSetLastWin32Error` at `0x1800484f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800485f1`
- `ntdll!RtlSetLastWin32Error` at `0x18018f2cf`
- `ntdll!RtlSetLastWin32Error` at `0x18018f2e0`
- `ntdll!RtlSetLastWin32Error` at `0x1800482f2`
- `ntdll!RtlSetLastWin32Error` at `0x1800484ca`
- `ntdll!RtlSetLastWin32Error` at `0x1800484f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800485f1`
- `ntdll!RtlSetLastWin32Error` at `0x18018f2cf`
- `ntdll!RtlSetLastWin32Error` at `0x18018f2e0`
- `ntdll!NtClose` at `0x1800483e5`
- `ntdll!NtClose` at `0x1800483e5`
- `ntdll!RtlFreeHeap` at `0x180048399`
- `ntdll!RtlFreeHeap` at `0x180048399`
- `ntdll!RtlAllocateHeap` at `0x180048311`
- `ntdll!RtlAllocateHeap` at `0x180048311`

## pseudocode

```c

```
