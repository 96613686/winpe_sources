# __imp_load_LsaLookupOpenLocalPolicy

- ea: `0x18000aa43`
- end: `0x18000aa4f`
- name: `__imp_load_LsaLookupOpenLocalPolicy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a9a0`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000aa43`

## pseudocode

```c
__int64 load_LsaLookupOpenLocalPolicy()
{
  return _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aa43  lea     rax, __imp_LsaLookupOpenLocalPolicy
0x18000aa4a  jmp     __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll
```
