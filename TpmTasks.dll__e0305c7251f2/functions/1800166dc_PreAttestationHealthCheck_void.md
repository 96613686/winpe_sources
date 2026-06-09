# PreAttestationHealthCheck(void)

- ea: `0x1800166dc`
- end: `0x180017946`
- name: `?PreAttestationHealthCheck@@YAXXZ`
- size: `4714`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x180009b2c`
- `0x180009c8c`
- `0x18000b534`
- `0x18000b80c`
- `0x18000bc54`
- `0x18000c4b4`
- `0x18000d410`
- `0x18000d524`
- `0x18000dd54`
- `0x18000e48c`
- `0x18000e5a8`
- `0x18000ea88`
- `0x18000efa4`
- `0x18000f654`
- `0x180011130`
- `0x180011218`
- `0x180014d38`
- `0x180014e34`
- `0x1800166dc`
- `0x18001c578`
- `0x18001cedc`
- `0x18001dd80`
- `0x180023634`
- `0x18002386c`
- `0x180023a50`
- `0x180023ca8`
- `0x180024de0`
- `0x180024e4c`
- `0x180024eb8`
- `0x180025894`
- `0x180038c00`
- `0x18003fbe4`
- `0x1800434f8`
- `0x180043748`
- `0x180043d8c`
- `0x1800451ec`
- `0x180058970`
- `0x180058a40`
- `0x18005e010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800169ec`
- `msvcp_win!_Xtime_get_ticks` at `0x1800169fa`
- `msvcp_win!_Xtime_get_ticks` at `0x1800169ec`
- `msvcp_win!_Xtime_get_ticks` at `0x1800169fa`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180016d42`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180016d42`
- `ntdll!NtQuerySystemInformation` at `0x180016c69`
- `ntdll!NtQuerySystemInformation` at `0x180016c90`
- `ntdll!NtQuerySystemInformation` at `0x180016c69`
- `ntdll!NtQuerySystemInformation` at `0x180016c90`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800178b3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800178b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017879`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016ac3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016b18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016b70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016ac3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016b18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016b70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178d2`
- `ncrypt!NCryptFreeObject` at `0x1800167a3`
- `ncrypt!NCryptFreeObject` at `0x180016903`
- `ncrypt!NCryptFreeObject` at `0x1800167a3`
- `ncrypt!NCryptFreeObject` at `0x180016903`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001677c`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800168dc`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001677c`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800168dc`
- `ncrypt!NCryptGetProperty` at `0x1800167f2`
- `ncrypt!NCryptGetProperty` at `0x1800167f2`
- `TpmCoreProvisioning!TpmCertGetWindowsAik` at `0x1800167c2`
- `TpmCoreProvisioning!TpmCertGetWindowsAik` at `0x180016922`
- `TpmCoreProvisioning!TpmCertGetWindowsAik` at `0x1800167c2`
- `TpmCoreProvisioning!TpmCertGetWindowsAik` at `0x180016922`
- `TpmCoreProvisioning!TpmGet_IsTpmPresent` at `0x180016724`
- `TpmCoreProvisioning!TpmGet_IsTpmPresent` at `0x180016724`
- `TpmCoreProvisioning!TpmGet_IsTpmVersion20` at `0x18001672f`
- `TpmCoreProvisioning!TpmGet_IsTpmVersion20` at `0x18001672f`

## string_xrefs

- `0x180017802`: `.json`
- `0x180016b64`: `PhysicalPcrReadError`
- `0x180017527`: `SecureCorePCCompliant`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
void __fastcall PreAttestationHealthCheck()
{
  NCRYPT_HANDLE v0; // rbx
  int v1; // esi
  bool v2; // r15
  char v3; // di
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  char v7; // r12
  int v8; // r13d
  __int64 ticks; // rbx
  HKEY WbclInstanceKey; // rbx
  LSTATUS ValueW; // eax
  bool v12; // sf
  LSTATUS v13; // eax
  bool v14; // sf
  char v15; // si
  LSTATUS v16; // eax
  bool v17; // sf
  LSTATUS v18; // eax
  bool v19; // sf
  __int64 v20; // rcx
  bool v21; // bl
  __int64 v22; // rax
  const wchar_t *v23; // rdx
  void (__fastcall *v24)(const unsigned __int16 *); // rax
  __int64 v25; // rdx
  int v26; // ebx
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // ebx
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // ebx
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  int v44; // ebx
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  int v50; // ebx
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rax
  bool v54; // di
  __int64 v55; // rbx
  int v56; // esi
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rdx
  int v63; // ebx
  __int64 v64; // rdx
  int v65; // eax
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rdi
  __int64 v69; // rdx
  int v70; // ebx
  __int64 v71; // rdx
  int v72; // eax
  DWORD v73; // r13d
  __int64 v74; // rax
  __int64 v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rdi
  __int64 v78; // rdx
  __int64 v79; // rdx
  int v80; // esi
  int v81; // eax
  __int64 v82; // rax
  __int64 v83; // rsi
  __int64 v84; // rdx
  __int64 v85; // rdi
  __int64 v86; // rdx
  int v87; // ebx
  __int64 v88; // rdx
  int v89; // eax
  __int64 v90; // rax
  __int64 v91; // rdx
  int v92; // ebx
  __int64 v93; // rdx
  int v94; // eax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rdx
  int v98; // ebx
  __int64 v99; // rdx
  int v100; // eax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rcx
  __int64 WbclInstanceName; // rax
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  const WCHAR *v110; // rax
  char v111; // dl
  HANDLE FileW; // rax
  void *v113; // rbx
  const void *v114; // rax
  DWORD v115; // r8d
  DWORD LastError; // eax
  bool v117; // [rsp+40h] [rbp-C0h] BYREF
  bool v118; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int8 v119; // [rsp+42h] [rbp-BEh] BYREF
  unsigned __int8 v120; // [rsp+43h] [rbp-BDh] BYREF
  bool v121; // [rsp+44h] [rbp-BCh]
  bool v122; // [rsp+45h] [rbp-BBh]
  char v123; // [rsp+46h] [rbp-BAh]
  bool v124; // [rsp+47h] [rbp-B9h]
  DWORD pcbResult; // [rsp+48h] [rbp-B8h] BYREF
  int v126; // [rsp+4Ch] [rbp-B4h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  bool v128; // [rsp+58h] [rbp-A8h]
  DWORD pvData; // [rsp+5Ch] [rbp-A4h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  void (__fastcall *v132)(const unsigned __int16 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v133; // [rsp+78h] [rbp-88h] BYREF
  DWORD v134; // [rsp+80h] [rbp-80h]
  _BYTE v135[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v136[232]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v137[8]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v138[232]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v139[240]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v140[240]; // [rsp+360h] [rbp+260h] BYREF
  __int128 v141; // [rsp+450h] [rbp+350h] BYREF
  __int128 v142; // [rsp+460h] [rbp+360h]
  _OWORD SystemInformation[2]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v144[32]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v145[32]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v146[32]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _DWORD v147[8]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v2 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v3 = 0;
  TpmGet_IsTpmPresent(&v119);
  TpmGet_IsTpmVersion20(&v120);
  if ( v119 )
    v121 = (int)TpmApiGetRandom(v4, SystemInformation) >= 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl'::`2'::impl) )
  {
    hObject = 0;
    phProvider = 0;
    if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) < 0 )
      goto LABEL_11;
    v0 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v132);
      NCryptFreeObject(v0);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v132);
    }
    hObject = 0;
    if ( (int)TpmCertGetWindowsAik(phProvider, &hObject) >= 0
      && (pcbResult = 0, NCryptGetProperty(hObject, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0) >= 0)
      && pcbResult )
    {
      v3 = 1;
    }
    else
    {
LABEL_11:
      g_fpGetMemory = (void *(*)(unsigned __int64))WinPlatformGetMemory;
      g_fpFreeMemory = (void (*)(void *))wil::details::FreeProcessHeap;
      g_fpIdle = WinPlatformIdle;
      g_fpTpmSubmit = (unsigned int (*)(unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))WinPlatformTbsSubmit;
      g_fpW8TpmSubmit = WinPlatformW8TbsSubmit;
      g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))WinPlatformGetRandom;
      g_fpSha1Hash = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))WinPlatformSha1Hash;
      g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))WinPlatformHash;
      g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbEncrypt;
      g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbDecrypt;
      v118 = 0;
      if ( (int)TrustedPlatformModule::CheckUpdateEkCertPresent(v6, v5, &v118) >= 0 && v118 )
        v3 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  }
  else
  {
    hObject = 0;
    phProvider = 0;
    if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) >= 0 )
    {
      v0 = hObject;
      if ( hObject )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v132);
        NCryptFreeObject(v0);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v132);
      }
      hObject = 0;
      if ( (int)TpmCertGetWindowsAik(phProvider, &hObject) >= 0 )
        v3 = 1;
    }
    pcbResult = 0;
    if ( (int)HWSecurityRegistryManager::GetDWordNoThrow(25, &pcbResult) >= 0 && pcbResult )
      v3 = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  v7 = 0;
  pcbResult = 0;
  v134 = 0;
  v8 = 0;
  LOBYTE(v1) = 0;
  LODWORD(hObject) = v1;
  LOBYTE(v0) = 0;
  LODWORD(phProvider) = v0;
  v122 = 0;
  v118 = 0;
  v132 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::GetImpl'::`2'::impl) )
  {
    v117 = 0;
    if ( (int)IsBootWbclLogPresent(&v117) >= 0 )
      LODWORD(phProvider) = v117;
    if ( (int)IsCurrentWbclLogPresent(&v117) >= 0 )
      LODWORD(hObject) = v117;
  }
  TpmTaskDebugProvider::TpmTaskGetWbclInformationStarted();
  ticks = _Xtime_get_ticks();
  ValidatePcrMatchesLog();
  v133 = (_Xtime_get_ticks() - ticks) / 10000;
  TpmTaskDebugProvider::TpmTaskGetWbclInformationEnded<__int64>(&v133);
  WbclInstanceKey = GetWbclInstanceKey();
  *(_QWORD *)&SystemInformation[0] = WbclInstanceKey;
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(WbclInstanceKey, 0, L"PcrsMatched", 0x10u, 0, &pvData, &pcbData);
  v12 = ValueW < 0;
  if ( ValueW > 0 )
    v12 = 1;
  if ( !v12 )
  {
    v117 = 1;
LABEL_37:
    v15 = 1;
    goto LABEL_48;
  }
  v117 = 0;
  v13 = RegGetValueW(WbclInstanceKey, 0, L"MismatchedPcrsMask", 0x10u, 0, &pvData, &pcbData);
  v14 = v13 < 0;
  if ( v13 > 0 )
    v14 = 1;
  if ( !v14 )
  {
    pcbResult = pvData;
    goto LABEL_37;
  }
  v15 = 0;
  v16 = RegGetValueW(WbclInstanceKey, 0, L"ReplayPcrError", 0x10u, 0, &pvData, &pcbData);
  v17 = v16 < 0;
  if ( v16 > 0 )
    v17 = 1;
  if ( !v17 )
  {
    v134 = pvData;
    if ( pvData != -2147418113 )
      v15 = 1;
    v2 = 0;
  }
  v18 = RegGetValueW(WbclInstanceKey, 0, L"PhysicalPcrReadError", 0x10u, 0, &pvData, &pcbData);
  v19 = v18 < 0;
  if ( v18 > 0 )
    v19 = 1;
  if ( !v19 )
    v8 = pvData;
LABEL_48:
  v126 = 0;
  if ( (int)HWSecurityRegistryManager::GetDWordNoThrow(34, &v126) >= 0 )
    v122 = v126 == 1;
  if ( (int)HWSecurityRegistryManager::GetDWordNoThrow(32, &v126) >= 0 )
    v118 = v126 == 1;
  HWSecurityRegistryManager::GetDWordNoThrow(35, &v126);
  HWSecurityRegistryManager::GetQWordNoThrow(v20, &v132);
  v126 = 0;
  LODWORD(v133) = 0;
  if ( (int)HWSecurityRegistryManager::GetDWordNoThrow(27, &v126) >= 0
    && v126
    && (int)HWSecurityRegistryManager::GetDWordNoThrow(31, &v133) >= 0
    && (_DWORD)v133 )
  {
    v7 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)SystemInformation);
  v21 = 0;
  SystemInformation[0] = 0;
  memset(v147, 0, sizeof(v147));
  if ( NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, SystemInformation, 0x10u, 0) >= 0 )
    v21 = (SystemInformation[0] & 2) != 0;
  if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, v147, 0x20u, 0) >= 0 )
    v2 = (v147[6] & 8) != 0;
  LODWORD(v133) = 0;
  IsSecureBootEnabled((enum SBServicingState::State *)&v133);
  v128 = (_DWORD)v133 == 0;
  v124 = (v2 || v7) && v21 && !(_DWORD)v133;
  if ( !v118 && !v7 || !v132 || (v123 = 1, !v122) )
    v123 = 0;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v135);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v140);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v139);
  v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L"{\"Version\":");
  std::basic_ostream<unsigned short>::operator<<(v22, 1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L",\"HealthStatus\":");
  if ( v119 && v121 && v120 && v15 && v3 )
  {
    v23 = L"\"Attestable\"";
    if ( !v117 )
      v23 = L"\"Possibly attestable\"";
    v24 = LogHealthcheckSuccess;
    if ( !v117 )
      v24 = LogHealthCheckNonCriticalFailure;
  }
  else
  {
    v24 = LogHealthcheckFailure;
    v23 = L"\"Cannot be attested\"";
  }
  v132 = v24;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, v23);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L",\"Required\":[");
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v25) = 1;
  v26 = BoolToJson(v144, v25);
  LOBYTE(v27) = v119;
  v28 = BoolToJson(v145, v27);
  v29 = FormatJsonSingleton((unsigned int)SystemInformation, (unsigned int)L"TpmPresent", v28, v26, (__int64)&v141);
  v30 = std::operator<<<unsigned short>(v135, v29);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, L",");
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(&v141);
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v31) = 1;
  v32 = BoolToJson(SystemInformation, v31);
  LOBYTE(v33) = v120;
  v34 = BoolToJson(v145, v33);
  v35 = FormatJsonSingleton((unsigned int)v144, (unsigned int)L"TpmMeetsMinimumVersion", v34, v32, (__int64)&v141);
  v36 = std::operator<<<unsigned short>(v135, v35);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, L",");
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v37) = 1;
  v38 = BoolToJson(SystemInformation, v37);
  LOBYTE(v39) = v121;
  v40 = BoolToJson(v145, v39);
  v41 = FormatJsonSingleton((unsigned int)v144, (unsigned int)L"TpmIsResponsive", v40, v38, (__int64)&v141);
  v42 = std::operator<<<unsigned short>(v135, v41);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, L",");
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v43) = 1;
  v44 = BoolToJson(SystemInformation, v43);
  LOBYTE(v45) = v3;
  v46 = BoolToJson(v145, v45);
  v47 = FormatJsonSingleton((unsigned int)v144, (unsigned int)L"EkCertIsAvailable", v46, v44, (__int64)&v141);
  v48 = std::operator<<<unsigned short>(v135, v47);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, L",");
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v49) = 1;
  v50 = BoolToJson(SystemInformation, v49);
  LOBYTE(v51) = v15;
  v52 = BoolToJson(v145, v51);
  v53 = FormatJsonSingleton((unsigned int)v144, (unsigned int)L"TcgLogFound", v52, v50, (__int64)&v141);
  std::operator<<<unsigned short>(v135, v53);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L"],\"Expected\":[");
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v137);
  v54 = v117;
  if ( !v117 )
  {
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, L"{");
    v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, L"\"SoftwarePcrReplayHresult\":");
    v56 = v134;
    v57 = std::to_wstring(v144, v134);
    std::operator<<<unsigned short>(v55, v57);
    std::wstring::_Tidy_deallocate(v144);
    v58 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, L",\"HardwarePcrReplayHresult\":");
    v59 = std::to_wstring(v144, (unsigned int)v8);
    std::operator<<<unsigned short>(v58, v59);
    std::wstring::_Tidy_deallocate(v144);
    if ( v56 >= 0 && v8 >= 0 )
    {
      v60 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, L",\"BitMaskOfPcrMismatches\":");
      v61 = std::to_wstring(v144, pcbResult);
      std::operator<<<unsigned short>(v60, v61);
      std::wstring::_Tidy_deallocate(v144);
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, L"}");
  }
  std::basic_stringbuf<unsigned short>::str(v138, &v141);
  LOBYTE(v62) = 1;
  v63 = BoolToJson(SystemInformation, v62);
  LOBYTE(v64) = v54;
  v65 = BoolToJson(v145, v64);
  v66 = FormatJsonSingleton((unsigned int)v144, (unsigned int)L"PcrsMatchTcgLog", v65, v63, (__int64)&v141);
  std::operator<<<unsigned short>(v135, v66);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L"],\"Informational\":[");
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v67) = 1;
  v68 = BoolToJson(v146, v67);
  LOBYTE(v69) = v122;
  v70 = BoolToJson(SystemInformation, v69);
  LOBYTE(v71) = v128;
  v72 = BoolToJson(v145, v71);
  v73 = pcbResult;
  v74 = FormatJsonTcgLogBackedObject(
          (unsigned int)v144,
          (unsigned int)L"SecureBootEnabled",
          v72,
          v70,
          v68,
          pcbResult,
          128,
          (__int64)&v141);
  std::operator<<<unsigned short>(v135, v74);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(v146);
  std::wstring::_Tidy_deallocate(&v141);
  v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L",");
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v76) = 1;
  v77 = BoolToJson(SystemInformation, v76);
  LOBYTE(v78) = v118;
  v80 = BoolToJson(v145, v78);
  LOBYTE(v79) = v2 || v7;
  v81 = BoolToJson(v144, v79);
  v82 = FormatJsonTcgLogBackedObject(
          (unsigned int)v146,
          (unsigned int)L"VirtualSecureMemory",
          v81,
          v80,
          v77,
          v73,
          0x20000,
          (__int64)&v141);
  std::operator<<<unsigned short>(v75, v82);
  std::wstring::_Tidy_deallocate(v146);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  v83 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L",");
  std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
  LOBYTE(v84) = 1;
  v85 = BoolToJson(SystemInformation, v84);
  LOBYTE(v86) = v123;
  v87 = BoolToJson(v145, v86);
  LOBYTE(v88) = v124;
  v89 = BoolToJson(v144, v88);
  v90 = FormatJsonTcgLogBackedObject(
          (unsigned int)v146,
          (unsigned int)L"SecureCorePCCompliant",
          v89,
          v87,
          v85,
          v73,
          135296,
          (__int64)&v141);
  std::operator<<<unsigned short>(v83, v90);
  std::wstring::_Tidy_deallocate(v146);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(v145);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(&v141);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::GetImpl'::`2'::impl) )
  {
    std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
    LOBYTE(v91) = 1;
    v92 = BoolToJson(v145, v91);
    LOBYTE(v93) = phProvider;
    v94 = BoolToJson(v144, v93);
    v95 = FormatJsonSingleton(
            (unsigned int)v146,
            (unsigned int)L"BootTcgLogFoundInFileSystem",
            v94,
            v92,
            (__int64)&v141);
    v96 = std::operator<<<unsigned short>(v135, v95);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, L",");
    std::wstring::_Tidy_deallocate(v146);
    std::wstring::_Tidy_deallocate(v144);
    std::wstring::_Tidy_deallocate(v145);
    std::wstring::_Tidy_deallocate(&v141);
    std::wstring::wstring((__int64)&v141, (__int64)&sourceString);
    LOBYTE(v97) = 1;
    v98 = BoolToJson(v145, v97);
    LOBYTE(v99) = hObject;
    v100 = BoolToJson(v144, v99);
    v101 = FormatJsonSingleton(
             (unsigned int)v146,
             (unsigned int)L"CurrentTcgLogFoundInFileSystem",
             v100,
             v98,
             (__int64)&v141);
    std::operator<<<unsigned short>(v135, v101);
    std::wstring::_Tidy_deallocate(v146);
    std::wstring::_Tidy_deallocate(v144);
    std::wstring::_Tidy_deallocate(v145);
    std::wstring::_Tidy_deallocate(&v141);
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, L"]}");
  std::basic_stringbuf<unsigned short>::str(v136, v147);
  *(_QWORD *)&SystemInformation[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v147);
  ProvisionTelemetryProvider::TpmTaskPreAttestationCheck<unsigned short const *>((__int64 *)SystemInformation);
  if ( (Microsoft_Windows_TPM_WMIEnableBits & 1) != 0 )
  {
    v102 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v147);
    McTemplateU0z_EventWriteTransfer(v103, TPMCORE_TPMTASKS_HEALTHCHECK_INFORMATIONAL, v102);
  }
  SystemInformation[0] = 0;
  SystemInformation[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(SystemInformation[0]) = 0;
  TpmTasksGetTpmDriverLogPath(SystemInformation);
  WbclInstanceName = GetWbclInstanceName(v146);
  v107 = std::wstring::_Insert<unsigned short>(WbclInstanceName, v105, v106, 1);
  v141 = 0;
  v142 = 0;
  v141 = *(_OWORD *)v107;
  v142 = *(_OWORD *)(v107 + 16);
  *(_QWORD *)(v107 + 16) = 0;
  *(_QWORD *)(v107 + 24) = 7;
  *(_WORD *)v107 = 0;
  v108 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v141);
  std::wstring::_Append<unsigned short>(SystemInformation, v108, v142);
  std::wstring::_Tidy_deallocate(&v141);
  std::wstring::_Tidy_deallocate(v146);
  std::wstring::_Append<unsigned short>(SystemInformation, L".json", 5);
  v109 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(SystemInformation);
  v132((const unsigned __int16 *)v109);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::GetImpl'::`2'::impl);
  v110 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(SystemInformation);
  if ( v111 )
    FileW = CreateFileW(v110, 0x40000000u, 0, 0, 2u, 0x24u, 0);
  else
    FileW = CreateFileW(v110, 0x40000000u, 0, 0, 2u, 0x20u, 0);
  v113 = FileW;
  if ( FileW == (HANDLE)-1LL
    || (LODWORD(hObject) = 0,
        v114 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v147),
        !WriteFile(v113, v114, v115, (LPDWORD)&hObject, 0)) )
  {
    LastError = GetLastError();
    HWSecurityRegistryManager::SetDWordNoThrow(0x46u, LastError);
  }
  CloseHandle(v113);
  std::wstring::_Tidy_deallocate(SystemInformation);
  std::wstring::_Tidy_deallocate(v147);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v137);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v139);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v140);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v135);
}

```

## disassembly

```asm
0x1800166dc  push    rbp
0x1800166de  push    rbx
0x1800166df  push    rsi
0x1800166e0  push    rdi
0x1800166e1  push    r12
0x1800166e3  push    r13
0x1800166e5  push    r14
0x1800166e7  push    r15
0x1800166e9  lea     rbp, [rsp-428h]
0x1800166f1  sub     rsp, 528h
0x1800166f8  mov     rax, cs:__security_cookie
0x1800166ff  xor     rax, rsp
0x180016702  mov     [rbp+460h+var_50], rax
0x180016709  xor     r15d, r15d
0x18001670c  mov     [rsp+560h+var_51E], r15b
0x180016711  mov     [rsp+560h+var_51D], r15b
0x180016716  mov     [rsp+560h+var_51C], r15b
0x18001671b  movzx   edi, r15b
0x18001671f  lea     rcx, [rsp+560h+var_51E]
0x180016724  call    cs:__imp_?TpmGet_IsTpmPresent@@YAJPEAE@Z; TpmGet_IsTpmPresent(uchar *)
0x18001672a  lea     rcx, [rsp+560h+var_51D]
0x18001672f  call    cs:__imp_?TpmGet_IsTpmVersion20@@YAJPEAE@Z; TpmGet_IsTpmVersion20(uchar *)
0x180016735  cmp     [rsp+560h+var_51E], r15b
0x18001673a  jz      short loc_18001674F
0x18001673c  lea     rdx, [rbp+460h+SystemInformation]
0x180016743  call    TpmApiGetRandom
0x180016748  test    eax, eax
0x18001674a  setns   [rsp+560h+var_51C]
0x18001674f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard> `wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl(void)'::`2'::impl
0x180016756  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(void)
0x18001675b  test    al, al
0x18001675d  jz      loc_1800168C3
0x180016763  mov     [rsp+560h+hObject], r15
0x180016768  mov     [rsp+560h+phProvider], r15
0x18001676d  xor     r8d, r8d; dwFlags
0x180016770  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180016777  lea     rcx, [rsp+560h+phProvider]; phProvider
0x18001677c  call    cs:__imp_NCryptOpenStorageProvider
0x180016782  mov     r14d, 1
0x180016788  test    eax, eax
0x18001678a  js      short loc_18001680B
0x18001678c  mov     rbx, [rsp+560h+hObject]
0x180016791  test    rbx, rbx
0x180016794  jz      short loc_1800167B3
0x180016796  lea     rcx, [rsp+560h+var_4F0]; this
0x18001679b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800167a0  mov     rcx, rbx; hObject
0x1800167a3  call    cs:__imp_NCryptFreeObject
0x1800167a9  lea     rcx, [rsp+560h+var_4F0]; this
0x1800167ae  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800167b3  mov     [rsp+560h+hObject], r15
0x1800167b8  lea     rdx, [rsp+560h+hObject]
0x1800167bd  mov     rcx, [rsp+560h+phProvider]
0x1800167c2  call    cs:__imp_?TpmCertGetWindowsAik@@YAJ_KPEA_K@Z; TpmCertGetWindowsAik(unsigned __int64,unsigned __int64 *)
0x1800167c8  test    eax, eax
0x1800167ca  js      short loc_18001680B
0x1800167cc  mov     [rsp+560h+var_518], r15d
0x1800167d1  mov     [rsp+560h+dwFlags], r15d; dwFlags
0x1800167d6  lea     rax, [rsp+560h+var_518]
0x1800167db  mov     [rsp+560h+pcbResult], rax; pcbResult
0x1800167e0  xor     r9d, r9d; cbOutput
0x1800167e3  xor     r8d, r8d; pbOutput
0x1800167e6  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x1800167ed  mov     rcx, [rsp+560h+hObject]; hObject
0x1800167f2  call    cs:__imp_NCryptGetProperty
0x1800167f8  test    eax, eax
0x1800167fa  js      short loc_18001680B
0x1800167fc  cmp     [rsp+560h+var_518], r15d
0x180016801  jz      short loc_18001680B
0x180016803  mov     dil, r14b
0x180016806  jmp     loc_1800168B3
0x18001680b  lea     rax, ?WinPlatformGetMemory@@YAPEAX_K@Z; WinPlatformGetMemory(unsigned __int64)
0x180016812  mov     cs:?g_fpGetMemory@@3P6APEAX_K@ZEA, rax; void * (*g_fpGetMemory)(unsigned __int64)
0x180016819  lea     rax, ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180016820  mov     cs:?g_fpFreeMemory@@3P6AXPEAX@ZEA, rax; void (*g_fpFreeMemory)(void *)
0x180016827  lea     rax, ?WinPlatformIdle@@YAXK@Z; WinPlatformIdle(ulong)
0x18001682e  mov     cs:?g_fpIdle@@3P6AXK@ZEA, rax; void (*g_fpIdle)(ulong)
0x180016835  lea     rax, ?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z; WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)
0x18001683c  mov     cs:?g_fpTpmSubmit@@3P6AIQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpTpmSubmit)(uchar * const,uint,uchar *,uint *)
0x180016843  lea     rax, ?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x18001684a  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x180016851  lea     rax, ?WinPlatformGetRandom@@YAJPEAEI@Z; WinPlatformGetRandom(uchar *,uint)
0x180016858  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x18001685f  lea     rax, ?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z; WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)
0x180016866  mov     cs:?g_fpSha1Hash@@3P6AJPEAEI0I0I@ZEA, rax; long (*g_fpSha1Hash)(uchar *,uint,uchar *,uint,uchar *,uint)
0x18001686d  lea     rax, ?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x180016874  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18001687b  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180016882  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180016889  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180016890  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180016897  mov     [rsp+560h+var_51F], r15b
0x18001689c  lea     r8, [rsp+560h+var_51F]
0x1800168a1  call    ?CheckUpdateEkCertPresent@TrustedPlatformModule@@QEAAJW4TpmAlgID@@AEA_N@Z; TrustedPlatformModule::CheckUpdateEkCertPresent(TpmAlgID,bool &)
0x1800168a6  test    eax, eax
0x1800168a8  js      short loc_1800168B3
0x1800168aa  cmp     [rsp+560h+var_51F], r15b
0x1800168af  cmovnz  edi, r14d
0x1800168b3  lea     rcx, [rsp+560h+hObject]
0x1800168b8  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800168bd  nop
0x1800168be  jmp     loc_18001695E
0x1800168c3  mov     [rsp+560h+hObject], r15
0x1800168c8  mov     [rsp+560h+phProvider], r15
0x1800168cd  xor     r8d, r8d; dwFlags
0x1800168d0  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800168d7  lea     rcx, [rsp+560h+phProvider]; phProvider
0x1800168dc  call    cs:__imp_NCryptOpenStorageProvider
0x1800168e2  mov     r14d, 1
0x1800168e8  test    eax, eax
0x1800168ea  js      short loc_18001692E
0x1800168ec  mov     rbx, [rsp+560h+hObject]
0x1800168f1  test    rbx, rbx
0x1800168f4  jz      short loc_180016913
0x1800168f6  lea     rcx, [rsp+560h+var_4F0]; this
0x1800168fb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016900  mov     rcx, rbx; hObject
0x180016903  call    cs:__imp_NCryptFreeObject
0x180016909  lea     rcx, [rsp+560h+var_4F0]; this
0x18001690e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016913  mov     [rsp+560h+hObject], r15
0x180016918  lea     rdx, [rsp+560h+hObject]
0x18001691d  mov     rcx, [rsp+560h+phProvider]
0x180016922  call    cs:__imp_?TpmCertGetWindowsAik@@YAJ_KPEA_K@Z; TpmCertGetWindowsAik(unsigned __int64,unsigned __int64 *)
0x180016928  test    eax, eax
0x18001692a  cmovns  edi, r14d
0x18001692e  mov     [rsp+560h+var_518], r15d
0x180016933  lea     rdx, [rsp+560h+var_518]
0x180016938  mov     ecx, 19h
0x18001693d  call    ?GetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEAK@Z; HWSecurityRegistryManager::GetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong &)
0x180016942  test    eax, eax
0x180016944  js      short loc_180016953
0x180016946  movzx   edi, dil
0x18001694a  cmp     [rsp+560h+var_518], r15d
0x18001694f  cmovnz  edi, r14d
0x180016953  lea     rcx, [rsp+560h+hObject]
0x180016958  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001695d  nop
0x18001695e  lea     rcx, [rsp+560h+phProvider]
0x180016963  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016968  movzx   r12d, r15b
0x18001696c  mov     [rsp+560h+var_518], r15d
0x180016971  mov     [rbp+460h+var_4E0], r15d
0x180016975  mov     r13d, r15d
0x180016978  mov     sil, r15b
0x18001697b  mov     dword ptr [rsp+560h+hObject], esi
0x18001697f  mov     bl, r15b
0x180016982  mov     dword ptr [rsp+560h+phProvider], ebx
0x180016986  mov     [rsp+560h+var_51B], r15b
0x18001698b  mov     [rsp+560h+var_51F], r15b
0x180016990  mov     [rsp+560h+var_4F0], r15
0x180016995  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TpmMissingLogsMaa@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TpmMissingLogsMaa@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TpmMissingLogsMaa> `wil::Feature<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::GetImpl(void)'::`2'::impl
0x18001699c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TpmMissingLogsMaa@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TpmMissingLogsMaa>::__private_IsEnabled(void)
0x1800169a1  test    al, al
0x1800169a3  jz      short loc_1800169E7
0x1800169a5  mov     [rsp+560h+var_520], r15b
0x1800169aa  lea     rcx, [rsp+560h+var_520]; bool *
0x1800169af  call    ?IsBootWbclLogPresent@@YAJAEA_N@Z; IsBootWbclLogPresent(bool &)
0x1800169b4  test    eax, eax
0x1800169b6  js      short loc_1800169C8
0x1800169b8  movzx   ebx, bl
0x1800169bb  cmp     [rsp+560h+var_520], r15b
0x1800169c0  cmovnz  ebx, r14d
0x1800169c4  mov     dword ptr [rsp+560h+phProvider], ebx
0x1800169c8  lea     rcx, [rsp+560h+var_520]; bool *
0x1800169cd  call    ?IsCurrentWbclLogPresent@@YAJAEA_N@Z; IsCurrentWbclLogPresent(bool &)
0x1800169d2  test    eax, eax
0x1800169d4  js      short loc_1800169E7
0x1800169d6  movzx   esi, sil
0x1800169da  cmp     [rsp+560h+var_520], r15b
0x1800169df  cmovnz  esi, r14d
0x1800169e3  mov     dword ptr [rsp+560h+hObject], esi
0x1800169e7  call    ?TpmTaskGetWbclInformationStarted@TpmTaskDebugProvider@@SAXXZ; TpmTaskDebugProvider::TpmTaskGetWbclInformationStarted(void)
0x1800169ec  call    cs:__imp__Xtime_get_ticks
0x1800169f2  mov     rbx, rax
0x1800169f5  call    ?ValidatePcrMatchesLog@@YAXXZ; ValidatePcrMatchesLog(void)
0x1800169fa  call    cs:__imp__Xtime_get_ticks
0x180016a00  mov     rcx, rax
0x180016a03  sub     rcx, rbx
0x180016a06  mov     rax, 346DC5D63886594Bh
0x180016a10  imul    rcx
0x180016a13  sar     rdx, 0Bh
0x180016a17  mov     rax, rdx
0x180016a1a  shr     rax, 3Fh
0x180016a1e  add     rdx, rax
0x180016a21  mov     [rsp+560h+var_4E8], rdx
0x180016a26  lea     rcx, [rsp+560h+var_4E8]
0x180016a2b  call    ??$TpmTaskGetWbclInformationEnded@_J@TpmTaskDebugProvider@@SAX$$QEA_J@Z; TpmTaskDebugProvider::TpmTaskGetWbclInformationEnded<__int64>(__int64 &&)
0x180016a30  call    ?GetWbclInstanceKey@@YAPEAUHKEY__@@XZ; GetWbclInstanceKey(void)
0x180016a35  mov     rbx, rax
0x180016a38  mov     qword ptr [rbp+460h+SystemInformation], rax
0x180016a3f  mov     [rsp+560h+pvData], r15d
0x180016a44  mov     [rsp+560h+var_4F8], 4
0x180016a4c  lea     rax, [rsp+560h+var_4F8]
0x180016a51  mov     [rsp+560h+pcbData], rax; pcbData
0x180016a56  lea     rax, [rsp+560h+pvData]
0x180016a5b  mov     qword ptr [rsp+560h+dwFlags], rax; pvData
0x180016a60  mov     [rsp+560h+pcbResult], r15; pdwType
0x180016a65  mov     esi, 10h
0x180016a6a  mov     r9d, esi; dwFlags
0x180016a6d  lea     r8, aPcrsmatched; "PcrsMatched"
0x180016a74  xor     edx, edx; lpSubKey
0x180016a76  mov     rcx, rbx; hkey
0x180016a79  call    cs:__imp_RegGetValueW
0x180016a7f  test    eax, eax
0x180016a81  jle     short loc_180016A8D
0x180016a83  movzx   eax, ax
0x180016a86  or      eax, 80070000h
0x180016a8b  test    eax, eax
0x180016a8d  js      short loc_180016A96
0x180016a8f  mov     [rsp+560h+var_520], r14b
0x180016a94  jmp     short loc_180016AE1
0x180016a96  mov     [rsp+560h+var_520], r15b
0x180016a9b  lea     rax, [rsp+560h+var_4F8]
0x180016aa0  mov     [rsp+560h+pcbData], rax; pcbData
0x180016aa5  lea     rax, [rsp+560h+pvData]
0x180016aaa  mov     qword ptr [rsp+560h+dwFlags], rax; pvData
0x180016aaf  mov     [rsp+560h+pcbResult], r15; pdwType
0x180016ab4  mov     r9d, esi; dwFlags
0x180016ab7  lea     r8, aMismatchedpcrs; "MismatchedPcrsMask"
0x180016abe  xor     edx, edx; lpSubKey
0x180016ac0  mov     rcx, rbx; hkey
0x180016ac3  call    cs:__imp_RegGetValueW
0x180016ac9  test    eax, eax
0x180016acb  jle     short loc_180016AD7
0x180016acd  movzx   eax, ax
0x180016ad0  or      eax, 80070000h
0x180016ad5  test    eax, eax
0x180016ad7  js      short loc_180016AE9
0x180016ad9  mov     eax, [rsp+560h+pvData]
0x180016add  mov     [rsp+560h+var_518], eax
0x180016ae1  mov     sil, r14b
0x180016ae4  jmp     loc_180016B8A
0x180016ae9  movzx   esi, r15b
0x180016aed  lea     rax, [rsp+560h+var_4F8]
0x180016af2  mov     [rsp+560h+pcbData], rax; pcbData
0x180016af7  lea     rax, [rsp+560h+pvData]
0x180016afc  mov     qword ptr [rsp+560h+dwFlags], rax; pvData
0x180016b01  mov     [rsp+560h+pcbResult], r15; pdwType
0x180016b06  mov     r9d, 10h; dwFlags
0x180016b0c  lea     r8, aReplaypcrerror; "ReplayPcrError"
0x180016b13  xor     edx, edx; lpSubKey
0x180016b15  mov     rcx, rbx; hkey
0x180016b18  call    cs:__imp_RegGetValueW
0x180016b1e  test    eax, eax
0x180016b20  jle     short loc_180016B2C
0x180016b22  movzx   eax, ax
0x180016b25  or      eax, 80070000h
0x180016b2a  test    eax, eax
0x180016b2c  js      short loc_180016B45
0x180016b2e  mov     r15d, [rsp+560h+pvData]
0x180016b33  mov     [rbp+460h+var_4E0], r15d
0x180016b37  cmp     r15d, 8000FFFFh
0x180016b3e  cmovnz  esi, r14d
0x180016b42  xor     r15d, r15d
0x180016b45  lea     rax, [rsp+560h+var_4F8]
0x180016b4a  mov     [rsp+560h+pcbData], rax; pcbData
0x180016b4f  lea     rax, [rsp+560h+pvData]
0x180016b54  mov     qword ptr [rsp+560h+dwFlags], rax; pvData
0x180016b59  mov     [rsp+560h+pcbResult], r15; pdwType
0x180016b5e  mov     r9d, 10h; dwFlags
0x180016b64  lea     r8, aPhysicalpcrrea_0; "PhysicalPcrReadError"
0x180016b6b  xor     edx, edx; lpSubKey
0x180016b6d  mov     rcx, rbx; hkey
0x180016b70  call    cs:__imp_RegGetValueW
0x180016b76  test    eax, eax
0x180016b78  jle     short loc_180016B84
0x180016b7a  movzx   eax, ax
0x180016b7d  or      eax, 80070000h
0x180016b82  test    eax, eax
0x180016b84  cmovns  r13d, [rsp+560h+pvData]
0x180016b8a  mov     [rsp+560h+var_514], r15d
0x180016b8f  lea     rdx, [rsp+560h+var_514]
0x180016b94  mov     ecx, 22h ; '"'
0x180016b99  call    ?GetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEAK@Z; HWSecurityRegistryManager::GetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong &)
0x180016b9e  test    eax, eax
0x180016ba0  js      short loc_180016BAC
0x180016ba2  cmp     [rsp+560h+var_514], r14d
0x180016ba7  setz    [rsp+560h+var_51B]
0x180016bac  lea     rdx, [rsp+560h+var_514]
0x180016bb1  mov     ecx, 20h ; ' '
0x180016bb6  call    ?GetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEAK@Z; HWSecurityRegistryManager::GetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong &)
0x180016bbb  test    eax, eax
0x180016bbd  js      short loc_180016BC9
0x180016bbf  cmp     [rsp+560h+var_514], r14d
0x180016bc4  setz    [rsp+560h+var_51F]
0x180016bc9  lea     rdx, [rsp+560h+var_514]
0x180016bce  mov     ecx, 23h ; '#'
0x180016bd3  call    ?GetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEAK@Z; HWSecurityRegistryManager::GetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong &)
0x180016bd8  lea     rdx, [rsp+560h+var_4F0]
0x180016bdd  call    ?GetQWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEA_K@Z; HWSecurityRegistryManager::GetQWordNoThrow(HWSecurityRegistryManager::RegValues,unsigned __int64 &)
0x180016be2  mov     [rsp+560h+var_514], r15d
0x180016be7  mov     dword ptr [rsp+560h+var_4E8], r15d
0x180016bec  lea     rdx, [rsp+560h+var_514]
0x180016bf1  mov     ecx, 1Bh
0x180016bf6  call    ?GetDWordNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEAK@Z; HWSecurityRegistryManager::GetDWordNoThrow(HWSecurityRegistryManager::RegValues,ulong &)
0x180016bfb  test    eax, eax
0x180016bfd  js      short loc_180016C22
0x180016bff  cmp     [rsp+560h+var_514], r15d
0x180016c04  jz      short loc_180016C22
  ... truncated ...
```
