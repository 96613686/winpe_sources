# CmsRpcClt_CreateActivity

- ea: `0x18000de10`
- end: `0x18000de3e`
- name: `CmsRpcClt_CreateActivity`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d88`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000de33`
- `RPCRT4!NdrClientCall3` at `0x18000de33`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateActivity(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x18u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000de10  sub     rsp, 48h
0x18000de14  mov     [rsp+48h+var_18], r9
0x18000de19  mov     r9, rcx
0x18000de1c  mov     [rsp+48h+var_20], r8
0x18000de21  lea     rcx, pProxyInfo; pProxyInfo
0x18000de28  xor     r8d, r8d; pReturnValue
0x18000de2b  mov     [rsp+48h+var_28], edx
0x18000de2f  lea     edx, [r8+18h]; nProcNum
0x18000de33  call    cs:__imp_NdrClientCall3
0x18000de39  add     rsp, 48h
0x18000de3d  retn
```
