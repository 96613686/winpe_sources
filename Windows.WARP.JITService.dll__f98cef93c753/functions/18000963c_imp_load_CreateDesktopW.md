# __imp_load_CreateDesktopW

- ea: `0x18000963c`
- end: `0x180009648`
- name: `__imp_load_CreateDesktopW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009555`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateDesktopW` at `0x18000963c`

## pseudocode

```c
__int64 load_CreateDesktopW()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000963c  lea     rax, __imp_CreateDesktopW
0x180009643  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll
```
