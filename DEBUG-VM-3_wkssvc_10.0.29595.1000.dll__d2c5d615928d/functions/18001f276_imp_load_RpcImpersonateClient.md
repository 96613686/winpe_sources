# __imp_load_RpcImpersonateClient

- ea: `0x18001f276`
- end: `0x18001f282`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001ef90`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001f276`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001f276  lea     rax, __imp_RpcImpersonateClient
0x18001f27d  jmp     __tailMerge_rpcrt4_dll
```
