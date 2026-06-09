# __imp_load_PostThreadMessageW

- ea: `0x14000204a`
- end: `0x140002056`
- name: `__imp_load_PostThreadMessageW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001fb9`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x14000204a`

## pseudocode

```c
__int64 load_PostThreadMessageW()
{
  return _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000204a  lea     rax, __imp_PostThreadMessageW
0x140002051  jmp     __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll
```
