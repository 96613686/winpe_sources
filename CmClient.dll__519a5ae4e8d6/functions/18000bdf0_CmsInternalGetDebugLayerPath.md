# CmsInternalGetDebugLayerPath

- ea: `0x18000bdf0`
- end: `0x18000bf91`
- name: `CmsInternalGetDebugLayerPath`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b7f0`
- `0x18000bdf0`
- `0x18000d9e8`
- `0x18000db50`
- `0x18000ee00`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000be6a`
- `RPCRT4!RpcBindingFree` at `0x18000beee`
- `RPCRT4!RpcBindingFree` at `0x18000bf35`
- `RPCRT4!RpcBindingFree` at `0x18000bf5a`
- `RPCRT4!RpcBindingFree` at `0x18000be6a`
- `RPCRT4!RpcBindingFree` at `0x18000beee`
- `RPCRT4!RpcBindingFree` at `0x18000bf35`
- `RPCRT4!RpcBindingFree` at `0x18000bf5a`

## string_xrefs

- `0x18000be41`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000bebf`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000bf6b`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetDebugLayerPath(int a1, void *a2, unsigned int *a3)
{
  int v6; // eax
  int v7; // ecx
  unsigned int v8; // ebx
  RPC_BINDING_HANDLE v9; // rbx
  int v10; // eax
  unsigned int v11; // esi
  unsigned int v13; // edx
  unsigned int v14; // eax
  void *v15; // rdi
  int v16; // [rsp+20h] [rbp-40h]
  int v17; // [rsp+20h] [rbp-40h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-30h] BYREF
  RPC_BINDING_HANDLE p_Src; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-20h] BYREF
  void *Src; // [rsp+48h] [rbp-18h] BYREF
  int v22[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  if ( !a3 || *a3 && !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)0x80070057LL,
      v16);
    return v8;
  }
  Binding = 0;
  v6 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v6,
      v16);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v8;
  }
  v9 = Binding;
  *(_QWORD *)v22 = &v20;
  v20 = 0;
  p_Src = &Src;
  Src = 0;
  v10 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,unsigned short * *,unsigned long *),void *,_GUID &,unsigned short * *,unsigned long *>(
          v7,
          (unsigned int)&Binding,
          a1,
          (unsigned int)&p_Src,
          (__int64)v22);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v13 = v20;
    v14 = *a3;
    *a3 = v20;
    if ( v14 < v13 )
    {
      if ( Src )
        MIDL_user_free(Src);
      if ( v9 )
      {
        p_Src = v9;
        RpcBindingFree(&p_Src);
      }
      return 2147942522LL;
    }
    else
    {
      v15 = Src;
      memcpy_0(a2, Src, 2LL * v13);
      if ( v15 )
        MIDL_user_free(v15);
      if ( v9 )
      {
        p_Src = v9;
        RpcBindingFree(&p_Src);
      }
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v10,
      v17);
    if ( Src )
      MIDL_user_free(Src);
    if ( v9 )
    {
      p_Src = v9;
      RpcBindingFree(&p_Src);
    }
    return v11;
  }
}

```

## disassembly

```asm
0x18000bdf0  push    rbp
0x18000bdf2  push    rbx
0x18000bdf3  push    rsi
0x18000bdf4  push    rdi
0x18000bdf5  push    r14
0x18000bdf7  mov     rbp, rsp
0x18000bdfa  sub     rsp, 60h
0x18000bdfe  mov     rdi, r8
0x18000be01  mov     r14, rdx
0x18000be04  mov     rsi, rcx
0x18000be07  test    r8, r8
0x18000be0a  jz      loc_18000BF67
0x18000be10  cmp     dword ptr [r8], 0
0x18000be14  jbe     short loc_18000BE1F
0x18000be16  test    rdx, rdx
0x18000be19  jz      loc_18000BF67
0x18000be1f  lea     rdx, [rbp+Binding]
0x18000be23  mov     [rbp+Binding], 0
0x18000be2b  lea     rcx, qword_180013DC0; IfSpec
0x18000be32  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000be37  mov     ebx, eax
0x18000be39  test    eax, eax
0x18000be3b  jns     short loc_18000BE75
0x18000be3d  mov     rcx, [rbp+28h]; this
0x18000be41  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000be48  mov     r9d, eax; char *
0x18000be4b  mov     edx, 31h ; '1'; void *
0x18000be50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be55  mov     rcx, [rbp+Binding]
0x18000be59  test    rcx, rcx
0x18000be5c  jz      loc_18000BF84
0x18000be62  mov     [rbp+Binding], rcx
0x18000be66  lea     rcx, [rbp+Binding]; Binding
0x18000be6a  call    cs:__imp_RpcBindingFree
0x18000be70  jmp     loc_18000BF84
0x18000be75  mov     rbx, [rbp+Binding]
0x18000be79  lea     rax, [rbp+var_20]
0x18000be7d  mov     qword ptr [rbp+var_10], rax
0x18000be81  lea     r9, [rbp+var_28]
0x18000be85  lea     rax, [rbp+Src]
0x18000be89  mov     [rbp+var_20], 0
0x18000be90  mov     [rbp+var_28], rax
0x18000be94  lea     rdx, [rbp+Binding]
0x18000be98  lea     rax, [rbp+var_10]
0x18000be9c  mov     [rbp+Src], 0
0x18000bea4  mov     r8, rsi
0x18000bea7  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000beac  mov     [rbp+Binding], rbx
0x18000beb0  call    ??$InvokeStubFunction@P6AJPEAXU_GUID@@PEAPEAGPEAK@ZPEAXAEAU1@PEAPEAGPEAK@Rpc@Manager@Container@@YAJP6AJPEAXU_GUID@@PEAPEAGPEAK@Z$$QEAPEAXAEAU3@$$QEAPEAPEAG$$QEAPEAK@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID,ushort * *,ulong *),void *,_GUID &,ushort * *,ulong *>(long (*)(void *,_GUID,ushort * *,ulong *),void * &&,_GUID &,ushort * * &&,ulong * &&)
0x18000beb5  mov     esi, eax
0x18000beb7  test    eax, eax
0x18000beb9  jns     short loc_18000BEFB
0x18000bebb  mov     rcx, [rbp+28h]; this
0x18000bebf  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bec6  mov     r9d, eax; char *
0x18000bec9  mov     edx, 39h ; '9'; void *
0x18000bece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bed3  mov     rcx, [rbp+Src]; void *
0x18000bed7  test    rcx, rcx
0x18000beda  jz      short loc_18000BEE1
0x18000bedc  call    MIDL_user_free
0x18000bee1  test    rbx, rbx
0x18000bee4  jz      short loc_18000BEF4
0x18000bee6  lea     rcx, [rbp+var_28]; Binding
0x18000beea  mov     [rbp+var_28], rbx
0x18000beee  call    cs:__imp_RpcBindingFree
0x18000bef4  mov     eax, esi
0x18000bef6  jmp     loc_18000BF86
0x18000befb  mov     edx, [rbp+var_20]
0x18000befe  mov     eax, [rdi]
0x18000bf00  mov     [rdi], edx
0x18000bf02  cmp     eax, edx
0x18000bf04  jb      short loc_18000BF3F
0x18000bf06  mov     rdi, [rbp+Src]
0x18000bf0a  mov     r8d, edx
0x18000bf0d  add     r8, r8; Size
0x18000bf10  mov     rdx, rdi; Src
0x18000bf13  mov     rcx, r14; void *
0x18000bf16  call    memcpy_0
0x18000bf1b  test    rdi, rdi
0x18000bf1e  jz      short loc_18000BF28
0x18000bf20  mov     rcx, rdi; void *
0x18000bf23  call    MIDL_user_free
0x18000bf28  test    rbx, rbx
0x18000bf2b  jz      short loc_18000BF3B
0x18000bf2d  lea     rcx, [rbp+var_28]; Binding
0x18000bf31  mov     [rbp+var_28], rbx
0x18000bf35  call    cs:__imp_RpcBindingFree
0x18000bf3b  xor     eax, eax
0x18000bf3d  jmp     short loc_18000BF86
0x18000bf3f  mov     rcx, [rbp+Src]; void *
0x18000bf43  test    rcx, rcx
0x18000bf46  jz      short loc_18000BF4D
0x18000bf48  call    MIDL_user_free
0x18000bf4d  test    rbx, rbx
0x18000bf50  jz      short loc_18000BF60
0x18000bf52  lea     rcx, [rbp+var_28]; Binding
0x18000bf56  mov     [rbp+var_28], rbx
0x18000bf5a  call    cs:__imp_RpcBindingFree
0x18000bf60  mov     eax, 8007007Ah
0x18000bf65  jmp     short loc_18000BF86
0x18000bf67  mov     rcx, [rbp+28h]; this
0x18000bf6b  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000bf72  mov     ebx, 80070057h
0x18000bf77  mov     edx, 2Ch ; ','; void *
0x18000bf7c  mov     r9d, ebx; char *
0x18000bf7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf84  mov     eax, ebx
0x18000bf86  add     rsp, 60h
0x18000bf8a  pop     r14
0x18000bf8c  pop     rdi
0x18000bf8d  pop     rsi
0x18000bf8e  pop     rbx
0x18000bf8f  pop     rbp
0x18000bf90  retn
```
