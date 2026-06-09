# __imp_load_RpcBindingCreateW

- ea: `0x180014af3`
- end: `0x180014aff`
- name: `__imp_load_RpcBindingCreateW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800143d9`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180014af3`

## pseudocode

```c
__int64 load_RpcBindingCreateW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180014af3  lea     rax, __imp_RpcBindingCreateW
0x180014afa  jmp     __tailMerge_rpcrt4_dll
```
