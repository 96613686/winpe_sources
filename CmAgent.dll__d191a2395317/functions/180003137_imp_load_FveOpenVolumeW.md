# __imp_load_FveOpenVolumeW

- ea: `0x180003137`
- end: `0x180003143`
- name: `__imp_load_FveOpenVolumeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003082`

## import_xrefs

- `FVEAPI!FveOpenVolumeW` at `0x180003137`

## pseudocode

```c
__int64 load_FveOpenVolumeW()
{
  return _tailMerge_fveapi_dll();
}

```

## disassembly

```asm
0x180003137  lea     rax, __imp_FveOpenVolumeW
0x18000313e  jmp     __tailMerge_fveapi_dll
```
