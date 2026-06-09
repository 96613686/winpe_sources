# WinHttpRequest::CopyRequestBody(ushort const *,char * *,ulong *)

- ea: `0x180095920`
- end: `0x180095a72`
- name: `?CopyRequestBody@WinHttpRequest@@AEAAJPEBGPEAPEADPEAK@Z`
- size: `338`
- prototype: `int(WinHttpRequest *__hidden this, const unsigned __int16 *, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009c1a0`

## callees

- `0x180004a24`
- `0x180005f24`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x180095920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095a45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180095a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009596b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009596b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a0e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009595f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180095a02`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009595f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180095a02`

## string_xrefs

- `0x180095983`: `WinHttpRequest::CopyRequestBody`
- `0x1800959b2`: `WinHttpRequest::CopyRequestBody`
- `0x180095a4e`: `WinHttpRequest::CopyRequestBody`

## pseudocode

```c

```
