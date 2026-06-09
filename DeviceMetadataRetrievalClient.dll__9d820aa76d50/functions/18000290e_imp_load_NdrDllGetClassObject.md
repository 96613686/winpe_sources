# __imp_load_NdrDllGetClassObject

- ea: `0x18000290e`
- end: `0x18000291a`
- name: `__imp_load_NdrDllGetClassObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000208a`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000290e`

## pseudocode

```c
__int64 load_NdrDllGetClassObject()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000290e  lea     rax, __imp_NdrDllGetClassObject
0x180002915  jmp     __tailMerge_rpcrt4_dll
```
