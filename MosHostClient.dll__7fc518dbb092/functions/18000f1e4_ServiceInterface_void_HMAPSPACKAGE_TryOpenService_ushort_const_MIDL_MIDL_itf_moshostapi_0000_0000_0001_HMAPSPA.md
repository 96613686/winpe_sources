# ServiceInterface<void *,HMAPSPACKAGE__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSPACKAGE__ * *)

- ea: `0x18000f1e4`
- end: `0x18000f486`
- name: `?TryOpenService@?$ServiceInterface@PEAXPEAUHMAPSPACKAGE__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSPACKAGE__@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f0c0`

## callees

- `0x180002550`
- `0x180006214`
- `0x180008cb4`
- `0x18000b1a8`
- `0x18000f1e4`
- `0x1800102e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2df`
- `RPCRT4!RpcBindingBind` at `0x18000f356`
- `RPCRT4!RpcBindingBind` at `0x18000f356`
- `RPCRT4!RpcBindingCreateW` at `0x18000f32e`
- `RPCRT4!RpcBindingCreateW` at `0x18000f32e`
- `RPCRT4!RpcBindingFree` at `0x18000f460`
- `RPCRT4!RpcBindingFree` at `0x18000f460`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000f2fb`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000f2fb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f2d7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f387`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f3dc`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f2d7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f387`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f3dc`

## string_xrefs

- `0x18000f2ef`: `MapsBrokerRpc\Service`
- `0x18000f29c`: `MapsBroker`

## pseudocode

```c
__int64 __fastcall ServiceInterface<void *,HMAPSPACKAGE__ *>::TryOpenService(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  signed int started; // eax
  signed int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int TransientObjectSecurityDescriptor; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // eax
  RPC_BINDING_HANDLE *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-B9h]
  int v19[2]; // [rsp+30h] [rbp-A9h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-A1h] BYREF
  RPC_BINDING_HANDLE v21; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v22; // [rsp+48h] [rbp-91h] BYREF
  __int64 v23; // [rsp+50h] [rbp-89h] BYREF
  __int64 v24; // [rsp+58h] [rbp-81h] BYREF
  __int64 v25; // [rsp+60h] [rbp-79h] BYREF
  int v26; // [rsp+68h] [rbp-71h]
  __int64 v27; // [rsp+6Ch] [rbp-6Dh]
  int v28; // [rsp+74h] [rbp-65h]
  __int128 v29; // [rsp+78h] [rbp-61h]
  __int64 v30; // [rsp+88h] [rbp-51h]
  __int64 v31; // [rsp+90h] [rbp-49h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+98h] [rbp-41h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+C0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v24 = a2;
  v22 = a3;
  v23 = 0;
  *a4 = 0;
  Binding = 0;
  *(_QWORD *)v19 = 0;
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  v25 = 5;
  v26 = 1;
  v27 = 3;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v25;
  started = StartServiceW(L"MapsBroker");
  v7 = started;
  if ( started >= 0 )
  {
    *(_QWORD *)v19 = 0;
    TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(9, L"MapsBrokerRpc\\Service", v19);
    if ( TransientObjectSecurityDescriptor < 0 )
    {
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             v11,
             v12,
             (const char *)(unsigned int)TransientObjectSecurityDescriptor,
             v18);
      goto LABEL_11;
    }
    v31 = *(_QWORD *)v19;
    v13 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
    v7 = v13 != 0 ? v13 | 0x80010000 : 0;
    if ( v7 >= 0 )
    {
      v14 = RpcBindingBind(0, Binding, *(RPC_IF_HANDLE *)a1);
      v7 = v14 != 0 ? v14 | 0x80010000 : 0;
      if ( v7 >= 0 )
      {
        if ( *(_QWORD *)v19 )
          FreeTransientObjectSecurityDescriptor(*(_QWORD *)v19);
        goto LABEL_20;
      }
      v9 = 163;
    }
    else
    {
      v9 = 157;
    }
    v8 = (unsigned int)v7;
  }
  else
  {
    v8 = (unsigned int)started;
    v9 = 140;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
    (const char *)v8);
LABEL_11:
  if ( *(_QWORD *)v19 )
    FreeTransientObjectSecurityDescriptor(*(_QWORD *)v19);
  if ( v7 == -2147024891 )
  {
    v7 = -2080374777;
    goto LABEL_16;
  }
  if ( v7 >= 0 )
  {
LABEL_20:
    *(_QWORD *)v19 = &v23;
    v21 = Binding;
    v16 = wil::invoke_rpc_nothrow<long (*&)(unsigned short const *,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),unsigned short const * &,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(
            (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 8),
            &v24,
            &v22,
            &v21,
            v19);
    v7 = v16;
    *a4 = v23;
    if ( v16 >= 0 )
    {
      if ( !Binding )
        return (unsigned int)v7;
      v21 = Binding;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
        (const char *)(unsigned int)v16);
      if ( !Binding )
        return (unsigned int)v7;
      v21 = Binding;
    }
    v15 = &v21;
    goto LABEL_26;
  }
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
    (const char *)(unsigned int)v7);
  if ( Binding )
  {
    *(_QWORD *)v19 = Binding;
    v15 = (RPC_BINDING_HANDLE *)v19;
LABEL_26:
    RpcBindingFree(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f1e4  push    rbp
0x18000f1e6  push    rbx
0x18000f1e7  push    rsi
0x18000f1e8  push    rdi
0x18000f1e9  push    r12
0x18000f1eb  push    r14
0x18000f1ed  push    r15
0x18000f1ef  lea     rbp, [rsp-27h]
0x18000f1f4  sub     rsp, 100h
0x18000f1fb  mov     rax, cs:__security_cookie
0x18000f202  xor     rax, rsp
0x18000f205  mov     [rbp+57h+var_38], rax
0x18000f209  mov     r14, r9
0x18000f20c  mov     rsi, rcx
0x18000f20f  mov     [rsp+130h+var_D8], rdx
0x18000f214  mov     [rsp+130h+var_E8], r8d
0x18000f219  xor     r15d, r15d
0x18000f21c  mov     [rsp+130h+var_E0], r15
0x18000f221  mov     [r9], r15
0x18000f224  mov     [rsp+130h+Binding], r15
0x18000f229  mov     qword ptr [rsp+130h+var_100], r15
0x18000f22e  lea     edx, [r15+1]
0x18000f232  mov     qword ptr [rbp+57h+Template.Version], rdx
0x18000f236  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x18000f23e  xorps   xmm0, xmm0
0x18000f241  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18000f246  mov     qword ptr [rbp+57h+Template.u1], r15
0x18000f24a  mov     [rbp+57h+Template.ObjectUuid.Data1], r15d
0x18000f24e  xor     eax, eax
0x18000f250  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x18000f254  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x18000f257  mov     [rbp+57h+var_D0], 5
0x18000f25f  mov     [rbp+57h+var_C8], edx
0x18000f262  mov     [rbp+57h+var_C4], 3
0x18000f26a  mov     [rbp+57h+var_BC], eax
0x18000f26d  movdqu  [rbp+57h+var_B8], xmm0
0x18000f272  mov     [rbp+57h+var_A8], r15
0x18000f276  mov     [rbp+57h+var_A0], r15
0x18000f27a  mov     qword ptr [rbp+57h+Security.Version], rdx
0x18000f27e  mov     [rbp+57h+Security.ServerPrincName], r15
0x18000f282  mov     [rbp+57h+Security.AuthnLevel], 6
0x18000f289  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18000f290  mov     [rbp+57h+Security.AuthIdentity], r15
0x18000f294  lea     rax, [rbp+57h+var_D0]
0x18000f298  mov     [rbp+57h+Security.SecurityQos], rax
0x18000f29c  lea     rcx, aMapsbroker_1; "MapsBroker"
0x18000f2a3  call    ?StartServiceW@@YAJPEBG@Z; StartServiceW(ushort const *)
0x18000f2a8  mov     ebx, eax
0x18000f2aa  lea     r12, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000f2b1  test    eax, eax
0x18000f2b3  jns     short loc_18000F2C2
0x18000f2b5  mov     r9d, eax
0x18000f2b8  mov     edx, 8Ch
0x18000f2bd  jmp     loc_18000F370
0x18000f2c2  mov     rdi, qword ptr [rsp+130h+var_100]
0x18000f2c7  test    rdi, rdi
0x18000f2ca  jz      short loc_18000F2E5
0x18000f2cc  call    cs:__imp_GetLastError
0x18000f2d2  mov     ebx, eax
0x18000f2d4  mov     rcx, rdi
0x18000f2d7  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000f2dd  mov     ecx, ebx; dwErrCode
0x18000f2df  call    cs:__imp_SetLastError
0x18000f2e5  mov     qword ptr [rsp+130h+var_100], r15
0x18000f2ea  lea     r8, [rsp+130h+var_100]
0x18000f2ef  lea     rdx, aMapsbrokerrpcS_1; "MapsBrokerRpc\\Service"
0x18000f2f6  mov     ecx, 9
0x18000f2fb  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000f301  test    eax, eax
0x18000f303  jns     short loc_18000F315
0x18000f305  mov     rcx, [rbp+5Fh]; this
0x18000f309  mov     r9d, eax; char *
0x18000f30c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000f311  mov     ebx, eax
0x18000f313  jmp     short loc_18000F37D
0x18000f315  mov     rax, qword ptr [rsp+130h+var_100]
0x18000f31a  mov     [rbp+57h+var_A0], rax
0x18000f31e  lea     r9, [rsp+130h+Binding]; Binding
0x18000f323  xor     r8d, r8d; Options
0x18000f326  lea     rdx, [rbp+57h+Security]; Security
0x18000f32a  lea     rcx, [rbp+57h+Template]; Template
0x18000f32e  call    cs:__imp_RpcBindingCreateW
0x18000f334  mov     ecx, eax
0x18000f336  mov     edi, 80010000h
0x18000f33b  or      ecx, edi
0x18000f33d  neg     eax
0x18000f33f  sbb     ebx, ebx
0x18000f341  and     ebx, ecx
0x18000f343  jge     short loc_18000F34C
0x18000f345  mov     edx, 9Dh
0x18000f34a  jmp     short loc_18000F36D
0x18000f34c  mov     r8, [rsi]; IfSpec
0x18000f34f  mov     rdx, [rsp+130h+Binding]; Binding
0x18000f354  xor     ecx, ecx; pAsync
0x18000f356  call    cs:__imp_RpcBindingBind
0x18000f35c  mov     ecx, eax
0x18000f35e  or      ecx, edi
0x18000f360  neg     eax
0x18000f362  sbb     ebx, ebx
0x18000f364  and     ebx, ecx
0x18000f366  jge     short loc_18000F3D2
0x18000f368  mov     edx, 0A3h; void *
0x18000f36d  mov     r9d, ebx; char *
0x18000f370  mov     r8, r12; unsigned int
0x18000f373  mov     rcx, [rbp+5Fh]; this
0x18000f377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f37c  nop
0x18000f37d  mov     rcx, qword ptr [rsp+130h+var_100]
0x18000f382  test    rcx, rcx
0x18000f385  jz      short loc_18000F38D
0x18000f387  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000f38d  cmp     ebx, 80070005h
0x18000f393  jnz     short loc_18000F39C
0x18000f395  mov     ebx, 84000007h
0x18000f39a  jmp     short loc_18000F3A0
0x18000f39c  test    ebx, ebx
0x18000f39e  jns     short loc_18000F3E2
0x18000f3a0  mov     rcx, [rbp+5Fh]; this
0x18000f3a4  mov     r9d, ebx; char *
0x18000f3a7  mov     r8, r12; unsigned int
0x18000f3aa  mov     edx, 0B4h; void *
0x18000f3af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f3b4  nop
0x18000f3b5  mov     rcx, [rsp+130h+Binding]
0x18000f3ba  test    rcx, rcx
0x18000f3bd  jz      loc_18000F466
0x18000f3c3  mov     qword ptr [rsp+130h+var_100], rcx
0x18000f3c8  lea     rcx, [rsp+130h+var_100]
0x18000f3cd  jmp     loc_18000F460
0x18000f3d2  mov     rcx, qword ptr [rsp+130h+var_100]
0x18000f3d7  test    rcx, rcx
0x18000f3da  jz      short loc_18000F3E2
0x18000f3dc  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000f3e2  lea     rax, [rsp+130h+var_E0]
0x18000f3e7  mov     qword ptr [rsp+130h+var_100], rax
0x18000f3ec  mov     rax, [rsp+130h+Binding]
0x18000f3f1  mov     [rsp+130h+var_F0], rax
0x18000f3f6  lea     rcx, [rsi+8]
0x18000f3fa  lea     rax, [rsp+130h+var_100]
0x18000f3ff  mov     qword ptr [rsp+130h+var_110], rax; int
0x18000f404  lea     r9, [rsp+130h+var_F0]
0x18000f409  lea     r8, [rsp+130h+var_E8]
0x18000f40e  lea     rdx, [rsp+130h+var_D8]
0x18000f413  call    ??$invoke_rpc_nothrow@AEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@PEAXPEAPEAX@wil@@YAJAEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@$$QEAPEAX$$QEAPEAPEAX@Z; wil::invoke_rpc_nothrow<long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void * &&,void * * &&)
0x18000f418  mov     ebx, eax
0x18000f41a  mov     rcx, [rsp+130h+var_E0]
0x18000f41f  mov     [r14], rcx
0x18000f422  test    eax, eax
0x18000f424  jns     short loc_18000F44C
0x18000f426  mov     rcx, [rbp+5Fh]; this
0x18000f42a  mov     r9d, eax; char *
0x18000f42d  mov     r8, r12; unsigned int
0x18000f430  mov     edx, 0B9h; void *
0x18000f435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f43a  nop
0x18000f43b  mov     rcx, [rsp+130h+Binding]
0x18000f440  test    rcx, rcx
0x18000f443  jz      short loc_18000F466
0x18000f445  mov     [rsp+130h+var_F0], rcx
0x18000f44a  jmp     short loc_18000F45B
0x18000f44c  mov     rax, [rsp+130h+Binding]
0x18000f451  test    rax, rax
0x18000f454  jz      short loc_18000F466
0x18000f456  mov     [rsp+130h+var_F0], rax
0x18000f45b  lea     rcx, [rsp+130h+var_F0]; Binding
0x18000f460  call    cs:__imp_RpcBindingFree
0x18000f466  mov     eax, ebx
0x18000f468  mov     rcx, [rbp+57h+var_38]
0x18000f46c  xor     rcx, rsp; StackCookie
0x18000f46f  call    __security_check_cookie
0x18000f474  add     rsp, 100h
0x18000f47b  pop     r15
0x18000f47d  pop     r14
0x18000f47f  pop     r12
0x18000f481  pop     rdi
0x18000f482  pop     rsi
0x18000f483  pop     rbx
0x18000f484  pop     rbp
0x18000f485  retn
```
