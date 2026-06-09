# RegistryProvider_DriftControlComputeHashValuePerCSP(DeclaredConfigurationScopeData *,DCDocument *,DCCSP *,int)

- ea: `0x1800e82c0`
- end: `0x1800e8bb2`
- name: `?RegistryProvider_DriftControlComputeHashValuePerCSP@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEAVDCCSP@@H@Z`
- size: `2290`
- prototype: `int(struct DeclaredConfigurationScopeData *, struct DCDocument *, struct DCCSP *, int)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e4848`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x18001924c`
- `0x180019270`
- `0x1800192b4`
- `0x180019d38`
- `0x18001aaec`
- `0x18001ce5c`
- `0x18001d020`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18001def8`
- `0x18004ec50`
- `0x180058148`
- `0x18005eeb8`
- `0x1800a03e0`
- `0x1800a4124`
- `0x1800adb6c`
- `0x1800ade50`
- `0x1800adf08`
- `0x1800ae000`
- `0x1800c4fe4`
- `0x1800e1cb4`
- `0x1800e1d80`
- `0x1800e82c0`
- `0x1800e8bb8`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100c90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e8554`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e8554`
- `OLEAUT32!__imp_VariantInit` at `0x1800e88dc`
- `OLEAUT32!__imp_VariantInit` at `0x1800e88dc`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8add`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8add`

## string_xrefs

- `0x1800e8415`: `URI%d`
- `0x1800e86d0`: `DCGetEnrollmentIdSidStateDocIdVersionKey`
- `0x1800e88b5`: `DCCDNUtil_SetRegistryBinary hashValue`
- `0x1800e833f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerregistry.cpp`
- `0x1800e843f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerregistry.cpp`
- `0x1800e8616`: `RegistryProvider_DriftControlComputeHashValuePerUri`
- `0x1800e861d`: `RegistryProvider_DriftControlComputeHashValuePerCSP`
- `0x1800e86d7`: `RegistryProvider_DriftControlComputeHashValuePerCSP`
- `0x1800e88bc`: `DriftControlComputeHashValuePerRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall RegistryProvider_DriftControlComputeHashValuePerCSP(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        struct DCCSP *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  _WORD *v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // r15d
  struct DCURI **v13; // rsi
  struct DCURI **v14; // rax
  int v15; // eax
  struct DCURI *v16; // r14
  _QWORD *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  char *v20; // r12
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  char *v24; // r9
  struct DCURI *v25; // rdx
  _QWORD *v26; // r8
  int v27; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v29; // r9
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // rdx
  int v32; // ebx
  CDeclaredConfigurationLogger *v33; // rax
  const unsigned __int16 *v34; // r9
  __int64 v35; // r12
  __int64 v36; // r15
  __int64 v37; // r14
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  const unsigned __int16 *v44; // rdx
  int v45; // eax
  int v46; // ebx
  CDeclaredConfigurationLogger *v47; // rax
  const unsigned __int16 *v48; // r9
  const unsigned __int16 *v49; // rax
  unsigned int v50; // r8d
  int v51; // ebx
  _QWORD *v52; // rdx
  bool v53; // zf
  __int64 v54; // rcx
  int v55; // ebx
  __int64 v56; // rcx
  struct DCURI *v57; // rbx
  __int64 v58; // rcx
  int v60; // [rsp+20h] [rbp-2A8h]
  int v61; // [rsp+20h] [rbp-2A8h]
  int v62; // [rsp+20h] [rbp-2A8h]
  int v63; // [rsp+20h] [rbp-2A8h]
  _QWORD *v64; // [rsp+30h] [rbp-298h] BYREF
  __int64 v65; // [rsp+38h] [rbp-290h] BYREF
  HKEY v66; // [rsp+40h] [rbp-288h] BYREF
  struct DeclaredConfigurationScopeData *v67; // [rsp+48h] [rbp-280h]
  char v68[8]; // [rsp+50h] [rbp-278h] BYREF
  char v69[8]; // [rsp+58h] [rbp-270h] BYREF
  char v70[8]; // [rsp+60h] [rbp-268h] BYREF
  char v71[8]; // [rsp+68h] [rbp-260h] BYREF
  char v72[8]; // [rsp+70h] [rbp-258h] BYREF
  struct DCURI **v73; // [rsp+78h] [rbp-250h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-248h] BYREF
  _QWORD Src[3]; // [rsp+98h] [rbp-230h] BYREF
  unsigned __int64 v76; // [rsp+B0h] [rbp-218h]
  HKEY *v77; // [rsp+B8h] [rbp-210h] BYREF
  HKEY v78; // [rsp+C0h] [rbp-208h] BYREF
  char v79; // [rsp+C8h] [rbp-200h]
  unsigned __int16 *v80[3]; // [rsp+D8h] [rbp-1F0h] BYREF
  unsigned __int64 v81; // [rsp+F0h] [rbp-1D8h]
  _BYTE v82[32]; // [rsp+F8h] [rbp-1D0h] BYREF
  char v83[8]; // [rsp+118h] [rbp-1B0h] BYREF
  char *v84; // [rsp+120h] [rbp-1A8h] BYREF
  _BYTE v85[32]; // [rsp+140h] [rbp-188h] BYREF
  _BYTE v86[32]; // [rsp+160h] [rbp-168h] BYREF
  _BYTE v87[32]; // [rsp+180h] [rbp-148h] BYREF
  _BYTE v88[32]; // [rsp+1A0h] [rbp-128h] BYREF
  _BYTE v89[32]; // [rsp+1C0h] [rbp-108h] BYREF
  _BYTE v90[32]; // [rsp+1E0h] [rbp-E8h] BYREF
  _BYTE v91[32]; // [rsp+200h] [rbp-C8h] BYREF
  _BYTE v92[32]; // [rsp+220h] [rbp-A8h] BYREF
  unsigned __int16 v93[16]; // [rsp+240h] [rbp-88h] BYREF
  unsigned __int16 v94[16]; // [rsp+260h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v67 = a1;
  DCRegistryProvider::DCRegistryProvider((DCRegistryProvider *)v83);
  v94[0] = 0;
  v93[0] = 0;
  v6 = StringCchPrintfW(v93, 0xFu, L"CSP%d");
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerregistry.cpp",
      (const char *)(unsigned int)v6,
      v63);
    goto LABEL_63;
  }
  std::wstring::wstring((__int64)v82);
  try
  {
    v8 = std::wstring::wstring((__int64)Src, (__int64)L"cooked\\");
    v9 = std::operator+<unsigned short>(v80, v8, v93);
    std::wstring::operator=(v82, v9);
    std::wstring::_Tidy_deallocate(v80);
    std::wstring::_Tidy_deallocate(Src);
    v10 = *(_WORD **)a1;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerregistry.cpp",
      (const char *)0x8007000ELL,
      v62);
    std::wstring::_Tidy_deallocate(v82);
    DCRegistryProvider::~DCRegistryProvider((DCRegistryProvider *)v83);
    return 2147942414LL;
  }
  std::wstring::_Assign<unsigned short>(&v84, v10, (char *)v11);
  v83[0] = 1;
  v12 = 1;
  LODWORD(v64) = 1;
  v13 = (struct DCURI **)*((_QWORD *)a3 + 2);
  v14 = (struct DCURI **)*((_QWORD *)a3 + 3);
  v73 = v14;
  while ( v13 != v14 )
  {
    if ( *((_DWORD *)*v13 + 46) != 1 )
      goto LABEL_61;
    v15 = StringCchPrintfW(v94, 0xFu, L"URI%d", v12);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerregistry.cpp",
        (const char *)(unsigned int)v15,
        v63);
      std::wstring::_Tidy_deallocate(v82);
      goto LABEL_63;
    }
    std::wstring::wstring((__int64)Src);
    try
    {
      v16 = *v13;
      v17 = (_QWORD *)((char *)a2 + 32);
      v18 = std::operator+<unsigned short>(v88, L"./", (char *)a2 + 32);
      v19 = std::operator+<unsigned short>(v87, v18, L"/");
      v20 = (char *)a3 + 88;
      v21 = std::operator+<unsigned short>(v86, v19, (char *)a3 + 88);
      v22 = std::operator+<unsigned short>(v85, v21, L"/");
      v23 = std::operator+<unsigned short>(&v77, v22, v16);
      std::wstring::operator=(Src, v23);
      std::wstring::_Tidy_deallocate(&v77);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v86);
      std::wstring::_Tidy_deallocate(v87);
      std::wstring::_Tidy_deallocate(v88);
      if ( *((_QWORD *)a2 + 7) > 7u )
        v17 = (_QWORD *)*v17;
      if ( !(unsigned int)_o__wcsicmp(v17, L"user") )
      {
        v24 = (char *)a2 + 64;
        if ( *((_QWORD *)a2 + 11) > 7u )
          v24 = *(char **)v24;
        std::wstring::_Replace<unsigned short>(Src, 2, 4u, v24, *((_QWORD *)a2 + 10));
      }
      v25 = *v13;
      v77 = (HKEY *)((char *)*v13 + 328);
      v78 = 0;
      v79 = 1;
      v26 = Src;
      if ( v76 > 7 )
        v26 = (_QWORD *)Src[0];
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerregistry.cpp",
        (const char *)0x8007000ELL,
        v61);
      goto LABEL_62;
    }
    v27 = RegistryProvider_DriftControlComputeHashValuePerUri(v83, v25, v26, &v78);
    wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&v77);
    if ( v27 < 0 )
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      v29 = (const unsigned __int16 *)Src;
      if ( v76 > 7 )
        v29 = (const unsigned __int16 *)Src[0];
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"RegistryProvider_DriftControlComputeHashValuePerCSP",
        L"RegistryProvider_DriftControlComputeHashValuePerUri",
        v29,
        v27);
    }
    v66 = 0;
    if ( v27 >= 0 && *((_QWORD *)*v13 + 41) )
    {
      v77 = &v66;
      v78 = 0;
      v79 = 1;
      v30 = (const unsigned __int16 *)((char *)a2 + 96);
      if ( *((_QWORD *)a2 + 15) > 7u )
        v30 = *(const unsigned __int16 **)v30;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v31 = (const unsigned __int16 *)a2;
      else
        v31 = *(const unsigned __int16 **)a2;
      v32 = DCGetEnrollmentIdSidStateDocIdVersionKey(v67, v31, v30, &v78, 0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v77);
      if ( v32 < 0 )
      {
        v33 = CDeclaredConfigurationLogger::GetLogger();
        v34 = (const unsigned __int16 *)Src;
        if ( v76 > 7 )
          v34 = (const unsigned __int16 *)Src[0];
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v33,
          L"RegistryProvider_DriftControlComputeHashValuePerCSP",
          L"DCGetEnrollmentIdSidStateDocIdVersionKey",
          v34,
          v32);
      }
      std::wstring::wstring((__int64)v80);
      if ( v32 >= 0 )
      {
        try
        {
          v35 = std::wstring::wstring((__int64)v92, (__int64)v94);
          v36 = std::wstring::wstring((__int64)v91, (__int64)L"\\");
          v37 = std::wstring::wstring((__int64)v90, (__int64)v93);
          v38 = std::wstring::wstring((__int64)v89, (__int64)L"\\");
          v39 = std::wstring::wstring((__int64)&v77, (__int64)L"cooked");
          v40 = std::operator+<unsigned short>(v85, v39, v38);
          v41 = std::operator+<unsigned short>(v86, v40, v37);
          v42 = std::operator+<unsigned short>(v87, v41, v36);
          v43 = std::operator+<unsigned short>(v88, v42, v35);
          std::wstring::operator=(v80, v43);
          std::wstring::_Tidy_deallocate(v88);
          std::wstring::_Tidy_deallocate(v87);
          std::wstring::_Tidy_deallocate(v86);
          std::wstring::_Tidy_deallocate(v85);
          std::wstring::_Tidy_deallocate(&v77);
          std::wstring::_Tidy_deallocate(v89);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          v44 = (const unsigned __int16 *)v80;
          if ( v81 > 7 )
            v44 = v80[0];
          v45 = DCCDNUtil_SetRegistryBinary(v66, v44, L"hashValue", *((const BYTE **)*v13 + 41), 0x10u);
        }
        catch ( std::bad_alloc )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCF,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerregistry.cpp",
            (const char *)0x8007000ELL,
            v60);
          std::wstring::_Tidy_deallocate(v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v66);
LABEL_62:
          std::wstring::_Tidy_deallocate(Src);
          std::wstring::_Tidy_deallocate(v82);
          v7 = -2147024882;
LABEL_63:
          DCRegistryProvider::~DCRegistryProvider((DCRegistryProvider *)v83);
          return v7;
        }
        v46 = v45;
        if ( v45 < 0 )
        {
          v47 = CDeclaredConfigurationLogger::GetLogger();
          v48 = (const unsigned __int16 *)Src;
          if ( v76 > 7 )
            v48 = (const unsigned __int16 *)Src[0];
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v47,
            L"DriftControlComputeHashValuePerRegistry",
            L"DCCDNUtil_SetRegistryBinary hashValue",
            v48,
            v46);
        }
        v20 = (char *)a3 + 88;
        v12 = (unsigned int)v64;
      }
      VariantInit(&pvarg);
      v49 = (const unsigned __int16 *)v80;
      if ( v81 > 7 )
        v49 = v80[0];
      if ( (int)SetVariantValueToSet(v67, a2, a3, *v13, v49, &pvarg) >= 0 && pvarg.vt )
      {
        v64 = 0;
        v77 = (HKEY *)&v64;
        v78 = 0;
        v79 = 1;
        v51 = ComputeHashValue(&pvarg, (unsigned __int8 **)&v78, v50);
        wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&v77);
        if ( v51 >= 0 )
        {
          v52 = (_QWORD *)*((_QWORD *)*v13 + 41);
          if ( !v52 )
          {
            v53 = v64 == 0;
            goto LABEL_56;
          }
          if ( !v64 )
            goto LABEL_57;
          v54 = *v64 - *v52;
          if ( *v64 == *v52 )
            v54 = v64[1] - v52[1];
          v53 = v54 == 0;
LABEL_56:
          if ( !v53 )
          {
LABEL_57:
            tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>>(&v65);
            *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::operator->(
                                    &v65,
                                    v68)
                     + 272LL) = 0;
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>(v68);
            v55 = *((_DWORD *)a3 + 32);
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::operator->(
                                     &v65,
                                     v69)
                      + 280LL) = v55;
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>(v69);
            v56 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::operator->(
                               &v65,
                               v70)
                + 288LL;
            std::wstring::operator=(v56, v20);
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>(v70);
            v57 = *v13;
            v58 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::operator->(
                               &v65,
                               v71)
                + 320LL;
            std::wstring::operator=(v58, v57);
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>(v71);
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::operator->(
                                     &v65,
                                     v72)
                      + 276LL) = 0;
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>(v72);
            tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::complete(&v65);
            wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>,wil::err_returncode_policy>(&v65);
          }
        }
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v64);
      }
      VariantClear(&pvarg);
      std::wstring::_Tidy_deallocate(v80);
    }
    LODWORD(v64) = ++v12;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v66);
    std::wstring::_Tidy_deallocate(Src);
LABEL_61:
    v13 += 2;
    v14 = v73;
  }
  std::wstring::_Tidy_deallocate(v82);
  DCRegistryProvider::~DCRegistryProvider((DCRegistryProvider *)v83);
  return 0;
}

```

## disassembly

```asm
0x1800e82c0  push    rbx
0x1800e82c2  push    rsi
0x1800e82c3  push    rdi
0x1800e82c4  push    r12
0x1800e82c6  push    r13
0x1800e82c8  push    r14
0x1800e82ca  push    r15
0x1800e82cc  sub     rsp, 290h
0x1800e82d3  mov     rax, cs:__security_cookie
0x1800e82da  xor     rax, rsp
0x1800e82dd  mov     [rsp+2C8h+var_48], rax
0x1800e82e5  mov     r13, r8
0x1800e82e8  mov     rdi, rdx
0x1800e82eb  mov     rsi, rcx
0x1800e82ee  mov     [rsp+2C8h+var_280], rcx
0x1800e82f3  lea     rcx, [rsp+2C8h+var_1B0]; this
0x1800e82fb  call    ??0DCRegistryProvider@@QEAA@XZ; DCRegistryProvider::DCRegistryProvider(void)
0x1800e8300  nop
0x1800e8301  xor     r14d, r14d
0x1800e8304  mov     [rsp+2C8h+var_68], r14w
0x1800e830d  mov     [rsp+2C8h+var_88], r14w
0x1800e8316  lea     r8, aCspD; "CSP%d"
0x1800e831d  lea     edx, [r14+0Fh]; unsigned __int64
0x1800e8321  lea     rcx, [rsp+2C8h+var_88]; unsigned __int16 *
0x1800e8329  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e832e  mov     ebx, eax
0x1800e8330  test    eax, eax
0x1800e8332  jns     short loc_1800E8354
0x1800e8334  mov     rcx, [rsp+2C8h]; this
0x1800e833c  mov     r9d, eax; char *
0x1800e833f  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e8346  lea     edx, [r14+7Ch]; void *
0x1800e834a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e834f  jmp     loc_1800E8B3F
0x1800e8354  lea     rcx, [rsp+2C8h+var_1D0]
0x1800e835c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e8361  nop
0x1800e8362  lea     rdx, aCooked_0; "cooked\\"
0x1800e8369  lea     rcx, [rsp+2C8h+Src]
0x1800e8371  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e8376  nop
0x1800e8377  lea     r8, [rsp+2C8h+var_88]
0x1800e837f  mov     rdx, rax
0x1800e8382  lea     rcx, [rsp+2C8h+var_1F0]
0x1800e838a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800e838f  mov     rdx, rax
0x1800e8392  lea     rcx, [rsp+2C8h+var_1D0]
0x1800e839a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e839f  lea     rcx, [rsp+2C8h+var_1F0]
0x1800e83a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e83ac  nop
0x1800e83ad  lea     rcx, [rsp+2C8h+Src]
0x1800e83b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e83ba  nop
0x1800e83bb  mov     rdx, [rsi]
0x1800e83be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800e83c2  inc     r8
0x1800e83c5  cmp     [rdx+r8*2], r14w
0x1800e83ca  jnz     short loc_1800E83C2
0x1800e83cc  lea     rcx, [rsp+2C8h+var_1A8]
0x1800e83d4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800e83d9  mov     [rsp+2C8h+var_1B0], 1
0x1800e83e1  mov     r15d, 1
0x1800e83e7  mov     dword ptr [rsp+2C8h+var_298], r15d
0x1800e83ec  mov     rsi, [r13+10h]
0x1800e83f0  mov     rax, [r13+18h]
0x1800e83f4  mov     [rsp+2C8h+var_250], rax
0x1800e83f9  cmp     rsi, rax
0x1800e83fc  jz      loc_1800E8B50
0x1800e8402  mov     rax, [rsi]
0x1800e8405  cmp     dword ptr [rax+0B8h], 1
0x1800e840c  jnz     loc_1800E8B11
0x1800e8412  mov     r9d, r15d
0x1800e8415  lea     r8, aUriD_0; "URI%d"
0x1800e841c  mov     edx, 0Fh; unsigned __int64
0x1800e8421  lea     rcx, [rsp+2C8h+var_68]; unsigned __int16 *
0x1800e8429  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e842e  mov     ebx, eax
0x1800e8430  test    eax, eax
0x1800e8432  jns     short loc_1800E8463
0x1800e8434  mov     rcx, [rsp+2C8h]; this
0x1800e843c  mov     r9d, eax; char *
0x1800e843f  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e8446  mov     edx, 94h; void *
0x1800e844b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e8450  nop
0x1800e8451  lea     rcx, [rsp+2C8h+var_1D0]
0x1800e8459  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e845e  jmp     loc_1800E8B3F
0x1800e8463  lea     rcx, [rsp+2C8h+Src]
0x1800e846b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e8470  nop
0x1800e8471  mov     r14, [rsi]
0x1800e8474  lea     rbx, [rdi+20h]
0x1800e8478  mov     r8, rbx
0x1800e847b  lea     rdx, asc_180142BE8; "./"
0x1800e8482  lea     rcx, [rsp+2C8h+var_128]
0x1800e848a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800e848f  nop
0x1800e8490  lea     r8, asc_18013EB9C; "/"
0x1800e8497  mov     rdx, rax
0x1800e849a  lea     rcx, [rsp+2C8h+var_148]
0x1800e84a2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800e84a7  nop
0x1800e84a8  lea     r12, [r13+58h]
0x1800e84ac  mov     r8, r12
0x1800e84af  mov     rdx, rax
0x1800e84b2  lea     rcx, [rsp+2C8h+var_168]
0x1800e84ba  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e84bf  nop
0x1800e84c0  lea     r8, asc_18013EB9C; "/"
0x1800e84c7  mov     rdx, rax
0x1800e84ca  lea     rcx, [rsp+2C8h+var_188]
0x1800e84d2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800e84d7  nop
0x1800e84d8  mov     r8, r14
0x1800e84db  mov     rdx, rax
0x1800e84de  lea     rcx, [rsp+2C8h+var_210]
0x1800e84e6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e84eb  mov     rdx, rax
0x1800e84ee  lea     rcx, [rsp+2C8h+Src]
0x1800e84f6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e84fb  lea     rcx, [rsp+2C8h+var_210]
0x1800e8503  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8508  nop
0x1800e8509  lea     rcx, [rsp+2C8h+var_188]
0x1800e8511  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8516  nop
0x1800e8517  lea     rcx, [rsp+2C8h+var_168]
0x1800e851f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8524  nop
0x1800e8525  lea     rcx, [rsp+2C8h+var_148]
0x1800e852d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8532  nop
0x1800e8533  lea     rcx, [rsp+2C8h+var_128]
0x1800e853b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8540  cmp     qword ptr [rdi+38h], 7
0x1800e8545  jbe     short loc_1800E854A
0x1800e8547  mov     rbx, [rbx]
0x1800e854a  lea     rdx, aUser_0; "user"
0x1800e8551  mov     rcx, rbx
0x1800e8554  call    cs:__imp__o__wcsicmp
0x1800e855a  xor     r14d, r14d
0x1800e855d  test    eax, eax
0x1800e855f  jnz     short loc_1800E858F
0x1800e8561  lea     r9, [rdi+40h]
0x1800e8565  mov     rax, [rdi+50h]
0x1800e8569  cmp     qword ptr [rdi+58h], 7
0x1800e856e  jbe     short loc_1800E8573
0x1800e8570  mov     r9, [r9]
0x1800e8573  mov     [rsp+2C8h+var_2A8], rax; void *
0x1800e8578  mov     edx, 2
0x1800e857d  lea     r8d, [rdx+2]
0x1800e8581  lea     rcx, [rsp+2C8h+Src]; Src
0x1800e8589  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800e858e  nop
0x1800e858f  mov     rdx, [rsi]
0x1800e8592  lea     rax, [rdx+148h]
0x1800e8599  mov     [rsp+2C8h+var_210], rax
0x1800e85a1  mov     [rsp+2C8h+var_208], r14
0x1800e85a9  mov     [rsp+2C8h+var_200], 1
0x1800e85b1  lea     r8, [rsp+2C8h+Src]
0x1800e85b9  cmp     [rsp+2C8h+var_218], 7
0x1800e85c2  cmova   r8, [rsp+2C8h+Src]
0x1800e85cb  lea     r9, [rsp+2C8h+var_208]
0x1800e85d3  lea     rcx, [rsp+2C8h+var_1B0]
0x1800e85db  call    RegistryProvider_DriftControlComputeHashValuePerUri
0x1800e85e0  mov     ebx, eax
0x1800e85e2  lea     rcx, [rsp+2C8h+var_210]
0x1800e85ea  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<uchar [0]>>::~out_param_t<std::unique_ptr<uchar [0]>>(void)
0x1800e85ef  test    ebx, ebx
0x1800e85f1  jns     short loc_1800E862C
0x1800e85f3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800e85f8  lea     r9, [rsp+2C8h+Src]
0x1800e8600  cmp     [rsp+2C8h+var_218], 7
0x1800e8609  cmova   r9, [rsp+2C8h+Src]; unsigned __int16 *
0x1800e8612  mov     dword ptr [rsp+2C8h+var_2A8], ebx; int
0x1800e8616  lea     r8, aRegistryprovid_12; "RegistryProvider_DriftControlComputeHas"...
0x1800e861d  lea     rdx, aRegistryprovid_5; "RegistryProvider_DriftControlComputeHas"...
0x1800e8624  mov     rcx, rax; this
0x1800e8627  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800e862c  mov     [rsp+2C8h+var_288], r14
0x1800e8631  test    ebx, ebx
0x1800e8633  js      loc_1800E8AF1
0x1800e8639  mov     rax, [rsi]
0x1800e863c  cmp     [rax+148h], r14
0x1800e8643  jz      loc_1800E8AF1
0x1800e8649  lea     rax, [rsp+2C8h+var_288]
0x1800e864e  mov     [rsp+2C8h+var_210], rax
0x1800e8656  mov     [rsp+2C8h+var_208], r14
0x1800e865e  mov     [rsp+2C8h+var_200], 1
0x1800e8666  lea     r8, [rdi+60h]
0x1800e866a  cmp     qword ptr [rdi+78h], 7
0x1800e866f  jbe     short loc_1800E8674
0x1800e8671  mov     r8, [r8]; unsigned __int16 *
0x1800e8674  cmp     qword ptr [rdi+18h], 7
0x1800e8679  jbe     short loc_1800E8680
0x1800e867b  mov     rdx, [rdi]
0x1800e867e  jmp     short loc_1800E8683
0x1800e8680  mov     rdx, rdi; unsigned __int16 *
0x1800e8683  mov     dword ptr [rsp+2C8h+var_2A8], r14d; int
0x1800e8688  lea     r9, [rsp+2C8h+var_208]; HKEY *
0x1800e8690  mov     rcx, [rsp+2C8h+var_280]; struct DeclaredConfigurationScopeData *
0x1800e8695  call    ?DCGetEnrollmentIdSidStateDocIdVersionKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DCGetEnrollmentIdSidStateDocIdVersionKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x1800e869a  mov     ebx, eax
0x1800e869c  lea     rcx, [rsp+2C8h+var_210]
0x1800e86a4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e86a9  test    ebx, ebx
0x1800e86ab  jns     short loc_1800E86E6
0x1800e86ad  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800e86b2  lea     r9, [rsp+2C8h+Src]
0x1800e86ba  cmp     [rsp+2C8h+var_218], 7
0x1800e86c3  cmova   r9, [rsp+2C8h+Src]; unsigned __int16 *
0x1800e86cc  mov     dword ptr [rsp+2C8h+var_2A8], ebx; int
0x1800e86d0  lea     r8, aDcgetenrollmen; "DCGetEnrollmentIdSidStateDocIdVersionKe"...
0x1800e86d7  lea     rdx, aRegistryprovid_5; "RegistryProvider_DriftControlComputeHas"...
0x1800e86de  mov     rcx, rax; this
0x1800e86e1  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800e86e6  lea     rcx, [rsp+2C8h+var_1F0]
0x1800e86ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e86f3  nop
0x1800e86f4  test    ebx, ebx
0x1800e86f6  js      loc_1800E88D4
0x1800e86fc  lea     rdx, [rsp+2C8h+var_68]
0x1800e8704  lea     rcx, [rsp+2C8h+var_A8]
0x1800e870c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e8711  mov     r12, rax
0x1800e8714  lea     rdx, StringValue; "\\"
0x1800e871b  lea     rcx, [rsp+2C8h+var_C8]
0x1800e8723  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e8728  mov     r15, rax
0x1800e872b  lea     rdx, [rsp+2C8h+var_88]
0x1800e8733  lea     rcx, [rsp+2C8h+var_E8]
0x1800e873b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e8740  mov     r14, rax
0x1800e8743  lea     rdx, StringValue; "\\"
0x1800e874a  lea     rcx, [rsp+2C8h+var_108]
0x1800e8752  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e8757  mov     rbx, rax
0x1800e875a  lea     rdx, aCooked; "cooked"
0x1800e8761  lea     rcx, [rsp+2C8h+var_210]
0x1800e8769  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e876e  nop
0x1800e876f  mov     r8, rbx
0x1800e8772  mov     rdx, rax
0x1800e8775  lea     rcx, [rsp+2C8h+var_188]
0x1800e877d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800e8782  nop
0x1800e8783  mov     r8, r14
0x1800e8786  mov     rdx, rax
0x1800e8789  lea     rcx, [rsp+2C8h+var_168]
0x1800e8791  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800e8796  nop
0x1800e8797  mov     r8, r15
0x1800e879a  mov     rdx, rax
0x1800e879d  lea     rcx, [rsp+2C8h+var_148]
0x1800e87a5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800e87aa  nop
0x1800e87ab  mov     r8, r12
0x1800e87ae  mov     rdx, rax
0x1800e87b1  lea     rcx, [rsp+2C8h+var_128]
0x1800e87b9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800e87be  mov     rdx, rax
0x1800e87c1  lea     rcx, [rsp+2C8h+var_1F0]
0x1800e87c9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e87ce  lea     rcx, [rsp+2C8h+var_128]
0x1800e87d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e87db  nop
0x1800e87dc  lea     rcx, [rsp+2C8h+var_148]
0x1800e87e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e87e9  nop
0x1800e87ea  lea     rcx, [rsp+2C8h+var_168]
0x1800e87f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e87f7  nop
0x1800e87f8  lea     rcx, [rsp+2C8h+var_188]
0x1800e8800  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8805  nop
0x1800e8806  lea     rcx, [rsp+2C8h+var_210]
0x1800e880e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8813  nop
0x1800e8814  lea     rcx, [rsp+2C8h+var_108]
0x1800e881c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8821  nop
0x1800e8822  lea     rcx, [rsp+2C8h+var_E8]
0x1800e882a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e882f  nop
0x1800e8830  lea     rcx, [rsp+2C8h+var_C8]
0x1800e8838  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e883d  nop
0x1800e883e  lea     rcx, [rsp+2C8h+var_A8]
0x1800e8846  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e884b  nop
0x1800e884c  mov     rax, [rsi]
0x1800e884f  lea     rdx, [rsp+2C8h+var_1F0]
0x1800e8857  cmp     [rsp+2C8h+var_1D8], 7
0x1800e8860  cmova   rdx, [rsp+2C8h+var_1F0]; unsigned __int16 *
0x1800e8869  mov     dword ptr [rsp+2C8h+var_2A8], 10h; unsigned int
0x1800e8871  mov     r9, [rax+148h]; void *
0x1800e8878  lea     r8, aHashvalue; "hashValue"
0x1800e887f  mov     rcx, [rsp+2C8h+var_288]; HKEY
  ... truncated ...
```
