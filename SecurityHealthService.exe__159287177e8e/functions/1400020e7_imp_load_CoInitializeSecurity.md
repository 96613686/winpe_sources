# __imp_load_CoInitializeSecurity

- ea: `0x1400020e7`
- end: `0x1400020f3`
- name: `__imp_load_CoInitializeSecurity`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002056`

## import_xrefs

- `ole32!CoInitializeSecurity` at `0x1400020e7`

## pseudocode

```c
__int64 load_CoInitializeSecurity()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1400020e7  lea     rax, __imp_CoInitializeSecurity
0x1400020ee  jmp     __tailMerge_ole32_dll
```
