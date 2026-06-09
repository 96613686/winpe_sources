# ClipStorage::GetLeaseDocumentsForKeyDocument(IStoredKeyDocument *,ILicenseIdentityContext *,ulong *,IStoredLeaseDocument * * *)

- ea: `0x1800107b0`
- end: `0x180011953`
- name: `?GetLeaseDocumentsForKeyDocument@ClipStorage@@UEAAJPEAUIStoredKeyDocument@@PEAUILicenseIdentityContext@@PEAKPEAPEAPEAUIStoredLeaseDocument@@@Z`
- size: `4515`
- prototype: `__int64 __fastcall(ClipStorage *__hidden this, struct IStoredKeyDocument *, struct ILicenseIdentityContext *, unsigned int *, struct IStoredLeaseDocument ***)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004738`
- `0x18000c70c`
- `0x18000e40c`
- `0x18000f07c`
- `0x18000f164`
- `0x18000f4f0`
- `0x180010250`
- `0x1800104c8`
- `0x1800107b0`
- `0x180011960`
- `0x1800119e0`
- `0x180011a00`
- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x180026a48`
- `0x1800279ec`
- `0x180054a54`
- `0x1800593bc`
- `0x18006b1a4`
- `0x180075e60`
- `0x1800767e0`
- `0x1800769f4`
- `0x180076a00`
- `0x18008251f`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180010f71`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180010f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800108a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010ecc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011283`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001130e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800113c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011613`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800108a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010ecc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011283`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001130e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800113c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010836`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010852`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010852`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001183c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001183c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011881`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011881`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010978`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010fde`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010978`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010fde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001111d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001111d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001117b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001117b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011792`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011792`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001174b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001174b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180011706`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180011706`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall ClipStorage::GetLeaseDocumentsForKeyDocument(
        ClipStorage *this,
        struct IStoredKeyDocument *a2,
        struct ILicenseIdentityContext *a3,
        unsigned int *a4,
        struct IStoredLeaseDocument ***a5)
{
  ClipLeaseDocument *k; // rdi
  volatile signed __int32 *v6; // rsi
  unsigned __int64 v8; // r13
  HANDLE CurrentThread; // rax
  BOOL v10; // eax
  int LastError; // eax
  void **v12; // r15
  __int64 v13; // r12
  __int64 i; // rax
  _DWORD *v15; // rdx
  __int64 v16; // rax
  volatile signed __int32 *v17; // r13
  _DWORD *v18; // rcx
  const wchar_t *v19; // rcx
  __int64 v20; // r13
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  char *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rcx
  int QualityImpl; // eax
  int v28; // eax
  __int64 v29; // rax
  void **v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  __int64 *v34; // rsi
  __int64 v35; // r14
  __int64 v36; // r12
  __int64 v37; // rdx
  int v38; // eax
  unsigned int **v39; // r15
  int v40; // eax
  int v41; // eax
  unsigned __int64 *v42; // r14
  __int64 v43; // rdx
  int v44; // eax
  int v45; // eax
  unsigned int *v46; // rax
  int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rcx
  char *v50; // rcx
  unsigned int *v51; // rdx
  void **v52; // rax
  int v53; // eax
  int v54; // eax
  const char *v55; // r9
  int v56; // eax
  __int64 v57; // rcx
  __int64 result; // rax
  unsigned __int64 v59; // rax
  const WCHAR *v60; // r8
  unsigned int *v61; // rcx
  LPCWCH *v62; // rcx
  __int64 v63; // rax
  _OWORD *v64; // r13
  unsigned __int64 v65; // r12
  int v66; // eax
  int v67; // eax
  const char *v68; // r9
  ClipLeaseDocument *j; // rax
  const WCHAR *v70; // r13
  int bIgnoreCase; // [rsp+20h] [rbp-208h]
  int bIgnoreCasea; // [rsp+20h] [rbp-208h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-208h]
  OLECHAR *v74; // [rsp+28h] [rbp-200h]
  int TokenInformation; // [rsp+50h] [rbp-1D8h] BYREF
  int v76; // [rsp+54h] [rbp-1D4h] BYREF
  DWORD ReturnLength[2]; // [rsp+58h] [rbp-1D0h] BYREF
  ClipLeaseDocument *v78; // [rsp+60h] [rbp-1C8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1C0h] BYREF
  int v80; // [rsp+70h] [rbp-1B8h]
  unsigned __int8 v81; // [rsp+74h] [rbp-1B4h]
  void **v82; // [rsp+78h] [rbp-1B0h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-1A8h] BYREF
  __int64 v84; // [rsp+88h] [rbp-1A0h] BYREF
  __int64 v85; // [rsp+90h] [rbp-198h] BYREF
  __int64 v86; // [rsp+98h] [rbp-190h] BYREF
  __int64 v87; // [rsp+A0h] [rbp-188h] BYREF
  ClipStorage *v88; // [rsp+A8h] [rbp-180h]
  unsigned int *v89; // [rsp+B0h] [rbp-178h]
  __int64 v90; // [rsp+B8h] [rbp-170h] BYREF
  void **v91; // [rsp+C0h] [rbp-168h] BYREF
  LPCWSTR StringSid; // [rsp+C8h] [rbp-160h]
  void **v93; // [rsp+D0h] [rbp-158h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-150h]
  void **v95; // [rsp+E0h] [rbp-148h] BYREF
  __int64 v96; // [rsp+E8h] [rbp-140h]
  void **v97; // [rsp+F0h] [rbp-138h] BYREF
  __int64 v98; // [rsp+F8h] [rbp-130h]
  int v99[2]; // [rsp+100h] [rbp-128h] BYREF
  struct IStoredKeyDocument *v100; // [rsp+108h] [rbp-120h]
  volatile signed __int32 *v101; // [rsp+110h] [rbp-118h] BYREF
  volatile signed __int32 *v102; // [rsp+118h] [rbp-110h]
  struct IStoredLeaseDocument ***v103; // [rsp+120h] [rbp-108h]
  struct ILicenseIdentityContext *v104; // [rsp+128h] [rbp-100h]
  char v105; // [rsp+130h] [rbp-F8h]
  struct ILicenseIdentityContext *v106; // [rsp+138h] [rbp-F0h]
  void **v107; // [rsp+140h] [rbp-E8h]
  int v108; // [rsp+148h] [rbp-E0h]
  _QWORD pExceptionObject[3]; // [rsp+150h] [rbp-D8h] BYREF
  char v110; // [rsp+168h] [rbp-C0h] BYREF
  LPCWCH lpString2[2]; // [rsp+170h] [rbp-B8h] BYREF
  unsigned __int64 v112; // [rsp+180h] [rbp-A8h]
  unsigned __int64 v113; // [rsp+188h] [rbp-A0h]
  OLECHAR sz[8]; // [rsp+190h] [rbp-98h] BYREF
  __int128 v115; // [rsp+1A0h] [rbp-88h]
  __int128 v116; // [rsp+1B0h] [rbp-78h]
  _BYTE v117[30]; // [rsp+1C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v89 = a4;
  v6 = (volatile signed __int32 *)a3;
  v104 = a3;
  v8 = (unsigned __int64)this;
  v88 = this;
  v103 = a5;
  *a4 = 0;
  *a5 = 0;
  v105 = 0;
  v106 = a3;
  LOBYTE(k) = 0;
  v82 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v10 = OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle);
  try
  {
    if ( v10 )
    {
      TokenInformation = 0;
      ReturnLength[0] = 4;
      if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, ReturnLength) )
        LOBYTE(k) = TokenInformation == 2;
    }
    v82 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( !TokenHandle
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v82) )
    {
      if ( !(_BYTE)k )
      {
        v31 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 24LL))(v6);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CF,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
            (const char *)(unsigned int)v31,
            bIgnoreCase);
        v105 = 1;
      }
      pv = 0;
      v32 = (*(__int64 (__fastcall **)(struct IStoredKeyDocument *, LPVOID *))(*(_QWORD *)a2 + 104LL))(a2, &pv);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          (const char *)(unsigned int)v32,
          bIgnoreCase);
      ClipKeyDocument::Get(&v90, a2);
      v74 = *(OLECHAR **)((char *)ClipDocument::LicenseData((ClipDocument *)(v90 + 32)) + 140);
      CreateQuery(&v97, L"%1=%2!d!;%3=%4", L"LicenseType", 3);
      v33 = *(_QWORD *)(v8 + 24);
      v84 = v33;
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
      v85 = 0;
      a2 = (struct IStoredKeyDocument *)operator new(0x20u);
      *((_DWORD *)a2 + 2) = 1;
      *((_DWORD *)a2 + 3) = 1;
      *(_QWORD *)a2 = &std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable';
      k = (struct IStoredKeyDocument *)((char *)a2 + 16);
      *((_QWORD *)a2 + 2) = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      *((_QWORD *)a2 + 3) = 0;
      *(_QWORD *)v99 = (char *)a2 + 16;
      v100 = a2;
      v34 = *(__int64 **)(v8 + 24);
      v35 = *v34;
      v36 = v98;
      v37 = v85;
      if ( !v85 )
      {
        v38 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v84 + 24LL))(v84, &v85);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\ClipHelpers.h",
            (const char *)(unsigned int)v38,
            (int)L"AssociatePFM");
        v37 = v85;
      }
      v39 = (unsigned int **)((char *)a2 + 24);
      v40 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v35 + 64))(v34, v37, v36, 1);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          (const char *)(unsigned int)v40,
          (_DWORD)a2 + 24);
      CreateQuery(&v95, L"%1=%2;%3=%4!d!", L"ContentId", pv);
      v6 = (volatile signed __int32 *)operator new(0x20u);
      *((_DWORD *)v6 + 2) = 1;
      *((_DWORD *)v6 + 3) = 1;
      *(_QWORD *)v6 = &std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable';
      v41 = (_DWORD)v6 + 16;
      *((_QWORD *)v6 + 2) = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
      *((_QWORD *)v6 + 3) = 0;
      v101 = v6 + 4;
      v102 = v6;
      v42 = *(unsigned __int64 **)(v8 + 24);
      v8 = *v42;
      v13 = v96;
      v43 = v85;
      if ( !v85 )
      {
        v44 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v84 + 24LL))(v84, &v85);
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\ClipHelpers.h",
            (const char *)(unsigned int)v44,
            (int)L"LicenseType");
        v43 = v85;
        v41 = (_DWORD)v6 + 16;
      }
      bIgnoreCase = v41 + 8;
      v45 = (*(__int64 (__fastcall **)(unsigned __int64 *, __int64, __int64, __int64))(v8 + 64))(v42, v43, v13, 1);
      if ( v45 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          (const char *)(unsigned int)v45,
          bIgnoreCase);
      GetEffectiveToken(&v93);
      GetTokenSID(&v91, &v93);
      v46 = *v39;
      if ( !*v39 )
      {
        v46 = (unsigned int *)*((_QWORD *)v6 + 3);
        if ( !v46 )
          goto LABEL_51;
      }
      v8 = *v46;
      v80 = v8;
      if ( !(_DWORD)v8 )
        goto LABEL_51;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
    }
    v12 = 0;
    v107 = 0;
    v108 = v8;
    if ( (_DWORD)v8 )
    {
      v52 = (void **)CoTaskMemAlloc(8 * v8);
      v12 = v52;
      v107 = v52;
      if ( !v52 )
      {
        pExceptionObject[2] = 0;
        pExceptionObject[1] = "bad allocation";
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      memset_0(v52, 0, 8 * v8);
    }
    LODWORD(v13) = 0;
    for ( i = 0; ; i = (unsigned int)v13 )
    {
      TokenInformation = v13;
      v15 = (_DWORD *)*((_QWORD *)k + 1);
      if ( !v15 || (unsigned int)i >= *v15 )
        break;
      *(_OWORD *)sz = 0;
      v115 = 0;
      v116 = 0;
      memset(v117, 0, sizeof(v117));
      v20 = 224 * i;
      v78 = retaddr;
      if ( !StringFromGUID2((const GUID *const)&v15[56 * i + 8], sz, 39) )
        wil::details::in1diag3::Throw_Hr(
          v78,
          (void *)0x171,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          (const char *)0x8007007ALL,
          bIgnoreCase);
      v21 = *((_QWORD *)k + 1);
      if ( *(_DWORD *)(v21 + v20 + 4) != 6 )
      {
LABEL_59:
        v74 = sz;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          0x191u,
          "ClipStorage::GetLeaseDocumentsForKeyDocument",
          (wchar_t *)L"Ignoring matching lease (%s) for Content ID %s because it is doesn't apply to this user");
        goto LABEL_63;
      }
      v22 = *(const WCHAR **)(v21 + v20 + 160);
      if ( v22 )
      {
        v70 = StringSid;
        if ( !StringSid )
          goto LABEL_59;
        if ( CompareStringOrdinal(v22, -1, StringSid, -1, 0) != 2 )
        {
          v82 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
          TokenHandle = 0;
          if ( !ConvertStringSidToSidW(v70, &TokenHandle) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x24C,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
              v68);
          LOBYTE(v8) = 0;
          for ( j = 0; ; j = (ClipLeaseDocument *)((char *)v78 + 1) )
          {
            v78 = j;
            if ( (unsigned __int64)j >= 2 )
              break;
            if ( EqualSid((char *)v88 + 68 * (_QWORD)j + 32, TokenHandle) )
            {
              LOBYTE(v8) = 1;
              break;
            }
          }
          v82 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
          if ( TokenHandle )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v82) )
            {
              v66 = GetLastError();
              if ( v66 > 0 )
                v66 = (unsigned __int16)v66 | 0x80070000;
              RaiseException(v66, 1u, 0, 0);
              goto LABEL_142;
            }
            TokenHandle = 0;
          }
LABEL_58:
          if ( !(_BYTE)v8 )
            goto LABEL_59;
        }
      }
      v87 = 0;
      v78 = 0;
      *(_QWORD *)ReturnLength = *((_QWORD *)v88 + 3);
      v23 = (char *)MakeCom<ClipLeaseDocument,IClipStore *,std::nullptr_t,unsigned int &,std::shared_ptr<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>> &>(
                      (unsigned int)&v86,
                      (unsigned int)ReturnLength,
                      (unsigned int)&v78,
                      (unsigned int)&TokenInformation,
                      (__int64)v99);
      v24 = 0;
      if ( &v110 != v23 )
      {
        v24 = *(_QWORD *)v23;
        *(_QWORD *)v23 = 0;
      }
      v25 = v24;
      v87 = v24;
      v26 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      if ( *(int *)(v24 + 152) < 0 )
        goto LABEL_27;
      v76 = 0;
      QualityImpl = ClipDocument::GetQualityImpl(
                      (ClipDocument *)(v24 + 48),
                      (enum LicenseQuality *)&v76,
                      (int *)ReturnLength);
      if ( QualityImpl < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\ClipDocument.h",
          (const char *)(unsigned int)QualityImpl,
          bIgnoreCasea);
      if ( v76 > 0x10000000 )
      {
        v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v24 + 24) + 24LL))(v24 + 24);
        v64 = (_OWORD *)v63;
        *(_OWORD *)lpString2 = 0;
        v112 = 0;
        v113 = 0;
        v65 = *(_QWORD *)(v63 + 16);
        if ( *(_QWORD *)(v63 + 24) > 7u )
          v64 = *(_OWORD **)v63;
        if ( v65 > 0x7FFFFFFFFFFFFFFELL )
          std::_Xlength_error("string too long");
        if ( v65 > 7 )
        {
          v78 = (ClipLeaseDocument *)std::wstring::_Calculate_growth(v65, 7);
          lpString2[0] = (LPCWCH)std::allocator<unsigned short>::allocate(lpString2, (char *)v78 + 1);
          v112 = v65;
          v113 = (unsigned __int64)v78;
          memcpy_0((void *)lpString2[0], v64, 2 * v65 + 2);
          v59 = v113;
          v65 = v112;
        }
        else
        {
          v112 = *(_QWORD *)(v63 + 16);
          v59 = 7;
          v113 = 7;
          *(_OWORD *)lpString2 = *v64;
        }
        if ( !v65 )
          goto LABEL_129;
        v60 = (const WCHAR *)lpString2;
        if ( v59 > 7 )
          v60 = lpString2[0];
        if ( CompareStringOrdinal((LPCWCH)pv, -1, v60, v65, 1) != 2 )
        {
          v62 = lpString2;
          if ( v113 > 7 )
            v62 = (LPCWCH *)lpString2[0];
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            0x17Fu,
            "ClipStorage::GetLeaseDocumentsForKeyDocument",
            (wchar_t *)L"Ignoring matching lease (%s) for Content ID %s because it doesn't match the key content id %s",
            sz,
            v62,
            pv);
        }
        else
        {
LABEL_129:
          v74 = sz;
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            0x183u,
            "ClipStorage::GetLeaseDocumentsForKeyDocument",
            (wchar_t *)L"Adding lease %s to results");
          v25 = 0;
          v61 = v89;
          v12[*v89] = (void *)(v24 + 8);
          ++*v61;
        }
        if ( v113 > 7 )
          std::_Deallocate<16>(lpString2[0], 2 * v113 + 2);
      }
      else
      {
LABEL_27:
        ReturnLength[0] = 0;
        v76 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, DWORD *, int *))(*(_QWORD *)v24 + 48LL))(v24, ReturnLength, &v76);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x18B,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            (const char *)(unsigned int)v28,
            bIgnoreCasea);
        v74 = sz;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          0x18Cu,
          "ClipStorage::GetLeaseDocumentsForKeyDocument",
          (wchar_t *)L"Ignoring otherwise matching lease (%s) for Content ID %s because of quality %d (0x%08x)");
      }
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      a2 = v100;
      k = *(ClipLeaseDocument **)v99;
      LODWORD(v13) = TokenInformation;
LABEL_63:
      LODWORD(v13) = v13 + 1;
    }
    k = 0;
    v16 = 0;
    v17 = v6 + 4;
    while ( 1 )
    {
      TokenInformation = (int)k;
      v18 = (_DWORD *)*((_QWORD *)v17 + 1);
      if ( !v18 || (unsigned int)v16 >= *v18 )
        break;
      v13 = 224 * v16;
      v19 = *(const wchar_t **)&v18[56 * v16 + 44];
      if ( v19
        && wcsstr(v19, L"\"productAddOns\"")
        && ClipStorage::ResultAppliesToUser(
             v88,
             (const struct _tagCLIP_LICENSE_DATA *)(v13 + *((_QWORD *)v17 + 1) + 4LL),
             StringSid) )
      {
        memset_0(sz, 0, 0x4Eu);
        if ( !StringFromGUID2((const GUID *const)(v13 + *((_QWORD *)v17 + 1) + 32LL), sz, 39) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x19D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            (const char *)0x8007007ALL,
            bIgnoreCase);
        v78 = 0;
        v87 = 0;
        *(_QWORD *)ReturnLength = *((_QWORD *)v88 + 3);
        v48 = MakeCom<ClipLeaseDocument,IClipStore *,std::nullptr_t,unsigned int &,std::shared_ptr<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>> &>(
                (unsigned int)&v86,
                (unsigned int)ReturnLength,
                (unsigned int)&v87,
                (unsigned int)&TokenInformation,
                (__int64)&v101);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&v78, v48);
        v49 = v86;
        if ( v86 )
        {
          v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        k = v78;
        if ( ClipLeaseDocument::IsValid(v78) )
        {
          v74 = sz;
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            0x1A3u,
            "ClipStorage::GetLeaseDocumentsForKeyDocument",
            (wchar_t *)L"Adding migrated lease %s to results");
          v78 = 0;
          v50 = (char *)k + 8;
          if ( !k )
            v50 = 0;
          v51 = v89;
          v12[*v89] = v50;
          ++*v51;
          k = 0;
LABEL_145:
          if ( k )
            (*(void (__fastcall **)(ClipLeaseDocument *))(*(_QWORD *)k + 16LL))(k);
          v6 = v102;
          v17 = v101;
          LODWORD(k) = TokenInformation;
          goto LABEL_15;
        }
LABEL_142:
        v76 = 0;
        ReturnLength[0] = 0;
        v67 = (*(__int64 (__fastcall **)(ClipLeaseDocument *, int *, DWORD *))(*(_QWORD *)k + 48LL))(
                k,
                &v76,
                ReturnLength);
        if ( v67 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
            (const char *)(unsigned int)v67,
            bIgnoreCaseb);
        v74 = sz;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
          0x1ABu,
          "ClipStorage::GetLeaseDocumentsForKeyDocument",
          (wchar_t *)L"Ignoring otherwise matching migrated lease (%s) for Content ID %s because of quality %d (0x%08x)");
        goto LABEL_145;
      }
LABEL_15:
      k = (ClipLeaseDocument *)(unsigned int)((_DWORD)k + 1);
      v16 = (unsigned int)k;
    }
    v29 = *v89;
    if ( (_DWORD)v29 )
    {
      if ( (unsigned int)v29 > 1 )
        std::_Sort_unchecked_IStoredLeaseDocument______lambda_2cc577d8b51c420dd27d24c389f57d6c___(
          v12,
          &v12[v29],
          (unsigned int)v29,
          v81);
      v30 = v12;
      v12 = 0;
      LODWORD(v8) = 0;
      *v103 = (struct IStoredLeaseDocument **)v30;
    }
    else
    {
      LODWORD(v8) = v80;
    }
    if ( v12 )
    {
      for ( k = 0; (unsigned int)k < (unsigned int)v8; k = (ClipLeaseDocument *)(unsigned int)((_DWORD)k + 1) )
      {
        v13 = (__int64)&v12[(_QWORD)k];
        if ( *(_QWORD *)v13 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 16LL))(*(_QWORD *)v13);
        *(_QWORD *)v13 = 0;
      }
      CoTaskMemFree(v12);
    }
LABEL_51:
    if ( *v89 )
    {
      LODWORD(v74) = *v89;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x1CCu,
        "ClipStorage::GetLeaseDocumentsForKeyDocument",
        (wchar_t *)L"Returning %d lease documents for contentid %s",
        v74,
        pv);
    }
    else
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        0x1C8u,
        "ClipStorage::GetLeaseDocumentsForKeyDocument",
        (wchar_t *)L"No lease documents found for contentid %s",
        pv);
    }
    v12 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    v91 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( !StringSid )
      goto LABEL_90;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v91) )
    {
      v47 = GetLastError();
      if ( v47 > 0 )
        v47 = (unsigned __int16)v47 | 0x80070000;
      RaiseException(v47, 1u, 0, 0);
      goto LABEL_58;
    }
    StringSid = 0;
LABEL_90:
    v93 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( v94 )
    {
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v93) )
      {
        v94 = 0;
      }
      else
      {
        v53 = GetLastError();
        if ( v53 > 0 )
          v53 = (unsigned __int16)v53 | 0x80070000;
        RaiseException(v53, 1u, 0, 0);
      }
    }
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    v95 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( v96 )
    {
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v95) )
      {
        v96 = 0;
      }
      else
      {
        v54 = GetLastError();
        if ( v54 > 0 )
          v54 = (unsigned __int16)v54 | 0x80070000;
        RaiseException(v54, 1u, 0, 0);
      }
    }
    if ( a2 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(struct IStoredKeyDocument *))a2)(a2);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(struct IStoredKeyDocument *))(*(_QWORD *)a2 + 8LL))(a2);
      }
    }
    if ( v85 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 32LL))(v84);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v84);
    v97 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( v98 )
    {
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v97) )
      {
        v98 = 0;
      }
      else
      {
        v56 = GetLastError();
        if ( v56 > 0 )
          v56 = (unsigned __int16)v56 | 0x80070000;
        RaiseException(v56, 1u, 0, 0);
      }
    }
    v57 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v105 )
      (*(void (__fastcall **)(struct ILicenseIdentityContext *))(*(_QWORD *)v104 + 32LL))(v104);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1D0,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
                           v55);
  }
  return result;
}

```

## disassembly

```asm
0x1800107b0  push    rbx
0x1800107b2  push    rsi
0x1800107b3  push    rdi
0x1800107b4  push    r12
0x1800107b6  push    r13
0x1800107b8  push    r14
0x1800107ba  push    r15
0x1800107bc  sub     rsp, 1F0h
0x1800107c3  mov     rax, cs:__security_cookie
0x1800107ca  xor     rax, rsp
0x1800107cd  mov     [rsp+228h+var_48], rax
0x1800107d5  mov     [rsp+228h+var_178], r9
0x1800107dd  mov     rsi, r8
0x1800107e0  mov     [rsp+228h+var_100], r8
0x1800107e8  mov     rbx, rdx
0x1800107eb  mov     r13, rcx
0x1800107ee  mov     [rsp+228h+var_180], rcx
0x1800107f6  mov     rcx, [rsp+228h+arg_20]
0x1800107fe  mov     [rsp+228h+var_108], rcx
0x180010806  xor     r14d, r14d
0x180010809  mov     [r9], r14d
0x18001080c  mov     [rcx], r14
0x18001080f  mov     [rsp+228h+var_F8], r14b
0x180010817  mov     [rsp+228h+var_F0], r8
0x18001081f  xor     dil, dil
0x180010822  lea     r15, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010829  mov     [rsp+228h+var_1B0], r15
0x18001082e  mov     [rsp+228h+TokenHandle], r14
0x180010836  call    cs:__imp_GetCurrentThread
0x18001083c  lea     r9, [rsp+228h+TokenHandle]; TokenHandle
0x180010844  mov     edx, 20008h; DesiredAccess
0x180010849  mov     r8d, 1; OpenAsSelf
0x18001084f  mov     rcx, rax; ThreadHandle
0x180010852  call    cs:__imp_OpenThreadToken
0x180010858  test    eax, eax
0x18001085a  jnz     loc_180011763
0x180010860  mov     [rsp+228h+var_1B0], r15
0x180010865  cmp     [rsp+228h+TokenHandle], 0
0x18001086e  jz      loc_180010B4A
0x180010874  lea     rcx, [rsp+228h+var_1B0]
0x180010879  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18001087e  test    al, al
0x180010880  jnz     loc_180010B4A
0x180010886  call    cs:__imp_GetLastError
0x18001088c  test    eax, eax
0x18001088e  jle     short loc_180010898
0x180010890  movzx   eax, ax
0x180010893  or      eax, 80070000h
0x180010898  xor     r9d, r9d; lpArguments
0x18001089b  xor     r8d, r8d; nNumberOfArguments
0x18001089e  mov     edx, 1; dwExceptionFlags
0x1800108a3  mov     ecx, eax; dwExceptionCode
0x1800108a5  call    cs:__imp_RaiseException
0x1800108ab  nop
0x1800108ac  xor     r15d, r15d
0x1800108af  mov     [rsp+228h+var_E8], r15
0x1800108b7  mov     [rsp+228h+var_E0], r13d
0x1800108bf  test    r13d, r13d
0x1800108c2  jnz     loc_180011113
0x1800108c8  xor     r12d, r12d
0x1800108cb  xor     eax, eax
0x1800108cd  mov     r14d, 0FFFFFFFFh
0x1800108d3  mov     [rsp+228h+TokenInformation], r12d
0x1800108d8  mov     rdx, [rdi+8]
0x1800108dc  test    rdx, rdx
0x1800108df  jnz     short loc_180010920
0x1800108e1  xor     edi, edi
0x1800108e3  xor     eax, eax
0x1800108e5  lea     r13, [rsi+10h]
0x1800108e9  mov     [rsp+228h+TokenInformation], edi
0x1800108ed  mov     rcx, [r13+8]
0x1800108f1  test    rcx, rcx
0x1800108f4  jz      loc_180010AFC
0x1800108fa  cmp     eax, [rcx]
0x1800108fc  jnb     loc_180010AFC
0x180010902  imul    r12, rax, 0E0h
0x180010909  mov     rcx, [r12+rcx+0B0h]; Str
0x180010911  test    rcx, rcx
0x180010914  jnz     loc_180010F6A
0x18001091a  inc     edi
0x18001091c  mov     eax, edi
0x18001091e  jmp     short loc_1800108E9
0x180010920  cmp     eax, [rdx]
0x180010922  jnb     short loc_1800108E1
0x180010924  xorps   xmm0, xmm0
0x180010927  movups  xmmword ptr [rsp+228h+sz], xmm0
0x18001092f  movups  [rsp+228h+var_88], xmm0
0x180010937  movups  [rsp+228h+var_78], xmm0
0x18001093f  movups  xmmword ptr [rsp+228h+var_68], xmm0
0x180010947  movups  xmmword ptr [rsp+228h+var_68+0Eh], xmm0
0x18001094f  imul    r13, rax, 0E0h
0x180010956  mov     rax, [rsp+228h]
0x18001095e  mov     [rsp+228h+var_1C8], rax
0x180010963  lea     rcx, [rdx+20h]
0x180010967  add     rcx, r13; rguid
0x18001096a  mov     r8d, 27h ; '''; cchMax
0x180010970  lea     rdx, [rsp+228h+sz]; lpsz
0x180010978  call    cs:__imp_StringFromGUID2
0x18001097e  test    eax, eax
0x180010980  jz      loc_1800117FE
0x180010986  mov     rax, [rdi+8]
0x18001098a  cmp     dword ptr [rax+r13+4], 6
0x180010990  jnz     loc_180010EDC
0x180010996  mov     rcx, [rax+r13+0A0h]; lpString1
0x18001099e  test    rcx, rcx
0x1800109a1  jnz     loc_18001181A
0x1800109a7  xor     r12d, r12d
0x1800109aa  mov     [rsp+228h+var_188], r12
0x1800109b2  mov     [rsp+228h+var_1C8], r12
0x1800109b7  mov     rax, [rsp+228h+var_180]
0x1800109bf  mov     rax, [rax+18h]
0x1800109c3  mov     qword ptr [rsp+228h+ReturnLength], rax
0x1800109c8  lea     rax, [rsp+228h+var_128]
0x1800109d0  mov     qword ptr [rsp+228h+bIgnoreCase], rax; int
0x1800109d5  lea     r9, [rsp+228h+TokenInformation]
0x1800109da  lea     r8, [rsp+228h+var_1C8]
0x1800109df  lea     rdx, [rsp+228h+ReturnLength]
0x1800109e4  lea     rcx, [rsp+228h+var_190]
0x1800109ec  call    ??$MakeCom@VClipLeaseDocument@@PEAUIClipStore@@$$TAEAIAEAV?$shared_ptr@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@@@YA?AV?$ComPtr@VClipLeaseDocument@@@WRL@Microsoft@@$$QEAPEAUIClipStore@@$$QEA$$TAEAIAEAV?$shared_ptr@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@@Z
0x1800109f1  mov     ebx, r12d
0x1800109f4  lea     rcx, [rsp+228h+var_C0]
0x1800109fc  cmp     rcx, rax
0x1800109ff  jz      short loc_180010A07
0x180010a01  mov     rbx, [rax]
0x180010a04  mov     [rax], r12
0x180010a07  mov     rdi, rbx
0x180010a0a  mov     [rsp+228h+var_188], rbx
0x180010a12  mov     rcx, [rsp+228h+var_190]
0x180010a1a  test    rcx, rcx
0x180010a1d  jz      short loc_180010A34
0x180010a1f  mov     [rsp+228h+var_190], r12
0x180010a27  mov     rax, [rcx]
0x180010a2a  mov     rax, [rax+10h]
0x180010a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a33  nop
0x180010a34  cmp     dword ptr [rbx+98h], 0
0x180010a3b  jl      short loc_180010A73
0x180010a3d  mov     [rsp+228h+var_1D4], r12d
0x180010a42  lea     rcx, [rbx+30h]; this
0x180010a46  lea     r8, [rsp+228h+ReturnLength]; int *
0x180010a4b  lea     rdx, [rsp+228h+var_1D4]; enum LicenseQuality *
0x180010a50  call    ?GetQualityImpl@ClipDocument@@QEAAJPEAW4LicenseQuality@@PEAJ@Z; ClipDocument::GetQualityImpl(LicenseQuality *,long *)
0x180010a55  mov     rcx, [rsp+228h]; this
0x180010a5d  test    eax, eax
0x180010a5f  js      loc_18001120C
0x180010a65  cmp     [rsp+228h+var_1D4], 10000000h
0x180010a6d  jg      loc_180011582
0x180010a73  mov     [rsp+228h+ReturnLength], r12d
0x180010a78  mov     [rsp+228h+var_1D4], r12d
0x180010a7d  mov     rax, [rbx]
0x180010a80  lea     r8, [rsp+228h+var_1D4]
0x180010a85  lea     rdx, [rsp+228h+ReturnLength]
0x180010a8a  mov     rcx, rbx
0x180010a8d  mov     rax, [rax+30h]
0x180010a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a96  mov     rcx, [rsp+228h]; this
0x180010a9e  test    eax, eax
0x180010aa0  js      loc_180011220
0x180010aa6  mov     eax, [rsp+228h+var_1D4]
0x180010aaa  mov     [rsp+228h+var_1E8], eax
0x180010aae  mov     eax, [rsp+228h+ReturnLength]
0x180010ab2  mov     [rsp+228h+var_1F0], eax
0x180010ab6  mov     rax, [rsp+228h+pv]
0x180010abb  mov     [rsp+228h+var_1F8], rax
0x180010ac0  lea     rax, [rsp+228h+sz]
0x180010ac8  mov     [rsp+228h+var_200], rax
0x180010acd  lea     rax, aIgnoringOtherw_0; "Ignoring otherwise matching lease (%s) "...
0x180010ad4  mov     qword ptr [rsp+228h+bIgnoreCase], rax; Format
0x180010ad9  lea     r9, aClipstorageGet; "ClipStorage::GetLeaseDocumentsForKeyDoc"...
0x180010ae0  mov     r8d, 18Ch; unsigned int
0x180010ae6  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180010aed  mov     ecx, 3; unsigned int
0x180010af2  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180010af7  jmp     loc_180010F35
0x180010afc  mov     rax, [rsp+228h+var_178]
0x180010b04  mov     eax, [rax]
0x180010b06  test    eax, eax
0x180010b08  jz      loc_180011186
0x180010b0e  cmp     eax, 1
0x180010b11  jbe     short loc_180010B28
0x180010b13  mov     r8d, eax
0x180010b16  lea     rdx, [r15+rax*8]
0x180010b1a  movzx   r9d, [rsp+228h+var_1B4]
0x180010b20  mov     rcx, r15
0x180010b23  call    std___Sort_unchecked_IStoredLeaseDocument______lambda_2cc577d8b51c420dd27d24c389f57d6c___
0x180010b28  mov     rax, r15
0x180010b2b  xor     r15d, r15d
0x180010b2e  xor     r13d, r13d
0x180010b31  mov     rcx, [rsp+228h+var_108]
0x180010b39  mov     [rcx], rax
0x180010b3c  test    r15, r15
0x180010b3f  jnz     loc_180011149
0x180010b45  jmp     loc_180010E2F
0x180010b4a  test    dil, dil
0x180010b4d  jnz     short loc_180010B76
0x180010b4f  mov     rax, [rsi]
0x180010b52  mov     rcx, rsi
0x180010b55  mov     rax, [rax+18h]
0x180010b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b5e  mov     rcx, [rsp+228h]; this
0x180010b66  test    eax, eax
0x180010b68  js      loc_180011190
0x180010b6e  mov     [rsp+228h+var_F8], 1
0x180010b76  mov     [rsp+228h+pv], r14
0x180010b7b  mov     rax, [rbx]
0x180010b7e  lea     rdx, [rsp+228h+pv]
0x180010b83  mov     rcx, rbx
0x180010b86  mov     rax, [rax+68h]
0x180010b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b8f  mov     rcx, [rsp+228h]; this
0x180010b97  test    eax, eax
0x180010b99  js      loc_1800111A5
0x180010b9f  mov     rdx, rbx
0x180010ba2  lea     rcx, [rsp+228h+var_170]
0x180010baa  call    ?Get@ClipKeyDocument@@SA?AV?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@PEAUIStoredKeyDocument@@@Z; ClipKeyDocument::Get(IStoredKeyDocument *)
0x180010baf  nop
0x180010bb0  mov     rcx, [rsp+228h+var_170]
0x180010bb8  add     rcx, 20h ; ' '; this
0x180010bbc  call    ?LicenseData@ClipDocument@@QEAAAEBU_tagCLIP_LICENSE_DATA@@XZ; ClipDocument::LicenseData(void)
0x180010bc1  mov     rax, [rax+8Ch]
0x180010bc8  mov     [rsp+228h+var_200], rax
0x180010bcd  lea     rax, aAssociatepfm; "AssociatePFM"
0x180010bd4  mov     qword ptr [rsp+228h+bIgnoreCase], rax; int
0x180010bd9  mov     r9d, 3
0x180010bdf  lea     r8, aLicensetype; "LicenseType"
0x180010be6  lea     rdx, a12D34; "%1=%2!d!;%3=%4"
0x180010bed  lea     rcx, [rsp+228h+var_138]
0x180010bf5  call    CreateQuery
0x180010bfa  nop
0x180010bfb  mov     rcx, [r13+18h]
0x180010bff  mov     [rsp+228h+var_1A0], rcx
0x180010c07  test    rcx, rcx
0x180010c0a  jz      short loc_180010C19
0x180010c0c  mov     rax, [rcx]
0x180010c0f  mov     rax, [rax+8]
0x180010c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c18  nop
0x180010c19  mov     [rsp+228h+var_198], r14
0x180010c21  mov     ecx, 20h ; ' '; Size
0x180010c26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010c2b  mov     rbx, rax
0x180010c2e  mov     dword ptr [rax+8], 1
0x180010c35  mov     dword ptr [rax+0Ch], 1
0x180010c3c  lea     rax, ??_7?$_Ref_count_obj2@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable'
0x180010c43  mov     [rbx], rax
0x180010c46  lea     rdi, [rbx+10h]
0x180010c4a  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180010c51  mov     [rdi], rax
0x180010c54  mov     [rdi+8], r14
0x180010c58  mov     qword ptr [rsp+228h+var_128], rdi
0x180010c60  mov     [rsp+228h+var_120], rbx
0x180010c68  mov     rsi, [r13+18h]
0x180010c6c  mov     r14, [rsi]
0x180010c6f  mov     r12, [rsp+228h+var_130]
0x180010c77  mov     rdx, [rsp+228h+var_198]
0x180010c7f  test    rdx, rdx
0x180010c82  jnz     short loc_180010CB8
0x180010c84  mov     rcx, [rsp+228h+var_1A0]
0x180010c8c  mov     rax, [rcx]
0x180010c8f  lea     rdx, [rsp+228h+var_198]
0x180010c97  mov     rax, [rax+18h]
0x180010c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ca0  mov     rcx, [rsp+228h]; this
0x180010ca8  test    eax, eax
0x180010caa  js      loc_1800111BA
0x180010cb0  mov     rdx, [rsp+228h+var_198]
0x180010cb8  lea     r15, [rdi+8]
0x180010cbc  mov     qword ptr [rsp+228h+bIgnoreCase], r15; int
0x180010cc1  mov     r9d, 1
0x180010cc7  mov     r8, r12
0x180010cca  mov     rcx, rsi
0x180010ccd  mov     rax, [r14+40h]
0x180010cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd6  mov     rcx, [rsp+228h]; this
0x180010cde  test    eax, eax
0x180010ce0  js      loc_1800111CE
0x180010ce6  mov     dword ptr [rsp+228h+var_200], 1
0x180010cee  lea     rax, aLicensetype; "LicenseType"
0x180010cf5  mov     qword ptr [rsp+228h+bIgnoreCase], rax; int
0x180010cfa  mov     r9, [rsp+228h+pv]
0x180010cff  lea     r8, aContentid; "ContentId"
0x180010d06  lea     rdx, a1234D; "%1=%2;%3=%4!d!"
0x180010d0d  lea     rcx, [rsp+228h+var_148]
0x180010d15  call    CreateQuery
0x180010d1a  nop
0x180010d1b  mov     ecx, 20h ; ' '; Size
0x180010d20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d25  mov     rsi, rax
0x180010d28  mov     dword ptr [rax+8], 1
0x180010d2f  mov     dword ptr [rax+0Ch], 1
0x180010d36  lea     rax, ??_7?$_Ref_count_obj2@V?$HandleT@UClipLicenseResultsTraits@@@Wrappers@WRL@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::WRL::Wrappers::HandleT<ClipLicenseResultsTraits>>::`vftable'
0x180010d3d  mov     [rsi], rax
0x180010d40  lea     rax, [rsi+10h]
0x180010d44  lea     rcx, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180010d4b  mov     [rax], rcx
0x180010d4e  mov     qword ptr [rax+8], 0
0x180010d56  mov     [rsp+228h+var_118], rax
0x180010d5e  mov     [rsp+228h+var_110], rsi
0x180010d66  mov     r14, [r13+18h]
0x180010d6a  mov     r13, [r14]
  ... truncated ...
```
