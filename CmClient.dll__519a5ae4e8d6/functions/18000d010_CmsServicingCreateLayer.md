# CmsServicingCreateLayer

- ea: `0x18000d010`
- end: `0x18000d259`
- name: `CmsServicingCreateLayer`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180001550`
- `0x180001574`
- `0x180001944`
- `0x1800066e4`
- `0x18000cc78`
- `0x18000d010`
- `0x18000d9e8`
- `0x18000db50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1d2`
- `RPCRT4!RpcBindingFree` at `0x18000d0bb`
- `RPCRT4!RpcBindingFree` at `0x18000d16c`
- `RPCRT4!RpcBindingFree` at `0x18000d209`
- `RPCRT4!RpcBindingFree` at `0x18000d0bb`
- `RPCRT4!RpcBindingFree` at `0x18000d16c`
- `RPCRT4!RpcBindingFree` at `0x18000d209`

## string_xrefs

- `0x18000d098`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d13d`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d217`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingCreateLayer(int a1, void *a2, _QWORD *a3)
{
  char *v4; // rax
  _QWORD *v5; // r14
  int v6; // eax
  int v7; // ecx
  unsigned int v8; // ebx
  void *v9; // rcx
  RPC_BINDING_HANDLE v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  void *v13; // rcx
  void *v14; // rdi
  void **v15; // r15
  void *v16; // r12
  DWORD LastError; // esi
  void *v18; // rcx
  int v20; // [rsp+20h] [rbp-59h]
  int v21; // [rsp+20h] [rbp-59h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-39h] BYREF
  void *v23; // [rsp+48h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE v24; // [rsp+50h] [rbp-29h] BYREF
  int v25; // [rsp+58h] [rbp-21h] BYREF
  __int64 v26; // [rsp+60h] [rbp-19h] BYREF
  __int64 *v27; // [rsp+68h] [rbp-11h] BYREF
  void **v28; // [rsp+70h] [rbp-9h] BYREF
  int v29[2]; // [rsp+78h] [rbp-1h] BYREF
  char v30; // [rsp+80h] [rbp+7h] BYREF
  __int128 v31; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v25 = a1;
  v24 = a2;
  v4 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)0x8007000ELL,
      v20);
    return v8;
  }
  *(_QWORD *)v4 = 0;
  Binding = 0;
  *(GUID *)(v4 + 8) = GUID_NULL;
  *((_QWORD *)v4 + 3) = 0;
  v6 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v8 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v6,
      v20);
    if ( Binding )
      RpcBindingFree(&Binding);
    v9 = (void *)v5[3];
    if ( v9 )
      MIDL_user_free(v9);
LABEL_15:
    operator delete(v5, (const struct std::nothrow_t *)0x20);
    return v8;
  }
  v10 = Binding;
  v27 = &v26;
  v26 = 0;
  v28 = &v23;
  v23 = 0;
  *(_QWORD *)v29 = &v31;
  v31 = 0;
  v11 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_ID,_CMS_LAYER_PROPERTIES *,_GUID *,unsigned short * *,void * *),void *,enum _CMS_CLIENT_ID &,_CMS_LAYER_PROPERTIES * &,_GUID *,unsigned short * *,void * *>(
          v7,
          (unsigned int)&Binding,
          (unsigned int)&v25,
          (unsigned int)&v24,
          (__int64)v29,
          (__int64)&v28,
          (__int64)&v27);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v11,
      v21);
    if ( v23 )
      MIDL_user_free(v23);
    if ( v10 )
    {
      v24 = v10;
      RpcBindingFree(&v24);
    }
    v13 = (void *)v5[3];
    if ( v13 )
      MIDL_user_free(v13);
    v8 = v12;
    goto LABEL_15;
  }
  v14 = v23;
  v15 = (void **)(v5 + 3);
  v23 = 0;
  *v5 = v26;
  *(_OWORD *)(v5 + 1) = v31;
  if ( v5 + 3 == (_QWORD *)&v30 )
  {
    if ( v14 )
      MIDL_user_free(v14);
  }
  else
  {
    v16 = *v15;
    if ( *v15 )
    {
      LastError = GetLastError();
      MIDL_user_free(v16);
      SetLastError(LastError);
    }
    *v15 = v14;
  }
  v18 = v23;
  *a3 = v5;
  if ( v18 )
    MIDL_user_free(v18);
  if ( v10 )
  {
    v24 = v10;
    RpcBindingFree(&v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d010  mov     [rsp-8+arg_18], rbx
0x18000d015  push    rbp
0x18000d016  push    rsi
0x18000d017  push    rdi
0x18000d018  push    r12
0x18000d01a  push    r13
0x18000d01c  push    r14
0x18000d01e  push    r15
0x18000d020  lea     rbp, [rsp-27h]
0x18000d025  sub     rsp, 0A0h
0x18000d02c  mov     rax, cs:__security_cookie
0x18000d033  xor     rax, rsp
0x18000d036  mov     [rbp+57h+var_38], rax
0x18000d03a  mov     [rbp+57h+var_78], ecx
0x18000d03d  mov     r15d, 20h ; ' '
0x18000d043  mov     [rbp+57h+var_80], rdx
0x18000d047  mov     ecx, r15d; unsigned __int64
0x18000d04a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d051  mov     r13, r8
0x18000d054  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d059  xor     esi, esi
0x18000d05b  mov     r14, rax
0x18000d05e  test    rax, rax
0x18000d061  jz      loc_18000D213
0x18000d067  mov     [rax], rsi
0x18000d06a  lea     rdx, [rbp+57h+Binding]
0x18000d06e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d075  lea     rcx, qword_180012D10; IfSpec
0x18000d07c  mov     [rbp+57h+Binding], rsi
0x18000d080  movdqu  xmmword ptr [rax+8], xmm0
0x18000d085  mov     [rax+18h], rsi
0x18000d089  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000d08e  mov     ebx, eax
0x18000d090  test    eax, eax
0x18000d092  jns     short loc_18000D0D8
0x18000d094  mov     rcx, [rbp+5Fh]; this
0x18000d098  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d09f  mov     r9d, eax; char *
0x18000d0a2  lea     edx, [rsi+65h]; void *
0x18000d0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0aa  mov     rcx, [rbp+57h+Binding]
0x18000d0ae  test    rcx, rcx
0x18000d0b1  jz      short loc_18000D0C1
0x18000d0b3  mov     [rbp+57h+Binding], rcx
0x18000d0b7  lea     rcx, [rbp+57h+Binding]; Binding
0x18000d0bb  call    cs:__imp_RpcBindingFree
0x18000d0c1  mov     rcx, [r14+18h]; void *
0x18000d0c5  test    rcx, rcx
0x18000d0c8  jz      loc_18000D182
0x18000d0ce  call    MIDL_user_free
0x18000d0d3  jmp     loc_18000D182
0x18000d0d8  mov     rbx, [rbp+57h+Binding]
0x18000d0dc  lea     rax, [rbp+57h+var_70]
0x18000d0e0  mov     [rbp+57h+var_68], rax
0x18000d0e4  lea     r9, [rbp+57h+var_80]
0x18000d0e8  lea     rax, [rbp+57h+var_88]
0x18000d0ec  mov     [rbp+57h+var_70], rsi
0x18000d0f0  mov     [rbp+57h+var_60], rax
0x18000d0f4  lea     r8, [rbp+57h+var_78]
0x18000d0f8  lea     rax, [rbp+57h+var_48]
0x18000d0fc  mov     [rbp+57h+var_88], rsi
0x18000d100  mov     qword ptr [rbp+57h+var_58], rax
0x18000d104  lea     rdx, [rbp+57h+Binding]
0x18000d108  lea     rax, [rbp+57h+var_68]
0x18000d10c  mov     [rbp+57h+Binding], rbx
0x18000d110  mov     [rsp+0D0h+var_A0], rax
0x18000d115  xorps   xmm0, xmm0
0x18000d118  lea     rax, [rbp+57h+var_60]
0x18000d11c  mov     [rsp+0D0h+var_A8], rax
0x18000d121  lea     rax, [rbp+57h+var_58]
0x18000d125  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18000d12a  movups  [rbp+57h+var_48], xmm0
0x18000d12e  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_LAYER_PROPERTIES@@PEAU_GUID@@PEAPEAGPEAPEAX@ZPEAXAEAW41@AEAPEAU2@PEAU3@PEAPEAGPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_LAYER_PROPERTIES@@PEAU_GUID@@PEAPEAGPEAPEAX@Z$$QEAPEAXAEAW43@AEAPEAU4@$$QEAPEAU5@$$QEAPEAPEAG$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_ID,_CMS_LAYER_PROPERTIES *,_GUID *,ushort * *,void * *),void *,_CMS_CLIENT_ID &,_CMS_LAYER_PROPERTIES * &,_GUID *,ushort * *,void * *>(long (*)(void *,_CMS_CLIENT_ID,_CMS_LAYER_PROPERTIES *,_GUID *,ushort * *,void * *),void * &&,_CMS_CLIENT_ID &,_CMS_LAYER_PROPERTIES * &,_GUID * &&,ushort * * &&,void * * &&)
0x18000d133  mov     edi, eax
0x18000d135  test    eax, eax
0x18000d137  jns     short loc_18000D192
0x18000d139  mov     rcx, [rbp+5Fh]; this
0x18000d13d  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d144  mov     r9d, eax; char *
0x18000d147  mov     edx, 75h ; 'u'; void *
0x18000d14c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d151  mov     rcx, [rbp+57h+var_88]; void *
0x18000d155  test    rcx, rcx
0x18000d158  jz      short loc_18000D15F
0x18000d15a  call    MIDL_user_free
0x18000d15f  test    rbx, rbx
0x18000d162  jz      short loc_18000D172
0x18000d164  lea     rcx, [rbp+57h+var_80]; Binding
0x18000d168  mov     [rbp+57h+var_80], rbx
0x18000d16c  call    cs:__imp_RpcBindingFree
0x18000d172  mov     rcx, [r14+18h]; void *
0x18000d176  test    rcx, rcx
0x18000d179  jz      short loc_18000D180
0x18000d17b  call    MIDL_user_free
0x18000d180  mov     ebx, edi
0x18000d182  mov     rdx, r15; struct std::nothrow_t *
0x18000d185  mov     rcx, r14; void *
0x18000d188  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d18d  jmp     loc_18000D230
0x18000d192  mov     rdi, [rbp+57h+var_88]
0x18000d196  lea     r15, [r14+18h]
0x18000d19a  mov     rax, [rbp+57h+var_70]
0x18000d19e  mov     [rbp+57h+var_88], rsi
0x18000d1a2  mov     [r14], rax
0x18000d1a5  lea     rax, [rbp+57h+var_50]
0x18000d1a9  movups  xmm0, [rbp+57h+var_48]
0x18000d1ad  movdqu  xmmword ptr [r14+8], xmm0
0x18000d1b3  cmp     r15, rax
0x18000d1b6  jz      short loc_18000D1DD
0x18000d1b8  mov     r12, [r15]
0x18000d1bb  test    r12, r12
0x18000d1be  jz      short loc_18000D1D8
0x18000d1c0  call    cs:__imp_GetLastError
0x18000d1c6  mov     rcx, r12; void *
0x18000d1c9  mov     esi, eax
0x18000d1cb  call    MIDL_user_free
0x18000d1d0  mov     ecx, esi; dwErrCode
0x18000d1d2  call    cs:__imp_SetLastError
0x18000d1d8  mov     [r15], rdi
0x18000d1db  jmp     short loc_18000D1EA
0x18000d1dd  test    rdi, rdi
0x18000d1e0  jz      short loc_18000D1EA
0x18000d1e2  mov     rcx, rdi; void *
0x18000d1e5  call    MIDL_user_free
0x18000d1ea  mov     rcx, [rbp+57h+var_88]; void *
0x18000d1ee  mov     [r13+0], r14
0x18000d1f2  test    rcx, rcx
0x18000d1f5  jz      short loc_18000D1FC
0x18000d1f7  call    MIDL_user_free
0x18000d1fc  test    rbx, rbx
0x18000d1ff  jz      short loc_18000D20F
0x18000d201  lea     rcx, [rbp+57h+var_80]; Binding
0x18000d205  mov     [rbp+57h+var_80], rbx
0x18000d209  call    cs:__imp_RpcBindingFree
0x18000d20f  xor     eax, eax
0x18000d211  jmp     short loc_18000D232
0x18000d213  mov     rcx, [rbp+5Fh]; this
0x18000d217  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d21e  mov     ebx, 8007000Eh
0x18000d223  mov     edx, 61h ; 'a'; void *
0x18000d228  mov     r9d, ebx; char *
0x18000d22b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d230  mov     eax, ebx
0x18000d232  mov     rcx, [rbp+57h+var_38]
0x18000d236  xor     rcx, rsp; StackCookie
0x18000d239  call    __security_check_cookie
0x18000d23e  mov     rbx, [rsp+0D0h+arg_18]
0x18000d246  add     rsp, 0A0h
0x18000d24d  pop     r15
0x18000d24f  pop     r14
0x18000d251  pop     r13
0x18000d253  pop     r12
0x18000d255  pop     rdi
0x18000d256  pop     rsi
0x18000d257  pop     rbp
0x18000d258  retn
```
