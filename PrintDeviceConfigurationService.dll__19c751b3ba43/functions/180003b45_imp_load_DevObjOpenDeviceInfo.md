# __imp_load_DevObjOpenDeviceInfo

- ea: `0x180003b45`
- end: `0x180003b51`
- name: `__imp_load_DevObjOpenDeviceInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003ab4`

## import_xrefs

- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180003b45`

## pseudocode

```c
__int64 load_DevObjOpenDeviceInfo()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x180003b45  lea     rax, __imp_DevObjOpenDeviceInfo
0x180003b4c  jmp     __tailMerge_devobj_dll
```
