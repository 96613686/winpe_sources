# SqldWideCharStringToString(uchar const *,unsigned __int64,IReportSqlError &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18304a050`
- end: `0x18304a212`
- name: `?SqldWideCharStringToString@@YAXPEBE_KAEAVIReportSqlError@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x183049b70`
- `0x18304bd10`

## callees

- `0x1815ceeb0`
- `0x182da7f60`
- `0x182dc4440`
- `0x18304a050`
- `0x1832c3a30`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18304a0c3`
- `KERNEL32!WideCharToMultiByte` at `0x18304a14f`
- `KERNEL32!WideCharToMultiByte` at `0x18304a0c3`
- `KERNEL32!WideCharToMultiByte` at `0x18304a14f`
- `KERNEL32!GetLastError` at `0x18304a0d0`
- `KERNEL32!GetLastError` at `0x18304a159`
- `KERNEL32!GetLastError` at `0x18304a0d0`
- `KERNEL32!GetLastError` at `0x18304a159`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1b5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1c5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1d5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1e2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1b5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1c5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1d5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18304a1e2`

## string_xrefs

- `0x18304a0ea`: `reading`
- `0x18304a173`: `reading`

## pseudocode

```c

```
