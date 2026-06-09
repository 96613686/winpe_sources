# OdmlSvcOpen

- ea: `0x180010db0`
- end: `0x180010ddc`
- name: `OdmlSvcOpen`
- size: `44`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010dd1`
- `RPCRT4!NdrClientCall3` at `0x180010dd1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcOpen(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 0, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010db0  sub     rsp, 48h
0x180010db4  mov     [rsp+48h+var_18], r9
0x180010db9  mov     r9, rcx
0x180010dbc  mov     [rsp+48h+var_20], r8
0x180010dc1  lea     rcx, stru_180013630; pProxyInfo
0x180010dc8  mov     [rsp+48h+var_28], edx
0x180010dcc  xor     r8d, r8d; pReturnValue
0x180010dcf  xor     edx, edx; nProcNum
0x180010dd1  call    cs:__imp_NdrClientCall3
0x180010dd7  add     rsp, 48h
0x180010ddb  retn
```
