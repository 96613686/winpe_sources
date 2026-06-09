# CmsRpcClt_CopyLayerTrace

- ea: `0x18000ddac`
- end: `0x18000dde4`
- name: `CmsRpcClt_CopyLayerTrace`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b874`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ddd9`
- `RPCRT4!NdrClientCall3` at `0x18000ddd9`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CopyLayerTrace(__int64 a1, __int128 *a2, __int64 a3)
{
  __int128 v4; // [rsp+30h] [rbp-18h] BYREF

  v4 = *a2;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x4Du, 0, a1, &v4, a3);
}

```

## disassembly

```asm
0x18000ddac  sub     rsp, 48h
0x18000ddb0  movups  xmm0, xmmword ptr [rdx]
0x18000ddb3  mov     [rsp+48h+var_20], r8
0x18000ddb8  lea     rax, [rsp+48h+var_18]
0x18000ddbd  xor     r8d, r8d; pReturnValue
0x18000ddc0  mov     [rsp+48h+var_28], rax
0x18000ddc5  mov     r9, rcx
0x18000ddc8  lea     rcx, pProxyInfo; pProxyInfo
0x18000ddcf  movdqu  [rsp+48h+var_18], xmm0
0x18000ddd5  lea     edx, [r8+4Dh]; nProcNum
0x18000ddd9  call    cs:__imp_NdrClientCall3
0x18000dddf  add     rsp, 48h
0x18000dde3  retn
```
