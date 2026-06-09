# __imp_load_InitThread

- ea: `0x180002554`
- end: `0x180002560`
- name: `__imp_load_InitThread`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!InitThread` at `0x180002554`

## pseudocode

```c
__int64 load_InitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002554  lea     rax, __imp_InitThread
0x18000255b  jmp     __tailMerge_dui70_dll
```
