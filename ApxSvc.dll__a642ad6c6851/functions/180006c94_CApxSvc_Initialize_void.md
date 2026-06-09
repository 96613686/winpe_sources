# CApxSvc::Initialize(void)

- ea: `0x180006c94`
- end: `0x1800070c8`
- name: `?Initialize@CApxSvc@@QEAAJXZ`
- size: `1076`
- prototype: `__int64 __fastcall(CApxSvc *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005bc4`

## callees

- `0x180001fc0`
- `0x180004924`
- `0x180006140`
- `0x1800061ac`
- `0x18000629c`
- `0x180006554`
- `0x180006ac4`
- `0x180006c94`
- `0x1800070d0`
- `0x1800073c0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006fb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006fb0`
- `RPCRT4!RpcBindingVectorFree` at `0x180006f01`
- `RPCRT4!RpcBindingVectorFree` at `0x180006f84`
- `RPCRT4!RpcBindingVectorFree` at `0x180006fa8`
- `RPCRT4!RpcBindingVectorFree` at `0x180006f01`
- `RPCRT4!RpcBindingVectorFree` at `0x180006f84`
- `RPCRT4!RpcBindingVectorFree` at `0x180006fa8`
- `RPCRT4!RpcServerUseProtseqW` at `0x180006eb1`
- `RPCRT4!RpcServerUseProtseqW` at `0x180006fff`
- `RPCRT4!RpcServerUseProtseqW` at `0x180006eb1`
- `RPCRT4!RpcServerUseProtseqW` at `0x180006fff`
- `RPCRT4!RpcServerRegisterIf3` at `0x180006e93`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007058`
- `RPCRT4!RpcServerRegisterIf3` at `0x180006e93`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007058`
- `RPCRT4!RpcServerInqBindings` at `0x180006ecb`
- `RPCRT4!RpcServerInqBindings` at `0x180006fc2`
- `RPCRT4!RpcServerInqBindings` at `0x180006ecb`
- `RPCRT4!RpcServerInqBindings` at `0x180006fc2`
- `RPCRT4!RpcEpRegisterW` at `0x180006ee6`
- `RPCRT4!RpcEpRegisterW` at `0x180006f35`
- `RPCRT4!RpcEpRegisterW` at `0x180006ee6`
- `RPCRT4!RpcEpRegisterW` at `0x180006f35`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006e08`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006e08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000709b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000709b`
- `Apx01000!imp_ApxBindClient` at `0x180006d39`
- `Apx01000!imp_ApxBindClient` at `0x180006d39`

## string_xrefs

- `0x180006ddd`: `onecoreuap\drivers\wdm\audio\backpln\apx\service\core\apfsvc.cpp`

## pseudocode

```c
__int64 __fastcall CApxSvc::Initialize(CApxSvc *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  _QWORD *v4; // rcx
  __int64 (*v5)(void); // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int ServerSddlString; // eax
  signed int LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  RPC_BINDING_VECTOR *v18; // rdi
  DWORD v19; // ebx
  int v20; // [rsp+20h] [rbp-60h]
  LPCWSTR *p_StringSecurityDescriptor; // [rsp+40h] [rbp-40h] BYREF
  char v22; // [rsp+48h] [rbp-38h]
  CApxSvc *v23; // [rsp+50h] [rbp-30h]
  char v24; // [rsp+58h] [rbp-28h]
  __int64 v25; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+68h] [rbp-18h]
  int v27; // [rsp+6Ch] [rbp-14h]
  __int64 v28; // [rsp+70h] [rbp-10h]
  __int64 v29; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C0h] [rbp+40h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+C8h] [rbp+48h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+D0h] [rbp+50h] BYREF
  RPC_BINDING_VECTOR *v34; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids);
  }
  StringSecurityDescriptor = 0;
  v23 = this;
  v24 = 1;
  StringSecurityDescriptor = (LPCWSTR)operator new[](0x400u);
  p_StringSecurityDescriptor = &StringSecurityDescriptor;
  v22 = 1;
  v28 = 1;
  v25 = 32;
  v26 = 1;
  v27 = 1;
  v29 = 0;
  imp_ApxBindClient(&v25, this);
  *((_BYTE *)this + 8) = 1;
  v2 = 0;
  v3 = 0;
  do
  {
    v4 = *(&g_SupportedAppList + 6 * v3 + 2);
    if ( v4 )
    {
      if ( !*v4 )
      {
        v5 = (__int64 (*)(void))*(&funcs_180006D6F + 6 * v3);
        if ( v5 )
        {
          v6 = v5();
          v2 = v6;
          if ( v6 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v20 = v6;
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (unsigned int)v3);
            }
LABEL_12:
            v9 = v2;
            v10 = 518;
LABEL_19:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v10,
              (unsigned int)"onecoreuap\\drivers\\wdm\\audio\\backpln\\apx\\service\\core\\apfsvc.cpp",
              (const char *)v9,
              v20);
            goto LABEL_60;
          }
        }
      }
    }
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 3 );
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_12;
  ServerSddlString = GetServerSddlString(4, StringSecurityDescriptor, &g_SupportedAppList);
  v2 = ServerSddlString;
  if ( ServerSddlString < 0 )
  {
    v9 = (unsigned int)ServerSddlString;
    v10 = 527;
    goto LABEL_19;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 23;
      goto LABEL_57;
    }
LABEL_58:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
LABEL_60:
    wil::details::lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___::_lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___(&p_StringSecurityDescriptor);
    CApxSvc::Cleanup(this);
    return v2;
  }
  if ( (unsigned int)RpcServerRegisterIf3(qword_18000A300, 0, 0, 33, 1234, 0, ApfSvcRpcIfCallback, SecurityDescriptor) )
  {
    v2 = RpcServerRegisterIf3(qword_18000A300, 0, 0, 33, 1234, 0, ApfSvcRpcIfCallback, SecurityDescriptor) | 0x80010000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_58;
    }
    v14 = 24;
LABEL_57:
    WPP_SF_d(v13[2], v14, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids, v2);
    goto LABEL_58;
  }
  if ( RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor) )
  {
    v2 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor) | 0x80010000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_58;
    }
    v14 = 25;
    goto LABEL_57;
  }
  BindingVector = 0;
  if ( RpcServerInqBindings(&BindingVector) )
  {
    v18 = BindingVector;
    if ( BindingVector )
    {
      v19 = GetLastError();
      v34 = v18;
      RpcBindingVectorFree(&v34);
      SetLastError(v19);
    }
    BindingVector = 0;
    v2 = RpcServerInqBindings(&BindingVector) | 0x80010000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_41;
    }
    v17 = 26;
    goto LABEL_40;
  }
  if ( RpcEpRegisterW(qword_18000A300, BindingVector, 0, 0) )
  {
    v2 = RpcEpRegisterW(qword_18000A300, BindingVector, 0, 0) | 0x80010000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_41:
      if ( BindingVector )
      {
        v34 = BindingVector;
        RpcBindingVectorFree(&v34);
      }
      goto LABEL_58;
    }
    v17 = 27;
LABEL_40:
    WPP_SF_d(v16[2], v17, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids, v2);
    goto LABEL_41;
  }
  if ( BindingVector )
  {
    v34 = BindingVector;
    RpcBindingVectorFree(&v34);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  wil::details::lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___::_lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___(&p_StringSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x180006c94  push    rbp
0x180006c96  push    rbx
0x180006c97  push    rsi
0x180006c98  push    rdi
0x180006c99  push    r12
0x180006c9b  push    r13
0x180006c9d  push    r15
0x180006c9f  mov     rbp, rsp
0x180006ca2  sub     rsp, 80h
0x180006ca9  mov     rsi, rcx
0x180006cac  lea     r12, WPP_GLOBAL_Control
0x180006cb3  lea     r13, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006cba  mov     r15d, 1
0x180006cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cc7  cmp     rcx, r12
0x180006cca  jz      short loc_180006CE8
0x180006ccc  test    [rcx+1Ch], r15b
0x180006cd0  jz      short loc_180006CE8
0x180006cd2  cmp     byte ptr [rcx+19h], 5
0x180006cd6  jb      short loc_180006CE8
0x180006cd8  lea     edx, [r15+14h]
0x180006cdc  mov     r8, r13
0x180006cdf  mov     rcx, [rcx+10h]
0x180006ce3  call    WPP_SF_
0x180006ce8  mov     [rbp+StringSecurityDescriptor], 0
0x180006cf0  mov     [rbp+var_30], rsi
0x180006cf4  mov     [rbp+var_28], r15b
0x180006cf8  mov     ecx, 400h; unsigned __int64
0x180006cfd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006d02  mov     [rbp+StringSecurityDescriptor], rax
0x180006d06  lea     rax, [rbp+StringSecurityDescriptor]
0x180006d0a  mov     [rbp+var_40], rax
0x180006d0e  mov     [rbp+var_38], r15b
0x180006d12  mov     [rbp+var_10], 1
0x180006d1a  mov     [rbp+var_20], 20h ; ' '
0x180006d22  mov     [rbp+var_18], r15d
0x180006d26  mov     [rbp+var_14], r15d
0x180006d2a  mov     [rbp+var_8], 0
0x180006d32  mov     rdx, rsi
0x180006d35  lea     rcx, [rbp+var_20]
0x180006d39  call    cs:__imp_imp_ApxBindClient
0x180006d3f  mov     [rsi+8], r15b
0x180006d43  xor     ebx, ebx
0x180006d45  xor     edi, edi
0x180006d47  lea     r8, ?g_SupportedAppList@@3PAU_APF_APP_INFO@@A; "TV"
0x180006d4e  lea     rdx, [rdi+rdi*2]
0x180006d52  add     rdx, rdx
0x180006d55  mov     rcx, [r8+rdx*8+10h]; void **
0x180006d5a  test    rcx, rcx
0x180006d5d  jz      short loc_180006D81
0x180006d5f  cmp     qword ptr [rcx], 0
0x180006d63  jnz     short loc_180006D81
0x180006d65  mov     rax, (funcs_180006D6F - 18000E000h)[r8+rdx*8]
0x180006d6a  test    rax, rax
0x180006d6d  jz      short loc_180006D81
0x180006d6f  call    _guard_dispatch_icall$thunk$10345483385596137414; PaW_InitContext(void * *) ...
0x180006d74  mov     ebx, eax
0x180006d76  test    eax, eax
0x180006d78  js      short loc_180006D97
0x180006d7a  lea     r8, ?g_SupportedAppList@@3PAU_APF_APP_INFO@@A; "TV"
0x180006d81  add     edi, r15d
0x180006d84  cmp     edi, 3
0x180006d87  jb      short loc_180006D4E
0x180006d89  test    ebx, ebx
0x180006d8b  jns     short loc_180006DC1
0x180006d8d  mov     r9d, ebx
0x180006d90  mov     edx, 206h
0x180006d95  jmp     short loc_180006DDD
0x180006d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d9e  cmp     rcx, r12
0x180006da1  jz      short loc_180006D8D
0x180006da3  test    byte ptr [rcx+1Ch], 80h
0x180006da7  jz      short loc_180006D8D
0x180006da9  cmp     byte ptr [rcx+19h], 2
0x180006dad  jb      short loc_180006D8D
0x180006daf  mov     [rsp+80h+var_60], eax
0x180006db3  mov     r9d, edi
0x180006db6  mov     rcx, [rcx+10h]
0x180006dba  call    WPP_SF_dd
0x180006dbf  jmp     short loc_180006D8D
0x180006dc1  mov     rdx, [rbp+StringSecurityDescriptor]
0x180006dc5  mov     ecx, 4
0x180006dca  call    ?GetServerSddlString@@YAJW4APF_SERVER_SECURITY_ENUM@@PEAGH@Z; GetServerSddlString(APF_SERVER_SECURITY_ENUM,ushort *,int)
0x180006dcf  mov     ebx, eax
0x180006dd1  test    eax, eax
0x180006dd3  jns     short loc_180006DF2
0x180006dd5  mov     r9d, eax; char *
0x180006dd8  mov     edx, 20Fh; void *
0x180006ddd  lea     r8, aOnecoreuapDriv; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180006de4  mov     rcx, [rbp+38h]; this
0x180006de8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ded  jmp     loc_1800070A2
0x180006df2  mov     [rbp+SecurityDescriptor], 0
0x180006dfa  xor     r9d, r9d; SecurityDescriptorSize
0x180006dfd  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180006e01  mov     edx, r15d; StringSDRevision
0x180006e04  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180006e08  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006e0e  test    eax, eax
0x180006e10  jnz     short loc_180006E55
0x180006e12  call    cs:__imp_GetLastError
0x180006e18  mov     ebx, eax
0x180006e1a  test    eax, eax
0x180006e1c  jle     short loc_180006E27
0x180006e1e  movzx   ebx, ax
0x180006e21  or      ebx, 80070000h
0x180006e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e2e  cmp     rcx, r12
0x180006e31  jz      loc_180007092
0x180006e37  test    byte ptr [rcx+1Ch], 80h
0x180006e3b  jz      loc_180007092
0x180006e41  cmp     byte ptr [rcx+19h], 2
0x180006e45  jb      loc_180007092
0x180006e4b  mov     edx, 17h
0x180006e50  jmp     loc_180007083
0x180006e55  mov     rax, [rbp+SecurityDescriptor]
0x180006e59  mov     [rsp+80h+var_48], rax
0x180006e5e  lea     rax, ?ApfSvcRpcIfCallback@@YAJPEAX0@Z; ApfSvcRpcIfCallback(void *,void *)
0x180006e65  mov     [rsp+80h+var_50], rax
0x180006e6a  mov     [rsp+80h+var_58], 0
0x180006e72  mov     edi, 4D2h
0x180006e77  mov     [rsp+80h+var_60], edi
0x180006e7b  mov     r15d, 21h ; '!'
0x180006e81  mov     r9d, r15d
0x180006e84  xor     r8d, r8d
0x180006e87  xor     edx, edx
0x180006e89  lea     rbx, qword_18000A300
0x180006e90  mov     rcx, rbx
0x180006e93  call    cs:__imp_RpcServerRegisterIf3
0x180006e99  test    eax, eax
0x180006e9b  jnz     loc_18000702C
0x180006ea1  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180006ea5  lea     edi, [rax+0Ah]
0x180006ea8  mov     edx, edi; MaxCalls
0x180006eaa  lea     rcx, Protseq; "ncalrpc"
0x180006eb1  call    cs:__imp_RpcServerUseProtseqW
0x180006eb7  test    eax, eax
0x180006eb9  jnz     loc_180006FF2
0x180006ebf  mov     [rbp+BindingVector], 0
0x180006ec7  lea     rcx, [rbp+BindingVector]; BindingVector
0x180006ecb  call    cs:__imp_RpcServerInqBindings
0x180006ed1  test    eax, eax
0x180006ed3  jnz     loc_180006F8F
0x180006ed9  xor     r9d, r9d; Annotation
0x180006edc  xor     r8d, r8d; UuidVector
0x180006edf  mov     rdx, [rbp+BindingVector]; BindingVector
0x180006ee3  mov     rcx, rbx; IfSpec
0x180006ee6  call    cs:__imp_RpcEpRegisterW
0x180006eec  test    eax, eax
0x180006eee  jnz     short loc_180006F28
0x180006ef0  mov     rax, [rbp+BindingVector]
0x180006ef4  test    rax, rax
0x180006ef7  jz      short loc_180006F07
0x180006ef9  mov     [rbp+arg_18], rax
0x180006efd  lea     rcx, [rbp+arg_18]; BindingVector
0x180006f01  call    cs:__imp_RpcBindingVectorFree
0x180006f07  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180006f0b  test    rcx, rcx
0x180006f0e  jz      short loc_180006F17
0x180006f10  call    cs:__imp_LocalFree
0x180006f16  nop
0x180006f17  lea     rcx, [rbp+var_40]
0x180006f1b  call    wil__details__lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052______lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___
0x180006f20  nop
0x180006f21  xor     eax, eax
0x180006f23  jmp     loc_1800070B6
0x180006f28  xor     r9d, r9d; Annotation
0x180006f2b  xor     r8d, r8d; UuidVector
0x180006f2e  mov     rdx, [rbp+BindingVector]; BindingVector
0x180006f32  mov     rcx, rbx; IfSpec
0x180006f35  call    cs:__imp_RpcEpRegisterW
0x180006f3b  mov     ebx, eax
0x180006f3d  or      ebx, 80010000h
0x180006f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f4a  cmp     rcx, r12
0x180006f4d  jz      short loc_180006F6F
0x180006f4f  test    byte ptr [rcx+1Ch], 80h
0x180006f53  jz      short loc_180006F6F
0x180006f55  cmp     byte ptr [rcx+19h], 2
0x180006f59  jb      short loc_180006F6F
0x180006f5b  mov     edx, 1Bh
0x180006f60  mov     r9d, ebx
0x180006f63  mov     r8, r13
0x180006f66  mov     rcx, [rcx+10h]
0x180006f6a  call    WPP_SF_d
0x180006f6f  mov     rax, [rbp+BindingVector]
0x180006f73  test    rax, rax
0x180006f76  jz      loc_180007092
0x180006f7c  mov     [rbp+arg_18], rax
0x180006f80  lea     rcx, [rbp+arg_18]; BindingVector
0x180006f84  call    cs:__imp_RpcBindingVectorFree
0x180006f8a  jmp     loc_180007092
0x180006f8f  mov     rdi, [rbp+BindingVector]
0x180006f93  test    rdi, rdi
0x180006f96  jz      short loc_180006FB6
0x180006f98  call    cs:__imp_GetLastError
0x180006f9e  mov     ebx, eax
0x180006fa0  mov     [rbp+arg_18], rdi
0x180006fa4  lea     rcx, [rbp+arg_18]; BindingVector
0x180006fa8  call    cs:__imp_RpcBindingVectorFree
0x180006fae  mov     ecx, ebx; dwErrCode
0x180006fb0  call    cs:__imp_SetLastError
0x180006fb6  mov     [rbp+BindingVector], 0
0x180006fbe  lea     rcx, [rbp+BindingVector]; BindingVector
0x180006fc2  call    cs:__imp_RpcServerInqBindings
0x180006fc8  mov     ebx, eax
0x180006fca  or      ebx, 80010000h
0x180006fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd7  cmp     rcx, r12
0x180006fda  jz      short loc_180006F6F
0x180006fdc  test    byte ptr [rcx+1Ch], 80h
0x180006fe0  jz      short loc_180006F6F
0x180006fe2  cmp     byte ptr [rcx+19h], 2
0x180006fe6  jb      short loc_180006F6F
0x180006fe8  mov     edx, 1Ah
0x180006fed  jmp     loc_180006F60
0x180006ff2  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180006ff6  mov     edx, edi; MaxCalls
0x180006ff8  lea     rcx, Protseq; "ncalrpc"
0x180006fff  call    cs:__imp_RpcServerUseProtseqW
0x180007005  mov     ebx, eax
0x180007007  or      ebx, 80010000h
0x18000700d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007014  cmp     rcx, r12
0x180007017  jz      short loc_180007092
0x180007019  test    byte ptr [rcx+1Ch], 80h
0x18000701d  jz      short loc_180007092
0x18000701f  cmp     byte ptr [rcx+19h], 2
0x180007023  jb      short loc_180007092
0x180007025  mov     edx, 19h
0x18000702a  jmp     short loc_180007083
0x18000702c  mov     rax, [rbp+SecurityDescriptor]
0x180007030  mov     [rsp+80h+var_48], rax
0x180007035  lea     rax, ?ApfSvcRpcIfCallback@@YAJPEAX0@Z; ApfSvcRpcIfCallback(void *,void *)
0x18000703c  mov     [rsp+80h+var_50], rax
0x180007041  mov     [rsp+80h+var_58], 0
0x180007049  mov     [rsp+80h+var_60], edi
0x18000704d  mov     r9d, r15d
0x180007050  xor     r8d, r8d
0x180007053  xor     edx, edx
0x180007055  mov     rcx, rbx
0x180007058  call    cs:__imp_RpcServerRegisterIf3
0x18000705e  mov     ebx, eax
0x180007060  or      ebx, 80010000h
0x180007066  mov     rcx, cs:WPP_GLOBAL_Control
0x18000706d  cmp     rcx, r12
0x180007070  jz      short loc_180007092
0x180007072  test    byte ptr [rcx+1Ch], 80h
0x180007076  jz      short loc_180007092
0x180007078  cmp     byte ptr [rcx+19h], 2
0x18000707c  jb      short loc_180007092
0x18000707e  mov     edx, 18h
0x180007083  mov     r9d, ebx
0x180007086  mov     r8, r13
0x180007089  mov     rcx, [rcx+10h]
0x18000708d  call    WPP_SF_d
0x180007092  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180007096  test    rcx, rcx
0x180007099  jz      short loc_1800070A2
0x18000709b  call    cs:__imp_LocalFree
0x1800070a1  nop
0x1800070a2  lea     rcx, [rbp+var_40]
0x1800070a6  call    wil__details__lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052______lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___
0x1800070ab  nop
0x1800070ac  mov     rcx, rsi; this
0x1800070af  call    ?Cleanup@CApxSvc@@QEAAJXZ; CApxSvc::Cleanup(void)
0x1800070b4  mov     eax, ebx
0x1800070b6  add     rsp, 80h
0x1800070bd  pop     r15
0x1800070bf  pop     r13
0x1800070c1  pop     r12
0x1800070c3  pop     rdi
0x1800070c4  pop     rsi
0x1800070c5  pop     rbx
0x1800070c6  pop     rbp
0x1800070c7  retn
```
