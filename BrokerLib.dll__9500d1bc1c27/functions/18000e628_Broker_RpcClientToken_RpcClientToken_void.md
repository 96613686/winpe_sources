# Broker::RpcClientToken::RpcClientToken(void)

- ea: `0x18000e628`
- end: `0x18000e7c2`
- name: `??0RpcClientToken@Broker@@QEAA@XZ`
- size: `410`
- prototype: `__int64 __fastcall(Broker::RpcClientToken *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ab8c`

## callees

- `0x180009e94`
- `0x18000b3a4`
- `0x18000e628`
- `0x18000e7c8`
- `0x1800139f8`
- `0x1800165da`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000e67a`
- `RPCRT4!RpcRevertToSelf` at `0x18000e67a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e64c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e64c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e656`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e656`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e66c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e712`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Broker::RpcClientToken *__fastcall Broker::RpcClientToken::RpcClientToken(Broker::RpcClientToken *this)
{
  unsigned int v2; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void **v6; // [rsp+20h] [rbp-50h] BYREF
  __int128 v7; // [rsp+28h] [rbp-48h]
  int v8; // [rsp+38h] [rbp-38h]
  unsigned int v9; // [rsp+40h] [rbp-30h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-28h] BYREF
  int v11; // [rsp+60h] [rbp-10h]
  unsigned int v12; // [rsp+68h] [rbp-8h]
  char v13; // [rsp+80h] [rbp+10h] BYREF

  Broker::RpcScopedImpersonation::RpcScopedImpersonation((Broker::RpcScopedImpersonation *)&v13);
  v2 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)this);
  if ( v2 )
  {
    v7 = 0;
    v8 = 1;
    v6 = &Broker::Win32Error::`vftable';
    v9 = v2;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v2);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v6);
    v11 = v8;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v12 = v9;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)this + 1) )
  {
    LastError = GetLastError();
    v7 = 0;
    v8 = 1;
    v6 = &Broker::Win32Error::`vftable';
    v9 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v6);
    v11 = v8;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v12 = v9;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( RpcRevertToSelf() && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
  return this;
}

```

## disassembly

```asm
0x18000e628  mov     [rsp-8+arg_8], rbx
0x18000e62d  mov     [rsp-8+arg_10], rdi
0x18000e632  push    rbp
0x18000e633  mov     rbp, rsp
0x18000e636  sub     rsp, 70h
0x18000e63a  mov     rdi, rcx
0x18000e63d  lea     rcx, [rbp+arg_0]; this
0x18000e641  call    ??0RpcScopedImpersonation@Broker@@QEAA@XZ; Broker::RpcScopedImpersonation::RpcScopedImpersonation(void)
0x18000e646  nop
0x18000e647  mov     rdx, rdi; Pid
0x18000e64a  xor     ecx, ecx; Binding
0x18000e64c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e652  test    eax, eax
0x18000e654  jnz     short loc_18000E69D
0x18000e656  call    cs:__imp_GetCurrentThread
0x18000e65c  mov     rcx, rax; ThreadHandle
0x18000e65f  lea     r9, [rdi+8]; TokenHandle
0x18000e663  mov     edx, 8; DesiredAccess
0x18000e668  lea     r8d, [rdx-7]; OpenAsSelf
0x18000e66c  call    cs:__imp_OpenThreadToken
0x18000e672  test    eax, eax
0x18000e674  jz      loc_18000E712
0x18000e67a  call    cs:__imp_RpcRevertToSelf
0x18000e680  test    eax, eax
0x18000e682  jnz     loc_18000E78D
0x18000e688  mov     rax, rdi
0x18000e68b  lea     r11, [rsp+70h+var_s0]
0x18000e690  mov     rbx, [r11+18h]
0x18000e694  mov     rdi, [r11+20h]
0x18000e698  mov     rsp, r11
0x18000e69b  pop     rbp
0x18000e69c  retn
0x18000e69d  xorps   xmm0, xmm0
0x18000e6a0  movups  [rbp+var_48], xmm0
0x18000e6a4  mov     [rbp+var_38], 1
0x18000e6ab  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000e6b2  mov     [rbp+var_50], rbx
0x18000e6b6  mov     [rbp+var_30], eax
0x18000e6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6c0  test    byte ptr [rcx+1Ch], 8
0x18000e6c4  jz      short loc_18000E6E4
0x18000e6c6  cmp     byte ptr [rcx+19h], 2
0x18000e6ca  jb      short loc_18000E6E4
0x18000e6cc  mov     edx, 0Eh
0x18000e6d1  mov     r9d, eax
0x18000e6d4  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000e6db  mov     rcx, [rcx+10h]
0x18000e6df  call    WPP_SF_d
0x18000e6e4  lea     rdx, [rbp+var_50]; struct std::exception *
0x18000e6e8  lea     rcx, [rbp+pExceptionObject]; this
0x18000e6ec  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000e6f1  mov     eax, [rbp+var_38]
0x18000e6f4  mov     [rbp+var_10], eax
0x18000e6f7  mov     [rbp+pExceptionObject], rbx
0x18000e6fb  mov     eax, [rbp+var_30]
0x18000e6fe  mov     [rbp+var_8], eax
0x18000e701  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000e708  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e70c  call    _CxxThrowException_0
0x18000e712  call    cs:__imp_GetLastError
0x18000e718  xorps   xmm0, xmm0
0x18000e71b  movups  [rbp+var_48], xmm0
0x18000e71f  mov     [rbp+var_38], 1
0x18000e726  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000e72d  mov     [rbp+var_50], rbx
0x18000e731  mov     [rbp+var_30], eax
0x18000e734  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e73b  test    byte ptr [rcx+1Ch], 8
0x18000e73f  jz      short loc_18000E75F
0x18000e741  cmp     byte ptr [rcx+19h], 2
0x18000e745  jb      short loc_18000E75F
0x18000e747  mov     edx, 0Fh
0x18000e74c  mov     r9d, eax
0x18000e74f  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000e756  mov     rcx, [rcx+10h]
0x18000e75a  call    WPP_SF_d
0x18000e75f  lea     rdx, [rbp+var_50]; struct std::exception *
0x18000e763  lea     rcx, [rbp+pExceptionObject]; this
0x18000e767  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000e76c  mov     eax, [rbp+var_38]
0x18000e76f  mov     [rbp+var_10], eax
0x18000e772  mov     [rbp+pExceptionObject], rbx
0x18000e776  mov     eax, [rbp+var_30]
0x18000e779  mov     [rbp+var_8], eax
0x18000e77c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000e783  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e787  call    _CxxThrowException_0
0x18000e78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e794  test    byte ptr [rcx+1Ch], 8
0x18000e798  jz      loc_18000E688
0x18000e79e  cmp     byte ptr [rcx+19h], 2
0x18000e7a2  jb      loc_18000E688
0x18000e7a8  mov     edx, 0Bh
0x18000e7ad  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000e7b4  mov     rcx, [rcx+10h]
0x18000e7b8  call    WPP_SF_
0x18000e7bd  jmp     loc_18000E688
```
