# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl::StopIncomingRpcCalls(void)

- ea: `0x1800130b0`
- end: `0x180013132`
- name: `?StopIncomingRpcCalls@DeManagementRpcServerImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAXXZ`
- size: `130`
- prototype: `void(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fa0c`
- `0x1800130b0`
- `0x180013720`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800130cd`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800130cd`
- `RPCRT4!RpcEpUnregister` at `0x1800130fe`
- `RPCRT4!RpcEpUnregister` at `0x1800130fe`

## string_xrefs

- `0x1800130dc`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`
- `0x18001310d`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserver.cpp`

## pseudocode

```c
void __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl::StopIncomingRpcCalls(
        Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerImpl *this)
{
  RPC_BINDING_VECTOR **v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (RPC_BINDING_VECTOR **)((char *)this + 120);
  if ( *((_QWORD *)this + 15) )
  {
    v2 = RpcServerUnregisterIfEx(qword_1800F6A60, 0, 1);
    if ( v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        (const char *)v2,
        v4);
    v3 = RpcEpUnregister(qword_1800F6A60, *v1, 0);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementrpcserver.cpp",
        (const char *)v3,
        v4);
    wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(
      v1,
      0);
  }
}

```

## disassembly

```asm
0x1800130b0  push    rbx; unsigned int
0x1800130b2  sub     rsp, 20h
0x1800130b6  lea     rbx, [rcx+78h]
0x1800130ba  cmp     qword ptr [rbx], 0
0x1800130be  jz      short loc_18001312C
0x1800130c0  xor     edx, edx; MgrTypeUuid
0x1800130c2  lea     rcx, qword_1800F6A60; IfSpec
0x1800130c9  lea     r8d, [rdx+1]; RundownContextHandles
0x1800130cd  call    cs:__imp_RpcServerUnregisterIfEx
0x1800130d3  test    eax, eax
0x1800130d5  jz      short loc_1800130F1
0x1800130d7  mov     rcx, [rsp+28h]; this
0x1800130dc  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800130e3  mov     r9d, eax; char *
0x1800130e6  mov     edx, 9Ah; void *
0x1800130eb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800130f1  mov     rdx, [rbx]; BindingVector
0x1800130f4  lea     rcx, qword_1800F6A60; IfSpec
0x1800130fb  xor     r8d, r8d; UuidVector
0x1800130fe  call    cs:__imp_RpcEpUnregister
0x180013104  test    eax, eax
0x180013106  jz      short loc_180013122
0x180013108  mov     rcx, [rsp+28h]; this
0x18001310d  lea     r8, aOnecoreuapDriv_31; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180013114  mov     r9d, eax; char *
0x180013117  mov     edx, 0A0h; void *
0x18001311c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180013122  xor     edx, edx
0x180013124  mov     rcx, rbx
0x180013127  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RPC_BINDING_VECTOR@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(_RPC_BINDING_VECTOR *)
0x18001312c  add     rsp, 20h
0x180013130  pop     rbx
0x180013131  retn
```
