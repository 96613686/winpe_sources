# __imp_load_BcdOpenStore

- ea: `0x180003baf`
- end: `0x180003bbb`
- name: `__imp_load_BcdOpenStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003b0c`

## import_xrefs

- `bcd!BcdOpenStore` at `0x180003baf`

## pseudocode

```c
__int64 load_BcdOpenStore()
{
  return _tailMerge_bcd_dll();
}

```

## disassembly

```asm
0x180003baf  lea     rax, __imp_BcdOpenStore
0x180003bb6  jmp     __tailMerge_bcd_dll
```
