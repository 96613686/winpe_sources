# __imp_load_OpenInputDesktop

- ea: `0x180003592`
- end: `0x18000359e`
- name: `__imp_load_OpenInputDesktop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003513`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x180003592`

## pseudocode

```c
__int64 load_OpenInputDesktop()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_1_dll();
}

```

## disassembly

```asm
0x180003592  lea     rax, __imp_OpenInputDesktop
0x180003599  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_1_dll
```
