# MosHostCacheStateUnuseSlot

- ea: `0x180010800`
- end: `0x180010824`
- name: `MosHostCacheStateUnuseSlot`
- size: `36`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010819`
- `RPCRT4!NdrClientCall3` at `0x180010819`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCacheStateUnuseSlot(__int64 a1, int a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0xBu, 0, a1, a2);
}

```

## disassembly

```asm
0x180010800  sub     rsp, 38h
0x180010804  xor     r8d, r8d; pReturnValue
0x180010807  mov     [rsp+38h+var_18], edx
0x18001080b  mov     r9, rcx
0x18001080e  lea     rcx, stru_1800140C0; pProxyInfo
0x180010815  lea     edx, [r8+0Bh]; nProcNum
0x180010819  call    cs:__imp_NdrClientCall3
0x18001081f  add     rsp, 38h
0x180010823  retn
```
