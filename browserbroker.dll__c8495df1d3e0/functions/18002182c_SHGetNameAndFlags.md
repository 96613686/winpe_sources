# SHGetNameAndFlags

- ea: `0x18002182c`
- end: `0x180021903`
- name: `SHGetNameAndFlags`
- size: `215`
- prototype: `__int64 __usercall@<rax>(LPCITEMIDLIST pidl@<rcx>, LPCITEMIDLIST ppidlLast)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800216e0`

## callees

- `0x1800217d8`
- `0x180021808`
- `0x18002182c`
- `0x18002505c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021860`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021873`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021860`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021873`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800218e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800218e1`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x1800218a1`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToParent` at `0x1800218a1`

## pseudocode

```c

```
