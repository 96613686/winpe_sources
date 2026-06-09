# __imp_load_NdrDllGetClassObject

- ea: `0x180002d08`
- end: `0x180002d14`
- name: `__imp_load_NdrDllGetClassObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c89`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180002d08`

## pseudocode

```c
__int64 load_NdrDllGetClassObject()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180002d08  lea     rax, __imp_NdrDllGetClassObject
0x180002d0f  jmp     __tailMerge_rpcrt4_dll
```
