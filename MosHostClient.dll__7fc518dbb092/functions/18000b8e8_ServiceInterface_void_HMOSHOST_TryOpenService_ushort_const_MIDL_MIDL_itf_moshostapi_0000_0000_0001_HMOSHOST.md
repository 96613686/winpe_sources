# ServiceInterface<void *,HMOSHOST__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMOSHOST__ * *)

- ea: `0x18000b8e8`
- end: `0x18000bba2`
- name: `?TryOpenService@?$ServiceInterface@PEAXPEAUHMOSHOST__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMOSHOST__@@@Z`
- size: `698`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a810`

## callees

- `0x180002550`
- `0x180006214`
- `0x180008cb4`
- `0x18000b1a8`
- `0x18000b8e8`
- `0x1800102e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9f1`
- `RPCRT4!RpcBindingBind` at `0x18000ba68`
- `RPCRT4!RpcBindingBind` at `0x18000ba68`
- `RPCRT4!RpcBindingCreateW` at `0x18000ba40`
- `RPCRT4!RpcBindingCreateW` at `0x18000ba40`
- `RPCRT4!RpcBindingFree` at `0x18000bb72`
- `RPCRT4!RpcBindingFree` at `0x18000bb72`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ba0d`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000ba0d`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000b9e9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000ba99`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000baee`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000b9e9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000ba99`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000baee`

## string_xrefs

- `0x18000ba01`: `MapsBrokerRpc\Service`
- `0x18000b9ae`: `MapsBroker`

## pseudocode

```c
__int64 __fastcall ServiceInterface<void *,HMOSHOST__ *>::TryOpenService(
        RPC_IF_HANDLE *a1,
        __int64 a2,
        __int64 a3,
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
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-C8h] BYREF
  RPC_BINDING_HANDLE v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+7Ch] [rbp-84h]
  int v30; // [rsp+84h] [rbp-7Ch]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+A8h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v24 = 2;
  v26 = 0;
  v25 = 0;
  *a4 = 0;
  Binding = 0;
  *(_QWORD *)v21 = 0;
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  v27 = 5;
  v28 = 1;
  v29 = 3;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v27;
  started = StartServiceW(L"MapsBroker");
  v7 = started;
  if ( started >= 0 )
  {
    *(_QWORD *)v21 = 0;
    TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(9, L"MapsBrokerRpc\\Service", v21);
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
    v33 = *(_QWORD *)v21;
    v13 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
    v7 = v13 != 0 ? v13 | 0x80010000 : 0;
    if ( v7 >= 0 )
    {
      v14 = RpcBindingBind(0, Binding, *a1);
      v7 = v14 != 0 ? v14 | 0x80010000 : 0;
      if ( v7 >= 0 )
      {
        if ( *(_QWORD *)v21 )
          FreeTransientObjectSecurityDescriptor(*(_QWORD *)v21);
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
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
    (const char *)v8,
    v18);
LABEL_11:
  if ( *(_QWORD *)v21 )
    FreeTransientObjectSecurityDescriptor(*(_QWORD *)v21);
  if ( v7 == -2147024891 )
  {
    v7 = -2080374777;
    goto LABEL_16;
  }
  if ( v7 >= 0 )
  {
LABEL_20:
    *(_QWORD *)v21 = &v25;
    v23 = Binding;
    v16 = wil::invoke_rpc_nothrow<long (*&)(unsigned short const *,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),unsigned short const * &,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(
            (int)a1 + 8,
            (unsigned int)&v26,
            (unsigned int)&v24,
            (unsigned int)&v23,
            (__int64)v21);
    v7 = v16;
    *a4 = v25;
    if ( v16 >= 0 )
    {
      if ( !Binding )
        return (unsigned int)v7;
      v23 = Binding;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
        (const char *)(unsigned int)v16,
        v20);
      if ( !Binding )
        return (unsigned int)v7;
      v23 = Binding;
    }
    v15 = &v23;
    goto LABEL_26;
  }
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
    (const char *)(unsigned int)v7,
    v19);
  if ( Binding )
  {
    *(_QWORD *)v21 = Binding;
    v15 = (RPC_BINDING_HANDLE *)v21;
LABEL_26:
    RpcBindingFree(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b8e8  mov     [rsp-8+arg_8], rbx
0x18000b8ed  mov     [rsp-8+arg_10], rsi
0x18000b8f2  push    rbp
0x18000b8f3  push    rdi
0x18000b8f4  push    r12
0x18000b8f6  push    r14
0x18000b8f8  push    r15
0x18000b8fa  lea     rbp, [rsp-10h]
0x18000b8ff  sub     rsp, 110h
0x18000b906  mov     rax, cs:__security_cookie
0x18000b90d  xor     rax, rsp
0x18000b910  mov     [rbp+30h+var_28], rax
0x18000b914  mov     r14, r9
0x18000b917  mov     rsi, rcx
0x18000b91a  mov     [rsp+130h+var_E8], 2
0x18000b922  xor     r15d, r15d
0x18000b925  mov     [rsp+130h+var_D0], r15
0x18000b92a  mov     [rsp+130h+var_E0], r15
0x18000b92f  mov     [r9], r15
0x18000b932  mov     [rsp+130h+Binding], r15
0x18000b937  mov     qword ptr [rsp+130h+var_100], r15
0x18000b93c  lea     edx, [r15+1]
0x18000b940  mov     qword ptr [rbp+30h+Template.Version], rdx
0x18000b944  mov     qword ptr [rbp+30h+Template.ProtocolSequence], 3
0x18000b94c  xorps   xmm0, xmm0
0x18000b94f  movdqu  xmmword ptr [rbp+30h+Template.NetworkAddress], xmm0
0x18000b954  mov     qword ptr [rbp+30h+Template.u1], r15
0x18000b958  mov     [rbp+30h+Template.ObjectUuid.Data1], r15d
0x18000b95c  xor     eax, eax
0x18000b95e  mov     qword ptr [rbp+30h+Template.ObjectUuid.Data2], rax
0x18000b962  mov     dword ptr [rbp+30h+Template.ObjectUuid.Data4+4], eax
0x18000b965  mov     [rsp+130h+var_C0], 5
0x18000b96e  mov     [rsp+130h+var_B8], edx
0x18000b972  mov     [rsp+130h+var_B4], 3
0x18000b97b  mov     [rbp+30h+var_AC], eax
0x18000b97e  movdqu  [rbp+30h+var_A8], xmm0
0x18000b983  mov     [rbp+30h+var_98], r15
0x18000b987  mov     [rbp+30h+var_90], r15
0x18000b98b  mov     qword ptr [rbp+30h+Security.Version], rdx
0x18000b98f  mov     [rbp+30h+Security.ServerPrincName], r15
0x18000b993  mov     [rbp+30h+Security.AuthnLevel], 6
0x18000b99a  mov     [rbp+30h+Security.AuthnSvc], 0Ah
0x18000b9a1  mov     [rbp+30h+Security.AuthIdentity], r15
0x18000b9a5  lea     rax, [rsp+130h+var_C0]
0x18000b9aa  mov     [rbp+30h+Security.SecurityQos], rax
0x18000b9ae  lea     rcx, ServiceName; "MapsBroker"
0x18000b9b5  call    ?StartServiceW@@YAJPEBG@Z; StartServiceW(ushort const *)
0x18000b9ba  mov     ebx, eax
0x18000b9bc  lea     r12, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000b9c3  test    eax, eax
0x18000b9c5  jns     short loc_18000B9D4
0x18000b9c7  mov     r9d, eax
0x18000b9ca  mov     edx, 8Ch
0x18000b9cf  jmp     loc_18000BA82
0x18000b9d4  mov     rdi, qword ptr [rsp+130h+var_100]
0x18000b9d9  test    rdi, rdi
0x18000b9dc  jz      short loc_18000B9F7
0x18000b9de  call    cs:__imp_GetLastError
0x18000b9e4  mov     ebx, eax
0x18000b9e6  mov     rcx, rdi
0x18000b9e9  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000b9ef  mov     ecx, ebx; dwErrCode
0x18000b9f1  call    cs:__imp_SetLastError
0x18000b9f7  mov     qword ptr [rsp+130h+var_100], r15
0x18000b9fc  lea     r8, [rsp+130h+var_100]
0x18000ba01  lea     rdx, aMapsbrokerrpcS; "MapsBrokerRpc\\Service"
0x18000ba08  mov     ecx, 9
0x18000ba0d  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000ba13  test    eax, eax
0x18000ba15  jns     short loc_18000BA27
0x18000ba17  mov     rcx, [rbp+38h]; this
0x18000ba1b  mov     r9d, eax; char *
0x18000ba1e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000ba23  mov     ebx, eax
0x18000ba25  jmp     short loc_18000BA8F
0x18000ba27  mov     rax, qword ptr [rsp+130h+var_100]
0x18000ba2c  mov     [rbp+30h+var_90], rax
0x18000ba30  lea     r9, [rsp+130h+Binding]; Binding
0x18000ba35  xor     r8d, r8d; Options
0x18000ba38  lea     rdx, [rbp+30h+Security]; Security
0x18000ba3c  lea     rcx, [rbp+30h+Template]; Template
0x18000ba40  call    cs:__imp_RpcBindingCreateW
0x18000ba46  mov     ecx, eax
0x18000ba48  mov     edi, 80010000h
0x18000ba4d  or      ecx, edi
0x18000ba4f  neg     eax
0x18000ba51  sbb     ebx, ebx
0x18000ba53  and     ebx, ecx
0x18000ba55  jge     short loc_18000BA5E
0x18000ba57  mov     edx, 9Dh
0x18000ba5c  jmp     short loc_18000BA7F
0x18000ba5e  mov     r8, [rsi]; IfSpec
0x18000ba61  mov     rdx, [rsp+130h+Binding]; Binding
0x18000ba66  xor     ecx, ecx; pAsync
0x18000ba68  call    cs:__imp_RpcBindingBind
0x18000ba6e  mov     ecx, eax
0x18000ba70  or      ecx, edi
0x18000ba72  neg     eax
0x18000ba74  sbb     ebx, ebx
0x18000ba76  and     ebx, ecx
0x18000ba78  jge     short loc_18000BAE4
0x18000ba7a  mov     edx, 0A3h; void *
0x18000ba7f  mov     r9d, ebx; char *
0x18000ba82  mov     r8, r12; unsigned int
0x18000ba85  mov     rcx, [rbp+38h]; this
0x18000ba89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba8e  nop
0x18000ba8f  mov     rcx, qword ptr [rsp+130h+var_100]
0x18000ba94  test    rcx, rcx
0x18000ba97  jz      short loc_18000BA9F
0x18000ba99  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000ba9f  cmp     ebx, 80070005h
0x18000baa5  jnz     short loc_18000BAAE
0x18000baa7  mov     ebx, 84000007h
0x18000baac  jmp     short loc_18000BAB2
0x18000baae  test    ebx, ebx
0x18000bab0  jns     short loc_18000BAF4
0x18000bab2  mov     rcx, [rbp+38h]; this
0x18000bab6  mov     r9d, ebx; char *
0x18000bab9  mov     r8, r12; unsigned int
0x18000babc  mov     edx, 0B4h; void *
0x18000bac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bac6  nop
0x18000bac7  mov     rcx, [rsp+130h+Binding]
0x18000bacc  test    rcx, rcx
0x18000bacf  jz      loc_18000BB78
0x18000bad5  mov     qword ptr [rsp+130h+var_100], rcx
0x18000bada  lea     rcx, [rsp+130h+var_100]
0x18000badf  jmp     loc_18000BB72
0x18000bae4  mov     rcx, qword ptr [rsp+130h+var_100]
0x18000bae9  test    rcx, rcx
0x18000baec  jz      short loc_18000BAF4
0x18000baee  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000baf4  lea     rax, [rsp+130h+var_E0]
0x18000baf9  mov     qword ptr [rsp+130h+var_100], rax
0x18000bafe  mov     rax, [rsp+130h+Binding]
0x18000bb03  mov     [rsp+130h+var_F0], rax
0x18000bb08  lea     rcx, [rsi+8]
0x18000bb0c  lea     rax, [rsp+130h+var_100]
0x18000bb11  mov     qword ptr [rsp+130h+var_110], rax; int
0x18000bb16  lea     r9, [rsp+130h+var_F0]
0x18000bb1b  lea     r8, [rsp+130h+var_E8]
0x18000bb20  lea     rdx, [rsp+130h+var_D0]
0x18000bb25  call    ??$invoke_rpc_nothrow@AEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@PEAXPEAPEAX@wil@@YAJAEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@$$QEAPEAX$$QEAPEAPEAX@Z; wil::invoke_rpc_nothrow<long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void * &&,void * * &&)
0x18000bb2a  mov     ebx, eax
0x18000bb2c  mov     rcx, [rsp+130h+var_E0]
0x18000bb31  mov     [r14], rcx
0x18000bb34  test    eax, eax
0x18000bb36  jns     short loc_18000BB5E
0x18000bb38  mov     rcx, [rbp+38h]; this
0x18000bb3c  mov     r9d, eax; char *
0x18000bb3f  mov     r8, r12; unsigned int
0x18000bb42  mov     edx, 0B9h; void *
0x18000bb47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb4c  nop
0x18000bb4d  mov     rcx, [rsp+130h+Binding]
0x18000bb52  test    rcx, rcx
0x18000bb55  jz      short loc_18000BB78
0x18000bb57  mov     [rsp+130h+var_F0], rcx
0x18000bb5c  jmp     short loc_18000BB6D
0x18000bb5e  mov     rax, [rsp+130h+Binding]
0x18000bb63  test    rax, rax
0x18000bb66  jz      short loc_18000BB78
0x18000bb68  mov     [rsp+130h+var_F0], rax
0x18000bb6d  lea     rcx, [rsp+130h+var_F0]; Binding
0x18000bb72  call    cs:__imp_RpcBindingFree
0x18000bb78  mov     eax, ebx
0x18000bb7a  mov     rcx, [rbp+30h+var_28]
0x18000bb7e  xor     rcx, rsp; StackCookie
0x18000bb81  call    __security_check_cookie
0x18000bb86  lea     r11, [rsp+130h+var_20]
0x18000bb8e  mov     rbx, [r11+38h]
0x18000bb92  mov     rsi, [r11+40h]
0x18000bb96  mov     rsp, r11
0x18000bb99  pop     r15
0x18000bb9b  pop     r14
0x18000bb9d  pop     r12
0x18000bb9f  pop     rdi
0x18000bba0  pop     rbp
0x18000bba1  retn
```
