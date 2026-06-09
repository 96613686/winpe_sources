# CNscTree::_UpdateItemDisplayInfo(ulong,IShellFolder *,_ITEMID_CHILD const *,_TREEITEM *,int *,int *)

- ea: `0x1800a4dc0`
- end: `0x1800a55ea`
- name: `?_UpdateItemDisplayInfo@CNscTree@@AEAAHKPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@PEAU_TREEITEM@@PEAH3@Z`
- size: `2090`
- prototype: `__int64 __usercall@<rax>(CNscTree *__hidden this@<rcx>, unsigned int@<edx>, struct IShellFolder *@<r8>, const struct _ITEMID_CHILD *@<r9>, struct _TREEITEM *, int *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update`

## callers

- `0x1800a4ce8`

## callees

- `0x18002903c`
- `0x180029078`
- `0x1800290d0`
- `0x18002aa70`
- `0x18003503c`
- `0x180045ce0`
- `0x1800492b0`
- `0x1800a4dc0`
- `0x1800dc3a4`
- `0x180123448`
- `0x18013fcac`
- `0x18015042c`
- `0x1801b2730`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800a4e87`
- `SHCORE!IUnknown_QueryService` at `0x1800a4e87`
- `SHCORE!IUnknown_Set` at `0x1800a4f56`
- `SHCORE!IUnknown_Set` at `0x1800a4f56`
- `SHELL32!SHCreateItemWithParent` at `0x1800a4fad`
- `SHELL32!SHCreateItemWithParent` at `0x1800a4fad`
- `SHELL32!__imp_ILClone` at `0x1800a5279`
- `SHELL32!__imp_ILClone` at `0x1800a5483`
- `SHELL32!__imp_ILClone` at `0x1800a5279`
- `SHELL32!__imp_ILClone` at `0x1800a5483`
- `SHELL32!__imp_ILFree` at `0x1800a55b5`
- `SHELL32!__imp_ILFree` at `0x1800a55b5`
- `SHELL32!__imp_SHMapIDListToSystemImageListIndexAsync` at `0x1800a5026`
- `SHELL32!__imp_SHMapIDListToSystemImageListIndexAsync` at `0x1800a5026`
- `USER32!SendMessageW` at `0x1800a4e51`
- `USER32!SendMessageW` at `0x1800a4ef1`
- `USER32!SendMessageW` at `0x1800a4e51`
- `USER32!SendMessageW` at `0x1800a4ef1`

## pseudocode

```c

```
