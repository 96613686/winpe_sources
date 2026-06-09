# ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality(LicenseQuality,ushort const *,ILicenseIdentityContext *,IStoredKeyDocument *,IStoredKeyDocument * *)

- ea: `0x180011aa0`
- end: `0x1800126e3`
- name: `?GetKeyDocumentForContentWithIdAndMinQuality@ClipStorage@@UEAAJW4LicenseQuality@@PEBGPEAUILicenseIdentityContext@@PEAUIStoredKeyDocument@@PEAPEAU4@@Z`
- size: `3139`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004738`
- `0x18000b7fc`
- `0x18000f07c`
- `0x18000f164`
- `0x180010250`
- `0x1800104c8`
- `0x180011960`
- `0x1800119e0`
- `0x180011a00`
- `0x180011aa0`
- `0x180013b50`
- `0x180026970`
- `0x180027460`
- `0x1800593bc`
- `0x180075e60`
- `0x1800767e0`
- `0x180082537`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001202b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001202b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012409`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001204a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012198`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012370`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012428`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001204a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012198`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012370`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012428`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800125ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800125ad`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011dae`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011dae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012502`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012502`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800124bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800124bb`

## string_xrefs

- `0x180011dd3`: `Considering License ID %s for content ID %s...`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality(
        __int64 a1,
        int a2,
        _WORD *a3,
        __int64 a4,
        __int64 a5,
        char **a6)
{
  __int64 v6; // r13
  int v10; // eax
  wil::details::in1diag3 *v11; // rbx
  char *v12; // rax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rcx
  char *v15; // r14
  char **v16; // r15
  __int64 *v17; // rsi
  __int64 v18; // r12
  wil::details::in1diag3 *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  char *v22; // rdi
  int v23; // eax
  void **v24; // rsi
  __int64 v25; // rax
  signed __int32 v26; // r12d
  char *v27; // rdx
  char *v28; // rax
  const WCHAR *v29; // rcx
  int v30; // eax
  int v31; // ecx
  char *v32; // rsi
  char *v33; // rcx
  wil::details::in1diag3 *v34; // rcx
  int v35; // eax
  const char *v36; // r9
  int v37; // eax
  char v38; // al
  int v39; // rax^4
  const void *v40; // r14
  __int64 v41; // rax
  int v42; // eax
  int v43; // eax
  __int64 result; // rax
  int LastError; // eax
  const char *v46; // r9
  wil::details::in1diag3 *i; // rax
  wil::details::in1diag3 *v48; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-198h]
  int bIgnoreCasea; // [rsp+20h] [rbp-198h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-198h]
  __int64 v52; // [rsp+30h] [rbp-188h]
  __int64 v53; // [rsp+38h] [rbp-180h]
  __int64 v54; // [rsp+40h] [rbp-178h]
  char v55; // [rsp+50h] [rbp-168h]
  int v56; // [rsp+54h] [rbp-164h] BYREF
  wil::details::in1diag3 *v57; // [rsp+58h] [rbp-160h] BYREF
  wil::details::in1diag3 *v58; // [rsp+60h] [rbp-158h] BYREF
  int v59; // [rsp+68h] [rbp-150h] BYREF
  _WORD *v60; // [rsp+70h] [rbp-148h]
  int v61; // [rsp+78h] [rbp-140h] BYREF
  int v62; // [rsp+7Ch] [rbp-13Ch]
  __int64 v63; // [rsp+80h] [rbp-138h]
  LPCWSTR StringSid; // [rsp+88h] [rbp-130h] BYREF
  __int64 v65; // [rsp+90h] [rbp-128h] BYREF
  __int64 v66; // [rsp+98h] [rbp-120h] BYREF
  char **v67; // [rsp+A0h] [rbp-118h]
  void **v68; // [rsp+A8h] [rbp-110h] BYREF
  PSID Sid; // [rsp+B0h] [rbp-108h] BYREF
  void **v70; // [rsp+B8h] [rbp-100h] BYREF
  LPCWCH lpString2; // [rsp+C0h] [rbp-F8h]
  __int64 v72; // [rsp+C8h] [rbp-F0h]
  char *v73; // [rsp+D0h] [rbp-E8h]
  void **v74; // [rsp+D8h] [rbp-E0h] BYREF
  __int64 v75; // [rsp+E0h] [rbp-D8h]
  void **v76; // [rsp+E8h] [rbp-D0h] BYREF
  wil::details::in1diag3 *v77; // [rsp+F0h] [rbp-C8h]
  int v78[2]; // [rsp+F8h] [rbp-C0h] BYREF
  char *v79; // [rsp+100h] [rbp-B8h]
  wil::details::in1diag3 *v80; // [rsp+108h] [rbp-B0h]
  __int64 v81; // [rsp+110h] [rbp-A8h]
  char v82; // [rsp+118h] [rbp-A0h]
  __int64 v83; // [rsp+120h] [rbp-98h]
  char v84; // [rsp+128h] [rbp-90h] BYREF
  OLECHAR sz[8]; // [rsp+130h] [rbp-88h] BYREF
  __int128 v86; // [rsp+140h] [rbp-78h]
  __int128 v87; // [rsp+150h] [rbp-68h]
  _BYTE v88[30]; // [rsp+160h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  try
  {
    v6 = a4;
    v81 = a4;
    v60 = a3;
    LODWORD(v63) = a2;
    v72 = a1;
    v67 = a6;
    *a6 = 0;
    if ( !a3 || !*a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        (const char *)0x80070057LL,
        bIgnoreCase);
    v82 = 0;
    v83 = a4;
    if ( !(unsigned __int8)ImpersonationScope<LicenseIdentityContextTraits>::AlreadyImpersonating(retaddr) )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
      v82 = 1;
    }
    v11 = 0;
    v80 = 0;
    if ( a5 )
    {
      v12 = (char *)ClipKeyDocument::Get(&v57, a5);
      if ( &v84 != v12 )
      {
        v11 = *(wil::details::in1diag3 **)v12;
        *(_QWORD *)v12 = 0;
      }
      v80 = v11;
      v13 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    CreateQuery(&v76, L"%1=%2;%3=%4!d!", L"ContentId", a3);
    v14 = *(_QWORD *)(a1 + 24);
    v65 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v66 = 0;
    v15 = (char *)operator new(0x20u);
    *((_DWORD *)v15 + 2) = 1;
    *((_DWORD *)v15 + 3) = 1;
    *(_QWORD *)v15 = &std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable';
    v16 = (char **)(v15 + 16);
    *((_QWORD *)v15 + 2) = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    *((_QWORD *)v15 + 3) = 0;
    *(_QWORD *)v78 = v15 + 16;
    v79 = v15;
    v17 = *(__int64 **)(a1 + 24);
    v18 = *v17;
    v19 = v77;
    v58 = v77;
    v20 = v66;
    if ( !v66 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 24LL))(v65, &v66);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\ClipHelpers.h",
          (const char *)(unsigned int)v21,
          (int)L"LicenseType");
      v20 = v66;
      v19 = v58;
    }
    v22 = v15 + 24;
    bIgnoreCasea = (_DWORD)v15 + 24;
    v23 = (*(__int64 (__fastcall **)(__int64 *, __int64, wil::details::in1diag3 *, __int64))(v18 + 64))(
            v17,
            v20,
            v19,
            1);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCasea);
    if ( !*(_QWORD *)v22 || !**(_DWORD **)v22 )
    {
      v26 = -1;
      v24 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      v16 = v67;
      goto LABEL_55;
    }
    v22 = 0;
    v73 = 0;
    v62 = 0;
    v24 = 0;
    GetEffectiveToken((__int64)&v74);
    GetTokenSID(&v70, &v74);
    v6 = 0;
    v25 = 0;
    v26 = -1;
    while ( 1 )
    {
      v61 = v6;
      v27 = v16[1];
      if ( (unsigned int)v25 >= *(_DWORD *)v27 )
        break;
      *(_OWORD *)sz = 0;
      v86 = 0;
      v87 = 0;
      memset(v88, 0, sizeof(v88));
      StringSid = (LPCWSTR)(224 * v25);
      v58 = retaddr;
      if ( !StringFromGUID2((const GUID *const)&v27[224 * v25 + 32], sz, 39) )
        wil::details::in1diag3::Throw_Hr(
          v58,
          (void *)0xBF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          (const char *)0x8007007ALL,
          bIgnoreCasea);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0xC0u,
        "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
        (wchar_t *)L"Considering License ID %s for content ID %s...",
        sz,
        v60);
      v28 = v16[1];
      if ( *(_DWORD *)&v28[(_QWORD)StringSid + 4] != 6 )
      {
LABEL_69:
        v39 = HIDWORD(lpString2);
LABEL_70:
        HIDWORD(v52) = v39;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          0xC4u,
          "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
          (wchar_t *)L"Ignoring key for %s because it does not apply to %s");
        goto LABEL_41;
      }
      v29 = *(const WCHAR **)&v28[(_QWORD)StringSid + 160];
      if ( v29 )
      {
        v39 = HIDWORD(lpString2);
        StringSid = lpString2;
        if ( !lpString2 )
          goto LABEL_70;
        if ( CompareStringOrdinal(v29, v26, lpString2, v26, 0) != 2 )
        {
          v68 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
          Sid = 0;
          if ( !ConvertStringSidToSidW(StringSid, &Sid) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x24C,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
              v46);
          v55 = 0;
          for ( i = 0; ; i = (wil::details::in1diag3 *)((char *)v58 + 1) )
          {
            v58 = i;
            if ( (unsigned __int64)i >= 2 )
              break;
            if ( EqualSid((PSID)(68LL * (_QWORD)i + v72 + 32), Sid) )
            {
              v38 = 1;
              v55 = 1;
              goto LABEL_92;
            }
          }
          v38 = 0;
LABEL_92:
          v68 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
          if ( Sid )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v68) )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              RaiseException(LastError, 1u, 0, 0);
              goto LABEL_97;
            }
            Sid = 0;
            v38 = v55;
          }
          goto LABEL_68;
        }
      }
LABEL_26:
      v15 = 0;
      StringSid = 0;
      v58 = *(wil::details::in1diag3 **)(v72 + 24);
      MakeCom<ClipKeyDocument,IClipStore *,std::nullptr_t,unsigned int &,std::shared_ptr<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>> &>(
        (unsigned int)&v57,
        (unsigned int)&v58,
        (unsigned int)&StringSid,
        (unsigned int)&v61,
        (__int64)v78);
      v56 = 0;
      v59 = 0;
      v30 = (*(__int64 (__fastcall **)(wil::details::in1diag3 *, int *, int *))(*(_QWORD *)v57 + 48LL))(v57, &v56, &v59);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCB,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          (const char *)(unsigned int)v30,
          bIgnoreCaseb);
      v31 = v56;
      if ( v56 > (int)v63 )
      {
        if ( v11 )
        {
          v40 = (const void *)((*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)v57 + 2) + 24LL))((_QWORD *)v57 + 2)
                             + 28);
          v41 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)v11 + 2) + 24LL))((_QWORD *)v11 + 2);
          if ( !memcmp_0((const void *)(v41 + 28), v40, 0x10u) )
          {
            if ( v57 != v11 )
            {
              v58 = v11;
              Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v58);
              v48 = v57;
              v58 = v57;
              v57 = v11;
              if ( v58 )
                (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v48 + 16LL))(v48);
            }
            v42 = (*(__int64 (__fastcall **)(wil::details::in1diag3 *, int *, int *))(*(_QWORD *)v11 + 48LL))(
                    v11,
                    &v56,
                    &v59);
            if ( v42 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xD9,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
                (const char *)(unsigned int)v42,
                bIgnoreCaseb);
          }
          v31 = v56;
          v15 = 0;
        }
        if ( !v22 )
        {
          HIDWORD(v52) = HIDWORD(v60);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            0xDFu,
            "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
            (wchar_t *)L"Accepting key with License ID %s for Content ID %s (first match)");
LABEL_31:
          v32 = (char *)v57 + 8;
          if ( !v57 )
            v32 = v15;
          if ( v32 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v32 + 8LL))(v32);
          v33 = v22;
          v22 = v32;
          v73 = v32;
          if ( v33 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 16LL))(v33);
          v62 = v56;
          v24 = *(void ***)((char *)ClipDocument::LicenseData((wil::details::in1diag3 *)((char *)v57 + 32)) + 108);
          goto LABEL_38;
        }
        if ( v31 > v62 )
        {
          LODWORD(v54) = v62;
          HIDWORD(v52) = HIDWORD(v60);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            0xE5u,
            "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
            (wchar_t *)L"Accepting key with License ID %s for Content ID %s (better quality: %x vs %x)");
          goto LABEL_31;
        }
        if ( v31 == v62 )
        {
LABEL_97:
          if ( (__int64)v24 < *(_QWORD *)((char *)ClipDocument::LicenseData((wil::details::in1diag3 *)((char *)v57 + 32))
                                        + 108) )
          {
            HIDWORD(v52) = HIDWORD(v60);
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
              0xEDu,
              "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
              (wchar_t *)L"Accepting key with License ID %s for Content ID %s (newer)");
            goto LABEL_31;
          }
          v31 = v56;
        }
        LODWORD(v53) = v59;
        LODWORD(v52) = v31;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          0xFBu,
          "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
          (wchar_t *)L"Ignoring key for %s with quality %x (0x%08x) (no better than best)",
          v60,
          v52,
          v53,
          v54);
        goto LABEL_38;
      }
LABEL_49:
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x100u,
        "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
        (wchar_t *)L"Ignoring key for %s with quality %x (0x%08x)");
LABEL_38:
      v34 = v57;
      if ( v57 )
      {
        v57 = (wil::details::in1diag3 *)v15;
        (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v15 = v79;
      v16 = *(char ***)v78;
      LODWORD(v6) = v61;
LABEL_41:
      v6 = (unsigned int)(v6 + 1);
      v25 = (unsigned int)v6;
    }
    if ( v22 )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x106u,
        "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
        (wchar_t *)L"Returning key document for contentid %s",
        v60);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 8LL))(v22);
      v16 = v67;
      *v67 = v22;
    }
    else
    {
      v16 = v67;
    }
    v24 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    v70 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( lpString2 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v70) )
      {
        v35 = GetLastError();
        if ( v35 > 0 )
          v35 = (unsigned __int16)v35 | 0x80070000;
        RaiseException(v35, 1u, 0, 0);
        goto LABEL_49;
      }
      lpString2 = 0;
    }
    v74 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( v75 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v74) )
      {
        v43 = GetLastError();
        if ( v43 > 0 )
          v43 = (unsigned __int16)v43 | 0x80070000;
        RaiseException(v43, 1u, 0, 0);
LABEL_87:
        if ( v11 )
          (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v11 + 16LL))(v11);
        if ( v82 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
        return 0;
      }
      v75 = 0;
    }
    if ( v22 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
    v6 = v81;
LABEL_55:
    if ( !*v16 )
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x10Du,
        "ClipStorage::GetKeyDocumentForContentWithIdAndMinQuality",
        (wchar_t *)L"No key document found for contentid %s",
        v60);
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, v26) == 1 )
      {
        (**(void (__fastcall ***)(void *))v15)(v15);
        v26 = _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 3, v26);
        if ( v26 == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 32LL))(v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
    v76 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( !v77 )
      goto LABEL_87;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v76) )
    {
      v77 = 0;
      goto LABEL_87;
    }
    v37 = GetLastError();
    if ( v37 > 0 )
      v37 = (unsigned __int16)v37 | 0x80070000;
    RaiseException(v37, 1u, 0, 0);
LABEL_68:
    if ( !v38 )
      goto LABEL_69;
    goto LABEL_26;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x111,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
                           v36);
  }
  return result;
}

```

## disassembly

```asm
0x180011aa0  mov     [rsp+arg_8], rbx
0x180011aa5  mov     [rsp+arg_18], rsi
0x180011aaa  push    rdi
0x180011aab  push    r12
0x180011aad  push    r13
0x180011aaf  push    r14
0x180011ab1  push    r15
0x180011ab3  sub     rsp, 190h
0x180011aba  mov     rax, cs:__security_cookie
0x180011ac1  xor     rax, rsp
0x180011ac4  mov     [rsp+1B8h+var_38], rax
0x180011acc  mov     r13, r9
0x180011acf  mov     [rsp+1B8h+var_A8], r9
0x180011ad7  mov     rsi, r8
0x180011ada  mov     [rsp+1B8h+var_148], r8
0x180011adf  mov     dword ptr [rsp+1B8h+var_138], edx
0x180011ae6  mov     r12, rcx
0x180011ae9  mov     [rsp+1B8h+var_F0], rcx
0x180011af1  mov     rdi, [rsp+1B8h+arg_20]
0x180011af9  mov     rax, [rsp+1B8h+arg_28]
0x180011b01  mov     [rsp+1B8h+var_118], rax
0x180011b09  xor     r14d, r14d
0x180011b0c  mov     [rax], r14
0x180011b0f  test    r8, r8
0x180011b12  jnz     loc_1800121ED
0x180011b18  mov     al, 1
0x180011b1a  mov     rcx, [rsp+1B8h]; this
0x180011b22  test    al, al
0x180011b24  jnz     loc_18001254F
0x180011b2a  mov     [rsp+1B8h+var_A0], al
0x180011b31  mov     [rsp+1B8h+var_98], r13
0x180011b39  call    ?AlreadyImpersonating@?$ImpersonationScope@ULicenseIdentityContextTraits@@@@CA_NXZ; ImpersonationScope<LicenseIdentityContextTraits>::AlreadyImpersonating(void)
0x180011b3e  test    al, al
0x180011b40  jnz     short loc_180011B6A
0x180011b42  mov     rax, [r13+0]
0x180011b46  mov     rcx, r13
0x180011b49  mov     rax, [rax+18h]
0x180011b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b52  mov     rcx, [rsp+1B8h]; this
0x180011b5a  test    eax, eax
0x180011b5c  js      loc_1800122B7
0x180011b62  mov     [rsp+1B8h+var_A0], 1
0x180011b6a  mov     rbx, r14
0x180011b6d  mov     [rsp+1B8h+var_B0], rbx
0x180011b75  test    rdi, rdi
0x180011b78  jz      short loc_180011BBE
0x180011b7a  mov     rdx, rdi
0x180011b7d  lea     rcx, [rsp+1B8h+var_160]
0x180011b82  call    ?Get@ClipKeyDocument@@SA?AV?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@PEAUIStoredKeyDocument@@@Z; ClipKeyDocument::Get(IStoredKeyDocument *)
0x180011b87  lea     rcx, [rsp+1B8h+var_90]
0x180011b8f  cmp     rcx, rax
0x180011b92  jz      short loc_180011B9A
0x180011b94  mov     rbx, [rax]
0x180011b97  mov     [rax], r14
0x180011b9a  mov     [rsp+1B8h+var_B0], rbx
0x180011ba2  mov     rcx, [rsp+1B8h+var_160]
0x180011ba7  test    rcx, rcx
0x180011baa  jz      short loc_180011BBE
0x180011bac  mov     [rsp+1B8h+var_160], r14
0x180011bb1  mov     rax, [rcx]
0x180011bb4  mov     rax, [rax+10h]
0x180011bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bbd  nop
0x180011bbe  mov     dword ptr [rsp+1B8h+var_190], 1
0x180011bc6  lea     rax, aLicensetype; "LicenseType"
0x180011bcd  mov     qword ptr [rsp+1B8h+bIgnoreCase], rax; int
0x180011bd2  mov     r9, rsi
0x180011bd5  lea     r8, aContentid; "ContentId"
0x180011bdc  lea     rdx, a1234D; "%1=%2;%3=%4!d!"
0x180011be3  lea     rcx, [rsp+1B8h+var_D0]
0x180011beb  call    CreateQuery
0x180011bf0  nop
0x180011bf1  mov     rcx, [r12+18h]
0x180011bf6  mov     [rsp+1B8h+var_128], rcx
0x180011bfe  test    rcx, rcx
0x180011c01  jz      short loc_180011C10
0x180011c03  mov     rax, [rcx]
0x180011c06  mov     rax, [rax+8]
0x180011c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c0f  nop
0x180011c10  mov     [rsp+1B8h+var_120], r14
0x180011c18  mov     ecx, 20h ; ' '; Size
0x180011c1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011c22  mov     r14, rax
0x180011c25  mov     dword ptr [rax+8], 1
0x180011c2c  mov     dword ptr [rax+0Ch], 1
0x180011c33  lea     rax, ??_7?$_Ref_count_obj2@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable'
0x180011c3a  mov     [r14], rax
0x180011c3d  lea     r15, [r14+10h]
0x180011c41  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180011c48  mov     [r15], rax
0x180011c4b  mov     qword ptr [r15+8], 0
0x180011c53  mov     qword ptr [rsp+1B8h+var_C0], r15
0x180011c5b  mov     [rsp+1B8h+var_B8], r14
0x180011c63  mov     rsi, [r12+18h]
0x180011c68  mov     r12, [rsi]
0x180011c6b  mov     rax, [rsp+1B8h+var_C8]
0x180011c73  mov     [rsp+1B8h+var_158], rax
0x180011c78  mov     rdx, [rsp+1B8h+var_120]
0x180011c80  test    rdx, rdx
0x180011c83  jnz     short loc_180011CBE
0x180011c85  mov     rcx, [rsp+1B8h+var_128]
0x180011c8d  mov     rax, [rcx]
0x180011c90  lea     rdx, [rsp+1B8h+var_120]
0x180011c98  mov     rax, [rax+18h]
0x180011c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca1  mov     rcx, [rsp+1B8h]; this
0x180011ca9  test    eax, eax
0x180011cab  js      loc_1800122CC
0x180011cb1  mov     rdx, [rsp+1B8h+var_120]
0x180011cb9  mov     rax, [rsp+1B8h+var_158]
0x180011cbe  lea     rdi, [r15+8]
0x180011cc2  mov     qword ptr [rsp+1B8h+bIgnoreCase], rdi; int
0x180011cc7  mov     r9d, 1
0x180011ccd  mov     r8, rax
0x180011cd0  mov     rcx, rsi
0x180011cd3  mov     rax, [r12+40h]
0x180011cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cdd  mov     rcx, [rsp+1B8h]; this
0x180011ce5  test    eax, eax
0x180011ce7  js      loc_1800122E0
0x180011ced  mov     rax, [rdi]
0x180011cf0  test    rax, rax
0x180011cf3  jz      loc_1800120A3
0x180011cf9  cmp     dword ptr [rax], 0
0x180011cfc  jz      loc_1800120A3
0x180011d02  xor     edi, edi
0x180011d04  mov     [rsp+1B8h+var_E8], rdi
0x180011d0c  mov     [rsp+1B8h+var_13C], edi
0x180011d10  xor     esi, esi
0x180011d12  lea     rcx, [rsp+1B8h+var_E0]
0x180011d1a  call    ?GetEffectiveToken@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; GetEffectiveToken(void)
0x180011d1f  nop
0x180011d20  lea     rdx, [rsp+1B8h+var_E0]
0x180011d28  lea     rcx, [rsp+1B8h+var_100]
0x180011d30  call    ?GetTokenSID@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@234@@Z; GetTokenSID(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180011d35  nop
0x180011d36  xor     r13d, r13d
0x180011d39  xor     eax, eax
0x180011d3b  mov     r12d, 0FFFFFFFFh
0x180011d41  mov     [rsp+1B8h+var_140], r13d
0x180011d46  mov     rdx, [r15+8]
0x180011d4a  cmp     eax, [rdx]
0x180011d4c  jnb     loc_180011F9F
0x180011d52  xorps   xmm0, xmm0
0x180011d55  movups  xmmword ptr [rsp+1B8h+sz], xmm0
0x180011d5d  movups  [rsp+1B8h+var_78], xmm0
0x180011d65  movups  [rsp+1B8h+var_68], xmm0
0x180011d6d  movups  xmmword ptr [rsp+1B8h+var_58], xmm0
0x180011d75  movups  xmmword ptr [rsp+1B8h+var_58+0Eh], xmm0
0x180011d7d  imul    rax, 0E0h
0x180011d84  mov     [rsp+1B8h+StringSid], rax
0x180011d8c  mov     rcx, [rsp+1B8h]
0x180011d94  mov     [rsp+1B8h+var_158], rcx
0x180011d99  lea     rcx, [rax+20h]
0x180011d9d  add     rcx, rdx; rguid
0x180011da0  mov     r8d, 27h ; '''; cchMax
0x180011da6  lea     rdx, [rsp+1B8h+sz]; lpsz
0x180011dae  call    cs:__imp_StringFromGUID2
0x180011db4  test    eax, eax
0x180011db6  jz      loc_180012567
0x180011dbc  mov     rax, [rsp+1B8h+var_148]
0x180011dc1  mov     [rsp+1B8h+var_188], rax
0x180011dc6  lea     rax, [rsp+1B8h+sz]
0x180011dce  mov     [rsp+1B8h+var_190], rax
0x180011dd3  lea     rax, aConsideringLic; "Considering License ID %s for content I"...
0x180011dda  mov     qword ptr [rsp+1B8h+bIgnoreCase], rax; Format
0x180011ddf  lea     r9, aClipstorageGet_0; "ClipStorage::GetKeyDocumentForContentWi"...
0x180011de6  mov     r8d, 0C0h; unsigned int
0x180011dec  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180011df3  mov     ecx, 3; unsigned int
0x180011df8  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180011dfd  mov     rax, [r15+8]
0x180011e01  mov     rcx, [rsp+1B8h+StringSid]
0x180011e09  cmp     dword ptr [rcx+rax+4], 6
0x180011e0e  jnz     loc_1800121A7
0x180011e14  mov     rcx, [rcx+rax+0A0h]; lpString1
0x180011e1c  test    rcx, rcx
0x180011e1f  jnz     loc_180012583
0x180011e25  xor     r14d, r14d
0x180011e28  mov     [rsp+1B8h+StringSid], r14
0x180011e30  mov     rax, [rsp+1B8h+var_F0]
0x180011e38  mov     rax, [rax+18h]
0x180011e3c  mov     [rsp+1B8h+var_158], rax
0x180011e41  lea     rax, [rsp+1B8h+var_C0]
0x180011e49  mov     qword ptr [rsp+1B8h+bIgnoreCase], rax; int
0x180011e4e  lea     r9, [rsp+1B8h+var_140]
0x180011e53  lea     r8, [rsp+1B8h+StringSid]
0x180011e5b  lea     rdx, [rsp+1B8h+var_158]
0x180011e60  lea     rcx, [rsp+1B8h+var_160]
0x180011e65  call    ??$MakeCom@VClipKeyDocument@@PEAUIClipStore@@$$TAEAIAEAV?$shared_ptr@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@@@YA?AV?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@$$QEAPEAUIClipStore@@$$QEA$$TAEAIAEAV?$shared_ptr@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@@Z
0x180011e6a  nop
0x180011e6b  mov     [rsp+1B8h+var_164], r14d
0x180011e70  mov     [rsp+1B8h+var_150], r14d
0x180011e75  mov     rcx, [rsp+1B8h+var_160]
0x180011e7a  mov     rax, [rcx]
0x180011e7d  lea     r8, [rsp+1B8h+var_150]
0x180011e82  lea     rdx, [rsp+1B8h+var_164]
0x180011e87  mov     rax, [rax+30h]
0x180011e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e90  mov     rcx, [rsp+1B8h]; this
0x180011e98  test    eax, eax
0x180011e9a  js      loc_1800122F5
0x180011ea0  mov     ecx, [rsp+1B8h+var_164]
0x180011ea4  cmp     ecx, dword ptr [rsp+1B8h+var_138]
0x180011eab  jle     loc_180012051
0x180011eb1  test    rbx, rbx
0x180011eb4  jnz     loc_1800121FF
0x180011eba  test    rdi, rdi
0x180011ebd  jnz     loc_1800125FD
0x180011ec3  mov     rax, [rsp+1B8h+var_148]
0x180011ec8  mov     [rsp+1B8h+var_188], rax
0x180011ecd  lea     rax, [rsp+1B8h+sz]
0x180011ed5  mov     [rsp+1B8h+var_190], rax
0x180011eda  lea     rax, aAcceptingKeyWi_1; "Accepting key with License ID %s for Co"...
0x180011ee1  mov     qword ptr [rsp+1B8h+bIgnoreCase], rax; Format
0x180011ee6  lea     r9, aClipstorageGet_0; "ClipStorage::GetKeyDocumentForContentWi"...
0x180011eed  mov     r8d, 0DFh; unsigned int
0x180011ef3  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180011efa  mov     ecx, 3; unsigned int
0x180011eff  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180011f04  mov     rcx, [rsp+1B8h+var_160]
0x180011f09  lea     rsi, [rcx+8]
0x180011f0d  test    rcx, rcx
0x180011f10  cmovz   rsi, r14
0x180011f14  test    rsi, rsi
0x180011f17  jz      short loc_180011F29
0x180011f19  mov     rax, [rsi]
0x180011f1c  mov     rcx, rsi
0x180011f1f  mov     rax, [rax+8]
0x180011f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f28  nop
0x180011f29  mov     rcx, rdi
0x180011f2c  mov     rdi, rsi
0x180011f2f  mov     [rsp+1B8h+var_E8], rsi
0x180011f37  test    rcx, rcx
0x180011f3a  jz      short loc_180011F49
0x180011f3c  mov     rax, [rcx]
0x180011f3f  mov     rax, [rax+10h]
0x180011f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f48  nop
0x180011f49  mov     eax, [rsp+1B8h+var_164]
0x180011f4d  mov     [rsp+1B8h+var_13C], eax
0x180011f51  mov     rcx, [rsp+1B8h+var_160]
0x180011f56  add     rcx, 20h ; ' '; this
0x180011f5a  call    ?LicenseData@ClipDocument@@QEAAAEBU_tagCLIP_LICENSE_DATA@@XZ; ClipDocument::LicenseData(void)
0x180011f5f  mov     rsi, [rax+6Ch]
0x180011f63  mov     rcx, [rsp+1B8h+var_160]
0x180011f68  test    rcx, rcx
0x180011f6b  jz      short loc_180011F7F
0x180011f6d  mov     [rsp+1B8h+var_160], r14
0x180011f72  mov     rax, [rcx]
0x180011f75  mov     rax, [rax+10h]
0x180011f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f7e  nop
0x180011f7f  mov     r14, [rsp+1B8h+var_B8]
0x180011f87  mov     r15, qword ptr [rsp+1B8h+var_C0]
0x180011f8f  mov     r13d, [rsp+1B8h+var_140]
0x180011f94  inc     r13d
0x180011f97  mov     eax, r13d
0x180011f9a  jmp     loc_180011D41
0x180011f9f  test    rdi, rdi
0x180011fa2  jz      loc_180012096
0x180011fa8  mov     rax, [rsp+1B8h+var_148]
0x180011fad  mov     [rsp+1B8h+var_190], rax
0x180011fb2  lea     rax, aReturningKeyDo; "Returning key document for contentid %s"
0x180011fb9  mov     qword ptr [rsp+1B8h+bIgnoreCase], rax; Format
0x180011fbe  lea     r9, aClipstorageGet_0; "ClipStorage::GetKeyDocumentForContentWi"...
0x180011fc5  mov     r8d, 106h; unsigned int
0x180011fcb  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180011fd2  mov     ecx, 3; unsigned int
0x180011fd7  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180011fdc  nop
0x180011fdd  mov     rax, [rdi]
0x180011fe0  mov     rcx, rdi
0x180011fe3  mov     rax, [rax+8]
0x180011fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fec  nop
0x180011fed  mov     r15, [rsp+1B8h+var_118]
0x180011ff5  mov     [r15], rdi
0x180011ff8  lea     rsi, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180011fff  mov     [rsp+1B8h+var_100], rsi
0x180012007  cmp     [rsp+1B8h+lpString2], 0
0x180012010  jz      loc_18001231E
0x180012016  lea     rcx, [rsp+1B8h+var_100]
0x18001201e  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x180012023  test    al, al
0x180012025  jnz     loc_1800126A4
0x18001202b  call    cs:__imp_GetLastError
0x180012031  test    eax, eax
0x180012033  jle     short loc_18001203D
0x180012035  movzx   eax, ax
0x180012038  or      eax, 80070000h
0x18001203d  xor     r9d, r9d; lpArguments
0x180012040  xor     r8d, r8d; nNumberOfArguments
0x180012043  mov     edx, 1; dwExceptionFlags
0x180012048  mov     ecx, eax; dwExceptionCode
0x18001204a  call    cs:__imp_RaiseException
0x180012050  nop
0x180012051  mov     eax, [rsp+1B8h+var_150]
  ... truncated ...
```
