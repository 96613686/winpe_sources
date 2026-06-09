# _CoAllocAnsiStringFromWideString(ushort const *,char * *)

- ea: `0x180049b48`
- end: `0x180049c4a`
- name: `?_CoAllocAnsiStringFromWideString@@YAJPEBGPEAPEAD@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049504`

## callees

- `0x180009d00`
- `0x18000f718`
- `0x18002fa14`
- `0x180049b48`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180049b92`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180049c14`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180049b92`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180049c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049c35`

## pseudocode

```c

```
