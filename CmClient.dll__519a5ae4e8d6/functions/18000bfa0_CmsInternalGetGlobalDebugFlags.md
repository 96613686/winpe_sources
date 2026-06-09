# CmsInternalGetGlobalDebugFlags

- ea: `0x18000bfa0`
- end: `0x18000c077`
- name: `CmsInternalGetGlobalDebugFlags`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b720`
- `0x18000bfa0`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000bffe`
- `RPCRT4!RpcBindingFree` at `0x18000c048`
- `RPCRT4!RpcBindingFree` at `0x18000c05f`
- `RPCRT4!RpcBindingFree` at `0x18000bffe`
- `RPCRT4!RpcBindingFree` at `0x18000c048`
- `RPCRT4!RpcBindingFree` at `0x18000c05f`

## string_xrefs

- `0x18000bfd9`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c027`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetGlobalDebugFlags(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rcx
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  __int64 v10; // [rsp+30h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp+18h] BYREF

  v10 = a1;
  Binding = 0;
  v1 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v3 = v1;
  if ( v1 >= 0 )
  {
    v5 = Binding;
    v6 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_GLOBAL_DEBUG_FLAGS *),void *,enum _CMS_GLOBAL_DEBUG_FLAGS * &>(
           v2,
           &Binding,
           &v10);
    v7 = v6;
    if ( v6 >= 0 )
    {
      if ( v5 )
      {
        Binding = v5;
        RpcBindingFree(&Binding);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
        (const char *)(unsigned int)v6,
        savedregs);
      if ( v5 )
      {
        Binding = v5;
        RpcBindingFree(&Binding);
      }
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v1,
      savedregs);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v3;
  }
}

```

## disassembly

```asm
0x18000bfa0  mov     [rsp-8+arg_10], rbx
0x18000bfa5  mov     [rsp-8+arg_18], rdi
0x18000bfaa  mov     [rsp-8+arg_0], rcx
0x18000bfaf  push    rbp; int
0x18000bfb0  mov     rbp, rsp
0x18000bfb3  sub     rsp, 20h
0x18000bfb7  lea     rdx, [rbp+Binding]
0x18000bfbb  mov     [rbp+Binding], 0
0x18000bfc3  lea     rcx, qword_180013DC0; IfSpec
0x18000bfca  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000bfcf  mov     ebx, eax
0x18000bfd1  test    eax, eax
0x18000bfd3  jns     short loc_18000C008
0x18000bfd5  mov     rcx, [rbp+8]; this
0x18000bfd9  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bfe0  mov     r9d, eax; char *
0x18000bfe3  mov     edx, 0C4h; void *
0x18000bfe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bfed  mov     rcx, [rbp+Binding]
0x18000bff1  test    rcx, rcx
0x18000bff4  jz      short loc_18000C004
0x18000bff6  mov     [rbp+Binding], rcx
0x18000bffa  lea     rcx, [rbp+Binding]; Binding
0x18000bffe  call    cs:__imp_RpcBindingFree
0x18000c004  mov     eax, ebx
0x18000c006  jmp     short loc_18000C067
0x18000c008  mov     rbx, [rbp+Binding]
0x18000c00c  lea     r8, [rbp+arg_0]
0x18000c010  lea     rdx, [rbp+Binding]
0x18000c014  mov     [rbp+Binding], rbx
0x18000c018  call    ??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_GLOBAL_DEBUG_FLAGS@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_GLOBAL_DEBUG_FLAGS@@@Z$$QEAPEAXAEAPEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS *),void *,_CMS_GLOBAL_DEBUG_FLAGS * &>(long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS *),void * &&,_CMS_GLOBAL_DEBUG_FLAGS * &)
0x18000c01d  mov     edi, eax
0x18000c01f  test    eax, eax
0x18000c021  jns     short loc_18000C052
0x18000c023  mov     rcx, [rbp+8]; this
0x18000c027  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c02e  mov     r9d, eax; char *
0x18000c031  mov     edx, 0C9h; void *
0x18000c036  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c03b  test    rbx, rbx
0x18000c03e  jz      short loc_18000C04E
0x18000c040  lea     rcx, [rbp+Binding]; Binding
0x18000c044  mov     [rbp+Binding], rbx
0x18000c048  call    cs:__imp_RpcBindingFree
0x18000c04e  mov     eax, edi
0x18000c050  jmp     short loc_18000C067
0x18000c052  test    rbx, rbx
0x18000c055  jz      short loc_18000C065
0x18000c057  lea     rcx, [rbp+Binding]; Binding
0x18000c05b  mov     [rbp+Binding], rbx
0x18000c05f  call    cs:__imp_RpcBindingFree
0x18000c065  xor     eax, eax
0x18000c067  mov     rbx, [rsp+20h+arg_10]
0x18000c06c  mov     rdi, [rsp+20h+arg_18]
0x18000c071  add     rsp, 20h
0x18000c075  pop     rbp
0x18000c076  retn
```
