# __imp_load_RpcBindingCreateW

- ea: `0x1800104f4`
- end: `0x180010500`
- name: `__imp_load_RpcBindingCreateW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001042d`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x1800104f4`

## pseudocode

```c
__int64 load_RpcBindingCreateW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800104f4  lea     rax, __imp_RpcBindingCreateW
0x1800104fb  jmp     __tailMerge_rpcrt4_dll
```
