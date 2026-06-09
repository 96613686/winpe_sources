# IsEmptyDirectory

- ea: `0x140027028`
- end: `0x140027323`
- name: `IsEmptyDirectory`
- size: `763`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140055684`

## callees

- `0x140002116`
- `0x140027028`
- `0x140028144`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400272d5`
- `KERNEL32!HeapFree` at `0x1400272d5`
- `KERNEL32!GetProcessHeap` at `0x1400272c1`
- `KERNEL32!GetProcessHeap` at `0x1400272c1`
- `KERNEL32!FindFirstFileW` at `0x1400271f4`
- `KERNEL32!FindFirstFileW` at `0x1400271f4`
- `KERNEL32!FindClose` at `0x1400272b5`
- `KERNEL32!FindClose` at `0x1400272b5`
- `KERNEL32!FindNextFileW` at `0x14002724e`
- `KERNEL32!FindNextFileW` at `0x14002724e`
- `KERNEL32!SetLastError` at `0x1400272ea`
- `KERNEL32!SetLastError` at `0x1400272ea`
- `ntdll!RtlFreeHeap` at `0x14002728a`
- `ntdll!RtlFreeHeap` at `0x14002728a`
- `ntdll!RtlAllocateHeap` at `0x1400270d6`
- `ntdll!RtlAllocateHeap` at `0x1400270d6`

## pseudocode

```c

```
