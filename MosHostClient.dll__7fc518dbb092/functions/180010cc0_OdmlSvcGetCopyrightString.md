# OdmlSvcGetCopyrightString

- ea: `0x180010cc0`
- end: `0x180010cea`
- name: `OdmlSvcGetCopyrightString`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010cdf`
- `RPCRT4!NdrClientCall3` at `0x180010cdf`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcGetCopyrightString(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 0xBu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180010cc0  sub     rsp, 38h
0x180010cc4  mov     [rsp+38h+var_10], r8
0x180010cc9  mov     r9, rcx
0x180010ccc  xor     r8d, r8d; pReturnValue
0x180010ccf  mov     [rsp+38h+var_18], rdx
0x180010cd4  lea     rcx, stru_180013630; pProxyInfo
0x180010cdb  lea     edx, [r8+0Bh]; nProcNum
0x180010cdf  call    cs:__imp_NdrClientCall3
0x180010ce5  add     rsp, 38h
0x180010ce9  retn
```
