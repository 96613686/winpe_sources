# __imp_load_DevObjOpenDeviceInfo

- ea: `0x18001ca4a`
- end: `0x18001ca56`
- name: `__imp_load_DevObjOpenDeviceInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c9cb`

## import_xrefs

- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18001ca4a`

## pseudocode

```c
__int64 load_DevObjOpenDeviceInfo()
{
  return _tailMerge_devobj_dll();
}

```

## disassembly

```asm
0x18001ca4a  lea     rax, __imp_DevObjOpenDeviceInfo
0x18001ca51  jmp     __tailMerge_devobj_dll
```
