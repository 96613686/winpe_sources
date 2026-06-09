# Broker::RpcClientToken::RpcClientToken(void)

- ea: `0x18000da40`
- end: `0x18000dc36`
- name: `??0RpcClientToken@Broker@@QEAA@XZ`
- size: `502`
- prototype: `Broker::RpcClientToken *__fastcall(Broker::RpcClientToken *this)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800029c0`
- `0x180002d10`
- `0x18000cc40`
- `0x18000ec10`
- `0x180010560`
- `0x180010e50`
- `0x18001aee0`
- `0x18001b5d0`
- `0x18001bb90`
- `0x18001e150`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x18000da40`
- `0x1800195e0`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000da7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000da7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000da93`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000da93`
- `RPCRT4!RpcImpersonateClient` at `0x18000da5a`
- `RPCRT4!RpcImpersonateClient` at `0x18000da5a`
- `RPCRT4!RpcRevertToSelf` at `0x18000daa1`
- `RPCRT4!RpcRevertToSelf` at `0x18000daa1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000da6d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000da6d`

## pseudocode

```c
Broker::RpcClientToken *__fastcall Broker::RpcClientToken::RpcClientToken(Broker::RpcClientToken *this)
{
  unsigned int v2; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v7; // [rsp+28h] [rbp-58h]
  int v8; // [rsp+38h] [rbp-48h]
  int v9; // [rsp+40h] [rbp-40h]
  _QWORD v10[3]; // [rsp+48h] [rbp-38h] BYREF
  int v11; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+68h] [rbp-18h]

  if ( RpcImpersonateClient(0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
    v7 = 0;
    v8 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v9 = 5;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v2 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)this);
  if ( v2 )
  {
    v7 = 0;
    v8 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v9 = v2;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v2);
    std::exception::exception((std::exception *)v10, (const struct std::exception *)&pExceptionObject);
    v11 = v8;
    v10[0] = &Broker::Win32Error::`vftable';
    v12 = v9;
    throw (Broker::Win32Error *)v10;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)this + 1) )
  {
    LastError = GetLastError();
    v7 = 0;
    v8 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v9 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    std::exception::exception((std::exception *)v10, (const struct std::exception *)&pExceptionObject);
    v11 = v8;
    v10[0] = &Broker::Win32Error::`vftable';
    v12 = v9;
    throw (Broker::Win32Error *)v10;
  }
  if ( RpcRevertToSelf() && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
  return this;
}

```

## disassembly

```asm
0x18000da40  mov     [rsp-8+arg_0], rbx
0x18000da45  mov     [rsp-8+arg_8], rdi
0x18000da4a  push    rbp
0x18000da4b  mov     rbp, rsp
0x18000da4e  sub     rsp, 80h
0x18000da55  mov     rbx, rcx
0x18000da58  xor     ecx, ecx; BindingHandle
0x18000da5a  call    cs:__imp_RpcImpersonateClient
0x18000da60  test    eax, eax
0x18000da62  jnz     loc_18000DAED
0x18000da68  mov     rdx, rbx; Pid
0x18000da6b  xor     ecx, ecx; Binding
0x18000da6d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000da73  test    eax, eax
0x18000da75  jnz     loc_18000DB46
0x18000da7b  call    cs:__imp_GetCurrentThread
0x18000da81  mov     rcx, rax; ThreadHandle
0x18000da84  lea     r9, [rbx+8]; TokenHandle
0x18000da88  mov     edx, 8; DesiredAccess
0x18000da8d  mov     r8d, 1; OpenAsSelf
0x18000da93  call    cs:__imp_OpenThreadToken
0x18000da99  test    eax, eax
0x18000da9b  jz      loc_18000DBBB
0x18000daa1  call    cs:__imp_RpcRevertToSelf
0x18000daa7  test    eax, eax
0x18000daa9  jnz     short loc_18000DAC3
0x18000daab  mov     rax, rbx
0x18000daae  lea     r11, [rsp+80h+var_s0]
0x18000dab6  mov     rbx, [r11+10h]
0x18000daba  mov     rdi, [r11+18h]
0x18000dabe  mov     rsp, r11
0x18000dac1  pop     rbp
0x18000dac2  retn
0x18000dac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daca  test    byte ptr [rcx+1Ch], 8
0x18000dace  jz      short loc_18000DAAB
0x18000dad0  cmp     byte ptr [rcx+19h], 2
0x18000dad4  jb      short loc_18000DAAB
0x18000dad6  mov     edx, 0Bh
0x18000dadb  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000dae2  mov     rcx, [rcx+10h]
0x18000dae6  call    WPP_SF_
0x18000daeb  jmp     short loc_18000DAAB
0x18000daed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daf4  test    byte ptr [rcx+1Ch], 8
0x18000daf8  jz      short loc_18000DB15
0x18000dafa  cmp     byte ptr [rcx+19h], 2
0x18000dafe  jb      short loc_18000DB15
0x18000db00  mov     edx, 0Ah
0x18000db05  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000db0c  mov     rcx, [rcx+10h]
0x18000db10  call    WPP_SF_
0x18000db15  xorps   xmm0, xmm0
0x18000db18  movups  [rbp+var_58], xmm0
0x18000db1c  mov     [rbp+var_48], 1
0x18000db23  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000db2a  mov     [rbp+pExceptionObject], rbx
0x18000db2e  mov     [rbp+var_40], 5
0x18000db35  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000db3c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000db40  call    _CxxThrowException_0
0x18000db46  xorps   xmm0, xmm0
0x18000db49  movups  [rbp+var_58], xmm0
0x18000db4d  mov     [rbp+var_48], 1
0x18000db54  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000db5b  mov     [rbp+pExceptionObject], rbx
0x18000db5f  mov     [rbp+var_40], eax
0x18000db62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db69  test    byte ptr [rcx+1Ch], 8
0x18000db6d  jz      short loc_18000DB8D
0x18000db6f  cmp     byte ptr [rcx+19h], 2
0x18000db73  jb      short loc_18000DB8D
0x18000db75  mov     edx, 0Eh
0x18000db7a  mov     r9d, eax
0x18000db7d  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000db84  mov     rcx, [rcx+10h]
0x18000db88  call    WPP_SF_d
0x18000db8d  lea     rdx, [rbp+pExceptionObject]; struct std::exception *
0x18000db91  lea     rcx, [rbp+var_38]; this
0x18000db95  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000db9a  mov     eax, [rbp+var_48]
0x18000db9d  mov     [rbp+var_20], eax
0x18000dba0  mov     [rbp+var_38], rbx
0x18000dba4  mov     eax, [rbp+var_40]
0x18000dba7  mov     [rbp+var_18], eax
0x18000dbaa  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000dbb1  lea     rcx, [rbp+var_38]; pExceptionObject
0x18000dbb5  call    _CxxThrowException_0
0x18000dbbb  call    cs:__imp_GetLastError
0x18000dbc1  xorps   xmm0, xmm0
0x18000dbc4  movups  [rbp+var_58], xmm0
0x18000dbc8  mov     [rbp+var_48], 1
0x18000dbcf  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000dbd6  mov     [rbp+pExceptionObject], rbx
0x18000dbda  mov     [rbp+var_40], eax
0x18000dbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbe4  test    byte ptr [rcx+1Ch], 8
0x18000dbe8  jz      short loc_18000DC08
0x18000dbea  cmp     byte ptr [rcx+19h], 2
0x18000dbee  jb      short loc_18000DC08
0x18000dbf0  mov     edx, 0Fh
0x18000dbf5  mov     r9d, eax
0x18000dbf8  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000dbff  mov     rcx, [rcx+10h]
0x18000dc03  call    WPP_SF_d
0x18000dc08  lea     rdx, [rbp+pExceptionObject]; struct std::exception *
0x18000dc0c  lea     rcx, [rbp+var_38]; this
0x18000dc10  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000dc15  mov     eax, [rbp+var_48]
0x18000dc18  mov     [rbp+var_20], eax
0x18000dc1b  mov     [rbp+var_38], rbx
0x18000dc1f  mov     eax, [rbp+var_40]
0x18000dc22  mov     [rbp+var_18], eax
0x18000dc25  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000dc2c  lea     rcx, [rbp+var_38]; pExceptionObject
0x18000dc30  call    _CxxThrowException_0
```
