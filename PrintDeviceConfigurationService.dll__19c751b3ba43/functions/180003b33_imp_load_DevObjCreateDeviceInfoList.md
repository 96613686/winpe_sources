# __imp_load_DevObjCreateDeviceInfoList

- ea: `0x180003b33`
- end: `0x180003b3f`
- name: `__imp_load_DevObjCreateDeviceInfoList`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003ab4`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180003b33`

## pseudocode

```c
__int64 load_DevObjCreateDeviceInfoList()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180003b33  lea     rax, __imp_DevObjCreateDeviceInfoList
0x180003b3a  jmp     __tailMerge_devobj_dll
```
