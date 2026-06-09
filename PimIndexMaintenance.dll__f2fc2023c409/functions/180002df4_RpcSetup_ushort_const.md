# RpcSetup(ushort const *)

- ea: `0x180002df4`
- end: `0x1800031c7`
- name: `?RpcSetup@@YAJPEBG@Z`
- size: `979`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800032f0`
- `0x180008f30`

## callees

- `0x180002c5c`
- `0x180002c80`
- `0x180002cb0`
- `0x180002cfc`
- `0x180002da8`
- `0x180002df4`
- `0x1800032a0`
- `0x1800035d4`
- `0x18002120a`
- `0x180021240`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqEpW` at `0x180003024`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180003024`
- `RPCRT4!RpcServerUseProtseqW` at `0x180002fa6`
- `RPCRT4!RpcServerUseProtseqW` at `0x180002fa6`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18000307c`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18000307c`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800030c5`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800030c5`
- `RPCRT4!RpcServerRegisterIf3` at `0x180002eb6`
- `RPCRT4!RpcServerRegisterIf3` at `0x180002eb6`
- `RPCRT4!RpcServerInqBindings` at `0x180003104`
- `RPCRT4!RpcServerInqBindings` at `0x180003104`
- `RPCRT4!RpcEpRegisterW` at `0x180003152`
- `RPCRT4!RpcEpRegisterW` at `0x180003152`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180002f14`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180002f14`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002e74`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002f44`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002f71`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000318a`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800031a4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002e74`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002f44`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002f71`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000318a`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800031a4`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x18000304f`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x18000304f`
- `UserDataPlatformHelperUtil!GetCombinedTransientObjectSecurityDescriptor` at `0x180002e46`
- `UserDataPlatformHelperUtil!GetCombinedTransientObjectSecurityDescriptor` at `0x180002e46`

## string_xrefs

- `0x180002f08`: `DefaultRpcAccess`
- `0x180002f24`: `onecoreuap\private\base\inc\CommsSecurityHelper.h`
- `0x180002e5c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180002f59`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180003099`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180003121`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\rpcsetup.cpp`
- `0x180002e32`: `PimIMServiceMobile\Interface`
- `0x180002e3f`: `PimIMServiceOneCore\Interface`

## pseudocode

```c
__int64 __fastcall RpcSetup(STRSAFE_LPCWSTR pszSrc)
{
  __int64 v2; // rax
  int CombinedTransientObjectSecurityDescriptor; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // rax
  _QWORD *v9; // rsi
  __int64 v10; // rax
  int TransientObjectSecurityDescriptor; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  RPC_STATUS v14; // eax
  RPC_STATUS v15; // eax
  __int64 v16; // r9
  RPC_STATUS v17; // eax
  RPC_BINDING_VECTOR **v18; // rax
  RPC_STATUS v19; // eax
  __int64 v20; // r9
  RPC_STATUS v21; // eax
  char v22; // [rsp+40h] [rbp-C0h] BYREF
  char v23; // [rsp+41h] [rbp-BFh]
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  void *SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  RPC_WSTR PrincName; // [rsp+58h] [rbp-A8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+60h] [rbp-A0h] BYREF
  RPC_WSTR *p_PrincName; // [rsp+68h] [rbp-98h] BYREF
  char v29; // [rsp+70h] [rbp-90h]
  wchar_t pszDest[29]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[470]; // [rsp+BAh] [rbp-46h] BYREF

  v24 = 0;
  v2 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&v24);
  CombinedTransientObjectSecurityDescriptor = GetCombinedTransientObjectSecurityDescriptor(
                                                L"PimIMServiceOneCore\\Interface",
                                                L"PimIMServiceMobile\\Interface",
                                                9,
                                                v2);
  if ( CombinedTransientObjectSecurityDescriptor < 0 )
  {
    v4 = 77;
    v5 = 1;
LABEL_3:
    Log_HREvent(
      (unsigned int)CombinedTransientObjectSecurityDescriptor,
      v5,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
      v4);
LABEL_4:
    if ( v24 )
      FreeTransientObjectSecurityDescriptor();
    return (unsigned int)CombinedTransientObjectSecurityDescriptor;
  }
  v7 = RpcServerRegisterIf3(qword_180024E00, 0, 0, 41, 1234, 0, 0, v24);
  CombinedTransientObjectSecurityDescriptor = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      CombinedTransientObjectSecurityDescriptor = (unsigned __int16)v7 | 0x80070000;
    v4 = 88;
    v5 = 0;
    goto LABEL_3;
  }
  v23 = 1;
  SecurityDescriptor = 0;
  v8 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&SecurityDescriptor);
  PrincName = 0;
  v9 = (_QWORD *)v8;
  v10 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&PrincName);
  TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", v10);
  if ( TransientObjectSecurityDescriptor >= 0 )
  {
    *v9 = PrincName;
  }
  else
  {
    CombinedTransientObjectSecurityDescriptor = TransientObjectSecurityDescriptor | 0x10000000;
    Log_HREvent(
      TransientObjectSecurityDescriptor | 0x10000000u,
      0,
      "onecoreuap\\private\\base\\inc\\CommsSecurityHelper.h",
      48);
    if ( PrincName )
      FreeTransientObjectSecurityDescriptor();
    if ( CombinedTransientObjectSecurityDescriptor < 0 )
    {
      v12 = 99;
LABEL_16:
      v13 = 1;
LABEL_17:
      Log_HREvent(
        (unsigned int)CombinedTransientObjectSecurityDescriptor,
        v13,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
        v12);
LABEL_18:
      if ( SecurityDescriptor )
        FreeTransientObjectSecurityDescriptor();
      tlx::_UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581___::__UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581___(&v22);
      goto LABEL_4;
    }
  }
  if ( pszSrc )
  {
    wcscpy(pszDest, L"PimIndexMaintenancterface");
    memset_0(v31, 0, 0x1CEu);
    CombinedTransientObjectSecurityDescriptor = StringCchCopyW(pszDest, 0x104u, pszSrc);
    if ( CombinedTransientObjectSecurityDescriptor < 0 )
    {
      v12 = 114;
      goto LABEL_16;
    }
    v14 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, pszDest, SecurityDescriptor);
  }
  else
  {
    v14 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  }
  CombinedTransientObjectSecurityDescriptor = v14;
  if ( v14 != 1740 && v14 )
  {
    if ( v14 > 0 )
      CombinedTransientObjectSecurityDescriptor = (unsigned __int16)v14 | 0x80070000;
    v12 = 125;
    v13 = 0;
    goto LABEL_17;
  }
  if ( !(unsigned int)IsCommsSystemService() )
  {
    PrincName = 0;
    p_PrincName = &PrincName;
    v29 = 1;
    v15 = RpcServerInqDefaultPrincNameW(0xAu, &PrincName);
    CombinedTransientObjectSecurityDescriptor = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        CombinedTransientObjectSecurityDescriptor = (unsigned __int16)v15 | 0x80070000;
      v16 = 139;
LABEL_37:
      Log_HREvent(
        (unsigned int)CombinedTransientObjectSecurityDescriptor,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
        v16);
      tlx::_UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb___::__UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb___(&p_PrincName);
      goto LABEL_18;
    }
    v17 = RpcServerRegisterAuthInfoW(PrincName, 0xAu, 0, 0);
    CombinedTransientObjectSecurityDescriptor = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        CombinedTransientObjectSecurityDescriptor = (unsigned __int16)v17 | 0x80070000;
      v16 = 141;
      goto LABEL_37;
    }
    tlx::_UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb___::__UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb___(&p_PrincName);
  }
  BindingVector = 0;
  v18 = (RPC_BINDING_VECTOR **)tlx::replace<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>(&BindingVector);
  v19 = RpcServerInqBindings(v18);
  CombinedTransientObjectSecurityDescriptor = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      CombinedTransientObjectSecurityDescriptor = (unsigned __int16)v19 | 0x80070000;
    v20 = 145;
LABEL_47:
    Log_HREvent(
      (unsigned int)CombinedTransientObjectSecurityDescriptor,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\rpcsetup.cpp",
      v20);
    tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(&BindingVector);
    goto LABEL_18;
  }
  v21 = RpcEpRegisterW(qword_180024E00, BindingVector, 0, 0);
  CombinedTransientObjectSecurityDescriptor = v21;
  if ( v21 )
  {
    if ( v21 > 0 )
      CombinedTransientObjectSecurityDescriptor = (unsigned __int16)v21 | 0x80070000;
    v20 = 148;
    goto LABEL_47;
  }
  v23 = 0;
  tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&void _CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(&BindingVector);
  if ( SecurityDescriptor )
    FreeTransientObjectSecurityDescriptor();
  tlx::_UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581___::__UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581___(&v22);
  if ( v24 )
    FreeTransientObjectSecurityDescriptor();
  return 0;
}

```

## disassembly

```asm
0x180002df4  push    rbp
0x180002df6  push    rbx
0x180002df7  push    rsi
0x180002df8  push    rdi
0x180002df9  lea     rbp, [rsp-1A8h]
0x180002e01  sub     rsp, 2A8h
0x180002e08  mov     rax, cs:__security_cookie
0x180002e0f  xor     rax, rsp
0x180002e12  mov     [rbp+1C0h+var_30], rax
0x180002e19  mov     rdi, rcx
0x180002e1c  mov     [rsp+2C0h+var_278], 0
0x180002e25  lea     rcx, [rsp+2C0h+var_278]
0x180002e2a  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180002e2f  mov     r9, rax
0x180002e32  lea     rdx, aPimimservicemo; "PimIMServiceMobile\\Interface"
0x180002e39  mov     r8d, 9
0x180002e3f  lea     rcx, aPimimserviceon; "PimIMServiceOneCore\\Interface"
0x180002e46  call    cs:__imp_GetCombinedTransientObjectSecurityDescriptor
0x180002e4c  mov     ebx, eax
0x180002e4e  test    eax, eax
0x180002e50  jns     short loc_180002E81
0x180002e52  mov     r9d, 4Dh ; 'M'
0x180002e58  lea     edx, [r9-4Ch]
0x180002e5c  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002e63  mov     ecx, ebx
0x180002e65  call    Log_HREvent
0x180002e6a  mov     rcx, [rsp+2C0h+var_278]
0x180002e6f  test    rcx, rcx
0x180002e72  jz      short loc_180002E7A
0x180002e74  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180002e7a  mov     eax, ebx
0x180002e7c  jmp     loc_1800031AC
0x180002e81  mov     rax, [rsp+2C0h+var_278]
0x180002e86  lea     rcx, qword_180024E00
0x180002e8d  mov     [rsp+2C0h+var_288], rax
0x180002e92  mov     r9d, 29h ; ')'
0x180002e98  mov     [rsp+2C0h+var_290], 0
0x180002ea1  xor     r8d, r8d
0x180002ea4  mov     [rsp+2C0h+var_298], 0
0x180002eac  xor     edx, edx
0x180002eae  mov     [rsp+2C0h+var_2A0], 4D2h
0x180002eb6  call    cs:__imp_RpcServerRegisterIf3
0x180002ebc  mov     ebx, eax
0x180002ebe  test    eax, eax
0x180002ec0  jz      short loc_180002ED7
0x180002ec2  jle     short loc_180002ECD
0x180002ec4  movzx   ebx, ax
0x180002ec7  or      ebx, 80070000h
0x180002ecd  mov     r9d, 58h ; 'X'
0x180002ed3  xor     edx, edx
0x180002ed5  jmp     short loc_180002E5C
0x180002ed7  lea     rcx, [rsp+2C0h+SecurityDescriptor]
0x180002edc  mov     [rsp+2C0h+var_27F], 1
0x180002ee1  mov     [rsp+2C0h+SecurityDescriptor], 0
0x180002eea  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180002eef  lea     rcx, [rsp+2C0h+PrincName]
0x180002ef4  mov     [rsp+2C0h+PrincName], 0
0x180002efd  mov     rsi, rax
0x180002f00  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180002f05  mov     r8, rax
0x180002f08  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x180002f0f  mov     ecx, 8
0x180002f14  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180002f1a  mov     ebx, eax
0x180002f1c  test    eax, eax
0x180002f1e  jns     short loc_180002F86
0x180002f20  bts     ebx, 1Ch
0x180002f24  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\base\\inc\\CommsSe"...
0x180002f2b  mov     ecx, ebx
0x180002f2d  mov     r9d, 30h ; '0'
0x180002f33  xor     edx, edx
0x180002f35  call    Log_HREvent
0x180002f3a  mov     rcx, [rsp+2C0h+PrincName]
0x180002f3f  test    rcx, rcx
0x180002f42  jz      short loc_180002F4A
0x180002f44  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180002f4a  test    ebx, ebx
0x180002f4c  jns     short loc_180002F8E
0x180002f4e  mov     r9d, 63h ; 'c'
0x180002f54  mov     edx, 1
0x180002f59  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002f60  mov     ecx, ebx
0x180002f62  call    Log_HREvent
0x180002f67  mov     rcx, [rsp+2C0h+SecurityDescriptor]
0x180002f6c  test    rcx, rcx
0x180002f6f  jz      short loc_180002F77
0x180002f71  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180002f77  lea     rcx, [rsp+2C0h+var_280]
0x180002f7c  call    tlx___UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581_______UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581___
0x180002f81  jmp     loc_180002E6A
0x180002f86  mov     rax, [rsp+2C0h+PrincName]
0x180002f8b  mov     [rsi], rax
0x180002f8e  test    rdi, rdi
0x180002f91  jnz     short loc_180002FAE
0x180002f93  mov     r8, [rsp+2C0h+SecurityDescriptor]; SecurityDescriptor
0x180002f98  lea     rcx, Protseq; "ncalrpc"
0x180002f9f  mov     edi, 0Ah
0x180002fa4  mov     edx, edi; MaxCalls
0x180002fa6  call    cs:__imp_RpcServerUseProtseqW
0x180002fac  jmp     short loc_18000302A
0x180002fae  movups  xmm0, xmmword ptr cs:aPimindexmainte_1; "PimIndexMaintenanceInterface"
0x180002fb5  xor     edx, edx; Val
0x180002fb7  mov     r8d, 1CEh; Size
0x180002fbd  movups  xmm1, xmmword ptr cs:aPimindexmainte_1+10h; "MaintenanceInterface"
0x180002fc4  lea     rcx, [rbp+1C0h+var_206]; void *
0x180002fc8  movaps  xmmword ptr [rbp+1C0h+pszDest], xmm0
0x180002fcc  movups  xmm0, xmmword ptr cs:aPimindexmainte_1+20h; "nceInterface"
0x180002fd3  movaps  [rbp+1C0h+var_230], xmm1
0x180002fd7  movups  xmm1, xmmword ptr cs:aPimindexmainte_1+2Ah; "terface"
0x180002fde  movaps  [rbp+1C0h+var_220], xmm0
0x180002fe2  movups  [rbp+1C0h+var_220+0Ah], xmm1
0x180002fe6  call    memset_0
0x180002feb  mov     r8, rdi; pszSrc
0x180002fee  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x180002ff2  mov     edx, 104h; cchDest
0x180002ff7  call    StringCchCopyW
0x180002ffc  mov     ebx, eax
0x180002ffe  test    eax, eax
0x180003000  jns     short loc_18000300D
0x180003002  mov     r9d, 72h ; 'r'
0x180003008  jmp     loc_180002F54
0x18000300d  mov     r9, [rsp+2C0h+SecurityDescriptor]; SecurityDescriptor
0x180003012  lea     r8, [rbp+1C0h+pszDest]; Endpoint
0x180003016  mov     edi, 0Ah
0x18000301b  lea     rcx, Protseq; "ncalrpc"
0x180003022  mov     edx, edi; MaxCalls
0x180003024  call    cs:__imp_RpcServerUseProtseqEpW
0x18000302a  mov     ebx, eax
0x18000302c  cmp     eax, 6CCh
0x180003031  jz      short loc_18000304F
0x180003033  test    eax, eax
0x180003035  jz      short loc_18000304F
0x180003037  jle     short loc_180003042
0x180003039  movzx   ebx, bx
0x18000303c  or      ebx, 80070000h
0x180003042  mov     r9d, 7Dh ; '}'
0x180003048  xor     edx, edx
0x18000304a  jmp     loc_180002F59
0x18000304f  call    cs:__imp_IsCommsSystemService
0x180003055  test    eax, eax
0x180003057  jnz     loc_1800030EE
0x18000305d  lea     rax, [rsp+2C0h+PrincName]
0x180003062  mov     [rsp+2C0h+PrincName], 0
0x18000306b  lea     rdx, [rsp+2C0h+PrincName]; PrincName
0x180003070  mov     [rsp+2C0h+var_258], rax
0x180003075  mov     ecx, edi; AuthnSvc
0x180003077  mov     [rsp+2C0h+var_250], 1
0x18000307c  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x180003082  mov     ebx, eax
0x180003084  test    eax, eax
0x180003086  jz      short loc_1800030B8
0x180003088  jle     short loc_180003093
0x18000308a  movzx   ebx, ax
0x18000308d  or      ebx, 80070000h
0x180003093  mov     r9d, 8Bh
0x180003099  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800030a0  xor     edx, edx
0x1800030a2  mov     ecx, ebx
0x1800030a4  call    Log_HREvent
0x1800030a9  lea     rcx, [rsp+2C0h+var_258]
0x1800030ae  call    tlx___UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb_______UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb___
0x1800030b3  jmp     loc_180002F67
0x1800030b8  mov     rcx, [rsp+2C0h+PrincName]; ServerPrincName
0x1800030bd  xor     r9d, r9d; Arg
0x1800030c0  xor     r8d, r8d; GetKeyFn
0x1800030c3  mov     edx, edi; AuthnSvc
0x1800030c5  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800030cb  mov     ebx, eax
0x1800030cd  test    eax, eax
0x1800030cf  jz      short loc_1800030E4
0x1800030d1  jle     short loc_1800030DC
0x1800030d3  movzx   ebx, ax
0x1800030d6  or      ebx, 80070000h
0x1800030dc  mov     r9d, 8Dh
0x1800030e2  jmp     short loc_180003099
0x1800030e4  lea     rcx, [rsp+2C0h+var_258]
0x1800030e9  call    tlx___UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb_______UndoSolo__lambda_f8428cfba661f5d7fa6995c3ed80debb___
0x1800030ee  lea     rcx, [rsp+2C0h+BindingVector]
0x1800030f3  mov     [rsp+2C0h+BindingVector], 0
0x1800030fc  call    ??$replace@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@YAPEAPEAU_RPC_BINDING_VECTOR@@AEAV?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@0@@Z; tlx::replace<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>(tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0> &)
0x180003101  mov     rcx, rax; BindingVector
0x180003104  call    cs:__imp_RpcServerInqBindings
0x18000310a  mov     ebx, eax
0x18000310c  test    eax, eax
0x18000310e  jz      short loc_180003140
0x180003110  jle     short loc_18000311B
0x180003112  movzx   ebx, ax
0x180003115  or      ebx, 80070000h
0x18000311b  mov     r9d, 91h
0x180003121  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003128  xor     edx, edx
0x18000312a  mov     ecx, ebx
0x18000312c  call    Log_HREvent
0x180003131  lea     rcx, [rsp+2C0h+BindingVector]
0x180003136  call    ?_Delete@?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(void)
0x18000313b  jmp     loc_180002F67
0x180003140  mov     rdx, [rsp+2C0h+BindingVector]; BindingVector
0x180003145  lea     rcx, qword_180024E00; IfSpec
0x18000314c  xor     r9d, r9d; Annotation
0x18000314f  xor     r8d, r8d; UuidVector
0x180003152  call    cs:__imp_RpcEpRegisterW
0x180003158  mov     ebx, eax
0x18000315a  test    eax, eax
0x18000315c  jz      short loc_180003171
0x18000315e  jle     short loc_180003169
0x180003160  movzx   ebx, ax
0x180003163  or      ebx, 80070000h
0x180003169  mov     r9d, 94h
0x18000316f  jmp     short loc_180003121
0x180003171  lea     rcx, [rsp+2C0h+BindingVector]
0x180003176  mov     [rsp+2C0h+var_27F], 0
0x18000317b  call    ?_Delete@?$auto_xxx@PEAU_RPC_BINDING_VECTOR@@P6AX$$QEAPEAU1@@Z$1?_CloseBindingVector@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR * &&),&_CloseBindingVector(_RPC_BINDING_VECTOR * &&),0>::_Delete(void)
0x180003180  mov     rcx, [rsp+2C0h+SecurityDescriptor]
0x180003185  test    rcx, rcx
0x180003188  jz      short loc_180003190
0x18000318a  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180003190  lea     rcx, [rsp+2C0h+var_280]
0x180003195  call    tlx___UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581_______UndoSolo__lambda_610898aad9a0a631e78dcfd0081bf581___
0x18000319a  mov     rcx, [rsp+2C0h+var_278]
0x18000319f  test    rcx, rcx
0x1800031a2  jz      short loc_1800031AA
0x1800031a4  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800031aa  xor     eax, eax
0x1800031ac  mov     rcx, [rbp+1C0h+var_30]
0x1800031b3  xor     rcx, rsp; StackCookie
0x1800031b6  call    __security_check_cookie
0x1800031bb  add     rsp, 2A8h
0x1800031c2  pop     rdi
0x1800031c3  pop     rsi
0x1800031c4  pop     rbx
0x1800031c5  pop     rbp
0x1800031c6  retn
```
