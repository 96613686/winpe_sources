# __imp_load_CryptMsgOpenToDecode

- ea: `0x180003a70`
- end: `0x180003a7c`
- name: `__imp_load_CryptMsgOpenToDecode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003997`

## import_xrefs

- `CRYPT32!CryptMsgOpenToDecode` at `0x180003a70`

## pseudocode

```c
__int64 load_CryptMsgOpenToDecode()
{
  return _tailMerge_crypt32_dll();
}

```

## disassembly

```asm
0x180003a70  lea     rax, __imp_CryptMsgOpenToDecode
0x180003a77  jmp     __tailMerge_crypt32_dll
```
