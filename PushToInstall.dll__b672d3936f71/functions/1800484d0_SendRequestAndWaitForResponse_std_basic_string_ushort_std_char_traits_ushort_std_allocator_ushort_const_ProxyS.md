# SendRequestAndWaitForResponse(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ProxySettings const &,HttpRequest &)

- ea: `0x1800484d0`
- end: `0x180048c06`
- name: `?SendRequestAndWaitForResponse@@YA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z`
- size: `1846`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800374d4`

## callees

- `0x1800026b0`
- `0x18000d75c`
- `0x18000dc43`
- `0x18000ea5c`
- `0x180021a64`
- `0x18002d5b8`
- `0x18002fbb4`
- `0x180030aac`
- `0x180031ac0`
- `0x1800354a0`
- `0x180036770`
- `0x180037ba8`
- `0x180046c44`
- `0x180046df8`
- `0x180047d38`
- `0x180048138`
- `0x1800484d0`
- `0x180048d34`
- `0x180049294`
- `0x180049420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048bec`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800489d3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800489d3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048787`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048877`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004893f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048787`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048877`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004893f`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18004888a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180048952`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18004888a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180048952`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004897c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180048999`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004897c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180048999`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048895`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004895d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800489af`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048895`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004895d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800489af`

## string_xrefs

- `0x180048b0a`: `Not using a config url`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
__int64 __fastcall SendRequestAndWaitForResponse(__int64 a1, __int64 a2, char *a3, WCHAR *a4)
{
  WCHAR *v4; // r15
  __int64 v6; // rsi
  char v7; // r13
  unsigned __int64 v8; // r14
  size_t v9; // r14
  __int64 v10; // rdi
  void *v11; // rax
  __int64 v12; // r14
  _OWORD *v13; // rdx
  _OWORD *v14; // rdx
  DWORD v15; // r14d
  const unsigned __int16 *v16; // rax
  __int64 v17; // rax
  int v18; // r14d
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rcx
  const unsigned __int16 *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  signed int v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  signed int v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  signed int v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  std::exception_ptr *v39; // rax
  std::exception_ptr *v40; // rax
  signed int LastError; // eax
  int v42; // edx
  unsigned int v43; // r8d
  signed int v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  wil *v47; // rcx
  unsigned int v48; // eax
  __int64 v49; // r9
  unsigned __int16 *v50; // rdx
  const char *v51; // rax
  unsigned __int16 *v52; // rax
  const char *v53; // rdx
  int v54; // [rsp+20h] [rbp-1B8h]
  char v55; // [rsp+40h] [rbp-198h]
  char v56; // [rsp+41h] [rbp-197h]
  unsigned __int16 *v57; // [rsp+50h] [rbp-188h]
  __int128 v59; // [rsp+68h] [rbp-170h] BYREF
  unsigned __int16 **i; // [rsp+78h] [rbp-160h]
  __int128 v61; // [rsp+80h] [rbp-158h] BYREF
  __int128 v62; // [rsp+90h] [rbp-148h] BYREF
  unsigned __int16 *v63[2]; // [rsp+A0h] [rbp-138h] BYREF
  size_t v64; // [rsp+B0h] [rbp-128h]
  int v65; // [rsp+B8h] [rbp-120h]
  WCHAR *v66; // [rsp+C0h] [rbp-118h]
  unsigned __int16 **v67; // [rsp+D0h] [rbp-108h]
  __int64 v68; // [rsp+E0h] [rbp-F8h]
  _BYTE pExceptionObject[48]; // [rsp+F0h] [rbp-E8h] BYREF
  char *v70[5]; // [rsp+120h] [rbp-B8h] BYREF
  void **v71; // [rsp+148h] [rbp-90h] BYREF
  __int64 v72; // [rsp+150h] [rbp-88h]
  unsigned __int16 *v73[2]; // [rsp+170h] [rbp-68h] BYREF
  __int128 v74; // [rsp+180h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v4 = a4;
  v6 = a1;
  v68 = a1;
  v66 = a4;
  v65 = 0;
  v56 = *a3;
  v7 = a3[1];
  v55 = a3[2];
  *(_OWORD *)v63 = 0;
  v64 = 0;
  v8 = (__int64)(*((_QWORD *)a3 + 2) - *((_QWORD *)a3 + 1)) >> 5;
  if ( v8 )
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFLL )
      std::vector<web::json::value>::_Xlength();
    v9 = 32 * v8;
    if ( v9 )
    {
      if ( v9 < 0x1000 )
        v11 = operator new(v9);
      else
        v11 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v9);
      v10 = (__int64)v11;
    }
    else
    {
      v10 = 0;
    }
    v63[0] = (unsigned __int16 *)v10;
    v63[1] = (unsigned __int16 *)v10;
    v64 = v9 + v10;
    v67 = v63;
    *(_QWORD *)&v61 = *((_QWORD *)a3 + 2);
    v12 = *((_QWORD *)a3 + 1);
    *(_QWORD *)&v59 = v10;
    *((_QWORD *)&v59 + 1) = v10;
    for ( i = v63; v12 != (_QWORD)v61; v12 += 32 )
    {
      *(_OWORD *)v10 = 0;
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 0;
      if ( *(_QWORD *)(v12 + 24) <= 7u )
        v13 = (_OWORD *)v12;
      else
        v13 = *(_OWORD **)v12;
      std::wstring::_Construct<2,unsigned short const *>(v10, v13, *(_QWORD *)(v12 + 16));
      v10 += 32;
      *((_QWORD *)&v59 + 1) = v10;
    }
    v63[1] = (unsigned __int16 *)v10;
  }
  v14 = a3 + 32;
  *(_OWORD *)v73 = 0;
  v74 = 0;
  if ( *((_QWORD *)a3 + 7) > 7u )
    v14 = *(_OWORD **)v14;
  std::wstring::_Construct<2,unsigned short const *>((__int64)v73, v14, *((_QWORD *)a3 + 6));
  *(_OWORD *)v6 = 0;
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  *(_DWORD *)(v6 + 32) = 0;
  *(_QWORD *)(v6 + 40) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  *(_QWORD *)(v6 + 48) = 0;
  *(_QWORD *)(v6 + 56) = 0;
  *(_QWORD *)(v6 + 64) = 0;
  v15 = 1;
  v65 = 1;
  if ( !v56 || v63[0] == v63[1] && !v55 )
  {
    if ( v7 || (LODWORD(v61) = 0, RtlGetDeviceFamilyInfoEnum(0, &v61, 0), (_DWORD)v61 == 5) )
      v15 = 0;
    HttpRequest::Open(v4, v15, v7, 0, 0, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
    {
      v25 = HttpRequest::Send(v4, v70);
      HttpResponse::operator=(v6, v25);
      v71 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
      if ( !v72 )
      {
LABEL_60:
        std::wstring::_Tidy_deallocate(v70);
        goto LABEL_61;
      }
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(&v71) )
      {
        v72 = 0;
        goto LABEL_60;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v42, v43);
    }
    else
    {
      v26 = HttpRequest::Send(v4, v70);
      HttpResponse::operator=(v6, v26);
      v71 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
      if ( !v72 )
        goto LABEL_60;
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(&v71) )
      {
        v72 = 0;
        goto LABEL_60;
      }
    }
    v44 = GetLastError();
    if ( v44 > 0 )
      v44 = (unsigned __int16)v44 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
    JUMPOUT(0x180048C05LL);
  }
  if ( !v55 )
  {
    v62 = 0;
    __ExceptionPtrCreate(&v62);
    v18 = 0;
    LODWORD(v61) = 0;
    v19 = v63[0];
    v20 = v63[1];
    v67 = (unsigned __int16 **)v63[1];
    while ( 2 )
    {
      v57 = v19;
      if ( v19 != v20 )
      {
        v21 = (const unsigned __int16 *)v73;
        if ( *((_QWORD *)&v74 + 1) > 7u )
          v21 = v73[0];
        if ( *((_QWORD *)v19 + 3) > 7u )
          v19 = *(unsigned __int16 **)v19;
        HttpRequest::Open(v4, 3u, 0, v19, v21, 0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
        {
          try
          {
            v22 = HttpRequest::Send(v4, v70);
            HttpResponse::operator=(v6, v22);
          }
          catch ( wil::ResultException )
          {
            v61 = 0;
            __ExceptionPtrCreate(&v61);
            __ExceptionPtrCurrentException(&v61);
            __ExceptionPtrAssign(&v62, &v61);
            __ExceptionPtrDestroy(&v61);
            v48 = wil::ResultFromCaughtException(v47);
            v49 = v48;
            if ( v48 == -2147012867 )
              v49 = 2151657495LL;
            LODWORD(v61) = v49;
            v50 = v57;
            if ( *((_QWORD *)v57 + 3) > 7u )
              v50 = *(unsigned __int16 **)v57;
            v51 = (const char *)a2;
            if ( *(_QWORD *)(a2 + 24) > 7u )
              v51 = *(const char **)a2;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x109,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
              (const char *)v49,
              (int)"Failed to connect to %ws with proxy %ws",
              v51,
              v50);
            v19 = v57 + 16;
            v18 = v61;
            v20 = (unsigned __int16 *)v67;
            v6 = v68;
            v4 = v66;
            continue;
          }
          v71 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
          if ( v72 )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(&v71) )
            {
LABEL_67:
              v31 = GetLastError();
              if ( v31 > 0 )
                v31 = (unsigned __int16)v31 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
              goto LABEL_70;
            }
            v72 = 0;
          }
          std::wstring::_Tidy_deallocate(v70);
          v59 = 0;
          __ExceptionPtrCreate(&v59);
          __ExceptionPtrAssign(&v62, &v59);
          __ExceptionPtrDestroy(&v59);
          v18 = 0;
        }
        else
        {
          try
          {
            v23 = HttpRequest::Send(v4, v70);
            HttpResponse::operator=(v6, v23);
          }
          catch ( wil::ResultException )
          {
            v52 = v57;
            if ( *((_QWORD *)v57 + 3) > 7u )
              v52 = *(unsigned __int16 **)v57;
            v53 = (const char *)a2;
            if ( *(_QWORD *)(a2 + 24) > 7u )
              v53 = *(const char **)a2;
            wil::details::in1diag3::Log_CaughtExceptionMsg(
              retaddr,
              (void *)0x116,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
              "Failed to connect to %ws with proxy %ws",
              v53,
              v52);
            v59 = 0;
            __ExceptionPtrCreate(&v59);
            __ExceptionPtrCurrentException(&v59);
            __ExceptionPtrAssign(&v62, &v59);
            __ExceptionPtrDestroy(&v59);
            v19 = v57 + 16;
            v18 = v61;
            v20 = (unsigned __int16 *)v67;
            v6 = v68;
            v4 = v66;
            continue;
          }
          v71 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
          if ( v72 )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(&v71) )
            {
LABEL_70:
              v34 = GetLastError();
              if ( v34 > 0 )
                v34 = (unsigned __int16)v34 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
              goto LABEL_73;
            }
            v72 = 0;
          }
          std::wstring::_Tidy_deallocate(v70);
          v59 = 0;
          __ExceptionPtrCreate(&v59);
          __ExceptionPtrAssign(&v62, &v59);
          __ExceptionPtrDestroy(&v59);
        }
      }
      break;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
    {
      if ( __ExceptionPtrToBool(&v62) )
      {
        v24 = 2151657495LL;
        if ( v18 != -2143309801 )
        {
          v39 = std::exception_ptr::exception_ptr((std::exception_ptr *)&v59, (const struct std::exception_ptr *)&v62);
          std::rethrow_exception(v39);
        }
LABEL_73:
        v37 = (const char *)(unsigned int)wil::verify_hresult<long>(v24);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x122, v38, v37, v54);
      }
    }
    else if ( __ExceptionPtrToBool(&v62) )
    {
      v40 = std::exception_ptr::exception_ptr((std::exception_ptr *)&v59, (const struct std::exception_ptr *)&v62);
      std::rethrow_exception(v40);
    }
    __ExceptionPtrDestroy(&v62);
    goto LABEL_61;
  }
  if ( !a3[2] )
  {
    std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Not using a config url");
    throw (std::logic_error *)pExceptionObject;
  }
  v16 = (const unsigned __int16 *)(a3 + 64);
  if ( *((_QWORD *)a3 + 11) > 7u )
    v16 = *(const unsigned __int16 **)v16;
  HttpRequest::Open(v4, 0, v7, 0, 0, v16);
  v17 = HttpRequest::Send(v4, v70);
  HttpResponse::operator=(v6, v17);
  v71 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  if ( !v72 )
    goto LABEL_27;
  if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(&v71) )
  {
    v28 = GetLastError();
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
    goto LABEL_67;
  }
  v72 = 0;
LABEL_27:
  std::wstring::_Tidy_deallocate(v70);
LABEL_61:
  std::wstring::_Tidy_deallocate((char **)v73);
  std::vector<std::wstring>::_Tidy(v63);
  return v6;
}

```

## disassembly

```asm
0x1800484d0  push    rbx
0x1800484d2  push    rsi
0x1800484d3  push    rdi
0x1800484d4  push    r12
0x1800484d6  push    r13
0x1800484d8  push    r14
0x1800484da  push    r15
0x1800484dc  sub     rsp, 1A0h
0x1800484e3  mov     rax, cs:__security_cookie
0x1800484ea  xor     rax, rsp
0x1800484ed  mov     [rsp+1D8h+var_48], rax
0x1800484f5  mov     r15, r9
0x1800484f8  mov     r12, r8
0x1800484fb  mov     rsi, rcx
0x1800484fe  mov     [rsp+1D8h+var_F8], rcx
0x180048506  mov     [rsp+1D8h+var_178], rdx
0x18004850b  mov     [rsp+1D8h+var_188], r8
0x180048510  mov     [rsp+1D8h+var_118], r9
0x180048518  xor     ebx, ebx
0x18004851a  mov     [rsp+1D8h+var_120], ebx
0x180048521  mov     al, [r8]
0x180048524  mov     [rsp+1D8h+var_197], al
0x180048528  mov     r13b, [r8+1]
0x18004852c  mov     al, [r8+2]
0x180048530  mov     [rsp+1D8h+var_198], al
0x180048534  xorps   xmm0, xmm0
0x180048537  movdqu  xmmword ptr [rsp+1D8h+var_138], xmm0
0x180048540  mov     [rsp+1D8h+var_128], rbx
0x180048548  mov     r14, [r8+10h]
0x18004854c  sub     r14, [r8+8]
0x180048550  sar     r14, 5
0x180048554  test    r14, r14
0x180048557  jz      loc_18004863B
0x18004855d  mov     rax, 7FFFFFFFFFFFFFFh
0x180048567  cmp     r14, rax
0x18004856a  ja      loc_180048B04
0x180048570  shl     r14, 5
0x180048574  test    r14, r14
0x180048577  jnz     short loc_18004857E
0x180048579  mov     rdi, rbx
0x18004857c  jmp     short loc_180048599
0x18004857e  mov     rcx, r14; Size
0x180048581  cmp     r14, 1000h
0x180048588  jb      short loc_180048591
0x18004858a  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18004858f  jmp     short loc_180048596
0x180048591  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048596  mov     rdi, rax
0x180048599  mov     [rsp+1D8h+var_138], rdi
0x1800485a1  mov     [rsp+1D8h+var_138+8], rdi
0x1800485a9  lea     rax, [r14+rdi]
0x1800485ad  mov     [rsp+1D8h+var_128], rax
0x1800485b5  lea     rax, [rsp+1D8h+var_138]
0x1800485bd  mov     [rsp+1D8h+var_108], rax
0x1800485c5  mov     rax, [r12+10h]
0x1800485ca  mov     qword ptr [rsp+1D8h+var_158], rax
0x1800485d2  mov     r14, [r12+8]
0x1800485d7  mov     qword ptr [rsp+1D8h+var_170], rdi
0x1800485dc  mov     qword ptr [rsp+1D8h+var_170+8], rdi
0x1800485e1  lea     rcx, [rsp+1D8h+var_138]
0x1800485e9  mov     [rsp+1D8h+var_160], rcx
0x1800485ee  cmp     r14, rax
0x1800485f1  jz      short loc_180048633
0x1800485f3  xorps   xmm0, xmm0
0x1800485f6  movups  xmmword ptr [rdi], xmm0
0x1800485f9  mov     [rdi+10h], rbx
0x1800485fd  mov     [rdi+18h], rbx
0x180048601  cmp     qword ptr [r14+18h], 7
0x180048606  jbe     short loc_18004860D
0x180048608  mov     rdx, [r14]
0x18004860b  jmp     short loc_180048610
0x18004860d  mov     rdx, r14
0x180048610  mov     r8, [r14+10h]
0x180048614  mov     rcx, rdi
0x180048617  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18004861c  add     rdi, 20h ; ' '
0x180048620  mov     qword ptr [rsp+1D8h+var_170+8], rdi
0x180048625  add     r14, 20h ; ' '
0x180048629  cmp     r14, qword ptr [rsp+1D8h+var_158]
0x180048631  jnz     short loc_1800485F3
0x180048633  mov     [rsp+1D8h+var_138+8], rdi
0x18004863b  mov     [rsp+1D8h+var_196], r13b
0x180048640  lea     rdx, [r12+20h]
0x180048645  xorps   xmm0, xmm0
0x180048648  movups  xmmword ptr [rsp+1D8h+var_68], xmm0
0x180048650  xorps   xmm1, xmm1
0x180048653  movdqu  [rsp+1D8h+var_58], xmm1
0x18004865c  mov     r8, [rdx+10h]
0x180048660  cmp     qword ptr [rdx+18h], 7
0x180048665  jbe     short loc_18004866A
0x180048667  mov     rdx, [rdx]
0x18004866a  lea     rcx, [rsp+1D8h+var_68]
0x180048672  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180048677  nop
0x180048678  xorps   xmm0, xmm0
0x18004867b  movups  xmmword ptr [rsi], xmm0
0x18004867e  mov     [rsi+10h], rbx
0x180048682  mov     qword ptr [rsi+18h], 7
0x18004868a  mov     [rsi], bx
0x18004868d  mov     [rsi+20h], ebx
0x180048690  lea     rdi, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x180048697  mov     [rsi+28h], rdi
0x18004869b  mov     [rsi+30h], rbx
0x18004869f  mov     [rsi+38h], rbx
0x1800486a3  mov     [rsi+40h], rbx
0x1800486a7  mov     r14d, 1
0x1800486ad  mov     [rsp+1D8h+var_120], r14d
0x1800486b5  cmp     [rsp+1D8h+var_197], bl
0x1800486b9  jz      loc_1800489BA
0x1800486bf  mov     rax, [rsp+1D8h+var_138+8]
0x1800486c7  cmp     [rsp+1D8h+var_138], rax
0x1800486cf  mov     al, [rsp+1D8h+var_198]
0x1800486d3  jnz     short loc_1800486DD
0x1800486d5  test    al, al
0x1800486d7  jz      loc_1800489BA
0x1800486dd  test    al, al
0x1800486df  jz      loc_180048776
0x1800486e5  cmp     [r12+2], bl
0x1800486ea  jz      loc_180048B0A
0x1800486f0  lea     rax, [r12+40h]
0x1800486f5  cmp     qword ptr [rax+18h], 7
0x1800486fa  jbe     short loc_1800486FF
0x1800486fc  mov     rax, [rax]
0x1800486ff  mov     [rsp+1D8h+var_1B0], rax; unsigned __int16 *
0x180048704  mov     [rsp+1D8h+var_1B8], rbx; int
0x180048709  xor     r9d, r9d; unsigned __int16 *
0x18004870c  mov     r8b, r13b; bool
0x18004870f  xor     edx, edx; unsigned int
0x180048711  mov     rcx, r15; pswzServerName
0x180048714  call    ?Open@HttpRequest@@QEAAXK_NPEBG11@Z; HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)
0x180048719  nop
0x18004871a  lea     rdx, [rsp+1D8h+var_B8]
0x180048722  mov     rcx, r15
0x180048725  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x18004872a  mov     rdx, rax
0x18004872d  mov     rcx, rsi
0x180048730  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x180048735  mov     [rsp+1D8h+var_90], rdi
0x18004873d  cmp     [rsp+1D8h+var_88], rbx
0x180048745  jz      short loc_180048764
0x180048747  lea     rcx, [rsp+1D8h+var_90]
0x18004874f  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x180048754  test    al, al
0x180048756  jz      loc_180048B33
0x18004875c  mov     [rsp+1D8h+var_88], rbx
0x180048764  lea     rcx, [rsp+1D8h+var_B8]
0x18004876c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048771  jmp     loc_180048A69
0x180048776  movdqu  [rsp+1D8h+var_148], xmm0
0x18004877f  lea     rcx, [rsp+1D8h+var_148]
0x180048787  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004878d  nop
0x18004878e  mov     r14d, ebx
0x180048791  mov     dword ptr [rsp+1D8h+var_158], ebx
0x180048798  mov     rax, [rsp+1D8h+var_138]
0x1800487a0  mov     rcx, [rsp+1D8h+var_138+8]
0x1800487a8  mov     [rsp+1D8h+var_108], rcx
0x1800487b0  mov     [rsp+1D8h+var_188], rax
0x1800487b5  cmp     rax, rcx
0x1800487b8  jz      loc_180048964
0x1800487be  lea     rcx, [rsp+1D8h+var_68]
0x1800487c6  cmp     qword ptr [rsp+1D8h+var_58+8], 7
0x1800487cf  cmova   rcx, [rsp+1D8h+var_68]
0x1800487d8  cmp     qword ptr [rax+18h], 7
0x1800487dd  jbe     short loc_1800487E2
0x1800487df  mov     rax, [rax]
0x1800487e2  mov     [rsp+1D8h+var_1B0], rbx; unsigned __int16 *
0x1800487e7  mov     [rsp+1D8h+var_1B8], rcx; unsigned __int16 *
0x1800487ec  mov     r9, rax; unsigned __int16 *
0x1800487ef  xor     r8d, r8d; bool
0x1800487f2  lea     edx, [r8+3]; unsigned int
0x1800487f6  mov     rcx, r15; pswzServerName
0x1800487f9  call    ?Open@HttpRequest@@QEAAXK_NPEBG11@Z; HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)
0x1800487fe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x180048805  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x18004880a  test    al, al
0x18004880c  jz      loc_1800488DA
0x180048812  lea     rdx, [rsp+1D8h+var_B8]
0x18004881a  mov     rcx, r15
0x18004881d  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x180048822  mov     rdx, rax
0x180048825  mov     rcx, rsi
0x180048828  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x18004882d  mov     [rsp+1D8h+var_90], rdi
0x180048835  cmp     [rsp+1D8h+var_88], rbx
0x18004883d  jz      short loc_18004885C
0x18004883f  lea     rcx, [rsp+1D8h+var_90]
0x180048847  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x18004884c  test    al, al
0x18004884e  jz      loc_180048B4D
0x180048854  mov     [rsp+1D8h+var_88], rbx
0x18004885c  lea     rcx, [rsp+1D8h+var_B8]
0x180048864  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048869  xorps   xmm0, xmm0
0x18004886c  movdqu  [rsp+1D8h+var_170], xmm0
0x180048872  lea     rcx, [rsp+1D8h+var_170]
0x180048877  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004887d  lea     rdx, [rsp+1D8h+var_170]
0x180048882  lea     rcx, [rsp+1D8h+var_148]
0x18004888a  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180048890  lea     rcx, [rsp+1D8h+var_170]
0x180048895  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18004889b  mov     r14d, ebx
0x18004889e  jmp     loc_180048964
0x1800488a3  mov     rax, [rsp+1D8h+var_188]
0x1800488a8  add     rax, 20h ; ' '
0x1800488ac  xor     ebx, ebx
0x1800488ae  lea     rdi, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x1800488b5  mov     r14d, dword ptr [rsp+1D8h+var_158]
0x1800488bd  mov     rcx, [rsp+1D8h+var_108]
0x1800488c5  mov     rsi, [rsp+1D8h+var_F8]
0x1800488cd  mov     r15, [rsp+1D8h+var_118]
0x1800488d5  jmp     loc_1800487B0
0x1800488da  lea     rdx, [rsp+1D8h+var_B8]
0x1800488e2  mov     rcx, r15
0x1800488e5  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x1800488ea  mov     rdx, rax
0x1800488ed  mov     rcx, rsi
0x1800488f0  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x1800488f5  mov     [rsp+1D8h+var_90], rdi
0x1800488fd  cmp     [rsp+1D8h+var_88], rbx
0x180048905  jz      short loc_180048924
0x180048907  lea     rcx, [rsp+1D8h+var_90]
0x18004890f  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x180048914  test    al, al
0x180048916  jz      loc_180048B67
0x18004891c  mov     [rsp+1D8h+var_88], rbx
0x180048924  lea     rcx, [rsp+1D8h+var_B8]
0x18004892c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048931  xorps   xmm0, xmm0
0x180048934  movdqu  [rsp+1D8h+var_170], xmm0
0x18004893a  lea     rcx, [rsp+1D8h+var_170]
0x18004893f  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180048945  lea     rdx, [rsp+1D8h+var_170]
0x18004894a  lea     rcx, [rsp+1D8h+var_148]
0x180048952  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180048958  lea     rcx, [rsp+1D8h+var_170]
0x18004895d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180048963  nop
0x180048964  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x18004896b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x180048970  lea     rcx, [rsp+1D8h+var_148]
0x180048978  test    al, al
0x18004897a  jz      short loc_180048999
0x18004897c  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180048982  test    al, al
0x180048984  jz      short loc_1800489A7
0x180048986  mov     ecx, 803FB017h
0x18004898b  cmp     r14d, ecx
0x18004898e  jnz     loc_180048B9C
0x180048994  jmp     loc_180048B81
0x180048999  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18004899f  test    al, al
0x1800489a1  jnz     loc_180048BB7
0x1800489a7  lea     rcx, [rsp+1D8h+var_148]
0x1800489af  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800489b5  jmp     loc_180048AC3
0x1800489ba  test    r13b, r13b
0x1800489bd  jnz     short loc_1800489E3
0x1800489bf  mov     dword ptr [rsp+1D8h+var_158], ebx
0x1800489c6  xor     r8d, r8d
0x1800489c9  lea     rdx, [rsp+1D8h+var_158]
0x1800489d1  xor     ecx, ecx
0x1800489d3  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800489d9  cmp     dword ptr [rsp+1D8h+var_158], 5
0x1800489e1  jnz     short loc_1800489E6
0x1800489e3  mov     r14d, ebx
0x1800489e6  mov     [rsp+1D8h+var_1B0], rbx; unsigned __int16 *
0x1800489eb  mov     [rsp+1D8h+var_1B8], rbx; unsigned __int16 *
0x1800489f0  xor     r9d, r9d; unsigned __int16 *
0x1800489f3  mov     r8b, r13b; bool
0x1800489f6  mov     edx, r14d; unsigned int
0x1800489f9  mov     rcx, r15; pswzServerName
0x1800489fc  call    ?Open@HttpRequest@@QEAAXK_NPEBG11@Z; HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)
0x180048a01  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x180048a08  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x180048a0d  test    al, al
0x180048a0f  jz      short loc_180048A6B
0x180048a11  lea     rdx, [rsp+1D8h+var_B8]
0x180048a19  mov     rcx, r15
0x180048a1c  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x180048a21  mov     rdx, rax
0x180048a24  mov     rcx, rsi
0x180048a27  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x180048a2c  mov     [rsp+1D8h+var_90], rdi
0x180048a34  cmp     [rsp+1D8h+var_88], rbx
0x180048a3c  jz      short loc_180048A5B
0x180048a3e  lea     rcx, [rsp+1D8h+var_90]
0x180048a46  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x180048a4b  test    al, al
0x180048a4d  jz      loc_180048BD2
0x180048a53  mov     [rsp+1D8h+var_88], rbx
0x180048a5b  lea     rcx, [rsp+1D8h+var_B8]
0x180048a63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048a68  nop
0x180048a69  jmp     short loc_180048AC3
0x180048a6b  lea     rdx, [rsp+1D8h+var_B8]
0x180048a73  mov     rcx, r15
0x180048a76  call    ?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ; HttpRequest::Send(void)
0x180048a7b  mov     rdx, rax
  ... truncated ...
```
