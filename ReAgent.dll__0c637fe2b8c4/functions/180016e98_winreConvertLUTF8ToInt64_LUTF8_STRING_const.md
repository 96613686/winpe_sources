# winreConvertLUTF8ToInt64(_LUTF8_STRING const *)

- ea: `0x180016e98`
- end: `0x180016f4f`
- name: `?winreConvertLUTF8ToInt64@@YA_KPEBU_LUTF8_STRING@@@Z`
- size: `183`
- prototype: `unsigned __int64 __fastcall(const struct _LUTF8_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800116b0`

## callees

- `0x180002786`
- `0x1800059fc`
- `0x180016e98`

## import_xrefs

- `msvcrt!_atoi64` at `0x180016f1a`
- `msvcrt!_atoi64` at `0x180016f1a`
- `KERNEL32!HeapFree` at `0x180016f31`
- `KERNEL32!HeapFree` at `0x180016f31`
- `KERNEL32!HeapAlloc` at `0x180016ec1`
- `KERNEL32!HeapAlloc` at `0x180016ec1`
- `KERNEL32!GetProcessHeap` at `0x180016ead`
- `KERNEL32!GetProcessHeap` at `0x180016f23`
- `KERNEL32!GetProcessHeap` at `0x180016ead`
- `KERNEL32!GetProcessHeap` at `0x180016f23`

## string_xrefs

- `0x180016ecf`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`

## pseudocode

```c

```
