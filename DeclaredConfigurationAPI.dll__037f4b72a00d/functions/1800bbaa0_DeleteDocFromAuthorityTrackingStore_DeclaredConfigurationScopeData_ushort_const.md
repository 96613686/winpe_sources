# DeleteDocFromAuthorityTrackingStore(DeclaredConfigurationScopeData *,ushort const *)

- ea: `0x1800bbaa0`
- end: `0x1800bc5a7`
- name: `?DeleteDocFromAuthorityTrackingStore@@YAJPEAUDeclaredConfigurationScopeData@@PEBG@Z`
- size: `2823`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180069de0`
- `0x180084280`
- `0x1801106fc`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180019270`
- `0x1800192b4`
- `0x180019d38`
- `0x18001aaec`
- `0x18001bc98`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18001dea8`
- `0x18001def8`
- `0x180048fe8`
- `0x18004bc88`
- `0x18004ec50`
- `0x18005ec48`
- `0x18005ee00`
- `0x180078e2c`
- `0x1800a01b0`
- `0x1800bb4bc`
- `0x1800bbaa0`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100ad8`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bbdd8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bbe09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bbe38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc0a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc29e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc2cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc2fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc42d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bbdd8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bbe09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bbe38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc0a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc29e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc2cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc2fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc42d`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800bc058`

## string_xrefs

- `0x1800bc4a5`: `registry`
- `0x1800bbb58`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bbbeb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bbcc4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bc178`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bc4ee`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bbb37`: `GetReadonlyEnrollmentIdSidStateDocIdKey`
- `0x1800bbb3e`: `DeleteDocFromAuthorityTrackingStore`
- `0x1800bbbd1`: `DeleteDocFromAuthorityTrackingStore`
- `0x1800bbcb0`: `DeleteDocFromAuthorityTrackingStore`
- `0x1800bc17f`: `DeleteDocFromAuthorityTrackingStore`
- `0x1800bc4f5`: `DeleteDocFromAuthorityTrackingStore`
- `0x1800bbbca`: `DCCDNUtil_GetRegistryString - get mostRecentVersion`
- `0x1800bbca9`: `DeclaredConfigurationStore_GetPersistedDocument: raw`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall DeleteDocFromAuthorityTrackingStore(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r15
  int RegistryString; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  CDeclaredConfigurationLogger *v6; // rax
  __int64 v7; // r8
  unsigned __int16 *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rdx
  CDeclaredConfigurationLogger *v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  char *v15; // rdi
  char *v16; // rcx
  int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 *v20; // r14
  __int64 *v21; // r12
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  _WORD *v26; // rdx
  __int64 v27; // r8
  const unsigned __int16 *v28; // rcx
  int v29; // eax
  __int64 v30; // rdi
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  _BYTE *v34; // rcx
  unsigned __int16 **v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  unsigned __int16 **v42; // r9
  _QWORD *v43; // rax
  int v44; // r9d
  unsigned __int16 **v45; // rdx
  _QWORD *v46; // rcx
  char *v47; // r9
  char IsEnabled; // al
  const unsigned __int16 *v49; // rdx
  const unsigned __int16 *v50; // r8
  int v51; // ebx
  CDeclaredConfigurationLogger *v52; // rax
  const unsigned __int16 *v53; // r9
  __int64 v54; // rax
  __int64 v55; // rdi
  __int64 *v56; // rsi
  __int64 *v57; // r14
  _QWORD *v58; // rcx
  _QWORD *v59; // rcx
  _QWORD *v60; // rcx
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  _QWORD *v67; // rcx
  char *v68; // r9
  char v69; // al
  const unsigned __int16 *v70; // rdx
  const unsigned __int16 *v71; // r8
  int v72; // ebx
  CDeclaredConfigurationLogger *v73; // rax
  const unsigned __int16 *v74; // r9
  const char *v75; // r9
  int v77; // [rsp+20h] [rbp-498h]
  int v78; // [rsp+20h] [rbp-498h]
  int v79; // [rsp+20h] [rbp-498h]
  int v80; // [rsp+20h] [rbp-498h]
  int v81; // [rsp+20h] [rbp-498h]
  unsigned __int16 *v82; // [rsp+20h] [rbp-498h]
  unsigned __int16 *v83; // [rsp+20h] [rbp-498h]
  int v84; // [rsp+30h] [rbp-488h]
  HKEY v85; // [rsp+38h] [rbp-480h] BYREF
  _WORD *v86; // [rsp+40h] [rbp-478h] BYREF
  char *v87; // [rsp+48h] [rbp-470h]
  char *i; // [rsp+50h] [rbp-468h]
  char v89[8]; // [rsp+58h] [rbp-460h] BYREF
  char v90; // [rsp+60h] [rbp-458h] BYREF
  unsigned __int16 *v91[3]; // [rsp+68h] [rbp-450h] BYREF
  unsigned __int64 v92; // [rsp+80h] [rbp-438h]
  unsigned __int16 *v93[3]; // [rsp+88h] [rbp-430h] BYREF
  unsigned __int64 v94; // [rsp+A0h] [rbp-418h]
  _QWORD Src[3]; // [rsp+A8h] [rbp-410h] BYREF
  unsigned __int64 v96; // [rsp+C0h] [rbp-3F8h]
  _BYTE v97[32]; // [rsp+C8h] [rbp-3F0h] BYREF
  _BYTE v98[32]; // [rsp+E8h] [rbp-3D0h] BYREF
  _BYTE v99[32]; // [rsp+108h] [rbp-3B0h] BYREF
  _BYTE v100[32]; // [rsp+128h] [rbp-390h] BYREF
  _BYTE v101[40]; // [rsp+148h] [rbp-370h] BYREF
  char *v102[4]; // [rsp+170h] [rbp-348h] BYREF
  _QWORD v103[3]; // [rsp+190h] [rbp-328h] BYREF
  unsigned __int64 v104; // [rsp+1A8h] [rbp-310h]
  char *v105[2]; // [rsp+1B0h] [rbp-308h] BYREF
  void *v106; // [rsp+1C0h] [rbp-2F8h]
  unsigned __int64 v107; // [rsp+1C8h] [rbp-2F0h]
  char *v108[9]; // [rsp+1D0h] [rbp-2E8h] BYREF
  char *v109; // [rsp+218h] [rbp-2A0h]
  int v110; // [rsp+284h] [rbp-234h]
  _QWORD v111[3]; // [rsp+370h] [rbp-148h] BYREF
  unsigned __int64 v112; // [rsp+388h] [rbp-130h]
  unsigned __int16 v113[4]; // [rsp+460h] [rbp-58h] BYREF
  HKEY v114; // [rsp+468h] [rbp-50h] BYREF
  char v115; // [rsp+470h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v2 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl'::`2'::impl,
    a2);
  v85 = 0;
  *(_QWORD *)v113 = &v85;
  v114 = 0;
  v115 = 1;
  RegistryString = DCGetEnrollmentIdSidStateDocIdKey((struct DeclaredConfigurationScopeData *)a1, v2, &v114);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v113);
  if ( RegistryString < 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DeleteDocFromAuthorityTrackingStore",
      L"GetReadonlyEnrollmentIdSidStateDocIdKey",
      v2,
      RegistryString);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)(unsigned int)RegistryString,
      v79);
    goto LABEL_111;
  }
  v86 = 0;
  *(_QWORD *)v113 = &v86;
  v114 = 0;
  v115 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(v85, 0, L"MostRecentVersion", (unsigned __int16 **)&v114);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v113);
  if ( RegistryString < 0 )
  {
    v6 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v6,
      L"DeleteDocFromAuthorityTrackingStore",
      L"DCCDNUtil_GetRegistryString - get mostRecentVersion",
      v2,
      RegistryString);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)(unsigned int)RegistryString,
      v80);
    goto LABEL_110;
  }
  DCDocument::DCDocument((DCDocument *)v102);
  v7 = -1;
  do
    ++v7;
  while ( v2[v7] );
  std::wstring::_Assign<unsigned short>(v102, v2, (char *)v7);
  v8 = a1[1];
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  std::wstring::_Assign<unsigned short>(v105, v8, (char *)v9);
  v10 = -1;
  do
    ++v10;
  while ( v86[v10] );
  std::wstring::_Assign<unsigned short>(v108, v86, (char *)v10);
  RegistryString = DeclaredConfigurationStore_GetPersistedDocumentBestEffort(
                     (__int64)a1,
                     v85,
                     (__int64)v86,
                     0,
                     (__int64)v102);
  if ( RegistryString >= 0 )
  {
    LOBYTE(v11) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl'::`2'::impl,
      v11);
    if ( v110 != 2
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::GetImpl'::`2'::impl) )
    {
LABEL_108:
      RegistryString = 0;
      goto LABEL_109;
    }
    v14 = 0;
    v15 = v108[8];
    v16 = v109;
    for ( i = v109; ; v16 = i )
    {
      v87 = v15;
      if ( v15 == v16 )
        goto LABEL_108;
      v84 = v14 + 1;
      RegistryString = StringCchPrintfW(v113, 0xFu, L"CSP%d", (unsigned int)(v14 + 1));
      if ( RegistryString < 0 )
        break;
      v17 = (***(__int64 (__fastcall ****)(_QWORD))v15)(*(_QWORD *)v15);
      if ( v17 == 1 )
      {
        v18 = _RTDynamicCast_0(*(_QWORD *)v15, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
        v19 = v18;
        if ( !v18 )
          goto LABEL_107;
        v20 = *(__int64 **)(v18 + 16);
        v21 = *(__int64 **)(v18 + 24);
        while ( v20 != v21 )
        {
          v22 = v111;
          if ( v112 > 7 )
            v22 = (_QWORD *)v111[0];
          if ( (unsigned int)_o__wcsicmp(v22, L"msftinventory") )
          {
            v23 = v111;
            if ( v112 > 7 )
              v23 = (_QWORD *)v111[0];
            if ( (unsigned int)_o__wcsicmp(v23, L"msftextensibilitymiproviderinventory") )
            {
              v24 = v111;
              if ( v112 > 7 )
                v24 = (_QWORD *)v111[0];
              if ( (unsigned int)_o__wcsicmp(v24, L"msftonetime") && !*(_BYTE *)(v19 + 81) )
              {
                std::wstring::wstring((__int64)v91);
                std::wstring::wstring((__int64)Src);
                std::wstring::wstring((__int64)v93);
                v25 = (_QWORD *)(v19 + 88);
                if ( *(_QWORD *)(v19 + 112) > 7u )
                  v25 = (_QWORD *)*v25;
                v26 = (_WORD *)v25 + 2;
                v27 = -1;
                do
                  ++v27;
                while ( v26[v27] );
                std::wstring::_Assign<unsigned short>((char **)v93, v26, (char *)v27);
                v28 = (const unsigned __int16 *)v93;
                if ( v94 > 7 )
                  v28 = v93[0];
                v29 = DCDoesCspNeedPrefix(v28);
                try
                {
                  v30 = *v20;
                  if ( v29 )
                  {
                    v35 = v93;
                    if ( v94 > 7 )
                      v35 = (unsigned __int16 **)v93[0];
                    v36 = std::operator+<unsigned short>(v101, L"./", v103);
                    v37 = std::operator+<unsigned short>(v100, v36, L"/");
                    v38 = std::operator+<unsigned short>(v97, v37, v35);
                    v39 = std::operator+<unsigned short>(v98, v38, L"/");
                    v40 = std::operator+<unsigned short>(v99, v39, v30);
                    std::wstring::operator=(v91, v40);
                    std::wstring::_Tidy_deallocate(v99);
                    std::wstring::_Tidy_deallocate(v98);
                    std::wstring::_Tidy_deallocate(v97);
                    std::wstring::_Tidy_deallocate(v100);
                    v34 = v101;
                  }
                  else
                  {
                    v31 = std::operator+<unsigned short>(v99, L"./", v93);
                    v32 = std::operator+<unsigned short>(v98, v31, L"/");
                    v33 = std::operator+<unsigned short>(v97, v32, v30);
                    std::wstring::operator=(v91, v33);
                    std::wstring::_Tidy_deallocate(v97);
                    std::wstring::_Tidy_deallocate(v98);
                    v34 = v99;
                  }
                  std::wstring::_Tidy_deallocate(v34);
                  v42 = v91;
                  if ( v92 > 7 )
                    v42 = (unsigned __int16 **)v91[0];
                  v43 = (_QWORD *)std::wstring::end(v91, v89, v41, v42);
                  v45 = v91;
                  if ( v92 > 7 )
                    LODWORD(v45) = v91[0];
                  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                    (unsigned int)&v90,
                    (_DWORD)v45,
                    *v43,
                    v44,
                    *(__int64 *)&_o_towlower);
                  std::wstring::operator=(Src, v91);
                  v46 = v103;
                  if ( v104 > 7 )
                    v46 = (_QWORD *)v103[0];
                  if ( !(unsigned int)_o__wcsicmp(v46, L"user") )
                  {
                    v47 = (char *)v105;
                    if ( v107 > 7 )
                      v47 = v105[0];
                    std::wstring::_Replace<unsigned short>(Src, 2, 4u, v47, (__int64)v106);
                  }
                }
                catch ( std::bad_alloc )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x496,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                    (const char *)0x8007000ELL,
                    v78);
                  std::wstring::_Tidy_deallocate(v93);
                  std::wstring::_Tidy_deallocate(Src);
                  std::wstring::_Tidy_deallocate(v91);
                  DCDocument::~DCDocument((DCDocument *)v102);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v86);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v85);
                  return 2147942414LL;
                }
                IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
                v49 = (const unsigned __int16 *)Src;
                v82 = a1[1];
                v50 = *a1;
                if ( IsEnabled )
                {
                  if ( v96 > 7 )
                    v49 = (const unsigned __int16 *)Src[0];
                  v51 = DeleteAndUpdateAuthorityProvider(L"csp", v49, v50, v2, v82);
                }
                else
                {
                  if ( v96 > 7 )
                    v49 = (const unsigned __int16 *)Src[0];
                  v51 = DeleteAndUpdateAuthorityProvider(0, v49, v50, v2, v82);
                }
                if ( v51 < 0 )
                {
                  v52 = CDeclaredConfigurationLogger::GetLogger();
                  v53 = (const unsigned __int16 *)Src;
                  if ( v96 > 7 )
                    v53 = (const unsigned __int16 *)Src[0];
                  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                    v52,
                    L"DeleteDocFromAuthorityTrackingStore",
                    L"DeleteAndUpdateAuthorityProvider",
                    v53,
                    v51);
                }
                std::wstring::_Tidy_deallocate(v93);
                std::wstring::_Tidy_deallocate(Src);
                std::wstring::_Tidy_deallocate(v91);
              }
            }
          }
          v20 += 2;
        }
LABEL_105:
        v15 = v87;
      }
      else
      {
        if ( v17 == 2 )
          goto LABEL_108;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          goto LABEL_107;
        if ( v17 == 3 )
        {
          v54 = _RTDynamicCast_0(
                  *(_QWORD *)v15,
                  0,
                  &DCProvider `RTTI Type Descriptor',
                  &DCCSP `RTTI Type Descriptor',
                  0);
          v55 = v54;
          if ( v54 )
          {
            v56 = *(__int64 **)(v54 + 16);
            v57 = *(__int64 **)(v54 + 24);
            while ( 1 )
            {
              if ( v56 == v57 )
                goto LABEL_105;
              v58 = v111;
              if ( v112 > 7 )
                v58 = (_QWORD *)v111[0];
              if ( (unsigned int)_o__wcsicmp(v58, L"msftinventory") )
              {
                v59 = v111;
                if ( v112 > 7 )
                  v59 = (_QWORD *)v111[0];
                if ( (unsigned int)_o__wcsicmp(v59, L"msftextensibilitymiproviderinventory") )
                {
                  v60 = v111;
                  if ( v112 > 7 )
                    v60 = (_QWORD *)v111[0];
                  if ( (unsigned int)_o__wcsicmp(v60, L"msftonetime") && !*(_BYTE *)(v55 + 81) )
                  {
                    try
                    {
                      std::wstring::wstring((__int64)v93);
                      std::wstring::wstring((__int64)v91);
                      v61 = *v56;
                      v62 = std::operator+<unsigned short>(v97, L"./", v103);
                      v63 = std::operator+<unsigned short>(v98, v62, L"/");
                      v64 = std::operator+<unsigned short>(v99, v63, v55 + 88);
                      v65 = std::operator+<unsigned short>(v100, v64, L"/");
                      v66 = std::operator+<unsigned short>(v101, v65, v61);
                      std::wstring::operator=(v93, v66);
                      std::wstring::_Tidy_deallocate(v101);
                      std::wstring::_Tidy_deallocate(v100);
                      std::wstring::_Tidy_deallocate(v99);
                      std::wstring::_Tidy_deallocate(v98);
                      std::wstring::_Tidy_deallocate(v97);
                      std::wstring::operator=(v91, v93);
                      v67 = v103;
                      if ( v104 > 7 )
                        v67 = (_QWORD *)v103[0];
                      if ( !(unsigned int)_o__wcsicmp(v67, L"user") )
                      {
                        v68 = (char *)v105;
                        if ( v107 > 7 )
                          v68 = v105[0];
                        std::wstring::_Replace<unsigned short>(v91, 2, 4u, v68, (__int64)v106);
                      }
                      v69 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
                      v70 = (const unsigned __int16 *)v91;
                      v83 = a1[1];
                      v71 = *a1;
                      if ( v69 )
                      {
                        if ( v92 > 7 )
                          v70 = v91[0];
                        v72 = DeleteAndUpdateAuthorityProvider(L"registry", v70, v71, v2, v83);
                      }
                      else
                      {
                        if ( v92 > 7 )
                          v70 = v91[0];
                        v72 = DeleteAndUpdateAuthorityProvider(0, v70, v71, v2, v83);
                      }
                      if ( v72 < 0 )
                      {
                        v73 = CDeclaredConfigurationLogger::GetLogger();
                        v74 = (const unsigned __int16 *)v91;
                        if ( v92 > 7 )
                          v74 = v91[0];
                        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                          v73,
                          L"DeleteDocFromAuthorityTrackingStore",
                          L"DeleteAndUpdateAuthorityProvider",
                          v74,
                          v72);
                      }
                      std::wstring::_Tidy_deallocate(v91);
                      std::wstring::_Tidy_deallocate(v93);
                    }
                    catch ( std::bad_alloc )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x4FE,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                        (const char *)0x8007000ELL,
                        v77);
                      RegistryString = -2147024882;
                      goto LABEL_109;
                    }
                    catch ( ... )
                    {
                      RegistryString = wil::details::in1diag3::Return_CaughtException(
                                         retaddr,
                                         (void *)0x500,
                                         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectm"
                                                       "odel\\lib\\providercsp.cpp",
                                         v75);
LABEL_109:
                      DCDocument::~DCDocument((DCDocument *)v102);
LABEL_110:
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v86);
LABEL_111:
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v85);
                      return (unsigned int)RegistryString;
                    }
                  }
                }
              }
              v56 += 2;
            }
          }
LABEL_107:
          RegistryString = -2147418113;
          goto LABEL_109;
        }
      }
      v15 += 16;
      v14 = v84;
    }
    v13 = 1132;
  }
  else
  {
    v12 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v12,
      L"DeleteDocFromAuthorityTrackingStore",
      L"DeclaredConfigurationStore_GetPersistedDocument: raw",
      v2,
      RegistryString);
    v13 = 1119;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
    (const char *)(unsigned int)RegistryString,
    v81);
  goto LABEL_109;
}

```

## disassembly

```asm
0x1800bbaa0  mov     [rsp+arg_10], rbx
0x1800bbaa5  mov     [rsp+arg_18], rsi
0x1800bbaaa  push    rdi
0x1800bbaab  push    r12
0x1800bbaad  push    r13
0x1800bbaaf  push    r14
0x1800bbab1  push    r15
0x1800bbab3  sub     rsp, 490h
0x1800bbaba  mov     rax, cs:__security_cookie
0x1800bbac1  xor     rax, rsp
0x1800bbac4  mov     [rsp+4B8h+var_38], rax
0x1800bbacc  mov     r15, rdx
0x1800bbacf  mov     r13, rcx
0x1800bbad2  mov     dl, 1
0x1800bbad4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl(void)'::`2'::impl
0x1800bbadb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bbae0  xor     r12d, r12d
0x1800bbae3  mov     [rsp+4B8h+var_480], r12
0x1800bbae8  lea     rax, [rsp+4B8h+var_480]
0x1800bbaed  mov     qword ptr [rsp+4B8h+var_58], rax
0x1800bbaf5  mov     [rsp+4B8h+var_50], r12
0x1800bbafd  mov     [rsp+4B8h+var_48], 1
0x1800bbb05  lea     r8, [rsp+4B8h+var_50]; HKEY *
0x1800bbb0d  mov     rdx, r15; unsigned __int16 *
0x1800bbb10  mov     rcx, r13; struct DeclaredConfigurationScopeData *
0x1800bbb13  call    ?DCGetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@@Z; DCGetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *)
0x1800bbb18  mov     ebx, eax
0x1800bbb1a  lea     rcx, [rsp+4B8h+var_58]
0x1800bbb22  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800bbb27  test    ebx, ebx
0x1800bbb29  jns     short loc_1800BBB6E
0x1800bbb2b  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bbb30  mov     dword ptr [rsp+4B8h+var_498], ebx; int
0x1800bbb34  mov     r9, r15; unsigned __int16 *
0x1800bbb37  lea     r8, aGetreadonlyenr; "GetReadonlyEnrollmentIdSidStateDocIdKey"
0x1800bbb3e  lea     rdx, aDeletedocfroma_0; "DeleteDocFromAuthorityTrackingStore"
0x1800bbb45  mov     rcx, rax; this
0x1800bbb48  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bbb4d  mov     rcx, [rsp+4B8h]; this
0x1800bbb55  mov     r9d, ebx; char *
0x1800bbb58  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bbb5f  mov     edx, 442h; void *
0x1800bbb64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbb69  jmp     loc_1800BC56E
0x1800bbb6e  mov     [rsp+4B8h+var_478], r12
0x1800bbb73  lea     rax, [rsp+4B8h+var_478]
0x1800bbb78  mov     qword ptr [rsp+4B8h+var_58], rax
0x1800bbb80  mov     [rsp+4B8h+var_50], r12
0x1800bbb88  mov     [rsp+4B8h+var_48], 1
0x1800bbb90  lea     r9, [rsp+4B8h+var_50]; unsigned __int16 **
0x1800bbb98  lea     r8, aMostrecentvers; "MostRecentVersion"
0x1800bbb9f  xor     edx, edx; unsigned __int16 *
0x1800bbba1  mov     rcx, [rsp+4B8h+var_480]; HKEY
0x1800bbba6  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800bbbab  mov     ebx, eax
0x1800bbbad  lea     rcx, [rsp+4B8h+var_58]
0x1800bbbb5  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800bbbba  test    ebx, ebx
0x1800bbbbc  jns     short loc_1800BBC01
0x1800bbbbe  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bbbc3  mov     dword ptr [rsp+4B8h+var_498], ebx; int
0x1800bbbc7  mov     r9, r15; unsigned __int16 *
0x1800bbbca  lea     r8, aDccdnutilGetre_1; "DCCDNUtil_GetRegistryString - get mostR"...
0x1800bbbd1  lea     rdx, aDeletedocfroma_0; "DeleteDocFromAuthorityTrackingStore"
0x1800bbbd8  mov     rcx, rax; this
0x1800bbbdb  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bbbe0  mov     rcx, [rsp+4B8h]; this
0x1800bbbe8  mov     r9d, ebx; char *
0x1800bbbeb  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bbbf2  mov     edx, 44Eh; void *
0x1800bbbf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbbfc  jmp     loc_1800BC563
0x1800bbc01  lea     rcx, [rsp+4B8h+var_348]; this
0x1800bbc09  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x1800bbc0e  nop
0x1800bbc0f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bbc13  mov     r8, rbx
0x1800bbc16  inc     r8
0x1800bbc19  cmp     [r15+r8*2], r12w
0x1800bbc1e  jnz     short loc_1800BBC16
0x1800bbc20  mov     rdx, r15
0x1800bbc23  lea     rcx, [rsp+4B8h+var_348]
0x1800bbc2b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bbc30  mov     rdx, [r13+8]
0x1800bbc34  mov     r8, rbx
0x1800bbc37  inc     r8
0x1800bbc3a  cmp     [rdx+r8*2], r12w
0x1800bbc3f  jnz     short loc_1800BBC37
0x1800bbc41  lea     rcx, [rsp+4B8h+var_308]
0x1800bbc49  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bbc4e  mov     rdx, [rsp+4B8h+var_478]
0x1800bbc53  mov     r8, rbx
0x1800bbc56  inc     r8
0x1800bbc59  cmp     [rdx+r8*2], r12w
0x1800bbc5e  jnz     short loc_1800BBC56
0x1800bbc60  lea     rcx, [rsp+4B8h+var_2E8]
0x1800bbc68  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bbc6d  mov     dword ptr [rsp+4B8h+var_490], 1; unsigned __int16 *
0x1800bbc75  lea     rax, [rsp+4B8h+var_348]
0x1800bbc7d  mov     [rsp+4B8h+var_498], rax
0x1800bbc82  xor     r9d, r9d
0x1800bbc85  mov     r8, [rsp+4B8h+var_478]
0x1800bbc8a  mov     rdx, [rsp+4B8h+var_480]
0x1800bbc8f  mov     rcx, r13
0x1800bbc92  call    ?DeclaredConfigurationStore_GetPersistedDocumentBestEffort@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocumentBestEffort(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x1800bbc97  mov     ebx, eax
0x1800bbc99  test    eax, eax
0x1800bbc9b  jns     short loc_1800BBCE0
0x1800bbc9d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bbca2  mov     dword ptr [rsp+4B8h+var_498], ebx; int
0x1800bbca6  mov     r9, r15; unsigned __int16 *
0x1800bbca9  lea     r8, aDeclaredconfig_161; "DeclaredConfigurationStore_GetPersisted"...
0x1800bbcb0  lea     rdx, aDeletedocfroma_0; "DeleteDocFromAuthorityTrackingStore"
0x1800bbcb7  mov     rcx, rax; this
0x1800bbcba  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bbcbf  mov     edx, 45Fh; void *
0x1800bbcc4  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bbccb  mov     r9d, ebx; char *
0x1800bbcce  mov     rcx, [rsp+4B8h]; this
0x1800bbcd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbcdb  jmp     loc_1800BC555
0x1800bbce0  mov     dl, 1
0x1800bbce2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl(void)'::`2'::impl
0x1800bbce9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bbcee  cmp     [rsp+4B8h+var_234], 2
0x1800bbcf6  jz      short loc_1800BBD0C
0x1800bbcf8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::GetImpl(void)'::`2'::impl
0x1800bbcff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::__private_IsEnabled(void)
0x1800bbd04  test    al, al
0x1800bbd06  jz      loc_1800BC552
0x1800bbd0c  mov     eax, r12d
0x1800bbd0f  mov     rdi, [rsp+4B8h+var_2A8]
0x1800bbd17  mov     rcx, [rsp+4B8h+var_2A0]
0x1800bbd1f  mov     [rsp+4B8h+var_468], rcx
0x1800bbd24  mov     [rsp+4B8h+var_470], rdi
0x1800bbd29  cmp     rdi, rcx
0x1800bbd2c  jz      loc_1800BC552
0x1800bbd32  inc     eax
0x1800bbd34  mov     [rsp+4B8h+var_488], eax
0x1800bbd38  mov     r9d, eax
0x1800bbd3b  lea     r8, aCspD; "CSP%d"
0x1800bbd42  mov     edx, 0Fh; unsigned __int64
0x1800bbd47  lea     rcx, [rsp+4B8h+var_58]; unsigned __int16 *
0x1800bbd4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bbd54  mov     ebx, eax
0x1800bbd56  test    eax, eax
0x1800bbd58  jns     short loc_1800BBD64
0x1800bbd5a  mov     edx, 46Ch
0x1800bbd5f  jmp     loc_1800BBCC4
0x1800bbd64  mov     rcx, [rdi]
0x1800bbd67  mov     rax, [rcx]
0x1800bbd6a  mov     rax, [rax]
0x1800bbd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd72  mov     ebx, eax
0x1800bbd74  cmp     eax, 1
0x1800bbd77  jnz     loc_1800BC21D
0x1800bbd7d  mov     dword ptr [rsp+4B8h+var_498], r12d
0x1800bbd82  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x1800bbd89  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x1800bbd90  xor     edx, edx
0x1800bbd92  mov     rcx, [rdi]
0x1800bbd95  call    __RTDynamicCast_0
0x1800bbd9a  mov     rsi, rax
0x1800bbd9d  test    rax, rax
0x1800bbda0  jz      loc_1800BC54B
0x1800bbda6  mov     r14, [rax+10h]
0x1800bbdaa  mov     r12, [rax+18h]
0x1800bbdae  cmp     r14, r12
0x1800bbdb1  jz      loc_1800BC531
0x1800bbdb7  lea     rcx, [rsp+4B8h+var_148]
0x1800bbdbf  cmp     [rsp+4B8h+var_130], 7
0x1800bbdc8  cmova   rcx, [rsp+4B8h+var_148]
0x1800bbdd1  lea     rdx, aMsftinventory; "msftinventory"
0x1800bbdd8  call    cs:__imp__o__wcsicmp
0x1800bbdde  xor     ebx, ebx
0x1800bbde0  test    eax, eax
0x1800bbde2  jz      loc_1800BC214
0x1800bbde8  lea     rcx, [rsp+4B8h+var_148]
0x1800bbdf0  cmp     [rsp+4B8h+var_130], 7
0x1800bbdf9  cmova   rcx, [rsp+4B8h+var_148]
0x1800bbe02  lea     rdx, aMsftextensibil_1; "msftextensibilitymiproviderinventory"
0x1800bbe09  call    cs:__imp__o__wcsicmp
0x1800bbe0f  test    eax, eax
0x1800bbe11  jz      loc_1800BC214
0x1800bbe17  lea     rcx, [rsp+4B8h+var_148]
0x1800bbe1f  cmp     [rsp+4B8h+var_130], 7
0x1800bbe28  cmova   rcx, [rsp+4B8h+var_148]
0x1800bbe31  lea     rdx, aMsftonetime; "msftonetime"
0x1800bbe38  call    cs:__imp__o__wcsicmp
0x1800bbe3e  test    eax, eax
0x1800bbe40  jz      loc_1800BC214
0x1800bbe46  cmp     [rsi+51h], bl
0x1800bbe49  jnz     loc_1800BC214
0x1800bbe4f  lea     rcx, [rsp+4B8h+var_450]
0x1800bbe54  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bbe59  nop
0x1800bbe5a  lea     rcx, [rsp+4B8h+Src]
0x1800bbe62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bbe67  nop
0x1800bbe68  lea     rcx, [rsp+4B8h+var_430]
0x1800bbe70  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bbe75  nop
0x1800bbe76  lea     rax, [rsi+58h]
0x1800bbe7a  cmp     qword ptr [rsi+70h], 7
0x1800bbe7f  jbe     short loc_1800BBE84
0x1800bbe81  mov     rax, [rax]
0x1800bbe84  lea     rdx, [rax+4]
0x1800bbe88  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bbe8c  inc     r8
0x1800bbe8f  cmp     [rdx+r8*2], bx
0x1800bbe94  jnz     short loc_1800BBE8C
0x1800bbe96  lea     rcx, [rsp+4B8h+var_430]
0x1800bbe9e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bbea3  nop
0x1800bbea4  lea     rcx, [rsp+4B8h+var_430]
0x1800bbeac  cmp     [rsp+4B8h+var_418], 7
0x1800bbeb5  cmova   rcx, [rsp+4B8h+var_430]; unsigned __int16 *
0x1800bbebe  call    ?DCDoesCspNeedPrefix@@YAHPEBG@Z; DCDoesCspNeedPrefix(ushort const *)
0x1800bbec3  mov     rdi, [r14]
0x1800bbec6  lea     rdx, asc_180142BE8; "./"
0x1800bbecd  test    eax, eax
0x1800bbecf  jnz     short loc_1800BBF48
0x1800bbed1  lea     r8, [rsp+4B8h+var_430]
0x1800bbed9  lea     rcx, [rsp+4B8h+var_3B0]
0x1800bbee1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800bbee6  nop
0x1800bbee7  lea     r8, asc_18013EB9C; "/"
0x1800bbeee  mov     rdx, rax
0x1800bbef1  lea     rcx, [rsp+4B8h+var_3D0]
0x1800bbef9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800bbefe  nop
0x1800bbeff  mov     r8, rdi
0x1800bbf02  mov     rdx, rax
0x1800bbf05  lea     rcx, [rsp+4B8h+var_3F0]
0x1800bbf0d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800bbf12  mov     rdx, rax
0x1800bbf15  lea     rcx, [rsp+4B8h+var_450]
0x1800bbf1a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800bbf1f  lea     rcx, [rsp+4B8h+var_3F0]
0x1800bbf27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bbf2c  nop
0x1800bbf2d  lea     rcx, [rsp+4B8h+var_3D0]
0x1800bbf35  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bbf3a  nop
0x1800bbf3b  lea     rcx, [rsp+4B8h+var_3B0]
0x1800bbf43  jmp     loc_1800BC01C
0x1800bbf48  lea     rbx, [rsp+4B8h+var_430]
0x1800bbf50  cmp     [rsp+4B8h+var_418], 7
0x1800bbf59  cmova   rbx, [rsp+4B8h+var_430]
0x1800bbf62  lea     r8, [rsp+4B8h+var_328]
0x1800bbf6a  lea     rcx, [rsp+4B8h+var_370]
0x1800bbf72  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800bbf77  nop
0x1800bbf78  lea     r8, asc_18013EB9C; "/"
0x1800bbf7f  mov     rdx, rax
0x1800bbf82  lea     rcx, [rsp+4B8h+var_390]
0x1800bbf8a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800bbf8f  nop
0x1800bbf90  mov     r8, rbx
0x1800bbf93  mov     rdx, rax
0x1800bbf96  lea     rcx, [rsp+4B8h+var_3F0]
0x1800bbf9e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800bbfa3  nop
0x1800bbfa4  lea     r8, asc_18013EB9C; "/"
0x1800bbfab  mov     rdx, rax
0x1800bbfae  lea     rcx, [rsp+4B8h+var_3D0]
0x1800bbfb6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800bbfbb  nop
0x1800bbfbc  mov     r8, rdi
0x1800bbfbf  mov     rdx, rax
0x1800bbfc2  lea     rcx, [rsp+4B8h+var_3B0]
0x1800bbfca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800bbfcf  mov     rdx, rax
0x1800bbfd2  lea     rcx, [rsp+4B8h+var_450]
0x1800bbfd7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800bbfdc  lea     rcx, [rsp+4B8h+var_3B0]
0x1800bbfe4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bbfe9  nop
0x1800bbfea  lea     rcx, [rsp+4B8h+var_3D0]
0x1800bbff2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bbff7  nop
0x1800bbff8  lea     rcx, [rsp+4B8h+var_3F0]
0x1800bc000  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bc005  nop
0x1800bc006  lea     rcx, [rsp+4B8h+var_390]
0x1800bc00e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bc013  nop
0x1800bc014  lea     rcx, [rsp+4B8h+var_370]
0x1800bc01c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bc021  lea     r9, [rsp+4B8h+var_450]
0x1800bc026  cmp     [rsp+4B8h+var_438], 7
0x1800bc02f  cmova   r9, [rsp+4B8h+var_450]
0x1800bc035  lea     rdx, [rsp+4B8h+var_460]
0x1800bc03a  lea     rcx, [rsp+4B8h+var_450]
0x1800bc03f  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800bc044  lea     rdx, [rsp+4B8h+var_450]
0x1800bc049  cmp     [rsp+4B8h+var_438], 7
0x1800bc052  cmova   rdx, [rsp+4B8h+var_450]
0x1800bc058  mov     rcx, cs:__imp__o_towlower
0x1800bc05f  mov     [rsp+4B8h+var_498], rcx
  ... truncated ...
```
