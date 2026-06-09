# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync(winrt::hstring const &)

- ea: `0x18002a6f0`
- end: `0x18002afe9`
- name: `?RemoveVirtualPrinterForAllUsersAsync@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@SA_KAEBUhstring@8@@Z`
- size: `2297`
- prototype: `unsigned __int64 __fastcall(const struct winrt::hstring *this)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d770`

## callees

- `0x180002d40`
- `0x180005fd8`
- `0x180008838`
- `0x18000f760`
- `0x18000f8a8`
- `0x18000fa2c`
- `0x180012498`
- `0x18001cfb4`
- `0x18001d0a0`
- `0x18001d1dc`
- `0x1800230fc`
- `0x180023a20`
- `0x180024314`
- `0x180026248`
- `0x1800264dc`
- `0x180027060`
- `0x180027120`
- `0x180027160`
- `0x1800273f0`
- `0x1800284bc`
- `0x180029108`
- `0x18002a034`
- `0x18002a6f0`
- `0x18002aff0`
- `0x18002b0e4`
- `0x18002b44c`
- `0x18002b4d0`
- `0x18002f194`
- `0x1800360f4`
- `0x180037c78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7b8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002aefa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002aefa`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18002af28`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18002af28`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18002a85d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18002a85d`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18002a7a2`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18002a805`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18002a7a2`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18002a805`

## string_xrefs

- `0x18002a737`: `Checking access`
- `0x18002a87a`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002af7d`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002af91`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002afa6`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002afbe`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002afd6`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002a73e`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync`
- `0x18002aa7e`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync`
- `0x18002aad6`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync`
- `0x18002ab06`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync`
- `0x18002ac70`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync`
- `0x18002adfa`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync`
- `0x18002aa77`: `Remove for sessionId 0x%x`
- `0x18002a8a5`: `Remove for %d existing users`
- `0x18002aacf`: `Failed to get user SID for sessionId: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinterForAllUsersAsync(
        const struct winrt::hstring *this)
{
  winrt::hstring *v1; // r13
  unsigned __int64 v2; // r14
  const char *v3; // r9
  const char *v4; // r9
  LPBYTE v5; // r12
  unsigned int v6; // eax
  __m128i si128; // xmm6
  HKEY v8; // rdi
  const unsigned __int16 *v9; // rax
  __int64 v10; // rbx
  int v11; // r8d
  int v12; // r9d
  __int64 StringValue; // rax
  char v14; // al
  DWORD i; // r15d
  __int64 UserSidFromSessionId; // rax
  _QWORD *j; // rbx
  _QWORD *v18; // r13
  __int128 *v19; // rdx
  __int64 v20; // r12
  _QWORD *v21; // rdx
  __int64 v22; // rax
  __int128 *v23; // rdx
  __int64 v24; // r12
  _QWORD *v25; // rdx
  __int64 v26; // rax
  __int128 *v27; // r9
  _QWORD *v28; // r8
  __int64 v29; // r8
  const WCHAR *v30; // rax
  const char *v31; // r9
  unsigned __int64 result; // rax
  int cbBuf; // [rsp+20h] [rbp-458h]
  DWORD cbBufa; // [rsp+20h] [rbp-458h]
  const char *pcbNeeded; // [rsp+28h] [rbp-450h]
  char v36[8]; // [rsp+40h] [rbp-438h] BYREF
  DWORD pcReturned; // [rsp+48h] [rbp-430h] BYREF
  DWORD pCount; // [rsp+4Ch] [rbp-42Ch] BYREF
  int v39[2]; // [rsp+50h] [rbp-428h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+58h] [rbp-420h] BYREF
  HKEY v41; // [rsp+60h] [rbp-418h] BYREF
  LPBYTE v42; // [rsp+68h] [rbp-410h]
  const struct winrt::hstring *v43; // [rsp+70h] [rbp-408h]
  _QWORD v44[2]; // [rsp+78h] [rbp-400h] BYREF
  __int64 v45; // [rsp+88h] [rbp-3F0h] BYREF
  LPBYTE pPrinterEnum[4]; // [rsp+98h] [rbp-3E0h] BYREF
  char v47; // [rsp+B8h] [rbp-3C0h]
  _BYTE v48[32]; // [rsp+C0h] [rbp-3B8h] BYREF
  _BYTE v49[32]; // [rsp+E0h] [rbp-398h] BYREF
  __int128 v50; // [rsp+100h] [rbp-378h] BYREF
  __int64 v51; // [rsp+110h] [rbp-368h]
  int v52[8]; // [rsp+120h] [rbp-358h] BYREF
  _OWORD v53[2]; // [rsp+140h] [rbp-338h] BYREF
  __int128 v54; // [rsp+160h] [rbp-318h]
  __m128i v55; // [rsp+170h] [rbp-308h]
  __int128 v56; // [rsp+180h] [rbp-2F8h] BYREF
  __m128i v57; // [rsp+190h] [rbp-2E8h]
  __int128 v58; // [rsp+1A0h] [rbp-2D8h]
  __m128i v59; // [rsp+1B0h] [rbp-2C8h]
  __int128 v60; // [rsp+1C0h] [rbp-2B8h] BYREF
  __int64 v61; // [rsp+1D0h] [rbp-2A8h]
  unsigned __int64 v62; // [rsp+1D8h] [rbp-2A0h]
  _OWORD v63[2]; // [rsp+1E0h] [rbp-298h] BYREF
  __int128 v64; // [rsp+200h] [rbp-278h]
  __m128i v65; // [rsp+210h] [rbp-268h]
  _OWORD v66[2]; // [rsp+220h] [rbp-258h] BYREF
  __int128 v67; // [rsp+240h] [rbp-238h]
  __m128i v68; // [rsp+250h] [rbp-228h]
  __int128 v69; // [rsp+260h] [rbp-218h]
  __m128i v70; // [rsp+270h] [rbp-208h]
  __int128 v71; // [rsp+280h] [rbp-1F8h]
  __m128i v72; // [rsp+290h] [rbp-1E8h]
  __int128 v73; // [rsp+2A0h] [rbp-1D8h]
  __m128i v74; // [rsp+2B0h] [rbp-1C8h]
  __int128 v75; // [rsp+2C0h] [rbp-1B8h]
  __m128i v76; // [rsp+2D0h] [rbp-1A8h]
  __int128 v77; // [rsp+2E0h] [rbp-198h]
  __m128i v78; // [rsp+2F0h] [rbp-188h]
  __int128 v79; // [rsp+300h] [rbp-178h]
  __m128i v80; // [rsp+310h] [rbp-168h]
  __int128 v81; // [rsp+320h] [rbp-158h]
  __m128i v82; // [rsp+330h] [rbp-148h]
  _BYTE v83[16]; // [rsp+340h] [rbp-138h] BYREF
  _BYTE v84[32]; // [rsp+350h] [rbp-128h] BYREF
  _BYTE v85[32]; // [rsp+370h] [rbp-108h] BYREF
  _BYTE v86[160]; // [rsp+390h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+0h]

  v1 = this;
  v43 = this;
  try
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage();
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinterForAllUsersAsync",
      L"Checking access");
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(
      0x3000u,
      0,
      0,
      0);
    v2 = 0;
    *(_DWORD *)&v36[4] = 0;
    pcReturned = 0;
    if ( EnumPrintersW(0x8000000A, 0, 5u, 0, 0, (LPDWORD)&v36[4], &pcReturned) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)0x8000FFFFLL,
        cbBuf);
    if ( GetLastError() != 122 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        v3);
    std::vector<unsigned char>::vector<unsigned char>(pPrinterEnum, *(unsigned int *)&v36[4]);
    if ( !EnumPrintersW(0x8000000A, 0, 5u, pPrinterEnum[0], *(DWORD *)&v36[4], (LPDWORD)&v36[4], &pcReturned) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        v4);
    v5 = pPrinterEnum[0];
    v42 = pPrinterEnum[0];
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinterForAllUsersAsync",
      L"Found %d printers",
      pcReturned);
    ppSessionInfo = 0;
    pCount = 0;
    v6 = WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)v6,
      (int)"Enumerate sessions failed!",
      pcbNeeded);
    pPrinterEnum[3] = (LPBYTE)&ppSessionInfo;
    v47 = 1;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinterForAllUsersAsync",
      L"Remove for %d existing users",
      pCount);
    v53[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v53[1] = si128;
    LOWORD(v53[0]) = 0;
    v54 = 0;
    v55 = si128;
    LOWORD(v54) = 0;
    v56 = 0;
    v57 = si128;
    LOWORD(v56) = 0;
    v58 = 0;
    v59 = si128;
    LOWORD(v58) = 0;
    v60 = 0;
    v61 = 0;
    v62 = 7;
    LOWORD(v60) = 0;
    std::wstring::wstring(
      &v50,
      L"System\\CurrentControlSet\\Control\\Print\\Actions\\PerUserLogon\\AllUserVirtualPrinters");
    *(_QWORD *)v39 = -2147483646;
    v8 = (HKEY)PrintCore::RegHelpers::OpenKey(v39, &v50);
    v41 = v8;
    std::wstring::_Tidy_deallocate(&v50);
    if ( !v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)0x80070490LL,
        cbBufa);
    v36[0] = 0;
    v9 = winrt::hstring::c_str(v1);
    std::wstring::wstring(v84, v9);
    *(_QWORD *)v39 = v8;
    v10 = PrintCore::RegHelpers::OpenKey(v39, v84);
    v44[0] = v10;
    std::wstring::_Tidy_deallocate(v84);
    if ( !v10
      || (*(_QWORD *)v39 = v10,
          StringValue = PrintCore::RegHelpers::GetStringValue((int)v52, (int)v39, v11, v12, cbBufa, (__int64)v36),
          std::wstring::operator=(&v56, StringValue),
          std::wstring::_Tidy_deallocate(v52),
          v14 = 0,
          !v36[0]) )
    {
      v14 = 1;
    }
    if ( v14 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)0x80070490LL,
        cbBufa);
    for ( i = 0; i < pCount; ++i )
    {
      if ( ppSessionInfo[i].SessionId )
      {
        PrintScanBrokerTelemetry::WriteDbgTraceInfo(
          "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::"
          "RemoveVirtualPrinterForAllUsersAsync",
          L"Remove for sessionId 0x%x");
        UserSidFromSessionId = PrintCore::UserImpersonationHelpers::TryGetUserSidFromSessionId(
                                 v52,
                                 ppSessionInfo[i].SessionId);
        std::wstring::operator=(&v60, UserSidFromSessionId);
        std::wstring::_Tidy_deallocate(v52);
        if ( v61 )
        {
          while ( v2 < pcReturned )
          {
            PrintScanBrokerTelemetry::WriteDbgTraceInfo(
              "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBrok"
              "er::RemoveVirtualPrinterForAllUsersAsync",
              L"Checking printer %ws",
              *(_QWORD *)&v5[32 * v2]);
            v63[0] = 0;
            v63[1] = si128;
            LOWORD(v63[0]) = 0;
            v64 = 0;
            v65 = si128;
            LOWORD(v64) = 0;
            v66[0] = 0;
            v66[1] = si128;
            LOWORD(v66[0]) = 0;
            v67 = 0;
            v68 = si128;
            LOWORD(v67) = 0;
            v69 = 0;
            v70 = si128;
            LOWORD(v69) = 0;
            v71 = 0;
            v72 = si128;
            LOWORD(v71) = 0;
            v73 = 0;
            v74 = si128;
            LOWORD(v73) = 0;
            v75 = 0;
            v76 = si128;
            LOWORD(v75) = 0;
            v77 = 0;
            v78 = si128;
            LOWORD(v77) = 0;
            v79 = 0;
            v80 = si128;
            LOWORD(v79) = 0;
            v81 = 0;
            v82 = si128;
            LOWORD(v81) = 0;
            std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v83);
            winrt::hstring::operator std::basic_string_view<unsigned short>(v1, &v45);
            std::wstring::_Assign<unsigned short>(v66, v45);
            PrintScanBrokerTelemetry::WriteDbgTraceInfo(
              "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBrok"
              "er::RemoveVirtualPrinterForAllUsersAsync",
              L"Found printer %ws",
              *(_QWORD *)&v5[32 * v2]);
            std::wstring::wstring(v52, L",");
            std::wstring::wstring(v85, *(_QWORD *)&v5[32 * v2 + 8]);
            PrintCore::StringHelpers::SplitString(&v50, v85, v52);
            std::wstring::_Tidy_deallocate(v85);
            std::wstring::_Tidy_deallocate(v52);
            v18 = (_QWORD *)*((_QWORD *)&v50 + 1);
            for ( j = (_QWORD *)v50; j != v18; j += 4 )
            {
              *(_QWORD *)v39 = v48;
              v19 = &v60;
              if ( v62 > 7 )
                v19 = (__int128 *)v60;
              v20 = std::wstring::wstring(v48, v19);
              if ( j[3] <= 7u )
                v21 = j;
              else
                v21 = (_QWORD *)*j;
              v22 = std::wstring::wstring(v49, v21);
              if ( (unsigned __int8)PrintCore::StringHelpers::IContains(v22, v20) )
              {
                v44[1] = v49;
                v23 = &v56;
                if ( v57.m128i_i64[1] > 7uLL )
                  v23 = (__int128 *)v56;
                v24 = std::wstring::wstring(v49, v23);
                v25 = j[3] <= 7u ? j : (_QWORD *)*j;
                v26 = std::wstring::wstring(v48, v25);
                if ( (unsigned __int8)PrintCore::StringHelpers::IContains(v26, v24) )
                {
                  v27 = &v60;
                  if ( v62 > 7 )
                    v27 = (__int128 *)v60;
                  if ( j[3] <= 7u )
                    v28 = j;
                  else
                    v28 = (_QWORD *)*j;
                  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
                    "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstall"
                    "erBroker::RemoveVirtualPrinterForAllUsersAsync",
                    L"Removing port %ws for user %ws",
                    v28,
                    v27);
                  if ( j[3] > 7u )
                    j = (_QWORD *)*j;
                  v29 = -1;
                  do
                    ++v29;
                  while ( *((_WORD *)j + v29) );
                  std::wstring::_Assign<unsigned short>(v63, j);
                  VirtualMon::VirtualPrinterInstaller::VirtualPrinterInstaller(
                    (VirtualMon::VirtualPrinterInstaller *)v86,
                    (const struct VirtualMon::VirtualPrinterAppInfo *)v53);
                  VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(
                    (VirtualMon::VirtualPrinterInstaller *)v86,
                    (const struct VirtualMon::VirtualPrinterInfo *)v63);
                  VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo((VirtualMon::VirtualPrinterAppInfo *)v86);
                  break;
                }
              }
            }
            if ( (_QWORD)v50 )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v50, *((_QWORD *)&v50 + 1));
              std::_Deallocate<16>(v50, (v51 - v50) & 0xFFFFFFFFFFFFFFE0uLL);
              v50 = 0;
              v51 = 0;
            }
            VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo((VirtualMon::VirtualPrinterInfo *)v63);
            ++v2;
            v5 = v42;
            v1 = v43;
          }
          v2 = 0;
        }
        else
        {
          PrintScanBrokerTelemetry::WriteDbgTraceWarning(
            "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker"
            "::RemoveVirtualPrinterForAllUsersAsync",
            L"Failed to get user SID for sessionId: 0x%x",
            ppSessionInfo[i].SessionId);
        }
      }
    }
    v30 = winrt::hstring::c_str(v1);
    RegDeleteKeyW(v8, v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v44);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
    VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo((VirtualMon::VirtualPrinterAppInfo *)v53);
    WTSFreeMemory(ppSessionInfo);
    std::vector<unsigned char>::_Tidy(pPrinterEnum);
    result = 0;
  }
  catch ( ... )
  {
    return (int)wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x12F,
                  (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
                  v31);
  }
  return result;
}

```

## disassembly

```asm
0x18002a6f0  mov     rax, rsp
0x18002a6f3  mov     [rax+10h], rbx
0x18002a6f7  mov     [rax+18h], rsi
0x18002a6fb  push    rdi
0x18002a6fc  push    r12
0x18002a6fe  push    r13
0x18002a700  push    r14
0x18002a702  push    r15
0x18002a704  sub     rsp, 450h
0x18002a70b  movaps  xmmword ptr [rax-38h], xmm6
0x18002a70f  mov     rax, cs:__security_cookie
0x18002a716  xor     rax, rsp
0x18002a719  mov     [rsp+478h+var_48], rax
0x18002a721  mov     r13, rcx
0x18002a724  mov     [rsp+478h+var_408], rcx
0x18002a729  mov     dl, 1
0x18002a72b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements> `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl(void)'::`2'::impl
0x18002a732  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a737  lea     rdx, aCheckingAccess; "Checking access"
0x18002a73e  lea     rdi, aWinrtWindowsGr_5; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a745  mov     rcx, rdi; char *
0x18002a748  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a74d  xor     r9d, r9d; unsigned __int16 *
0x18002a750  xor     r8d, r8d; unsigned __int16 *
0x18002a753  xor     edx, edx; unsigned __int16 *
0x18002a755  mov     ecx, 3000h; unsigned int
0x18002a75a  call    ?VirtualPrinterInstallAccessCheck@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CAXKPEBG00@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(ulong,ushort const *,ushort const *,ushort const *)
0x18002a75f  xor     r14d, r14d
0x18002a762  mov     dword ptr [rsp+478h+var_438+4], r14d
0x18002a767  mov     [rsp+478h+var_430], r14d
0x18002a76c  mov     rbx, [rsp+478h]
0x18002a774  lea     rax, [rsp+478h+var_430]
0x18002a779  mov     [rsp+478h+pcReturned], rax; pcReturned
0x18002a77e  lea     rax, [rsp+478h+var_438+4]
0x18002a783  mov     [rsp+478h+pcbNeeded], rax; pcbNeeded
0x18002a788  mov     [rsp+478h+cbBuf], r14d; int
0x18002a78d  xor     r9d, r9d; pPrinterEnum
0x18002a790  lea     esi, [r14+5]
0x18002a794  mov     r8d, esi; Level
0x18002a797  xor     edx, edx; Name
0x18002a799  mov     r15d, 8000000Ah
0x18002a79f  mov     ecx, r15d; Flags
0x18002a7a2  call    cs:__imp_EnumPrintersW
0x18002a7a8  test    eax, eax
0x18002a7aa  jnz     loc_18002AF77
0x18002a7b0  mov     rbx, [rsp+478h]
0x18002a7b8  call    cs:__imp_GetLastError
0x18002a7be  cmp     eax, 7Ah ; 'z'
0x18002a7c1  jnz     loc_18002AF91
0x18002a7c7  mov     edx, dword ptr [rsp+478h+var_438+4]
0x18002a7cb  lea     rcx, [rsp+478h+pPrinterEnum]
0x18002a7d3  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002a7d8  nop
0x18002a7d9  mov     eax, dword ptr [rsp+478h+var_438+4]
0x18002a7dd  lea     rdx, [rsp+478h+var_430]
0x18002a7e2  mov     [rsp+478h+pcReturned], rdx; pcReturned
0x18002a7e7  lea     rdx, [rsp+478h+var_438+4]
0x18002a7ec  mov     [rsp+478h+pcbNeeded], rdx; char *
0x18002a7f1  mov     [rsp+478h+cbBuf], eax; cbBuf
0x18002a7f5  mov     r9, [rsp+478h+pPrinterEnum]; pPrinterEnum
0x18002a7fd  mov     r8d, esi; Level
0x18002a800  xor     edx, edx; Name
0x18002a802  mov     ecx, r15d; Flags
0x18002a805  call    cs:__imp_EnumPrintersW
0x18002a80b  mov     rcx, [rsp+478h]; this
0x18002a813  test    eax, eax
0x18002a815  jz      loc_18002AFA6
0x18002a81b  mov     r12, [rsp+478h+pPrinterEnum]
0x18002a823  mov     [rsp+478h+var_410], r12
0x18002a828  mov     r8d, [rsp+478h+var_430]
0x18002a82d  lea     rdx, aFoundDPrinters; "Found %d printers"
0x18002a834  mov     rcx, rdi; char *
0x18002a837  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a83c  mov     [rsp+478h+ppSessionInfo], r14
0x18002a841  mov     [rsp+478h+pCount], r14d
0x18002a846  lea     rax, [rsp+478h+pCount]
0x18002a84b  mov     qword ptr [rsp+478h+cbBuf], rax; pCount
0x18002a850  lea     r9, [rsp+478h+ppSessionInfo]; ppSessionInfo
0x18002a855  xor     edx, edx; Reserved
0x18002a857  xor     ecx, ecx; hServer
0x18002a859  lea     r8d, [rdx+1]; Version
0x18002a85d  call    cs:__imp_WTSEnumerateSessionsW
0x18002a863  mov     rcx, [rsp+478h]; this
0x18002a86b  lea     rdx, aEnumerateSessi; "Enumerate sessions failed!"
0x18002a872  mov     qword ptr [rsp+478h+cbBuf], rdx; int
0x18002a877  mov     r9d, eax; char *
0x18002a87a  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002a881  mov     edx, 0ECh; void *
0x18002a886  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18002a88b  lea     rsi, [rsp+478h+ppSessionInfo]
0x18002a890  mov     [rsp+478h+var_3C8], rsi
0x18002a898  mov     [rsp+478h+var_3C0], 1
0x18002a8a0  mov     r8d, [rsp+478h+pCount]
0x18002a8a5  lea     rdx, aRemoveForDExis; "Remove for %d existing users"
0x18002a8ac  mov     rcx, rdi; char *
0x18002a8af  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a8b4  xorps   xmm0, xmm0
0x18002a8b7  movups  [rsp+478h+var_338], xmm0
0x18002a8bf  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002a8c7  movdqa  [rsp+478h+var_328], xmm6
0x18002a8d0  mov     word ptr [rsp+478h+var_338], r14w
0x18002a8d9  movups  [rsp+478h+var_318], xmm0
0x18002a8e1  movdqa  [rsp+478h+var_308], xmm6
0x18002a8ea  mov     word ptr [rsp+478h+var_318], r14w
0x18002a8f3  movups  [rsp+478h+var_2F8], xmm0
0x18002a8fb  movdqa  [rsp+478h+var_2E8], xmm6
0x18002a904  mov     word ptr [rsp+478h+var_2F8], r14w
0x18002a90d  movups  [rsp+478h+var_2D8], xmm0
0x18002a915  movdqa  [rsp+478h+var_2C8], xmm6
0x18002a91e  mov     word ptr [rsp+478h+var_2D8], r14w
0x18002a927  movups  [rsp+478h+var_2B8], xmm0
0x18002a92f  mov     [rsp+478h+var_2A8], r14
0x18002a937  mov     [rsp+478h+var_2A0], 7
0x18002a943  mov     word ptr [rsp+478h+var_2B8], r14w
0x18002a94c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pri"...
0x18002a953  lea     rcx, [rsp+478h+var_378]
0x18002a95b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a960  nop
0x18002a961  mov     qword ptr [rsp+478h+var_428], 0FFFFFFFF80000002h
0x18002a96a  lea     rdx, [rsp+478h+var_378]
0x18002a972  lea     rcx, [rsp+478h+var_428]
0x18002a977  call    ?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x18002a97c  mov     rdi, rax
0x18002a97f  mov     [rsp+478h+var_418], rax
0x18002a984  lea     rcx, [rsp+478h+var_378]
0x18002a98c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a991  test    rdi, rdi
0x18002a994  setz    al
0x18002a997  mov     rcx, [rsp+478h]; this
0x18002a99f  test    al, al
0x18002a9a1  jnz     loc_18002AFB8
0x18002a9a7  mov     [rsp+478h+var_438], r14b
0x18002a9ac  mov     rcx, r13; this
0x18002a9af  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a9b4  mov     rdx, rax
0x18002a9b7  lea     rcx, [rsp+478h+var_128]
0x18002a9bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a9c4  nop
0x18002a9c5  mov     qword ptr [rsp+478h+var_428], rdi
0x18002a9ca  lea     rdx, [rsp+478h+var_128]
0x18002a9d2  lea     rcx, [rsp+478h+var_428]
0x18002a9d7  call    ?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x18002a9dc  mov     rbx, rax
0x18002a9df  mov     [rsp+478h+var_400], rax
0x18002a9e4  lea     rcx, [rsp+478h+var_128]
0x18002a9ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9f1  test    rbx, rbx
0x18002a9f4  jz      short loc_18002AA3E
0x18002a9f6  mov     qword ptr [rsp+478h+var_428], rbx
0x18002a9fb  lea     rax, [rsp+478h+var_438]
0x18002aa00  mov     [rsp+478h+pcbNeeded], rax; __int64
0x18002aa05  lea     rdx, [rsp+478h+var_428]; int
0x18002aa0a  lea     rcx, [rsp+478h+var_358]; int
0x18002aa12  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x18002aa17  mov     rdx, rax
0x18002aa1a  lea     rcx, [rsp+478h+var_2F8]
0x18002aa22  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002aa27  lea     rcx, [rsp+478h+var_358]
0x18002aa2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aa34  cmp     [rsp+478h+var_438], r14b
0x18002aa39  mov     al, r14b
0x18002aa3c  jnz     short loc_18002AA40
0x18002aa3e  mov     al, 1
0x18002aa40  mov     rcx, [rsp+478h]; this
0x18002aa48  test    al, al
0x18002aa4a  jnz     loc_18002AFD0
0x18002aa50  mov     r15d, r14d
0x18002aa53  cmp     r15d, [rsp+478h+pCount]
0x18002aa58  jnb     loc_18002AEE7
0x18002aa5e  mov     eax, r15d
0x18002aa61  lea     rbx, [rax+rax*2]
0x18002aa65  mov     rax, [rsp+478h+ppSessionInfo]
0x18002aa6a  mov     r8d, [rax+rbx*8]
0x18002aa6e  test    r8d, r8d
0x18002aa71  jz      loc_18002AEDF
0x18002aa77  lea     rdx, aRemoveForSessi; "Remove for sessionId 0x%x"
0x18002aa7e  lea     rcx, aWinrtWindowsGr_5; "winrt::Windows::Graphics::Internal::Pri"...
0x18002aa85  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002aa8a  mov     rdx, [rsp+478h+ppSessionInfo]
0x18002aa8f  mov     edx, [rdx+rbx*8]
0x18002aa92  lea     rcx, [rsp+478h+var_358]
0x18002aa9a  call    ?TryGetUserSidFromSessionId@UserImpersonationHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::UserImpersonationHelpers::TryGetUserSidFromSessionId(ulong)
0x18002aa9f  mov     rdx, rax
0x18002aaa2  lea     rcx, [rsp+478h+var_2B8]
0x18002aaaa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002aaaf  lea     rcx, [rsp+478h+var_358]
0x18002aab7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aabc  cmp     [rsp+478h+var_2A8], r14
0x18002aac4  jnz     short loc_18002AAE7
0x18002aac6  mov     r8, [rsp+478h+ppSessionInfo]
0x18002aacb  mov     r8d, [r8+rbx*8]
0x18002aacf  lea     rdx, aFailedToGetUse_1; "Failed to get user SID for sessionId: 0"...
0x18002aad6  lea     rcx, aWinrtWindowsGr_5; "winrt::Windows::Graphics::Internal::Pri"...
0x18002aadd  call    ?WriteDbgTraceWarning@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002aae2  jmp     loc_18002AEDF
0x18002aae7  mov     eax, [rsp+478h+var_430]
0x18002aaeb  cmp     r14, rax
0x18002aaee  jnb     loc_18002AEDC
0x18002aaf4  mov     rbx, r14
0x18002aaf7  shl     rbx, 5
0x18002aafb  mov     r8, [rbx+r12]
0x18002aaff  lea     rdx, aCheckingPrinte; "Checking printer %ws"
0x18002ab06  lea     rcx, aWinrtWindowsGr_5; "winrt::Windows::Graphics::Internal::Pri"...
0x18002ab0d  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002ab12  xorps   xmm0, xmm0
0x18002ab15  movups  [rsp+478h+var_298], xmm0
0x18002ab1d  movdqa  [rsp+478h+var_288], xmm6
0x18002ab26  xor     ecx, ecx
0x18002ab28  mov     word ptr [rsp+478h+var_298], cx
0x18002ab30  movups  [rsp+478h+var_278], xmm0
0x18002ab38  movdqa  [rsp+478h+var_268], xmm6
0x18002ab41  mov     word ptr [rsp+478h+var_278], cx
0x18002ab49  movups  [rsp+478h+var_258], xmm0
0x18002ab51  movdqa  [rsp+478h+var_248], xmm6
0x18002ab5a  mov     word ptr [rsp+478h+var_258], cx
0x18002ab62  movups  [rsp+478h+var_238], xmm0
0x18002ab6a  movdqa  [rsp+478h+var_228], xmm6
0x18002ab73  mov     word ptr [rsp+478h+var_238], cx
0x18002ab7b  movups  [rsp+478h+var_218], xmm0
0x18002ab83  movdqa  [rsp+478h+var_208], xmm6
0x18002ab8c  mov     word ptr [rsp+478h+var_218], cx
0x18002ab94  movups  [rsp+478h+var_1F8], xmm0
0x18002ab9c  movdqa  [rsp+478h+var_1E8], xmm6
0x18002aba5  mov     word ptr [rsp+478h+var_1F8], cx
0x18002abad  movups  [rsp+478h+var_1D8], xmm0
0x18002abb5  movdqa  [rsp+478h+var_1C8], xmm6
0x18002abbe  mov     word ptr [rsp+478h+var_1D8], cx
0x18002abc6  movups  [rsp+478h+var_1B8], xmm0
0x18002abce  movdqa  [rsp+478h+var_1A8], xmm6
0x18002abd7  mov     word ptr [rsp+478h+var_1B8], cx
0x18002abdf  movups  [rsp+478h+var_198], xmm0
0x18002abe7  movdqa  [rsp+478h+var_188], xmm6
0x18002abf0  mov     word ptr [rsp+478h+var_198], cx
0x18002abf8  movups  [rsp+478h+var_178], xmm0
0x18002ac00  movdqa  [rsp+478h+var_168], xmm6
0x18002ac09  mov     word ptr [rsp+478h+var_178], cx
0x18002ac11  movups  [rsp+478h+var_158], xmm0
0x18002ac19  movdqa  [rsp+478h+var_148], xmm6
0x18002ac22  mov     word ptr [rsp+478h+var_158], cx
0x18002ac2a  lea     rcx, [rsp+478h+var_138]
0x18002ac32  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18002ac37  nop
0x18002ac38  lea     rdx, [rsp+478h+var_3F0]
0x18002ac40  mov     rcx, r13
0x18002ac43  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002ac48  mov     r8, [rsp+478h+var_3E8]
0x18002ac50  mov     rdx, [rsp+478h+var_3F0]
0x18002ac58  lea     rcx, [rsp+478h+var_258]
0x18002ac60  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002ac65  mov     r8, [rbx+r12]
0x18002ac69  lea     rdx, aFoundPrinterWs; "Found printer %ws"
0x18002ac70  lea     rcx, aWinrtWindowsGr_5; "winrt::Windows::Graphics::Internal::Pri"...
0x18002ac77  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002ac7c  lea     rdx, asc_18004D314; ","
0x18002ac83  lea     rcx, [rsp+478h+var_358]
0x18002ac8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ac90  nop
0x18002ac91  mov     rdx, [rbx+r12+8]
0x18002ac96  lea     rcx, [rsp+478h+var_108]
0x18002ac9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aca3  nop
0x18002aca4  lea     r8, [rsp+478h+var_358]
0x18002acac  lea     rdx, [rsp+478h+var_108]
0x18002acb4  lea     rcx, [rsp+478h+var_378]
0x18002acbc  call    ?SplitString@StringHelpers@PrintCore@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0@Z; PrintCore::StringHelpers::SplitString(std::wstring const &,std::wstring const &)
0x18002acc1  nop
0x18002acc2  lea     rcx, [rsp+478h+var_108]
0x18002acca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002accf  nop
0x18002acd0  lea     rcx, [rsp+478h+var_358]
0x18002acd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002acdd  mov     rbx, qword ptr [rsp+478h+var_378]
0x18002ace5  mov     r13, qword ptr [rsp+478h+var_378+8]
0x18002aced  cmp     rbx, r13
0x18002acf0  jz      loc_18002AE70
0x18002acf6  lea     rax, [rsp+478h+var_3B8]
0x18002acfe  mov     qword ptr [rsp+478h+var_428], rax
0x18002ad03  lea     rdx, [rsp+478h+var_2B8]
0x18002ad0b  cmp     [rsp+478h+var_2A0], 7
0x18002ad14  cmova   rdx, qword ptr [rsp+478h+var_2B8]
0x18002ad1d  lea     rcx, [rsp+478h+var_3B8]
0x18002ad25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad2a  mov     r12, rax
0x18002ad2d  cmp     qword ptr [rbx+18h], 7
0x18002ad32  jbe     short loc_18002AD39
0x18002ad34  mov     rdx, [rbx]
0x18002ad37  jmp     short loc_18002AD3C
0x18002ad39  mov     rdx, rbx
0x18002ad3c  lea     rcx, [rsp+478h+var_398]
0x18002ad44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad49  nop
0x18002ad4a  mov     rdx, r12
0x18002ad4d  mov     rcx, rax
0x18002ad50  call    ?IContains@StringHelpers@PrintCore@@SA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IContains(std::wstring,std::wstring)
0x18002ad55  test    al, al
0x18002ad57  jz      loc_18002AE67
0x18002ad5d  lea     rax, [rsp+478h+var_398]
0x18002ad65  mov     [rsp+478h+var_3F8], rax
0x18002ad6d  lea     rdx, [rsp+478h+var_2F8]
0x18002ad75  cmp     qword ptr [rsp+478h+var_2E8+8], 7
  ... truncated ...
```
