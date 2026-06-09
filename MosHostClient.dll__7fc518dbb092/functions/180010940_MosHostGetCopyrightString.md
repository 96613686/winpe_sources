# MosHostGetCopyrightString

- ea: `0x180010940`
- end: `0x18001096a`
- name: `MosHostGetCopyrightString`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001095f`
- `RPCRT4!NdrClientCall3` at `0x18001095f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostGetCopyrightString(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0x11u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180010940  sub     rsp, 38h
0x180010944  mov     [rsp+38h+var_10], r8
0x180010949  mov     r9, rcx
0x18001094c  xor     r8d, r8d; pReturnValue
0x18001094f  mov     [rsp+38h+var_18], rdx
0x180010954  lea     rcx, stru_1800140C0; pProxyInfo
0x18001095b  lea     edx, [r8+11h]; nProcNum
0x18001095f  call    cs:__imp_NdrClientCall3
0x180010965  add     rsp, 38h
0x180010969  retn
```
