# Broker::RpcClientToken::RpcClientToken(void)

- ea: `0x180004000`
- end: `0x18000418d`
- name: `??0RpcClientToken@Broker@@QEAA@XZ`
- size: `397`
- prototype: `Broker::RpcClientToken *__fastcall(Broker::RpcClientToken *this)`
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003700`
- `0x180003ac0`
- `0x180004274`
- `0x180004be0`
- `0x18000ef50`
- `0x1800118e0`
- `0x180011c20`
- `0x1800147b0`
- `0x1800149d0`

## callees

- `0x180003800`
- `0x180003840`
- `0x180004000`
- `0x180004194`
- `0x180011240`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004112`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004046`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000402e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000402e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180004024`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180004024`
- `RPCRT4!RpcRevertToSelf` at `0x180004054`
- `RPCRT4!RpcRevertToSelf` at `0x180004054`

## pseudocode

```c
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v2);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v6);
    v11 = v8;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v12 = v9;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( RpcRevertToSelf() && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
  return this;
}

```

## disassembly

```asm
0x180004000  mov     [rsp-8+arg_8], rbx
0x180004005  mov     [rsp-8+arg_10], rdi
0x18000400a  push    rbp
0x18000400b  mov     rbp, rsp
0x18000400e  sub     rsp, 70h
0x180004012  mov     rbx, rcx
0x180004015  lea     rcx, [rbp+arg_0]; this
0x180004019  call    ??0RpcScopedImpersonation@Broker@@QEAA@XZ; Broker::RpcScopedImpersonation::RpcScopedImpersonation(void)
0x18000401e  nop
0x18000401f  mov     rdx, rbx; Pid
0x180004022  xor     ecx, ecx; Binding
0x180004024  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000402a  test    eax, eax
0x18000402c  jnz     short loc_18000409D
0x18000402e  call    cs:__imp_GetCurrentThread
0x180004034  mov     rcx, rax; ThreadHandle
0x180004037  lea     r9, [rbx+8]; TokenHandle
0x18000403b  mov     edx, 8; DesiredAccess
0x180004040  mov     r8d, 1; OpenAsSelf
0x180004046  call    cs:__imp_OpenThreadToken
0x18000404c  test    eax, eax
0x18000404e  jz      loc_180004112
0x180004054  call    cs:__imp_RpcRevertToSelf
0x18000405a  test    eax, eax
0x18000405c  jnz     short loc_180004073
0x18000405e  mov     rax, rbx
0x180004061  lea     r11, [rsp+70h+var_s0]
0x180004066  mov     rbx, [r11+18h]
0x18000406a  mov     rdi, [r11+20h]
0x18000406e  mov     rsp, r11
0x180004071  pop     rbp
0x180004072  retn
0x180004073  mov     rcx, cs:WPP_GLOBAL_Control
0x18000407a  test    byte ptr [rcx+1Ch], 8
0x18000407e  jz      short loc_18000405E
0x180004080  cmp     byte ptr [rcx+19h], 2
0x180004084  jb      short loc_18000405E
0x180004086  mov     edx, 0Bh
0x18000408b  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180004092  mov     rcx, [rcx+10h]
0x180004096  call    WPP_SF_
0x18000409b  jmp     short loc_18000405E
0x18000409d  xorps   xmm0, xmm0
0x1800040a0  movups  [rbp+var_48], xmm0
0x1800040a4  mov     [rbp+var_38], 1
0x1800040ab  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800040b2  mov     [rbp+var_50], rbx
0x1800040b6  mov     [rbp+var_30], eax
0x1800040b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040c0  test    byte ptr [rcx+1Ch], 8
0x1800040c4  jz      short loc_1800040E4
0x1800040c6  cmp     byte ptr [rcx+19h], 2
0x1800040ca  jb      short loc_1800040E4
0x1800040cc  mov     edx, 0Eh
0x1800040d1  mov     r9d, eax
0x1800040d4  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800040db  mov     rcx, [rcx+10h]
0x1800040df  call    WPP_SF_d
0x1800040e4  lea     rdx, [rbp+var_50]; struct std::exception *
0x1800040e8  lea     rcx, [rbp+pExceptionObject]; this
0x1800040ec  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x1800040f1  mov     eax, [rbp+var_38]
0x1800040f4  mov     [rbp+var_10], eax
0x1800040f7  mov     [rbp+pExceptionObject], rbx
0x1800040fb  mov     eax, [rbp+var_30]
0x1800040fe  mov     [rbp+var_8], eax
0x180004101  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180004108  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000410c  call    _CxxThrowException_0
0x180004112  call    cs:__imp_GetLastError
0x180004118  xorps   xmm0, xmm0
0x18000411b  movups  [rbp+var_48], xmm0
0x18000411f  mov     [rbp+var_38], 1
0x180004126  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000412d  mov     [rbp+var_50], rbx
0x180004131  mov     [rbp+var_30], eax
0x180004134  mov     rcx, cs:WPP_GLOBAL_Control
0x18000413b  test    byte ptr [rcx+1Ch], 8
0x18000413f  jz      short loc_18000415F
0x180004141  cmp     byte ptr [rcx+19h], 2
0x180004145  jb      short loc_18000415F
0x180004147  mov     edx, 0Fh
0x18000414c  mov     r9d, eax
0x18000414f  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180004156  mov     rcx, [rcx+10h]
0x18000415a  call    WPP_SF_d
0x18000415f  lea     rdx, [rbp+var_50]; struct std::exception *
0x180004163  lea     rcx, [rbp+pExceptionObject]; this
0x180004167  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000416c  mov     eax, [rbp+var_38]
0x18000416f  mov     [rbp+var_10], eax
0x180004172  mov     [rbp+pExceptionObject], rbx
0x180004176  mov     eax, [rbp+var_30]
0x180004179  mov     [rbp+var_8], eax
0x18000417c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180004183  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004187  call    _CxxThrowException_0
```
