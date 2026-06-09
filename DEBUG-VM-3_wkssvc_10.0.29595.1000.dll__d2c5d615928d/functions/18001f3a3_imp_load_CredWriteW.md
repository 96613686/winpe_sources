# __imp_load_CredWriteW

- ea: `0x18001f3a3`
- end: `0x18001f3af`
- name: `__imp_load_CredWriteW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f0a6`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18001f3a3`

## pseudocode

```c
__int64 load_CredWriteW()
{
  return _tailMerge_api_ms_win_security_credentials_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001f3a3  lea     rax, __imp_CredWriteW
0x18001f3aa  jmp     __tailMerge_api_ms_win_security_credentials_l1_1_0_dll
```
