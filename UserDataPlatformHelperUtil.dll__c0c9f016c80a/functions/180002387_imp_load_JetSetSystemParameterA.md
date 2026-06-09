# __imp_load_JetSetSystemParameterA

- ea: `0x180002387`
- end: `0x180002393`
- name: `__imp_load_JetSetSystemParameterA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002308`

## import_xrefs

- `ESENT!JetSetSystemParameterA` at `0x180002387`

## pseudocode

```c
__int64 load_JetSetSystemParameterA()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002387  lea     rax, __imp_JetSetSystemParameterA
0x18000238e  jmp     __tailMerge_esent_dll
```
