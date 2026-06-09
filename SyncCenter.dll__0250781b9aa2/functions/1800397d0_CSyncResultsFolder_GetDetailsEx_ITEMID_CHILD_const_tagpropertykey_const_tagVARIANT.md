# CSyncResultsFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x1800397d0`
- end: `0x18003993c`
- name: `?GetDetailsEx@CSyncResultsFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `364`
- prototype: `int(CSyncResultsFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002f314`
- `0x1800397d0`
- `0x180053010`

## import_xrefs

- `SHELL32!AssocGetDetailsOfPropKey` at `0x18003991b`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x18003991b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800398de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800398de`
- `PROPSYS!PropVariantToVariant` at `0x1800398cb`
- `PROPSYS!PropVariantToVariant` at `0x1800398cb`
- `OLEAUT32!__imp_VariantInit` at `0x1800397f8`
- `OLEAUT32!__imp_VariantInit` at `0x1800397f8`

## string_xrefs

- `0x18003984e`: `prop:System.ItemNameDisplay;System.Sync.HandlerName;System.DateCreated`

## pseudocode

```c

```
