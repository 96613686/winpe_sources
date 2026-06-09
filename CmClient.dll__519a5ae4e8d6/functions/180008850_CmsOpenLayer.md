# CmsOpenLayer

- ea: `0x180008850`
- end: `0x180008a82`
- name: `CmsOpenLayer`
- size: `562`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x180001574`
- `0x180001944`
- `0x180002a98`
- `0x1800066e4`
- `0x180008850`
- `0x18000d9e8`
- `0x18000db50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089fe`
- `RPCRT4!RpcBindingFree` at `0x180008900`
- `RPCRT4!RpcBindingFree` at `0x180008999`
- `RPCRT4!RpcBindingFree` at `0x180008a35`
- `RPCRT4!RpcBindingFree` at `0x180008900`
- `RPCRT4!RpcBindingFree` at `0x180008999`
- `RPCRT4!RpcBindingFree` at `0x180008a35`

## string_xrefs

- `0x1800088db`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x18000896a`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008a59`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsOpenLayer(_OWORD *a1, int a2, _QWORD *a3)
{
  char *v5; // rax
  _QWORD *v6; // r14
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ebx
  void *v10; // rcx
  RPC_BINDING_HANDLE v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  void *v14; // rcx
  void *v15; // rdi
  void **v16; // r15
  void *v17; // r12
  DWORD LastError; // esi
  void *v19; // rcx
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-40h]
  int v23; // [rsp+20h] [rbp-40h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-30h] BYREF
  __int64 v25; // [rsp+38h] [rbp-28h] BYREF
  void **v26; // [rsp+40h] [rbp-20h] BYREF
  RPC_BINDING_HANDLE v27; // [rsp+48h] [rbp-18h] BYREF
  char v28; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  _OWORD *v30; // [rsp+A0h] [rbp+40h] BYREF
  int v31; // [rsp+A8h] [rbp+48h] BYREF
  void *v32; // [rsp+B8h] [rbp+58h] BYREF

  v31 = a2;
  v30 = a1;
  if ( !a2 || a2 >= 33 )
  {
    v9 = -2147024809;
    v21 = 1562;
    goto LABEL_31;
  }
  v5 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v9 = -2147024882;
    v21 = 1567;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)v9,
      v22);
    return v9;
  }
  *(_QWORD *)v5 = 0;
  Binding = 0;
  *(GUID *)(v5 + 8) = GUID_NULL;
  *((_QWORD *)v5 + 3) = 0;
  v7 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x623,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v7,
      v22);
    if ( Binding )
      RpcBindingFree(&Binding);
    v10 = (void *)v6[3];
    if ( v10 )
      MIDL_user_free(v10);
LABEL_17:
    operator delete(v6, (const struct std::nothrow_t *)0x20);
    return v9;
  }
  v11 = Binding;
  v26 = &v32;
  v25 = 0;
  v27 = &v25;
  v32 = 0;
  v12 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,void * *,unsigned short * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,void * *,unsigned short * *>(
          v8,
          (unsigned int)&Binding,
          (unsigned int)&v30,
          (unsigned int)&v31,
          (__int64)&v27,
          (__int64)&v26);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x630,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v12,
      v23);
    if ( v32 )
      MIDL_user_free(v32);
    if ( v11 )
    {
      v27 = v11;
      RpcBindingFree(&v27);
    }
    v14 = (void *)v6[3];
    if ( v14 )
      MIDL_user_free(v14);
    v9 = v13;
    goto LABEL_17;
  }
  v15 = v32;
  v16 = (void **)(v6 + 3);
  v32 = 0;
  *v6 = v25;
  *(_OWORD *)(v6 + 1) = *a1;
  if ( v6 + 3 == (_QWORD *)&v28 )
  {
    if ( v15 )
      MIDL_user_free(v15);
  }
  else
  {
    v17 = *v16;
    if ( *v16 )
    {
      LastError = GetLastError();
      MIDL_user_free(v17);
      SetLastError(LastError);
    }
    *v16 = v15;
  }
  v19 = v32;
  *a3 = v6;
  if ( v19 )
    MIDL_user_free(v19);
  if ( v11 )
  {
    v27 = v11;
    RpcBindingFree(&v27);
  }
  return 0;
}

```

## disassembly

```asm
0x180008850  mov     [rsp-38h+arg_10], rbx
0x180008855  mov     [rsp-38h+arg_8], edx
0x180008859  mov     [rsp-38h+arg_0], rcx
0x18000885e  push    rbp
0x18000885f  push    rsi
0x180008860  push    rdi
0x180008861  push    r12
0x180008863  push    r13
0x180008865  push    r14
0x180008867  push    r15
0x180008869  mov     rbp, rsp
0x18000886c  sub     rsp, 60h
0x180008870  xor     r12d, r12d
0x180008873  mov     r13, r8
0x180008876  mov     rsi, rcx
0x180008879  test    edx, edx
0x18000887b  jz      loc_180008A4B
0x180008881  cmp     edx, 21h ; '!'
0x180008884  jge     loc_180008A4B
0x18000888a  lea     r15d, [r12+20h]
0x18000888f  mov     ecx, r15d; unsigned __int64
0x180008892  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008899  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000889e  mov     r14, rax
0x1800088a1  test    rax, rax
0x1800088a4  jz      loc_180008A3F
0x1800088aa  mov     [rax], r12
0x1800088ad  lea     rdx, [rbp+Binding]
0x1800088b1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800088b8  lea     rcx, qword_180012D10; IfSpec
0x1800088bf  mov     [rbp+Binding], r12
0x1800088c3  movdqu  xmmword ptr [rax+8], xmm0
0x1800088c8  mov     [rax+18h], r12
0x1800088cc  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x1800088d1  mov     ebx, eax
0x1800088d3  test    eax, eax
0x1800088d5  jns     short loc_18000891D
0x1800088d7  mov     rcx, [rbp+38h]; this
0x1800088db  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800088e2  mov     r9d, eax; char *
0x1800088e5  mov     edx, 623h; void *
0x1800088ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088ef  mov     rcx, [rbp+Binding]
0x1800088f3  test    rcx, rcx
0x1800088f6  jz      short loc_180008906
0x1800088f8  mov     [rbp+Binding], rcx
0x1800088fc  lea     rcx, [rbp+Binding]; Binding
0x180008900  call    cs:__imp_RpcBindingFree
0x180008906  mov     rcx, [r14+18h]; void *
0x18000890a  test    rcx, rcx
0x18000890d  jz      loc_1800089AF
0x180008913  call    MIDL_user_free
0x180008918  jmp     loc_1800089AF
0x18000891d  mov     rbx, [rbp+Binding]
0x180008921  lea     rax, [rbp+arg_18]
0x180008925  mov     [rbp+var_20], rax
0x180008929  lea     r9, [rbp+arg_8]
0x18000892d  lea     rax, [rbp+var_28]
0x180008931  mov     [rbp+var_28], r12
0x180008935  mov     [rbp+var_18], rax
0x180008939  lea     r8, [rbp+arg_0]
0x18000893d  lea     rax, [rbp+var_20]
0x180008941  mov     [rbp+arg_18], r12
0x180008945  mov     [rsp+60h+var_38], rax
0x18000894a  lea     rdx, [rbp+Binding]
0x18000894e  lea     rax, [rbp+var_18]
0x180008952  mov     [rbp+Binding], rbx
0x180008956  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000895b  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAXPEAPEAG@ZPEAXAEAPEAU1@AEAW42@PEAPEAXPEAPEAG@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAXPEAPEAG@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAPEAX$$QEAPEAPEAG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *,ushort * *),void *,_GUID * &,_CMS_CLIENT_ID &,void * *,ushort * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *,ushort * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,void * * &&,ushort * * &&)
0x180008960  mov     edi, eax
0x180008962  test    eax, eax
0x180008964  jns     short loc_1800089BF
0x180008966  mov     rcx, [rbp+38h]; this
0x18000896a  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008971  mov     r9d, eax; char *
0x180008974  mov     edx, 630h; void *
0x180008979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000897e  mov     rcx, [rbp+arg_18]; void *
0x180008982  test    rcx, rcx
0x180008985  jz      short loc_18000898C
0x180008987  call    MIDL_user_free
0x18000898c  test    rbx, rbx
0x18000898f  jz      short loc_18000899F
0x180008991  lea     rcx, [rbp+var_18]; Binding
0x180008995  mov     [rbp+var_18], rbx
0x180008999  call    cs:__imp_RpcBindingFree
0x18000899f  mov     rcx, [r14+18h]; void *
0x1800089a3  test    rcx, rcx
0x1800089a6  jz      short loc_1800089AD
0x1800089a8  call    MIDL_user_free
0x1800089ad  mov     ebx, edi
0x1800089af  mov     rdx, r15; struct std::nothrow_t *
0x1800089b2  mov     rcx, r14; void *
0x1800089b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800089ba  jmp     loc_180008A68
0x1800089bf  mov     rdi, [rbp+arg_18]
0x1800089c3  lea     r15, [r14+18h]
0x1800089c7  mov     rax, [rbp+var_28]
0x1800089cb  mov     [rbp+arg_18], r12
0x1800089cf  mov     [r14], rax
0x1800089d2  lea     rax, [rbp+var_10]
0x1800089d6  movups  xmm0, xmmword ptr [rsi]
0x1800089d9  movdqu  xmmword ptr [r14+8], xmm0
0x1800089df  cmp     r15, rax
0x1800089e2  jz      short loc_180008A09
0x1800089e4  mov     r12, [r15]
0x1800089e7  test    r12, r12
0x1800089ea  jz      short loc_180008A04
0x1800089ec  call    cs:__imp_GetLastError
0x1800089f2  mov     rcx, r12; void *
0x1800089f5  mov     esi, eax
0x1800089f7  call    MIDL_user_free
0x1800089fc  mov     ecx, esi; dwErrCode
0x1800089fe  call    cs:__imp_SetLastError
0x180008a04  mov     [r15], rdi
0x180008a07  jmp     short loc_180008A16
0x180008a09  test    rdi, rdi
0x180008a0c  jz      short loc_180008A16
0x180008a0e  mov     rcx, rdi; void *
0x180008a11  call    MIDL_user_free
0x180008a16  mov     rcx, [rbp+arg_18]; void *
0x180008a1a  mov     [r13+0], r14
0x180008a1e  test    rcx, rcx
0x180008a21  jz      short loc_180008A28
0x180008a23  call    MIDL_user_free
0x180008a28  test    rbx, rbx
0x180008a2b  jz      short loc_180008A3B
0x180008a2d  lea     rcx, [rbp+var_18]; Binding
0x180008a31  mov     [rbp+var_18], rbx
0x180008a35  call    cs:__imp_RpcBindingFree
0x180008a3b  xor     eax, eax
0x180008a3d  jmp     short loc_180008A6A
0x180008a3f  mov     ebx, 8007000Eh
0x180008a44  mov     edx, 61Fh
0x180008a49  jmp     short loc_180008A55
0x180008a4b  mov     ebx, 80070057h
0x180008a50  mov     edx, 61Ah; void *
0x180008a55  mov     rcx, [rbp+38h]; this
0x180008a59  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008a60  mov     r9d, ebx; char *
0x180008a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a68  mov     eax, ebx
0x180008a6a  mov     rbx, [rsp+60h+arg_10]
0x180008a72  add     rsp, 60h
0x180008a76  pop     r15
0x180008a78  pop     r14
0x180008a7a  pop     r13
0x180008a7c  pop     r12
0x180008a7e  pop     rdi
0x180008a7f  pop     rsi
0x180008a80  pop     rbp
0x180008a81  retn
```
