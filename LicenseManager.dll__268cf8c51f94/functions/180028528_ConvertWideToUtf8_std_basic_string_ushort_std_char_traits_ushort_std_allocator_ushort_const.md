# ConvertWideToUtf8(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180028528`
- end: `0x1800286b1`
- name: `?ConvertWideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `393`
- prototype: `__int64 __fastcall(void *Src, LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028160`
- `0x18005815c`

## callees

- `0x180028528`
- `0x1800769f4`
- `0x18008a400`
- `0x1800a19dc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800285b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002867c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800285b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002867c`

## string_xrefs

- `0x180028686`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c

```
