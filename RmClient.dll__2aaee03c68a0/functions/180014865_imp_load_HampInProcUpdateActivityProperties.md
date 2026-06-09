# __imp_load_HampInProcUpdateActivityProperties

- ea: `0x180014865`
- end: `0x180014871`
- name: `__imp_load_HampInProcUpdateActivityProperties`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180014744`

## import_xrefs

- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcUpdateActivityProperties` at `0x180014865`

## pseudocode

```c
__int64 load_HampInProcUpdateActivityProperties()
{
  return _tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x180014865  lea     rax, __imp_HampInProcUpdateActivityProperties
0x18001486c  jmp     __tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll
```
