# CmsRpcClt_CreateStorageTransacted

- ea: `0x18000e028`
- end: `0x18000e060`
- name: `CmsRpcClt_CreateStorageTransacted`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cd0c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e055`
- `RPCRT4!NdrClientCall3` at `0x18000e055`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateStorageTransacted(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x45u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000e028  sub     rsp, 48h
0x18000e02c  mov     rax, [rsp+48h+arg_20]
0x18000e031  mov     [rsp+48h+var_10], rax
0x18000e036  mov     [rsp+48h+var_18], r9
0x18000e03b  mov     r9, rcx
0x18000e03e  mov     [rsp+48h+var_20], r8
0x18000e043  lea     rcx, pProxyInfo; pProxyInfo
0x18000e04a  xor     r8d, r8d; pReturnValue
0x18000e04d  mov     [rsp+48h+var_28], edx
0x18000e051  lea     edx, [r8+45h]; nProcNum
0x18000e055  call    cs:__imp_NdrClientCall3
0x18000e05b  add     rsp, 48h
0x18000e05f  retn
```
