# __imp_load_JetGetSystemParameterA

- ea: `0x180002399`
- end: `0x1800023a5`
- name: `__imp_load_JetGetSystemParameterA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002308`

## import_xrefs

- `ESENT!JetGetSystemParameterA` at `0x180002399`

## pseudocode

```c
__int64 load_JetGetSystemParameterA()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002399  lea     rax, __imp_JetGetSystemParameterA
0x1800023a0  jmp     __tailMerge_esent_dll
```
