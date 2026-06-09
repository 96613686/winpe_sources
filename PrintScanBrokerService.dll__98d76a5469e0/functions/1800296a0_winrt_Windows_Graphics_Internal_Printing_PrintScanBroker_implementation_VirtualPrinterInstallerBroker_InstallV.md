# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinterForAllUsers(winrt::Windows::Foundation::IInspectable const &,winrt::hstring const &)

- ea: `0x1800296a0`
- end: `0x180029ff0`
- name: `?InstallVirtualPrinterForAllUsers@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@SA_KAEBUIInspectable@Foundation@78@AEBUhstring@8@@Z`
- size: `2384`
- prototype: `unsigned __int64 __fastcall(const struct IInspectable *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b3e0`

## callees

- `0x180002d40`
- `0x180005eb4`
- `0x180007a58`
- `0x180008838`
- `0x18000f760`
- `0x18000f8a8`
- `0x18000fa2c`
- `0x18000fa48`
- `0x18000fb60`
- `0x180012498`
- `0x1800182cc`
- `0x18001c08c`
- `0x18001cfb4`
- `0x18001d0a0`
- `0x1800232bc`
- `0x1800256f8`
- `0x180027060`
- `0x180027160`
- `0x180027640`
- `0x1800278a4`
- `0x1800278ec`
- `0x180027cf4`
- `0x180027d54`
- `0x1800288d8`
- `0x1800296a0`
- `0x18002aff0`
- `0x18002b07c`
- `0x18002b22c`
- `0x18002b4d0`
- `0x18002faf8`
- `0x18003170c`
- `0x180044088`
- `0x180048010`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180029d6d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180029d6d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180029cc0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180029cc0`
- `IppCommon!InstallVirtualPrintersForSessionId` at `0x180029d48`
- `IppCommon!InstallVirtualPrintersForSessionId` at `0x180029d48`

## string_xrefs

- `0x180029a38`: `PrinterUri`
- `0x180029b28`: `PdcFilePath`
- `0x180029bc8`: `PdrFilePath`
- `0x1800296d6`: `Checking access`
- `0x180029cdd`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f00`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f15`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f29`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f3d`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f51`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f65`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f79`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029f8d`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029fa1`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029fb5`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029fc9`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029fdd`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029772`: `Getting pkg path by full name`
- `0x1800296dd`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinterForAllUsers`
- `0x1800298b3`: `Opening printer name regkey`
- `0x180029856`: `Opening allusers regkey`
- `0x180029c89`: `Install for existing users`
- `0x180029d31`: `Install for sessionId 0x%x`
- `0x180029d08`: `Install for %d existing users`
- `0x180029d57`: `Installed for sessionId 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinterForAllUsers(
        const struct IInspectable *a1,
        const struct winrt::hstring *a2)
{
  const WCHAR *v4; // rax
  unsigned __int16 **v5; // r8
  int SinglePackageFullNameFromPackageFamilyName; // eax
  const unsigned __int16 *v7; // r9
  unsigned __int16 *v8; // rdi
  unsigned __int16 **v9; // r9
  int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // rbx
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdx
  int v18; // eax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  _QWORD *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  _QWORD *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  int v30; // eax
  _QWORD *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  _QWORD *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // eax
  _QWORD *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rdx
  int v42; // eax
  _QWORD *v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rdx
  int v46; // eax
  _QWORD *v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rdx
  int v50; // eax
  _QWORD *v51; // rdx
  __int64 v52; // rax
  __int64 v53; // rdx
  int v54; // eax
  __int128 *p_Src; // rdx
  __int64 v56; // rax
  __int64 v57; // rdx
  int v58; // eax
  unsigned int v59; // eax
  __int64 i; // rdi
  const char *v61; // r9
  unsigned __int64 result; // rax
  __int64 v63; // rsi
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  int pCount; // [rsp+20h] [rbp-288h]
  const char *v69; // [rsp+28h] [rbp-280h]
  __int64 v70; // [rsp+30h] [rbp-278h] BYREF
  __int64 v71; // [rsp+38h] [rbp-270h] BYREF
  __int64 v72; // [rsp+40h] [rbp-268h] BYREF
  DWORD v73; // [rsp+48h] [rbp-260h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+50h] [rbp-258h] BYREF
  unsigned __int16 *v75; // [rsp+58h] [rbp-250h] BYREF
  __int64 v76; // [rsp+60h] [rbp-248h] BYREF
  _BYTE v77[8]; // [rsp+68h] [rbp-240h] BYREF
  __int64 v78; // [rsp+70h] [rbp-238h] BYREF
  _BYTE v79[8]; // [rsp+78h] [rbp-230h] BYREF
  _BYTE v80[8]; // [rsp+80h] [rbp-228h] BYREF
  _BYTE v81[8]; // [rsp+88h] [rbp-220h] BYREF
  __int64 *v82; // [rsp+90h] [rbp-218h] BYREF
  int v83; // [rsp+98h] [rbp-210h]
  void **v84; // [rsp+A0h] [rbp-208h]
  PWTS_SESSION_INFOW *p_ppSessionInfo; // [rsp+A8h] [rbp-200h] BYREF
  __int128 v86; // [rsp+B0h] [rbp-1F8h]
  unsigned __int16 *v87[3]; // [rsp+C8h] [rbp-1E0h] BYREF
  unsigned __int64 v88; // [rsp+E0h] [rbp-1C8h]
  __int128 Src; // [rsp+E8h] [rbp-1C0h] BYREF
  __m128i si128; // [rsp+F8h] [rbp-1B0h]
  _BYTE v91[32]; // [rsp+110h] [rbp-198h] BYREF
  _QWORD v92[4]; // [rsp+130h] [rbp-178h] BYREF
  _QWORD v93[3]; // [rsp+150h] [rbp-158h] BYREF
  unsigned __int64 v94; // [rsp+168h] [rbp-140h]
  _QWORD v95[4]; // [rsp+190h] [rbp-118h] BYREF
  _QWORD v96[4]; // [rsp+1B0h] [rbp-F8h] BYREF
  _QWORD v97[4]; // [rsp+1D0h] [rbp-D8h] BYREF
  _QWORD v98[4]; // [rsp+1F0h] [rbp-B8h] BYREF
  _QWORD v99[4]; // [rsp+210h] [rbp-98h] BYREF
  _QWORD v100[4]; // [rsp+230h] [rbp-78h] BYREF
  _QWORD v101[6]; // [rsp+250h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage();
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Checking access");
    v75 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v75,
      0);
    v4 = winrt::hstring::c_str(a2);
    SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                   v4,
                                                   (const unsigned __int16 *)&v75,
                                                   v5);
    if ( SinglePackageFullNameFromPackageFamilyName < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
        pCount);
    v84 = &PrintSupportUtility::`vftable';
    TokenUtility::GetUserSidForActiveSession(retaddr, v87);
    v7 = (const unsigned __int16 *)v87;
    if ( v88 > 7 )
      v7 = v87[0];
    v8 = v75;
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(
      0x3000u,
      v75,
      0,
      v7);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Getting pkg path by full name");
    winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Devices::Printers::VirtualPrinterInstallationParameters>(
      a1,
      v77);
    v9 = v87;
    if ( v88 > 7 )
      v9 = (unsigned __int16 **)v87[0];
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetVirtualPrinterInfo(
      v91,
      v77,
      v8,
      v9);
    Src = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src) = 0;
    winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterInstallationParameters<winrt::Windows::Devices::Printers::IVirtualPrinterInstallationParameters>::SupportedInputFormats(
      v77,
      &v76);
    v82 = &v76;
    v10 = 0;
    v83 = 0;
    LODWORD(v70) = 0;
    LODWORD(p_ppSessionInfo) = 0;
    v86 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v76 + 56LL))(v76, &v70);
    winrt::check_hresult(&v72, v11, &p_ppSessionInfo);
    while ( v10 != (_DWORD)v70 )
    {
      winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Devices::Printers::VirtualPrinterSupportedFormat>>::operator*(
        &v82,
        &v72);
      v63 = winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
              &v72,
              &v71);
      v64 = winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::ContentType(
              &v72,
              v81);
      v65 = winrt::operator+(v80, v64, L",");
      v66 = winrt::operator+(v79, v65, v63);
      v67 = winrt::operator+(&v78, v66, L",");
      winrt::hstring::operator std::basic_string_view<unsigned short>(v67, &p_ppSessionInfo);
      std::wstring::_Append<unsigned short>(&Src);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v78);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v79);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v80);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v81);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v71);
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v72);
      v83 = ++v10;
    }
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Opening allusers regkey");
    std::wstring::wstring(
      &p_ppSessionInfo,
      L"System\\CurrentControlSet\\Control\\Print\\Actions\\PerUserLogon\\AllUserVirtualPrinters");
    v72 = -2147483646;
    v12 = PrintCore::RegHelpers::CreateOrOpenKey(&v72, &p_ppSessionInfo);
    v78 = v12;
    std::wstring::_Tidy_deallocate(&p_ppSessionInfo);
    v72 = 0;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Opening printer name regkey");
    v13 = v93;
    if ( v94 > 7 )
      v13 = (_QWORD *)v93[0];
    std::wstring::wstring(&p_ppSessionInfo, v13);
    v70 = v12;
    v14 = PrintCore::RegHelpers::CreateOrOpenKey(&v70, &p_ppSessionInfo);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v72,
      v14);
    std::wstring::_Tidy_deallocate(&p_ppSessionInfo);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Writing printer name regkey");
    v15 = std::wstring::wstring(&p_ppSessionInfo, v8);
    v16 = v72;
    v70 = v72;
    v18 = PrintCore::RegHelpers::SetStringValue(&v70, v17, L"AppPackageFullName", v15);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v18,
        pCount);
    v19 = v92;
    if ( v92[3] > 7u )
      v19 = (_QWORD *)v92[0];
    v20 = std::wstring::wstring(&p_ppSessionInfo, v19);
    v70 = v16;
    v22 = PrintCore::RegHelpers::SetStringValue(&v70, v21, L"AppEntryPoint", v20);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v22,
        pCount);
    v23 = v93;
    if ( v94 > 7 )
      v23 = (_QWORD *)v93[0];
    v24 = std::wstring::wstring(&p_ppSessionInfo, v23);
    v70 = v16;
    v26 = PrintCore::RegHelpers::SetStringValue(&v70, v25, L"DisplayName", v24);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v26,
        pCount);
    v27 = v95;
    if ( v95[3] > 7u )
      v27 = (_QWORD *)v95[0];
    v28 = std::wstring::wstring(&p_ppSessionInfo, v27);
    v70 = v16;
    v30 = PrintCore::RegHelpers::SetStringValue(&v70, v29, L"PrinterUri", v28);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v30,
        pCount);
    v31 = v101;
    if ( v101[3] > 7u )
      v31 = (_QWORD *)v101[0];
    v32 = std::wstring::wstring(&p_ppSessionInfo, v31);
    v70 = v16;
    v34 = PrintCore::RegHelpers::SetStringValue(&v70, v33, L"OutputFileTypes", v32);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v34,
        pCount);
    v35 = v96;
    if ( v96[3] > 7u )
      v35 = (_QWORD *)v96[0];
    v36 = std::wstring::wstring(&p_ppSessionInfo, v35);
    v70 = v16;
    v38 = PrintCore::RegHelpers::SetStringValue(&v70, v37, L"PdcFileResource", v36);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v38,
        pCount);
    v39 = v97;
    if ( v97[3] > 7u )
      v39 = (_QWORD *)v97[0];
    v40 = std::wstring::wstring(&p_ppSessionInfo, v39);
    v70 = v16;
    v42 = PrintCore::RegHelpers::SetStringValue(&v70, v41, L"PdcFilePath", v40);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v42,
        pCount);
    v43 = v98;
    if ( v98[3] > 7u )
      v43 = (_QWORD *)v98[0];
    v44 = std::wstring::wstring(&p_ppSessionInfo, v43);
    v70 = v16;
    v46 = PrintCore::RegHelpers::SetStringValue(&v70, v45, L"PdrFileResource", v44);
    if ( v46 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v46,
        pCount);
    v47 = v99;
    if ( v99[3] > 7u )
      v47 = (_QWORD *)v99[0];
    v48 = std::wstring::wstring(&p_ppSessionInfo, v47);
    v70 = v16;
    v50 = PrintCore::RegHelpers::SetStringValue(&v70, v49, L"PdrFilePath", v48);
    if ( v50 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v50,
        pCount);
    v51 = v100;
    if ( v100[3] > 7u )
      v51 = (_QWORD *)v100[0];
    v52 = std::wstring::wstring(&p_ppSessionInfo, v51);
    v70 = v16;
    v54 = PrintCore::RegHelpers::SetStringValue(&v70, v53, L"PreferredInputFormat", v52);
    if ( v54 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v54,
        pCount);
    p_Src = &Src;
    if ( si128.m128i_i64[1] > 7uLL )
      p_Src = (__int128 *)Src;
    v56 = std::wstring::wstring(&p_ppSessionInfo, p_Src);
    v70 = v16;
    v58 = PrintCore::RegHelpers::SetStringValue(&v70, v57, L"SupportedInputFormats", v56);
    if ( v58 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v58,
        pCount);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Install for existing users");
    ppSessionInfo = 0;
    v73 = 0;
    v59 = WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v73);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)v59,
      (int)"Enumerate sessions failed!",
      v69);
    p_ppSessionInfo = &ppSessionInfo;
    LOBYTE(v86) = 1;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinterForAllUsers",
      L"Install for %d existing users",
      v73);
    for ( i = 0; (unsigned int)i < v73; i = (unsigned int)(i + 1) )
    {
      if ( ppSessionInfo[i].SessionId )
      {
        PrintScanBrokerTelemetry::WriteDbgTraceInfo(
          "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::"
          "InstallVirtualPrinterForAllUsers",
          L"Install for sessionId 0x%x");
        InstallVirtualPrintersForSessionId(ppSessionInfo[i].SessionId);
        PrintScanBrokerTelemetry::WriteDbgTraceInfo(
          "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::"
          "InstallVirtualPrinterForAllUsers",
          L"Installed for sessionId 0x%x",
          ppSessionInfo[i].SessionId);
      }
    }
    WTSFreeMemory(ppSessionInfo);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v78);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v76);
    std::wstring::_Tidy_deallocate(&Src);
    VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo((VirtualMon::VirtualPrinterInfo *)v91);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v77);
    std::wstring::_Tidy_deallocate(v87);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
    result = 0;
  }
  catch ( ... )
  {
    return (int)wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x98,
                  (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
                  v61);
  }
  return result;
}

```

## disassembly

```asm
0x1800296a0  mov     [rsp+arg_10], rbx
0x1800296a5  push    rsi
0x1800296a6  push    rdi
0x1800296a7  push    r12
0x1800296a9  sub     rsp, 290h
0x1800296b0  mov     rax, cs:__security_cookie
0x1800296b7  xor     rax, rsp
0x1800296ba  mov     [rsp+2A8h+var_28], rax
0x1800296c2  mov     rdi, rdx
0x1800296c5  mov     rbx, rcx
0x1800296c8  mov     dl, 1
0x1800296ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements> `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl(void)'::`2'::impl
0x1800296d1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800296d6  lea     rdx, aCheckingAccess; "Checking access"
0x1800296dd  lea     r12, aWinrtWindowsGr_0; "winrt::Windows::Graphics::Internal::Pri"...
0x1800296e4  mov     rcx, r12; char *
0x1800296e7  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800296ec  mov     [rsp+2A8h+var_250], 0
0x1800296f5  xor     edx, edx
0x1800296f7  lea     rcx, [rsp+2A8h+var_250]
0x1800296fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180029701  mov     rcx, rdi; this
0x180029704  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180029709  lea     rdx, [rsp+2A8h+var_250]; unsigned __int16 *
0x18002970e  mov     rcx, rax; packageFamilyName
0x180029711  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x180029716  mov     rcx, [rsp+2A8h]; this
0x18002971e  test    eax, eax
0x180029720  js      loc_180029EFD
0x180029726  lea     rax, ??_7PrintSupportUtility@@6B@; const PrintSupportUtility::`vftable'
0x18002972d  mov     [rsp+2A8h+var_208], rax
0x180029735  lea     rdx, [rsp+2A8h+var_1E0]
0x18002973d  call    ?GetUserSidForActiveSession@TokenUtility@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; TokenUtility::GetUserSidForActiveSession(void)
0x180029742  nop
0x180029743  lea     r9, [rsp+2A8h+var_1E0]
0x18002974b  cmp     [rsp+2A8h+var_1C8], 7
0x180029754  cmova   r9, [rsp+2A8h+var_1E0]; unsigned __int16 *
0x18002975d  xor     r8d, r8d; unsigned __int16 *
0x180029760  mov     rdi, [rsp+2A8h+var_250]
0x180029765  mov     rdx, rdi; unsigned __int16 *
0x180029768  mov     ecx, 3000h; unsigned int
0x18002976d  call    ?VirtualPrinterInstallAccessCheck@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CAXKPEBG00@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(ulong,ushort const *,ushort const *,ushort const *)
0x180029772  lea     rdx, aGettingPkgPath; "Getting pkg path by full name"
0x180029779  mov     rcx, r12; char *
0x18002977c  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180029781  lea     rdx, [rsp+2A8h+var_240]
0x180029786  mov     rcx, rbx
0x180029789  call    ??$as@UVirtualPrinterInstallationParameters@Printers@Devices@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18002978e  nop
0x18002978f  lea     r9, [rsp+2A8h+var_1E0]
0x180029797  cmp     [rsp+2A8h+var_1C8], 7
0x1800297a0  cmova   r9, [rsp+2A8h+var_1E0]
0x1800297a9  mov     r8, rdi
0x1800297ac  lea     rdx, [rsp+2A8h+var_240]
0x1800297b1  lea     rcx, [rsp+2A8h+var_198]
0x1800297b9  call    ?GetVirtualPrinterInfo@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AUVirtualPrinterInfo@VirtualMon@@AEBUVirtualPrinterInstallationParameters@Printers@Devices@78@PEBG1@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetVirtualPrinterInfo(winrt::Windows::Devices::Printers::VirtualPrinterInstallationParameters const &,ushort const *,ushort const *)
0x1800297be  nop
0x1800297bf  xorps   xmm0, xmm0
0x1800297c2  movups  [rsp+2A8h+Src], xmm0
0x1800297ca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800297d2  movdqu  [rsp+2A8h+var_1B0], xmm1
0x1800297db  xor     eax, eax
0x1800297dd  mov     word ptr [rsp+2A8h+Src], ax
0x1800297e5  lea     rdx, [rsp+2A8h+var_248]
0x1800297ea  lea     rcx, [rsp+2A8h+var_240]
0x1800297ef  call    ?SupportedInputFormats@?$consume_Windows_Devices_Printers_IVirtualPrinterInstallationParameters@UIVirtualPrinterInstallationParameters@Printers@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterInstallationParameters<winrt::Windows::Devices::Printers::IVirtualPrinterInstallationParameters>::SupportedInputFormats(void)
0x1800297f4  nop
0x1800297f5  lea     rax, [rsp+2A8h+var_248]
0x1800297fa  mov     [rsp+2A8h+var_218], rax
0x180029802  xor     ebx, ebx
0x180029804  mov     [rsp+2A8h+var_210], ebx
0x18002980b  mov     dword ptr [rsp+2A8h+var_278], ebx
0x18002980f  mov     rcx, [rsp+2A8h+var_248]
0x180029814  mov     dword ptr [rsp+2A8h+var_200], ebx
0x18002981b  xorps   xmm0, xmm0
0x18002981e  movdqu  [rsp+2A8h+var_1F8], xmm0
0x180029827  mov     rax, [rcx]
0x18002982a  lea     rdx, [rsp+2A8h+var_278]
0x18002982f  mov     rax, [rax+38h]
0x180029833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029838  lea     r8, [rsp+2A8h+var_200]
0x180029840  mov     edx, eax
0x180029842  lea     rcx, [rsp+2A8h+var_268]
0x180029847  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002984c  cmp     ebx, dword ptr [rsp+2A8h+var_278]
0x180029850  jnz     loc_180029DDB
0x180029856  lea     rdx, aOpeningAlluser; "Opening allusers regkey"
0x18002985d  mov     rcx, r12; char *
0x180029860  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180029865  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pri"...
0x18002986c  lea     rcx, [rsp+2A8h+var_200]
0x180029874  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029879  nop
0x18002987a  mov     [rsp+2A8h+var_268], 0FFFFFFFF80000002h
0x180029883  lea     rdx, [rsp+2A8h+var_200]
0x18002988b  lea     rcx, [rsp+2A8h+var_268]
0x180029890  call    ?CreateOrOpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::CreateOrOpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x180029895  mov     rbx, rax
0x180029898  mov     [rsp+2A8h+var_238], rax
0x18002989d  lea     rcx, [rsp+2A8h+var_200]
0x1800298a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298aa  mov     [rsp+2A8h+var_268], 0
0x1800298b3  lea     rdx, aOpeningPrinter; "Opening printer name regkey"
0x1800298ba  mov     rcx, r12; char *
0x1800298bd  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800298c2  lea     rdx, [rsp+2A8h+var_158]
0x1800298ca  cmp     [rsp+2A8h+var_140], 7
0x1800298d3  cmova   rdx, [rsp+2A8h+var_158]
0x1800298dc  lea     rcx, [rsp+2A8h+var_200]
0x1800298e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800298e9  nop
0x1800298ea  mov     [rsp+2A8h+var_278], rbx
0x1800298ef  lea     rdx, [rsp+2A8h+var_200]
0x1800298f7  lea     rcx, [rsp+2A8h+var_278]
0x1800298fc  call    ?CreateOrOpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::CreateOrOpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x180029901  mov     rdx, rax
0x180029904  lea     rcx, [rsp+2A8h+var_268]
0x180029909  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002990e  nop
0x18002990f  lea     rcx, [rsp+2A8h+var_200]
0x180029917  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002991c  lea     rdx, aWritingPrinter; "Writing printer name regkey"
0x180029923  mov     rcx, r12; char *
0x180029926  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002992b  mov     rdx, rdi
0x18002992e  lea     rcx, [rsp+2A8h+var_200]
0x180029936  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002993b  mov     rbx, [rsp+2A8h+var_268]
0x180029940  mov     [rsp+2A8h+var_278], rbx
0x180029945  mov     r9, rax
0x180029948  lea     r8, Value; "AppPackageFullName"
0x18002994f  lea     rcx, [rsp+2A8h+var_278]
0x180029954  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029959  mov     rcx, [rsp+2A8h]; this
0x180029961  test    eax, eax
0x180029963  js      loc_180029F12
0x180029969  lea     rdx, [rsp+2A8h+var_178]
0x180029971  cmp     [rsp+2A8h+var_160], 7
0x18002997a  cmova   rdx, [rsp+2A8h+var_178]
0x180029983  lea     rcx, [rsp+2A8h+var_200]
0x18002998b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029990  mov     [rsp+2A8h+var_278], rbx
0x180029995  mov     r9, rax
0x180029998  lea     r8, aAppentrypoint; "AppEntryPoint"
0x18002999f  lea     rcx, [rsp+2A8h+var_278]
0x1800299a4  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x1800299a9  mov     rcx, [rsp+2A8h]; this
0x1800299b1  test    eax, eax
0x1800299b3  js      loc_180029F26
0x1800299b9  lea     rdx, [rsp+2A8h+var_158]
0x1800299c1  cmp     [rsp+2A8h+var_140], 7
0x1800299ca  cmova   rdx, [rsp+2A8h+var_158]
0x1800299d3  lea     rcx, [rsp+2A8h+var_200]
0x1800299db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800299e0  mov     [rsp+2A8h+var_278], rbx
0x1800299e5  mov     r9, rax
0x1800299e8  lea     r8, aDisplayname; "DisplayName"
0x1800299ef  lea     rcx, [rsp+2A8h+var_278]
0x1800299f4  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x1800299f9  mov     rcx, [rsp+2A8h]; this
0x180029a01  test    eax, eax
0x180029a03  js      loc_180029F3A
0x180029a09  lea     rdx, [rsp+2A8h+var_118]
0x180029a11  cmp     [rsp+2A8h+var_100], 7
0x180029a1a  cmova   rdx, [rsp+2A8h+var_118]
0x180029a23  lea     rcx, [rsp+2A8h+var_200]
0x180029a2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029a30  mov     [rsp+2A8h+var_278], rbx
0x180029a35  mov     r9, rax
0x180029a38  lea     r8, aPrinteruri; "PrinterUri"
0x180029a3f  lea     rcx, [rsp+2A8h+var_278]
0x180029a44  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029a49  mov     rcx, [rsp+2A8h]; this
0x180029a51  test    eax, eax
0x180029a53  js      loc_180029F4E
0x180029a59  lea     rdx, [rsp+2A8h+var_58]
0x180029a61  cmp     [rsp+2A8h+var_40], 7
0x180029a6a  cmova   rdx, [rsp+2A8h+var_58]
0x180029a73  lea     rcx, [rsp+2A8h+var_200]
0x180029a7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029a80  mov     [rsp+2A8h+var_278], rbx
0x180029a85  mov     r9, rax
0x180029a88  lea     r8, aOutputfiletype; "OutputFileTypes"
0x180029a8f  lea     rcx, [rsp+2A8h+var_278]
0x180029a94  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029a99  mov     rcx, [rsp+2A8h]; this
0x180029aa1  test    eax, eax
0x180029aa3  js      loc_180029F62
0x180029aa9  lea     rdx, [rsp+2A8h+var_F8]
0x180029ab1  cmp     [rsp+2A8h+var_E0], 7
0x180029aba  cmova   rdx, [rsp+2A8h+var_F8]
0x180029ac3  lea     rcx, [rsp+2A8h+var_200]
0x180029acb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029ad0  mov     [rsp+2A8h+var_278], rbx
0x180029ad5  mov     r9, rax
0x180029ad8  lea     r8, aPdcfileresourc; "PdcFileResource"
0x180029adf  lea     rcx, [rsp+2A8h+var_278]
0x180029ae4  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029ae9  mov     rcx, [rsp+2A8h]; this
0x180029af1  test    eax, eax
0x180029af3  js      loc_180029F76
0x180029af9  lea     rdx, [rsp+2A8h+var_D8]
0x180029b01  cmp     [rsp+2A8h+var_C0], 7
0x180029b0a  cmova   rdx, [rsp+2A8h+var_D8]
0x180029b13  lea     rcx, [rsp+2A8h+var_200]
0x180029b1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b20  mov     [rsp+2A8h+var_278], rbx
0x180029b25  mov     r9, rax
0x180029b28  lea     r8, aPdcfilepath; "PdcFilePath"
0x180029b2f  lea     rcx, [rsp+2A8h+var_278]
0x180029b34  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029b39  mov     rcx, [rsp+2A8h]; this
0x180029b41  test    eax, eax
0x180029b43  js      loc_180029F8A
0x180029b49  lea     rdx, [rsp+2A8h+var_B8]
0x180029b51  cmp     [rsp+2A8h+var_A0], 7
0x180029b5a  cmova   rdx, [rsp+2A8h+var_B8]
0x180029b63  lea     rcx, [rsp+2A8h+var_200]
0x180029b6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b70  mov     [rsp+2A8h+var_278], rbx
0x180029b75  mov     r9, rax
0x180029b78  lea     r8, aPdrfileresourc; "PdrFileResource"
0x180029b7f  lea     rcx, [rsp+2A8h+var_278]
0x180029b84  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029b89  mov     rcx, [rsp+2A8h]; this
0x180029b91  test    eax, eax
0x180029b93  js      loc_180029F9E
0x180029b99  lea     rdx, [rsp+2A8h+var_98]
0x180029ba1  cmp     [rsp+2A8h+var_80], 7
0x180029baa  cmova   rdx, [rsp+2A8h+var_98]
0x180029bb3  lea     rcx, [rsp+2A8h+var_200]
0x180029bbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029bc0  mov     [rsp+2A8h+var_278], rbx
0x180029bc5  mov     r9, rax
0x180029bc8  lea     r8, aPdrfilepath; "PdrFilePath"
0x180029bcf  lea     rcx, [rsp+2A8h+var_278]
0x180029bd4  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029bd9  mov     rcx, [rsp+2A8h]; this
0x180029be1  test    eax, eax
0x180029be3  js      loc_180029FB2
0x180029be9  lea     rdx, [rsp+2A8h+var_78]
0x180029bf1  cmp     [rsp+2A8h+var_60], 7
0x180029bfa  cmova   rdx, [rsp+2A8h+var_78]
0x180029c03  lea     rcx, [rsp+2A8h+var_200]
0x180029c0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029c10  mov     [rsp+2A8h+var_278], rbx
0x180029c15  mov     r9, rax
0x180029c18  lea     r8, aPreferredinput; "PreferredInputFormat"
0x180029c1f  lea     rcx, [rsp+2A8h+var_278]
0x180029c24  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029c29  mov     rcx, [rsp+2A8h]; this
0x180029c31  test    eax, eax
0x180029c33  js      loc_180029FC6
0x180029c39  lea     rdx, [rsp+2A8h+Src]
0x180029c41  cmp     qword ptr [rsp+2A8h+var_1B0+8], 7
0x180029c4a  cmova   rdx, qword ptr [rsp+2A8h+Src]
0x180029c53  lea     rcx, [rsp+2A8h+var_200]
0x180029c5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029c60  mov     [rsp+2A8h+var_278], rbx
0x180029c65  mov     r9, rax
0x180029c68  lea     r8, aSupportedinput; "SupportedInputFormats"
0x180029c6f  lea     rcx, [rsp+2A8h+var_278]
0x180029c74  call    ?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::wstring,ulong)
0x180029c79  mov     rcx, [rsp+2A8h]; this
0x180029c81  test    eax, eax
0x180029c83  js      loc_180029FDA
0x180029c89  lea     rdx, aInstallForExis; "Install for existing users"
0x180029c90  mov     rcx, r12; char *
0x180029c93  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180029c98  mov     [rsp+2A8h+ppSessionInfo], 0
0x180029ca1  mov     [rsp+2A8h+var_260], 0
0x180029ca9  lea     rax, [rsp+2A8h+var_260]
0x180029cae  mov     [rsp+2A8h+pCount], rax; pCount
0x180029cb3  lea     r9, [rsp+2A8h+ppSessionInfo]; ppSessionInfo
0x180029cb8  xor     edx, edx; Reserved
0x180029cba  xor     ecx, ecx; hServer
0x180029cbc  lea     r8d, [rdx+1]; Version
0x180029cc0  call    cs:__imp_WTSEnumerateSessionsW
0x180029cc6  mov     rcx, [rsp+2A8h]; this
0x180029cce  lea     rdx, aEnumerateSessi; "Enumerate sessions failed!"
0x180029cd5  mov     [rsp+2A8h+pCount], rdx; int
0x180029cda  mov     r9d, eax; char *
0x180029cdd  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x180029ce4  mov     edx, 84h; void *
0x180029ce9  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180029cee  lea     rbx, [rsp+2A8h+ppSessionInfo]
0x180029cf3  mov     [rsp+2A8h+var_200], rbx
0x180029cfb  mov     byte ptr [rsp+2A8h+var_1F8], 1
0x180029d03  mov     r8d, [rsp+2A8h+var_260]
0x180029d08  lea     rdx, aInstallForDExi; "Install for %d existing users"
0x180029d0f  mov     rcx, r12; char *
0x180029d12  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180029d17  xor     edi, edi
0x180029d19  cmp     edi, [rsp+2A8h+var_260]
0x180029d1d  jnb     short loc_180029D6A
0x180029d1f  lea     rsi, [rdi+rdi*2]
0x180029d23  mov     rax, [rsp+2A8h+ppSessionInfo]
0x180029d28  mov     r8d, [rax+rsi*8]
0x180029d2c  test    r8d, r8d
0x180029d2f  jz      short loc_180029D66
  ... truncated ...
```
