# CmsInternalSetDebugConfiguration

- ea: `0x18000c850`
- end: `0x18000c9d0`
- name: `CmsInternalSetDebugConfiguration`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000c850`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000c8d8`
- `RPCRT4!RpcBindingFree` at `0x18000c92a`
- `RPCRT4!RpcBindingFree` at `0x18000c944`
- `RPCRT4!RpcBindingFree` at `0x18000c8d8`
- `RPCRT4!RpcBindingFree` at `0x18000c92a`
- `RPCRT4!RpcBindingFree` at `0x18000c944`

## string_xrefs

- `0x18000c8af`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c909`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c9a8`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetDebugConfiguration(__int64 a1, __int64 a2)
{
  int v2; // eax
  int v3; // ebx
  RPC_BINDING_HANDLE v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  __int64 v8; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+10h] BYREF
  __int64 v12; // [rsp+38h] [rbp+18h] BYREF

  v12 = a2;
  if ( !a1 )
    return 2147942450LL;
  if ( *(_DWORD *)a1 == 1 )
  {
    Binding = **(RPC_BINDING_HANDLE **)(a1 + 8);
    v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
           CmsRpcClt_SetDebugConfigurationForStorage,
           &Binding,
           &v12);
    if ( v3 < 0 )
    {
      v8 = 545;
      goto LABEL_19;
    }
    return 0;
  }
  if ( *(_DWORD *)a1 == 2 )
  {
    Binding = **(RPC_BINDING_HANDLE **)(a1 + 8);
    v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
           CmsRpcClt_SetDebugConfigurationForLayer,
           &Binding,
           &v12);
    if ( v3 < 0 )
    {
      v8 = 557;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
        (const char *)(unsigned int)v3,
        savedregs);
      return (unsigned int)v3;
    }
    return 0;
  }
  if ( *(_DWORD *)a1 != 3 )
    return 2147942450LL;
  Binding = 0;
  v2 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v2,
      savedregs);
    if ( Binding )
      RpcBindingFree(&Binding);
    return (unsigned int)v3;
  }
  v4 = Binding;
  v5 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         CmsRpcClt_SetDebugConfigurationGlobal,
         &Binding,
         &v12);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( v4 )
    {
      Binding = v4;
      RpcBindingFree(&Binding);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23C,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (const char *)(unsigned int)v5,
    savedregs);
  if ( v4 )
  {
    Binding = v4;
    RpcBindingFree(&Binding);
  }
  return v6;
}

```

## disassembly

```asm
0x18000c850  mov     [rsp-8+arg_10], rbx
0x18000c855  mov     [rsp-8+arg_18], rdi
0x18000c85a  mov     [rsp-8+arg_8], rdx
0x18000c85f  push    rbp; int
0x18000c860  mov     rbp, rsp
0x18000c863  sub     rsp, 20h
0x18000c867  test    rcx, rcx
0x18000c86a  jz      loc_18000C9BB
0x18000c870  mov     edx, [rcx]
0x18000c872  sub     edx, 1
0x18000c875  jz      loc_18000C97A
0x18000c87b  sub     edx, 1
0x18000c87e  jz      loc_18000C94E
0x18000c884  cmp     edx, 1
0x18000c887  jnz     loc_18000C9BB
0x18000c88d  lea     rdx, [rbp+Binding]
0x18000c891  mov     [rbp+Binding], 0
0x18000c899  lea     rcx, qword_180012D10; IfSpec
0x18000c8a0  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000c8a5  mov     ebx, eax
0x18000c8a7  test    eax, eax
0x18000c8a9  jns     short loc_18000C8E3
0x18000c8ab  mov     rcx, [rbp+8]; this
0x18000c8af  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c8b6  mov     r9d, eax; char *
0x18000c8b9  mov     edx, 237h; void *
0x18000c8be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8c3  mov     rcx, [rbp+Binding]
0x18000c8c7  test    rcx, rcx
0x18000c8ca  jz      loc_18000C9B7
0x18000c8d0  mov     [rbp+Binding], rcx
0x18000c8d4  lea     rcx, [rbp+Binding]; Binding
0x18000c8d8  call    cs:__imp_RpcBindingFree
0x18000c8de  jmp     loc_18000C9B7
0x18000c8e3  mov     rbx, [rbp+Binding]
0x18000c8e7  lea     r8, [rbp+arg_8]
0x18000c8eb  lea     rdx, [rbp+Binding]
0x18000c8ef  mov     [rbp+Binding], rbx
0x18000c8f3  lea     rcx, CmsRpcClt_SetDebugConfigurationGlobal
0x18000c8fa  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000c8ff  mov     edi, eax
0x18000c901  test    eax, eax
0x18000c903  jns     short loc_18000C937
0x18000c905  mov     rcx, [rbp+8]; this
0x18000c909  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c910  mov     r9d, eax; char *
0x18000c913  mov     edx, 23Ch; void *
0x18000c918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c91d  test    rbx, rbx
0x18000c920  jz      short loc_18000C930
0x18000c922  lea     rcx, [rbp+Binding]; Binding
0x18000c926  mov     [rbp+Binding], rbx
0x18000c92a  call    cs:__imp_RpcBindingFree
0x18000c930  mov     eax, edi
0x18000c932  jmp     loc_18000C9C0
0x18000c937  test    rbx, rbx
0x18000c93a  jz      short loc_18000C94A
0x18000c93c  lea     rcx, [rbp+Binding]; Binding
0x18000c940  mov     [rbp+Binding], rbx
0x18000c944  call    cs:__imp_RpcBindingFree
0x18000c94a  xor     eax, eax
0x18000c94c  jmp     short loc_18000C9C0
0x18000c94e  mov     rax, [rcx+8]
0x18000c952  lea     r8, [rbp+arg_8]
0x18000c956  lea     rdx, [rbp+Binding]
0x18000c95a  mov     rcx, [rax]
0x18000c95d  mov     [rbp+Binding], rcx
0x18000c961  lea     rcx, CmsRpcClt_SetDebugConfigurationForLayer
0x18000c968  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000c96d  mov     ebx, eax
0x18000c96f  test    eax, eax
0x18000c971  jns     short loc_18000C94A
0x18000c973  mov     edx, 22Dh
0x18000c978  jmp     short loc_18000C9A4
0x18000c97a  mov     rax, [rcx+8]
0x18000c97e  lea     r8, [rbp+arg_8]
0x18000c982  lea     rdx, [rbp+Binding]
0x18000c986  mov     rcx, [rax]
0x18000c989  mov     [rbp+Binding], rcx
0x18000c98d  lea     rcx, CmsRpcClt_SetDebugConfigurationForStorage
0x18000c994  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000c999  mov     ebx, eax
0x18000c99b  test    eax, eax
0x18000c99d  jns     short loc_18000C94A
0x18000c99f  mov     edx, 221h; void *
0x18000c9a4  mov     rcx, [rbp+8]; this
0x18000c9a8  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c9af  mov     r9d, ebx; char *
0x18000c9b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9b7  mov     eax, ebx
0x18000c9b9  jmp     short loc_18000C9C0
0x18000c9bb  mov     eax, 80070032h
0x18000c9c0  mov     rbx, [rsp+20h+arg_10]
0x18000c9c5  mov     rdi, [rsp+20h+arg_18]
0x18000c9ca  add     rsp, 20h
0x18000c9ce  pop     rbp
0x18000c9cf  retn
```
