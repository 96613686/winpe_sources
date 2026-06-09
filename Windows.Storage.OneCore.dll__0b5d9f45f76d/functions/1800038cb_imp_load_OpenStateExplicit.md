# __imp_load_OpenStateExplicit

- ea: `0x1800038cb`
- end: `0x1800038d7`
- name: `__imp_load_OpenStateExplicit`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1800038cb`

## pseudocode

```c
__int64 load_OpenStateExplicit()
{
  return _tailMerge_ext_ms_win_appmodel_state_ext_l1_2_0_dll();
}

```

## disassembly

```asm
0x1800038cb  lea     rax, __imp_OpenStateExplicit
0x1800038d2  jmp     __tailMerge_ext_ms_win_appmodel_state_ext_l1_2_0_dll
```
