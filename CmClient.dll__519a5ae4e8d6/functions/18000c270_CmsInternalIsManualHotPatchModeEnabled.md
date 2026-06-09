# CmsInternalIsManualHotPatchModeEnabled

- ea: `0x18000c270`
- end: `0x18000c34e`
- name: `CmsInternalIsManualHotPatchModeEnabled`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000c270`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000c2ce`
- `RPCRT4!RpcBindingFree` at `0x18000c31f`
- `RPCRT4!RpcBindingFree` at `0x18000c336`
- `RPCRT4!RpcBindingFree` at `0x18000c2ce`
- `RPCRT4!RpcBindingFree` at `0x18000c31f`
- `RPCRT4!RpcBindingFree` at `0x18000c336`

## string_xrefs

- `0x18000c2a9`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c2fe`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalIsManualHotPatchModeEnabled(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  RPC_BINDING_HANDLE v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  __int64 v9; // [rsp+30h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp+18h] BYREF

  v9 = a1;
  Binding = 0;
  v1 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v4 = Binding;
    v5 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
           CmsRpcClt_IsManualHotPatchModeEnabled,
           &Binding,
           &v9);
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
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x260,
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
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v1,
      savedregs);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v2;
  }
}

```

## disassembly

```asm
0x18000c270  mov     [rsp-8+arg_10], rbx
0x18000c275  mov     [rsp-8+arg_18], rdi
0x18000c27a  mov     [rsp-8+arg_0], rcx
0x18000c27f  push    rbp; int
0x18000c280  mov     rbp, rsp
0x18000c283  sub     rsp, 20h
0x18000c287  lea     rdx, [rbp+Binding]
0x18000c28b  mov     [rbp+Binding], 0
0x18000c293  lea     rcx, qword_180013DC0; IfSpec
0x18000c29a  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000c29f  mov     ebx, eax
0x18000c2a1  test    eax, eax
0x18000c2a3  jns     short loc_18000C2D8
0x18000c2a5  mov     rcx, [rbp+8]; this
0x18000c2a9  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c2b0  mov     r9d, eax; char *
0x18000c2b3  mov     edx, 25Ah; void *
0x18000c2b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2bd  mov     rcx, [rbp+Binding]
0x18000c2c1  test    rcx, rcx
0x18000c2c4  jz      short loc_18000C2D4
0x18000c2c6  mov     [rbp+Binding], rcx
0x18000c2ca  lea     rcx, [rbp+Binding]; Binding
0x18000c2ce  call    cs:__imp_RpcBindingFree
0x18000c2d4  mov     eax, ebx
0x18000c2d6  jmp     short loc_18000C33E
0x18000c2d8  mov     rbx, [rbp+Binding]
0x18000c2dc  lea     r8, [rbp+arg_0]
0x18000c2e0  lea     rdx, [rbp+Binding]
0x18000c2e4  mov     [rbp+Binding], rbx
0x18000c2e8  lea     rcx, CmsRpcClt_IsManualHotPatchModeEnabled
0x18000c2ef  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000c2f4  mov     edi, eax
0x18000c2f6  test    eax, eax
0x18000c2f8  jns     short loc_18000C329
0x18000c2fa  mov     rcx, [rbp+8]; this
0x18000c2fe  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c305  mov     r9d, eax; char *
0x18000c308  mov     edx, 260h; void *
0x18000c30d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c312  test    rbx, rbx
0x18000c315  jz      short loc_18000C325
0x18000c317  lea     rcx, [rbp+Binding]; Binding
0x18000c31b  mov     [rbp+Binding], rbx
0x18000c31f  call    cs:__imp_RpcBindingFree
0x18000c325  mov     eax, edi
0x18000c327  jmp     short loc_18000C33E
0x18000c329  test    rbx, rbx
0x18000c32c  jz      short loc_18000C33C
0x18000c32e  lea     rcx, [rbp+Binding]; Binding
0x18000c332  mov     [rbp+Binding], rbx
0x18000c336  call    cs:__imp_RpcBindingFree
0x18000c33c  xor     eax, eax
0x18000c33e  mov     rbx, [rsp+20h+arg_10]
0x18000c343  mov     rdi, [rsp+20h+arg_18]
0x18000c348  add     rsp, 20h
0x18000c34c  pop     rbp
0x18000c34d  retn
```
