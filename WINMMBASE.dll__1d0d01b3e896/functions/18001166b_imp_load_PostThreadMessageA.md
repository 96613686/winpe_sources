# __imp_load_PostThreadMessageA

- ea: `0x18001166b`
- end: `0x180011677`
- name: `__imp_load_PostThreadMessageA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800115ec`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x18001166b`

## pseudocode

```c
__int64 load_PostThreadMessageA()
{
  return _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001166b  lea     rax, __imp_PostThreadMessageA
0x180011672  jmp     __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll
```
