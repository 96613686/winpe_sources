# __imp_load_BcdOpenObject

- ea: `0x180003bd3`
- end: `0x180003bdf`
- name: `__imp_load_BcdOpenObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003b0c`

## import_xrefs

- `bcd!BcdOpenObject` at `0x180003bd3`

## pseudocode

```c
__int64 load_BcdOpenObject()
{
  return _tailMerge_bcd_dll();
}

```

## disassembly

```asm
0x180003bd3  lea     rax, __imp_BcdOpenObject
0x180003bda  jmp     __tailMerge_bcd_dll
```
