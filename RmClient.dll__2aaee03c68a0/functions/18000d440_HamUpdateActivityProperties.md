# HamUpdateActivityProperties

- ea: `0x18000d440`
- end: `0x18000d49b`
- name: `HamUpdateActivityProperties`
- size: `91`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000d440`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d46e`
- `RPCRT4!NdrClientCall3` at `0x18000d46e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b3ae`
- `RPCRT4!RpcExceptionFilter` at `0x18001b3ae`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d481`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000d481`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcUpdateActivityProperties` at `0x18000d493`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcUpdateActivityProperties` at `0x18000d493`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamUpdateActivityProperties(_QWORD *a1, __int64 a2, __int64 a3)
{
  if ( !a1[1] )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xAu, 0, *a1, a2, a3);
  return (CLIENT_CALL_RETURN)HampInProcUpdateActivityProperties(a1[1]);
}

```

## disassembly

```asm
0x18000d440  sub     rsp, 48h
0x18000d444  mov     rax, [rcx+8]
0x18000d448  test    rax, rax
0x18000d44b  jnz     short loc_18000D490
0x18000d44d  mov     [rsp+48h+arg_0], rax
0x18000d452  mov     [rsp+48h+var_20], r8
0x18000d457  mov     [rsp+48h+var_28], rdx
0x18000d45c  mov     r9, [rcx]
0x18000d45f  xor     r8d, r8d; pReturnValue
0x18000d462  mov     edx, 0Ah; nProcNum
0x18000d467  lea     rcx, pProxyInfo; pProxyInfo
0x18000d46e  call    cs:__imp_NdrClientCall3
0x18000d474  mov     [rsp+48h+arg_0], rax
0x18000d479  mov     [rsp+48h+var_18], eax
0x18000d47d  jmp     short loc_18000D48B
0x18000d47f  mov     ecx, eax; Status
0x18000d481  call    cs:__imp_I_RpcMapWin32Status
0x18000d487  mov     [rsp+48h+var_18], eax
0x18000d48b  add     rsp, 48h
0x18000d48f  retn
0x18000d490  mov     rcx, rax
0x18000d493  call    cs:__imp_HampInProcUpdateActivityProperties
0x18000d499  jmp     short loc_18000D48B
0x18001b3a0  push    rbp
0x18001b3a2  sub     rsp, 30h
0x18001b3a6  mov     rbp, rdx
0x18001b3a9  mov     rcx, [rcx]
0x18001b3ac  mov     ecx, [rcx]; ExceptionCode
0x18001b3ae  call    cs:__imp_RpcExceptionFilter
0x18001b3b4  nop
0x18001b3b5  add     rsp, 30h
0x18001b3b9  pop     rbp
0x18001b3ba  retn
```
