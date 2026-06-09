# __imp_load_RpcBindingCreateW

- ea: `0x18000213c`
- end: `0x180002148`
- name: `__imp_load_RpcBindingCreateW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001f5a`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18000213c`

## pseudocode

```c
__int64 load_RpcBindingCreateW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000213c  lea     rax, __imp_RpcBindingCreateW
0x180002143  jmp     __tailMerge_rpcrt4_dll
```
