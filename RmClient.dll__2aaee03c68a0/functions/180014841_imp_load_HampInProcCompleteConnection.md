# __imp_load_HampInProcCompleteConnection

- ea: `0x180014841`
- end: `0x18001484d`
- name: `__imp_load_HampInProcCompleteConnection`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014744`

## import_xrefs

- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCompleteConnection` at `0x180014841`

## pseudocode

```c
__int64 load_HampInProcCompleteConnection()
{
  return _tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll();
}

```

## disassembly

```asm
0x180014841  lea     rax, __imp_HampInProcCompleteConnection
0x180014848  jmp     __tailMerge_ext_ms_win_hostactivitymanager_ham_private_ext_l1_1_0_dll
```
