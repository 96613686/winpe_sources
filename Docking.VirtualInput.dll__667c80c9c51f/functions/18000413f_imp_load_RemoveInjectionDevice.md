# __imp_load_RemoveInjectionDevice

- ea: `0x18000413f`
- end: `0x18000414b`
- name: `__imp_load_RemoveInjectionDevice`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800040ae`

## import_xrefs

- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000413f`

## pseudocode

```c
__int64 load_RemoveInjectionDevice()
{
  return _tailMerge_ext_ms_win_ntuser_rim_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000413f  lea     rax, __imp_RemoveInjectionDevice
0x180004146  jmp     __tailMerge_ext_ms_win_ntuser_rim_l1_1_0_dll
```
