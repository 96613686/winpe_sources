# CreateUdmBindingHandle(void *,void *,void * *)

- ea: `0x1800c5f64`
- end: `0x1800c6118`
- name: `?CreateUdmBindingHandle@@YAJPEAX0PEAPEAX@Z`
- size: `436`
- prototype: `int(void *, void *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c6120`

## callees

- `0x180049800`
- `0x1800c5d1c`
- `0x1800c5f3c`
- `0x1800c5f64`
- `0x1800c6940`

## import_xrefs

- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800c5fe8`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800c5fe8`
- `RPCRT4!RpcBindingBind` at `0x1800c60d3`
- `RPCRT4!RpcBindingBind` at `0x1800c60d3`
- `RPCRT4!RpcBindingCreateW` at `0x1800c60a7`
- `RPCRT4!RpcBindingCreateW` at `0x1800c60a7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800c5fbd`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800c60f1`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800c5fbd`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800c60f1`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800c5fa4`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800c5fa4`

## string_xrefs

- `0x1800c5f98`: `UserDataServiceOneCore\Server`

## pseudocode

```c
__int64 __fastcall CreateUdmBindingHandle(void *a1, __int64 a2, void **a3)
{
  int v5; // ebx
  int TokenInformationNo; // ebx
  RPC_STATUS v8; // eax
  bool v9; // cc
  __int64 v10; // [rsp+20h] [rbp-69h] BYREF
  _QWORD *v11; // [rsp+28h] [rbp-61h] BYREF
  _OWORD v12[2]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v13; // [rsp+50h] [rbp-39h]
  __int64 v14; // [rsp+60h] [rbp-29h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-21h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp+7h] BYREF

  v10 = 0;
  v5 = QueryTransientObjectSecurityDescriptor(9, L"UserDataServiceOneCore\\Server", &v10);
  if ( v5 < 0 )
  {
    TokenInformationNo = v5 | 0x10000000;
LABEL_3:
    if ( v10 )
      FreeTransientObjectSecurityDescriptor();
    return (unsigned int)TokenInformationNo;
  }
  memset(v12, 0, sizeof(v12));
  v14 = 0;
  v13 = 0;
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(&v11);
  if ( (unsigned int)IsCommsSystemService() )
  {
    DWORD1(v12[0]) = 0;
  }
  else
  {
    TokenInformationNo = wil::GetTokenInformationNoThrow<_TOKEN_USER>((void **)&v11, a2);
    if ( TokenInformationNo < 0 )
    {
LABEL_8:
      wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(&v11);
      goto LABEL_3;
    }
    DWORD1(v12[0]) = 17;
    *(_QWORD *)&v13 = *v11;
  }
  v14 = v10;
  *((_QWORD *)&v12[0] + 1) = 0x300000001LL;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v12;
  *(_QWORD *)&Security.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  *(_QWORD *)&Template.Version = 1;
  LODWORD(v12[0]) = 5;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  memset(&Template.NetworkAddress, 0, 40);
  v8 = RpcBindingCreateW(&Template, &Security, 0, a3);
  TokenInformationNo = v8;
  v9 = v8 <= 0;
  if ( v8 || (v8 = RpcBindingBind(0, *a3, L"`"), TokenInformationNo = v8, v9 = v8 <= 0, v8) )
  {
    if ( !v9 )
      TokenInformationNo = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_8;
  }
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(&v11);
  if ( v10 )
    FreeTransientObjectSecurityDescriptor();
  return 0;
}

```

## disassembly

```asm
0x1800c5f64  mov     [rsp-8+arg_0], rbx
0x1800c5f69  push    rbp
0x1800c5f6a  push    rsi
0x1800c5f6b  push    rdi
0x1800c5f6c  lea     rbp, [rsp-47h]
0x1800c5f71  sub     rsp, 0D0h
0x1800c5f78  mov     rax, cs:__security_cookie
0x1800c5f7f  xor     rax, rsp
0x1800c5f82  mov     [rbp+57h+var_18], rax
0x1800c5f86  mov     rdi, r8
0x1800c5f89  mov     [rbp+57h+var_C0], 0
0x1800c5f91  mov     rsi, rdx
0x1800c5f94  lea     r8, [rbp+57h+var_C0]
0x1800c5f98  lea     rdx, aUserdataservic_0; "UserDataServiceOneCore\\Server"
0x1800c5f9f  mov     ecx, 9
0x1800c5fa4  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1800c5faa  mov     ebx, eax
0x1800c5fac  test    eax, eax
0x1800c5fae  jns     short loc_1800C5FCA
0x1800c5fb0  bts     ebx, 1Ch
0x1800c5fb4  mov     rcx, [rbp+57h+var_C0]
0x1800c5fb8  test    rcx, rcx
0x1800c5fbb  jz      short loc_1800C5FC3
0x1800c5fbd  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800c5fc3  mov     eax, ebx
0x1800c5fc5  jmp     loc_1800C60F9
0x1800c5fca  xorps   xmm0, xmm0
0x1800c5fcd  lea     rcx, [rbp+57h+var_B8]; void *
0x1800c5fd1  xor     eax, eax
0x1800c5fd3  movups  [rbp+57h+var_B0], xmm0
0x1800c5fd7  mov     [rbp+57h+var_80], rax
0x1800c5fdb  movups  [rbp+57h+var_A0], xmm0
0x1800c5fdf  movups  [rbp+57h+var_90], xmm0
0x1800c5fe3  call    ??$?0$00X@?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
0x1800c5fe8  call    cs:__imp_IsCommsSystemService
0x1800c5fee  test    eax, eax
0x1800c5ff0  jnz     short loc_1800C6023
0x1800c5ff2  mov     rdx, rsi
0x1800c5ff5  lea     rcx, [rbp+57h+var_B8]
0x1800c5ff9  call    ??$GetTokenInformationNoThrow@U_TOKEN_USER@@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::GetTokenInformationNoThrow<_TOKEN_USER>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800c5ffe  mov     ebx, eax
0x1800c6000  test    eax, eax
0x1800c6002  jns     short loc_1800C600F
0x1800c6004  lea     rcx, [rbp+57h+var_B8]
0x1800c6008  call    ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
0x1800c600d  jmp     short loc_1800C5FB4
0x1800c600f  mov     rax, [rbp+57h+var_B8]
0x1800c6013  mov     dword ptr [rbp+57h+var_B0+4], 11h
0x1800c601a  mov     rcx, [rax]
0x1800c601d  mov     qword ptr [rbp+57h+var_90], rcx
0x1800c6021  jmp     short loc_1800C602A
0x1800c6023  mov     dword ptr [rbp+57h+var_B0+4], 0
0x1800c602a  mov     rax, [rbp+57h+var_C0]
0x1800c602e  mov     ecx, 1
0x1800c6033  mov     [rbp+57h+var_80], rax
0x1800c6037  xorps   xmm0, xmm0
0x1800c603a  lea     rax, [rbp+57h+var_B0]
0x1800c603e  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x1800c6041  mov     [rbp+57h+Security.SecurityQos], rax
0x1800c6045  mov     r9, rdi; Binding
0x1800c6048  lea     edx, [rcx+2]
0x1800c604b  mov     qword ptr [rbp+57h+Security.Version], rcx
0x1800c604f  xor     eax, eax
0x1800c6051  mov     dword ptr [rbp+57h+var_B0+0Ch], edx
0x1800c6054  mov     qword ptr [rbp+57h+Template.ProtocolSequence], rdx
0x1800c6058  xor     r8d, r8d; Options
0x1800c605b  mov     qword ptr [rbp+57h+Template.Version], rcx
0x1800c605f  lea     rdx, [rbp+57h+Security]; Security
0x1800c6063  lea     rcx, [rbp+57h+Template]; Template
0x1800c6067  mov     dword ptr [rbp+57h+var_B0], 5
0x1800c606e  mov     [rbp+57h+Security.ServerPrincName], 0
0x1800c6076  mov     [rbp+57h+Security.AuthnLevel], 6
0x1800c607d  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x1800c6084  mov     [rbp+57h+Security.AuthIdentity], 0
0x1800c608c  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x1800c6091  mov     qword ptr [rbp+57h+Template.u1], 0
0x1800c6099  mov     [rbp+57h+Template.ObjectUuid.Data1], 0
0x1800c60a0  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x1800c60a4  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x1800c60a7  call    cs:__imp_RpcBindingCreateW
0x1800c60ad  mov     ebx, eax
0x1800c60af  test    eax, eax
0x1800c60b1  jz      short loc_1800C60C7
0x1800c60b3  jle     loc_1800C6004
0x1800c60b9  movzx   ebx, ax
0x1800c60bc  or      ebx, 80070000h
0x1800c60c2  jmp     loc_1800C6004
0x1800c60c7  mov     rdx, [rdi]; Binding
0x1800c60ca  lea     r8, asc_1800E3D40; "`"
0x1800c60d1  xor     ecx, ecx; pAsync
0x1800c60d3  call    cs:__imp_RpcBindingBind
0x1800c60d9  mov     ebx, eax
0x1800c60db  test    eax, eax
0x1800c60dd  jnz     short loc_1800C60B3
0x1800c60df  lea     rcx, [rbp+57h+var_B8]
0x1800c60e3  call    ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
0x1800c60e8  mov     rcx, [rbp+57h+var_C0]
0x1800c60ec  test    rcx, rcx
0x1800c60ef  jz      short loc_1800C60F7
0x1800c60f1  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800c60f7  xor     eax, eax
0x1800c60f9  mov     rcx, [rbp+57h+var_18]
0x1800c60fd  xor     rcx, rsp; StackCookie
0x1800c6100  call    __security_check_cookie
0x1800c6105  mov     rbx, [rsp+0E0h+arg_0]
0x1800c610d  add     rsp, 0D0h
0x1800c6114  pop     rdi
0x1800c6115  pop     rsi
0x1800c6116  pop     rbp
0x1800c6117  retn
```
