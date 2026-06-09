# __imp_load_AddAccessDeniedAce

- ea: `0x18000a7ca`
- end: `0x18000a7d6`
- name: `__imp_load_AddAccessDeniedAce`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000a7ca`

## pseudocode

```c
__int64 load_AddAccessDeniedAce()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a7ca  lea     rax, __imp_AddAccessDeniedAce
0x18000a7d1  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
