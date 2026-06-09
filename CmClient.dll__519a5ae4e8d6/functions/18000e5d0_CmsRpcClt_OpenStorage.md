# CmsRpcClt_OpenStorage

- ea: `0x18000e5d0`
- end: `0x18000e5ff`
- name: `CmsRpcClt_OpenStorage`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e5f4`
- `RPCRT4!NdrClientCall3` at `0x18000e5f4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenStorage(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Cu, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e5d0  sub     rsp, 48h
0x18000e5d4  mov     [rsp+48h+var_18], r9
0x18000e5d9  mov     r9, rcx
0x18000e5dc  mov     [rsp+48h+var_20], r8d
0x18000e5e1  lea     rcx, pProxyInfo; pProxyInfo
0x18000e5e8  xor     r8d, r8d; pReturnValue
0x18000e5eb  mov     [rsp+48h+var_28], rdx
0x18000e5f0  lea     edx, [r8+2Ch]; nProcNum
0x18000e5f4  call    cs:__imp_NdrClientCall3
0x18000e5fa  add     rsp, 48h
0x18000e5fe  retn
```
