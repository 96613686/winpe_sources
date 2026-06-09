# MpCommonExceptionMetric::GetModuleFileNameByAddress(void const *,wchar_t *,ulong,unsigned __int64 *)

- ea: `0x14000ae80`
- end: `0x14000af62`
- name: `?GetModuleFileNameByAddress@MpCommonExceptionMetric@@CAHPEBXPEA_WKPEA_K@Z`
- size: `226`
- prototype: `__int64 __fastcall(LPCWSTR lpModuleName, wchar_t *, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000aa98`
- `0x14000ad50`

## callees

- `0x14000ae80`
- `0x14003a5c0`
- `0x1401662d0`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x14000aec5`
- `KERNEL32!GetModuleHandleExW` at `0x14000aec5`
- `KERNEL32!GetModuleFileNameW` at `0x14000aedb`
- `KERNEL32!GetModuleFileNameW` at `0x14000aedb`

## pseudocode

```c

```
