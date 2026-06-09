# __imp_load_Int_FwValidateComplianceAndReduceCryptoSetToVersion

- ea: `0x180020538`
- end: `0x180020544`
- name: `__imp_load_Int_FwValidateComplianceAndReduceCryptoSetToVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceCryptoSetToVersion` at `0x180020538`

## pseudocode

```c
__int64 load_Int_FwValidateComplianceAndReduceCryptoSetToVersion()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020538  lea     rax, __imp_Int_FwValidateComplianceAndReduceCryptoSetToVersion
0x18002053f  jmp     __tailMerge_fwbase_dll
```
