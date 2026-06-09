# ApplicationContentInfo::ApplicationContentInfo(web::json::value const &,web::json::value const &,_tagCLIP_LICENSE_DATA const &,_tagCLIP_LICENSE_DATA const *)

- ea: `0x180014c10`
- end: `0x180015aae`
- name: `??0ApplicationContentInfo@@QEAA@AEBVvalue@json@web@@0AEBU_tagCLIP_LICENSE_DATA@@PEBU4@@Z`
- size: `3742`
- prototype: `ApplicationContentInfo *__fastcall(ApplicationContentInfo *__hidden this, const struct web::json::value *, const struct web::json::value *, const struct _tagCLIP_LICENSE_DATA *, const struct _tagCLIP_LICENSE_DATA *)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d470`

## callees

- `0x1800061e0`
- `0x18000a110`
- `0x18000a98c`
- `0x180012dc0`
- `0x180014870`
- `0x180014c10`
- `0x1800171b0`
- `0x180017200`
- `0x180017230`
- `0x180017330`
- `0x180017654`
- `0x180054a54`
- `0x1800593bc`
- `0x18006a3b0`
- `0x18006bc84`
- `0x180075e60`
- `0x180078dd0`
- `0x18007bfb0`
- `0x18007c1c0`
- `0x18007c2c0`
- `0x18007d350`
- `0x18007dfe0`
- `0x18008251f`
- `0x18008252b`
- `0x1800941d4`
- `0x1800a25b8`
- `0x1800a2624`
- `0x1800a274c`
- `0x1800b8010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015938`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001596c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015990`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015938`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001596c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015990`
- `RPCRT4!UuidFromStringW` at `0x180014f2a`
- `RPCRT4!UuidFromStringW` at `0x180015370`
- `RPCRT4!UuidFromStringW` at `0x180014f2a`
- `RPCRT4!UuidFromStringW` at `0x180015370`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800157aa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180015874`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800157aa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180015874`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
ApplicationContentInfo *__fastcall ApplicationContentInfo::ApplicationContentInfo(
        ApplicationContentInfo *this,
        const struct web::json::value *a2,
        const struct web::json::value *a3,
        const struct _tagCLIP_LICENSE_DATA *a4,
        const struct _tagCLIP_LICENSE_DATA *a5)
{
  const struct _tagCLIP_LICENSE_DATA *v8; // r12
  _QWORD *v9; // r13
  _QWORD *v10; // r14
  unsigned __int64 v11; // rsi
  _WORD *v12; // r14
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rax
  __int64 v15; // rbx
  void *v16; // r12
  _QWORD *v17; // rdi
  const struct web::json::value *v18; // r13
  __int64 v19; // rax
  __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  RPC_STATUS v22; // eax
  _WORD *v23; // rdi
  unsigned __int64 v24; // r13
  __int64 v25; // rbx
  char *v26; // r14
  size_t v27; // rsi
  __int64 v28; // rbx
  __int64 v29; // rax
  char v30; // bl
  __int64 v31; // rbx
  __int64 v32; // rax
  char v33; // bl
  __int64 v34; // rbx
  __int64 v35; // rax
  char v36; // bl
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v40; // rbx
  __int64 v41; // rax
  char v42; // bl
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rcx
  RPC_STATUS v48; // eax
  __int64 v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // rax
  __int64 v53; // rbx
  unsigned __int16 *v54; // rax
  char v55; // bl
  __int64 v56; // rbx
  unsigned __int16 *v57; // rax
  __int64 v58; // rax
  _QWORD *v59; // rax
  char v60; // bl
  __int64 v61; // rbx
  __int64 v62; // rax
  web::json::value *v63; // rax
  const struct web::json::array *v64; // rdi
  unsigned __int64 v65; // rcx
  __int64 v66; // rbx
  __int64 v67; // rdi
  _QWORD *v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r8
  HRESULT v72; // eax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  const OLECHAR *v77; // rcx
  HRESULT v78; // eax
  size_t v79; // rsi
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rbx
  __int64 v84; // rax
  __int64 v85; // rax
  int v86[2]; // [rsp+20h] [rbp-91h] BYREF
  const struct _tagCLIP_LICENSE_DATA *v87; // [rsp+28h] [rbp-89h] BYREF
  const struct _tagCLIP_LICENSE_DATA *v88; // [rsp+30h] [rbp-81h] BYREF
  unsigned __int64 *v89; // [rsp+38h] [rbp-79h]
  unsigned __int64 v90; // [rsp+40h] [rbp-71h]
  const struct web::json::value *v91; // [rsp+48h] [rbp-69h]
  ApplicationContentInfo *v92; // [rsp+50h] [rbp-61h]
  _BYTE v93[32]; // [rsp+58h] [rbp-59h] BYREF
  RPC_WSTR StringUuid[2]; // [rsp+78h] [rbp-39h] BYREF
  __m128i si128; // [rsp+88h] [rbp-29h]
  _BYTE v96[32]; // [rsp+98h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v88 = a4;
  v91 = a3;
  v92 = this;
  v8 = a5;
  v87 = a5;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::`vftable'{for `IApplicationContentInfo2'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationContentInfo3>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &ApplicationContentInfo::`vftable';
  *((_QWORD *)this + 1) = &ApplicationContentInfo::`vftable'{for `IApplicationContentInfo2'};
  *((_QWORD *)this + 2) = &ApplicationContentInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationContentInfo3>'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v9 = (_QWORD *)((char *)this + 56);
  *(_OWORD *)((char *)this + 56) = 0;
  *(_QWORD *)v86 = (char *)this + 72;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 7;
  *((_WORD *)this + 28) = 0;
  *(_OWORD *)((char *)this + 88) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 7;
  *((_WORD *)this + 44) = 0;
  v10 = (_QWORD *)((char *)this + 120);
  *(_OWORD *)((char *)this + 120) = 0;
  v89 = (unsigned __int64 *)((char *)this + 136);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 7;
  *((_WORD *)this + 60) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 7;
  *((_WORD *)this + 76) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 7;
  *((_WORD *)this + 92) = 0;
  *(_OWORD *)((char *)this + 216) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 7;
  *((_WORD *)this + 108) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 7;
  *((_WORD *)this + 124) = 0;
  *(_OWORD *)((char *)this + 280) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 7;
  *((_WORD *)this + 140) = 0;
  *((_QWORD *)this + 39) = 0;
  *((GUID *)this + 20) = GUID_NULL;
  *((_DWORD *)this + 84) = *((_DWORD *)a4 + 25);
  *((_DWORD *)this + 85) = *((_DWORD *)a4 + 26);
  *(_OWORD *)((char *)this + 344) = *(_OWORD *)((char *)a4 + 76);
  v11 = -1;
  if ( (unsigned int)web::json::value::type(a2) == 3 )
  {
    *(_OWORD *)StringUuid = 0;
    si128 = 0;
    v49 = std::wstring::_Calculate_growth(17, 7);
    v50 = std::allocator<unsigned short>::allocate(StringUuid, v49 + 1);
    StringUuid[0] = (RPC_WSTR)v50;
    si128.m128i_i64[0] = 17;
    si128.m128i_i64[1] = v49;
    *(_OWORD *)v50 = *(_OWORD *)L"packageIdentifier";
    *(_OWORD *)(v50 + 16) = *(_OWORD *)L"dentifier";
    *(_WORD *)(v50 + 32) = aPackageidentif[16];
    *(_WORD *)(v50 + 34) = 0;
    v51 = web::json::value::at(a2, StringUuid);
    v52 = (_QWORD *)web::json::value::as_string(v51);
    if ( v9 != v52 )
    {
      v70 = v52[2];
      if ( v52[3] > 7u )
        v52 = (_QWORD *)*v52;
      std::wstring::_Assign<unsigned short>((char *)this + 56, v52, v70);
    }
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    *(_OWORD *)StringUuid = 0;
    si128 = 0;
    v53 = std::wstring::_Calculate_growth(9, 7);
    v54 = (unsigned __int16 *)std::allocator<unsigned short>::allocate(StringUuid, v53 + 1);
    StringUuid[0] = v54;
    si128.m128i_i64[0] = 9;
    si128.m128i_i64[1] = v53;
    *(_OWORD *)v54 = *(_OWORD *)L"productId";
    v54[8] = aProductid[8];
    v54[9] = 0;
    v55 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, StringUuid);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    if ( v55 )
    {
      *(_OWORD *)StringUuid = 0;
      si128 = 0;
      v56 = std::wstring::_Calculate_growth(9, 7);
      v57 = (unsigned __int16 *)std::allocator<unsigned short>::allocate(StringUuid, v56 + 1);
      StringUuid[0] = v57;
      si128.m128i_i64[0] = 9;
      si128.m128i_i64[1] = v56;
      *(_OWORD *)v57 = *(_OWORD *)L"productId";
      v57[8] = aProductid[8];
      v57[9] = 0;
      v58 = web::json::value::at(a2, StringUuid);
      v59 = (_QWORD *)web::json::value::as_string(v58);
      if ( (_QWORD *)((char *)this + 88) != v59 )
      {
        v71 = v59[2];
        if ( v59[3] > 7u )
          v59 = (_QWORD *)*v59;
        std::wstring::_Assign<unsigned short>((char *)this + 88, v59, v71);
      }
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    StringUuid[0] = *(RPC_WSTR *)L"skuId";
    StringUuid[1] = (RPC_WSTR)aSkuid[4];
    v60 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, StringUuid);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    if ( v60 )
    {
      std::wstring::wstring(StringUuid, L"skuId");
      v73 = web::json::value::at(a2, StringUuid);
      v74 = web::json::value::as_string(v73);
      std::wstring::operator=((char *)this + 280, v74);
      std::wstring::_Tidy_deallocate(StringUuid);
    }
    *(_OWORD *)StringUuid = 0;
    si128 = 0;
    v61 = std::wstring::_Calculate_growth(13, 7);
    v62 = std::allocator<unsigned short>::allocate(StringUuid, v61 + 1);
    StringUuid[0] = (RPC_WSTR)v62;
    si128.m128i_i64[0] = 13;
    si128.m128i_i64[1] = v61;
    *(_OWORD *)v62 = *(_OWORD *)L"productAddOns";
    *(_OWORD *)(v62 + 10) = *(_OWORD *)L"ctAddOns";
    *(_WORD *)(v62 + 26) = 0;
    v63 = (web::json::value *)web::json::value::at(a2, StringUuid);
    v64 = web::json::value::as_array(v63);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(StringUuid[0]) = 0;
    v65 = (__int64)(*((_QWORD *)v64 + 1) - *(_QWORD *)v64) >> 3;
    v87 = (const struct _tagCLIP_LICENSE_DATA *)v65;
    if ( v65 > (__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 4)) >> 3 )
    {
      if ( v65 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      std::vector<Microsoft::WRL::ComPtr<ApplicationContentInfo::ApplicationAddOn>>::_Reallocate<0>(
        (char *)this + 32,
        &v87);
    }
    v66 = *(_QWORD *)v64;
    v67 = *((_QWORD *)v64 + 1);
    while ( v66 != v67 )
    {
      MakeCom<ApplicationContentInfo::ApplicationAddOn,web::json::value const &>(v86, v66);
      v68 = (_QWORD *)*((_QWORD *)this + 5);
      if ( v68 == *((_QWORD **)this + 6) )
      {
        std::vector<Microsoft::WRL::ComPtr<ApplicationContentInfo::ApplicationAddOn>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<ApplicationContentInfo::ApplicationAddOn> const &>(
          (char *)this + 32,
          v68,
          v86);
      }
      else
      {
        *v68 = *(_QWORD *)v86;
        if ( *(_QWORD *)v86 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v86 + 8LL))(*(_QWORD *)v86);
        *((_QWORD *)this + 5) += 8LL;
      }
      v69 = *(_QWORD *)v86;
      if ( *(_QWORD *)v86 )
      {
        *(_QWORD *)v86 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      }
      v66 += 8;
    }
  }
  else
  {
    v12 = *(_WORD **)((char *)a4 + 140);
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = *((_QWORD *)this + 10);
    v90 = v14;
    if ( v13 <= v14 )
    {
      if ( v14 > 7 )
        v9 = (_QWORD *)*v9;
      **(_QWORD **)v86 = v13;
      memmove_0(v9, v12, 2 * v13);
      *((_WORD *)v9 + v13) = 0;
    }
    else
    {
      if ( v13 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      v15 = std::wstring::_Calculate_growth((char *)this + 56, v13);
      v16 = (void *)std::allocator<unsigned short>::allocate((char *)this + 56, v15 + 1);
      **(_QWORD **)v86 = v13;
      *((_QWORD *)this + 10) = v15;
      memcpy_0(v16, v12, 2 * v13);
      *((_WORD *)v16 + v13) = 0;
      if ( v90 > 7 )
        std::_Deallocate<16>(*v9, 2 * v90 + 2);
      *v9 = v16;
      v8 = v87;
    }
    v10 = (_QWORD *)((char *)this + 120);
  }
  v17 = (_QWORD *)((char *)this + 320);
  *((_OWORD *)this + 20) = 0;
  v18 = v91;
  if ( (unsigned int)web::json::value::type(v91) == 3 )
  {
    *(_OWORD *)StringUuid = 0;
    si128 = 0;
    v40 = std::wstring::_Calculate_growth(15, 7);
    v41 = std::allocator<unsigned short>::allocate(StringUuid, v40 + 1);
    StringUuid[0] = (RPC_WSTR)v41;
    si128.m128i_i64[0] = 15;
    si128.m128i_i64[1] = v40;
    *(_OWORD *)v41 = *(_OWORD *)L"legacyProductId";
    *(_OWORD *)(v41 + 14) = *(_OWORD *)L"roductId";
    *(_WORD *)(v41 + 30) = 0;
    v42 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18, StringUuid);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    if ( v42 )
    {
      *(_OWORD *)StringUuid = 0;
      si128 = 0;
      v43 = std::wstring::_Calculate_growth(15, 7);
      v44 = std::allocator<unsigned short>::allocate(StringUuid, v43 + 1);
      StringUuid[0] = (RPC_WSTR)v44;
      si128.m128i_i64[0] = 15;
      si128.m128i_i64[1] = v43;
      *(_OWORD *)v44 = *(_OWORD *)L"legacyProductId";
      *(_OWORD *)(v44 + 14) = *(_OWORD *)L"roductId";
      *(_WORD *)(v44 + 30) = 0;
      v45 = web::json::value::at(v18, StringUuid);
      v46 = web::json::value::as_string(v45);
      v47 = *(_QWORD *)(v46 + 16);
      if ( v47 == 36 )
      {
        if ( *(_QWORD *)(v46 + 24) > 7u )
          v46 = *(_QWORD *)v46;
        v48 = UuidFromStringW((RPC_WSTR)v46, (UUID *)this + 20);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x179,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\appcontentinfo.cpp",
            (const char *)(unsigned int)v48,
            v86[0]);
      }
      else if ( v47 == 38 )
      {
        if ( *(_QWORD *)(v46 + 24) > 7u )
          v46 = *(_QWORD *)v46;
        v72 = CLSIDFromString((LPCOLESTR)v46, (LPCLSID)this + 20);
        if ( v72 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\appcontentinfo.cpp",
            (const char *)(unsigned int)v72,
            v86[0]);
      }
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
    }
  }
  v19 = *v17 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *v17 == *(_QWORD *)&GUID_NULL.Data1 )
    v19 = *((_QWORD *)this + 41) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v19 )
  {
    v20 = *(_QWORD *)((char *)v88 + 132);
    if ( v20 )
    {
      std::wstring::wstring(StringUuid, v20);
      if ( si128.m128i_i64[0] == 36 )
      {
        v21 = (unsigned __int16 *)StringUuid;
        if ( si128.m128i_i64[1] > 7uLL )
          v21 = StringUuid[0];
        v22 = UuidFromStringW(v21, (UUID *)this + 20);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x179,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\appcontentinfo.cpp",
            (const char *)(unsigned int)v22,
            v86[0]);
      }
      else if ( si128.m128i_i64[0] == 38 )
      {
        v77 = (const OLECHAR *)StringUuid;
        if ( si128.m128i_i64[1] > 7uLL )
          v77 = StringUuid[0];
        v78 = CLSIDFromString(v77, (LPCLSID)this + 20);
        if ( v78 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\appcontentinfo.cpp",
            (const char *)(unsigned int)v78,
            v86[0]);
      }
      std::wstring::_Tidy_deallocate(StringUuid);
    }
  }
  *((_DWORD *)this + 79) = 0x7FFFFFFF;
  *((_DWORD *)this + 78) = -1;
  if ( v8 )
  {
    v23 = *(_WORD **)((char *)v8 + 172);
    if ( v23 )
    {
      do
        ++v11;
      while ( v23[v11] );
      v24 = v10[3];
      if ( v11 <= v24 )
      {
        if ( v24 > 7 )
          v10 = (_QWORD *)*v10;
        *v89 = v11;
        v79 = 2 * v11;
        memmove_0(v10, v23, v79);
        *(_WORD *)((char *)v10 + v79) = 0;
      }
      else
      {
        if ( v11 > 0x7FFFFFFFFFFFFFFELL )
          std::_Xlength_error("string too long");
        v25 = std::wstring::_Calculate_growth(v10, v11);
        v26 = (char *)std::allocator<unsigned short>::allocate(v10, v25 + 1);
        *v89 = v11;
        *((_QWORD *)this + 18) = v25;
        v27 = 2 * v11;
        memcpy_0(v26, v23, v27);
        *(_WORD *)&v26[v27] = 0;
        if ( v24 > 7 )
          std::_Deallocate<16>(*((_QWORD *)this + 15), 2 * v24 + 2);
        *((_QWORD *)this + 15) = v26;
      }
      DecodeCustomPolicy(v86, *(_QWORD *)((char *)v8 + 172));
      *(_OWORD *)StringUuid = 0;
      si128 = 0;
      v28 = std::wstring::_Calculate_growth(18, 7);
      v29 = std::allocator<unsigned short>::allocate(StringUuid, v28 + 1);
      StringUuid[0] = (RPC_WSTR)v29;
      si128.m128i_i64[0] = 18;
      si128.m128i_i64[1] = v28;
      *(_OWORD *)v29 = *(_OWORD *)L"trialTimeRemaining";
      *(_OWORD *)(v29 + 16) = *(_OWORD *)L"eRemaining";
      *(_DWORD *)(v29 + 32) = *(_DWORD *)L"ng";
      *(_WORD *)(v29 + 36) = 0;
      v30 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)v86 + 8LL))(*(_QWORD *)v86, StringUuid);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
      if ( v30 )
      {
        std::wstring::wstring(StringUuid, L"trialTimeRemaining");
        v80 = web::json::value::at(v86, StringUuid);
        v81 = web::json::value::as_string(v80);
        std::wstring::wstring(v96, v81);
        ContentIdString::~ContentIdString((ContentIdString *)StringUuid);
        v82 = std::wstring::wstring(v93, v96);
        v83 = *(_QWORD *)string_to_seconds(&v88, v82);
        *((_QWORD *)this + 39) = 10000000LL * (unsigned int)v83 + *(_QWORD *)utility::datetime::utc_now(&v88);
        ContentIdString::~ContentIdString((ContentIdString *)v96);
      }
      *(_OWORD *)StringUuid = 0;
      si128 = 0;
      v31 = std::wstring::_Calculate_growth(10, 7);
      v32 = std::allocator<unsigned short>::allocate(StringUuid, v31 + 1);
      StringUuid[0] = (RPC_WSTR)v32;
      si128.m128i_i64[0] = 10;
      si128.m128i_i64[1] = v31;
      *(_OWORD *)v32 = *(_OWORD *)L"appModelId";
      *(_DWORD *)(v32 + 16) = *(_DWORD *)L"Id";
      *(_WORD *)(v32 + 20) = 0;
      v33 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)v86 + 8LL))(*(_QWORD *)v86, StringUuid);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
      if ( v33 )
      {
        std::wstring::wstring(v96, L"appModelId");
        v84 = web::json::value::at(v86, v96);
        v85 = web::json::value::as_string(v84);
        std::wstring::operator=((char *)this + 184, v85);
        ContentIdString::~ContentIdString((ContentIdString *)v96);
      }
      *(_OWORD *)StringUuid = 0;
      si128 = 0;
      v34 = std::wstring::_Calculate_growth(13, 7);
      v35 = std::allocator<unsigned short>::allocate(StringUuid, v34 + 1);
      StringUuid[0] = (RPC_WSTR)v35;
      si128.m128i_i64[0] = 13;
      si128.m128i_i64[1] = v34;
      *(_OWORD *)v35 = *(_OWORD *)L"entitlementId";
      *(_OWORD *)(v35 + 10) = *(_OWORD *)L"lementId";
      *(_WORD *)(v35 + 26) = 0;
      v36 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)v86 + 8LL))(*(_QWORD *)v86, StringUuid);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(StringUuid[0], 2 * si128.m128i_i64[1] + 2);
      if ( v36 )
      {
        std::wstring::wstring(v96, L"entitlementId");
        v75 = web::json::value::at(v86, v96);
        v76 = web::json::value::as_string(v75);
        std::wstring::operator=((char *)this + 248, v76);
        std::wstring::_Tidy_deallocate(v96);
      }
      if ( *(_QWORD *)v86 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v86 + 192LL))(*(_QWORD *)v86, 1);
    }
    v37 = *(_QWORD *)((char *)v8 + 148);
    if ( v37 )
      std::wstring::assign((char *)this + 152, v37);
    v38 = *(_QWORD *)((char *)v8 + 156);
    if ( v38 )
      std::wstring::assign((char *)this + 216, v38);
  }
  return this;
}

```

## disassembly

```asm
0x180014c10  push    rbp
0x180014c12  push    rbx
0x180014c13  push    rsi
0x180014c14  push    rdi
0x180014c15  push    r12
0x180014c17  push    r13
0x180014c19  push    r14
0x180014c1b  push    r15
0x180014c1d  lea     rbp, [rsp-17h]
0x180014c22  sub     rsp, 0C8h
0x180014c29  mov     rax, cs:__security_cookie
0x180014c30  xor     rax, rsp
0x180014c33  mov     [rbp+4Fh+var_48], rax
0x180014c37  mov     rbx, r9
0x180014c3a  mov     [rsp+100h+var_D0], rbx
0x180014c3f  mov     [rbp+4Fh+var_B8], r8
0x180014c43  mov     rdi, rdx
0x180014c46  mov     r15, rcx
0x180014c49  mov     [rbp+4Fh+var_B0], rcx
0x180014c4d  mov     r12, [rbp+4Fh+arg_20]
0x180014c51  mov     [rsp+100h+var_D8], r12
0x180014c56  xor     esi, esi
0x180014c58  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIApplicationContentInfo@@UIApplicationContentInfo2@@UIApplicationContentInfo3@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>(void)
0x180014c5d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationContentInfo@@UIApplicationContentInfo2@@UIApplicationContentInfo3@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::`vftable'
0x180014c64  mov     [r15], rcx
0x180014c67  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationContentInfo@@UIApplicationContentInfo2@@UIApplicationContentInfo3@@@WRL@Microsoft@@6BIApplicationContentInfo2@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::`vftable'{for `IApplicationContentInfo2'}
0x180014c6e  mov     [r15+8], rax
0x180014c72  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationContentInfo@@UIApplicationContentInfo2@@UIApplicationContentInfo3@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIApplicationContentInfo3@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationContentInfo,IApplicationContentInfo2,IApplicationContentInfo3>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationContentInfo3>'}
0x180014c79  mov     [r15+10h], rax
0x180014c7d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014c84  test    rcx, rcx
0x180014c87  jz      short loc_180014C96
0x180014c89  mov     rax, [rcx]
0x180014c8c  mov     rax, [rax+8]
0x180014c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c95  nop
0x180014c96  lea     rax, ??_7ApplicationContentInfo@@6B@; const ApplicationContentInfo::`vftable'
0x180014c9d  mov     [r15], rax
0x180014ca0  lea     rax, ??_7ApplicationContentInfo@@6BIApplicationContentInfo2@@@; const ApplicationContentInfo::`vftable'{for `IApplicationContentInfo2'}
0x180014ca7  mov     [r15+8], rax
0x180014cab  lea     rax, ??_7ApplicationContentInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIApplicationContentInfo3@@@Details@WRL@Microsoft@@@; const ApplicationContentInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationContentInfo3>'}
0x180014cb2  mov     [r15+10h], rax
0x180014cb6  mov     [r15+20h], rsi
0x180014cba  mov     [r15+28h], rsi
0x180014cbe  mov     [r15+30h], rsi
0x180014cc2  lea     r13, [r15+38h]
0x180014cc6  xorps   xmm0, xmm0
0x180014cc9  movups  xmmword ptr [r13+0], xmm0
0x180014cce  lea     rax, [r13+10h]
0x180014cd2  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180014cd7  mov     [rax], rsi
0x180014cda  mov     qword ptr [r13+18h], 7
0x180014ce2  mov     [r13+0], si
0x180014ce7  movups  xmmword ptr [r15+58h], xmm0
0x180014cec  mov     [r15+68h], rsi
0x180014cf0  mov     qword ptr [r15+70h], 7
0x180014cf8  mov     [r15+58h], si
0x180014cfd  lea     r14, [r15+78h]
0x180014d01  movups  xmmword ptr [r14], xmm0
0x180014d05  lea     rax, [r14+10h]
0x180014d09  mov     [rbp+4Fh+var_C8], rax
0x180014d0d  mov     [rax], rsi
0x180014d10  mov     qword ptr [r14+18h], 7
0x180014d18  mov     [r14], si
0x180014d1c  movups  xmmword ptr [r15+98h], xmm0
0x180014d24  mov     [r15+0A8h], rsi
0x180014d2b  mov     qword ptr [r15+0B0h], 7
0x180014d36  mov     [r15+98h], si
0x180014d3e  movups  xmmword ptr [r15+0B8h], xmm0
0x180014d46  mov     [r15+0C8h], rsi
0x180014d4d  mov     qword ptr [r15+0D0h], 7
0x180014d58  mov     [r15+0B8h], si
0x180014d60  movups  xmmword ptr [r15+0D8h], xmm0
0x180014d68  mov     [r15+0E8h], rsi
0x180014d6f  mov     qword ptr [r15+0F0h], 7
0x180014d7a  mov     [r15+0D8h], si
0x180014d82  movups  xmmword ptr [r15+0F8h], xmm0
0x180014d8a  mov     [r15+108h], rsi
0x180014d91  mov     qword ptr [r15+110h], 7
0x180014d9c  mov     [r15+0F8h], si
0x180014da4  movups  xmmword ptr [r15+118h], xmm0
0x180014dac  mov     [r15+128h], rsi
0x180014db3  mov     qword ptr [r15+130h], 7
0x180014dbe  mov     [r15+118h], si
0x180014dc6  mov     [r15+138h], rsi
0x180014dcd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014dd4  movups  xmmword ptr [r15+140h], xmm0
0x180014ddc  mov     eax, [rbx+64h]
0x180014ddf  mov     [r15+150h], eax
0x180014de6  mov     eax, [rbx+68h]
0x180014de9  mov     [r15+154h], eax
0x180014df0  movups  xmm0, xmmword ptr [rbx+4Ch]
0x180014df4  movups  xmmword ptr [r15+158h], xmm0
0x180014dfc  mov     rcx, rdi
0x180014dff  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x180014e04  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180014e0e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180014e15  cmp     eax, 3
0x180014e18  jz      loc_1800153A6
0x180014e1e  mov     r14, [rbx+8Ch]
0x180014e25  mov     rdi, rsi
0x180014e28  nop     dword ptr [rax+rax+00000000h]
0x180014e30  inc     rdi
0x180014e33  cmp     word ptr [r14+rdi*2], 0
0x180014e39  jnz     short loc_180014E30
0x180014e3b  mov     rax, [r13+18h]
0x180014e3f  mov     [rbp+4Fh+var_C0], rax
0x180014e43  cmp     rdi, rax
0x180014e46  jbe     loc_1800158C5
0x180014e4c  cmp     rdi, rcx
0x180014e4f  ja      loc_180015965
0x180014e55  mov     rdx, rdi
0x180014e58  mov     rcx, r13
0x180014e5b  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBA_K_K@Z; std::wstring::_Calculate_growth(unsigned __int64)
0x180014e60  mov     rbx, rax
0x180014e63  lea     rdx, [rax+1]
0x180014e67  mov     rcx, r13
0x180014e6a  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180014e6f  mov     r12, rax
0x180014e72  mov     rax, qword ptr [rsp+100h+var_E0]
0x180014e77  mov     [rax], rdi
0x180014e7a  mov     [r13+18h], rbx
0x180014e7e  lea     rbx, [rdi+rdi]
0x180014e82  mov     r8, rbx; Size
0x180014e85  mov     rdx, r14; Src
0x180014e88  mov     rcx, r12; void *
0x180014e8b  call    memcpy_0
0x180014e90  xor     eax, eax
0x180014e92  mov     [rbx+r12], ax
0x180014e97  mov     rdx, [rbp+4Fh+var_C0]
0x180014e9b  cmp     rdx, 7
0x180014e9f  ja      loc_180015973
0x180014ea5  mov     [r13+0], r12
0x180014ea9  mov     r12, [rsp+100h+var_D8]
0x180014eae  lea     r14, [r15+78h]
0x180014eb2  xorps   xmm0, xmm0
0x180014eb5  lea     rdi, [r15+140h]
0x180014ebc  movups  xmmword ptr [rdi], xmm0
0x180014ebf  mov     r13, [rbp+4Fh+var_B8]
0x180014ec3  mov     rcx, r13
0x180014ec6  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x180014ecb  cmp     eax, 3
0x180014ece  jz      loc_180015245
0x180014ed4  mov     rax, [rdi]
0x180014ed7  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180014ede  jnz     short loc_180014EEB
0x180014ee0  mov     rax, [rdi+8]
0x180014ee4  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180014eeb  test    rax, rax
0x180014eee  jnz     short loc_180014F45
0x180014ef0  mov     rax, [rsp+100h+var_D0]
0x180014ef5  mov     rdx, [rax+84h]
0x180014efc  test    rdx, rdx
0x180014eff  jz      short loc_180014F45
0x180014f01  lea     rcx, [rbp+4Fh+StringUuid]
0x180014f05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014f0a  nop
0x180014f0b  mov     rax, qword ptr [rbp+4Fh+var_78]
0x180014f0f  cmp     rax, 24h ; '$'
0x180014f13  jnz     loc_180015859
0x180014f19  lea     rcx, [rbp+4Fh+StringUuid]
0x180014f1d  cmp     qword ptr [rbp+4Fh+var_78+8], 7
0x180014f22  cmova   rcx, [rbp+4Fh+StringUuid]; StringUuid
0x180014f27  mov     rdx, rdi; Uuid
0x180014f2a  call    cs:__imp_UuidFromStringW
0x180014f30  mov     rcx, [rbp+57h]; this
0x180014f34  test    eax, eax
0x180014f36  js      loc_1800158B0
0x180014f3c  lea     rcx, [rbp+4Fh+StringUuid]
0x180014f40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014f45  mov     dword ptr [r15+13Ch], 7FFFFFFFh
0x180014f50  mov     dword ptr [r15+138h], 0FFFFFFFFh
0x180014f5b  test    r12, r12
0x180014f5e  jz      loc_180015222
0x180014f64  mov     rdi, [r12+0ACh]
0x180014f6c  test    rdi, rdi
0x180014f6f  jz      loc_180015200
0x180014f75  inc     rsi
0x180014f78  cmp     word ptr [rdi+rsi*2], 0
0x180014f7d  jnz     short loc_180014F75
0x180014f7f  mov     r13, [r14+18h]
0x180014f83  cmp     rsi, r13
0x180014f86  jbe     loc_1800158F5
0x180014f8c  mov     rax, 7FFFFFFFFFFFFFFEh
0x180014f96  cmp     rsi, rax
0x180014f99  ja      loc_180015989
0x180014f9f  mov     rdx, rsi
0x180014fa2  mov     rcx, r14
0x180014fa5  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBA_K_K@Z; std::wstring::_Calculate_growth(unsigned __int64)
0x180014faa  mov     rbx, rax
0x180014fad  lea     rdx, [rax+1]
0x180014fb1  mov     rcx, r14
0x180014fb4  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180014fb9  mov     r14, rax
0x180014fbc  mov     rax, [rbp+4Fh+var_C8]
0x180014fc0  mov     [rax], rsi
0x180014fc3  mov     [r15+90h], rbx
0x180014fca  add     rsi, rsi
0x180014fcd  mov     r8, rsi; Size
0x180014fd0  mov     rdx, rdi; Src
0x180014fd3  mov     rcx, r14; void *
0x180014fd6  call    memcpy_0
0x180014fdb  xor     eax, eax
0x180014fdd  mov     [r14+rsi], ax
0x180014fe2  cmp     r13, 7
0x180014fe6  ja      loc_180015997
0x180014fec  mov     [r15+78h], r14
0x180014ff0  mov     rdx, [r12+0ACh]
0x180014ff8  lea     rcx, [rsp+100h+var_E0]
0x180014ffd  call    ?DecodeCustomPolicy@@YA?AVvalue@json@web@@PEBG@Z; DecodeCustomPolicy(ushort const *)
0x180015002  nop
0x180015003  xorps   xmm0, xmm0
0x180015006  movups  xmmword ptr [rbp+4Fh+StringUuid], xmm0
0x18001500a  xorps   xmm1, xmm1
0x18001500d  movdqu  [rbp+4Fh+var_78], xmm1
0x180015012  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18001501c  mov     r8, rdi
0x18001501f  mov     edx, 7
0x180015024  mov     ecx, 12h
0x180015029  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001502e  mov     rbx, rax
0x180015031  lea     rdx, [rax+1]
0x180015035  lea     rcx, [rbp+4Fh+StringUuid]
0x180015039  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18001503e  mov     rcx, rax
0x180015041  mov     [rbp+4Fh+StringUuid], rax
0x180015045  mov     qword ptr [rbp+4Fh+var_78], 12h
0x18001504d  mov     qword ptr [rbp+4Fh+var_78+8], rbx
0x180015051  movups  xmm0, xmmword ptr cs:aTrialtimeremai; "trialTimeRemaining"
0x180015058  movups  xmmword ptr [rax], xmm0
0x18001505b  movups  xmm1, xmmword ptr cs:aTrialtimeremai+10h; "eRemaining"
0x180015062  movups  xmmword ptr [rax+10h], xmm1
0x180015066  mov     eax, dword ptr cs:aTrialtimeremai+20h; "ng"
0x18001506c  mov     [rcx+20h], eax
0x18001506f  xor     eax, eax
0x180015071  mov     [rcx+24h], ax
0x180015075  mov     rcx, qword ptr [rsp+100h+var_E0]
0x18001507a  mov     rax, [rcx]
0x18001507d  lea     rdx, [rbp+4Fh+StringUuid]
0x180015081  mov     rax, [rax+8]
0x180015085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001508a  movzx   ebx, al
0x18001508d  mov     rdx, qword ptr [rbp+4Fh+var_78+8]
0x180015091  cmp     rdx, 7
0x180015095  jbe     short loc_1800150A8
0x180015097  lea     rdx, ds:2[rdx*2]
0x18001509f  mov     rcx, [rbp+4Fh+StringUuid]
0x1800150a3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800150a8  test    bl, bl
0x1800150aa  jnz     loc_1800159AD
0x1800150b0  xorps   xmm0, xmm0
0x1800150b3  movups  xmmword ptr [rbp+4Fh+StringUuid], xmm0
0x1800150b7  xorps   xmm1, xmm1
0x1800150ba  movdqu  [rbp+4Fh+var_78], xmm1
0x1800150bf  mov     r8, rdi
0x1800150c2  mov     edx, 7
0x1800150c7  mov     ecx, 0Ah
0x1800150cc  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800150d1  mov     rbx, rax
0x1800150d4  lea     rdx, [rax+1]
0x1800150d8  lea     rcx, [rbp+4Fh+StringUuid]
0x1800150dc  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x1800150e1  mov     rcx, rax
0x1800150e4  mov     [rbp+4Fh+StringUuid], rax
0x1800150e8  mov     qword ptr [rbp+4Fh+var_78], 0Ah
0x1800150f0  mov     qword ptr [rbp+4Fh+var_78+8], rbx
0x1800150f4  movups  xmm0, xmmword ptr cs:aAppmodelid; "appModelId"
0x1800150fb  movups  xmmword ptr [rax], xmm0
0x1800150fe  mov     eax, dword ptr cs:aAppmodelid+10h; "Id"
0x180015104  mov     [rcx+10h], eax
0x180015107  xor     eax, eax
0x180015109  mov     [rcx+14h], ax
0x18001510d  mov     rcx, qword ptr [rsp+100h+var_E0]
0x180015112  mov     rax, [rcx]
0x180015115  lea     rdx, [rbp+4Fh+StringUuid]
0x180015119  mov     rax, [rax+8]
0x18001511d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015122  movzx   ebx, al
0x180015125  mov     rdx, qword ptr [rbp+4Fh+var_78+8]
0x180015129  cmp     rdx, 7
0x18001512d  jbe     short loc_180015140
0x18001512f  lea     rdx, ds:2[rdx*2]
0x180015137  mov     rcx, [rbp+4Fh+StringUuid]
0x18001513b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015140  test    bl, bl
0x180015142  jnz     loc_180015A46
0x180015148  xorps   xmm0, xmm0
0x18001514b  movups  xmmword ptr [rbp+4Fh+StringUuid], xmm0
0x18001514f  xorps   xmm1, xmm1
0x180015152  movdqu  [rbp+4Fh+var_78], xmm1
0x180015157  mov     r8, rdi
0x18001515a  mov     edx, 7
0x18001515f  mov     ecx, 0Dh
0x180015164  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180015169  mov     rbx, rax
0x18001516c  lea     rdx, [rax+1]
0x180015170  lea     rcx, [rbp+4Fh+StringUuid]
0x180015174  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180015179  mov     rcx, rax
0x18001517c  mov     [rbp+4Fh+StringUuid], rax
  ... truncated ...
```
