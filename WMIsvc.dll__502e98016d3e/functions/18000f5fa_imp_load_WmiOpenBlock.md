# __imp_load_WmiOpenBlock

- ea: `0x18000f5fa`
- end: `0x18000f606`
- name: `__imp_load_WmiOpenBlock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f57b`

## import_xrefs

- `WMICLNT!WmiOpenBlock` at `0x18000f5fa`

## pseudocode

```c
__int64 load_WmiOpenBlock()
{
  return _tailMerge_wmiclnt_dll();
}

```

## disassembly

```asm
0x18000f5fa  lea     rax, __imp_WmiOpenBlock
0x18000f601  jmp     __tailMerge_wmiclnt_dll
```
