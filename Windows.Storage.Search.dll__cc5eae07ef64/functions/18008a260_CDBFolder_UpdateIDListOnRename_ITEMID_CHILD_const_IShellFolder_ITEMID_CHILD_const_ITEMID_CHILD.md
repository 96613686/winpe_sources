# CDBFolder::UpdateIDListOnRename(_ITEMID_CHILD const *,IShellFolder *,_ITEMID_CHILD const *,_ITEMID_CHILD * *)

- ea: `0x18008a260`
- end: `0x18008a44e`
- name: `?UpdateIDListOnRename@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEAUIShellFolder@@PEBU2@PEAPEAU2@@Z`
- size: `494`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, struct IShellFolder *, const struct _ITEMID_CHILD *, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008cd6c`

## callees

- `0x18002eb80`
- `0x18004959c`
- `0x1800515ac`
- `0x180071dc0`
- `0x180072cf4`
- `0x18008a260`
- `0x18008bf08`

## import_xrefs

- `Windows.Storage!ILFree` at `0x18008a419`
- `Windows.Storage!ILFree` at `0x18008a419`
- `Windows.Storage!SHGetIDListFromObject` at `0x18008a31e`
- `Windows.Storage!SHGetIDListFromObject` at `0x18008a31e`
- `Windows.Storage!ILGetSize` at `0x18008a35c`
- `Windows.Storage!ILGetSize` at `0x18008a35c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18008a2df`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18008a2df`
- `PROPSYS!ClearPropVariantArray` at `0x18008a428`
- `PROPSYS!ClearPropVariantArray` at `0x18008a428`

## pseudocode

```c

```
