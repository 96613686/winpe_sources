# MosHostGetDataDirectory

- ea: `0x180010a00`
- end: `0x180010a2a`
- name: `MosHostGetDataDirectory`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010a1f`
- `RPCRT4!NdrClientCall3` at `0x180010a1f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostGetDataDirectory(__int64 a1, __int64 a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 2u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180010a00  sub     rsp, 38h
0x180010a04  mov     [rsp+38h+var_10], r8d
0x180010a09  mov     r9, rcx
0x180010a0c  xor     r8d, r8d; pReturnValue
0x180010a0f  mov     [rsp+38h+var_18], rdx
0x180010a14  lea     rcx, stru_1800140C0; pProxyInfo
0x180010a1b  lea     edx, [r8+2]; nProcNum
0x180010a1f  call    cs:__imp_NdrClientCall3
0x180010a25  add     rsp, 38h
0x180010a29  retn
```
