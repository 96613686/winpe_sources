# SendRequestAndWaitForResponse(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ProxySettings const &,HttpRequest &)

- ea: `0x18000655c`
- end: `0x18000697e`
- name: `?SendRequestAndWaitForResponse@@YA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z`
- size: `1058`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005914`
- `0x180006cec`
- `0x18005c424`

## callees

- `0x1800044d4`
- `0x1800061e0`
- `0x18000655c`
- `0x180006b08`
- `0x1800073e8`
- `0x1800077c0`
- `0x1800089f4`
- `0x18000a98c`
- `0x180012dc0`
- `0x180036394`
- `0x1800593bc`
- `0x180069b50`
- `0x18006bda0`
- `0x18006e46c`
- `0x180075e60`
- `0x1800a8918`
- `0x1800a8a98`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180006834`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180006883`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180006834`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180006883`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800067da`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000683b`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800067da`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000683b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000681f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000686e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000681f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000686e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000684d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000684d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800066a9`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800066a9`

## string_xrefs

- `0x1800067f7`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SendRequestAndWaitForResponse(__int64 a1, __int64 a2, char *a3, WCHAR *a4)
{
  WCHAR *v4; // rsi
  __int64 v6; // r14
  char v7; // bl
  char v8; // r15
  char v9; // r12
  __int64 ConfigUrl; // rax
  __int64 v11; // rax
  int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  char IsEnabled; // al
  __int128 *v19; // rcx
  char v20; // al
  DWORD v21; // edx
  __int64 v22; // rax
  wil *v23; // rcx
  __int64 v24; // rax
  wil *v26; // rcx
  unsigned int v27; // ebx
  _QWORD *v28; // rax
  _QWORD *v29; // rdx
  const char *v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // rdx
  const char *v33; // rax
  const void *v34; // rax
  wil *v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // r9
  unsigned __int16 *v38; // rdx
  const char *v39; // rax
  unsigned __int16 *v40; // rax
  const char *v41; // rdx
  const void *v42; // rax
  unsigned int v43; // eax
  const char *v44; // r9
  const char *v45; // rax
  const char *v46; // rax
  int v47; // [rsp+20h] [rbp-188h]
  int v48; // [rsp+20h] [rbp-188h]
  int v49; // [rsp+20h] [rbp-188h]
  unsigned __int16 *v51; // [rsp+48h] [rbp-160h]
  int v53; // [rsp+58h] [rbp-150h]
  __int128 v54; // [rsp+60h] [rbp-148h] BYREF
  WCHAR *v55; // [rsp+70h] [rbp-138h]
  __int128 v56; // [rsp+80h] [rbp-128h] BYREF
  int v57; // [rsp+90h] [rbp-118h]
  __int64 v58; // [rsp+A0h] [rbp-108h]
  unsigned __int16 *v59; // [rsp+B0h] [rbp-F8h] BYREF
  unsigned __int16 *v60; // [rsp+B8h] [rbp-F0h]
  _BYTE v61[16]; // [rsp+C8h] [rbp-E0h] BYREF
  _BYTE v62[24]; // [rsp+D8h] [rbp-D0h] BYREF
  _BYTE v63[40]; // [rsp+F0h] [rbp-B8h] BYREF
  void **v64; // [rsp+118h] [rbp-90h] BYREF
  unsigned __int16 *v65[4]; // [rsp+140h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v4 = a4;
  v6 = a1;
  v58 = a1;
  v55 = a4;
  v57 = 0;
  v7 = *a3;
  v8 = a3[1];
  v9 = a3[2];
  std::vector<std::wstring>::vector<std::wstring>(&v59, a3 + 8);
  std::wstring::wstring(v65, a3 + 32);
  *(_OWORD *)v6 = 0;
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  *(_DWORD *)(v6 + 32) = 0;
  *(_QWORD *)(v6 + 40) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  *(_QWORD *)(v6 + 48) = 0;
  *(_QWORD *)(v6 + 56) = 0;
  *(_QWORD *)(v6 + 64) = 0;
  v57 = 1;
  if ( v7 && (v59 != v60 || v9) )
  {
    if ( v9 )
    {
      ConfigUrl = ProxySettings::GetConfigUrl(a3);
      if ( *(_QWORD *)(ConfigUrl + 24) > 7u )
        ConfigUrl = *(_QWORD *)ConfigUrl;
      HttpRequest::Open(v4, 0, v8, 0, 0, (const unsigned __int16 *)ConfigUrl);
      try
      {
        v11 = HttpRequest::Send(v4, v63);
        HttpResponse::operator=(v6, v11);
        HttpResponse::~HttpResponse((HttpResponse *)v63);
      }
      catch ( wil::ResultException )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
        {
          v27 = wil::ResultFromCaughtException(v26);
          if ( v27 == -2147012867 )
            v27 = -2143309801;
          v28 = (_QWORD *)ProxySettings::GetConfigUrl(a3);
          v29 = v28;
          if ( v28[3] > 7u )
            v29 = (_QWORD *)*v28;
          v30 = (const char *)a2;
          if ( *(_QWORD *)(a2 + 24) > 7u )
            v30 = *(const char **)a2;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xE2,
            (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
            (const char *)v27,
            (int)"Failed to connect to %ws with proxy config url %ws",
            v30,
            v29);
          if ( v27 == -2143309801 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE5,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
              (const char *)0x803FB017LL,
              v47);
        }
        else
        {
          v31 = (_QWORD *)ProxySettings::GetConfigUrl(a3);
          v32 = v31;
          if ( v31[3] > 7u )
            v32 = (_QWORD *)*v31;
          v33 = (const char *)a2;
          if ( *(_QWORD *)(a2 + 24) > 7u )
            v33 = *(const char **)a2;
          wil::details::in1diag3::Log_CaughtExceptionMsg(
            retaddr,
            (void *)0xEA,
            (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
            "Failed to connect to %ws with proxy config url %ws",
            v33,
            v32);
        }
        throw;
      }
      goto LABEL_29;
    }
    v56 = 0;
    __ExceptionPtrCreate(&v56);
    v12 = 0;
    v53 = 0;
    v13 = v59;
    v14 = v60;
    *(_QWORD *)&v54 = v60;
    while ( 2 )
    {
      v51 = v13;
      if ( v13 != v14 )
      {
        v15 = (const unsigned __int16 *)v65;
        if ( v65[3] > (unsigned __int16 *)7 )
          v15 = v65[0];
        if ( *((_QWORD *)v13 + 3) > 7u )
          v13 = *(unsigned __int16 **)v13;
        HttpRequest::Open(v4, 3u, 0, v13, v15, 0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
        {
          try
          {
            v16 = HttpRequest::Send(v4, v63);
            HttpResponse::operator=(v6, v16);
            HttpResponse::~HttpResponse((HttpResponse *)v63);
            std::exception_ptr::operator=(&v56);
            v12 = 0;
          }
          catch ( wil::ResultException )
          {
            v34 = (const void *)std::current_exception(v61);
            __ExceptionPtrAssign(&v56, v34);
            __ExceptionPtrDestroy(v61);
            v36 = wil::ResultFromCaughtException(v35);
            v37 = v36;
            if ( v36 == -2147012867 )
              v37 = 2151657495LL;
            v53 = v37;
            v38 = v51;
            if ( *((_QWORD *)v51 + 3) > 7u )
              v38 = *(unsigned __int16 **)v51;
            v39 = (const char *)a2;
            if ( *(_QWORD *)(a2 + 24) > 7u )
              v39 = *(const char **)a2;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x109,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
              (const char *)v37,
              (int)"Failed to connect to %ws with proxy %ws",
              v39,
              v38);
            v13 = v51 + 16;
            v12 = v53;
            v14 = (unsigned __int16 *)v54;
            v6 = v58;
            v4 = v55;
            continue;
          }
        }
        else
        {
          try
          {
            v17 = HttpRequest::Send(v4, v63);
            HttpResponse::operator=(v6, v17);
            HttpResponse::~HttpResponse((HttpResponse *)v63);
            std::exception_ptr::operator=(&v56);
          }
          catch ( wil::ResultException )
          {
            v40 = v51;
            if ( *((_QWORD *)v51 + 3) > 7u )
              v40 = *(unsigned __int16 **)v51;
            v41 = (const char *)a2;
            if ( *(_QWORD *)(a2 + 24) > 7u )
              v41 = *(const char **)a2;
            wil::details::in1diag3::Log_CaughtExceptionMsg(
              retaddr,
              (void *)0x116,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
              "Failed to connect to %ws with proxy %ws",
              v41,
              v40);
            v42 = (const void *)std::current_exception(v62);
            __ExceptionPtrAssign(&v56, v42);
            __ExceptionPtrDestroy(v62);
            v13 = v51 + 16;
            v12 = v53;
            v14 = (unsigned __int16 *)v54;
            v6 = v58;
            v4 = v55;
            continue;
          }
        }
      }
      break;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl);
    v19 = &v56;
    if ( IsEnabled )
    {
      if ( !__ExceptionPtrToBool(&v56) )
      {
LABEL_22:
        __ExceptionPtrDestroy(&v56);
        goto LABEL_29;
      }
      if ( v12 == -2143309801 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          (const char *)0x803FB017LL,
          v49);
      v54 = 0;
      __ExceptionPtrCopy(&v54, &v56);
      v55 = (WCHAR *)&v54;
      __ExceptionPtrRethrow(&v54);
    }
    if ( !__ExceptionPtrToBool(v19) )
      goto LABEL_22;
    v54 = 0;
    __ExceptionPtrCopy(&v54, &v56);
    v55 = (WCHAR *)&v54;
    __ExceptionPtrRethrow(&v54);
  }
  if ( v8 || (v20 = IsDeviceXbox(), v21 = 1, v20) )
    v21 = 0;
  HttpRequest::Open(v4, v21, v8, 0, 0, 0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
  {
    try
    {
      v22 = HttpRequest::Send(v4, v63);
      HttpResponse::operator=(v6, v22);
      HttpResponse::~HttpResponse((HttpResponse *)v63);
    }
    catch ( wil::ResultException )
    {
      v43 = wil::ResultFromCaughtException(v23);
      v44 = (const char *)v43;
      if ( v8 && v43 == -2147012867 )
      {
        v45 = (const char *)a2;
        if ( *(_QWORD *)(a2 + 24) > 7u )
          v45 = *(const char **)a2;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xC3,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          (const char *)0x803FB017LL,
          (int)"Failed to connect to %ws with auto-proxy",
          v45);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          (const char *)0x803FB017LL,
          v48);
      }
      v46 = (const char *)a2;
      if ( *(_QWORD *)(a2 + 24) > 7u )
        v46 = *(const char **)a2;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v44,
        (int)"Failed to connect to %ws",
        v46);
      throw;
    }
  }
  else
  {
    v24 = HttpRequest::Send(v4, v63);
    HttpResponse::operator=(v6, v24);
    v64 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(&v64);
    ContentIdString::~ContentIdString((ContentIdString *)v63);
  }
LABEL_29:
  std::wstring::_Tidy_deallocate(v65);
  std::vector<std::wstring>::_Tidy(&v59);
  return v6;
}

```

## disassembly

```asm
0x18000655c  push    rbx
0x18000655e  push    rsi
0x18000655f  push    rdi
0x180006560  push    r12
0x180006562  push    r13
0x180006564  push    r14
0x180006566  push    r15
0x180006568  sub     rsp, 170h
0x18000656f  mov     rax, cs:__security_cookie
0x180006576  xor     rax, rsp
0x180006579  mov     [rsp+1A8h+var_48], rax
0x180006581  mov     rsi, r9
0x180006584  mov     r13, r8
0x180006587  mov     r14, rcx
0x18000658a  mov     [rsp+1A8h+var_108], rcx
0x180006592  mov     [rsp+1A8h+var_158], rdx
0x180006597  mov     [rsp+1A8h+var_160], r8
0x18000659c  mov     [rsp+1A8h+var_138], r9
0x1800065a1  xor     edi, edi
0x1800065a3  mov     [rsp+1A8h+var_118], edi
0x1800065aa  mov     bl, [r8]
0x1800065ad  mov     r15b, [r8+1]
0x1800065b1  mov     r12b, [r8+2]
0x1800065b5  lea     rdx, [r8+8]
0x1800065b9  lea     rcx, [rsp+1A8h+var_F8]
0x1800065c1  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800065c6  nop
0x1800065c7  lea     rdx, [r13+20h]
0x1800065cb  lea     rcx, [rsp+1A8h+var_68]
0x1800065d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800065d8  nop
0x1800065d9  xorps   xmm0, xmm0
0x1800065dc  movups  xmmword ptr [r14], xmm0
0x1800065e0  mov     [r14+10h], rdi
0x1800065e4  mov     qword ptr [r14+18h], 7
0x1800065ec  mov     [r14], di
0x1800065f0  mov     [r14+20h], edi
0x1800065f4  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x1800065fb  mov     [r14+28h], rax
0x1800065ff  mov     [r14+30h], rdi
0x180006603  mov     [r14+38h], rdi
0x180006607  mov     [r14+40h], rdi
0x18000660b  mov     [rsp+1A8h+var_118], 1
0x180006616  test    bl, bl
0x180006618  jz      loc_18000688A
0x18000661e  mov     rax, [rsp+1A8h+var_F0]
0x180006626  cmp     [rsp+1A8h+var_F8], rax
0x18000662e  jnz     short loc_180006639
0x180006630  test    r12b, r12b
0x180006633  jz      loc_18000688A
0x180006639  test    r12b, r12b
0x18000663c  jz      short loc_180006698
0x18000663e  mov     rcx, r13
0x180006641  call    ?GetConfigUrl@ProxySettings@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProxySettings::GetConfigUrl(void)
0x180006646  cmp     qword ptr [rax+18h], 7
0x18000664b  jbe     short loc_180006650
0x18000664d  mov     rax, [rax]
0x180006650  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x180006655  mov     [rsp+1A8h+var_188], rdi; unsigned __int16 *
0x18000665a  xor     r9d, r9d; unsigned __int16 *
0x18000665d  mov     r8b, r15b; bool
0x180006660  xor     edx, edx; unsigned int
0x180006662  mov     rcx, rsi; pswzServerName
0x180006665  call    ?Open@HttpRequest@@QEAAXK_NPEBG11@Z; HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)
0x18000666a  nop
0x18000666b  lea     rdx, [rsp+1A8h+var_B8]
0x180006673  mov     rcx, rsi
0x180006676  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x18000667b  mov     rdx, rax
0x18000667e  mov     rcx, r14
0x180006681  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x180006686  lea     rcx, [rsp+1A8h+var_B8]; this
0x18000668e  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x180006693  jmp     loc_1800068F5
0x180006698  movdqu  [rsp+1A8h+var_128], xmm0
0x1800066a1  lea     rcx, [rsp+1A8h+var_128]
0x1800066a9  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800066af  nop
0x1800066b0  mov     ebx, edi
0x1800066b2  mov     [rsp+1A8h+var_150], ebx
0x1800066b6  mov     rax, [rsp+1A8h+var_F8]
0x1800066be  mov     rcx, [rsp+1A8h+var_F0]
0x1800066c6  mov     qword ptr [rsp+1A8h+var_148], rcx
0x1800066cb  mov     [rsp+1A8h+var_160], rax
0x1800066d0  cmp     rax, rcx
0x1800066d3  jz      loc_1800067C2
0x1800066d9  lea     rcx, [rsp+1A8h+var_68]
0x1800066e1  cmp     [rsp+1A8h+var_50], 7
0x1800066ea  cmova   rcx, [rsp+1A8h+var_68]
0x1800066f3  cmp     qword ptr [rax+18h], 7
0x1800066f8  jbe     short loc_1800066FD
0x1800066fa  mov     rax, [rax]
0x1800066fd  mov     [rsp+1A8h+var_180], rdi; unsigned __int16 *
0x180006702  mov     [rsp+1A8h+var_188], rcx; unsigned __int16 *
0x180006707  mov     r9, rax; unsigned __int16 *
0x18000670a  xor     r8d, r8d; bool
0x18000670d  lea     edx, [r8+3]; unsigned int
0x180006711  mov     rcx, rsi; pswzServerName
0x180006714  call    ?Open@HttpRequest@@QEAAXK_NPEBG11@Z; HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)
0x180006719  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x180006720  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x180006725  test    al, al
0x180006727  jz      short loc_180006764
0x180006729  lea     rdx, [rsp+1A8h+var_B8]
0x180006731  mov     rcx, rsi
0x180006734  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x180006739  mov     rdx, rax
0x18000673c  mov     rcx, r14
0x18000673f  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x180006744  lea     rcx, [rsp+1A8h+var_B8]; this
0x18000674c  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x180006751  lea     rcx, [rsp+1A8h+var_128]
0x180006759  call    ??4exception_ptr@std@@QEAAAEAV01@$$T@Z; std::exception_ptr::operator=(std::nullptr_t)
0x18000675e  mov     ebx, edi
0x180006760  jmp     short loc_1800067C2
0x180006762  jmp     short loc_18000679C
0x180006764  lea     rdx, [rsp+1A8h+var_B8]
0x18000676c  mov     rcx, rsi
0x18000676f  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x180006774  mov     rdx, rax
0x180006777  mov     rcx, r14
0x18000677a  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x18000677f  lea     rcx, [rsp+1A8h+var_B8]; this
0x180006787  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x18000678c  lea     rcx, [rsp+1A8h+var_128]
0x180006794  call    ??4exception_ptr@std@@QEAAAEAV01@$$T@Z; std::exception_ptr::operator=(std::nullptr_t)
0x180006799  nop
0x18000679a  jmp     short loc_1800067C2
0x18000679c  mov     rax, [rsp+1A8h+var_160]
0x1800067a1  add     rax, 20h ; ' '
0x1800067a5  xor     edi, edi
0x1800067a7  mov     ebx, [rsp+1A8h+var_150]
0x1800067ab  mov     rcx, qword ptr [rsp+1A8h+var_148]
0x1800067b0  mov     r14, [rsp+1A8h+var_108]
0x1800067b8  mov     rsi, [rsp+1A8h+var_138]
0x1800067bd  jmp     loc_1800066CB
0x1800067c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x1800067c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x1800067ce  lea     rcx, [rsp+1A8h+var_128]
0x1800067d6  test    al, al
0x1800067d8  jz      short loc_18000683B
0x1800067da  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800067e0  test    al, al
0x1800067e2  jz      short loc_180006845
0x1800067e4  mov     r9d, 803FB017h; char *
0x1800067ea  cmp     ebx, r9d
0x1800067ed  jnz     short loc_180006809
0x1800067ef  mov     rcx, [rsp+1A8h]; this
0x1800067f7  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x1800067fe  mov     edx, 122h; void *
0x180006803  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180006809  xorps   xmm0, xmm0
0x18000680c  movdqu  [rsp+1A8h+var_148], xmm0
0x180006812  lea     rdx, [rsp+1A8h+var_128]
0x18000681a  lea     rcx, [rsp+1A8h+var_148]
0x18000681f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180006825  lea     rax, [rsp+1A8h+var_148]
0x18000682a  mov     [rsp+1A8h+var_138], rax
0x18000682f  lea     rcx, [rsp+1A8h+var_148]
0x180006834  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18000683a  nop
0x18000683b  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180006841  test    al, al
0x180006843  jnz     short loc_180006858
0x180006845  lea     rcx, [rsp+1A8h+var_128]
0x18000684d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180006853  jmp     loc_18000693C
0x180006858  xorps   xmm0, xmm0
0x18000685b  movdqu  [rsp+1A8h+var_148], xmm0
0x180006861  lea     rdx, [rsp+1A8h+var_128]
0x180006869  lea     rcx, [rsp+1A8h+var_148]
0x18000686e  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180006874  lea     rax, [rsp+1A8h+var_148]
0x180006879  mov     [rsp+1A8h+var_138], rax
0x18000687e  lea     rcx, [rsp+1A8h+var_148]
0x180006883  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180006889  nop
0x18000688a  test    r15b, r15b
0x18000688d  jnz     short loc_18000689D
0x18000688f  call    IsDeviceXbox
0x180006894  test    al, al
0x180006896  mov     edx, 1
0x18000689b  jz      short loc_18000689F
0x18000689d  mov     edx, edi; unsigned int
0x18000689f  mov     [rsp+1A8h+var_180], rdi; unsigned __int16 *
0x1800068a4  mov     [rsp+1A8h+var_188], rdi; unsigned __int16 *
0x1800068a9  xor     r9d, r9d; unsigned __int16 *
0x1800068ac  mov     r8b, r15b; bool
0x1800068af  mov     rcx, rsi; pswzServerName
0x1800068b2  call    ?Open@HttpRequest@@QEAAXK_NPEBG11@Z; HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)
0x1800068b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x1800068be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x1800068c3  test    al, al
0x1800068c5  jz      short loc_1800068F7
0x1800068c7  mov     [rsp+1A8h+var_168], r15b
0x1800068cc  lea     rdx, [rsp+1A8h+var_B8]
0x1800068d4  mov     rcx, rsi
0x1800068d7  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x1800068dc  mov     rdx, rax
0x1800068df  mov     rcx, r14
0x1800068e2  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x1800068e7  lea     rcx, [rsp+1A8h+var_B8]; this
0x1800068ef  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x1800068f4  nop
0x1800068f5  jmp     short loc_18000693C
0x1800068f7  lea     rdx, [rsp+1A8h+var_B8]
0x1800068ff  mov     rcx, rsi
0x180006902  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x180006907  mov     rdx, rax
0x18000690a  mov     rcx, r14
0x18000690d  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x180006912  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x180006919  mov     [rsp+1A8h+var_90], rax
0x180006921  lea     rcx, [rsp+1A8h+var_90]
0x180006929  call    ?Close@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(void)
0x18000692e  lea     rcx, [rsp+1A8h+var_B8]; this
0x180006936  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18000693b  nop
0x18000693c  lea     rcx, [rsp+1A8h+var_68]
0x180006944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180006949  nop
0x18000694a  lea     rcx, [rsp+1A8h+var_F8]
0x180006952  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180006957  mov     rax, r14
0x18000695a  mov     rcx, [rsp+1A8h+var_48]
0x180006962  xor     rcx, rsp; StackCookie
0x180006965  call    __security_check_cookie
0x18000696a  add     rsp, 170h
0x180006971  pop     r15
0x180006973  pop     r14
0x180006975  pop     r13
0x180006977  pop     r12
0x180006979  pop     rdi
0x18000697a  pop     rsi
0x18000697b  pop     rbx
0x18000697c  retn
```
