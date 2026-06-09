# ResourceManagerProxy::RmAccessCheck(RmResourceType,ulong)

- ea: `0x18000dc00`
- end: `0x18000dc4e`
- name: `?RmAccessCheck@ResourceManagerProxy@@QEAAJW4RmResourceType@@K@Z`
- size: `78`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000db70`

## callees

- `0x18000dc00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dc28`
- `RPCRT4!NdrClientCall3` at `0x18000dc28`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001b400`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001b400`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall ResourceManagerProxy::RmAccessCheck(__int64 a1, int a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001D000, 3u, 0, *(_QWORD *)(a1 + 8), a2, a3);
}

```

## disassembly

```asm
0x18000dc00  sub     rsp, 48h
0x18000dc04  mov     [rsp+48h+arg_18], 0
0x18000dc0d  mov     [rsp+48h+var_20], r8d
0x18000dc12  mov     [rsp+48h+var_28], edx
0x18000dc16  mov     r9, [rcx+8]
0x18000dc1a  xor     r8d, r8d; pReturnValue
0x18000dc1d  lea     edx, [r8+3]; nProcNum
0x18000dc21  lea     rcx, stru_18001D000; pProxyInfo
0x18000dc28  call    cs:__imp_NdrClientCall3
0x18000dc2e  mov     [rsp+48h+arg_18], rax
0x18000dc33  mov     [rsp+48h+var_18], eax
0x18000dc37  jmp     short loc_18000DC49
0x18000dc39  test    eax, eax
0x18000dc3b  jle     short loc_18000DC45
0x18000dc3d  movzx   eax, ax
0x18000dc40  or      eax, 80070000h
0x18000dc45  mov     [rsp+48h+var_18], eax
0x18000dc49  add     rsp, 48h
0x18000dc4d  retn
0x18001b3f2  push    rbp
0x18001b3f4  sub     rsp, 30h
0x18001b3f8  mov     rbp, rdx
0x18001b3fb  mov     rcx, [rcx]
0x18001b3fe  mov     ecx, [rcx]; ExceptionCode
0x18001b400  call    cs:__imp_I_RpcExceptionFilter
0x18001b406  nop
0x18001b407  add     rsp, 30h
0x18001b40b  pop     rbp
0x18001b40c  retn
```
