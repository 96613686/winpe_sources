# CleanInstallFolder(ushort const *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)

- ea: `0x1400076e8`
- end: `0x140007b8d`
- name: `?CleanInstallFolder@@YAJPEBGPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@1@Z`
- size: `1189`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1400076e8`
- `0x140018ccc`

## callees

- `0x140002116`
- `0x140005ec0`
- `0x140005f7c`
- `0x140006ffc`
- `0x1400072bc`
- `0x1400076c8`
- `0x1400076e8`
- `0x140007cb0`
- `0x1400135b8`
- `0x140016bb4`
- `0x140020498`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007807`
- `KERNEL32!HeapFree` at `0x140007b1f`
- `KERNEL32!HeapFree` at `0x140007b4d`
- `KERNEL32!HeapFree` at `0x140007807`
- `KERNEL32!HeapFree` at `0x140007b1f`
- `KERNEL32!HeapFree` at `0x140007b4d`
- `KERNEL32!GetProcessHeap` at `0x1400077f2`
- `KERNEL32!GetProcessHeap` at `0x140007b0a`
- `KERNEL32!GetProcessHeap` at `0x140007b38`
- `KERNEL32!GetProcessHeap` at `0x1400077f2`
- `KERNEL32!GetProcessHeap` at `0x140007b0a`
- `KERNEL32!GetProcessHeap` at `0x140007b38`
- `KERNEL32!GetLastError` at `0x140007a55`
- `KERNEL32!GetLastError` at `0x140007a66`
- `KERNEL32!GetLastError` at `0x140007a55`
- `KERNEL32!GetLastError` at `0x140007a66`
- `KERNEL32!FindFirstFileW` at `0x14000779e`
- `KERNEL32!FindFirstFileW` at `0x14000779e`
- `KERNEL32!FindClose` at `0x140007af8`
- `KERNEL32!FindClose` at `0x140007af8`
- `KERNEL32!FindNextFileW` at `0x140007a3f`
- `KERNEL32!FindNextFileW` at `0x140007a3f`

## string_xrefs

- `0x14000786e`: `Error cleaning path: [%s]`
- `0x140007ac9`: `CleanInstallFolder`

## pseudocode

```c

```
