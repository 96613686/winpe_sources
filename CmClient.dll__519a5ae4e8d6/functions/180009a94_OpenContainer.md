# OpenContainer

- ea: `0x180009a94`
- end: `0x180009d3e`
- name: `OpenContainer`
- size: `682`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180008630`
- `0x1800086b0`

## callees

- `0x180001550`
- `0x180001574`
- `0x1800023f0`
- `0x180002970`
- `0x180003e68`
- `0x1800066e4`
- `0x180009a94`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180009b57`
- `RPCRT4!RpcBindingFree` at `0x180009bfe`
- `RPCRT4!RpcBindingFree` at `0x180009ce9`
- `RPCRT4!RpcBindingFree` at `0x180009b57`
- `RPCRT4!RpcBindingFree` at `0x180009bfe`
- `RPCRT4!RpcBindingFree` at `0x180009ce9`

## string_xrefs

- `0x180009b2e`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180009bdd`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180009c8d`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180009cf8`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall OpenContainer(__int128 **a1, __int64 a2, int a3, int a4, _QWORD *a5)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // ebx
  RPC_BINDING_HANDLE v12; // rbx
  int v13; // eax
  unsigned int v14; // esi
  RPC_BINDING_HANDLE *v15; // rcx
  __int128 v16; // xmm0
  int v17; // eax
  __int64 v18; // rcx
  int v20; // [rsp+20h] [rbp-81h]
  int v21; // [rsp+20h] [rbp-81h]
  int v22; // [rsp+20h] [rbp-81h]
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-51h] BYREF
  int v24; // [rsp+58h] [rbp-49h] BYREF
  int v25; // [rsp+60h] [rbp-41h] BYREF
  int v26; // [rsp+68h] [rbp-39h] BYREF
  RPC_BINDING_HANDLE v27; // [rsp+70h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE v28; // [rsp+78h] [rbp-29h] BYREF
  __int64 v29; // [rsp+80h] [rbp-21h] BYREF
  _DWORD *v30; // [rsp+88h] [rbp-19h] BYREF
  __int64 *v31; // [rsp+90h] [rbp-11h] BYREF
  __int128 *v32; // [rsp+98h] [rbp-9h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-1h] BYREF
  __int128 v34; // [rsp+A8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v26 = a3;
  v25 = a4;
  v7 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    v11 = -2147024882;
    v30 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x8007000ELL,
      v20);
    goto LABEL_22;
  }
  v7[4] = 0;
  v30 = v7;
  *(GUID *)v7 = GUID_NULL;
  v7[5] = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 5) = 0;
  *((_QWORD *)v7 + 4) = 0;
  Binding = 0;
  v9 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v9,
      v20);
    if ( Binding )
      RpcBindingFree(&Binding);
    goto LABEL_22;
  }
  v34 = 0;
  v29 = 0;
  v33 = 0;
  v24 = 0;
  if ( *((_BYTE *)a1 + 8) )
  {
    v12 = Binding;
    v31 = &v29;
    v32 = (__int128 *)&v24;
    v27 = &v33;
    v13 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,unsigned long,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,unsigned long &,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,void * *>(
            v10,
            (unsigned int)&Binding,
            (_DWORD)a1,
            (unsigned int)&v26,
            (__int64)&v25,
            (__int64)&v27,
            (__int64)&v32,
            (__int64)&v31);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v13,
        v21);
      if ( !v12 )
      {
LABEL_10:
        v11 = v14;
        goto LABEL_22;
      }
      v27 = v12;
      v15 = &v27;
LABEL_9:
      RpcBindingFree(v15);
      goto LABEL_10;
    }
    v16 = **a1;
    v34 = v16;
  }
  else
  {
    v27 = &v29;
    v32 = &v34;
    v31 = (__int64 *)&v24;
    v28 = &v33;
    if ( !*(_BYTE *)(a2 + 8) )
      __int2c();
    v12 = Binding;
    v17 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,enum _CMS_CLIENT_ID,unsigned long,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,_GUID *,void * *),void *,void * &,enum _CMS_CLIENT_ID &,unsigned long &,_WNF_STATE_NAME *,enum _CMS_CONTAINER_TYPE *,_GUID *,void * *>(
            v10,
            (unsigned int)&Binding,
            a2,
            (unsigned int)&v26,
            (__int64)&v25,
            (__int64)&v28,
            (__int64)&v31,
            (__int64)&v32,
            (__int64)&v27);
    v14 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v17,
        v22);
      if ( !v12 )
        goto LABEL_10;
      v28 = v12;
      v15 = &v28;
      goto LABEL_9;
    }
    v16 = v34;
  }
  v18 = v29;
  v8[4] = v24;
  v30 = 0;
  *(_OWORD *)v8 = v16;
  *((_QWORD *)v8 + 4) = v33;
  *((_QWORD *)v8 + 3) = v18;
  *a5 = v8;
  if ( v12 )
  {
    v28 = v12;
    RpcBindingFree(&v28);
  }
  v11 = 0;
LABEL_22:
  wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(&v30);
  return v11;
}

```

## disassembly

```asm
0x180009a94  push    rbp
0x180009a96  push    rbx
0x180009a97  push    rsi
0x180009a98  push    rdi
0x180009a99  push    r12
0x180009a9b  push    r14
0x180009a9d  push    r15
0x180009a9f  lea     rbp, [rsp-1Fh]
0x180009aa4  sub     rsp, 0C0h
0x180009aab  mov     rax, cs:__security_cookie
0x180009ab2  xor     rax, rsp
0x180009ab5  mov     [rbp+4Fh+var_38], rax
0x180009ab9  mov     r15, [rbp+4Fh+arg_20]
0x180009abd  mov     rsi, rdx
0x180009ac0  mov     r14, rcx
0x180009ac3  mov     [rbp+4Fh+var_88], r8d
0x180009ac7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009ace  mov     [rbp+4Fh+var_90], r9d
0x180009ad2  mov     ecx, 30h ; '0'; unsigned __int64
0x180009ad7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009adc  xor     r12d, r12d
0x180009adf  mov     rdi, rax
0x180009ae2  test    rax, rax
0x180009ae5  jz      loc_180009CF4
0x180009aeb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180009af2  mov     [rax+10h], r12d
0x180009af6  lea     rdx, [rbp+4Fh+Binding]
0x180009afa  lea     rcx, qword_180012D10; IfSpec
0x180009b01  mov     [rbp+4Fh+var_68], rdi
0x180009b05  movdqu  xmmword ptr [rax], xmm0
0x180009b09  mov     [rax+14h], r12d
0x180009b0d  mov     [rax+18h], r12
0x180009b11  mov     [rax+28h], r12
0x180009b15  xor     eax, eax
0x180009b17  mov     [rdi+20h], rax
0x180009b1b  mov     [rbp+4Fh+Binding], r12
0x180009b1f  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180009b24  mov     ebx, eax
0x180009b26  test    eax, eax
0x180009b28  jns     short loc_180009B62
0x180009b2a  mov     rcx, [rbp+57h]; this
0x180009b2e  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009b35  mov     r9d, eax; char *
0x180009b38  mov     edx, 0DAh; void *
0x180009b3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b42  mov     rcx, [rbp+4Fh+Binding]
0x180009b46  test    rcx, rcx
0x180009b49  jz      loc_180009D15
0x180009b4f  mov     [rbp+4Fh+Binding], rcx
0x180009b53  lea     rcx, [rbp+4Fh+Binding]; Binding
0x180009b57  call    cs:__imp_RpcBindingFree
0x180009b5d  jmp     loc_180009D15
0x180009b62  lea     rax, [rbp+4Fh+var_70]
0x180009b66  xorps   xmm0, xmm0
0x180009b69  movups  [rbp+4Fh+var_48], xmm0
0x180009b6d  mov     [rbp+4Fh+var_70], r12
0x180009b71  mov     [rbp+4Fh+var_50], r12
0x180009b75  mov     [rbp+4Fh+var_98], r12d
0x180009b79  cmp     [r14+8], r12b
0x180009b7d  jz      loc_180009C1A
0x180009b83  mov     rbx, [rbp+4Fh+Binding]
0x180009b87  lea     r9, [rbp+4Fh+var_88]
0x180009b8b  mov     [rbp+4Fh+var_60], rax
0x180009b8f  lea     rdx, [rbp+4Fh+Binding]
0x180009b93  lea     rax, [rbp+4Fh+var_98]
0x180009b97  mov     [rbp+4Fh+Binding], rbx
0x180009b9b  mov     [rbp+4Fh+var_58], rax
0x180009b9f  mov     r8, r14
0x180009ba2  lea     rax, [rbp+4Fh+var_50]
0x180009ba6  mov     [rbp+4Fh+var_80], rax
0x180009baa  lea     rax, [rbp+4Fh+var_60]
0x180009bae  mov     [rsp+0F0h+var_B8], rax
0x180009bb3  lea     rax, [rbp+4Fh+var_58]
0x180009bb7  mov     [rsp+0F0h+var_C0], rax
0x180009bbc  lea     rax, [rbp+4Fh+var_80]
0x180009bc0  mov     [rsp+0F0h+var_C8], rax
0x180009bc5  lea     rax, [rbp+4Fh+var_90]
0x180009bc9  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180009bce  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@AEAKPEAU3@PEAW44@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@AEAK$$QEAPEAU5@$$QEAPEAW46@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME * &&,_CMS_CONTAINER_TYPE * &&,void * * &&)
0x180009bd3  mov     esi, eax
0x180009bd5  test    eax, eax
0x180009bd7  jns     short loc_180009C0B
0x180009bd9  mov     rcx, [rbp+57h]; this
0x180009bdd  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009be4  mov     r9d, eax; char *
0x180009be7  mov     edx, 0F0h; void *
0x180009bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bf1  test    rbx, rbx
0x180009bf4  jz      short loc_180009C04
0x180009bf6  mov     [rbp+4Fh+var_80], rbx
0x180009bfa  lea     rcx, [rbp+4Fh+var_80]; Binding
0x180009bfe  call    cs:__imp_RpcBindingFree
0x180009c04  mov     ebx, esi
0x180009c06  jmp     loc_180009D15
0x180009c0b  mov     rax, [r14]
0x180009c0e  movups  xmm0, xmmword ptr [rax]
0x180009c11  movups  [rbp+4Fh+var_48], xmm0
0x180009c15  jmp     loc_180009CBB
0x180009c1a  mov     [rbp+4Fh+var_80], rax
0x180009c1e  lea     rax, [rbp+4Fh+var_48]
0x180009c22  mov     [rbp+4Fh+var_58], rax
0x180009c26  lea     rax, [rbp+4Fh+var_98]
0x180009c2a  mov     [rbp+4Fh+var_60], rax
0x180009c2e  lea     rax, [rbp+4Fh+var_50]
0x180009c32  mov     [rbp+4Fh+var_78], rax
0x180009c36  cmp     [rsi+8], r12b
0x180009c3a  jnz     short loc_180009C3E
0x180009c3c  int     2Ch; Windows NT - assertion failure
0x180009c3e  mov     rbx, [rbp+4Fh+Binding]
0x180009c42  lea     rax, [rbp+4Fh+var_80]
0x180009c46  mov     [rsp+0F0h+var_B0], rax
0x180009c4b  lea     r9, [rbp+4Fh+var_88]
0x180009c4f  lea     rax, [rbp+4Fh+var_58]
0x180009c53  mov     [rbp+4Fh+Binding], rbx
0x180009c57  mov     [rsp+0F0h+var_B8], rax
0x180009c5c  lea     rdx, [rbp+4Fh+Binding]
0x180009c60  lea     rax, [rbp+4Fh+var_60]
0x180009c64  mov     r8, rsi
0x180009c67  mov     [rsp+0F0h+var_C0], rax
0x180009c6c  lea     rax, [rbp+4Fh+var_78]
0x180009c70  mov     [rsp+0F0h+var_C8], rax
0x180009c75  lea     rax, [rbp+4Fh+var_90]
0x180009c79  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180009c7e  call    ??$InvokeStubFunction@P6AJPEAX0W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAU_GUID@@PEAPEAX@ZPEAXAEAPEAXAEAW41@AEAKPEAU2@PEAW43@PEAU4@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX0W4_CMS_CLIENT_ID@@KPEAU_WNF_STATE_NAME@@PEAW4_CMS_CONTAINER_TYPE@@PEAU_GUID@@PEAPEAX@Z$$QEAPEAXAEAPEAXAEAW43@AEAK$$QEAPEAU4@$$QEAPEAW45@$$QEAPEAU6@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,_GUID *,void * *),void *,void * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,_GUID *,void * *>(long (*)(void *,void *,_CMS_CLIENT_ID,ulong,_WNF_STATE_NAME *,_CMS_CONTAINER_TYPE *,_GUID *,void * *),void * &&,void * &,_CMS_CLIENT_ID &,ulong &,_WNF_STATE_NAME * &&,_CMS_CONTAINER_TYPE * &&,_GUID * &&,void * * &&)
0x180009c83  mov     esi, eax
0x180009c85  test    eax, eax
0x180009c87  jns     short loc_180009CB7
0x180009c89  mov     rcx, [rbp+57h]; this
0x180009c8d  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009c94  mov     r9d, eax; char *
0x180009c97  mov     edx, 104h; void *
0x180009c9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ca1  test    rbx, rbx
0x180009ca4  jz      loc_180009C04
0x180009caa  mov     [rbp+4Fh+var_78], rbx
0x180009cae  lea     rcx, [rbp+4Fh+var_78]
0x180009cb2  jmp     loc_180009BFE
0x180009cb7  movups  xmm0, [rbp+4Fh+var_48]
0x180009cbb  mov     eax, [rbp+4Fh+var_98]
0x180009cbe  mov     rcx, [rbp+4Fh+var_70]
0x180009cc2  mov     [rdi+10h], eax
0x180009cc5  mov     [rbp+4Fh+var_68], r12
0x180009cc9  movdqu  xmmword ptr [rdi], xmm0
0x180009ccd  mov     rax, [rbp+4Fh+var_50]
0x180009cd1  mov     [rdi+20h], rax
0x180009cd5  mov     [rdi+18h], rcx
0x180009cd9  mov     [r15], rdi
0x180009cdc  test    rbx, rbx
0x180009cdf  jz      short loc_180009CEF
0x180009ce1  lea     rcx, [rbp+4Fh+var_78]; Binding
0x180009ce5  mov     [rbp+4Fh+var_78], rbx
0x180009ce9  call    cs:__imp_RpcBindingFree
0x180009cef  mov     ebx, r12d
0x180009cf2  jmp     short loc_180009D15
0x180009cf4  mov     rcx, [rbp+57h]; this
0x180009cf8  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009cff  mov     ebx, 8007000Eh
0x180009d04  mov     [rbp+4Fh+var_68], r12
0x180009d08  mov     r9d, ebx; char *
0x180009d0b  mov     edx, 0D5h; void *
0x180009d10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d15  lea     rcx, [rbp+4Fh+var_68]
0x180009d19  call    ??1?$unique_ptr@VOutOfProcClientContainerHandle@Client@Manager@Container@@U?$default_delete@VOutOfProcClientContainerHandle@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(void)
0x180009d1e  mov     eax, ebx
0x180009d20  mov     rcx, [rbp+4Fh+var_38]
0x180009d24  xor     rcx, rsp; StackCookie
0x180009d27  call    __security_check_cookie
0x180009d2c  add     rsp, 0C0h
0x180009d33  pop     r15
0x180009d35  pop     r14
0x180009d37  pop     r12
0x180009d39  pop     rdi
0x180009d3a  pop     rsi
0x180009d3b  pop     rbx
0x180009d3c  pop     rbp
0x180009d3d  retn
```
