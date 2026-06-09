# OdmlSvcRemoveMapPackages

- ea: `0x180010df0`
- end: `0x180010e1a`
- name: `OdmlSvcRemoveMapPackages`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010e0f`
- `RPCRT4!NdrClientCall3` at `0x180010e0f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcRemoveMapPackages(__int64 a1, __int64 a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 8u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180010df0  sub     rsp, 38h
0x180010df4  mov     [rsp+38h+var_10], r8d
0x180010df9  mov     r9, rcx
0x180010dfc  xor     r8d, r8d; pReturnValue
0x180010dff  mov     [rsp+38h+var_18], rdx
0x180010e04  lea     rcx, stru_180013630; pProxyInfo
0x180010e0b  lea     edx, [r8+8]; nProcNum
0x180010e0f  call    cs:__imp_NdrClientCall3
0x180010e15  add     rsp, 38h
0x180010e19  retn
```
