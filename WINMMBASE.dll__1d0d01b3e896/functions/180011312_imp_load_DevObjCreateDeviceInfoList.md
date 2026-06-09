# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x180011312`
- end: `0x18001131e`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001119c`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180011312`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180011312  lea     rax, __imp_DevObjCreateDeviceInfoList
0x180011319  jmp     __tailMerge_devobj_dll
```
