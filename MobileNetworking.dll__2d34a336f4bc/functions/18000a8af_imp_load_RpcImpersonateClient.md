# __imp_load_RpcImpersonateClient

- ea: `0x18000a8af`
- end: `0x18000a8bb`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000a830`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000a8af`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000a8af  lea     rax, __imp_RpcImpersonateClient
0x18000a8b6  jmp     __tailMerge_rpcrt4_dll
```
