# __imp_load_WmiOpenBlock

- ea: `0x18000aeed`
- end: `0x18000aef9`
- name: `__imp_load_WmiOpenBlock`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ae6e`

## import_xrefs

- `WMICLNT!WmiOpenBlock` at `0x18000aeed`

## pseudocode

```c
__int64 load_WmiOpenBlock()
{
  return _tailMerge_wmiclnt_dll();
}

```

## disassembly

```asm
0x18000aeed  lea     rax, __imp_WmiOpenBlock
0x18000aef4  jmp     __tailMerge_wmiclnt_dll
```
