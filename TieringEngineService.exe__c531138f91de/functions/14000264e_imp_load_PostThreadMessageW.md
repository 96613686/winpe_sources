# __imp_load_PostThreadMessageW

- ea: `0x14000264e`
- end: `0x14000265a`
- name: `__imp_load_PostThreadMessageW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400025cf`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14000264e`

## pseudocode

```c
__int64 load_PostThreadMessageW()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x14000264e  lea     rax, __imp_PostThreadMessageW
0x140002655  jmp     __tailMerge_user32_dll
```
