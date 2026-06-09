# MosHostDeleteDataAsync

- ea: `0x1800108d0`
- end: `0x1800108ff`
- name: `MosHostDeleteDataAsync`
- size: `47`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!Ndr64AsyncClientCall` at `0x1800108f4`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800108f4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostDeleteDataAsync(__int64 a1, __int64 a2, int a3, int a4)
{
  return Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0x10u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800108d0  sub     rsp, 48h
0x1800108d4  mov     [rsp+48h+var_18], r9d
0x1800108d9  mov     r9, rcx
0x1800108dc  mov     [rsp+48h+var_20], r8d
0x1800108e1  lea     rcx, stru_1800140C0; pProxyInfo
0x1800108e8  xor     r8d, r8d; pReturnValue
0x1800108eb  mov     [rsp+48h+var_28], rdx
0x1800108f0  lea     edx, [r8+10h]; nProcNum
0x1800108f4  call    cs:__imp_Ndr64AsyncClientCall
0x1800108fa  add     rsp, 48h
0x1800108fe  retn
```
