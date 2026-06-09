# CShellBrowser::_HandleFileSysChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180088f44`
- end: `0x180089276`
- name: `?_HandleFileSysChange@CShellBrowser@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z`
- size: `818`
- prototype: `void(CShellBrowser *__hidden this, int, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180087970`

## callees

- `0x1800218ac`
- `0x180073378`
- `0x180088e9c`
- `0x180088f44`
- `0x18008927c`
- `0x180089460`
- `0x1800899cc`
- `0x1800899f8`
- `0x1800dc4cc`
- `0x18013fcac`
- `0x1802006dc`
- `0x180210010`

## import_xrefs

- `SHCORE!__imp_SHQueueUserWorkItem` at `0x180089087`
- `SHCORE!__imp_SHQueueUserWorkItem` at `0x180089087`
- `SHELL32!__imp_ILClone` at `0x1800891b8`
- `SHELL32!__imp_ILClone` at `0x1800891b8`
- `SHELL32!__imp_ILIsEqual` at `0x180088fba`
- `SHELL32!__imp_ILIsEqual` at `0x180089128`
- `SHELL32!__imp_ILIsEqual` at `0x180088fba`
- `SHELL32!__imp_ILIsEqual` at `0x180089128`
- `SHELL32!__imp_ILIsParent` at `0x180088fcd`
- `SHELL32!__imp_ILIsParent` at `0x1800890d5`
- `SHELL32!__imp_ILIsParent` at `0x180089248`
- `SHELL32!__imp_ILIsParent` at `0x180088fcd`
- `SHELL32!__imp_ILIsParent` at `0x1800890d5`
- `SHELL32!__imp_ILIsParent` at `0x180089248`
- `SHELL32!__imp_ILFree` at `0x1800890e0`
- `SHELL32!__imp_ILFree` at `0x1800890e0`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x180089206`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x180089206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890fb`
- `USER32!PostMessageW` at `0x18008926b`
- `USER32!PostMessageW` at `0x18008926b`

## pseudocode

```c

```
