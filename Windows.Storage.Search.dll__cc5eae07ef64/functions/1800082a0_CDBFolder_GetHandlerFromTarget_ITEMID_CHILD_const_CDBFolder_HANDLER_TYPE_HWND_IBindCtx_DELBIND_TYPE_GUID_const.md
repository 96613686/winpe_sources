# CDBFolder::_GetHandlerFromTarget(_ITEMID_CHILD const *,CDBFolder::HANDLER_TYPE,HWND__ *,IBindCtx *,DELBIND_TYPE,_GUID const &,void * *)

- ea: `0x1800082a0`
- end: `0x18000873e`
- name: `?_GetHandlerFromTarget@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@W4HANDLER_TYPE@1@PEAUHWND__@@PEAUIBindCtx@@W4DELBIND_TYPE@@AEBU_GUID@@PEAPEAX@Z`
- size: `1182`
- prototype: `__int64 __fastcall(struct IShellFolder *, const ITEMIDLIST *, int, HWND, struct IBindCtx *, unsigned int, void *Buf1, void **ppv)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e40`
- `0x180016df8`
- `0x180018ae0`
- `0x18001a640`
- `0x1800582f0`

## callees

- `0x1800082a0`
- `0x18000a350`
- `0x18000a730`
- `0x180015e40`
- `0x180019b60`
- `0x1800281f4`
- `0x18005a814`
- `0x18006000c`
- `0x180072cd0`
- `0x18008b3a0`
- `0x18008b7c0`
- `0x18008c25c`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x180008312`
- `Windows.Storage!ILFindLastID` at `0x180008312`
- `Windows.Storage!ILFree` at `0x1800085a6`
- `Windows.Storage!ILFree` at `0x1800085a6`
- `Windows.Storage!SHCreateItemWithParent` at `0x180008608`
- `Windows.Storage!SHCreateItemWithParent` at `0x180008608`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800086c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800086c1`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x1800086b4`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x1800086b4`

## pseudocode

```c

```
