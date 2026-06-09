# __imp_load_DuplicateTokenEx

- ea: `0x18000dde9`
- end: `0x18000ddf5`
- name: `__imp_load_DuplicateTokenEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000dd6a`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000dde9`

## pseudocode

```c
__int64 load_DuplicateTokenEx()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000dde9  lea     rax, __imp_DuplicateTokenEx
0x18000ddf0  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
