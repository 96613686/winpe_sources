# MosHostGetResourceDirectory

- ea: `0x180010a30`
- end: `0x180010a5a`
- name: `MosHostGetResourceDirectory`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010a4f`
- `RPCRT4!NdrClientCall3` at `0x180010a4f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostGetResourceDirectory(__int64 a1, __int64 a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 3u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180010a30  sub     rsp, 38h
0x180010a34  mov     [rsp+38h+var_10], r8d
0x180010a39  mov     r9, rcx
0x180010a3c  xor     r8d, r8d; pReturnValue
0x180010a3f  mov     [rsp+38h+var_18], rdx
0x180010a44  lea     rcx, stru_1800140C0; pProxyInfo
0x180010a4b  lea     edx, [r8+3]; nProcNum
0x180010a4f  call    cs:__imp_NdrClientCall3
0x180010a55  add     rsp, 38h
0x180010a59  retn
```
