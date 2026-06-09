# Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::StopIncomingRpcCalls(void)

- ea: `0x180069790`
- end: `0x18006982e`
- name: `?StopIncomingRpcCalls@DeoRpcServerImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAXXZ`
- size: `158`
- prototype: `void(Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180068854`

## callees

- `0x180013138`
- `0x180013720`
- `0x180069790`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800697b1`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800697b1`
- `RPCRT4!RpcEpUnregister` at `0x1800697ee`
- `RPCRT4!RpcEpUnregister` at `0x1800697ee`

## string_xrefs

- `0x1800697cc`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`
- `0x180069809`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserver.cpp`

## pseudocode

```c
void __fastcall Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl::StopIncomingRpcCalls(
        Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerImpl *this)
{
  RPC_BINDING_VECTOR **v1; // rbx
  int v2; // eax
  bool v3; // sf
  int v4; // eax
  bool v5; // sf
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (RPC_BINDING_VECTOR **)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
  {
    v2 = RpcServerUnregisterIfEx(qword_1800F7E50, 0, 1);
    v3 = v2 < 0;
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80010000;
      v3 = v2 < 0;
    }
    if ( v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserver.cpp",
        (const char *)(unsigned int)v2,
        v6);
    v4 = RpcEpUnregister(qword_1800F7E50, *v1, 0);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80010000;
      v5 = v4 < 0;
    }
    if ( v5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserver.cpp",
        (const char *)(unsigned int)v4,
        v6);
    wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(
      v1,
      0);
  }
}

```

## disassembly

```asm
0x180069790  push    rbx; int
0x180069792  sub     rsp, 20h
0x180069796  lea     rbx, [rcx+30h]
0x18006979a  cmp     qword ptr [rbx], 0
0x18006979e  jz      loc_180069828
0x1800697a4  xor     edx, edx; MgrTypeUuid
0x1800697a6  lea     rcx, qword_1800F7E50; IfSpec
0x1800697ad  lea     r8d, [rdx+1]; RundownContextHandles
0x1800697b1  call    cs:__imp_RpcServerUnregisterIfEx
0x1800697b7  test    eax, eax
0x1800697b9  jle     short loc_1800697C5
0x1800697bb  movzx   eax, ax
0x1800697be  or      eax, 80010000h
0x1800697c3  test    eax, eax
0x1800697c5  jns     short loc_1800697E1
0x1800697c7  mov     rcx, [rsp+28h]; this
0x1800697cc  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800697d3  mov     r9d, eax; char *
0x1800697d6  mov     edx, 6Fh ; 'o'; void *
0x1800697db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800697e1  mov     rdx, [rbx]; BindingVector
0x1800697e4  lea     rcx, qword_1800F7E50; IfSpec
0x1800697eb  xor     r8d, r8d; UuidVector
0x1800697ee  call    cs:__imp_RpcEpUnregister
0x1800697f4  test    eax, eax
0x1800697f6  jle     short loc_180069802
0x1800697f8  movzx   eax, ax
0x1800697fb  or      eax, 80010000h
0x180069800  test    eax, eax
0x180069802  jns     short loc_18006981E
0x180069804  mov     rcx, [rsp+28h]; this
0x180069809  lea     r8, aOnecoreuapDriv_16; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180069810  mov     r9d, eax; char *
0x180069813  mov     edx, 75h ; 'u'; void *
0x180069818  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006981e  xor     edx, edx
0x180069820  mov     rcx, rbx
0x180069823  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RPC_BINDING_VECTOR@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(_RPC_BINDING_VECTOR *)
0x180069828  add     rsp, 20h
0x18006982c  pop     rbx
0x18006982d  retn
```
