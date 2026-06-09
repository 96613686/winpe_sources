# CmsRpcClt_GetDebugLayerPath

- ea: `0x18000eb40`
- end: `0x18000eb7c`
- name: `CmsRpcClt_GetDebugLayerPath`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b7f0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000eb71`
- `RPCRT4!NdrClientCall3` at `0x18000eb71`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_GetDebugLayerPath(__int64 a1, __int128 *a2, __int64 a3, __int64 a4)
{
  __int128 v5; // [rsp+40h] [rbp-18h] BYREF

  v5 = *a2;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013E20, 1u, 0, a1, &v5, a3, a4);
}

```

## disassembly

```asm
0x18000eb40  mov     rax, rsp
0x18000eb43  sub     rsp, 58h
0x18000eb47  movups  xmm0, xmmword ptr [rdx]
0x18000eb4a  mov     [rax-28h], r9
0x18000eb4e  mov     r9, rcx
0x18000eb51  mov     [rax-30h], r8
0x18000eb55  xor     r8d, r8d; pReturnValue
0x18000eb58  movdqu  xmmword ptr [rax-18h], xmm0
0x18000eb5d  lea     rax, [rax-18h]
0x18000eb61  lea     rcx, stru_180013E20; pProxyInfo
0x18000eb68  mov     [rsp+58h+var_38], rax
0x18000eb6d  lea     edx, [r8+1]; nProcNum
0x18000eb71  call    cs:__imp_NdrClientCall3
0x18000eb77  add     rsp, 58h
0x18000eb7b  retn
```
