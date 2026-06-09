# CmsRpcClt_CreateStorage

- ea: `0x18000dfe8`
- end: `0x18000e020`
- name: `CmsRpcClt_CreateStorage`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e04`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e015`
- `RPCRT4!NdrClientCall3` at `0x18000e015`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateStorage(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Bu, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000dfe8  sub     rsp, 48h
0x18000dfec  mov     rax, [rsp+48h+arg_20]
0x18000dff1  mov     [rsp+48h+var_10], rax
0x18000dff6  mov     [rsp+48h+var_18], r9
0x18000dffb  mov     r9, rcx
0x18000dffe  mov     [rsp+48h+var_20], r8
0x18000e003  lea     rcx, pProxyInfo; pProxyInfo
0x18000e00a  xor     r8d, r8d; pReturnValue
0x18000e00d  mov     [rsp+48h+var_28], edx
0x18000e011  lea     edx, [r8+2Bh]; nProcNum
0x18000e015  call    cs:__imp_NdrClientCall3
0x18000e01b  add     rsp, 48h
0x18000e01f  retn
```
