# CreateUdmBindingHandle(void *,void *,void * *)

- ea: `0x1801ffa60`
- end: `0x1801ffc2d`
- name: `?CreateUdmBindingHandle@@YAJPEAX0PEAPEAX@Z`
- size: `461`
- prototype: `int(void *, void *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c5104`

## callees

- `0x1800210f0`
- `0x1800f0260`
- `0x1800f0f0c`
- `0x1801ffa60`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x1801ffbe4`
- `RPCRT4!RpcBindingBind` at `0x1801ffbe4`
- `RPCRT4!RpcBindingCreateW` at `0x1801ffba1`
- `RPCRT4!RpcBindingCreateW` at `0x1801ffba1`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1801ffab9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1801ffbce`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1801ffc06`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1801ffab9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1801ffbce`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1801ffc06`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1801ffaa0`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1801ffaa0`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1801ffae1`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1801ffae1`

## string_xrefs

- `0x1801ffa94`: `UserDataServiceOneCore\Server`

## pseudocode

```c
__int64 __fastcall CreateUdmBindingHandle(void *a1, __int64 a2, void **a3)
{
  int v5; // ebx
  int token_information; // ebx
  void *v8; // rbx
  RPC_STATUS v9; // eax
  unsigned int v10; // edi
  bool v11; // cc
  __int64 v12; // [rsp+20h] [rbp-69h] BYREF
  void *Block; // [rsp+28h] [rbp-61h] BYREF
  _OWORD v14[2]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v15; // [rsp+50h] [rbp-39h]
  __int64 v16; // [rsp+60h] [rbp-29h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-21h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp+7h] BYREF

  v12 = 0;
  v5 = QueryTransientObjectSecurityDescriptor(9, L"UserDataServiceOneCore\\Server", &v12);
  if ( v5 < 0 )
  {
    token_information = v5 | 0x10000000;
LABEL_3:
    if ( v12 )
      FreeTransientObjectSecurityDescriptor();
    return (unsigned int)token_information;
  }
  v8 = 0;
  v16 = 0;
  memset(v14, 0, sizeof(v14));
  Block = 0;
  v15 = 0;
  if ( (unsigned int)IsCommsSystemService() )
  {
    DWORD1(v14[0]) = 0;
  }
  else
  {
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a2);
    if ( token_information < 0 )
    {
      if ( Block )
        operator delete(Block);
      goto LABEL_3;
    }
    v8 = Block;
    DWORD1(v14[0]) = 17;
    *(_QWORD *)&v15 = *(_QWORD *)Block;
  }
  v16 = v12;
  *((_QWORD *)&v14[0] + 1) = 0x300000001LL;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v14;
  *(_QWORD *)&Security.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  *(_QWORD *)&Template.Version = 1;
  LODWORD(v14[0]) = 5;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  memset(&Template.NetworkAddress, 0, 40);
  v9 = RpcBindingCreateW(&Template, &Security, 0, a3);
  v10 = v9;
  v11 = v9 <= 0;
  if ( v9 || (v9 = RpcBindingBind(0, *a3, qword_1802A3950), v10 = v9, v11 = v9 <= 0, v9) )
  {
    if ( !v11 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 )
      operator delete(v8);
    if ( v12 )
      FreeTransientObjectSecurityDescriptor();
    return v10;
  }
  else
  {
    if ( v8 )
      operator delete(v8);
    if ( v12 )
      FreeTransientObjectSecurityDescriptor();
    return 0;
  }
}

```

## disassembly

```asm
0x1801ffa60  mov     [rsp-8+arg_0], rbx
0x1801ffa65  push    rbp
0x1801ffa66  push    rsi
0x1801ffa67  push    rdi
0x1801ffa68  lea     rbp, [rsp-47h]
0x1801ffa6d  sub     rsp, 0D0h
0x1801ffa74  mov     rax, cs:__security_cookie
0x1801ffa7b  xor     rax, rsp
0x1801ffa7e  mov     [rbp+57h+var_18], rax
0x1801ffa82  mov     rsi, r8
0x1801ffa85  mov     [rbp+57h+var_C0], 0
0x1801ffa8d  mov     rdi, rdx
0x1801ffa90  lea     r8, [rbp+57h+var_C0]
0x1801ffa94  lea     rdx, aUserdataservic; "UserDataServiceOneCore\\Server"
0x1801ffa9b  mov     ecx, 9
0x1801ffaa0  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1801ffaa6  mov     ebx, eax
0x1801ffaa8  test    eax, eax
0x1801ffaaa  jns     short loc_1801FFAC6
0x1801ffaac  bts     ebx, 1Ch
0x1801ffab0  mov     rcx, [rbp+57h+var_C0]
0x1801ffab4  test    rcx, rcx
0x1801ffab7  jz      short loc_1801FFABF
0x1801ffab9  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1801ffabf  mov     eax, ebx
0x1801ffac1  jmp     loc_1801FFC0E
0x1801ffac6  xorps   xmm0, xmm0
0x1801ffac9  xor     eax, eax
0x1801ffacb  xor     ebx, ebx
0x1801ffacd  mov     [rbp+57h+var_80], rax
0x1801ffad1  movups  [rbp+57h+var_B0], xmm0
0x1801ffad5  mov     [rbp+57h+Block], rbx
0x1801ffad9  movups  [rbp+57h+var_A0], xmm0
0x1801ffadd  movups  [rbp+57h+var_90], xmm0
0x1801ffae1  call    cs:__imp_IsCommsSystemService
0x1801ffae7  test    eax, eax
0x1801ffae9  jnz     short loc_1801FFB21
0x1801ffaeb  mov     rdx, rdi
0x1801ffaee  lea     rcx, [rbp+57h+Block]
0x1801ffaf2  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1801ffaf7  mov     ebx, eax
0x1801ffaf9  test    eax, eax
0x1801ffafb  jns     short loc_1801FFB0D
0x1801ffafd  mov     rcx, [rbp+57h+Block]; Block
0x1801ffb01  test    rcx, rcx
0x1801ffb04  jz      short loc_1801FFAB0
0x1801ffb06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801ffb0b  jmp     short loc_1801FFAB0
0x1801ffb0d  mov     rbx, [rbp+57h+Block]
0x1801ffb11  mov     dword ptr [rbp+57h+var_B0+4], 11h
0x1801ffb18  mov     rax, [rbx]
0x1801ffb1b  mov     qword ptr [rbp+57h+var_90], rax
0x1801ffb1f  jmp     short loc_1801FFB24
0x1801ffb21  mov     dword ptr [rbp+57h+var_B0+4], ebx
0x1801ffb24  mov     rax, [rbp+57h+var_C0]
0x1801ffb28  mov     ecx, 1
0x1801ffb2d  mov     [rbp+57h+var_80], rax
0x1801ffb31  xorps   xmm0, xmm0
0x1801ffb34  lea     rax, [rbp+57h+var_B0]
0x1801ffb38  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x1801ffb3b  mov     [rbp+57h+Security.SecurityQos], rax
0x1801ffb3f  mov     r9, rsi; Binding
0x1801ffb42  lea     edx, [rcx+2]
0x1801ffb45  mov     qword ptr [rbp+57h+Security.Version], rcx
0x1801ffb49  xor     eax, eax
0x1801ffb4b  mov     dword ptr [rbp+57h+var_B0+0Ch], edx
0x1801ffb4e  mov     qword ptr [rbp+57h+Template.ProtocolSequence], rdx
0x1801ffb52  xor     r8d, r8d; Options
0x1801ffb55  mov     qword ptr [rbp+57h+Template.Version], rcx
0x1801ffb59  lea     rdx, [rbp+57h+Security]; Security
0x1801ffb5d  lea     rcx, [rbp+57h+Template]; Template
0x1801ffb61  mov     dword ptr [rbp+57h+var_B0], 5
0x1801ffb68  mov     [rbp+57h+Security.ServerPrincName], 0
0x1801ffb70  mov     [rbp+57h+Security.AuthnLevel], 6
0x1801ffb77  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x1801ffb7e  mov     [rbp+57h+Security.AuthIdentity], 0
0x1801ffb86  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x1801ffb8b  mov     qword ptr [rbp+57h+Template.u1], 0
0x1801ffb93  mov     [rbp+57h+Template.ObjectUuid.Data1], 0
0x1801ffb9a  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x1801ffb9e  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x1801ffba1  call    cs:__imp_RpcBindingCreateW
0x1801ffba7  mov     edi, eax
0x1801ffba9  test    eax, eax
0x1801ffbab  jz      short loc_1801FFBD8
0x1801ffbad  jle     short loc_1801FFBB8
0x1801ffbaf  movzx   edi, ax
0x1801ffbb2  or      edi, 80070000h
0x1801ffbb8  test    rbx, rbx
0x1801ffbbb  jz      short loc_1801FFBC5
0x1801ffbbd  mov     rcx, rbx; Block
0x1801ffbc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801ffbc5  mov     rcx, [rbp+57h+var_C0]
0x1801ffbc9  test    rcx, rcx
0x1801ffbcc  jz      short loc_1801FFBD4
0x1801ffbce  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1801ffbd4  mov     eax, edi
0x1801ffbd6  jmp     short loc_1801FFC0E
0x1801ffbd8  mov     rdx, [rsi]; Binding
0x1801ffbdb  lea     r8, qword_1802A3950; IfSpec
0x1801ffbe2  xor     ecx, ecx; pAsync
0x1801ffbe4  call    cs:__imp_RpcBindingBind
0x1801ffbea  mov     edi, eax
0x1801ffbec  test    eax, eax
0x1801ffbee  jnz     short loc_1801FFBAD
0x1801ffbf0  test    rbx, rbx
0x1801ffbf3  jz      short loc_1801FFBFD
0x1801ffbf5  mov     rcx, rbx; Block
0x1801ffbf8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801ffbfd  mov     rcx, [rbp+57h+var_C0]
0x1801ffc01  test    rcx, rcx
0x1801ffc04  jz      short loc_1801FFC0C
0x1801ffc06  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1801ffc0c  xor     eax, eax
0x1801ffc0e  mov     rcx, [rbp+57h+var_18]
0x1801ffc12  xor     rcx, rsp; StackCookie
0x1801ffc15  call    __security_check_cookie
0x1801ffc1a  mov     rbx, [rsp+0E0h+arg_0]
0x1801ffc22  add     rsp, 0D0h
0x1801ffc29  pop     rdi
0x1801ffc2a  pop     rsi
0x1801ffc2b  pop     rbp
0x1801ffc2c  retn
```
