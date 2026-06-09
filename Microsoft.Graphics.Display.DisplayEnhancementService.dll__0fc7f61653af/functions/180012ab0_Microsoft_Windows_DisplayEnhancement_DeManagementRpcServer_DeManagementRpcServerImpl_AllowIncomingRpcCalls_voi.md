# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl::AllowIncomingRpcCalls(void)

- ea: `0x180012ab0`
- end: `0x180012c29`
- name: `?AllowIncomingRpcCalls@DeManagementRpcServerImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAXXZ`
- size: `377`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000fa0c`
- `0x180011704`
- `0x1800123fc`
- `0x180012498`
- `0x180012ab0`
- `0x180013720`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180012ae8`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180012ae8`
- `RPCRT4!RpcServerInqBindings` at `0x180012bc0`
- `RPCRT4!RpcServerInqBindings` at `0x180012bc0`
- `RPCRT4!RpcServerRegisterIf3` at `0x180012b8d`
- `RPCRT4!RpcServerRegisterIf3` at `0x180012b8d`
- `RPCRT4!RpcServerUseProtseqW` at `0x180012b27`
- `RPCRT4!RpcServerUseProtseqW` at `0x180012b27`
- `RPCRT4!RpcEpRegisterW` at `0x180012bf5`
- `RPCRT4!RpcEpRegisterW` at `0x180012bf5`

## string_xrefs

- `0x180012afa`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180012b39`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180012b9f`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180012bd2`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180012c07`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x180012adc`: `DefaultRpcAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl::AllowIncomingRpcCalls(
        Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl *this)
{
  int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-48h]
  void **p_SecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  __int64 v9; // [rsp+48h] [rbp-20h] BYREF
  char v10; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void *SecurityDescriptor; // [rsp+78h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  p_SecurityDescriptor = &SecurityDescriptor;
  v9 = 0;
  v10 = 1;
  v2 = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", &v9);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
      (const char *)(unsigned int)v2,
      v7);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_SecurityDescriptor);
  v3 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
      (const char *)v3,
      v7);
  (***((void (__fastcall ****)(_QWORD))this + 16))(*((_QWORD *)this + 16));
  v4 = RpcServerRegisterIf3(qword_1800F6A60, 0, 0, 41);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
      (const char *)v4,
      0x4D2u);
  wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(
    (char *)this + 120,
    0);
  v5 = RpcServerInqBindings((RPC_BINDING_VECTOR **)this + 15);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
      (const char *)v5,
      0x4D2u);
  v6 = RpcEpRegisterW(qword_1800F6A60, *((RPC_BINDING_VECTOR **)this + 15), 0, 0);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
      (const char *)v6,
      0x4D2u);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
}

```

## disassembly

```asm
0x180012ab0  mov     r11, rsp
0x180012ab3  push    rbx
0x180012ab4  sub     rsp, 60h
0x180012ab8  mov     rbx, rcx
0x180012abb  mov     qword ptr [r11+10h], 0
0x180012ac3  lea     rax, [r11+10h]
0x180012ac7  mov     [r11-28h], rax
0x180012acb  mov     qword ptr [r11-20h], 0
0x180012ad3  mov     [rsp+68h+var_18], 1
0x180012ad8  lea     r8, [r11-20h]
0x180012adc  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x180012ae3  mov     ecx, 8
0x180012ae8  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180012aee  mov     rcx, [rsp+68h]; this
0x180012af3  test    eax, eax
0x180012af5  jns     short loc_180012B0C
0x180012af7  mov     r9d, eax; char *
0x180012afa  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180012b01  mov     edx, 73h ; 's'; void *
0x180012b06  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180012b0c  lea     rcx, [rsp+68h+var_28]
0x180012b11  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180012b16  mov     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180012b1b  mov     edx, 0Ah; MaxCalls
0x180012b20  lea     rcx, Protseq; "ncalrpc"
0x180012b27  call    cs:__imp_RpcServerUseProtseqW
0x180012b2d  mov     rcx, [rsp+68h]; this
0x180012b32  test    eax, eax
0x180012b34  jz      short loc_180012B4B
0x180012b36  mov     r9d, eax; char *
0x180012b39  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180012b40  mov     edx, 79h ; 'y'; void *
0x180012b45  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012b4b  mov     rcx, [rbx+80h]
0x180012b52  mov     rax, [rcx]
0x180012b55  mov     rax, [rax]
0x180012b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b5d  mov     [rsp+68h+var_30], rax
0x180012b62  mov     [rsp+68h+var_38], 0
0x180012b6b  mov     [rsp+68h+var_40], 0
0x180012b73  mov     [rsp+68h+var_48], 4D2h; unsigned int
0x180012b7b  mov     r9d, 29h ; ')'
0x180012b81  xor     r8d, r8d
0x180012b84  xor     edx, edx
0x180012b86  lea     rcx, qword_1800F6A60
0x180012b8d  call    cs:__imp_RpcServerRegisterIf3
0x180012b93  mov     rcx, [rsp+68h]; this
0x180012b98  test    eax, eax
0x180012b9a  jz      short loc_180012BB1
0x180012b9c  mov     r9d, eax; char *
0x180012b9f  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180012ba6  mov     edx, 84h; void *
0x180012bab  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012bb1  xor     edx, edx
0x180012bb3  lea     rcx, [rbx+78h]
0x180012bb7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RPC_BINDING_VECTOR@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(_RPC_BINDING_VECTOR *)
0x180012bbc  lea     rcx, [rbx+78h]; BindingVector
0x180012bc0  call    cs:__imp_RpcServerInqBindings
0x180012bc6  mov     rcx, [rsp+68h]; this
0x180012bcb  test    eax, eax
0x180012bcd  jz      short loc_180012BE4
0x180012bcf  mov     r9d, eax; char *
0x180012bd2  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180012bd9  mov     edx, 88h; void *
0x180012bde  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012be4  xor     r9d, r9d; Annotation
0x180012be7  xor     r8d, r8d; UuidVector
0x180012bea  mov     rdx, [rbx+78h]; BindingVector
0x180012bee  lea     rcx, qword_1800F6A60; IfSpec
0x180012bf5  call    cs:__imp_RpcEpRegisterW
0x180012bfb  mov     rcx, [rsp+68h]; this
0x180012c00  test    eax, eax
0x180012c02  jz      short loc_180012C19
0x180012c04  mov     r9d, eax; char *
0x180012c07  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180012c0e  mov     edx, 8Fh; void *
0x180012c13  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012c19  lea     rcx, [rsp+68h+SecurityDescriptor]
0x180012c1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012c23  add     rsp, 60h
0x180012c27  pop     rbx
0x180012c28  retn
```
