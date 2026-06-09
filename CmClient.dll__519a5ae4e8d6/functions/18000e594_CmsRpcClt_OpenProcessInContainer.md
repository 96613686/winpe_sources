# CmsRpcClt_OpenProcessInContainer

- ea: `0x18000e594`
- end: `0x18000e5c2`
- name: `CmsRpcClt_OpenProcessInContainer`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002524`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e5b7`
- `RPCRT4!NdrClientCall3` at `0x18000e5b7`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenProcessInContainer(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x28u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e594  sub     rsp, 48h
0x18000e598  mov     [rsp+48h+var_18], r9
0x18000e59d  mov     r9, rcx
0x18000e5a0  mov     [rsp+48h+var_20], r8
0x18000e5a5  lea     rcx, pProxyInfo; pProxyInfo
0x18000e5ac  xor     r8d, r8d; pReturnValue
0x18000e5af  mov     [rsp+48h+var_28], edx
0x18000e5b3  lea     edx, [r8+28h]; nProcNum
0x18000e5b7  call    cs:__imp_NdrClientCall3
0x18000e5bd  add     rsp, 48h
0x18000e5c1  retn
```
