# GetProviderCLSID(ILocationDescription *,_GUID *)

- ea: `0x18002bcc0`
- end: `0x18002bd6d`
- name: `?GetProviderCLSID@@YAJPEAUILocationDescription@@PEAU_GUID@@@Z`
- size: `173`
- prototype: `int(struct ILocationDescription *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e2e0`

## callees

- `0x18002bcc0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bd49`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bd49`
- `PROPSYS!PropVariantToGUID` at `0x18002bd3c`
- `PROPSYS!PropVariantToGUID` at `0x18002bd3c`

## string_xrefs

- `0x18002bd0e`: `clsid`

## pseudocode

```c

```
