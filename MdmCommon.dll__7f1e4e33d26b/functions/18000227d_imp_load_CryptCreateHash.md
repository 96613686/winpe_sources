# __imp_load_CryptCreateHash

- ea: `0x18000227d`
- end: `0x180002289`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000212b`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18000227d`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000227d  lea     rax, __imp_CryptCreateHash
0x180002284  jmp     __tailMerge_api_ms_win_security_cryptoapi_l1_1_0_dll
```
