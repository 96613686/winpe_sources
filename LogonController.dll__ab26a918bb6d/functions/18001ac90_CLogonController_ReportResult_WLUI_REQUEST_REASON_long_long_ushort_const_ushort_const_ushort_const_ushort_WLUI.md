# CLogonController::ReportResult(_WLUI_REQUEST_REASON,long,long,ushort const *,ushort const *,ushort const *,ushort * *,_WLUI_CREDPROV_RESPONSE *,int *)

- ea: `0x18001ac90`
- end: `0x18001c563`
- name: `?ReportResult@CLogonController@@UEAAJW4_WLUI_REQUEST_REASON@@JJPEBG11PEAPEAGPEAW4_WLUI_CREDPROV_RESPONSE@@PEAH@Z`
- size: `6355`
- prototype: `__int64 __fastcall(__int64, int, DWORD, UINT32, const WCHAR *, unsigned __int16 *, unsigned __int16 *, _QWORD *, _DWORD *, WCHAR *)`
- caller_count: `0`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000df10`
- `0x180010328`
- `0x180015920`
- `0x18001a568`
- `0x18001a648`
- `0x18001a780`
- `0x18001a83c`
- `0x18001aad0`
- `0x18001ac90`
- `0x18001c56c`
- `0x18001c6a4`
- `0x18001c730`
- `0x18001c7c0`
- `0x18001c860`
- `0x18001db70`
- `0x180031720`
- `0x1800328e0`
- `0x1800342ac`
- `0x18003b910`
- `0x18003db60`
- `0x18003fa40`
- `0x180041ed4`
- `0x180046f10`
- `0x180047680`
- `0x18004f3ec`
- `0x18005045c`
- `0x18005b3e4`
- `0x18005d488`
- `0x18005e794`
- `0x180061470`
- `0x180061ebc`
- `0x1800661c8`
- `0x18006a7b0`
- `0x18006c000`
- `0x180073500`
- `0x180073cb4`
- `0x18007bdf8`
- `0x18007c2e4`
- `0x18009b170`
- `0x18009b790`
- `0x18009b79c`
- `0x18009d010`

## import_xrefs

- `CredProvCommonCore!__imp_?WriteLastLoggedOnUserinfo@@YAXPEBG00@Z` at `0x18001b299`
- `CredProvCommonCore!__imp_?WriteLastLoggedOnUserinfo@@YAXPEBG00@Z` at `0x18001b299`
- `CredProvCommonCore!__imp_?FormatLastLoggedOn@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1PEAPEAG@Z` at `0x18001b280`
- `CredProvCommonCore!__imp_?FormatLastLoggedOn@@YAJW4_CREDENTIAL_PROVIDER_USAGE_SCENARIO@@PEBG1PEAPEAG@Z` at `0x18001b280`
- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x18001af06`
- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x18001af06`
- `KERNEL32!FreeLibrary` at `0x18001b0a3`
- `KERNEL32!FreeLibrary` at `0x18001b0a3`
- `KERNEL32!RaiseException` at `0x18001b221`
- `KERNEL32!RaiseException` at `0x18001b546`
- `KERNEL32!RaiseException` at `0x18001b5b6`
- `KERNEL32!RaiseException` at `0x18001b62e`
- `KERNEL32!RaiseException` at `0x18001b9dd`
- `KERNEL32!RaiseException` at `0x18001badf`
- `KERNEL32!RaiseException` at `0x18001baf3`
- `KERNEL32!RaiseException` at `0x18001bb07`
- `KERNEL32!RaiseException` at `0x18001bfb9`
- `KERNEL32!RaiseException` at `0x18001b221`
- `KERNEL32!RaiseException` at `0x18001b546`
- `KERNEL32!RaiseException` at `0x18001b5b6`
- `KERNEL32!RaiseException` at `0x18001b62e`
- `KERNEL32!RaiseException` at `0x18001b9dd`
- `KERNEL32!RaiseException` at `0x18001badf`
- `KERNEL32!RaiseException` at `0x18001baf3`
- `KERNEL32!RaiseException` at `0x18001bb07`
- `KERNEL32!RaiseException` at `0x18001bfb9`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001af68`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001af68`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001afe4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b23d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b764`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b9c5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001beef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c02e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c06a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c0e2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c0fa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c112`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c14c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001afe4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b23d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b764`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b9c5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001beef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c02e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c06a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c0e2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c0fa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c112`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c14c`
- `KERNEL32!AcquireSRWLockShared` at `0x18001af4d`
- `KERNEL32!AcquireSRWLockShared` at `0x18001af4d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001afaa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b01e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b0f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b6f4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001becb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c019`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c137`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001afaa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b01e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b0f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b6f4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001becb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c019`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bbbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bc39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c4cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c54a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bbbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bc39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c4cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c54a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b32a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bf62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b32a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bf62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bbee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b197`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ba85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b197`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ba85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ae2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ae2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ae95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ae95`
- `SHCORE!IsOS` at `0x18001c183`
- `SHCORE!IsOS` at `0x18001c183`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001b0be`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001b0cd`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001b24d`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001b0be`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001b0cd`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001b24d`
- `USER32!ShowCursor` at `0x18001b0d9`
- `USER32!ShowCursor` at `0x18001b0d9`

## pseudocode

```c
__int64 __fastcall CLogonController::ReportResult(
        __int64 a1,
        int a2,
        DWORD a3,
        UINT32 a4,
        const WCHAR *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        _QWORD *a8,
        _DWORD *a9,
        WCHAR *a10)
{
  __int64 v10; // r12
  unsigned __int16 *v12; // r13
  unsigned __int64 v13; // r14
  _DWORD *v14; // rdi
  WCHAR *v15; // rbx
  __int64 v16; // r15
  __int128 v17; // xmm6
  LSTATUS Value; // eax
  bool v19; // sf
  int v20; // ebx
  char v21; // r14
  int v22; // eax
  __int64 v23; // r15
  int v24; // r14d
  WCHAR *v25; // rbx
  CProcessStateManager *v26; // r15
  __int64 v27; // rcx
  int v28; // eax
  bool v29; // r12
  PCWSTR v30; // rdx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v31; // r12
  const WCHAR *v32; // rcx
  unsigned __int64 v33; // rdx
  CProcessStateManager *v34; // rcx
  CProcessStateManager *v35; // rcx
  HRESULT v36; // eax
  int v37; // eax
  __int64 v39; // rcx
  CLogonController *v40; // rcx
  int v41; // eax
  unsigned int v42; // ebx
  const WCHAR *v43; // rcx
  unsigned __int64 v44; // rdx
  HRESULT v45; // eax
  unsigned __int16 *v46; // rcx
  unsigned __int64 v47; // rdx
  HRESULT v48; // eax
  HRESULT v49; // eax
  int v50; // eax
  PVOID Reserved1; // rbx
  unsigned int v52; // r14d
  WCHAR *v53; // r15
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rdi
  int v57; // eax
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rcx
  PVOID v61; // rcx
  __int64 v62; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v63; // rcx
  __int64 v64; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v65; // rcx
  __int64 v66; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v67; // rcx
  unsigned int v68; // r9d
  __int64 v69; // rdi
  int *v70; // r12
  _QWORD *v71; // r13
  int v72; // eax
  int v73; // eax
  PCWSTR StringRawBuffer; // r14
  size_t v75; // rbx
  void *v76; // rax
  void *v77; // rdi
  __int64 v78; // rcx
  PVOID v79; // rcx
  __int64 v80; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v81; // rcx
  PVOID v82; // rcx
  __int64 v83; // rcx
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v84; // rcx
  CLogonController *v85; // rdi
  int v86; // eax
  __int64 v87; // rcx
  __int64 v88; // rcx
  HRESULT v89; // eax
  unsigned int v90; // eax
  BOOL v91; // eax
  int v92; // eax
  __int64 v93; // rdx
  __int64 v94; // rax
  int IsSIDSystemManagedAccount; // eax
  char v96; // di
  __int64 v97; // rbx
  const WCHAR *v98; // rax
  unsigned int v99; // eax
  __int64 v100; // r10
  int v101; // eax
  unsigned int v102; // ebx
  char v103; // di
  int v104; // edx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResulte; // [rsp+20h] [rbp-E0h]
  int phkResultf; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResultd; // [rsp+20h] [rbp-E0h]
  bool v112; // [rsp+50h] [rbp-B0h] BYREF
  char v113; // [rsp+51h] [rbp-AFh]
  _BYTE v114[6]; // [rsp+52h] [rbp-AEh] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v116; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData[2]; // [rsp+68h] [rbp-98h] BYREF
  char v118; // [rsp+70h] [rbp-90h]
  UINT32 length; // [rsp+74h] [rbp-8Ch] BYREF
  struct Windows::Internal::UI::Logon::Controller::ILogonUX *v120; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v122; // [rsp+88h] [rbp-78h] BYREF
  int v123; // [rsp+90h] [rbp-70h]
  PCWSTR v124; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey[2]; // [rsp+A0h] [rbp-60h] BYREF
  int *v126; // [rsp+B0h] [rbp-50h]
  PCWSTR sourceString; // [rsp+B8h] [rbp-48h]
  WCHAR *v128; // [rsp+C0h] [rbp-40h]
  _QWORD *v129; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v130; // [rsp+D0h] [rbp-30h]
  _QWORD v131[3]; // [rsp+D8h] [rbp-28h] BYREF
  char v132; // [rsp+F0h] [rbp-10h]
  HSTRING_HEADER Data; // [rsp+100h] [rbp+0h] BYREF
  HSTRING string; // [rsp+118h] [rbp+18h] BYREF
  void **v135; // [rsp+120h] [rbp+20h] BYREF
  int v136; // [rsp+128h] [rbp+28h] BYREF
  char v137; // [rsp+12Ch] [rbp+2Ch]
  int v138; // [rsp+150h] [rbp+50h] BYREF
  const char *v139; // [rsp+158h] [rbp+58h]
  __int64 v140; // [rsp+160h] [rbp+60h]
  char v141; // [rsp+168h] [rbp+68h]
  int v142; // [rsp+170h] [rbp+70h]
  __int128 v143; // [rsp+178h] [rbp+78h]
  __int128 v144; // [rsp+188h] [rbp+88h]
  __int128 v145; // [rsp+198h] [rbp+98h]
  __int128 v146; // [rsp+1A8h] [rbp+A8h]
  __int128 v147; // [rsp+1B8h] [rbp+B8h]
  __int128 v148; // [rsp+1C8h] [rbp+C8h]
  __int128 v149; // [rsp+1D8h] [rbp+D8h]
  __int128 v150; // [rsp+1E8h] [rbp+E8h]
  __int128 v151; // [rsp+1F8h] [rbp+F8h]
  __int64 v152; // [rsp+208h] [rbp+108h]
  __int128 v153; // [rsp+210h] [rbp+110h]
  int v154; // [rsp+220h] [rbp+120h]
  __int64 v155; // [rsp+228h] [rbp+128h]
  int *v156; // [rsp+230h] [rbp+130h]
  _QWORD v157[4]; // [rsp+238h] [rbp+138h] BYREF
  int v158; // [rsp+258h] [rbp+158h]
  int *v159; // [rsp+260h] [rbp+160h]
  char v160; // [rsp+268h] [rbp+168h]
  HSTRING_HEADER v161; // [rsp+270h] [rbp+170h] BYREF
  HSTRING v162; // [rsp+288h] [rbp+188h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+290h] [rbp+190h] BYREF
  HSTRING v164; // [rsp+2A8h] [rbp+1A8h] BYREF
  HSTRING_HEADER v165; // [rsp+2B0h] [rbp+1B0h] BYREF
  HSTRING v166; // [rsp+2C8h] [rbp+1C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  length = a4;
  v123 = a3;
  LODWORD(v10) = a2;
  LODWORD(v122) = a2;
  v130 = a6;
  pcbData[0] = a3;
  LODWORD(v120) = a4;
  v124 = a5;
  v12 = a7;
  sourceString = a7;
  v131[0] = a7;
  v13 = (unsigned __int64)a8;
  v129 = a8;
  v14 = a9;
  v126 = a9;
  v15 = a10;
  v128 = a10;
  v16 = 0;
  v136 = 0;
  v137 = 0;
  v141 = 0;
  v138 = 0;
  v139 = "CLogonController_ReportResult_Activity";
  v140 = 0;
  v142 = 0;
  v153 = 0;
  v143 = 0;
  v144 = 0;
  v145 = 0;
  v146 = 0;
  v147 = 0;
  v148 = 0;
  v149 = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v154 = 1;
  v155 = 0;
  v156 = &v136;
  v157[0] = 0;
  v157[1] = 0;
  v157[2] = &v135;
  v157[3] = 0;
  v158 = 0;
  v159 = &v138;
  v160 = 0;
  v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
  v17 = 0;
  *(_OWORD *)&Data.Reserved.Reserved1 = 0;
  hKey[0] = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TelemetryCorrelation",
         0,
         0x20019u,
         hKey) < 0 )
    goto LABEL_64;
  Type[0] = 3;
  cbData[0] = 16;
  Value = RegQueryValueExW(hKey[0], L"FirstRunCorrelationID", 0, Type, (LPBYTE)&Data, cbData);
  v19 = Value < 0;
  if ( Value > 0 )
    v19 = 1;
  if ( v19 )
    *(_OWORD *)&Data.Reserved.Reserved1 = 0;
  else
LABEL_64:
    v17 = *(_OWORD *)&Data.Reserved.Reserved1;
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  *(_OWORD *)hKey = v17;
  if ( memcmp_0(hKey, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    goto LABEL_55;
  while ( 1 )
  {
    LogonControllerTelemetry::CLogonController_ReportResult_Activity::StartActivity((LogonControllerTelemetry::CLogonController_ReportResult_Activity *)&v135);
    *(_QWORD *)v13 = v16;
    *v14 = v16;
    *(_DWORD *)v15 = v16;
    hKey[0] = (HKEY)(a1 - 32);
    v112 = 0;
    LODWORD(v15) = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)(*(_QWORD *)(a1 - 32 + 144) + 16LL) + 224LL))(
                     *(_QWORD *)(a1 - 32 + 144) + 16LL,
                     &v112);
    if ( (int)v15 < 0 )
    {
LABEL_170:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE18,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v15,
        (int)phkResult);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49C,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v15,
        phkResultf);
      v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v135);
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v135);
      return (unsigned int)v15;
    }
    if ( !IsFirstBoot() && !IsFirstLogonAfterOOBE() && !v112 && !CProcessStateManager::IsUserOOBESignInOrSignOut(v35)
      || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8LL) + 32LL))(*(_QWORD *)(a1 + 144) + 8LL)
      || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8LL) + 56LL))(*(_QWORD *)(a1 + 144) + 8LL)
      || (v91 = IsOS(0x1Du), v113 = 1, v91) )
    {
      v113 = 0;
    }
    v20 = 0;
    if ( v12 )
      v20 = IsUserSidAssignedAccessSingleApp(v12);
    AcquireSRWLockShared((PSRWLOCK)(a1 + 256));
    v21 = *(_BYTE *)(a1 + 272);
    v118 = v21;
    if ( a1 != -256 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 256));
    if ( v123 < 0 )
    {
      LogonControllerTelemetry::SignInFailure<long &,long &>(pcbData, &v120);
      if ( v113 || v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8LL) + 24LL))(*(_QWORD *)(a1 + 144) + 8LL);
        v113 = 0;
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 256));
        *(_BYTE *)(a1 + 272) = 0;
        if ( a1 != -256 )
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 256));
        v118 = 0;
      }
    }
    else if ( v21 || v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8LL) + 24LL))(*(_QWORD *)(a1 + 144) + 8LL);
    }
    v116 = 0;
    v14 = (_DWORD *)(a1 + 184);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 184));
    Data.Reserved.Reserved1 = (PVOID)(a1 + 184);
    v22 = *(_DWORD *)(a1 + 192);
    if ( v22 && v22 != 3 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD7A,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)0x8007009DLL,
        (int)phkResult);
      if ( a1 != -184 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 184));
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C6,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)0x8007009DLL,
        phkResultc);
      v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v135);
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v135);
      return 2147942557LL;
    }
    *(_DWORD *)(a1 + 192) = 1;
    v116 = ++*(_DWORD *)(a1 + 208);
    if ( a1 != -184 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 184));
    v131[1] = a1 - 32;
    v131[2] = &v116;
    v132 = 1;
    v23 = *(_QWORD *)(a1 + 112);
    Type[0] = 4;
    if ( (_DWORD)v10 == 1 )
    {
      v24 = 1;
    }
    else
    {
      v24 = 4;
      if ( (_DWORD)v10 )
      {
        if ( (_DWORD)v10 == 2 )
        {
          v24 = 2;
        }
        else if ( (_DWORD)v10 == 3 )
        {
          v24 = 3;
        }
      }
      else
      {
        v24 = 0;
      }
    }
    AcquireSRWLockExclusive((PSRWLOCK)(v23 + 600));
    *(_DWORD *)(v23 + 608) = v24;
    if ( v23 != -600 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v23 + 600));
    v25 = (WCHAR *)&::sourceString;
    if ( v124 )
      v25 = (WCHAR *)v124;
    v13 = -1;
    if ( v123 >= 0 && (unsigned int)v10 <= 1 )
    {
      v26 = *(CProcessStateManager **)(a1 + 112);
      if ( (_DWORD)v10 )
      {
        if ( !GetSystemMetrics(4096) && v25 && *v25 )
        {
          Data.Reserved.Reserved1 = 0;
          *(_QWORD *)&Data.Reserved.Reserved2[8] = -1;
          *(_QWORD *)&Data.Reserved.Reserved2[16] = -1;
          if ( (int)FormatLastLoggedOn(CPUS_LOGON, v25, 0, (unsigned __int16 **)&Data) < 0 )
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              (__int64)&Data,
              v25,
              0xFFFFFFFFFFFFFFFFuLL);
          WriteLastLoggedOnUserinfo((const unsigned __int16 *)Data.Reserved.Reserved1, v130, v12);
          if ( Data.Reserved.Reserved1 )
            CoTaskMemFree(Data.Reserved.Reserved1);
        }
        CProcessStateManager::_WriteColorKeysIfNecessary(v26, v12);
        CProcessStateManager::_ResetUserSwitchState(v34);
      }
      else
      {
        CProcessStateManager::RecordSuccessfulLogon(*(CProcessStateManager **)(a1 + 112), v25, v130, v12);
      }
      memset(&Data, 0, sizeof(Data));
      Windows::Shell::CImmersiveCursor::_EnableMouseInputForCursorSuppression(
        (Windows::Shell::CImmersiveCursor *)&Data,
        0);
      if ( *(_QWORD *)&Data.Reserved.Reserved2[16] )
        FreeLibrary(*(HMODULE *)&Data.Reserved.Reserved2[16]);
      if ( byte_1800D3540 )
      {
        byte_1800D3540 = 0;
        if ( GetSystemMetrics(19) )
        {
          if ( !GetSystemMetrics(4096) )
            ShowCursor(0);
        }
      }
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 312));
      Data.Reserved.Reserved1 = (PVOID)(a1 + 312);
      v27 = *(_QWORD *)(a1 + 368);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 72LL))(v27);
      if ( a1 != -312 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 312));
    }
    v112 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL) + 224LL))(
            *(_QWORD *)(a1 + 112) + 16LL,
            &v112);
    LODWORD(v15) = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7E,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v28,
        (int)phkResult);
      goto LABEL_81;
    }
    v29 = 0;
    if ( v112 )
      goto LABEL_46;
    cbData[0] = 0;
    pcbData[0] = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
      L"DefaultAccountAction",
      0x10u,
      0,
      cbData,
      pcbData);
    if ( cbData[0] - 1 <= 1 )
      goto LABEL_46;
    *(_QWORD *)pcbData = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 312));
    if ( *(_BYTE *)(a1 + 320) )
    {
      LODWORD(v15) = -2147483622;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7C,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)0x8000001ALL,
        (int)phkResult);
      if ( a1 != -312 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 312));
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE83,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)0x8000001ALL,
        phkResultd);
      v39 = *(_QWORD *)pcbData;
      if ( *(_QWORD *)pcbData )
      {
        *(_QWORD *)pcbData = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      goto LABEL_81;
    }
    if ( *(_BYTE *)(a1 + 321) )
    {
      if ( !*(_QWORD *)(a1 + 352) )
      {
        string = 0;
        v89 = WindowsCreateStringReference(
                L"Windows.Internal.SystemManagedAccount.Logon.SystemManagedAccountCredential",
                0x4Au,
                &Data,
                &string);
        if ( v89 < 0 )
        {
          RaiseException(v89, 1u, 0, 0);
LABEL_222:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 8LL))(v88);
          *(_QWORD *)pcbData = *(_QWORD *)(a1 + 352);
          goto LABEL_208;
        }
        v90 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential>>(
                string,
                a1 + 352);
        if ( (int)(v90 + 0x80000000) >= 0 && v90 != -2147221164 )
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0xA85,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)v90,
            (int)phkResult);
      }
      v88 = *(_QWORD *)(a1 + 352);
      if ( !v88 )
      {
        *(_BYTE *)(a1 + 321) = 0;
        goto LABEL_208;
      }
      goto LABEL_222;
    }
LABEL_208:
    if ( a1 != -312 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 312));
    if ( !*(_QWORD *)pcbData )
      goto LABEL_211;
    Data.Reserved.Reserved1 = 0;
    v92 = Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential>::As<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>(
            pcbData,
            &Data);
    LODWORD(v15) = v92;
    if ( v92 < 0 )
    {
      v93 = 3720;
      goto LABEL_262;
    }
    cbData[0] = 0;
    v92 = (*(__int64 (__fastcall **)(PVOID, DWORD *))(*(_QWORD *)Data.Reserved.Reserved1 + 48LL))(
            Data.Reserved.Reserved1,
            cbData);
    LODWORD(v15) = v92;
    if ( v92 < 0 )
    {
      v93 = 3723;
      goto LABEL_262;
    }
    if ( cbData[0] )
    {
      v114[0] = 0;
      v92 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)pcbData + 48LL))(*(_QWORD *)pcbData, v114);
      LODWORD(v15) = v92;
      if ( v92 < 0 )
      {
        v93 = 3728;
LABEL_262:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v93,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v92,
          (int)phkResult);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&Data);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(pcbData);
LABEL_81:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E3,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v15,
          phkResulta);
LABEL_82:
        v40 = (CLogonController *)hKey[0];
        goto LABEL_83;
      }
      v29 = v114[0] != 0;
    }
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&Data);
LABEL_211:
    v87 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    }
LABEL_46:
    LOBYTE(v12) = 0;
    v112 = 0;
    v30 = sourceString;
    if ( v29 && sourceString )
    {
      v94 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v161, v131);
      IsSIDSystemManagedAccount = CLogonController::_IsSIDSystemManagedAccount(
                                    (CLogonController *)(a1 - 32),
                                    *(HSTRING *)(v94 + 24),
                                    &v112);
      v42 = IsSIDSystemManagedAccount;
      if ( IsSIDSystemManagedAccount < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E9,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)IsSIDSystemManagedAccount,
          (int)phkResult);
LABEL_157:
        CLogonController::_TransitionToNone((CLogonController *)(a1 - 32), v116);
        v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v135);
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v135);
        return v42;
      }
      v12 = (unsigned __int16 *)v112;
      v30 = sourceString;
    }
    LODWORD(v31) = v122;
    if ( (unsigned int)v122 > 1 )
      goto LABEL_86;
    cbData[0] = 0;
    v15 = *(WCHAR **)(a1 + 112);
    v10 = *((_QWORD *)v15 + 3);
    v32 = &::sourceString;
    if ( v30 )
      v32 = v30;
    string = 0;
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v16 = 0xFFFFFFFFLL;
    if ( v33 <= 0xFFFFFFFF && (int)v33 + 1 >= (unsigned int)v33 )
      break;
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_55:
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v135,
      hKey);
  }
  v36 = WindowsCreateStringReference(v32, v33, &Data, &string);
  if ( v36 < 0 )
  {
    RaiseException(v36, 1u, 0, 0);
LABEL_159:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x516,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v15,
      (int)phkResult);
    v66 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v67 + 16LL))(v67);
    }
    goto LABEL_82;
  }
  v37 = (*(__int64 (__fastcall **)(WCHAR *, HSTRING, DWORD *))(v10 + 48))(v15 + 12, string, cbData);
  LODWORD(v15) = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F0,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v37,
      (int)phkResult);
    CLogonController::_TransitionToNone((CLogonController *)hKey[0], v116);
    v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
    if ( v157[0] )
    {
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        &v135,
        &v124);
      if ( v157[0] && *(_DWORD *)v157[0] == 1 )
      {
        v96 = 1;
      }
      else
      {
        v96 = 0;
        wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(v157);
      }
      if ( v124 )
        ReleaseSRWLockExclusive((PSRWLOCK)v124);
      if ( !v96 )
        goto LABEL_78;
    }
    if ( *v156 != 1 )
      goto LABEL_78;
    goto LABEL_77;
  }
  LODWORD(v31) = v122;
  v114[0] = (_DWORD)v122 == 1;
  pcbData[0] = cbData[0];
  LogonControllerTelemetry::LogonAndUnlockSubmit<unsigned long,bool,bool &,unsigned short const * &>(
    pcbData,
    v114,
    &v112,
    v131);
LABEL_86:
  while ( 2 )
  {
    if ( v123 >= 0 )
    {
      cbData[0] = 0;
      pcbData[0] = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
        L"DefaultAccountAction",
        0x10u,
        0,
        cbData,
        pcbData);
      if ( cbData[0] == 1 )
      {
        cbData[0] = 0;
        SHRegGetBOOLWithREGSAM(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ExperienceManagerData",
          L"LaunchCflScenario",
          v68,
          (int *)cbData);
        if ( !cbData[0] )
          FireOOBEMonitorEvent();
      }
    }
    if ( v113 || v118 )
    {
      *v129 = 0;
      v70 = v126;
      *v126 = 0;
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 256));
      *(_BYTE *)(a1 + 272) = 0;
      if ( a1 != -256 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 256));
      goto LABEL_241;
    }
    if ( (_BYTE)v12 )
    {
      *v129 = 0;
      v70 = v126;
      *v126 = 3;
      LogonControllerTelemetry::SystemManagedAccountLogin();
LABEL_241:
      v85 = (CLogonController *)(a1 - 32);
      goto LABEL_242;
    }
    if ( *(_BYTE *)(a1 + 273) )
    {
      v85 = (CLogonController *)(a1 - 32);
      v97 = *(_QWORD *)(a1 - 32 + 184);
      v98 = &::sourceString;
      if ( sourceString )
        v98 = sourceString;
      v124 = v98;
      Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v161, &v124);
      v99 = WluiRequestReasonToLogonReason((unsigned int)v31);
      v70 = v126;
      phkResult = *(PHKEY *)(v100 + 24);
      v101 = SilentTSAutologonManager::ReportTSAutoLogonResult(v97, v99, (unsigned int)v123, length);
      v102 = v101;
      if ( v101 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50D,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v101,
          (int)phkResult);
        CLogonController::_TransitionToNone((CLogonController *)(a1 - 32), v116);
        v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v135);
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v135);
        return v102;
      }
      *(_BYTE *)(a1 + 273) = 0;
LABEL_242:
      v53 = v128;
      goto LABEL_197;
    }
    v120 = 0;
    v41 = CLogonController::_EnsureLogonUX((CLogonController *)(a1 - 32), &v120);
    v42 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x513,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v41,
        (int)phkResult);
      v65 = v120;
      if ( v120 )
      {
        v120 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v65 + 16LL))(v65);
      }
      goto LABEL_157;
    }
    *(_QWORD *)pcbData = 0;
    v31 = v120;
    v12 = *(unsigned __int16 **)v120;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(pcbData);
    v15 = (WCHAR *)&::sourceString;
    v43 = &::sourceString;
    if ( sourceString )
      v43 = sourceString;
    v164 = 0;
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    if ( v44 > 0xFFFFFFFF || (int)v44 + 1 < (unsigned int)v44 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      continue;
    }
    break;
  }
  v45 = WindowsCreateStringReference(v43, v44, &hstringHeader, &v164);
  if ( v45 < 0 )
  {
    RaiseException(v45, 1u, 0, 0);
LABEL_168:
    RaiseException(v48, 1u, 0, 0);
LABEL_169:
    RaiseException(v49, 1u, 0, 0);
    goto LABEL_170;
  }
  v46 = v130;
  if ( !v130 )
    v46 = (unsigned __int16 *)&::sourceString;
  v166 = 0;
  v47 = -1;
  do
    ++v47;
  while ( v46[v47] );
  if ( v47 > 0xFFFFFFFF || (int)v47 + 1 < (unsigned int)v47 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v48 = WindowsCreateStringReference(v46, v47, &v165, &v166);
  if ( v48 < 0 )
    goto LABEL_168;
  if ( v124 )
    v15 = (WCHAR *)v124;
  v124 = v15;
  v162 = 0;
  do
    ++v13;
  while ( v15[v13] );
  if ( v13 > 0xFFFFFFFF || (int)v13 + 1 < (unsigned int)v13 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  LODWORD(v15) = (_DWORD)v166;
  v49 = WindowsCreateStringReference(v124, v13, &v161, &v162);
  if ( v49 < 0 )
    goto LABEL_169;
  if ( (_DWORD)v122 == 1 )
  {
    Type[0] = 1;
  }
  else if ( (_DWORD)v122 )
  {
    if ( (_DWORD)v122 == 2 )
    {
      Type[0] = 2;
    }
    else if ( (_DWORD)v122 == 3 )
    {
      Type[0] = 3;
    }
  }
  else
  {
    Type[0] = 0;
  }
  LODWORD(phkResult) = (_DWORD)v162;
  LODWORD(v15) = (*((__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *, _QWORD, _QWORD, _QWORD))v12
                  + 10))(
                   v31,
                   Type[0],
                   (unsigned int)v123,
                   length);
  if ( (int)v15 < 0 )
    goto LABEL_159;
  Data.Reserved.Reserved1 = 0;
  v50 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, HSTRING_HEADER *))pcbData)(
          *(_QWORD *)pcbData,
          &GUID_00000036_0000_0000_c000_000000000046,
          &Data);
  LODWORD(v15) = v50;
  if ( v50 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x519,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v50,
      (int)phkResult);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Data);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(pcbData);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
    goto LABEL_82;
  }
  Reserved1 = Data.Reserved.Reserved1;
  v52 = v116;
  v53 = v128;
  *(_DWORD *)v128 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 184));
  if ( *(_DWORD *)(a1 + 192) == 1 && v52 == *(_DWORD *)(a1 + 208) )
  {
    *(_DWORD *)(a1 + 192) = 2;
    if ( *(PVOID *)(a1 + 200) != Reserved1 )
    {
      if ( Reserved1 )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Reserved1 + 8LL))(Reserved1);
      v55 = *(_QWORD *)(a1 + 200);
      *(_QWORD *)(a1 + 200) = Reserved1;
      if ( v55 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
  }
  else
  {
    *(_DWORD *)v53 = 1;
  }
  if ( a1 != -184 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 184));
  if ( *(_DWORD *)v53 )
  {
    v70 = v126;
    goto LABEL_190;
  }
  v122 = 0;
  v56 = *(_QWORD *)pcbData;
  *(_DWORD *)v53 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v122);
  LODWORD(v15) = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Logon::Controller::ReportCredentialsData *>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::Logon::Controller::ReportCredentialsData *>>(v56);
  if ( (int)v15 >= 0 )
    LODWORD(v15) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 64LL))(v56, &v122);
  if ( (_DWORD)v15 == -2147023673 )
  {
    *(_DWORD *)v53 = 1;
    goto LABEL_172;
  }
  if ( (int)v15 < 0 )
    goto LABEL_139;
  *(_QWORD *)cbData = 0;
  v57 = (**(__int64 (__fastcall ***)(__int64, GUID *, DWORD *))v56)(
          v56,
          &GUID_00000036_0000_0000_c000_000000000046,
          cbData);
  LODWORD(v15) = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE1,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v57,
      (int)phkResult);
    v64 = *(_QWORD *)cbData;
    if ( *(_QWORD *)cbData )
    {
      *(_QWORD *)cbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
LABEL_139:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51F,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v15,
      (int)phkResult);
    v60 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = Data.Reserved.Reserved1;
    if ( Data.Reserved.Reserved1 )
    {
      Data.Reserved.Reserved1 = 0;
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v63 + 16LL))(v63);
    }
    goto LABEL_82;
  }
  length = 0;
  v58 = (*(__int64 (__fastcall **)(_QWORD, UINT32 *))(**(_QWORD **)cbData + 56LL))(*(_QWORD *)cbData, &length);
  LODWORD(v15) = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB4,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v58,
      (int)phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE2,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v15,
      phkResulte);
    v59 = *(_QWORD *)cbData;
    if ( *(_QWORD *)cbData )
    {
      *(_QWORD *)cbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    goto LABEL_139;
  }
  *(_DWORD *)v53 = length != 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(cbData);
LABEL_172:
  v69 = v122;
  v70 = v126;
  if ( !v122 )
    goto LABEL_188;
  v71 = v129;
  *v129 = 0;
  *v70 = 0;
  cbData[0] = 0;
  v72 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v69 + 56LL))(v69, cbData);
  LODWORD(v15) = v72;
  if ( v72 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD58,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v72,
      (int)phkResult);
    goto LABEL_177;
  }
  *(_QWORD *)Type = 0;
  v15 = *(WCHAR **)(*(_QWORD *)v69 + 48LL);
  WindowsDeleteString(0);
  *(_QWORD *)Type = 0;
  v73 = ((__int64 (__fastcall *)(__int64, DWORD *))v15)(v69, Type);
  LODWORD(v15) = v73;
  if ( v73 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5B,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v73,
      (int)phkResult);
    WindowsDeleteString(*(HSTRING *)Type);
LABEL_177:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x522,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v15,
      phkResultb);
    v78 = v122;
    if ( v122 )
    {
      v122 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v79 = Data.Reserved.Reserved1;
    if ( Data.Reserved.Reserved1 )
    {
      Data.Reserved.Reserved1 = 0;
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v80 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    }
    v81 = v120;
    if ( v120 )
    {
      v120 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v81 + 16LL))(v81);
    }
    CLogonController::_TransitionToNone((CLogonController *)hKey[0], v116);
    v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
    if ( v157[0] )
    {
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        &v135,
        &v124);
      if ( v157[0] && *(_DWORD *)v157[0] == 1 )
      {
        v103 = 1;
      }
      else
      {
        v103 = 0;
        wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(v157);
      }
      if ( v124 )
        ReleaseSRWLockExclusive((PSRWLOCK)v124);
      if ( !v103 )
        goto LABEL_78;
    }
    if ( *v156 != 1 )
      goto LABEL_78;
LABEL_77:
    wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v135);
    goto LABEL_78;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)Type, &length);
  v75 = 2LL * (length + 1);
  v76 = MIDL_user_allocate(v75);
  v77 = v76;
  if ( !v76 )
  {
    LODWORD(v15) = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD67,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)0x8007000ELL,
      (int)phkResult);
    WindowsDeleteString(*(HSTRING *)Type);
    goto LABEL_177;
  }
  memcpy_0(v76, StringRawBuffer, v75);
  *v71 = v77;
  v104 = 0;
  if ( cbData[0] == 1 )
  {
    v104 = 1;
  }
  else if ( cbData[0] == 2 )
  {
    v104 = 2;
  }
  *v70 = v104;
  WindowsDeleteString(*(HSTRING *)Type);
  v69 = v122;
LABEL_188:
  if ( v69 )
  {
    v122 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  }
LABEL_190:
  v82 = Data.Reserved.Reserved1;
  if ( Data.Reserved.Reserved1 )
  {
    Data.Reserved.Reserved1 = 0;
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v82 + 16LL))(v82);
  }
  v83 = *(_QWORD *)pcbData;
  if ( *(_QWORD *)pcbData )
  {
    *(_QWORD *)pcbData = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  }
  v84 = v120;
  if ( v120 )
  {
    v120 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::ILogonUX *))(*(_QWORD *)v84 + 16LL))(v84);
  }
  v85 = (CLogonController *)(a1 - 32);
LABEL_197:
  if ( *v70
    || *(_DWORD *)v53
    || (LOBYTE(v54) = 1,
        v86 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL) + 144LL))(
                *(_QWORD *)(a1 + 112) + 16LL,
                v54),
        LODWORD(v15) = v86,
        v86 >= 0) )
  {
    CLogonController::_TransitionToNone(v85, v116);
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v135, 0);
    v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v135);
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v135);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52A,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v86,
      (int)phkResult);
    v40 = v85;
LABEL_83:
    CLogonController::_TransitionToNone(v40, v116);
    v135 = &LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v135);
LABEL_78:
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v135);
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x18001ac90  push    rbp
0x18001ac92  push    rbx
0x18001ac93  push    rsi
0x18001ac94  push    rdi
0x18001ac95  push    r12
0x18001ac97  push    r13
0x18001ac99  push    r14
0x18001ac9b  push    r15
0x18001ac9d  lea     rbp, [rsp-1F8h]
0x18001aca5  sub     rsp, 2F8h
0x18001acac  movaps  [rsp+330h+var_50], xmm6
0x18001acb4  mov     rax, cs:__security_cookie
0x18001acbb  xor     rax, rsp
0x18001acbe  mov     [rbp+230h+var_60], rax
0x18001acc5  mov     [rsp+330h+length], r9d
0x18001acca  mov     [rbp+230h+var_2A0], r8d
0x18001acce  mov     r12d, edx
0x18001acd1  mov     dword ptr [rbp+230h+var_2A8], edx
0x18001acd4  mov     rsi, rcx
0x18001acd7  mov     rax, [rbp+230h+arg_28]
0x18001acde  mov     [rbp+230h+var_260], rax
0x18001ace2  mov     [rsp+330h+var_2D8], r8d
0x18001ace7  mov     dword ptr [rsp+330h+var_2B8], r9d
0x18001acec  mov     rax, [rbp+230h+arg_20]
0x18001acf3  mov     [rbp+230h+var_298], rax
0x18001acf7  mov     r13, [rbp+230h+arg_30]
0x18001acfe  mov     [rbp+230h+sourceString], r13
0x18001ad02  mov     [rbp+230h+var_258], r13
0x18001ad06  mov     r14, [rbp+230h+arg_38]
0x18001ad0d  mov     [rbp+230h+var_268], r14
0x18001ad11  mov     rdi, [rbp+230h+arg_40]
0x18001ad18  mov     [rbp+230h+var_280], rdi
0x18001ad1c  mov     rbx, [rbp+230h+arg_48]
0x18001ad23  mov     [rbp+230h+var_270], rbx
0x18001ad27  xor     r15d, r15d
0x18001ad2a  mov     [rbp+230h+var_208], r15d
0x18001ad2e  mov     [rbp+230h+var_204], r15b
0x18001ad32  mov     [rbp+230h+var_1C8], r15b
0x18001ad36  mov     [rbp+230h+var_1E0], r15d
0x18001ad3a  lea     rax, aClogoncontroll_26; "CLogonController_ReportResult_Activity"
0x18001ad41  mov     [rbp+230h+var_1D8], rax
0x18001ad45  mov     [rbp+230h+var_1D0], r15
0x18001ad49  mov     [rbp+230h+var_1C0], r15d
0x18001ad4d  xorps   xmm0, xmm0
0x18001ad50  movdqa  [rbp+230h+var_120], xmm0
0x18001ad58  xorps   xmm1, xmm1
0x18001ad5b  xor     eax, eax
0x18001ad5d  movups  [rbp+230h+var_1B8], xmm1
0x18001ad61  movups  [rbp+230h+var_1A8], xmm1
0x18001ad68  movups  [rbp+230h+var_198], xmm1
0x18001ad6f  movups  [rbp+230h+var_188], xmm1
0x18001ad76  movups  [rbp+230h+var_178], xmm1
0x18001ad7d  movups  [rbp+230h+var_168], xmm1
0x18001ad84  movups  [rbp+230h+var_158], xmm1
0x18001ad8b  movups  [rbp+230h+var_148], xmm1
0x18001ad92  movups  [rbp+230h+var_138], xmm1
0x18001ad99  mov     [rbp+230h+var_128], rax
0x18001ada0  mov     [rbp+230h+var_110], 1
0x18001adaa  mov     [rbp+230h+var_108], rax
0x18001adb1  lea     rax, [rbp+230h+var_208]
0x18001adb5  mov     [rbp+230h+var_100], rax
0x18001adbc  mov     [rbp+230h+var_F8], r15
0x18001adc3  mov     [rbp+230h+var_F0], r15
0x18001adca  lea     rax, [rbp+230h+var_210]
0x18001adce  mov     [rbp+230h+var_E8], rax
0x18001add5  mov     [rbp+230h+var_E0], r15
0x18001addc  mov     [rbp+230h+var_D8], r15d
0x18001ade3  lea     rax, [rbp+230h+var_1E0]
0x18001ade7  mov     [rbp+230h+var_D0], rax
0x18001adee  mov     [rbp+230h+var_C8], r15b
0x18001adf5  lea     rax, ??_7CLogonController_ReportResult_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_ReportResult_Activity::`vftable'
0x18001adfc  mov     [rbp+230h+var_210], rax
0x18001ae00  xorps   xmm6, xmm6
0x18001ae03  movdqa  xmmword ptr [rbp+230h+Data], xmm6
0x18001ae08  mov     [rbp+230h+hKey], r15
0x18001ae0c  lea     rax, [rbp+230h+hKey]
0x18001ae10  mov     [rsp+330h+phkResult], rax; phkResult
0x18001ae15  mov     r9d, 20019h; samDesired
0x18001ae1b  xor     r8d, r8d; ulOptions
0x18001ae1e  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ae25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ae2c  call    cs:__imp_RegOpenKeyExW
0x18001ae32  test    eax, eax
0x18001ae34  js      loc_18001B2C4
0x18001ae3a  mov     [rbp+230h+Type], 3
0x18001ae41  mov     [rsp+330h+cbData], 10h
0x18001ae49  lea     rax, [rsp+330h+cbData]
0x18001ae4e  mov     [rsp+330h+lpcbData], rax; lpcbData
0x18001ae53  lea     rax, [rbp+230h+Data]
0x18001ae57  mov     [rsp+330h+phkResult], rax; int
0x18001ae5c  lea     r9, [rbp+230h+Type]; lpType
0x18001ae60  xor     r8d, r8d; lpReserved
0x18001ae63  lea     rdx, aFirstruncorrel; "FirstRunCorrelationID"
0x18001ae6a  mov     rcx, [rbp+230h+hKey]; hKey
0x18001ae6e  call    cs:__imp_RegQueryValueExW
0x18001ae74  test    eax, eax
0x18001ae76  jle     short loc_18001AE82
0x18001ae78  movzx   eax, ax
0x18001ae7b  or      eax, 80070000h
0x18001ae80  test    eax, eax
0x18001ae82  jns     loc_18001B2C4
0x18001ae88  movaps  xmmword ptr [rbp+230h+Data], xmm6
0x18001ae8c  mov     rcx, [rbp+230h+hKey]; hKey
0x18001ae90  test    rcx, rcx
0x18001ae93  jz      short loc_18001AE9B
0x18001ae95  call    cs:__imp_RegCloseKey
0x18001ae9b  movdqa  xmmword ptr [rbp+230h+hKey], xmm6
0x18001aea0  mov     r8d, 10h; Size
0x18001aea6  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18001aead  lea     rcx, [rbp+230h+hKey]; Buf1
0x18001aeb1  call    memcmp_0
0x18001aeb6  test    eax, eax
0x18001aeb8  jnz     loc_18001B228
0x18001aebe  lea     rcx, [rbp+230h+var_210]; this
0x18001aec2  call    ?StartActivity@CLogonController_ReportResult_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLogonController_ReportResult_Activity::StartActivity(void)
0x18001aec7  mov     [r14], r15
0x18001aeca  mov     [rdi], r15d
0x18001aecd  mov     [rbx], r15d
0x18001aed0  lea     r15, [rsi-20h]
0x18001aed4  mov     [rbp+230h+hKey], r15
0x18001aed8  mov     [rsp+330h+var_2E0], 0
0x18001aedd  mov     rcx, [r15+90h]
0x18001aee4  add     rcx, 10h
0x18001aee8  mov     rax, [rcx]
0x18001aeeb  lea     rdx, [rsp+330h+var_2E0]
0x18001aef0  mov     rax, [rax+0E0h]
0x18001aef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aefc  mov     ebx, eax
0x18001aefe  test    eax, eax
0x18001af00  js      loc_18001BB0E
0x18001af06  call    cs:__imp_?IsFirstBoot@@YA_NXZ; IsFirstBoot(void)
0x18001af0c  test    al, al
0x18001af0e  jz      loc_18001B2CD
0x18001af14  mov     rcx, [rsi+90h]
0x18001af1b  add     rcx, 8
0x18001af1f  mov     rax, [rcx]
0x18001af22  mov     rax, [rax+20h]
0x18001af26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af2b  test    eax, eax
0x18001af2d  jnz     loc_18001C15F
0x18001af33  mov     [rsp+330h+var_2DF], 0
0x18001af38  xor     ebx, ebx
0x18001af3a  test    r13, r13
0x18001af3d  jnz     loc_18001C19B
0x18001af43  lea     rdi, [rsi+100h]
0x18001af4a  mov     rcx, rdi; SRWLock
0x18001af4d  call    cs:__imp_AcquireSRWLockShared
0x18001af53  movzx   r14d, byte ptr [rsi+110h]
0x18001af5b  mov     [rsp+330h+var_2C0], r14b
0x18001af60  test    rdi, rdi
0x18001af63  jz      short loc_18001AF6E
0x18001af65  mov     rcx, rdi; SRWLock
0x18001af68  call    cs:__imp_ReleaseSRWLockShared
0x18001af6e  cmp     [rbp+230h+var_2A0], 0
0x18001af72  jl      loc_18001C1AA
0x18001af78  test    r14b, r14b
0x18001af7b  jz      loc_18001C1D2
0x18001af81  mov     rcx, [rsi+90h]
0x18001af88  add     rcx, 8
0x18001af8c  mov     rax, [rcx]
0x18001af8f  mov     rax, [rax+18h]
0x18001af93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af98  mov     [rsp+330h+var_2D0], 0
0x18001afa0  lea     rdi, [rsi+0B8h]
0x18001afa7  mov     rcx, rdi; SRWLock
0x18001afaa  call    cs:__imp_AcquireSRWLockExclusive
0x18001afb0  mov     qword ptr [rbp+230h+Data], rdi
0x18001afb4  mov     eax, [rsi+0C0h]
0x18001afba  test    eax, eax
0x18001afbc  jnz     loc_18001C1DF
0x18001afc2  mov     dword ptr [rsi+0C0h], 1
0x18001afcc  inc     dword ptr [rsi+0D0h]
0x18001afd2  mov     eax, [rsi+0D0h]
0x18001afd8  mov     [rsp+330h+var_2D0], eax
0x18001afdc  test    rdi, rdi
0x18001afdf  jz      short loc_18001AFEA
0x18001afe1  mov     rcx, rdi; SRWLock
0x18001afe4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001afea  mov     [rbp+230h+var_250], r15
0x18001afee  lea     rax, [rsp+330h+var_2D0]
0x18001aff3  mov     [rbp+230h+var_248], rax
0x18001aff7  mov     [rbp+230h+var_240], 1
0x18001affb  mov     r15, [rsi+70h]
0x18001afff  mov     eax, 4
0x18001b004  mov     [rbp+230h+Type], eax
0x18001b007  cmp     r12d, 1
0x18001b00b  jnz     loc_18001B2F6
0x18001b011  mov     r14d, r12d
0x18001b014  lea     rbx, [r15+258h]
0x18001b01b  mov     rcx, rbx; SRWLock
0x18001b01e  call    cs:__imp_AcquireSRWLockExclusive
0x18001b024  mov     [r15+260h], r14d
0x18001b02b  test    rbx, rbx
0x18001b02e  jnz     loc_18001B23A
0x18001b034  lea     rbx, sourceString
0x18001b03b  mov     rax, [rbp+230h+var_298]
0x18001b03f  test    rax, rax
0x18001b042  cmovnz  rbx, rax
0x18001b046  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001b04d  cmp     [rbp+230h+var_2A0], 0
0x18001b051  jl      loc_18001B11E
0x18001b057  cmp     r12d, 1
0x18001b05b  ja      loc_18001B11E
0x18001b061  mov     r15, [rsi+70h]
0x18001b065  test    r12d, r12d
0x18001b068  jnz     loc_18001B248
0x18001b06e  mov     r9, r13; unsigned __int16 *
0x18001b071  mov     r8, [rbp+230h+var_260]; unsigned __int16 *
0x18001b075  mov     rdx, rbx; unsigned __int16 *
0x18001b078  mov     rcx, r15; this
0x18001b07b  call    ?RecordSuccessfulLogon@CProcessStateManager@@QEAAXPEBG00@Z; CProcessStateManager::RecordSuccessfulLogon(ushort const *,ushort const *,ushort const *)
0x18001b080  xor     eax, eax
0x18001b082  mov     qword ptr [rbp+230h+Data], rax
0x18001b086  mov     qword ptr [rbp+230h+Data+8], rax
0x18001b08a  mov     [rbp+230h+hLibModule], rax
0x18001b08e  xor     edx, edx; int
0x18001b090  lea     rcx, [rbp+230h+Data]; this
0x18001b094  call    ?_EnableMouseInputForCursorSuppression@CImmersiveCursor@Shell@Windows@@AEAA_NH@Z; Windows::Shell::CImmersiveCursor::_EnableMouseInputForCursorSuppression(int)
0x18001b099  nop
0x18001b09a  mov     rcx, [rbp+230h+hLibModule]; hLibModule
0x18001b09e  test    rcx, rcx
0x18001b0a1  jz      short loc_18001B0A9
0x18001b0a3  call    cs:__imp_FreeLibrary
0x18001b0a9  cmp     cs:byte_1800D3540, 0
0x18001b0b0  jz      short loc_18001B0DF
0x18001b0b2  mov     cs:byte_1800D3540, 0
0x18001b0b9  mov     ecx, 13h; nIndex
0x18001b0be  call    cs:__imp_GetSystemMetrics
0x18001b0c4  test    eax, eax
0x18001b0c6  jz      short loc_18001B0DF
0x18001b0c8  mov     ecx, 1000h; nIndex
0x18001b0cd  call    cs:__imp_GetSystemMetrics
0x18001b0d3  test    eax, eax
0x18001b0d5  jnz     short loc_18001B0DF
0x18001b0d7  xor     ecx, ecx; bShow
0x18001b0d9  call    cs:__imp_ShowCursor
0x18001b0df  test    r12d, r12d
0x18001b0e2  jnz     loc_18001BDFB
0x18001b0e8  lea     rbx, [rsi+138h]
0x18001b0ef  mov     rcx, rbx; SRWLock
0x18001b0f2  call    cs:__imp_AcquireSRWLockExclusive
0x18001b0f8  mov     qword ptr [rbp+230h+Data], rbx
0x18001b0fc  mov     rcx, [rsi+170h]
0x18001b103  test    rcx, rcx
0x18001b106  jz      short loc_18001B115
0x18001b108  mov     rax, [rcx]
0x18001b10b  mov     rax, [rax+48h]
0x18001b10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b114  nop
0x18001b115  test    rbx, rbx
0x18001b118  jnz     loc_18001B9C2
0x18001b11e  mov     [rsp+330h+var_2E0], 0
0x18001b123  mov     rcx, [rsi+70h]
0x18001b127  add     rcx, 10h
0x18001b12b  mov     rax, [rcx]
0x18001b12e  lea     rdx, [rsp+330h+var_2E0]
0x18001b133  mov     rax, [rax+0E0h]
0x18001b13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b13f  mov     ebx, eax
0x18001b141  test    eax, eax
0x18001b143  js      loc_18001BE63
0x18001b149  xor     r12b, r12b
0x18001b14c  xor     r15d, r15d
0x18001b14f  cmp     [rsp+330h+var_2E0], r12b
0x18001b154  jnz     short loc_18001B1AC
0x18001b156  mov     [rsp+330h+cbData], r15d
0x18001b15b  mov     [rsp+330h+var_2D8], 4
0x18001b163  lea     rax, [rsp+330h+var_2D8]
0x18001b168  mov     [rsp+330h+pcbData], rax; pcbData
0x18001b16d  lea     rax, [rsp+330h+cbData]
0x18001b172  mov     [rsp+330h+lpcbData], rax; pvData
0x18001b177  mov     [rsp+330h+phkResult], r15; int
0x18001b17c  mov     r9d, 10h; dwFlags
0x18001b182  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x18001b189  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001b190  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001b197  call    cs:__imp_RegGetValueW
0x18001b19d  mov     eax, [rsp+330h+cbData]
0x18001b1a1  dec     eax
0x18001b1a3  cmp     eax, 1
0x18001b1a6  ja      loc_18001BEBC
0x18001b1ac  xor     r13b, r13b
0x18001b1af  mov     [rsp+330h+var_2E0], r13b
0x18001b1b4  mov     rdx, [rbp+230h+sourceString]
0x18001b1b8  test    r12b, r12b
0x18001b1bb  jnz     loc_18001C2CE
0x18001b1c1  mov     r12d, dword ptr [rbp+230h+var_2A8]
0x18001b1c5  cmp     r12d, 1
0x18001b1c9  ja      loc_18001B54D
0x18001b1cf  mov     [rsp+330h+cbData], r15d
0x18001b1d4  mov     rbx, [rsi+70h]
0x18001b1d8  mov     r12, [rbx+18h]
0x18001b1dc  lea     rcx, sourceString
0x18001b1e3  test    rdx, rdx
0x18001b1e6  cmovnz  rcx, rdx; sourceString
0x18001b1ea  mov     [rbp+230h+string], r15
0x18001b1ee  mov     rdx, r14
0x18001b1f1  inc     rdx; length
0x18001b1f4  cmp     word ptr [rcx+rdx*2], 0
0x18001b1f9  jnz     short loc_18001B1F1
  ... truncated ...
```
