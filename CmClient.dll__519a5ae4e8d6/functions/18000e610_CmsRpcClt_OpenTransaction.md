# CmsRpcClt_OpenTransaction

- ea: `0x18000e610`
- end: `0x18000e63f`
- name: `CmsRpcClt_OpenTransaction`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e634`
- `RPCRT4!NdrClientCall3` at `0x18000e634`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenTransaction(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x3Au, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e610  sub     rsp, 48h
0x18000e614  mov     [rsp+48h+var_18], r9
0x18000e619  mov     r9, rcx
0x18000e61c  mov     [rsp+48h+var_20], r8d
0x18000e621  lea     rcx, pProxyInfo; pProxyInfo
0x18000e628  xor     r8d, r8d; pReturnValue
0x18000e62b  mov     [rsp+48h+var_28], rdx
0x18000e630  lea     edx, [r8+3Ah]; nProcNum
0x18000e634  call    cs:__imp_NdrClientCall3
0x18000e63a  add     rsp, 48h
0x18000e63e  retn
```
