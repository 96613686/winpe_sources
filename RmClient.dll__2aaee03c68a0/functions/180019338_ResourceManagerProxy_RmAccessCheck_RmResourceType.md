# ResourceManagerProxy::RmAccessCheck(RmResourceType)

- ea: `0x180019338`
- end: `0x180019381`
- name: `?RmAccessCheck@ResourceManagerProxy@@QEAAJW4RmResourceType@@@Z`
- size: `73`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180019450`

## callees

- `0x180019338`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001935b`
- `RPCRT4!NdrClientCall3` at `0x18001935b`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001bab6`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001bab6`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall ResourceManagerProxy::RmAccessCheck(__int64 a1, int a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001D000, 4u, 0, *(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x180019338  sub     rsp, 48h
0x18001933c  mov     [rsp+48h+arg_10], 0
0x180019345  mov     [rsp+48h+var_28], edx
0x180019349  mov     r9, [rcx+8]
0x18001934d  xor     r8d, r8d; pReturnValue
0x180019350  lea     edx, [r8+4]; nProcNum
0x180019354  lea     rcx, stru_18001D000; pProxyInfo
0x18001935b  call    cs:__imp_NdrClientCall3
0x180019361  mov     [rsp+48h+arg_10], rax
0x180019366  mov     [rsp+48h+var_18], eax
0x18001936a  jmp     short loc_18001937C
0x18001936c  test    eax, eax
0x18001936e  jle     short loc_180019378
0x180019370  movzx   eax, ax
0x180019373  or      eax, 80070000h
0x180019378  mov     [rsp+48h+var_18], eax
0x18001937c  add     rsp, 48h
0x180019380  retn
0x18001baa8  push    rbp
0x18001baaa  sub     rsp, 30h
0x18001baae  mov     rbp, rdx
0x18001bab1  mov     rcx, [rcx]
0x18001bab4  mov     ecx, [rcx]; ExceptionCode
0x18001bab6  call    cs:__imp_I_RpcExceptionFilter
0x18001babc  nop
0x18001babd  add     rsp, 30h
0x18001bac1  pop     rbp
0x18001bac2  retn
```
