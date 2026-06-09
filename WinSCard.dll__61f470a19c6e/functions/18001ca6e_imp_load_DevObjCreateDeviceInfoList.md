# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x18001ca6e`
- end: `0x18001ca7a`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c9cb`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001ca6e`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x18001ca6e  lea     rax, __imp_DevObjCreateDeviceInfoList
0x18001ca75  jmp     __tailMerge_devobj_dll
```
