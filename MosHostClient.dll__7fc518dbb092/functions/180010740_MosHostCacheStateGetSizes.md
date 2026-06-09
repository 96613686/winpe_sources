# MosHostCacheStateGetSizes

- ea: `0x180010740`
- end: `0x18001076a`
- name: `MosHostCacheStateGetSizes`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001075f`
- `RPCRT4!NdrClientCall3` at `0x18001075f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCacheStateGetSizes(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 9u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180010740  sub     rsp, 38h
0x180010744  mov     [rsp+38h+var_10], r8
0x180010749  mov     r9, rcx
0x18001074c  xor     r8d, r8d; pReturnValue
0x18001074f  mov     [rsp+38h+var_18], rdx
0x180010754  lea     rcx, stru_1800140C0; pProxyInfo
0x18001075b  lea     edx, [r8+9]; nProcNum
0x18001075f  call    cs:__imp_NdrClientCall3
0x180010765  add     rsp, 38h
0x180010769  retn
```
