# CmsInternalSetGlobalDebugFlags

- ea: `0x18000c9e0`
- end: `0x18000cab6`
- name: `CmsInternalSetGlobalDebugFlags`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b9bc`
- `0x18000c9e0`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000ca3d`
- `RPCRT4!RpcBindingFree` at `0x18000ca87`
- `RPCRT4!RpcBindingFree` at `0x18000ca9e`
- `RPCRT4!RpcBindingFree` at `0x18000ca3d`
- `RPCRT4!RpcBindingFree` at `0x18000ca87`
- `RPCRT4!RpcBindingFree` at `0x18000ca9e`

## string_xrefs

- `0x18000ca18`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000ca66`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetGlobalDebugFlags(int a1)
{
  int v1; // eax
  __int64 v2; // rcx
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  int v10; // [rsp+30h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp+18h] BYREF

  v10 = a1;
  Binding = 0;
  v1 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v3 = v1;
  if ( v1 >= 0 )
  {
    v5 = Binding;
    v6 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_GLOBAL_DEBUG_FLAGS),void *,enum _CMS_GLOBAL_DEBUG_FLAGS &>(
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
        (void *)0xB6,
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
      (void *)0xB1,
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
0x18000c9e0  mov     [rsp-8+arg_10], rbx
0x18000c9e5  mov     [rsp-8+arg_18], rdi
0x18000c9ea  mov     [rsp-8+arg_0], ecx
0x18000c9ee  push    rbp; int
0x18000c9ef  mov     rbp, rsp
0x18000c9f2  sub     rsp, 20h
0x18000c9f6  lea     rdx, [rbp+Binding]
0x18000c9fa  mov     [rbp+Binding], 0
0x18000ca02  lea     rcx, qword_180013DC0; IfSpec
0x18000ca09  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000ca0e  mov     ebx, eax
0x18000ca10  test    eax, eax
0x18000ca12  jns     short loc_18000CA47
0x18000ca14  mov     rcx, [rbp+8]; this
0x18000ca18  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ca1f  mov     r9d, eax; char *
0x18000ca22  mov     edx, 0B1h; void *
0x18000ca27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca2c  mov     rcx, [rbp+Binding]
0x18000ca30  test    rcx, rcx
0x18000ca33  jz      short loc_18000CA43
0x18000ca35  mov     [rbp+Binding], rcx
0x18000ca39  lea     rcx, [rbp+Binding]; Binding
0x18000ca3d  call    cs:__imp_RpcBindingFree
0x18000ca43  mov     eax, ebx
0x18000ca45  jmp     short loc_18000CAA6
0x18000ca47  mov     rbx, [rbp+Binding]
0x18000ca4b  lea     r8, [rbp+arg_0]
0x18000ca4f  lea     rdx, [rbp+Binding]
0x18000ca53  mov     [rbp+Binding], rbx
0x18000ca57  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_GLOBAL_DEBUG_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_GLOBAL_DEBUG_FLAGS@@@Z$$QEAPEAXAEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS),void *,_CMS_GLOBAL_DEBUG_FLAGS &>(long (*)(void *,_CMS_GLOBAL_DEBUG_FLAGS),void * &&,_CMS_GLOBAL_DEBUG_FLAGS &)
0x18000ca5c  mov     edi, eax
0x18000ca5e  test    eax, eax
0x18000ca60  jns     short loc_18000CA91
0x18000ca62  mov     rcx, [rbp+8]; this
0x18000ca66  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ca6d  mov     r9d, eax; char *
0x18000ca70  mov     edx, 0B6h; void *
0x18000ca75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca7a  test    rbx, rbx
0x18000ca7d  jz      short loc_18000CA8D
0x18000ca7f  lea     rcx, [rbp+Binding]; Binding
0x18000ca83  mov     [rbp+Binding], rbx
0x18000ca87  call    cs:__imp_RpcBindingFree
0x18000ca8d  mov     eax, edi
0x18000ca8f  jmp     short loc_18000CAA6
0x18000ca91  test    rbx, rbx
0x18000ca94  jz      short loc_18000CAA4
0x18000ca96  lea     rcx, [rbp+Binding]; Binding
0x18000ca9a  mov     [rbp+Binding], rbx
0x18000ca9e  call    cs:__imp_RpcBindingFree
0x18000caa4  xor     eax, eax
0x18000caa6  mov     rbx, [rsp+20h+arg_10]
0x18000caab  mov     rdi, [rsp+20h+arg_18]
0x18000cab0  add     rsp, 20h
0x18000cab4  pop     rbp
0x18000cab5  retn
```
