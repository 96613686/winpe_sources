# Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::AllowIncomingRpcCalls(void)

- ea: `0x180068ba0`
- end: `0x180068dcc`
- name: `?AllowIncomingRpcCalls@DeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAXXZ`
- size: `556`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f9f0`
- `0x1800123fc`
- `0x180012498`
- `0x180013138`
- `0x18001c7f0`
- `0x180068830`
- `0x180068ba0`

## import_xrefs

- `RPCRT4!RpcServerInqBindings` at `0x180068cc1`
- `RPCRT4!RpcServerInqBindings` at `0x180068cc1`
- `RPCRT4!RpcServerRegisterIf3` at `0x180068c3a`
- `RPCRT4!RpcServerRegisterIf3` at `0x180068c3a`
- `RPCRT4!RpcServerUseProtseqW` at `0x180068c81`
- `RPCRT4!RpcServerUseProtseqW` at `0x180068c81`
- `RPCRT4!RpcEpRegisterW` at `0x180068d07`
- `RPCRT4!RpcEpRegisterW` at `0x180068d07`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068be7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068be7`

## string_xrefs

- `0x180068bf1`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x180068c5b`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x180068c9c`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x180068cdc`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x180068d22`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::AllowIncomingRpcCalls(
        LPCWSTR *this)
{
  char v2; // bl
  const char *v3; // r9
  signed int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  void **v10; // [rsp+50h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-18h] BYREF
  char v12; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  void *v14; // [rsp+A0h] [rbp+30h] BYREF

  v14 = 0;
  v10 = &v14;
  SecurityDescriptor = 0;
  v2 = 1;
  v12 = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(this[5], 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      v3);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v10);
  v4 = RpcServerRegisterIf3(qword_1800F7E50, 0, 0, 33);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80010000;
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)(unsigned int)v4,
      1234);
  v5 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, v14);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80010000;
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)(unsigned int)v5,
      1234);
  v10 = (void **)(this + 6);
  SecurityDescriptor = 0;
  v12 = 1;
  v6 = RpcServerInqBindings((RPC_BINDING_VECTOR **)&SecurityDescriptor);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80010000;
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)(unsigned int)v6,
      1234);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>>(&v10);
  v7 = RpcEpRegisterW(qword_1800F7E50, (RPC_BINDING_VECTOR *)this[6], 0, 0);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80010000;
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserver.cpp",
      (const char *)(unsigned int)v7,
      1234);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
    || (LOBYTE(v8) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v8) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 24) )
    v2 = 0;
  if ( (_BYTE)v8 || v2 )
  {
    LOBYTE(v9) = v2;
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      10,
      10,
      &WPP_67c0ebe1d1de3334192790ee1d4cb078_Traceguids);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
}

```

## disassembly

```asm
0x180068ba0  mov     [rsp-28h+arg_8], rbx
0x180068ba5  mov     [rsp-28h+arg_10], rsi
0x180068baa  push    rbp
0x180068bab  push    rdi
0x180068bac  push    r12
0x180068bae  push    r14
0x180068bb0  push    r15
0x180068bb2  mov     rbp, rsp
0x180068bb5  sub     rsp, 70h
0x180068bb9  mov     rsi, rcx
0x180068bbc  xor     r14d, r14d
0x180068bbf  mov     [rbp+arg_0], r14
0x180068bc3  lea     rax, [rbp+arg_0]
0x180068bc7  mov     [rbp+var_20], rax
0x180068bcb  mov     [rbp+SecurityDescriptor], r14
0x180068bcf  lea     ebx, [r14+1]
0x180068bd3  mov     [rbp+var_10], bl
0x180068bd6  mov     rdi, [rbp+28h]
0x180068bda  xor     r9d, r9d; SecurityDescriptorSize
0x180068bdd  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180068be1  mov     edx, ebx; StringSDRevision
0x180068be3  mov     rcx, [rcx+28h]; StringSecurityDescriptor
0x180068be7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180068bed  test    eax, eax
0x180068bef  jnz     short loc_180068C04
0x180068bf1  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180068bf8  lea     edx, [rbx+46h]; void *
0x180068bfb  mov     rcx, rdi; this
0x180068bfe  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180068c04  lea     rcx, [rbp+var_20]
0x180068c08  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180068c0d  mov     rax, [rbp+arg_0]
0x180068c11  mov     [rsp+70h+MessageGuid], rax
0x180068c16  mov     qword ptr [rsp+70h+var_40], r14
0x180068c1b  mov     [rsp+70h+var_48], r14d
0x180068c20  mov     dword ptr [rsp+70h+var_50], 4D2h; int
0x180068c28  mov     r9d, 21h ; '!'
0x180068c2e  xor     r8d, r8d
0x180068c31  xor     edx, edx
0x180068c33  lea     rcx, qword_1800F7E50
0x180068c3a  call    cs:__imp_RpcServerRegisterIf3
0x180068c40  mov     r15d, 80010000h
0x180068c46  test    eax, eax
0x180068c48  jle     short loc_180068C50
0x180068c4a  movzx   eax, ax
0x180068c4d  or      eax, r15d
0x180068c50  mov     rcx, [rbp+28h]; this
0x180068c54  test    eax, eax
0x180068c56  jns     short loc_180068C6D
0x180068c58  mov     r9d, eax; char *
0x180068c5b  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180068c62  mov     edx, 52h ; 'R'; void *
0x180068c67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068c6d  mov     r8, [rbp+arg_0]; SecurityDescriptor
0x180068c71  mov     r12d, 0Ah
0x180068c77  mov     edx, r12d; MaxCalls
0x180068c7a  lea     rcx, Protseq; "ncalrpc"
0x180068c81  call    cs:__imp_RpcServerUseProtseqW
0x180068c87  test    eax, eax
0x180068c89  jle     short loc_180068C91
0x180068c8b  movzx   eax, ax
0x180068c8e  or      eax, r15d
0x180068c91  mov     rcx, [rbp+28h]; this
0x180068c95  test    eax, eax
0x180068c97  jns     short loc_180068CAE
0x180068c99  mov     r9d, eax; char *
0x180068c9c  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180068ca3  mov     edx, 58h ; 'X'; void *
0x180068ca8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068cae  lea     rdi, [rsi+30h]
0x180068cb2  mov     [rbp+var_20], rdi
0x180068cb6  mov     [rbp+SecurityDescriptor], r14
0x180068cba  mov     [rbp+var_10], bl
0x180068cbd  lea     rcx, [rbp+SecurityDescriptor]; BindingVector
0x180068cc1  call    cs:__imp_RpcServerInqBindings
0x180068cc7  test    eax, eax
0x180068cc9  jle     short loc_180068CD1
0x180068ccb  movzx   eax, ax
0x180068cce  or      eax, r15d
0x180068cd1  mov     rcx, [rbp+28h]; this
0x180068cd5  test    eax, eax
0x180068cd7  jns     short loc_180068CEE
0x180068cd9  mov     r9d, eax; char *
0x180068cdc  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180068ce3  mov     edx, 5Bh ; '['; void *
0x180068ce8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068cee  lea     rcx, [rbp+var_20]
0x180068cf2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>>(void)
0x180068cf7  xor     r9d, r9d; Annotation
0x180068cfa  xor     r8d, r8d; UuidVector
0x180068cfd  mov     rdx, [rdi]; BindingVector
0x180068d00  lea     rcx, qword_1800F7E50; IfSpec
0x180068d07  call    cs:__imp_RpcEpRegisterW
0x180068d0d  test    eax, eax
0x180068d0f  jle     short loc_180068D17
0x180068d11  movzx   eax, ax
0x180068d14  or      eax, r15d
0x180068d17  mov     rcx, [rbp+28h]; this
0x180068d1b  test    eax, eax
0x180068d1d  jns     short loc_180068D34
0x180068d1f  mov     r9d, eax; char *
0x180068d22  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180068d29  mov     edx, 62h ; 'b'; void *
0x180068d2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068d34  lea     rax, WPP_GLOBAL_Control
0x180068d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180068d42  cmp     rcx, rax
0x180068d45  jz      short loc_180068D58
0x180068d47  test    dword ptr [rcx+1Ch], 200h
0x180068d4e  jz      short loc_180068D58
0x180068d50  cmp     byte ptr [rcx+19h], 5
0x180068d54  mov     dl, bl
0x180068d56  jnb     short loc_180068D5B
0x180068d58  mov     dl, r14b; int
0x180068d5b  lea     rax, WPP_RECORDER_INITIALIZED
0x180068d62  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180068d69  jz      short loc_180068D72
0x180068d6b  cmp     [rcx+30h], r14w
0x180068d70  jnz     short loc_180068D75
0x180068d72  mov     bl, r14b
0x180068d75  test    dl, dl
0x180068d77  jnz     short loc_180068D7D
0x180068d79  test    bl, bl
0x180068d7b  jz      short loc_180068DAA
0x180068d7d  lea     rax, WPP_67c0ebe1d1de3334192790ee1d4cb078_Traceguids
0x180068d84  mov     [rsp+70h+MessageGuid], rax; MessageGuid
0x180068d89  mov     [rsp+70h+var_40], r12w; __int16
0x180068d8f  mov     [rsp+70h+var_48], r12d; int
0x180068d94  mov     [rsp+70h+var_50], 5; char
0x180068d99  mov     r9, [rcx+28h]; int
0x180068d9d  mov     r8b, bl; int
0x180068da0  mov     rcx, [rcx+10h]; int
0x180068da4  call    WPP_RECORDER_AND_TRACE_SF_s
0x180068da9  nop
0x180068daa  lea     rcx, [rbp+arg_0]
0x180068dae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180068db3  lea     r11, [rsp+70h+var_s0]
0x180068db8  mov     rbx, [r11+38h]
0x180068dbc  mov     rsi, [r11+40h]
0x180068dc0  mov     rsp, r11
0x180068dc3  pop     r15
0x180068dc5  pop     r14
0x180068dc7  pop     r12
0x180068dc9  pop     rdi
0x180068dca  pop     rbp
0x180068dcb  retn
```
