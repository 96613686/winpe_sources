# WerpAddGatherBlockToReport(void *,ulong,WER_GATHER *,long (*)(void *,wchar_t const *,_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *),long (*)(void *,ulong,void *,ulong,ulong),long (*)(void *,ulong,void *,ulong,ulong),ulong)

- ea: `0x1800a38e0`
- end: `0x1800a3a6b`
- name: `?WerpAddGatherBlockToReport@@YAJPEAXKPEAUWER_GATHER@@P6AJ0PEB_WW4_WER_FILE_TYPE@@K22@ZP6AJ0K0KK@Z5K@Z`
- size: `395`
- prototype: `__int64 __fastcall(void *, unsigned int, struct WER_GATHER *, int (*)(void *, const wchar_t *, enum _WER_FILE_TYPE, unsigned int, const wchar_t *, const wchar_t *), int (*)(void *, unsigned int, void *, unsigned int, unsigned int), int (*)(void *, unsigned int, void *, unsigned int, unsigned int), unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180066fd0`

## callees

- `0x180025b10`
- `0x180051b7c`
- `0x180066a3c`
- `0x180066f10`
- `0x1800a38e0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800a39df`
- `ntdll!DbgPrintEx` at `0x1800a3a15`
- `ntdll!DbgPrintEx` at `0x1800a3a55`
- `ntdll!DbgPrintEx` at `0x1800a39df`
- `ntdll!DbgPrintEx` at `0x1800a3a15`
- `ntdll!DbgPrintEx` at `0x1800a3a55`

## string_xrefs

- `0x1800a39d1`: `WER/CrashAPI/%u:%u: ERROR StringCchCopyN failed\n`

## pseudocode

```c

```
