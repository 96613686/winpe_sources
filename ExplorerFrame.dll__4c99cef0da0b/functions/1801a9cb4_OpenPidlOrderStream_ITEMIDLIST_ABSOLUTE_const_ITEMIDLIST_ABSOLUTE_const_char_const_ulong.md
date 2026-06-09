# OpenPidlOrderStream(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,char const *,ulong)

- ea: `0x1801a9cb4`
- end: `0x1801a9ea5`
- name: `?OpenPidlOrderStream@@YAPEAUIStream@@PEBU_ITEMIDLIST_ABSOLUTE@@0PEBDK@Z`
- size: `497`
- prototype: `struct IStream *__fastcall(const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *, const char *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801a9960`
- `0x1801aa530`

## callees

- `0x1800243b0`
- `0x180037ce0`
- `0x1800e00bc`
- `0x18013f7d0`
- `0x1801a9cb4`
- `0x1802086a0`
- `0x180210010`

## import_xrefs

- `SHCORE!SHOpenRegStream2W` at `0x1801a9e75`
- `SHCORE!SHOpenRegStream2W` at `0x1801a9e75`
- `SHCORE!SHAnsiToUnicode` at `0x1801a9d07`
- `SHCORE!SHAnsiToUnicode` at `0x1801a9d07`
- `SHELL32!SHBindToParent` at `0x1801a9dbd`
- `SHELL32!SHBindToParent` at `0x1801a9dbd`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1801a9d49`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1801a9d49`
- `SHELL32!__imp_ILClone` at `0x1801a9d68`
- `SHELL32!__imp_ILClone` at `0x1801a9d68`
- `SHELL32!__imp_ILFindChild` at `0x1801a9d80`
- `SHELL32!__imp_ILFindChild` at `0x1801a9d80`
- `SHELL32!__imp_ILGetNext` at `0x1801a9e37`
- `SHELL32!__imp_ILGetNext` at `0x1801a9e37`
- `SHELL32!__imp_ILFree` at `0x1801a9e4c`
- `SHELL32!__imp_ILFree` at `0x1801a9e57`
- `SHELL32!__imp_ILFree` at `0x1801a9e4c`
- `SHELL32!__imp_ILFree` at `0x1801a9e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9e1a`

## pseudocode

```c

```
