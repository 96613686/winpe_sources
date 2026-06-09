# CNscTree::_AddItemToTree(_TREEITEM *,IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,int,ulong,IShellItemFilter *,int,_TREEITEM *,int,int,int,int)

- ea: `0x18009a298`
- end: `0x18009a972`
- name: `?_AddItemToTree@CNscTree@@AEAAPEAU_TREEITEM@@PEAU2@PEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@HKPEAUIShellItemFilter@@H0HHHH@Z`
- size: `1754`
- prototype: `struct _TREEITEM *__usercall@<rax>(CNscTree *__hidden this@<rcx>, struct _TREEITEM *@<rdx>, IUnknown *punk@<r8>, const struct _ITEMIDLIST_ABSOLUTE *@<r9>, LPCITEMIDLIST pidl1, int, unsigned int, struct IShellItemFilter *, int, struct _TREEITEM *, int, int, int, int)`
- caller_count: `4`
- callee_count: `27`
- tags: `service_task`

## callers

- `0x180094ffc`
- `0x180096e58`
- `0x180100798`
- `0x1801b8194`

## callees

- `0x1800218ac`
- `0x1800218d8`
- `0x1800218fc`
- `0x1800235e8`
- `0x1800245dc`
- `0x180026424`
- `0x18002ae50`
- `0x18002b634`
- `0x18002c6b0`
- `0x18004872c`
- `0x1800903fc`
- `0x180094e2c`
- `0x1800955cc`
- `0x180095f5c`
- `0x1800969e0`
- `0x180099528`
- `0x18009a008`
- `0x18009a298`
- `0x18009a978`
- `0x18009aa0c`
- `0x18009aa48`
- `0x1800ecfe0`
- `0x18013fcac`
- `0x1801406ec`
- `0x1801b24fc`
- `0x1801b2978`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18009a2ed`
- `SHCORE!IUnknown_QueryService` at `0x18009a2ed`
- `SHCORE!IUnknown_Set` at `0x18009a39e`
- `SHCORE!IUnknown_Set` at `0x18009a447`
- `SHCORE!IUnknown_Set` at `0x18009a39e`
- `SHCORE!IUnknown_Set` at `0x18009a447`
- `SHELL32!SHCreateItemWithParent` at `0x18009a4c3`
- `SHELL32!SHCreateItemWithParent` at `0x18009a4c3`
- `SHELL32!SHBindToFolderIDListParent` at `0x18009a484`
- `SHELL32!SHBindToFolderIDListParent` at `0x18009a484`
- `SHELL32!SHGetIDListFromObject` at `0x18009a7aa`
- `SHELL32!SHGetIDListFromObject` at `0x18009a878`
- `SHELL32!SHGetIDListFromObject` at `0x18009a7aa`
- `SHELL32!SHGetIDListFromObject` at `0x18009a878`
- `SHELL32!__imp_ILFindLastID` at `0x18009a5af`
- `SHELL32!__imp_ILFindLastID` at `0x18009a5af`
- `SHELL32!__imp_ILClone` at `0x18009a585`
- `SHELL32!__imp_ILClone` at `0x18009a585`
- `SHELL32!__imp_ILCloneFirst` at `0x18009a5b8`
- `SHELL32!__imp_ILCloneFirst` at `0x18009a5b8`
- `SHELL32!__imp_ILIsEqual` at `0x18009a358`
- `SHELL32!__imp_ILIsEqual` at `0x18009a889`
- `SHELL32!__imp_ILIsEqual` at `0x18009a358`
- `SHELL32!__imp_ILIsEqual` at `0x18009a889`
- `SHELL32!__imp_ILFree` at `0x18009a7fa`
- `SHELL32!__imp_ILFree` at `0x18009a8ce`
- `SHELL32!__imp_ILFree` at `0x18009a8ee`
- `SHELL32!__imp_ILFree` at `0x18009a932`
- `SHELL32!__imp_ILFree` at `0x18009a7fa`
- `SHELL32!__imp_ILFree` at `0x18009a8ce`
- `SHELL32!__imp_ILFree` at `0x18009a8ee`
- `SHELL32!__imp_ILFree` at `0x18009a932`
- `USER32!SendMessageW` at `0x18009a741`
- `USER32!SendMessageW` at `0x18009a8b2`
- `USER32!SendMessageW` at `0x18009a741`
- `USER32!SendMessageW` at `0x18009a8b2`

## pseudocode

```c

```
