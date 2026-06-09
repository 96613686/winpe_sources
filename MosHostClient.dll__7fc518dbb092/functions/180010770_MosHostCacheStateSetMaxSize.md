# MosHostCacheStateSetMaxSize

- ea: `0x180010770`
- end: `0x180010794`
- name: `MosHostCacheStateSetMaxSize`
- size: `36`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010789`
- `RPCRT4!NdrClientCall3` at `0x180010789`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCacheStateSetMaxSize(__int64 a1, int a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 8u, 0, a1, a2);
}

```

## disassembly

```asm
0x180010770  sub     rsp, 38h
0x180010774  xor     r8d, r8d; pReturnValue
0x180010777  mov     [rsp+38h+var_18], edx
0x18001077b  mov     r9, rcx
0x18001077e  lea     rcx, stru_1800140C0; pProxyInfo
0x180010785  lea     edx, [r8+8]; nProcNum
0x180010789  call    cs:__imp_NdrClientCall3
0x18001078f  add     rsp, 38h
0x180010793  retn
```
