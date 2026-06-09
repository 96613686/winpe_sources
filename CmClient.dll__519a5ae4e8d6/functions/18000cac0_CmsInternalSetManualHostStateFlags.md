# CmsInternalSetManualHostStateFlags

- ea: `0x18000cac0`
- end: `0x18000cb96`
- name: `CmsInternalSetManualHostStateFlags`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000ba24`
- `0x18000cac0`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000cb1d`
- `RPCRT4!RpcBindingFree` at `0x18000cb67`
- `RPCRT4!RpcBindingFree` at `0x18000cb7e`
- `RPCRT4!RpcBindingFree` at `0x18000cb1d`
- `RPCRT4!RpcBindingFree` at `0x18000cb67`
- `RPCRT4!RpcBindingFree` at `0x18000cb7e`

## string_xrefs

- `0x18000caf8`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000cb46`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetManualHostStateFlags(int a1)
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
    v6 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_MANUAL_HOST_STATE_FLAGS),void *,enum _CMS_MANUAL_HOST_STATE_FLAGS &>(
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
        (void *)0xDC,
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
      (void *)0xD7,
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
0x18000cac0  mov     [rsp-8+arg_10], rbx
0x18000cac5  mov     [rsp-8+arg_18], rdi
0x18000caca  mov     [rsp-8+arg_0], ecx
0x18000cace  push    rbp; int
0x18000cacf  mov     rbp, rsp
0x18000cad2  sub     rsp, 20h
0x18000cad6  lea     rdx, [rbp+Binding]
0x18000cada  mov     [rbp+Binding], 0
0x18000cae2  lea     rcx, qword_180013DC0; IfSpec
0x18000cae9  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000caee  mov     ebx, eax
0x18000caf0  test    eax, eax
0x18000caf2  jns     short loc_18000CB27
0x18000caf4  mov     rcx, [rbp+8]; this
0x18000caf8  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000caff  mov     r9d, eax; char *
0x18000cb02  mov     edx, 0D7h; void *
0x18000cb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb0c  mov     rcx, [rbp+Binding]
0x18000cb10  test    rcx, rcx
0x18000cb13  jz      short loc_18000CB23
0x18000cb15  mov     [rbp+Binding], rcx
0x18000cb19  lea     rcx, [rbp+Binding]; Binding
0x18000cb1d  call    cs:__imp_RpcBindingFree
0x18000cb23  mov     eax, ebx
0x18000cb25  jmp     short loc_18000CB86
0x18000cb27  mov     rbx, [rbp+Binding]
0x18000cb2b  lea     r8, [rbp+arg_0]
0x18000cb2f  lea     rdx, [rbp+Binding]
0x18000cb33  mov     [rbp+Binding], rbx
0x18000cb37  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_MANUAL_HOST_STATE_FLAGS@@@ZPEAXAEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_MANUAL_HOST_STATE_FLAGS@@@Z$$QEAPEAXAEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS),void *,_CMS_MANUAL_HOST_STATE_FLAGS &>(long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS),void * &&,_CMS_MANUAL_HOST_STATE_FLAGS &)
0x18000cb3c  mov     edi, eax
0x18000cb3e  test    eax, eax
0x18000cb40  jns     short loc_18000CB71
0x18000cb42  mov     rcx, [rbp+8]; this
0x18000cb46  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000cb4d  mov     r9d, eax; char *
0x18000cb50  mov     edx, 0DCh; void *
0x18000cb55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb5a  test    rbx, rbx
0x18000cb5d  jz      short loc_18000CB6D
0x18000cb5f  lea     rcx, [rbp+Binding]; Binding
0x18000cb63  mov     [rbp+Binding], rbx
0x18000cb67  call    cs:__imp_RpcBindingFree
0x18000cb6d  mov     eax, edi
0x18000cb6f  jmp     short loc_18000CB86
0x18000cb71  test    rbx, rbx
0x18000cb74  jz      short loc_18000CB84
0x18000cb76  lea     rcx, [rbp+Binding]; Binding
0x18000cb7a  mov     [rbp+Binding], rbx
0x18000cb7e  call    cs:__imp_RpcBindingFree
0x18000cb84  xor     eax, eax
0x18000cb86  mov     rbx, [rsp+20h+arg_10]
0x18000cb8b  mov     rdi, [rsp+20h+arg_18]
0x18000cb90  add     rsp, 20h
0x18000cb94  pop     rbp
0x18000cb95  retn
```
