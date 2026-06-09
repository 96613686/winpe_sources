# CmsRpcClt_OpenLayer

- ea: `0x18000e554`
- end: `0x18000e58c`
- name: `CmsRpcClt_OpenLayer`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a98`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e581`
- `RPCRT4!NdrClientCall3` at `0x18000e581`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenLayer(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x38u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000e554  mov     r11, rsp
0x18000e557  sub     rsp, 48h
0x18000e55b  mov     rax, [rsp+48h+arg_20]
0x18000e560  mov     [r11-10h], rax
0x18000e564  mov     [r11-18h], r9
0x18000e568  mov     r9, rcx
0x18000e56b  mov     [r11-20h], r8d
0x18000e56f  lea     rcx, pProxyInfo; pProxyInfo
0x18000e576  xor     r8d, r8d; pReturnValue
0x18000e579  mov     [r11-28h], rdx
0x18000e57d  lea     edx, [r8+38h]; nProcNum
0x18000e581  call    cs:__imp_NdrClientCall3
0x18000e587  add     rsp, 48h
0x18000e58b  retn
```
