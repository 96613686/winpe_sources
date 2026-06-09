# __imp_load_InitializeAcl

- ea: `0x18000a7a6`
- end: `0x18000a7b2`
- name: `__imp_load_InitializeAcl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000a7a6`

## pseudocode

```c
__int64 load_InitializeAcl()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a7a6  lea     rax, __imp_InitializeAcl
0x18000a7ad  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
