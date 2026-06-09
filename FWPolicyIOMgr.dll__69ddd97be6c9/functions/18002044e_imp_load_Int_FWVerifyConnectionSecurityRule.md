# __imp_load_Int_FWVerifyConnectionSecurityRule

- ea: `0x18002044e`
- end: `0x18002045a`
- name: `__imp_load_Int_FWVerifyConnectionSecurityRule`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FWVerifyConnectionSecurityRule` at `0x18002044e`

## pseudocode

```c
__int64 load_Int_FWVerifyConnectionSecurityRule()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x18002044e  lea     rax, __imp_Int_FWVerifyConnectionSecurityRule
0x180020455  jmp     __tailMerge_fwbase_dll
```
