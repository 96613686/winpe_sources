# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000ffcc`
- end: `0x180010070`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800169fc`

## callees

- `0x180004b20`
- `0x180006080`
- `0x1800065ec`
- `0x18000ffcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010058`

## string_xrefs

- `0x18000ffe3`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x18001001e`: `shell\oobe\user\dll\oobelauncher.cpp`

## pseudocode

```c

```
