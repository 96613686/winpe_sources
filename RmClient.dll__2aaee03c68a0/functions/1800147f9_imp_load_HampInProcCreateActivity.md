# __imp_load_HampInProcCreateActivity

- ea: `0x1800147f9`
- end: `0x180014805`
- name: `__imp_load_HampInProcCreateActivity`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014744`

## import_xrefs

- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCreateActivity` at `0x1800147f9`

## pseudocode

```c
__int64 load_HampInProcCreateActivity()
{
  return _tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800147f9  lea     rax, __imp_HampInProcCreateActivity
0x180014800  jmp     __tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll
```
