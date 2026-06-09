# __imp_load_AddAccessAllowedAce

- ea: `0x18000a7b8`
- end: `0x18000a7c4`
- name: `__imp_load_AddAccessAllowedAce`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000a7b8`

## pseudocode

```c
__int64 load_AddAccessAllowedAce()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a7b8  lea     rax, __imp_AddAccessAllowedAce
0x18000a7bf  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
