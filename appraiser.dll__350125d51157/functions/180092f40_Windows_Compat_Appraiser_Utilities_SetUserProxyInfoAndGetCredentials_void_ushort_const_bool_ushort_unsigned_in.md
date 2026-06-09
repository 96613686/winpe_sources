# Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180092f40`
- end: `0x180093786`
- name: `?SetUserProxyInfoAndGetCredentials@Utilities@Appraiser@Compat@Windows@@SAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `2118`
- prototype: `static int(void **, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800911bc`

## callees

- `0x180001008`
- `0x1800011ac`
- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800142b4`
- `0x1800151d8`
- `0x18001a2f4`
- `0x18002924c`
- `0x18002c0fc`
- `0x18002d7f8`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180087e70`
- `0x180089b2c`
- `0x180092f40`
- `0x1800a5d88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800934f1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800934f1`
- `KERNEL32!GlobalFree` at `0x180093058`
- `KERNEL32!GlobalFree` at `0x18009306d`
- `KERNEL32!GlobalFree` at `0x180093081`
- `KERNEL32!GlobalFree` at `0x180093094`
- `KERNEL32!GlobalFree` at `0x1800930a7`
- `KERNEL32!GlobalFree` at `0x1800932b2`
- `KERNEL32!GlobalFree` at `0x1800932cb`
- `KERNEL32!GlobalFree` at `0x180093342`
- `KERNEL32!GlobalFree` at `0x18009335b`
- `KERNEL32!GlobalFree` at `0x18009338e`
- `KERNEL32!GlobalFree` at `0x1800933a3`
- `KERNEL32!GlobalFree` at `0x180093058`
- `KERNEL32!GlobalFree` at `0x18009306d`
- `KERNEL32!GlobalFree` at `0x180093081`
- `KERNEL32!GlobalFree` at `0x180093094`
- `KERNEL32!GlobalFree` at `0x1800930a7`
- `KERNEL32!GlobalFree` at `0x1800932b2`
- `KERNEL32!GlobalFree` at `0x1800932cb`
- `KERNEL32!GlobalFree` at `0x180093342`
- `KERNEL32!GlobalFree` at `0x18009335b`
- `KERNEL32!GlobalFree` at `0x18009338e`
- `KERNEL32!GlobalFree` at `0x1800933a3`
- `KERNEL32!ExitProcess` at `0x18009377f`
- `KERNEL32!ExitProcess` at `0x18009377f`
- `KERNEL32!CloseHandle` at `0x180093043`
- `KERNEL32!CloseHandle` at `0x180093043`
- `KERNEL32!GetLastError` at `0x180093121`
- `KERNEL32!GetLastError` at `0x180093148`
- `KERNEL32!GetLastError` at `0x180093171`
- `KERNEL32!GetLastError` at `0x1800931c4`
- `KERNEL32!GetLastError` at `0x1800931d3`
- `KERNEL32!GetLastError` at `0x1800931fd`
- `KERNEL32!GetLastError` at `0x180093217`
- `KERNEL32!GetLastError` at `0x18009326a`
- `KERNEL32!GetLastError` at `0x1800933c0`
- `KERNEL32!GetLastError` at `0x1800933e5`
- `KERNEL32!GetLastError` at `0x1800933fc`
- `KERNEL32!GetLastError` at `0x180093468`
- `KERNEL32!GetLastError` at `0x18009348d`
- `KERNEL32!GetLastError` at `0x1800934a4`
- `KERNEL32!GetLastError` at `0x1800935ed`
- `KERNEL32!GetLastError` at `0x180093604`
- `KERNEL32!GetLastError` at `0x18009362f`
- `KERNEL32!GetLastError` at `0x180093777`
- `KERNEL32!GetLastError` at `0x180093121`
- `KERNEL32!GetLastError` at `0x180093148`
- `KERNEL32!GetLastError` at `0x180093171`
- `KERNEL32!GetLastError` at `0x1800931c4`
- `KERNEL32!GetLastError` at `0x1800931d3`
- `KERNEL32!GetLastError` at `0x1800931fd`
- `KERNEL32!GetLastError` at `0x180093217`
- `KERNEL32!GetLastError` at `0x18009326a`
- `KERNEL32!GetLastError` at `0x1800933c0`
- `KERNEL32!GetLastError` at `0x1800933e5`
- `KERNEL32!GetLastError` at `0x1800933fc`
- `KERNEL32!GetLastError` at `0x180093468`
- `KERNEL32!GetLastError` at `0x18009348d`
- `KERNEL32!GetLastError` at `0x1800934a4`
- `KERNEL32!GetLastError` at `0x1800935ed`
- `KERNEL32!GetLastError` at `0x180093604`
- `KERNEL32!GetLastError` at `0x18009362f`
- `KERNEL32!GetLastError` at `0x180093777`
- `ADVAPI32!RevertToSelf` at `0x1800935df`
- `ADVAPI32!RevertToSelf` at `0x1800935df`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180093113`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180093113`
- `WINHTTP!WinHttpSetOption` at `0x18009345e`
- `WINHTTP!WinHttpSetOption` at `0x18009345e`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800931ab`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800931ab`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800932ed`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800932ed`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800933b6`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800933b6`

## string_xrefs

- `0x18009300f`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800930f1`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093183`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093239`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093562`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093641`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800936ee`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093127`: `Failed to impersonate user to get proxy: [%d].`
- `0x18009360a`: `Failed to un-impersonate user: [%d].`
- `0x180092f7d`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x18009315a`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x1800931e5`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x180093232`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x1800933d3`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x18009347b`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x18009352c`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x180093543`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x18009359e`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x1800935c3`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`
- `0x180093617`: `Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials(
        void **a1,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned __int16 *a6)
{
  char v7; // r14
  char *v8; // r15
  int UserSession; // eax
  signed int v10; // ebx
  DWORD LastError; // eax
  signed int v13; // eax
  DWORD v14; // eax
  signed int v15; // eax
  char v16; // dl
  const char *v17; // rax
  unsigned __int64 v18; // rbx
  BOOL ProxyForUrl; // eax
  WCHAR *lpszProxy; // rax
  DWORD v21; // eax
  signed int v22; // eax
  char *v23; // rbx
  DWORD v24; // eax
  signed int v25; // eax
  wchar_t *v26; // rax
  unsigned __int64 v27; // r8
  int CredentialsForBasicProxyIfPresent; // eax
  int v29; // esi
  __int64 v30; // rcx
  signed int v31; // eax
  signed int v32; // ebx
  DWORD v33; // eax
  TraceLoggingCorrelationVector *v34; // rcx
  const struct _tlgProvider_t *GeneralProvider; // rax
  __int64 v36; // r15
  __int64 v37; // rax
  const char **v38; // r14
  const char **v39; // rsi
  const char **v40; // rdi
  const unsigned __int16 *v41; // rax
  const size_t **v42; // rbx
  struct _SYSTEMTIME *v43; // rdx
  __int128 v44; // xmm0
  __int64 v45; // r8
  __int64 v46; // r9
  UINT v47; // eax
  char *v48; // [rsp+20h] [rbp-E0h]
  char *v49; // [rsp+20h] [rbp-E0h]
  char *v50; // [rsp+20h] [rbp-E0h]
  char *v51; // [rsp+20h] [rbp-E0h]
  char *v52; // [rsp+20h] [rbp-E0h]
  char *v53; // [rsp+20h] [rbp-E0h]
  char *v54; // [rsp+30h] [rbp-D0h]
  char v55; // [rsp+60h] [rbp-A0h]
  int v56; // [rsp+64h] [rbp-9Ch] BYREF
  WINHTTP_PROXY_INFO hMem; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  HINTERNET *v59; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v60; // [rsp+90h] [rbp-70h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG v61; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v62; // [rsp+B8h] [rbp-48h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v64[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v65[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v66[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v67; // [rsp+100h] [rbp+0h] BYREF
  char v68[144]; // [rsp+110h] [rbp+10h] BYREF
  char v69[144]; // [rsp+1A0h] [rbp+A0h] BYREF

  v59 = a1;
  v60 = a4;
  v62 = a6;
  v56 = 0;
  *a6 = 0;
  *a4 = 0;
  v7 = 0;
  v55 = 0;
  v8 = 0;
  hObject = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&v61, 0, sizeof(v61));
  memset(&hMem, 0, sizeof(hMem));
  if ( !a3 )
  {
    UserSession = Windows::Compat::Appraiser::Utilities::FindUserSession(&hObject, &v56);
    v10 = UserSession;
    if ( UserSession < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
        2970,
        "Failed to look for current user session: [0x%x].",
        UserSession);
      LODWORD(v54) = v10;
      LODWORD(v49) = v10;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        155,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
        v49,
        (int)"Failed to look for current user session: [0x%x].",
        v54);
      v8 = (char *)hObject;
      goto LABEL_4;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB9Bu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
        "Failed to look for current user session: [0x%x].",
        UserSession);
    v8 = (char *)hObject;
    if ( v56 )
    {
      if ( !ImpersonateLoggedOnUser(hObject) )
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
          2977,
          "Failed to impersonate user to get proxy: [%d].",
          LastError);
        v13 = GetLastError();
        v10 = v13;
        if ( v13 > 0 )
          v10 = (unsigned __int16)v13 | 0x80070000;
        if ( v10 >= 0 )
          v10 = -2147467259;
        LODWORD(v54) = GetLastError();
        LODWORD(v50) = v10;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          162,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
          v50,
          (int)"Failed to impersonate user to get proxy: [%d].",
          v54);
        goto LABEL_4;
      }
      v55 = 1;
    }
  }
  if ( !WinHttpGetIEProxyConfigForCurrentUser(&v61) && GetLastError() != 2 )
  {
    v14 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
      2992,
      "Failed to get proxy from current user: [%d].",
      v14);
    v15 = GetLastError();
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
    LODWORD(v54) = GetLastError();
    v16 = -79;
    v17 = "Failed to get proxy from current user: [%d].";
    goto LABEL_35;
  }
  v18 = 0;
  ProxyForUrl = 0;
  do
  {
    if ( ProxyForUrl )
      goto LABEL_80;
    if ( v18 )
    {
      if ( GetLastError() != 12015 )
        goto LABEL_51;
      pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    }
    pAutoProxyOptions.lpszAutoConfigUrl = v61.lpszAutoConfigUrl;
    if ( v61.lpszAutoConfigUrl )
    {
      *(_QWORD *)&pAutoProxyOptions.dwFlags = 2;
    }
    else
    {
      pAutoProxyOptions.dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
    }
    if ( v7 )
    {
      if ( hMem.lpszProxy )
      {
        GlobalFree(hMem.lpszProxy);
        hMem.lpszProxy = 0;
      }
      if ( hMem.lpszProxyBypass )
      {
        GlobalFree(hMem.lpszProxyBypass);
        hMem.lpszProxyBypass = 0;
      }
    }
    ProxyForUrl = WinHttpGetProxyForUrl(*v59, a2, &pAutoProxyOptions, &hMem);
    ++v18;
    v7 = 1;
  }
  while ( v18 < 2 );
  if ( ProxyForUrl )
    goto LABEL_80;
LABEL_51:
  lpszProxy = v61.lpszProxy;
  if ( v61.lpszProxy && *v61.lpszProxy && (*v61.lpszProxy != 58 || v61.lpszProxy[1]) )
  {
    if ( v7 )
    {
      if ( hMem.lpszProxy )
      {
        GlobalFree(hMem.lpszProxy);
        lpszProxy = v61.lpszProxy;
        hMem.lpszProxy = 0;
      }
      if ( hMem.lpszProxyBypass )
      {
        GlobalFree(hMem.lpszProxyBypass);
        lpszProxy = v61.lpszProxy;
      }
      v7 = 0;
    }
    hMem.lpszProxy = lpszProxy;
    hMem.lpszProxyBypass = v61.lpszProxyBypass;
    hMem.dwAccessType = 3;
    goto LABEL_80;
  }
  if ( v7 )
  {
    if ( hMem.lpszProxy )
    {
      GlobalFree(hMem.lpszProxy);
      hMem.lpszProxy = 0;
    }
    if ( hMem.lpszProxyBypass )
    {
      GlobalFree(hMem.lpszProxyBypass);
      hMem.lpszProxyBypass = 0;
    }
    v7 = 0;
  }
  if ( WinHttpGetDefaultProxyConfiguration(&hMem) )
  {
    v23 = (char *)hMem.lpszProxy;
    if ( !hMem.lpszProxy || !*hMem.lpszProxy || *hMem.lpszProxy == 58 && !hMem.lpszProxy[1] )
    {
      v7 = 1;
      goto LABEL_98;
    }
    v7 = 1;
LABEL_80:
    if ( !WinHttpSetOption(*v59, 0x26u, &hMem, 0x18u) )
    {
      v24 = GetLastError();
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
        3068,
        "Failed to set proxy option: [%d].",
        v24);
      v25 = GetLastError();
      v10 = v25;
      if ( v25 > 0 )
        v10 = (unsigned __int16)v25 | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      LODWORD(v54) = GetLastError();
      v16 = -3;
      v17 = "Failed to set proxy option: [%d].";
      goto LABEL_35;
    }
    v23 = (char *)hMem.lpszProxy;
    if ( hMem.lpszProxy && *hMem.lpszProxy && (*hMem.lpszProxy != 58 || hMem.lpszProxy[1]) )
    {
      v26 = wcsrchr(hMem.lpszProxy, 0x3Au);
      if ( v26 )
        *v26 = 0;
      CredentialsForBasicProxyIfPresent = Windows::Compat::Appraiser::Utilities::GetCredentialsForBasicProxyIfPresent(
                                            v23,
                                            v60,
                                            v27,
                                            v62,
                                            (unsigned __int64)v48);
      v29 = CredentialsForBasicProxyIfPresent;
      if ( CredentialsForBasicProxyIfPresent < 0 )
      {
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
          3099,
          "Failed to get credentials for proxy %ls: [0x%x].",
          (const wchar_t *)v23,
          CredentialsForBasicProxyIfPresent);
        if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
        {
          LODWORD(v52) = v29;
          v30 = 1;
        }
        else
        {
          v52 = 0;
          v30 = 0;
        }
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)v30,
          28,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
          v52,
          (int)"Failed to get credentials for proxy %ls: [0x%x].",
          v23,
          v29);
      }
      v23 = (char *)hMem.lpszProxy;
    }
LABEL_98:
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
      3105,
      "Proxy Server List: %ls.",
      (const wchar_t *)v23);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
      3106,
      "Proxy Bypass List: %ls.",
      hMem.lpszProxyBypass);
    v10 = 0;
    goto LABEL_99;
  }
  v21 = GetLastError();
  AslLogCallPrintf(
    3,
    "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
    3052,
    "Failed to get proxy from global defaults: [%d].",
    v21);
  v22 = GetLastError();
  v10 = v22;
  if ( v22 > 0 )
    v10 = (unsigned __int16)v22 | 0x80070000;
  if ( v10 >= 0 )
    v10 = -2147467259;
  LODWORD(v54) = GetLastError();
  v16 = -19;
  v17 = "Failed to get proxy from global defaults: [%d].";
LABEL_35:
  LODWORD(v51) = v10;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v16,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
    "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
    v51,
    (int)v17,
    v54);
LABEL_99:
  if ( v55 && !RevertToSelf() )
  {
    v31 = GetLastError();
    v32 = v31;
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    if ( v32 >= 0 )
      v32 = -2147467259;
    v33 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
      3122,
      "Failed to un-impersonate user: [%d].",
      v33);
    LODWORD(v54) = GetLastError();
    LODWORD(v53) = v32;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      51,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials",
      v53,
      (int)"Failed to un-impersonate user: [%d].",
      v54);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v68);
    v34 = (TraceLoggingCorrelationVector *)v68;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v34 = Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToString(v34, v69);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler);
    GeneralProvider = Windows::Compat::Shared::Telemetry::TelemetryProvider::GetGeneralProvider((Windows::Compat::Shared::Telemetry::TelemetryProvider *)&APPRAISER_INSTRUMENTATION_PROVIDER);
    v36 = (__int64)GeneralProvider;
    if ( *(_DWORD *)GeneralProvider > 5u && (unsigned __int8)tlgKeywordOn(GeneralProvider, 0x200000000000LL) )
    {
      v37 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v62, v69);
      v56 = v32;
      v38 = (const char **)v37;
      v39 = (const char **)_tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
                             &v59,
                             "Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials");
      v40 = (const char **)_tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
                             v64,
                             "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp");
      LODWORD(hObject) = 3123;
      v41 = Windows::Compat::Appraiser::WicaFactory::Pcfp();
      v42 = (const size_t **)_tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v65, v41);
      v44 = (__int128)*Windows::Compat::Appraiser::GetCurrentSystemTime((Windows::Compat::Appraiser *)v66, v43);
      v60 = (unsigned __int16 *)&v67;
      v67 = v44;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v36,
        (__int64)&byte_1802A2137,
        v45,
        v46,
        (__int64 *)&v60,
        v42,
        (__int64)&hObject,
        v40,
        v39,
        (__int64)&v56,
        v38);
    }
    v47 = GetLastError();
    ExitProcess(v47);
  }
LABEL_4:
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  if ( v7 )
  {
    if ( hMem.lpszProxy )
    {
      GlobalFree(hMem.lpszProxy);
      hMem.lpszProxy = 0;
    }
    if ( hMem.lpszProxyBypass )
    {
      GlobalFree(hMem.lpszProxyBypass);
      hMem.lpszProxyBypass = 0;
    }
  }
  if ( v61.lpszAutoConfigUrl )
  {
    GlobalFree(v61.lpszAutoConfigUrl);
    v61.lpszAutoConfigUrl = 0;
  }
  if ( v61.lpszProxy )
  {
    GlobalFree(v61.lpszProxy);
    v61.lpszProxy = 0;
  }
  if ( v61.lpszProxyBypass )
    GlobalFree(v61.lpszProxyBypass);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180092f40  mov     [rsp-8+arg_10], rbx
0x180092f45  push    rbp
0x180092f46  push    rsi
0x180092f47  push    rdi
0x180092f48  push    r12
0x180092f4a  push    r13
0x180092f4c  push    r14
0x180092f4e  push    r15
0x180092f50  lea     rbp, [rsp-140h]
0x180092f58  sub     rsp, 240h
0x180092f5f  mov     rax, cs:__security_cookie
0x180092f66  xor     rax, rsp
0x180092f69  mov     [rbp+170h+var_40], rax
0x180092f70  xor     edi, edi
0x180092f72  mov     [rbp+170h+var_1E8], rcx
0x180092f76  mov     rcx, [rbp+170h+arg_28]
0x180092f7d  lea     r12, aWindowsCompatA_275; "Windows::Compat::Appraiser::Utilities::"...
0x180092f84  xorps   xmm0, xmm0
0x180092f87  mov     [rbp+170h+var_1E0], r9
0x180092f8b  xor     eax, eax
0x180092f8d  mov     [rbp+170h+var_1B8], rcx
0x180092f91  mov     [rsp+270h+var_20C], edi
0x180092f95  xorps   xmm1, xmm1
0x180092f98  mov     [rcx], di
0x180092f9b  mov     r13, rdx
0x180092f9e  mov     [r9], di
0x180092fa2  mov     r14b, dil
0x180092fa5  mov     [rsp+270h+var_210], dil
0x180092faa  mov     r15d, edi
0x180092fad  mov     [rsp+270h+var_1F8], rax
0x180092fb2  mov     [rbp+170h+hObject], rdi
0x180092fb6  movups  xmmword ptr [rbp+170h+pAutoProxyOptions.dwFlags], xmm0
0x180092fba  movups  xmmword ptr [rbp+170h+pAutoProxyOptions.lpvReserved], xmm0
0x180092fbe  movups  xmmword ptr [rbp+170h+var_1D8], xmm1
0x180092fc2  movups  xmmword ptr [rbp+170h+var_1C8], xmm1
0x180092fc6  movups  xmmword ptr [rsp+270h+hMem], xmm0
0x180092fcb  test    r8b, r8b
0x180092fce  jnz     loc_1800931A7
0x180092fd4  lea     rdx, [rsp+270h+var_20C]; int *
0x180092fd9  lea     rcx, [rbp+170h+hObject]; void **
0x180092fdd  call    ?FindUserSession@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAXPEAH@Z; Windows::Compat::Appraiser::Utilities::FindUserSession(void * *,int *)
0x180092fe2  mov     ebx, eax
0x180092fe4  test    eax, eax
0x180092fe6  jns     loc_1800930D9
0x180092fec  lea     rsi, aFailedToLookFo; "Failed to look for current user session"...
0x180092ff3  mov     dword ptr [rsp+270h+var_250], eax
0x180092ff7  mov     r9, rsi
0x180092ffa  lea     ecx, [rdi+3]
0x180092ffd  mov     r8d, 0B9Ah
0x180093003  mov     rdx, r12
0x180093006  call    AslLogCallPrintf
0x18009300b  mov     dword ptr [rsp+270h+var_240], ebx; char *
0x18009300f  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180093016  mov     qword ptr [rsp+270h+var_248], rsi; int
0x18009301b  lea     ecx, [rdi+1]; this
0x18009301e  mov     r9, r12; char *
0x180093021  mov     dword ptr [rsp+270h+var_250], ebx; char *
0x180093025  mov     edx, 0B9Bh; bool
0x18009302a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18009302f  mov     r15, [rbp+170h+hObject]
0x180093033  xor     r13d, r13d
0x180093036  lea     rax, [r15-1]
0x18009303a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009303e  ja      short loc_180093049
0x180093040  mov     rcx, r15; hObject
0x180093043  call    cs:__imp_CloseHandle
0x180093049  test    r14b, r14b
0x18009304c  jz      short loc_180093078
0x18009304e  mov     rcx, [rsp+270h+hMem+8]; hMem
0x180093053  test    rcx, rcx
0x180093056  jz      short loc_180093063
0x180093058  call    cs:__imp_GlobalFree
0x18009305e  mov     [rsp+270h+hMem+8], r13
0x180093063  mov     rcx, [rsp+270h+var_1F8]; hMem
0x180093068  test    rcx, rcx
0x18009306b  jz      short loc_180093078
0x18009306d  call    cs:__imp_GlobalFree
0x180093073  mov     [rsp+270h+var_1F8], r13
0x180093078  mov     rcx, [rbp+170h+var_1D8+8]; hMem
0x18009307c  test    rcx, rcx
0x18009307f  jz      short loc_18009308B
0x180093081  call    cs:__imp_GlobalFree
0x180093087  mov     [rbp+170h+var_1D8+8], r13
0x18009308b  mov     rcx, [rbp+170h+var_1C8]; hMem
0x18009308f  test    rcx, rcx
0x180093092  jz      short loc_18009309E
0x180093094  call    cs:__imp_GlobalFree
0x18009309a  mov     [rbp+170h+var_1C8], r13
0x18009309e  mov     rcx, [rbp+170h+var_1C8+8]; hMem
0x1800930a2  test    rcx, rcx
0x1800930a5  jz      short loc_1800930AD
0x1800930a7  call    cs:__imp_GlobalFree
0x1800930ad  mov     eax, ebx
0x1800930af  mov     rcx, [rbp+170h+var_40]
0x1800930b6  xor     rcx, rsp; StackCookie
0x1800930b9  call    __security_check_cookie
0x1800930be  mov     rbx, [rsp+270h+arg_10]
0x1800930c6  add     rsp, 240h
0x1800930cd  pop     r15
0x1800930cf  pop     r14
0x1800930d1  pop     r13
0x1800930d3  pop     r12
0x1800930d5  pop     rdi
0x1800930d6  pop     rsi
0x1800930d7  pop     rbp
0x1800930d8  retn
0x1800930d9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800930df  test    al, 1
0x1800930e1  jz      short loc_180093102
0x1800930e3  lea     r9, aFailedToLookFo; "Failed to look for current user session"...
0x1800930ea  mov     dword ptr [rsp+270h+var_250], ebx; unsigned __int64
0x1800930ee  mov     r8, r12; char *
0x1800930f1  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800930f8  mov     ecx, 0B9Bh; unsigned int
0x1800930fd  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180093102  mov     r15, [rbp+170h+hObject]
0x180093106  cmp     [rsp+270h+var_20C], edi
0x18009310a  jz      loc_1800931A7
0x180093110  mov     rcx, r15; hToken
0x180093113  call    cs:__imp_ImpersonateLoggedOnUser
0x180093119  test    eax, eax
0x18009311b  jnz     loc_1800931A2
0x180093121  call    cs:__imp_GetLastError
0x180093127  lea     rsi, aFailedToImpers; "Failed to impersonate user to get proxy"...
0x18009312e  mov     r8d, 0BA1h
0x180093134  mov     r9, rsi
0x180093137  mov     dword ptr [rsp+270h+var_250], eax
0x18009313b  mov     rdx, r12
0x18009313e  mov     ecx, 3
0x180093143  call    AslLogCallPrintf
0x180093148  call    cs:__imp_GetLastError
0x18009314e  xor     r13d, r13d
0x180093151  mov     ebx, eax
0x180093153  test    eax, eax
0x180093155  jle     short loc_180093167
0x180093157  movzx   ebx, ax
0x18009315a  lea     r12, aWindowsCompatA_275; "Windows::Compat::Appraiser::Utilities::"...
0x180093161  or      ebx, 80070000h
0x180093167  mov     eax, 80004005h
0x18009316c  test    ebx, ebx
0x18009316e  cmovns  ebx, eax
0x180093171  call    cs:__imp_GetLastError
0x180093177  mov     dword ptr [rsp+270h+var_240], eax; char *
0x18009317b  mov     r9, r12; char *
0x18009317e  mov     qword ptr [rsp+270h+var_248], rsi; int
0x180093183  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009318a  mov     edx, 0BA2h; bool
0x18009318f  mov     dword ptr [rsp+270h+var_250], ebx; char *
0x180093193  mov     ecx, 1; this
0x180093198  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18009319d  jmp     loc_180093036
0x1800931a2  mov     [rsp+270h+var_210], 1
0x1800931a7  lea     rcx, [rbp+170h+var_1D8]; pProxyConfig
0x1800931ab  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800931b1  mov     esi, 80004005h
0x1800931b6  mov     r12d, 80070000h
0x1800931bc  test    eax, eax
0x1800931be  jnz     loc_180093253
0x1800931c4  call    cs:__imp_GetLastError
0x1800931ca  cmp     eax, 2
0x1800931cd  jz      loc_180093253
0x1800931d3  call    cs:__imp_GetLastError
0x1800931d9  mov     edi, 3
0x1800931de  lea     r9, aFailedToGetPro_11; "Failed to get proxy from current user: "...
0x1800931e5  lea     rdx, aWindowsCompatA_275; "Windows::Compat::Appraiser::Utilities::"...
0x1800931ec  mov     dword ptr [rsp+270h+var_250], eax
0x1800931f0  mov     ecx, edi
0x1800931f2  mov     r8d, 0BB0h
0x1800931f8  call    AslLogCallPrintf
0x1800931fd  call    cs:__imp_GetLastError
0x180093203  xor     r13d, r13d
0x180093206  mov     ebx, eax
0x180093208  test    eax, eax
0x18009320a  jle     short loc_180093212
0x18009320c  movzx   ebx, ax
0x18009320f  or      ebx, r12d
0x180093212  test    ebx, ebx
0x180093214  cmovns  ebx, esi
0x180093217  call    cs:__imp_GetLastError
0x18009321d  mov     dword ptr [rsp+270h+var_240], eax; char *
0x180093221  mov     edx, 0BB1h; bool
0x180093226  lea     rax, aFailedToGetPro_11; "Failed to get proxy from current user: "...
0x18009322d  mov     qword ptr [rsp+270h+var_248], rax; int
0x180093232  lea     r9, aWindowsCompatA_275; "Windows::Compat::Appraiser::Utilities::"...
0x180093239  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180093240  mov     dword ptr [rsp+270h+var_250], ebx; char *
0x180093244  mov     ecx, 1; this
0x180093249  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18009324e  jmp     loc_1800935D4
0x180093253  mov     rbx, rdi
0x180093256  mov     eax, edi
0x180093258  mov     edi, 3
0x18009325d  test    eax, eax
0x18009325f  jnz     loc_180093445
0x180093265  test    rbx, rbx
0x180093268  jz      short loc_180093282
0x18009326a  call    cs:__imp_GetLastError
0x180093270  cmp     eax, 2EEFh
0x180093275  jnz     loc_180093310
0x18009327b  mov     [rbp+170h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x180093282  mov     rax, [rbp+170h+var_1D8+8]
0x180093286  mov     [rbp+170h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x18009328a  test    rax, rax
0x18009328d  jnz     short loc_18009329B
0x18009328f  mov     [rbp+170h+pAutoProxyOptions.dwFlags], 1
0x180093296  mov     [rbp+170h+pAutoProxyOptions.dwAutoDetectFlags], edi
0x180093299  jmp     short loc_1800932A3
0x18009329b  mov     qword ptr [rbp+170h+pAutoProxyOptions.dwFlags], 2
0x1800932a3  test    r14b, r14b
0x1800932a6  jz      short loc_1800932DA
0x1800932a8  mov     rcx, [rsp+270h+hMem+8]; hMem
0x1800932ad  test    rcx, rcx
0x1800932b0  jz      short loc_1800932C1
0x1800932b2  call    cs:__imp_GlobalFree
0x1800932b8  mov     [rsp+270h+hMem+8], 0
0x1800932c1  mov     rcx, [rsp+270h+var_1F8]; hMem
0x1800932c6  test    rcx, rcx
0x1800932c9  jz      short loc_1800932DA
0x1800932cb  call    cs:__imp_GlobalFree
0x1800932d1  mov     [rsp+270h+var_1F8], 0
0x1800932da  mov     rax, [rbp+170h+var_1E8]
0x1800932de  lea     r9, [rsp+270h+hMem]; pProxyInfo
0x1800932e3  lea     r8, [rbp+170h+pAutoProxyOptions]; pAutoProxyOptions
0x1800932e7  mov     rdx, r13; lpcwszUrl
0x1800932ea  mov     rcx, [rax]; hSession
0x1800932ed  call    cs:__imp_WinHttpGetProxyForUrl
0x1800932f3  inc     rbx
0x1800932f6  mov     r14b, 1
0x1800932f9  cmp     rbx, 2
0x1800932fd  jb      loc_18009325D
0x180093303  xor     r13d, r13d
0x180093306  test    eax, eax
0x180093308  jnz     loc_180093448
0x18009330e  jmp     short loc_180093313
0x180093310  xor     r13d, r13d
0x180093313  mov     rax, [rbp+170h+var_1C8]
0x180093317  test    rax, rax
0x18009331a  jz      short loc_18009337F
0x18009331c  cmp     [rax], r13w
0x180093320  jz      short loc_18009337F
0x180093322  mov     ecx, 3Ah ; ':'
0x180093327  cmp     [rax], cx
0x18009332a  jnz     short loc_180093333
0x18009332c  cmp     [rax+2], r13w
0x180093331  jz      short loc_18009337F
0x180093333  test    r14b, r14b
0x180093336  jz      short loc_180093368
0x180093338  mov     rcx, [rsp+270h+hMem+8]; hMem
0x18009333d  test    rcx, rcx
0x180093340  jz      short loc_180093351
0x180093342  call    cs:__imp_GlobalFree
0x180093348  mov     rax, [rbp+170h+var_1C8]
0x18009334c  mov     [rsp+270h+hMem+8], r13
0x180093351  mov     rcx, [rsp+270h+var_1F8]; hMem
0x180093356  test    rcx, rcx
0x180093359  jz      short loc_180093365
0x18009335b  call    cs:__imp_GlobalFree
0x180093361  mov     rax, [rbp+170h+var_1C8]
0x180093365  mov     r14b, r13b
0x180093368  mov     [rsp+270h+hMem+8], rax
0x18009336d  mov     rax, [rbp+170h+var_1C8+8]
0x180093371  mov     [rsp+270h+var_1F8], rax
0x180093376  mov     dword ptr [rsp+270h+hMem], edi
0x18009337a  jmp     loc_180093448
0x18009337f  test    r14b, r14b
0x180093382  jz      short loc_1800933B1
0x180093384  mov     rcx, [rsp+270h+hMem+8]; hMem
0x180093389  test    rcx, rcx
0x18009338c  jz      short loc_180093399
0x18009338e  call    cs:__imp_GlobalFree
0x180093394  mov     [rsp+270h+hMem+8], r13
0x180093399  mov     rcx, [rsp+270h+var_1F8]; hMem
0x18009339e  test    rcx, rcx
0x1800933a1  jz      short loc_1800933AE
0x1800933a3  call    cs:__imp_GlobalFree
0x1800933a9  mov     [rsp+270h+var_1F8], r13
0x1800933ae  mov     r14b, r13b
0x1800933b1  lea     rcx, [rsp+270h+hMem]; pProxyInfo
0x1800933b6  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800933bc  test    eax, eax
0x1800933be  jnz     short loc_180093417
0x1800933c0  call    cs:__imp_GetLastError
0x1800933c6  lea     r9, aFailedToGetPro_4; "Failed to get proxy from global default"...
0x1800933cd  mov     r8d, 0BECh
0x1800933d3  lea     rdx, aWindowsCompatA_275; "Windows::Compat::Appraiser::Utilities::"...
0x1800933da  mov     dword ptr [rsp+270h+var_250], eax
0x1800933de  mov     ecx, edi
0x1800933e0  call    AslLogCallPrintf
0x1800933e5  call    cs:__imp_GetLastError
0x1800933eb  mov     ebx, eax
0x1800933ed  test    eax, eax
0x1800933ef  jle     short loc_1800933F7
0x1800933f1  movzx   ebx, ax
0x1800933f4  or      ebx, r12d
0x1800933f7  test    ebx, ebx
0x1800933f9  cmovns  ebx, esi
0x1800933fc  call    cs:__imp_GetLastError
0x180093402  mov     dword ptr [rsp+270h+var_240], eax
0x180093406  mov     edx, 0BEDh
0x18009340b  lea     rax, aFailedToGetPro_4; "Failed to get proxy from global default"...
  ... truncated ...
```
