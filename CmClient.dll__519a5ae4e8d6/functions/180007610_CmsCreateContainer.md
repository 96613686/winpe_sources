# CmsCreateContainer

- ea: `0x180007610`
- end: `0x1800079c2`
- name: `CmsCreateContainer`
- size: `946`
- prototype: `__int64 __fastcall(_OWORD *, int, __int64, __int16 *, char, GUID **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001550`
- `0x180001574`
- `0x180002244`
- `0x180002b20`
- `0x180003e68`
- `0x1800066e4`
- `0x180007610`
- `0x18000d8e0`
- `0x18000d9e8`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x1800076ea`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800076ea`
- `RPCRT4!RpcBindingFree` at `0x18000784f`
- `RPCRT4!RpcBindingFree` at `0x180007918`
- `RPCRT4!RpcBindingFree` at `0x18000784f`
- `RPCRT4!RpcBindingFree` at `0x180007918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007957`

## string_xrefs

- `0x1800076b6`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x1800077dc`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x18000782a`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x1800078e2`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x18000798c`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCreateContainer(_OWORD *a1, int a2, __int64 a3, __int16 *a4, char a5, GUID **a6)
{
  GUID **v6; // r12
  HLOCAL v7; // rdi
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // ebx
  ULONG v14; // eax
  GUID *v15; // rax
  GUID *v16; // rsi
  int v17; // ecx
  int v18; // ecx
  unsigned int v19; // edi
  __int64 v20; // rdx
  int v21; // eax
  int v22; // ecx
  unsigned int v23; // r14d
  int v24; // eax
  GUID v25; // xmm0
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // [rsp+20h] [rbp-89h]
  int v29; // [rsp+20h] [rbp-89h]
  HLOCAL hMem; // [rsp+50h] [rbp-59h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-51h] BYREF
  __int64 *v32; // [rsp+60h] [rbp-49h] BYREF
  ULONG v33; // [rsp+68h] [rbp-41h] BYREF
  int v34; // [rsp+70h] [rbp-39h] BYREF
  __int64 v35; // [rsp+78h] [rbp-31h] BYREF
  __int64 *v36; // [rsp+80h] [rbp-29h] BYREF
  __int64 *v37; // [rsp+88h] [rbp-21h] BYREF
  int v38[2]; // [rsp+90h] [rbp-19h] BYREF
  _OWORD *v39; // [rsp+98h] [rbp-11h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]

  v6 = a6;
  v39 = a1;
  v7 = a4;
  v34 = a2;
  *(_QWORD *)v38 = a3;
  if ( !a1 )
  {
    v10 = 46;
LABEL_32:
    v19 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x80070057LL,
      v28);
    return v19;
  }
  if ( !a2 || a2 >= 33 )
  {
    v10 = 47;
    goto LABEL_32;
  }
  if ( !a3 )
  {
    v10 = 48;
    goto LABEL_32;
  }
  if ( !a6 )
  {
    v10 = 49;
    goto LABEL_32;
  }
  hMem = 0;
  if ( a4 )
  {
    if ( a4[1] >= 0 )
    {
      v11 = Csl::DuplicateSecurityDescriptor(a4);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
          (const char *)(unsigned int)v11,
          v28);
        return v12;
      }
      v7 = hMem;
    }
    v14 = RtlLengthSecurityDescriptor(v7);
  }
  else
  {
    v7 = 0;
    v14 = 0;
  }
  v33 = v14;
  v15 = (GUID *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    hMem = 0;
    v19 = -2147024882;
    v20 = 92;
    goto LABEL_22;
  }
  v15[1].Data1 = 0;
  hMem = v15;
  *v15 = GUID_NULL;
  *(_DWORD *)&v15[1].Data2 = 0;
  *(_QWORD *)v15[1].Data4 = 0;
  *(_QWORD *)v15[2].Data4 = 0;
  *(_QWORD *)&v15[2].Data1 = 0;
  v35 = 0;
  v40 = 0;
  v17 = *(_DWORD *)(a3 + 112);
  if ( !v17 )
    goto LABEL_29;
  v18 = v17 - 1;
  if ( !v18 )
  {
    v32 = 0;
    v21 = Container::Manager::Rpc::ConnectToServer(qword_180012D10);
    v23 = v21;
    if ( v21 >= 0 )
    {
      v36 = (__int64 *)v7;
      Binding = &v35;
      v37 = &v40;
      v24 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,unsigned char *,unsigned long,unsigned long,_WNF_STATE_NAME *,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,unsigned char *,unsigned long &,unsigned long &,_WNF_STATE_NAME *,void * *>(
              v22,
              (unsigned int)&v32,
              (unsigned int)&v39,
              (unsigned int)&v34,
              (__int64)v38,
              (__int64)&v36,
              (__int64)&v33,
              (__int64)&a5,
              (__int64)&v37,
              (__int64)&Binding);
      v23 = v24;
      if ( v24 >= 0 )
        goto LABEL_28;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v24,
        v29);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v21,
        v28);
    }
    wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(&hMem);
    return v23;
  }
  if ( v18 != 1 )
  {
LABEL_29:
    v19 = -2147024809;
    v20 = 149;
    goto LABEL_22;
  }
  v37 = (__int64 *)v7;
  v32 = &v35;
  v36 = &v40;
  Binding = **(RPC_BINDING_HANDLE **)(a3 + 120);
  v19 = Container::Manager::Rpc::InvokeStubFunction<long (*)(_GUID *,enum _CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,void *,unsigned char *,unsigned long,unsigned long,_WNF_STATE_NAME *,void * *),_GUID * &,enum _CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,void *,unsigned char *,unsigned long &,unsigned long &,_WNF_STATE_NAME *,void * *>(
          (_DWORD)Binding,
          (unsigned int)&v39,
          (unsigned int)&v34,
          (unsigned int)v38,
          (__int64)&Binding,
          (__int64)&v37,
          (__int64)&v33,
          (__int64)&a5,
          (__int64)&v36,
          (__int64)&v32);
  if ( (v19 & 0x80000000) == 0 )
  {
LABEL_28:
    v25 = (GUID)*a1;
    v26 = v35;
    v16[1].Data1 = *(_DWORD *)(a3 + 12);
    *v16 = v25;
    v27 = v40;
    *(_QWORD *)v16[1].Data4 = v26;
    *(_QWORD *)&v16[2].Data1 = v27;
    *v6 = v16;
    hMem = 0;
    wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(&hMem);
    return 0;
  }
  v20 = 141;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)v19,
    v28);
  wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(&hMem);
  return v19;
}

```

## disassembly

```asm
0x180007610  push    rbp
0x180007612  push    rbx
0x180007613  push    rsi
0x180007614  push    rdi
0x180007615  push    r12
0x180007617  push    r13
0x180007619  push    r14
0x18000761b  push    r15
0x18000761d  lea     rbp, [rsp-0Fh]
0x180007622  sub     rsp, 0B8h
0x180007629  mov     rax, cs:__security_cookie
0x180007630  xor     rax, rsp
0x180007633  mov     [rbp+47h+var_48], rax
0x180007637  mov     r12, [rbp+47h+arg_28]
0x18000763b  xor     r14d, r14d
0x18000763e  mov     [rbp+47h+var_58], rcx
0x180007642  mov     rdi, r9
0x180007645  mov     [rbp+47h+var_80], edx
0x180007648  mov     r15, r8
0x18000764b  mov     qword ptr [rbp+47h+var_60], r8
0x18000764f  mov     r13, rcx
0x180007652  test    rcx, rcx
0x180007655  jnz     short loc_18000765F
0x180007657  lea     edx, [rcx+2Eh]
0x18000765a  jmp     loc_180007988
0x18000765f  test    edx, edx
0x180007661  jz      loc_180007983
0x180007667  cmp     edx, 21h ; '!'
0x18000766a  jge     loc_180007983
0x180007670  test    r15, r15
0x180007673  jnz     short loc_18000767E
0x180007675  lea     edx, [r15+30h]
0x180007679  jmp     loc_180007988
0x18000767e  test    r12, r12
0x180007681  jnz     short loc_18000768D
0x180007683  lea     edx, [r12+31h]
0x180007688  jmp     loc_180007988
0x18000768d  mov     rbx, r14
0x180007690  mov     [rbp+47h+hMem], rbx
0x180007694  test    r9, r9
0x180007697  jz      short loc_1800076F2
0x180007699  cmp     [r9+2], r14w
0x18000769e  jl      short loc_1800076E7
0x1800076a0  lea     rdx, [rbp+47h+hMem]
0x1800076a4  mov     rcx, r9; Src
0x1800076a7  call    ?DuplicateSecurityDescriptor@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Csl::DuplicateSecurityDescriptor(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x1800076ac  mov     ebx, eax
0x1800076ae  test    eax, eax
0x1800076b0  jns     short loc_1800076E0
0x1800076b2  mov     rcx, [rbp+4Fh]; this
0x1800076b6  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800076bd  mov     r9d, eax; char *
0x1800076c0  mov     edx, 49h ; 'I'; void *
0x1800076c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076ca  mov     rcx, [rbp+47h+hMem]; hMem
0x1800076ce  test    rcx, rcx
0x1800076d1  jz      short loc_1800076D9
0x1800076d3  call    cs:__imp_LocalFree
0x1800076d9  mov     eax, ebx
0x1800076db  jmp     loc_1800079A2
0x1800076e0  mov     rbx, [rbp+47h+hMem]
0x1800076e4  mov     rdi, rbx
0x1800076e7  mov     rcx, rdi; SecurityDescriptor
0x1800076ea  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800076f0  jmp     short loc_1800076F8
0x1800076f2  mov     rdi, r14
0x1800076f5  mov     eax, r14d
0x1800076f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800076ff  mov     [rbp+47h+var_88], eax
0x180007702  mov     ecx, 30h ; '0'; unsigned __int64
0x180007707  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000770c  mov     rsi, rax
0x18000770f  test    rax, rax
0x180007712  jz      loc_180007970
0x180007718  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000771f  mov     [rax+10h], r14d
0x180007723  mov     [rbp+47h+hMem], rsi
0x180007727  movdqu  xmmword ptr [rax], xmm0
0x18000772b  mov     [rax+14h], r14d
0x18000772f  mov     [rax+18h], r14
0x180007733  mov     [rax+28h], r14
0x180007737  xor     eax, eax
0x180007739  mov     [rsi+20h], rax
0x18000773d  mov     [rbp+47h+var_78], r14
0x180007741  mov     [rbp+47h+var_50], r14
0x180007745  mov     ecx, [r15+70h]
0x180007749  test    ecx, ecx
0x18000774b  jz      loc_180007961
0x180007751  sub     ecx, 1
0x180007754  jz      loc_18000780B
0x18000775a  cmp     ecx, 1
0x18000775d  jnz     loc_180007961
0x180007763  lea     rax, [rbp+47h+var_78]
0x180007767  mov     [rbp+47h+var_68], rdi
0x18000776b  mov     [rbp+47h+var_90], rax
0x18000776f  lea     r9, [rbp+47h+var_60]
0x180007773  lea     rax, [rbp+47h+var_50]
0x180007777  mov     [rbp+47h+var_70], rax
0x18000777b  lea     r8, [rbp+47h+var_80]
0x18000777f  mov     rax, [r15+78h]
0x180007783  lea     rdx, [rbp+47h+var_58]
0x180007787  mov     rcx, [rax]
0x18000778a  lea     rax, [rbp+47h+var_90]
0x18000778e  mov     [rsp+0F0h+var_A8], rax
0x180007793  lea     rax, [rbp+47h+var_70]
0x180007797  mov     [rsp+0F0h+var_B0], rax
0x18000779c  lea     rax, [rbp+47h+arg_20]
0x1800077a0  mov     [rsp+0F0h+var_B8], rax
0x1800077a5  lea     rax, [rbp+47h+var_88]
0x1800077a9  mov     [rsp+0F0h+var_C0], rax
0x1800077ae  lea     rax, [rbp+47h+var_68]
0x1800077b2  mov     [rsp+0F0h+var_C8], rax
0x1800077b7  lea     rax, [rbp+47h+Binding]
0x1800077bb  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800077c0  mov     [rbp+47h+Binding], rcx
0x1800077c4  call    ??$InvokeStubFunction@P6AJPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAXPEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@ZAEAPEAU1@AEAW42@AEAPEAU3@PEAXPEAEAEAKAEAKPEAU4@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAXPEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@ZAEAPEAU3@AEAW44@AEAPEAU5@$$QEAPEAX$$QEAPEAEAEAKAEAK$$QEAPEAU6@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,void *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,void *,uchar *,ulong &,ulong &,_WNF_STATE_NAME *,void * *>(long (*)(_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,void *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,void * &&,uchar * &&,ulong &,ulong &,_WNF_STATE_NAME * &&,void * * &&)
0x1800077c9  mov     edi, eax
0x1800077cb  test    eax, eax
0x1800077cd  jns     loc_18000791E
0x1800077d3  mov     edx, 8Dh; void *
0x1800077d8  mov     rcx, [rbp+4Fh]; this
0x1800077dc  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800077e3  mov     r9d, edi; char *
0x1800077e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077eb  lea     rcx, [rbp+47h+hMem]
0x1800077ef  call    ??1?$unique_ptr@VOutOfProcClientContainerHandle@Client@Manager@Container@@U?$default_delete@VOutOfProcClientContainerHandle@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(void)
0x1800077f4  test    rbx, rbx
0x1800077f7  jz      loc_1800079A0
0x1800077fd  mov     rcx, rbx; hMem
0x180007800  call    cs:__imp_LocalFree
0x180007806  jmp     loc_1800079A0
0x18000780b  lea     rdx, [rbp+47h+var_90]
0x18000780f  mov     [rbp+47h+var_90], r14
0x180007813  lea     rcx, qword_180012D10; IfSpec
0x18000781a  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000781f  mov     r14d, eax
0x180007822  test    eax, eax
0x180007824  jns     short loc_180007874
0x180007826  mov     rcx, [rbp+4Fh]; this
0x18000782a  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007831  mov     r9d, eax; char *
0x180007834  mov     edx, 6Ch ; 'l'; void *
0x180007839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000783e  mov     rcx, [rbp+47h+var_90]
0x180007842  test    rcx, rcx
0x180007845  jz      short loc_180007855
0x180007847  mov     [rbp+47h+Binding], rcx
0x18000784b  lea     rcx, [rbp+47h+Binding]; Binding
0x18000784f  call    cs:__imp_RpcBindingFree
0x180007855  lea     rcx, [rbp+47h+hMem]
0x180007859  call    ??1?$unique_ptr@VOutOfProcClientContainerHandle@Client@Manager@Container@@U?$default_delete@VOutOfProcClientContainerHandle@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(void)
0x18000785e  test    rbx, rbx
0x180007861  jz      short loc_18000786C
0x180007863  mov     rcx, rbx; hMem
0x180007866  call    cs:__imp_LocalFree
0x18000786c  mov     eax, r14d
0x18000786f  jmp     loc_1800079A2
0x180007874  lea     rax, [rbp+47h+var_78]
0x180007878  mov     [rbp+47h+var_70], rdi
0x18000787c  mov     rdi, [rbp+47h+var_90]
0x180007880  lea     r9, [rbp+47h+var_80]
0x180007884  mov     [rbp+47h+Binding], rax
0x180007888  lea     r8, [rbp+47h+var_58]
0x18000788c  lea     rax, [rbp+47h+var_50]
0x180007890  mov     [rbp+47h+var_90], rdi
0x180007894  mov     [rbp+47h+var_68], rax
0x180007898  lea     rdx, [rbp+47h+var_90]
0x18000789c  lea     rax, [rbp+47h+Binding]
0x1800078a0  mov     [rsp+0F0h+var_A8], rax
0x1800078a5  lea     rax, [rbp+47h+var_68]
0x1800078a9  mov     [rsp+0F0h+var_B0], rax
0x1800078ae  lea     rax, [rbp+47h+arg_20]
0x1800078b2  mov     [rsp+0F0h+var_B8], rax
0x1800078b7  lea     rax, [rbp+47h+var_88]
0x1800078bb  mov     [rsp+0F0h+var_C0], rax
0x1800078c0  lea     rax, [rbp+47h+var_70]
0x1800078c4  mov     [rsp+0F0h+var_C8], rax
0x1800078c9  lea     rax, [rbp+47h+var_60]
0x1800078cd  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800078d2  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@AEAPEAU3@PEAEAEAKAEAKPEAU4@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAU_CMS_CONTAINER_PROPERTIES@@PEAEKKPEAU_WNF_STATE_NAME@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@AEAPEAU5@$$QEAPEAEAEAKAEAK$$QEAPEAU6@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,uchar *,ulong &,ulong &,_WNF_STATE_NAME *,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,_CMS_CONTAINER_PROPERTIES *,uchar *,ulong,ulong,_WNF_STATE_NAME *,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,_CMS_CONTAINER_PROPERTIES * &,uchar * &&,ulong &,ulong &,_WNF_STATE_NAME * &&,void * * &&)
0x1800078d7  mov     r14d, eax
0x1800078da  test    eax, eax
0x1800078dc  jns     short loc_180007908
0x1800078de  mov     rcx, [rbp+4Fh]; this
0x1800078e2  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800078e9  mov     r9d, eax; char *
0x1800078ec  mov     edx, 78h ; 'x'; void *
0x1800078f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078f6  test    rdi, rdi
0x1800078f9  jz      loc_180007855
0x1800078ff  mov     [rbp+47h+Binding], rdi
0x180007903  jmp     loc_18000784B
0x180007908  xor     r14d, r14d
0x18000790b  test    rdi, rdi
0x18000790e  jz      short loc_18000791E
0x180007910  lea     rcx, [rbp+47h+Binding]; Binding
0x180007914  mov     [rbp+47h+Binding], rdi
0x180007918  call    cs:__imp_RpcBindingFree
0x18000791e  mov     eax, [r15+0Ch]
0x180007922  movups  xmm0, xmmword ptr [r13+0]
0x180007927  mov     rcx, [rbp+47h+var_78]
0x18000792b  mov     [rsi+10h], eax
0x18000792e  movdqu  xmmword ptr [rsi], xmm0
0x180007932  mov     rax, [rbp+47h+var_50]
0x180007936  mov     [rsi+18h], rcx
0x18000793a  lea     rcx, [rbp+47h+hMem]
0x18000793e  mov     [rsi+20h], rax
0x180007942  mov     [r12], rsi
0x180007946  mov     [rbp+47h+hMem], r14
0x18000794a  call    ??1?$unique_ptr@VOutOfProcClientContainerHandle@Client@Manager@Container@@U?$default_delete@VOutOfProcClientContainerHandle@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(void)
0x18000794f  test    rbx, rbx
0x180007952  jz      short loc_18000795D
0x180007954  mov     rcx, rbx; hMem
0x180007957  call    cs:__imp_LocalFree
0x18000795d  xor     eax, eax
0x18000795f  jmp     short loc_1800079A2
0x180007961  mov     edi, 80070057h
0x180007966  mov     edx, 95h
0x18000796b  jmp     loc_1800077D8
0x180007970  mov     [rbp+47h+hMem], r14
0x180007974  mov     edi, 8007000Eh
0x180007979  mov     edx, 5Ch ; '\'
0x18000797e  jmp     loc_1800077D8
0x180007983  mov     edx, 2Fh ; '/'; void *
0x180007988  mov     rcx, [rbp+4Fh]; this
0x18000798c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007993  mov     edi, 80070057h
0x180007998  mov     r9d, edi; char *
0x18000799b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079a0  mov     eax, edi
0x1800079a2  mov     rcx, [rbp+47h+var_48]
0x1800079a6  xor     rcx, rsp; StackCookie
0x1800079a9  call    __security_check_cookie
0x1800079ae  add     rsp, 0B8h
0x1800079b5  pop     r15
0x1800079b7  pop     r14
0x1800079b9  pop     r13
0x1800079bb  pop     r12
0x1800079bd  pop     rdi
0x1800079be  pop     rsi
0x1800079bf  pop     rbx
0x1800079c0  pop     rbp
0x1800079c1  retn
```
