# ServiceInterface<void *,HODML__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HODML__ * *)

- ea: `0x18000dad8`
- end: `0x18000dd7a`
- name: `?TryOpenService@?$ServiceInterface@PEAXPEAUHODML__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHODML__@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE *, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d760`

## callees

- `0x180002550`
- `0x180006214`
- `0x180008cb4`
- `0x18000b1a8`
- `0x18000dad8`
- `0x1800102e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbd3`
- `RPCRT4!RpcBindingBind` at `0x18000dc4a`
- `RPCRT4!RpcBindingBind` at `0x18000dc4a`
- `RPCRT4!RpcBindingCreateW` at `0x18000dc22`
- `RPCRT4!RpcBindingCreateW` at `0x18000dc22`
- `RPCRT4!RpcBindingFree` at `0x18000dd54`
- `RPCRT4!RpcBindingFree` at `0x18000dd54`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000dbef`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000dbef`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000dbcb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000dc7b`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000dcd0`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000dbcb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000dc7b`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000dcd0`

## string_xrefs

- `0x18000dbe3`: `MapsBrokerRpc\Service`
- `0x18000db90`: `MapsBroker`

## pseudocode

```c
__int64 __fastcall ServiceInterface<void *,HODML__ *>::TryOpenService(
        RPC_IF_HANDLE *a1,
        __int64 a2,
        int a3,
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
  int v19; // [rsp+20h] [rbp-B9h]
  int v20; // [rsp+20h] [rbp-B9h]
  int v21[2]; // [rsp+30h] [rbp-A9h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-A1h] BYREF
  RPC_BINDING_HANDLE v23; // [rsp+40h] [rbp-99h] BYREF
  int v24; // [rsp+48h] [rbp-91h] BYREF
  __int64 v25; // [rsp+50h] [rbp-89h] BYREF
  __int64 v26; // [rsp+58h] [rbp-81h] BYREF
  __int64 v27; // [rsp+60h] [rbp-79h] BYREF
  int v28; // [rsp+68h] [rbp-71h]
  __int64 v29; // [rsp+6Ch] [rbp-6Dh]
  int v30; // [rsp+74h] [rbp-65h]
  __int128 v31; // [rsp+78h] [rbp-61h]
  __int64 v32; // [rsp+88h] [rbp-51h]
  __int64 v33; // [rsp+90h] [rbp-49h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+98h] [rbp-41h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+C0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v26 = a2;
  v24 = a3;
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
0x18000dad8  push    rbp
0x18000dada  push    rbx
0x18000dadb  push    rsi
0x18000dadc  push    rdi
0x18000dadd  push    r12
0x18000dadf  push    r14
0x18000dae1  push    r15
0x18000dae3  lea     rbp, [rsp-27h]
0x18000dae8  sub     rsp, 100h
0x18000daef  mov     rax, cs:__security_cookie
0x18000daf6  xor     rax, rsp
0x18000daf9  mov     [rbp+57h+var_38], rax
0x18000dafd  mov     r14, r9
0x18000db00  mov     rsi, rcx
0x18000db03  mov     [rsp+130h+var_D8], rdx
0x18000db08  mov     [rsp+130h+var_E8], r8d
0x18000db0d  xor     r15d, r15d
0x18000db10  mov     [rsp+130h+var_E0], r15
0x18000db15  mov     [r9], r15
0x18000db18  mov     [rsp+130h+Binding], r15
0x18000db1d  mov     qword ptr [rsp+130h+var_100], r15
0x18000db22  lea     edx, [r15+1]
0x18000db26  mov     qword ptr [rbp+57h+Template.Version], rdx
0x18000db2a  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x18000db32  xorps   xmm0, xmm0
0x18000db35  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18000db3a  mov     qword ptr [rbp+57h+Template.u1], r15
0x18000db3e  mov     [rbp+57h+Template.ObjectUuid.Data1], r15d
0x18000db42  xor     eax, eax
0x18000db44  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x18000db48  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x18000db4b  mov     [rbp+57h+var_D0], 5
0x18000db53  mov     [rbp+57h+var_C8], edx
0x18000db56  mov     [rbp+57h+var_C4], 3
0x18000db5e  mov     [rbp+57h+var_BC], eax
0x18000db61  movdqu  [rbp+57h+var_B8], xmm0
0x18000db66  mov     [rbp+57h+var_A8], r15
0x18000db6a  mov     [rbp+57h+var_A0], r15
0x18000db6e  mov     qword ptr [rbp+57h+Security.Version], rdx
0x18000db72  mov     [rbp+57h+Security.ServerPrincName], r15
0x18000db76  mov     [rbp+57h+Security.AuthnLevel], 6
0x18000db7d  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18000db84  mov     [rbp+57h+Security.AuthIdentity], r15
0x18000db88  lea     rax, [rbp+57h+var_D0]
0x18000db8c  mov     [rbp+57h+Security.SecurityQos], rax
0x18000db90  lea     rcx, aMapsbroker_0; "MapsBroker"
0x18000db97  call    ?StartServiceW@@YAJPEBG@Z; StartServiceW(ushort const *)
0x18000db9c  mov     ebx, eax
0x18000db9e  lea     r12, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000dba5  test    eax, eax
0x18000dba7  jns     short loc_18000DBB6
0x18000dba9  mov     r9d, eax
0x18000dbac  mov     edx, 8Ch
0x18000dbb1  jmp     loc_18000DC64
0x18000dbb6  mov     rdi, qword ptr [rsp+130h+var_100]
0x18000dbbb  test    rdi, rdi
0x18000dbbe  jz      short loc_18000DBD9
0x18000dbc0  call    cs:__imp_GetLastError
0x18000dbc6  mov     ebx, eax
0x18000dbc8  mov     rcx, rdi
0x18000dbcb  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000dbd1  mov     ecx, ebx; dwErrCode
0x18000dbd3  call    cs:__imp_SetLastError
0x18000dbd9  mov     qword ptr [rsp+130h+var_100], r15
0x18000dbde  lea     r8, [rsp+130h+var_100]
0x18000dbe3  lea     rdx, aMapsbrokerrpcS_0; "MapsBrokerRpc\\Service"
0x18000dbea  mov     ecx, 9
0x18000dbef  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000dbf5  test    eax, eax
0x18000dbf7  jns     short loc_18000DC09
0x18000dbf9  mov     rcx, [rbp+5Fh]; this
0x18000dbfd  mov     r9d, eax; char *
0x18000dc00  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000dc05  mov     ebx, eax
0x18000dc07  jmp     short loc_18000DC71
0x18000dc09  mov     rax, qword ptr [rsp+130h+var_100]
0x18000dc0e  mov     [rbp+57h+var_A0], rax
0x18000dc12  lea     r9, [rsp+130h+Binding]; Binding
0x18000dc17  xor     r8d, r8d; Options
0x18000dc1a  lea     rdx, [rbp+57h+Security]; Security
0x18000dc1e  lea     rcx, [rbp+57h+Template]; Template
0x18000dc22  call    cs:__imp_RpcBindingCreateW
0x18000dc28  mov     ecx, eax
0x18000dc2a  mov     edi, 80010000h
0x18000dc2f  or      ecx, edi
0x18000dc31  neg     eax
0x18000dc33  sbb     ebx, ebx
0x18000dc35  and     ebx, ecx
0x18000dc37  jge     short loc_18000DC40
0x18000dc39  mov     edx, 9Dh
0x18000dc3e  jmp     short loc_18000DC61
0x18000dc40  mov     r8, [rsi]; IfSpec
0x18000dc43  mov     rdx, [rsp+130h+Binding]; Binding
0x18000dc48  xor     ecx, ecx; pAsync
0x18000dc4a  call    cs:__imp_RpcBindingBind
0x18000dc50  mov     ecx, eax
0x18000dc52  or      ecx, edi
0x18000dc54  neg     eax
0x18000dc56  sbb     ebx, ebx
0x18000dc58  and     ebx, ecx
0x18000dc5a  jge     short loc_18000DCC6
0x18000dc5c  mov     edx, 0A3h; void *
0x18000dc61  mov     r9d, ebx; char *
0x18000dc64  mov     r8, r12; unsigned int
0x18000dc67  mov     rcx, [rbp+5Fh]; this
0x18000dc6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc70  nop
0x18000dc71  mov     rcx, qword ptr [rsp+130h+var_100]
0x18000dc76  test    rcx, rcx
0x18000dc79  jz      short loc_18000DC81
0x18000dc7b  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000dc81  cmp     ebx, 80070005h
0x18000dc87  jnz     short loc_18000DC90
0x18000dc89  mov     ebx, 84000007h
0x18000dc8e  jmp     short loc_18000DC94
0x18000dc90  test    ebx, ebx
0x18000dc92  jns     short loc_18000DCD6
0x18000dc94  mov     rcx, [rbp+5Fh]; this
0x18000dc98  mov     r9d, ebx; char *
0x18000dc9b  mov     r8, r12; unsigned int
0x18000dc9e  mov     edx, 0B4h; void *
0x18000dca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dca8  nop
0x18000dca9  mov     rcx, [rsp+130h+Binding]
0x18000dcae  test    rcx, rcx
0x18000dcb1  jz      loc_18000DD5A
0x18000dcb7  mov     qword ptr [rsp+130h+var_100], rcx
0x18000dcbc  lea     rcx, [rsp+130h+var_100]
0x18000dcc1  jmp     loc_18000DD54
0x18000dcc6  mov     rcx, qword ptr [rsp+130h+var_100]
0x18000dccb  test    rcx, rcx
0x18000dcce  jz      short loc_18000DCD6
0x18000dcd0  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000dcd6  lea     rax, [rsp+130h+var_E0]
0x18000dcdb  mov     qword ptr [rsp+130h+var_100], rax
0x18000dce0  mov     rax, [rsp+130h+Binding]
0x18000dce5  mov     [rsp+130h+var_F0], rax
0x18000dcea  lea     rcx, [rsi+8]
0x18000dcee  lea     rax, [rsp+130h+var_100]
0x18000dcf3  mov     qword ptr [rsp+130h+var_110], rax; int
0x18000dcf8  lea     r9, [rsp+130h+var_F0]
0x18000dcfd  lea     r8, [rsp+130h+var_E8]
0x18000dd02  lea     rdx, [rsp+130h+var_D8]
0x18000dd07  call    ??$invoke_rpc_nothrow@AEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@PEAXPEAPEAX@wil@@YAJAEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@$$QEAPEAX$$QEAPEAPEAX@Z; wil::invoke_rpc_nothrow<long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void * &&,void * * &&)
0x18000dd0c  mov     ebx, eax
0x18000dd0e  mov     rcx, [rsp+130h+var_E0]
0x18000dd13  mov     [r14], rcx
0x18000dd16  test    eax, eax
0x18000dd18  jns     short loc_18000DD40
0x18000dd1a  mov     rcx, [rbp+5Fh]; this
0x18000dd1e  mov     r9d, eax; char *
0x18000dd21  mov     r8, r12; unsigned int
0x18000dd24  mov     edx, 0B9h; void *
0x18000dd29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd2e  nop
0x18000dd2f  mov     rcx, [rsp+130h+Binding]
0x18000dd34  test    rcx, rcx
0x18000dd37  jz      short loc_18000DD5A
0x18000dd39  mov     [rsp+130h+var_F0], rcx
0x18000dd3e  jmp     short loc_18000DD4F
0x18000dd40  mov     rax, [rsp+130h+Binding]
0x18000dd45  test    rax, rax
0x18000dd48  jz      short loc_18000DD5A
0x18000dd4a  mov     [rsp+130h+var_F0], rax
0x18000dd4f  lea     rcx, [rsp+130h+var_F0]; Binding
0x18000dd54  call    cs:__imp_RpcBindingFree
0x18000dd5a  mov     eax, ebx
0x18000dd5c  mov     rcx, [rbp+57h+var_38]
0x18000dd60  xor     rcx, rsp; StackCookie
0x18000dd63  call    __security_check_cookie
0x18000dd68  add     rsp, 100h
0x18000dd6f  pop     r15
0x18000dd71  pop     r14
0x18000dd73  pop     r12
0x18000dd75  pop     rdi
0x18000dd76  pop     rsi
0x18000dd77  pop     rbx
0x18000dd78  pop     rbp
0x18000dd79  retn
```
