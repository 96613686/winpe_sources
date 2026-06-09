# OrphanFileFinder::SearchForLooseAppFiles(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,ulong,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180039110`
- end: `0x18003a03f`
- name: `?SearchForLooseAppFiles@OrphanFileFinder@@KAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@KKAEAV43@@Z`
- size: `3887`
- prototype: `void __fastcall(const WCHAR *, char **, unsigned int, unsigned int, __int64 *)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180039110`
- `0x180106e48`

## callees

- `0x1800056f0`
- `0x180018a60`
- `0x1800197d4`
- `0x180021d04`
- `0x1800260f4`
- `0x180039110`
- `0x18003f8a8`
- `0x18003f90c`
- `0x180040500`
- `0x180046db0`
- `0x180047ae4`
- `0x180052cd4`
- `0x180052f28`
- `0x180059920`
- `0x180059cf0`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x180067a70`
- `0x180067a88`
- `0x180125490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039c04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039c04`
- `KERNEL32!FindFirstFileW` at `0x180039280`
- `KERNEL32!FindFirstFileW` at `0x180039280`
- `KERNEL32!FindNextFileW` at `0x180039ead`
- `KERNEL32!FindNextFileW` at `0x180039ead`
- `KERNEL32!FindClose` at `0x180039f98`
- `KERNEL32!FindClose` at `0x180039f98`
- `KERNEL32!LocalFree` at `0x180039226`
- `KERNEL32!LocalFree` at `0x180039e96`
- `KERNEL32!LocalFree` at `0x180039f84`
- `KERNEL32!LocalFree` at `0x180039fa7`
- `KERNEL32!LocalFree` at `0x180039226`
- `KERNEL32!LocalFree` at `0x180039e96`
- `KERNEL32!LocalFree` at `0x180039f84`
- `KERNEL32!LocalFree` at `0x180039fa7`
- `KERNEL32!GetLastError` at `0x180039ebb`
- `KERNEL32!GetLastError` at `0x180039ebb`

## string_xrefs

- `0x180039f5d`: `PathAllocCombine failed for %ws`

## pseudocode

```c

```
