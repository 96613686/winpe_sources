# HamCreateAutoRestartActivity

- ea: `0x18001ac50`
- end: `0x18001ad03`
- name: `HamCreateAutoRestartActivity`
- size: `179`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001ac50`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001ac74`
- `ntdll!RtlLengthSid` at `0x18001ac74`
- `RPCRT4!NdrClientCall3` at `0x18001acce`
- `RPCRT4!NdrClientCall3` at `0x18001acce`
- `RPCRT4!RpcExceptionFilter` at `0x18001bb3e`
- `RPCRT4!RpcExceptionFilter` at `0x18001bb3e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001ace4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001ace4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamCreateAutoRestartActivity(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rsi
  ULONG v9; // eax
  CLIENT_CALL_RETURN result; // rax
  ULONG v11; // [rsp+30h] [rbp-78h]
  int v12; // [rsp+38h] [rbp-70h]
  int v13; // [rsp+40h] [rbp-68h]

  v8 = a2 + 464;
  v9 = RtlLengthSid((PSID)(a2 + 464));
  v13 = *(_DWORD *)(a2 + 536);
  v12 = *(_DWORD *)(a2 + 532);
  v11 = v9;
  result.Pointer = NdrClientCall3(
                     (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                     5u,
                     0,
                     *a1,
                     a2,
                     v8,
                     v11,
                     v12,
                     v13,
                     *(_QWORD *)(a2 + 544),
                     a3,
                     a4).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001ac50  push    rbx
0x18001ac52  push    rsi
0x18001ac53  push    rdi
0x18001ac54  push    r12
0x18001ac56  push    r14
0x18001ac58  push    r15
0x18001ac5a  sub     rsp, 78h
0x18001ac5e  mov     r14, r9
0x18001ac61  mov     r15, r8
0x18001ac64  mov     rdi, rdx
0x18001ac67  mov     r12, rcx
0x18001ac6a  lea     rsi, [rdx+1D0h]
0x18001ac71  mov     rcx, rsi; Sid
0x18001ac74  call    cs:__imp_RtlLengthSid
0x18001ac7a  nop
0x18001ac7b  mov     r8, [rdi+220h]
0x18001ac82  mov     edx, [rdi+218h]
0x18001ac88  mov     ecx, [rdi+214h]
0x18001ac8e  xor     ebx, ebx
0x18001ac90  mov     [rsp+0A8h+arg_0], rbx
0x18001ac98  mov     [rsp+0A8h+var_50], r14
0x18001ac9d  mov     [rsp+0A8h+var_58], r15
0x18001aca2  mov     [rsp+0A8h+var_60], r8
0x18001aca7  mov     [rsp+0A8h+var_68], edx
0x18001acab  mov     [rsp+0A8h+var_70], ecx
0x18001acaf  mov     [rsp+0A8h+var_78], eax
0x18001acb3  mov     [rsp+0A8h+var_80], rsi
0x18001acb8  mov     [rsp+0A8h+var_88], rdi
0x18001acbd  mov     r9, [r12]
0x18001acc1  xor     r8d, r8d; pReturnValue
0x18001acc4  lea     edx, [rbx+5]; nProcNum
0x18001acc7  lea     rcx, pProxyInfo; pProxyInfo
0x18001acce  call    cs:__imp_NdrClientCall3
0x18001acd4  mov     [rsp+0A8h+arg_0], rax
0x18001acdc  mov     [rsp+0A8h+var_48], eax
0x18001ace0  jmp     short loc_18001ACF0
0x18001ace2  mov     ecx, eax; Status
0x18001ace4  call    cs:__imp_I_RpcMapWin32Status
0x18001acea  mov     [rsp+0A8h+var_48], eax
0x18001acee  xor     ebx, ebx
0x18001acf0  test    eax, eax
0x18001acf2  cmovns  eax, ebx
0x18001acf5  add     rsp, 78h
0x18001acf9  pop     r15
0x18001acfb  pop     r14
0x18001acfd  pop     r12
0x18001acff  pop     rdi
0x18001ad00  pop     rsi
0x18001ad01  pop     rbx
0x18001ad02  retn
0x18001bb30  push    rbp
0x18001bb32  sub     rsp, 60h
0x18001bb36  mov     rbp, rdx
0x18001bb39  mov     rcx, [rcx]
0x18001bb3c  mov     ecx, [rcx]; ExceptionCode
0x18001bb3e  call    cs:__imp_RpcExceptionFilter
0x18001bb44  nop
0x18001bb45  add     rsp, 60h
0x18001bb49  pop     rbp
0x18001bb4a  retn
```
