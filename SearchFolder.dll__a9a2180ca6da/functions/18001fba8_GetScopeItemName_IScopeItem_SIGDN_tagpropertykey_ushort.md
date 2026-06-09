# _GetScopeItemName(IScopeItem *,_SIGDN,_tagpropertykey,ushort * *)

- ea: `0x18001fba8`
- end: `0x18001fd31`
- name: `?_GetScopeItemName@@YAJPEAUIScopeItem@@W4_SIGDN@@U_tagpropertykey@@PEAPEAG@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct IScopeItem *, enum _SIGDN, struct _tagpropertykey *, LPVOID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d0f8`

## callees

- `0x18001d5f0`
- `0x18001fba8`
- `0x18004fb0c`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fc73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fc73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcee`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001fc60`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001fc60`

## pseudocode

```c

```
