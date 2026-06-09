# DeclaredConfigurationStore_ConstructPriorityRulesStorage(DeclaredConfigurationScopeData *,DCPriorityRulesDocument *)

- ea: `0x180066550`
- end: `0x180067157`
- name: `?DeclaredConfigurationStore_ConstructPriorityRulesStorage@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCPriorityRulesDocument@@@Z`
- size: `3079`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCPriorityRulesDocument *)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config`

## callees

- `0x18000b9e0`
- `0x1800117bc`
- `0x1800117dc`
- `0x180013b44`
- `0x180014348`
- `0x1800143c8`
- `0x18001440c`
- `0x180018a70`
- `0x180018ac0`
- `0x18001ace4`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180055540`
- `0x180059cf4`
- `0x180066550`
- `0x180071708`
- `0x180071b94`
- `0x180071c4c`
- `0x180071e0c`
- `0x180072198`
- `0x18007b7f4`
- `0x180100ad8`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800666aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800666aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180066ce6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180066fc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180066ce6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180066fc2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180066d04`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180066fe0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180066d04`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180066fe0`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180066d33`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180067027`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180066d33`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180067027`

## string_xrefs

- `0x18006674a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800669f4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180066ab2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180066ff2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall DeclaredConfigurationStore_ConstructPriorityRulesStorage(
        struct DeclaredConfigurationScopeData *a1,
        struct DCPriorityRulesDocument *a2)
{
  char *v3; // rdx
  int LastError; // ebx
  int RegistryString; // ebx
  LSTATUS v6; // eax
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  const unsigned __int16 *v10; // r9
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r9
  int v14; // eax
  const unsigned __int16 *v15; // r9
  int v16; // eax
  struct DCPriorityRulesDocument *v17; // rdx
  unsigned __int64 v18; // r15
  unsigned __int64 i; // rsi
  __int64 v20; // rax
  int v21; // r14d
  __int64 v22; // r8
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  const unsigned __int16 *v25; // r9
  int v26; // eax
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  unsigned __int64 v29; // r13
  unsigned __int64 j; // rbx
  __int64 v31; // r8
  const unsigned __int16 *v32; // rdx
  int v33; // esi
  int v34; // ebx
  struct DCPriorityRulesDocument *v35; // rax
  _QWORD *v36; // rbx
  _QWORD *v37; // rsi
  _QWORD *v38; // rcx
  unsigned __int16 **v39; // r8
  _QWORD *v40; // rbx
  _QWORD *v41; // rsi
  unsigned __int16 **v42; // r8
  _QWORD *v43; // rcx
  const unsigned __int16 *v44; // rdx
  int EnrollmentIdDocIdKeyRegardlessOfState; // ebx
  const unsigned __int16 *v46; // rdx
  int ResultsDocIdKeyRegardlessOfState; // ebx
  _QWORD *v48; // r14
  _QWORD *v49; // rax
  const char *v50; // r9
  unsigned __int64 k; // rbx
  unsigned __int64 m; // rbx
  const unsigned __int16 *v53; // r9
  const char *v54; // r9
  const char *v55; // r9
  int v57; // [rsp+20h] [rbp-198h]
  char *v58; // [rsp+30h] [rbp-188h] BYREF
  struct DCPriorityRulesDocument *v59; // [rsp+38h] [rbp-180h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-178h] BYREF
  unsigned __int16 *v61; // [rsp+48h] [rbp-170h] BYREF
  HKEY v62; // [rsp+50h] [rbp-168h] BYREF
  __int64 v63; // [rsp+58h] [rbp-160h] BYREF
  HKEY v64; // [rsp+60h] [rbp-158h] BYREF
  unsigned __int16 *v65; // [rsp+68h] [rbp-150h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-148h] BYREF
  __int64 v67; // [rsp+78h] [rbp-140h] BYREF
  _QWORD v68[3]; // [rsp+80h] [rbp-138h] BYREF
  char v69; // [rsp+98h] [rbp-120h]
  HKEY v70; // [rsp+A0h] [rbp-118h] BYREF
  HKEY v71; // [rsp+A8h] [rbp-110h] BYREF
  struct _FILETIME FileTime; // [rsp+B0h] [rbp-108h] BYREF
  struct _FILETIME v73; // [rsp+B8h] [rbp-100h] BYREF
  _QWORD *v74; // [rsp+C0h] [rbp-F8h] BYREF
  HKEY *v75; // [rsp+C8h] [rbp-F0h] BYREF
  HKEY v76; // [rsp+D0h] [rbp-E8h] BYREF
  char v77; // [rsp+D8h] [rbp-E0h]
  _QWORD *v78; // [rsp+E0h] [rbp-D8h] BYREF
  _QWORD *v79; // [rsp+E8h] [rbp-D0h]
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-C0h] BYREF
  char v81; // [rsp+108h] [rbp-B0h]
  unsigned __int16 *v82[2]; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v83; // [rsp+120h] [rbp-98h]
  unsigned __int64 v84; // [rsp+128h] [rbp-90h]
  _QWORD Src[4]; // [rsp+130h] [rbp-88h] BYREF
  unsigned __int16 *v86[4]; // [rsp+150h] [rbp-68h] BYREF
  SYSTEMTIME v87; // [rsp+170h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v59 = a2;
  LODWORD(v58) = 0;
  hKey = 0;
  v62 = 0;
  v64 = 0;
  v67 = 0;
  v68[0] = &v58;
  v68[1] = &v59;
  v68[2] = &hKey;
  v69 = 1;
  if ( !a1 || !a2 )
  {
    LastError = -2147024809;
    LODWORD(v58) = -2147024809;
    goto LABEL_122;
  }
  *(_QWORD *)&SystemTime.wYear = &hKey;
  *(_QWORD *)&SystemTime.wHour = 0;
  v81 = 1;
  v3 = (char *)a2 + 32;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  LODWORD(v58) = DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdKey(
                   a1,
                   (const unsigned __int16 *)v3,
                   (HKEY *)&SystemTime.wHour,
                   0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
  LastError = (int)v58;
  if ( (_DWORD)v58 == -2147024894 )
  {
    LODWORD(v58) = 0;
  }
  else if ( (int)v58 < 0 )
  {
    goto LABEL_122;
  }
  if ( hKey )
  {
    lpSubKey = 0;
    *(_QWORD *)&SystemTime.wYear = &lpSubKey;
    *(_QWORD *)&SystemTime.wHour = 0;
    v81 = 1;
    RegistryString = DCCDNUtil_GetRegistryString(hKey, 0, L"version", (unsigned __int16 **)&SystemTime.wHour);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&SystemTime);
    if ( RegistryString >= 0 )
    {
      v6 = RegDeleteTreeW(hKey, lpSubKey);
      LastError = v6;
      if ( v6 )
      {
        if ( v6 > 0 )
          LastError = (unsigned __int16)v6 | 0x80070000;
        LODWORD(v58) = LastError;
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
        goto LABEL_122;
      }
    }
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  }
  *(_QWORD *)&SystemTime.wYear = &hKey;
  *(_QWORD *)&SystemTime.wHour = 0;
  v81 = 1;
  v7 = (const unsigned __int16 *)((char *)v59 + 32);
  if ( *((_QWORD *)v59 + 7) > 7u )
    v7 = *(const unsigned __int16 **)v7;
  LODWORD(v58) = DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdKey(a1, v7, (HKEY *)&SystemTime.wHour, 1);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
  LastError = (int)v58;
  if ( (int)v58 < 0 )
  {
    v8 = 5064;
LABEL_19:
    v9 = (unsigned int)LastError;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)v9,
      v57);
    goto LABEL_122;
  }
  v10 = (const unsigned __int16 *)((char *)v59 + 64);
  if ( *((_QWORD *)v59 + 11) > 7u )
    v10 = *(const unsigned __int16 **)v10;
  v11 = DCCDNUtil_SetRegistryString(hKey, 0, L"version", v10, 0);
  LastError = v11;
  LODWORD(v58) = v11;
  if ( v11 < 0 )
  {
    v9 = (unsigned int)v11;
    v8 = 5067;
    goto LABEL_20;
  }
  *(_QWORD *)&SystemTime.wYear = &v62;
  *(_QWORD *)&SystemTime.wHour = 0;
  v81 = 1;
  v12 = (const unsigned __int16 *)((char *)v59 + 32);
  if ( *((_QWORD *)v59 + 7) > 7u )
    v12 = *(const unsigned __int16 **)v12;
  LODWORD(v58) = DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionKey(
                   a1,
                   v12,
                   (HKEY *)&SystemTime.wHour,
                   1);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
  LastError = (int)v58;
  if ( (int)v58 < 0 )
  {
    v8 = 5074;
    goto LABEL_19;
  }
  v13 = (const unsigned __int16 *)v59;
  if ( *((_QWORD *)v59 + 3) > 7u )
    v13 = *(const unsigned __int16 **)v59;
  v14 = DCCDNUtil_SetRegistryString(v62, 0, L"schemaVersion", v13, 0);
  LastError = v14;
  LODWORD(v58) = v14;
  if ( v14 < 0 )
  {
    v9 = (unsigned int)v14;
    v8 = 5077;
    goto LABEL_20;
  }
  v15 = (const unsigned __int16 *)((char *)v59 + 96);
  if ( *((_QWORD *)v59 + 15) > 7u )
    v15 = *(const unsigned __int16 **)v15;
  v16 = DCCDNUtil_SetRegistryString(v62, 0, L"osDefinedScenario", v15, 0);
  LastError = v16;
  LODWORD(v58) = v16;
  if ( v16 < 0 )
  {
    v9 = (unsigned int)v16;
    v8 = 5080;
    goto LABEL_20;
  }
  v17 = v59;
  v18 = 0x8E38E38E38E38E39uLL * ((__int64)(*((_QWORD *)v59 + 22) - *((_QWORD *)v59 + 21)) >> 3);
  for ( i = 0; i < v18; ++i )
  {
    v20 = *((_QWORD *)v17 + 21);
    v21 = *(_DWORD *)(v20 + 72 * i);
    std::wstring::wstring((__int64)v86, (_QWORD *)(v20 + 40 + 72 * i));
    *(_QWORD *)&SystemTime.wYear = &v64;
    *(_QWORD *)&SystemTime.wHour = 0;
    v81 = 1;
    v22 = *((_QWORD *)v59 + 21) + 8LL + 72 * i;
    if ( *(_QWORD *)(v22 + 24) > 7u )
      v22 = *(_QWORD *)v22;
    v23 = (const unsigned __int16 *)((char *)v59 + 32);
    if ( *((_QWORD *)v59 + 7) > 7u )
      v23 = *(const unsigned __int16 **)v23;
    LODWORD(v58) = DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionOrderedDocIdKey(
                     a1,
                     v23,
                     (const unsigned __int16 *)v22,
                     (HKEY *)&SystemTime.wHour,
                     1);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
    LastError = (int)v58;
    if ( (int)v58 < 0 )
    {
      v27 = (unsigned int)v58;
      v28 = 5094;
      goto LABEL_52;
    }
    v24 = DCCDNUtil_SetRegistryDWORD(v64, 0, L"ranking", v21);
    LastError = v24;
    LODWORD(v58) = v24;
    if ( v24 < 0 )
    {
      v27 = (unsigned int)v24;
      v28 = 5097;
      goto LABEL_52;
    }
    v25 = (const unsigned __int16 *)v86;
    if ( v86[3] > (unsigned __int16 *)7 )
      v25 = v86[0];
    v26 = DCCDNUtil_SetRegistryString(v64, 0, L"customCR", v25, 0);
    LastError = v26;
    LODWORD(v58) = v26;
    if ( v26 < 0 )
    {
      v27 = (unsigned int)v26;
      v28 = 5100;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)v27,
        v57);
      std::wstring::_Tidy_deallocate(v86);
      goto LABEL_122;
    }
    std::wstring::_Tidy_deallocate(v86);
    v17 = v59;
  }
  v29 = (__int64)(*((_QWORD *)v17 + 25) - *((_QWORD *)v17 + 24)) >> 5;
  for ( j = 0; j < v29; ++j )
  {
    *(_QWORD *)&SystemTime.wYear = &v67;
    *(_QWORD *)&SystemTime.wHour = 0;
    v81 = 1;
    v31 = *((_QWORD *)v17 + 24) + 32 * j;
    if ( *(_QWORD *)(v31 + 24) > 7u )
      v31 = *(_QWORD *)v31;
    v32 = (const unsigned __int16 *)((char *)v17 + 32);
    if ( *((_QWORD *)v32 + 3) > 7u )
      v32 = *(const unsigned __int16 **)v32;
    LODWORD(v58) = DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionUnorderedDocIdKey(
                     a1,
                     v32,
                     (const unsigned __int16 *)v31,
                     (HKEY *)&SystemTime.wHour,
                     v57);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
    v33 = (int)v58;
    if ( (int)v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v58,
        v57);
      LastError = v33;
      goto LABEL_122;
    }
    v17 = v59;
  }
  v63 = 0;
  *(_QWORD *)&SystemTime.wYear = &v63;
  *(_QWORD *)&SystemTime.wHour = 0;
  v81 = 1;
  v34 = DCCDNUtil_GetRegistryString(hKey, 0, L"ListOfWindcDocs", (unsigned __int16 **)&SystemTime.wHour);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&SystemTime);
  if ( v34 >= 0 )
  {
    std::vector<ConfigDoc>::vector<ConfigDoc>(&v78);
    try
    {
      dmtl::split<std::back_insert_iterator<std::vector<std::wstring>>,unsigned short>(&v74, v63, 59, &v78);
      v48 = v78;
      v49 = v79;
      v74 = v79;
      while ( v48 != v49 )
      {
        std::wstring::wstring((__int64)v82, v48);
        v35 = v59;
        v36 = (_QWORD *)*((_QWORD *)v59 + 21);
        v37 = (_QWORD *)*((_QWORD *)v59 + 22);
        if ( v36 != v37 )
        {
          do
          {
            v38 = v36 + 1;
            v39 = v82;
            if ( v84 > 7 )
              v39 = (unsigned __int16 **)v82[0];
            if ( v36[4] > 7u )
              v38 = (_QWORD *)*v38;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v38, v36[3], v39, v83) )
              break;
            v36 += 9;
          }
          while ( v36 != v37 );
          v35 = v59;
        }
        if ( v36 == *((_QWORD **)v35 + 22) )
        {
          v40 = (_QWORD *)*((_QWORD *)v35 + 24);
          v41 = (_QWORD *)*((_QWORD *)v35 + 25);
          if ( v40 != v41 )
          {
            do
            {
              v42 = v82;
              if ( v84 > 7 )
                v42 = (unsigned __int16 **)v82[0];
              if ( v40[3] <= 7u )
                v43 = v40;
              else
                v43 = (_QWORD *)*v40;
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v43, v40[2], v42, v83) )
                break;
              v40 += 4;
            }
            while ( v40 != v41 );
            v35 = v59;
          }
          if ( v40 == *((_QWORD **)v35 + 25) )
          {
            v71 = 0;
            v70 = 0;
            *(_QWORD *)&SystemTime.wYear = &v70;
            *(_QWORD *)&SystemTime.wHour = 0;
            v81 = 1;
            v44 = (const unsigned __int16 *)v82;
            if ( v84 > 7 )
              v44 = v82[0];
            EnrollmentIdDocIdKeyRegardlessOfState = DeclaredConfigurationStore_GetEnrollmentIdDocIdKeyRegardlessOfState(
                                                      a1,
                                                      v44,
                                                      (HKEY *)&SystemTime.wHour);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
            if ( EnrollmentIdDocIdKeyRegardlessOfState >= 0 )
            {
              SystemTime = 0;
              GetLocalTime(&SystemTime);
              FileTime = 0;
              if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
              {
                v61 = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &v61,
                  0);
                FileTimeToISO8601String(&FileTime, 0, &v61);
                if ( (int)DCCDNUtil_SetRegistryString(v70, 0, L"requestTimeStamp", v61, 0) >= 0 )
                {
                  v75 = &v71;
                  v76 = 0;
                  v77 = 1;
                  v46 = (const unsigned __int16 *)v82;
                  if ( v84 > 7 )
                    v46 = v82[0];
                  ResultsDocIdKeyRegardlessOfState = DeclaredConfigurationStore_GetResultsDocIdKeyRegardlessOfState(
                                                       a1,
                                                       v46,
                                                       &v76);
                  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v75);
                  if ( ResultsDocIdKeyRegardlessOfState >= 0 )
                    DCCDNUtil_SetRegistryDWORD(v71, 0, L"State", 40);
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v70);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
          }
        }
        std::wstring::_Tidy_deallocate(v82);
        v48 += 4;
        v49 = v74;
      }
      std::vector<std::wstring>::_Tidy(&v78);
    }
    catch ( ... )
    {
      LODWORD(v61) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x1421,
                       (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declare"
                                     "dconfigurationapi.cpp",
                       v50);
      goto LABEL_118;
    }
  }
  try
  {
    std::wstring::wstring((__int64)Src);
    for ( k = 0; k < v18; k = 1 )
    {
      if ( k )
        std::wstring::_Append<unsigned short>(Src);
      std::wstring::_Append<unsigned short>(Src);
    }
    for ( m = 0; m < v29; ++m )
    {
      if ( m )
      {
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Append<unsigned short>(Src);
      }
      else
      {
        if ( v18 )
          std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Append<unsigned short>(Src);
      }
    }
    v53 = (const unsigned __int16 *)Src;
    if ( Src[3] > 7u )
      v53 = (const unsigned __int16 *)Src[0];
    LODWORD(v58) = DCCDNUtil_SetRegistryString(hKey, 0, L"ListOfWindcDocs", v53, 0);
  }
  catch ( ... )
  {
    LODWORD(v61) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x1449,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredc"
                                   "onfigurationapi.cpp",
                     v54);
    std::wstring::_Tidy_deallocate(Src);
LABEL_118:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v63);
    if ( v69 )
    {
      v69 = 0;
      lambda_b4d438a28537cf5237a0445c30a05489_::operator()(v68);
    }
    LastError = (int)v61;
    goto LABEL_123;
  }
  v87 = 0;
  GetLocalTime(&v87);
  v73 = 0;
  if ( SystemTimeToFileTime(&v87, &v73) )
  {
    v65 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v65,
      0);
    FileTimeToISO8601String(&v73, 0, &v65);
    LastError = DCCDNUtil_SetRegistryString(v62, 0, L"requestTimeStamp", v65, 0);
    LODWORD(v58) = LastError;
    if ( LastError >= 0 )
    {
      LastError = DCCDNUtil_SetRegistryDWORD(v62, 0, L"State", 46);
      LODWORD(v58) = LastError;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x144F,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconf"
                                "igurationapi.cpp",
                  v55);
  }
  std::wstring::_Tidy_deallocate(Src);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v63);
LABEL_122:
  v69 = 0;
  lambda_b4d438a28537cf5237a0445c30a05489_::operator()(v68);
LABEL_123:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v64);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180066550  mov     r11, rsp
0x180066553  mov     [r11+18h], rbx
0x180066557  mov     [r11+20h], rsi
0x18006655b  push    rdi
0x18006655c  push    r12
0x18006655e  push    r13
0x180066560  push    r14
0x180066562  push    r15
0x180066564  sub     rsp, 190h
0x18006656b  mov     rax, cs:__security_cookie
0x180066572  xor     rax, rsp
0x180066575  mov     [rsp+1B8h+var_38], rax
0x18006657d  mov     r12, rcx
0x180066580  mov     [rsp+1B8h+var_180], rdx
0x180066585  xor     edi, edi
0x180066587  mov     dword ptr [rsp+1B8h+var_188], edi
0x18006658b  mov     [rsp+1B8h+hKey], rdi
0x180066590  mov     [rsp+1B8h+var_168], rdi
0x180066595  mov     [rsp+1B8h+var_158], rdi
0x18006659a  mov     [rsp+1B8h+var_140], rdi
0x18006659f  lea     rax, [rsp+1B8h+var_188]
0x1800665a4  mov     [r11-138h], rax
0x1800665ab  lea     rax, [rsp+1B8h+var_180]
0x1800665b0  mov     [r11-130h], rax
0x1800665b7  lea     rax, [rsp+1B8h+hKey]
0x1800665bc  mov     [r11-128h], rax
0x1800665c3  lea     r14d, [rdi+1]
0x1800665c7  mov     [r11-120h], r14b
0x1800665ce  test    rcx, rcx
0x1800665d1  jz      loc_1800670DE
0x1800665d7  test    rdx, rdx
0x1800665da  jz      loc_1800670DE
0x1800665e0  lea     rax, [rsp+1B8h+hKey]
0x1800665e5  mov     [r11-0C0h], rax
0x1800665ec  mov     [r11-0B8h], rdi
0x1800665f3  mov     [r11-0B0h], r14b
0x1800665fa  add     rdx, 20h ; ' '
0x1800665fe  cmp     qword ptr [rdx+18h], 7
0x180066603  jbe     short loc_180066608
0x180066605  mov     rdx, [rdx]; unsigned __int16 *
0x180066608  xor     r9d, r9d; int
0x18006660b  lea     r8, [rsp+1B8h+SystemTime.wHour]; HKEY *
0x180066613  call    ?DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180066618  mov     dword ptr [rsp+1B8h+var_188], eax
0x18006661c  lea     rcx, [rsp+1B8h+SystemTime]
0x180066624  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180066629  mov     ebx, dword ptr [rsp+1B8h+var_188]
0x18006662d  cmp     ebx, 80070002h
0x180066633  jnz     short loc_18006663B
0x180066635  mov     dword ptr [rsp+1B8h+var_188], edi
0x180066639  jmp     short loc_180066643
0x18006663b  test    ebx, ebx
0x18006663d  js      loc_1800670E7
0x180066643  mov     rcx, [rsp+1B8h+hKey]; HKEY
0x180066648  test    rcx, rcx
0x18006664b  jz      loc_1800666DE
0x180066651  mov     [rsp+1B8h+lpSubKey], rdi
0x180066656  lea     rax, [rsp+1B8h+lpSubKey]
0x18006665b  mov     qword ptr [rsp+1B8h+SystemTime.wYear], rax
0x180066663  mov     qword ptr [rsp+1B8h+SystemTime.wHour], rdi
0x18006666b  mov     [rsp+1B8h+var_B0], r14b
0x180066673  lea     r9, [rsp+1B8h+SystemTime.wHour]; unsigned __int16 **
0x18006667b  lea     r8, aVersion; "version"
0x180066682  xor     edx, edx; unsigned __int16 *
0x180066684  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180066689  mov     ebx, eax
0x18006668b  lea     rcx, [rsp+1B8h+SystemTime]
0x180066693  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180066698  shr     ebx, 1Fh
0x18006669b  xor     bl, r14b
0x18006669e  jz      short loc_1800666D4
0x1800666a0  mov     rdx, [rsp+1B8h+lpSubKey]; lpSubKey
0x1800666a5  mov     rcx, [rsp+1B8h+hKey]; hKey
0x1800666aa  call    cs:__imp_RegDeleteTreeW
0x1800666b0  mov     ebx, eax
0x1800666b2  test    eax, eax
0x1800666b4  jz      short loc_1800666D4
0x1800666b6  jle     short loc_1800666C1
0x1800666b8  movzx   ebx, ax
0x1800666bb  or      ebx, 80070000h
0x1800666c1  mov     dword ptr [rsp+1B8h+var_188], ebx
0x1800666c5  lea     rcx, [rsp+1B8h+lpSubKey]
0x1800666ca  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800666cf  jmp     loc_1800670E7
0x1800666d4  lea     rcx, [rsp+1B8h+lpSubKey]
0x1800666d9  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800666de  lea     rax, [rsp+1B8h+hKey]
0x1800666e3  mov     qword ptr [rsp+1B8h+SystemTime.wYear], rax
0x1800666eb  mov     qword ptr [rsp+1B8h+SystemTime.wHour], rdi
0x1800666f3  mov     [rsp+1B8h+var_B0], r14b
0x1800666fb  mov     rdx, [rsp+1B8h+var_180]
0x180066700  add     rdx, 20h ; ' '
0x180066704  cmp     qword ptr [rdx+18h], 7
0x180066709  jbe     short loc_18006670E
0x18006670b  mov     rdx, [rdx]; unsigned __int16 *
0x18006670e  mov     r9d, r14d; int
0x180066711  lea     r8, [rsp+1B8h+SystemTime.wHour]; HKEY *
0x180066719  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x18006671c  call    ?DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180066721  mov     dword ptr [rsp+1B8h+var_188], eax
0x180066725  lea     rcx, [rsp+1B8h+SystemTime]
0x18006672d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180066732  mov     ebx, dword ptr [rsp+1B8h+var_188]
0x180066736  test    ebx, ebx
0x180066738  jns     short loc_18006675B
0x18006673a  mov     edx, 13C8h; void *
0x18006673f  mov     r9d, ebx; char *
0x180066742  mov     rcx, [rsp+1B8h]; this
0x18006674a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180066751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066756  jmp     loc_1800670E7
0x18006675b  mov     r9, [rsp+1B8h+var_180]
0x180066760  add     r9, 40h ; '@'
0x180066764  cmp     qword ptr [r9+18h], 7
0x180066769  jbe     short loc_18006676E
0x18006676b  mov     r9, [r9]; unsigned __int16 *
0x18006676e  mov     [rsp+1B8h+var_198], dil; bool
0x180066773  lea     r8, aVersion; "version"
0x18006677a  xor     edx, edx; unsigned __int16 *
0x18006677c  mov     rcx, [rsp+1B8h+hKey]; HKEY
0x180066781  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x180066786  mov     ebx, eax
0x180066788  mov     dword ptr [rsp+1B8h+var_188], eax
0x18006678c  test    eax, eax
0x18006678e  jns     short loc_18006679A
0x180066790  mov     r9d, eax
0x180066793  mov     edx, 13CBh
0x180066798  jmp     short loc_180066742
0x18006679a  lea     rax, [rsp+1B8h+var_168]
0x18006679f  mov     qword ptr [rsp+1B8h+SystemTime.wYear], rax
0x1800667a7  mov     qword ptr [rsp+1B8h+SystemTime.wHour], rdi
0x1800667af  mov     [rsp+1B8h+var_B0], r14b
0x1800667b7  mov     rdx, [rsp+1B8h+var_180]
0x1800667bc  add     rdx, 20h ; ' '
0x1800667c0  cmp     qword ptr [rdx+18h], 7
0x1800667c5  jbe     short loc_1800667CA
0x1800667c7  mov     rdx, [rdx]; unsigned __int16 *
0x1800667ca  mov     r9d, r14d; int
0x1800667cd  lea     r8, [rsp+1B8h+SystemTime.wHour]; HKEY *
0x1800667d5  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x1800667d8  call    ?DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1800667dd  mov     dword ptr [rsp+1B8h+var_188], eax
0x1800667e1  lea     rcx, [rsp+1B8h+SystemTime]
0x1800667e9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800667ee  mov     ebx, dword ptr [rsp+1B8h+var_188]
0x1800667f2  test    ebx, ebx
0x1800667f4  jns     short loc_180066800
0x1800667f6  mov     edx, 13D2h
0x1800667fb  jmp     loc_18006673F
0x180066800  mov     r9, [rsp+1B8h+var_180]
0x180066805  cmp     qword ptr [r9+18h], 7
0x18006680a  jbe     short loc_18006680F
0x18006680c  mov     r9, [r9]; unsigned __int16 *
0x18006680f  mov     [rsp+1B8h+var_198], dil; bool
0x180066814  lea     r8, aSchemaversion; "schemaVersion"
0x18006681b  xor     edx, edx; unsigned __int16 *
0x18006681d  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x180066822  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x180066827  mov     ebx, eax
0x180066829  mov     dword ptr [rsp+1B8h+var_188], eax
0x18006682d  test    eax, eax
0x18006682f  jns     short loc_18006683E
0x180066831  mov     r9d, eax
0x180066834  mov     edx, 13D5h
0x180066839  jmp     loc_180066742
0x18006683e  mov     r9, [rsp+1B8h+var_180]
0x180066843  add     r9, 60h ; '`'
0x180066847  cmp     qword ptr [r9+18h], 7
0x18006684c  jbe     short loc_180066851
0x18006684e  mov     r9, [r9]; unsigned __int16 *
0x180066851  mov     [rsp+1B8h+var_198], dil; int
0x180066856  lea     r8, aOsdefinedscena_2; "osDefinedScenario"
0x18006685d  xor     edx, edx; unsigned __int16 *
0x18006685f  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x180066864  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x180066869  mov     ebx, eax
0x18006686b  mov     dword ptr [rsp+1B8h+var_188], eax
0x18006686f  test    eax, eax
0x180066871  jns     short loc_180066880
0x180066873  mov     r9d, eax
0x180066876  mov     edx, 13D8h
0x18006687b  jmp     loc_180066742
0x180066880  mov     rdx, [rsp+1B8h+var_180]
0x180066885  mov     r15, [rdx+0B0h]
0x18006688c  sub     r15, [rdx+0A8h]
0x180066893  sar     r15, 3
0x180066897  mov     rax, 8E38E38E38E38E39h
0x1800668a1  imul    r15, rax
0x1800668a5  mov     rsi, rdi
0x1800668a8  cmp     rsi, r15
0x1800668ab  jnb     loc_180066A13
0x1800668b1  lea     rbx, [rsi+rsi*8]
0x1800668b5  mov     rax, [rdx+0A8h]
0x1800668bc  mov     r14d, [rax+rbx*8]
0x1800668c0  lea     rdx, [rax+28h]
0x1800668c4  lea     rdx, [rdx+rbx*8]
0x1800668c8  lea     rcx, [rsp+1B8h+var_68]
0x1800668d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800668d5  nop
0x1800668d6  lea     rax, [rsp+1B8h+var_158]
0x1800668db  mov     qword ptr [rsp+1B8h+SystemTime.wYear], rax
0x1800668e3  mov     qword ptr [rsp+1B8h+SystemTime.wHour], rdi
0x1800668eb  mov     [rsp+1B8h+var_B0], 1
0x1800668f3  mov     rdx, [rsp+1B8h+var_180]
0x1800668f8  mov     r8, [rdx+0A8h]
0x1800668ff  add     r8, 8
0x180066903  lea     r8, [r8+rbx*8]
0x180066907  cmp     qword ptr [r8+18h], 7
0x18006690c  jbe     short loc_180066911
0x18006690e  mov     r8, [r8]; unsigned __int16 *
0x180066911  add     rdx, 20h ; ' '
0x180066915  cmp     qword ptr [rdx+18h], 7
0x18006691a  jbe     short loc_18006691F
0x18006691c  mov     rdx, [rdx]; unsigned __int16 *
0x18006691f  mov     dword ptr [rsp+1B8h+var_198], 1; int
0x180066927  lea     r9, [rsp+1B8h+SystemTime.wHour]; HKEY *
0x18006692f  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x180066932  call    ?DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionOrderedDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionOrderedDocIdKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x180066937  mov     dword ptr [rsp+1B8h+var_188], eax
0x18006693b  lea     rcx, [rsp+1B8h+SystemTime]
0x180066943  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180066948  mov     ebx, dword ptr [rsp+1B8h+var_188]
0x18006694c  test    ebx, ebx
0x18006694e  js      loc_1800669E4
0x180066954  mov     r9d, r14d; unsigned int
0x180066957  lea     r8, aRanking_0; "ranking"
0x18006695e  xor     edx, edx; unsigned __int16 *
0x180066960  mov     rcx, [rsp+1B8h+var_158]; HKEY
0x180066965  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18006696a  mov     ebx, eax
0x18006696c  mov     dword ptr [rsp+1B8h+var_188], eax
0x180066970  test    eax, eax
0x180066972  js      short loc_1800669DA
0x180066974  lea     r9, [rsp+1B8h+var_68]
0x18006697c  cmp     [rsp+1B8h+var_50], 7
0x180066985  cmova   r9, [rsp+1B8h+var_68]; unsigned __int16 *
0x18006698e  mov     [rsp+1B8h+var_198], dil; bool
0x180066993  lea     r8, aCustomcr_0; "customCR"
0x18006699a  xor     edx, edx; unsigned __int16 *
0x18006699c  mov     rcx, [rsp+1B8h+var_158]; HKEY
0x1800669a1  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800669a6  mov     ebx, eax
0x1800669a8  mov     dword ptr [rsp+1B8h+var_188], eax
0x1800669ac  test    eax, eax
0x1800669ae  js      short loc_1800669D0
0x1800669b0  lea     rcx, [rsp+1B8h+var_68]
0x1800669b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800669bd  mov     r14d, 1
0x1800669c3  add     rsi, r14
0x1800669c6  mov     rdx, [rsp+1B8h+var_180]
0x1800669cb  jmp     loc_1800668A8
0x1800669d0  mov     r9d, eax
0x1800669d3  mov     edx, 13ECh
0x1800669d8  jmp     short loc_1800669EC
0x1800669da  mov     r9d, eax
0x1800669dd  mov     edx, 13E9h
0x1800669e2  jmp     short loc_1800669EC
0x1800669e4  mov     r9d, ebx; char *
0x1800669e7  mov     edx, 13E6h; void *
0x1800669ec  mov     rcx, [rsp+1B8h]; this
0x1800669f4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800669fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066a00  nop
0x180066a01  lea     rcx, [rsp+1B8h+var_68]
0x180066a09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066a0e  jmp     loc_1800670E7
0x180066a13  mov     r13, [rdx+0C8h]
0x180066a1a  sub     r13, [rdx+0C0h]
0x180066a21  sar     r13, 5
0x180066a25  mov     rbx, rdi
0x180066a28  cmp     rbx, r13
0x180066a2b  jnb     loc_180066ACA
0x180066a31  lea     rax, [rsp+1B8h+var_140]
0x180066a36  mov     qword ptr [rsp+1B8h+SystemTime.wYear], rax
0x180066a3e  mov     qword ptr [rsp+1B8h+SystemTime.wHour], rdi
0x180066a46  mov     [rsp+1B8h+var_B0], r14b
0x180066a4e  mov     r8, rbx
0x180066a51  shl     r8, 5
0x180066a55  add     r8, [rdx+0C0h]
0x180066a5c  cmp     qword ptr [r8+18h], 7
0x180066a61  jbe     short loc_180066A66
0x180066a63  mov     r8, [r8]; unsigned __int16 *
0x180066a66  add     rdx, 20h ; ' '
0x180066a6a  cmp     qword ptr [rdx+18h], 7
0x180066a6f  jbe     short loc_180066A74
0x180066a71  mov     rdx, [rdx]; unsigned __int16 *
0x180066a74  lea     r9, [rsp+1B8h+SystemTime.wHour]; HKEY *
0x180066a7c  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x180066a7f  call    ?DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionUnorderedDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdPriorityRulesDocIdVersionUnorderedDocIdKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x180066a84  mov     dword ptr [rsp+1B8h+var_188], eax
0x180066a88  lea     rcx, [rsp+1B8h+SystemTime]
0x180066a90  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180066a95  mov     esi, dword ptr [rsp+1B8h+var_188]
0x180066a99  test    esi, esi
0x180066a9b  js      short loc_180066AA7
0x180066a9d  add     rbx, r14
0x180066aa0  mov     rdx, [rsp+1B8h+var_180]
0x180066aa5  jmp     short loc_180066A28
0x180066aa7  mov     rcx, [rsp+1B8h]; this
0x180066aaf  mov     r9d, esi; char *
  ... truncated ...
```
