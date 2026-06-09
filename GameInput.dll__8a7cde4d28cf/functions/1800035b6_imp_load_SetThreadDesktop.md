# __imp_load_SetThreadDesktop

- ea: `0x1800035b6`
- end: `0x1800035c2`
- name: `__imp_load_SetThreadDesktop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003488`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!SetThreadDesktop` at `0x1800035b6`

## pseudocode

```c
__int64 load_SetThreadDesktop()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800035b6  lea     rax, __imp_SetThreadDesktop
0x1800035bd  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll
```
