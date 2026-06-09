# __imp_load_RpcMgmtSetComTimeout

- ea: `0x180020454`
- end: `0x180020460`
- name: `__imp_load_RpcMgmtSetComTimeout`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ef90`

## import_xrefs

- `RPCRT4!RpcMgmtSetComTimeout` at `0x180020454`

## pseudocode

```c
__int64 load_RpcMgmtSetComTimeout()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180020454  lea     rax, __imp_RpcMgmtSetComTimeout
0x18002045b  jmp     __tailMerge_rpcrt4_dll
```
