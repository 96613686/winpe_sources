# CWebPlatformTridentHost::AggregatedNavigation2(ulong,IBindCtx *,IBindStatusCallback *,ushort const *,IUri *,ushort const *)

- ea: `0x1809e58c0`
- end: `0x1809e5d6a`
- name: `?AggregatedNavigation2@CWebPlatformTridentHost@@UEAAJKPEAUIBindCtx@@PEAUIBindStatusCallback@@PEBGPEAUIUri@@2@Z`
- size: `1194`
- prototype: `__int64 __fastcall(CWebPlatformTridentHost *__hidden this, unsigned int, struct IBindCtx *, struct IBindStatusCallback *, const unsigned __int16 *, struct IUri *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1809ea400`

## callees

- `0x1801af6e0`
- `0x1801b0510`
- `0x18028ecdc`
- `0x1809e58c0`
- `0x1809eced0`
- `0x1809ed1e8`
- `0x18106645c`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1809e5b6d`
- `KERNEL32!LocalFree` at `0x1809e5d09`
- `KERNEL32!LocalFree` at `0x1809e5b6d`
- `KERNEL32!LocalFree` at `0x1809e5d09`
- `KERNEL32!LocalAlloc` at `0x1809e5b29`
- `KERNEL32!LocalAlloc` at `0x1809e5b29`
- `iertutil!CreateUriWithFragment` at `0x1809e5996`
- `iertutil!CreateUriWithFragment` at `0x1809e5996`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809e5d22`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809e5d2c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809e5d22`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809e5d2c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809e5b62`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809e5b88`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809e5b62`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809e5b88`
- `ole32!ReleaseStgMedium` at `0x1809e5d18`
- `ole32!ReleaseStgMedium` at `0x1809e5d18`
- `OLEAUT32!__imp_SysAllocString` at `0x1809e5aa1`
- `OLEAUT32!__imp_SysAllocString` at `0x1809e5aa1`
- `OLEAUT32!__imp_SysFreeString` at `0x1809e5cf5`
- `OLEAUT32!__imp_SysFreeString` at `0x1809e5d36`
- `OLEAUT32!__imp_SysFreeString` at `0x1809e5d3f`
- `OLEAUT32!__imp_SysFreeString` at `0x1809e5cf5`
- `OLEAUT32!__imp_SysFreeString` at `0x1809e5d36`
- `OLEAUT32!__imp_SysFreeString` at `0x1809e5d3f`

## pseudocode

```c

```
