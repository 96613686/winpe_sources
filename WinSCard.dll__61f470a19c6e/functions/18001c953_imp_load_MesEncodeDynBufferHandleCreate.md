# __imp_load_MesEncodeDynBufferHandleCreate

- ea: `0x18001c953`
- end: `0x18001c95f`
- name: `__imp_load_MesEncodeDynBufferHandleCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c856`

## import_xrefs

- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001c953`

## pseudocode

```c
__int64 load_MesEncodeDynBufferHandleCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001c953  lea     rax, __imp_MesEncodeDynBufferHandleCreate
0x18001c95a  jmp     __tailMerge_rpcrt4_dll
```
