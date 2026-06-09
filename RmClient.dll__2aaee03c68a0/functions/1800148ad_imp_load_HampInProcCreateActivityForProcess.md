# __imp_load_HampInProcCreateActivityForProcess

- ea: `0x1800148ad`
- end: `0x1800148b9`
- name: `__imp_load_HampInProcCreateActivityForProcess`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014744`

## import_xrefs

- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCreateActivityForProcess` at `0x1800148ad`

## pseudocode

```c
__int64 load_HampInProcCreateActivityForProcess()
{
  return _tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800148ad  lea     rax, __imp_HampInProcCreateActivityForProcess
0x1800148b4  jmp     __tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll
```
