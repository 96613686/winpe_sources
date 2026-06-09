# BValidateAndMergeDevmodeWithOemPlugins

- ea: `0x180033b84`
- end: `0x180033cd7`
- name: `BValidateAndMergeDevmodeWithOemPlugins`
- size: `339`
- prototype: `__int64 __usercall@<rax>(struct _devicemodeW *@<rcx>, __int64, __int64, unsigned int, struct _devicemodeW *, struct _OEM_PLUGINS *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002540c`

## callees

- `0x180033b84`
- `0x180033ce0`
- `0x1800341e8`
- `0x18003489c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180033c60`
- `KERNEL32!LocalFree` at `0x180033c60`

## pseudocode

```c

```
