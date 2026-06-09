# MosHostGetBrowseCacheSizeInMBytes

- ea: `0x180010910`
- end: `0x180010935`
- name: `MosHostGetBrowseCacheSizeInMBytes`
- size: `37`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001092a`
- `RPCRT4!NdrClientCall3` at `0x18001092a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostGetBrowseCacheSizeInMBytes(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 4u, 0, a1, a2);
}

```

## disassembly

```asm
0x180010910  sub     rsp, 38h
0x180010914  xor     r8d, r8d; pReturnValue
0x180010917  mov     [rsp+38h+var_18], rdx
0x18001091c  mov     r9, rcx
0x18001091f  lea     rcx, stru_1800140C0; pProxyInfo
0x180010926  lea     edx, [r8+4]; nProcNum
0x18001092a  call    cs:__imp_NdrClientCall3
0x180010930  add     rsp, 38h
0x180010934  retn
```
