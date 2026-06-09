# CFSFolder::InitializeEx(IBindCtx *,_ITEMIDLIST_ABSOLUTE const *,_PERSIST_FOLDER_TARGET_INFO const *)

- ea: `0x180180d90`
- end: `0x180181553`
- name: `?InitializeEx@CFSFolder@@UEAAJPEAUIBindCtx@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBU_PERSIST_FOLDER_TARGET_INFO@@@Z`
- size: `1987`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, struct IBindCtx *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _PERSIST_FOLDER_TARGET_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800432f0`
- `0x180093c20`
- `0x1800a5580`
- `0x180180d90`
- `0x1803a4cb0`
- `0x1803a96d9`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180181497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180181497`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18018151d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18018151d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801813b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801813b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180181503`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180181503`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18018144e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18018144e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801814dc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801814dc`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1801814b9`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1801814b9`
- `OLEAUT32!__imp_SysAllocString` at `0x180180e4b`
- `OLEAUT32!__imp_SysAllocString` at `0x180180e4b`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18018134d`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18018134d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180181052`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18018106c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180181086`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801810a0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801810af`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180181052`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18018106c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180181086`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801810a0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1801810af`

## string_xrefs

- `0x1801814d5`: `%SystemRoot%\System32\RuntimeBroker.exe`
- `0x180180fdc`: `ItemCacheContext`
- `0x180181061`: `FSFolder_ConvertToSidString`
- `0x180181044`: `FSFolder_ResolveSidToUserName`

## pseudocode

```c

```
