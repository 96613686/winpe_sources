# CPubFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180043170`
- end: `0x1800433a0`
- name: `?GetUIObjectOf@CPubFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `560`
- prototype: `__int64 __usercall@<rax>(CPubFolder *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, const struct _ITEMID_CHILD *const *@<r9>, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b2dc`
- `0x18004218c`
- `0x18004230c`
- `0x180043094`
- `0x180043170`
- `0x180043efc`
- `0x180059010`

## import_xrefs

- `PROPSYS!PropVariantToUInt32WithDefault` at `0x1800432fb`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x1800432fb`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1800432d3`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1800432d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043380`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004338b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043380`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004338b`

## string_xrefs

- `0x180043338`: `imageres.dll`

## pseudocode

```c

```
