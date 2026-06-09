# NgcHandler::AuthenticatedReqResp(void *,_GUID const &,unsigned __int64,ushort const *,ushort const *,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180048850`
- end: `0x180048c0d`
- name: `?AuthenticatedReqResp@NgcHandler@@QEAAJPEAXAEBU_GUID@@_KPEBG33PEBEKPEAPEAEPEAK@Z`
- size: `957`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c9d8`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x18000c7e0`
- `0x18000d450`
- `0x180012190`
- `0x1800134a0`
- `0x180014350`
- `0x1800143c0`
- `0x180018194`
- `0x180023278`
- `0x18002c640`
- `0x18002d500`
- `0x180048850`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800488fa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800489f2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048b6f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048bd7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800488fa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800489f2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048b6f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048bd7`

## string_xrefs

- `0x180048949`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180048a31`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180048adc`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcHandler::AuthenticatedReqResp(
        __int64 (__fastcall **this)(__int128 *, __int64 **),
        void *a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        const unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  int v13; // eax
  int v14; // ebx
  bool v15; // zf
  __int64 (__fastcall *v17)(__int128 *, __int64 **); // rbx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rax
  _QWORD *v21; // r9
  int v22; // edi
  unsigned __int8 *v23; // rax
  unsigned __int8 *v24; // rbx
  int v25; // [rsp+20h] [rbp-C9h]
  int v26; // [rsp+20h] [rbp-C9h]
  _BYTE v27[8]; // [rsp+50h] [rbp-99h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-91h] BYREF
  size_t size; // [rsp+60h] [rbp-89h]
  __int64 v30; // [rsp+68h] [rbp-81h] BYREF
  int v31; // [rsp+70h] [rbp-79h] BYREF
  void *Src; // [rsp+78h] [rbp-71h] BYREF
  int v33[4]; // [rsp+80h] [rbp-69h] BYREF
  __int128 v34; // [rsp+90h] [rbp-59h] BYREF
  unsigned int *v35; // [rsp+A0h] [rbp-49h]
  _QWORD v36[2]; // [rsp+A8h] [rbp-41h] BYREF
  char v37; // [rsp+B8h] [rbp-31h]
  _QWORD v38[4]; // [rsp+C0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+3Fh]

  v30 = a4;
  *(_QWORD *)v33 = a8;
  v35 = a11;
  v27[0] = 0;
  v13 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v27, (unsigned int)a2);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v30) = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AACE3,
        0,
        0,
        (__int64)&v30);
    }
    v15 = v27[0] == 0;
    goto LABEL_5;
  }
  v28 = 0;
  v17 = *this;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v34 = (__int128)*a3;
  v14 = v17(&v34, &v28);
  if ( v14 < 0 )
  {
    v18 = 2167;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v14,
      v25);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v15 = v27[0] == 0;
LABEL_5:
    if ( !v15 )
      CoUninitialize();
    return (unsigned int)v14;
  }
  v31 = 0;
  v34 = xmmword_18008F2D8;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, int *))(*v28 + 88))(v28, &v34, &v31);
  if ( v14 < 0 )
  {
    v18 = 2173;
    goto LABEL_10;
  }
  if ( !v31 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v30) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&dword_1800AACBC,
        0,
        0,
        (__int64)&v30);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    if ( v27[0] )
      CoUninitialize();
    return 2147942487LL;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v38);
  v19 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(a6, a7, a5, (__int64)v38);
  v14 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v19,
      v25);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v38);
    goto LABEL_11;
  }
  Src = 0;
  LODWORD(size) = 0;
  v20 = *v28;
  v36[0] = &Src;
  v36[1] = 0;
  v37 = 1;
  v21 = v38;
  if ( v38[3] > 7u )
    v21 = (_QWORD *)v38[0];
  v34 = xmmword_18008F2D8;
  v26 = v33[0];
  v22 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, _QWORD *))(v20 + 424))(v28, &v34, v30, v21);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)v36);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v22,
      v26);
LABEL_33:
    wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&Src, 0);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    if ( v27[0] )
      CoUninitialize();
    return (unsigned int)v22;
  }
  v23 = (unsigned __int8 *)MIDL_user_allocate((unsigned int)size);
  v24 = v23;
  *(_QWORD *)v33 = v23;
  if ( v23 )
  {
    memcpy_0(v23, Src, (unsigned int)size);
    *(_QWORD *)v33 = 0;
    *a10 = v24;
    *v35 = size;
    std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(v33);
    goto LABEL_33;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(v30) = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800AAC37,
      0,
      0,
      (__int64)&v30);
  }
  std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(v33);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&Src, 0);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  if ( v27[0] )
    CoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x180048850  mov     [rsp-8+arg_8], rbx
0x180048855  push    rbp
0x180048856  push    rsi
0x180048857  push    rdi
0x180048858  push    r12
0x18004885a  push    r13
0x18004885c  push    r14
0x18004885e  push    r15
0x180048860  lea     rbp, [rsp-7]
0x180048865  sub     rsp, 0F0h
0x18004886c  mov     rax, cs:__security_cookie
0x180048873  xor     rax, rsp
0x180048876  mov     [rbp+37h+var_40], rax
0x18004887a  mov     [rsp+120h+var_B8], r9
0x18004887f  mov     rsi, r8
0x180048882  mov     rdi, rcx
0x180048885  mov     r14, [rbp+37h+arg_20]
0x180048889  mov     r15, [rbp+37h+arg_28]
0x18004888d  mov     r12, [rbp+37h+arg_30]
0x180048891  mov     rax, [rbp+37h+arg_38]
0x180048895  mov     qword ptr [rbp+37h+var_A0], rax
0x180048899  mov     r13, [rbp+37h+arg_48]
0x1800488a0  mov     rax, [rbp+37h+arg_50]
0x1800488a7  mov     [rbp+37h+var_80], rax
0x1800488ab  mov     [rsp+120h+var_D0], 0
0x1800488b0  lea     rcx, [rsp+120h+var_D0]; this
0x1800488b5  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800488ba  mov     ebx, eax
0x1800488bc  test    eax, eax
0x1800488be  jns     short loc_18004890D
0x1800488c0  mov     ecx, cs:dword_1800BE0B8
0x1800488c6  cmp     ecx, 2
0x1800488c9  jbe     short loc_1800488F3
0x1800488cb  mov     dword ptr [rsp+120h+var_B8], eax
0x1800488cf  lea     rax, [rsp+120h+var_B8]
0x1800488d4  mov     qword ptr [rsp+120h+var_100], rax
0x1800488d9  xor     r9d, r9d
0x1800488dc  xor     r8d, r8d
0x1800488df  lea     rdx, byte_1800AACE3
0x1800488e6  lea     rcx, dword_1800BE0B8
0x1800488ed  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800488f2  nop
0x1800488f3  cmp     [rsp+120h+var_D0], 0
0x1800488f8  jz      short loc_180048906
0x1800488fa  call    cs:__imp_CoUninitialize
0x180048901  nop     dword ptr [rax+rax+00h]
0x180048906  mov     eax, ebx
0x180048908  jmp     loc_180048BE5
0x18004890d  mov     [rsp+120h+var_C8], 0
0x180048916  mov     rbx, [rdi]
0x180048919  lea     rcx, [rsp+120h+var_C8]
0x18004891e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048923  movups  xmm0, xmmword ptr [rsi]
0x180048926  movdqu  [rbp+37h+var_90], xmm0
0x18004892b  lea     rdx, [rsp+120h+var_C8]
0x180048930  lea     rcx, [rbp+37h+var_90]
0x180048934  mov     rax, rbx
0x180048937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004893c  mov     ebx, eax
0x18004893e  xor     esi, esi
0x180048940  test    eax, eax
0x180048942  jns     short loc_18004896F
0x180048944  mov     edx, 877h; void *
0x180048949  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180048950  mov     r9d, ebx; char *
0x180048953  mov     rcx, [rbp+3Fh]; this
0x180048957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004895c  nop
0x18004895d  lea     rcx, [rsp+120h+var_C8]
0x180048962  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048967  nop
0x180048968  cmp     [rsp+120h+var_D0], sil
0x18004896d  jmp     short loc_1800488F8
0x18004896f  mov     [rbp+37h+var_B0], esi
0x180048972  mov     rcx, [rsp+120h+var_C8]
0x180048977  movups  xmm0, cs:xmmword_18008F2D8
0x18004897e  movdqu  [rbp+37h+var_90], xmm0
0x180048983  mov     rax, [rcx]
0x180048986  lea     r8, [rbp+37h+var_B0]
0x18004898a  lea     rdx, [rbp+37h+var_90]
0x18004898e  mov     rax, [rax+58h]
0x180048992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048997  mov     ebx, eax
0x180048999  test    eax, eax
0x18004899b  jns     short loc_1800489A4
0x18004899d  mov     edx, 87Dh
0x1800489a2  jmp     short loc_180048949
0x1800489a4  cmp     [rbp+37h+var_B0], esi
0x1800489a7  jnz     short loc_180048A08
0x1800489a9  mov     eax, cs:dword_1800BE0B8
0x1800489af  cmp     eax, 2
0x1800489b2  jbe     short loc_1800489E0
0x1800489b4  mov     dword ptr [rsp+120h+var_B8], 80070057h
0x1800489bc  lea     rax, [rsp+120h+var_B8]
0x1800489c1  mov     qword ptr [rsp+120h+var_100], rax
0x1800489c6  xor     r9d, r9d
0x1800489c9  xor     r8d, r8d
0x1800489cc  lea     rdx, dword_1800AACBC
0x1800489d3  lea     rcx, dword_1800BE0B8
0x1800489da  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800489df  nop
0x1800489e0  lea     rcx, [rsp+120h+var_C8]
0x1800489e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800489ea  nop
0x1800489eb  cmp     [rsp+120h+var_D0], sil
0x1800489f0  jz      short loc_1800489FE
0x1800489f2  call    cs:__imp_CoUninitialize
0x1800489f9  nop     dword ptr [rax+rax+00h]
0x1800489fe  mov     eax, 80070057h
0x180048a03  jmp     loc_180048BE5
0x180048a08  lea     rcx, [rbp+37h+var_60]
0x180048a0c  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180048a11  nop
0x180048a12  lea     r9, [rbp+37h+var_60]
0x180048a16  mov     r8, r14
0x180048a19  mov     rdx, r12
0x180048a1c  mov     rcx, r15; Src
0x180048a1f  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x180048a24  mov     ebx, eax
0x180048a26  test    eax, eax
0x180048a28  jns     short loc_180048A51
0x180048a2a  mov     rcx, [rbp+3Fh]; this
0x180048a2e  mov     r9d, eax; char *
0x180048a31  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180048a38  mov     edx, 88Fh; void *
0x180048a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048a42  nop
0x180048a43  lea     rcx, [rbp+37h+var_60]
0x180048a47  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180048a4c  jmp     loc_18004895D
0x180048a51  mov     [rbp+37h+Src], rsi
0x180048a55  mov     dword ptr [rsp+120h+size], esi
0x180048a59  mov     rcx, [rsp+120h+var_C8]
0x180048a5e  mov     rax, [rcx]
0x180048a61  lea     rdx, [rbp+37h+Src]
0x180048a65  mov     [rbp+37h+var_78], rdx
0x180048a69  mov     [rbp+37h+var_70], rsi
0x180048a6d  mov     [rbp+37h+var_68], 1
0x180048a71  lea     r9, [rbp+37h+var_60]
0x180048a75  cmp     [rbp+37h+var_48], 7
0x180048a7a  cmova   r9, [rbp+37h+var_60]
0x180048a7f  movups  xmm0, cs:xmmword_18008F2D8
0x180048a86  movdqu  [rbp+37h+var_90], xmm0
0x180048a8b  lea     rdx, [rsp+120h+size]
0x180048a90  mov     [rsp+120h+var_E8], rdx
0x180048a95  lea     rdx, [rbp+37h+var_70]
0x180048a99  mov     [rsp+120h+var_F0], rdx
0x180048a9e  mov     edx, [rbp+37h+arg_40]
0x180048aa4  mov     [rsp+120h+var_F8], edx
0x180048aa8  mov     rdx, qword ptr [rbp+37h+var_A0]
0x180048aac  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180048ab1  mov     r8, [rsp+120h+var_B8]
0x180048ab6  lea     rdx, [rbp+37h+var_90]
0x180048aba  mov     rax, [rax+1A8h]
0x180048ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ac6  mov     edi, eax
0x180048ac8  lea     rcx, [rbp+37h+var_78]
0x180048acc  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180048ad1  test    edi, edi
0x180048ad3  jns     short loc_180048AF2
0x180048ad5  mov     rcx, [rbp+3Fh]; this
0x180048ad9  mov     r9d, edi; char *
0x180048adc  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180048ae3  mov     edx, 89Bh; void *
0x180048ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048aed  jmp     loc_180048BAF
0x180048af2  mov     ecx, dword ptr [rsp+120h+size]; size
0x180048af6  call    MIDL_user_allocate
0x180048afb  mov     rbx, rax
0x180048afe  mov     qword ptr [rbp+37h+var_A0], rax
0x180048b02  test    rax, rax
0x180048b05  jnz     short loc_180048B82
0x180048b07  mov     eax, cs:dword_1800BE0B8
0x180048b0d  cmp     eax, 2
0x180048b10  jbe     short loc_180048B3D
0x180048b12  mov     dword ptr [rsp+120h+var_B8], 8007000Eh
0x180048b1a  lea     rax, [rsp+120h+var_B8]
0x180048b1f  mov     qword ptr [rsp+120h+var_100], rax
0x180048b24  xor     r9d, r9d
0x180048b27  xor     r8d, r8d
0x180048b2a  lea     rdx, byte_1800AAC37
0x180048b31  lea     rcx, dword_1800BE0B8
0x180048b38  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180048b3d  lea     rcx, [rbp+37h+var_A0]
0x180048b41  call    ??1?$unique_ptr@EU?$rpcmem_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_delete<uchar>>::~unique_ptr<uchar,rpcmem_delete<uchar>>(void)
0x180048b46  nop
0x180048b47  xor     edx, edx
0x180048b49  lea     rcx, [rbp+37h+Src]
0x180048b4d  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x180048b52  nop
0x180048b53  lea     rcx, [rbp+37h+var_60]
0x180048b57  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180048b5c  nop
0x180048b5d  lea     rcx, [rsp+120h+var_C8]
0x180048b62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048b67  nop
0x180048b68  cmp     [rsp+120h+var_D0], sil
0x180048b6d  jz      short loc_180048B7B
0x180048b6f  call    cs:__imp_CoUninitialize
0x180048b76  nop     dword ptr [rax+rax+00h]
0x180048b7b  mov     eax, 8007000Eh
0x180048b80  jmp     short loc_180048BE5
0x180048b82  mov     r8d, dword ptr [rsp+120h+size]; Size
0x180048b87  mov     rdx, [rbp+37h+Src]; Src
0x180048b8b  mov     rcx, rbx; void *
0x180048b8e  call    memcpy_0
0x180048b93  mov     qword ptr [rbp+37h+var_A0], rsi
0x180048b97  mov     [r13+0], rbx
0x180048b9b  mov     eax, dword ptr [rsp+120h+size]
0x180048b9f  mov     rcx, [rbp+37h+var_80]
0x180048ba3  mov     [rcx], eax
0x180048ba5  lea     rcx, [rbp+37h+var_A0]
0x180048ba9  call    ??1?$unique_ptr@EU?$rpcmem_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_delete<uchar>>::~unique_ptr<uchar,rpcmem_delete<uchar>>(void)
0x180048bae  nop
0x180048baf  xor     edx, edx
0x180048bb1  lea     rcx, [rbp+37h+Src]
0x180048bb5  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x180048bba  nop
0x180048bbb  lea     rcx, [rbp+37h+var_60]
0x180048bbf  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180048bc4  nop
0x180048bc5  lea     rcx, [rsp+120h+var_C8]
0x180048bca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048bcf  nop
0x180048bd0  cmp     [rsp+120h+var_D0], sil
0x180048bd5  jz      short loc_180048BE3
0x180048bd7  call    cs:__imp_CoUninitialize
0x180048bde  nop     dword ptr [rax+rax+00h]
0x180048be3  mov     eax, edi
0x180048be5  mov     rcx, [rbp+37h+var_40]
0x180048be9  xor     rcx, rsp; StackCookie
0x180048bec  call    __security_check_cookie
0x180048bf1  mov     rbx, [rsp+120h+arg_8]
0x180048bf9  add     rsp, 0F0h
0x180048c00  pop     r15
0x180048c02  pop     r14
0x180048c04  pop     r13
0x180048c06  pop     r12
0x180048c08  pop     rdi
0x180048c09  pop     rsi
0x180048c0a  pop     rbp
0x180048c0b  retn
```
