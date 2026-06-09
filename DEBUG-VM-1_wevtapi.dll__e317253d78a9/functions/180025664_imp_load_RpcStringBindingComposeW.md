# __imp_load_RpcStringBindingComposeW

- ea: `0x180025664`
- end: `0x180025670`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180025579`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180025664`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180025664  lea     rax, __imp_RpcStringBindingComposeW
0x18002566b  jmp     __tailMerge_rpcrt4_dll
```
