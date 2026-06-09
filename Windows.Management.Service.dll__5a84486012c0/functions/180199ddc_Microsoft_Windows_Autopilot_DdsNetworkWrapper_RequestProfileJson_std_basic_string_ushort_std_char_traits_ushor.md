# Microsoft::Windows::Autopilot::DdsNetworkWrapper::RequestProfileJson(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x180199ddc`
- end: `0x18019b1b0`
- name: `?RequestProfileJson@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `5076`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ae8e0`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067008`
- `0x180067a34`
- `0x180067a54`
- `0x180067ffc`
- `0x18006defc`
- `0x18007755c`
- `0x18008019c`
- `0x1800806b0`
- `0x180080708`
- `0x18008084c`
- `0x18008122c`
- `0x1800839bc`
- `0x1800853a0`
- `0x18008982c`
- `0x180089b58`
- `0x18008a014`
- `0x18008a464`
- `0x18008afec`
- `0x18008b9c4`
- `0x18008e438`
- `0x18008ecf8`
- `0x18008f068`
- `0x1800df644`
- `0x18017f68c`
- `0x1801984ac`
- `0x18019874c`
- `0x180199b2c`
- `0x180199d50`
- `0x180199ddc`
- `0x18019b1b8`
- `0x18019b5c8`
- `0x18019bacc`
- `0x1801afb38`
- `0x1801afe28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180199edd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180199f09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180199edd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180199f09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180199fbf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180199fbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18019ac32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18019ac32`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18019a2a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18019a2a5`
- `api-ms-win-core-sysinfo-l1-2-0!SetSystemTime` at `0x18019adc2`
- `api-ms-win-core-sysinfo-l1-2-0!SetSystemTime` at `0x18019adc2`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18019a34f`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18019a34f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18019ad66`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18019ad66`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18019ac50`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18019ac50`
- `WINHTTP!WinHttpCrackUrl` at `0x180199ea2`
- `WINHTTP!WinHttpCrackUrl` at `0x180199ea2`

## string_xrefs

- `0x18019a85e`: `Windows.Data.Json.JsonObject`
- `0x180199eb4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180199f76`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180199fd6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a05b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a0e0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a173`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a214`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a2b7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a361`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a40f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a527`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a689`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a7b3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a899`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019a95a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019aa18`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019ab8a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019ac66`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019ae91`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019af79`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b030`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b16b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019add6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::RequestProfileJson(
        Microsoft::Windows::Autopilot::DdsNetworkWrapper *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  const WCHAR *v11; // rax
  const char *v12; // r9
  unsigned __int16 v14; // di
  DWORD v15; // r15d
  __m128i si128; // xmm6
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  HRESULT v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  unsigned int v27; // ebx
  int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // ebx
  int v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  const char *v36; // r9
  unsigned int LastError; // ebx
  const char *v38; // r9
  unsigned int v39; // ebx
  int v40; // eax
  unsigned int v41; // ebx
  const struct Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride *v42; // r9
  unsigned int Request; // ebx
  unsigned int Data; // ebx
  int v45; // eax
  unsigned int v46; // ebx
  int v47; // eax
  unsigned int v48; // ebx
  int v49; // eax
  unsigned int v50; // ebx
  __int64 v51; // rdx
  int v52; // ebx
  const unsigned __int16 *v53; // rax
  int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // r8
  const char *v57; // r9
  unsigned int v58; // ebx
  int v59; // edi
  signed int MaximumAllowedTimeDriftInMinutes; // eax
  char v61; // si
  int v62; // ecx
  int v63; // ebx
  int v64; // eax
  int v65; // edx
  int v66; // ecx
  __int64 v67; // rcx
  __int64 v68; // r8
  const char *v69; // r9
  int v70; // eax
  __int64 v71; // rax
  __int64 v72; // rcx
  const unsigned __int16 *v73; // rax
  int v74; // eax
  unsigned int v75; // ebx
  const unsigned __int16 *v76; // rax
  int v77; // eax
  unsigned int v78; // ebx
  int v79; // eax
  unsigned int v80; // ebx
  __int64 v81; // rax
  __int64 v82; // rcx
  int ppv; // [rsp+20h] [rbp-7A8h]
  int ppva; // [rsp+20h] [rbp-7A8h]
  int ppvb; // [rsp+20h] [rbp-7A8h]
  int ppvc; // [rsp+20h] [rbp-7A8h]
  LPVOID v87; // [rsp+60h] [rbp-768h] BYREF
  struct Windows::Data::Json::IJsonObject *v88; // [rsp+68h] [rbp-760h] BYREF
  DWORD pdwReturnedProductType; // [rsp+70h] [rbp-758h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-750h] BYREF
  LPCCH lpMultiByteStr; // [rsp+80h] [rbp-748h] BYREF
  int cbMultiByte[2]; // [rsp+88h] [rbp-740h]
  struct _FILETIME FileTime; // [rsp+90h] [rbp-738h] BYREF
  __int64 v94; // [rsp+98h] [rbp-730h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+A0h] [rbp-728h] BYREF
  _OWORD v96[2]; // [rsp+110h] [rbp-6B8h] BYREF
  __int64 v97[2]; // [rsp+130h] [rbp-698h] BYREF
  __m128i v98; // [rsp+140h] [rbp-688h]
  __int64 v99[2]; // [rsp+150h] [rbp-678h] BYREF
  __m128i v100; // [rsp+160h] [rbp-668h]
  __int64 v101[2]; // [rsp+170h] [rbp-658h] BYREF
  __m128i v102; // [rsp+180h] [rbp-648h]
  __int64 v103[2]; // [rsp+190h] [rbp-638h] BYREF
  __m128i v104; // [rsp+1A0h] [rbp-628h]
  __int64 v105[4]; // [rsp+1B0h] [rbp-618h] BYREF
  __int128 hstringHeader; // [rsp+1D0h] [rbp-5F8h] BYREF
  __m128i hstringHeader_16; // [rsp+1E0h] [rbp-5E8h]
  SYSTEMTIME SystemTime; // [rsp+1F0h] [rbp-5D8h] BYREF
  _OWORD v109[2]; // [rsp+200h] [rbp-5C8h] BYREF
  struct _SYSTEMTIME v110; // [rsp+220h] [rbp-5A8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+230h] [rbp-598h] BYREF
  unsigned __int16 v112; // [rsp+344h] [rbp-484h]
  unsigned __int16 v113; // [rsp+346h] [rbp-482h]
  _BYTE v114[16]; // [rsp+350h] [rbp-478h] BYREF
  unsigned __int16 v115[256]; // [rsp+360h] [rbp-468h] BYREF
  unsigned __int16 v116[264]; // [rsp+560h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7C8h] [rbp+0h]

  v94 = a7;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  memset_0(v115, 0, sizeof(v115));
  UrlComponents.lpszHostName = (LPSTR)v115;
  UrlComponents.dwHostNameLength = 256;
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( !WinHttpCrackUrl(v11, 0, 0, &UrlComponents) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x72,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v12);
  if ( (unsigned int)_o__wcsnicmp(L"https", UrlComponents.lpszScheme, 5) )
  {
    if ( (unsigned int)_o__wcsnicmp(L"http", UrlComponents.lpszScheme, 4) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        v81 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        McTemplateU0z_EventWriteTransfer(v82, AutopilotDownloadBadTargetUrl, v81);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
      return 2147549183LL;
    }
    v14 = 80;
    v15 = 0;
  }
  else
  {
    v14 = 443;
    v15 = 0x800000;
  }
  v96[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v96[1] = si128;
  LOWORD(v96[0]) = 0;
  v17 = std::wstring::wstring(&hstringHeader, a3);
  v19 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(v18, v17, v96);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v19,
      ppv);
    std::wstring::_Tidy_deallocate(v96);
    return v20;
  }
  v87 = 0;
  v21 = CoCreateInstance(
          &GUID_66d0db14_5638_475f_a386_629522d8c461,
          0,
          1u,
          &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
          &v87);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v21,
      ppva);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v23;
  }
  *(_OWORD *)v97 = 0;
  v98 = si128;
  LOWORD(v97[0]) = 0;
  LOBYTE(v22) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl'::`2'::impl,
    v22);
  v25 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(
          v24,
          v87,
          L"./DevDetail/Ext/DeviceHardwareData",
          v97);
  v27 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v25,
      ppva);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v27;
  }
  *(_OWORD *)v99 = 0;
  v100 = si128;
  LOWORD(v99[0]) = 0;
  v28 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(v26, v87, L"./DevInfo/Man", v99);
  v30 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v28,
      ppva);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v30;
  }
  *(_OWORD *)v101 = 0;
  v102 = si128;
  LOWORD(v101[0]) = 0;
  v31 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(v29, v87, L"./DevInfo/Mod", v101);
  v33 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v31,
      ppva);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v33;
  }
  *(_OWORD *)v103 = 0;
  v104 = si128;
  LOWORD(v103[0]) = 0;
  v34 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(v32, v87, L"./DevDetail/SwV", v103);
  v35 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v34,
      ppva);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v35;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA2,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                  v36);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return LastError;
  }
  pdwReturnedProductType = 0;
  if ( !GetProductInfo(
          VersionInformation.dwMajorVersion,
          VersionInformation.dwMinorVersion,
          v112,
          v113,
          &pdwReturnedProductType) )
  {
    v39 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xAA,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
            v38);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v39;
  }
  memset_0(v116, 0, 0x208u);
  v40 = StringCchPrintfW(v116, 0x104u, L"%d", pdwReturnedProductType);
  v41 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v40,
      ppvb);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v41;
  }
  std::wstring::wstring(v105, v116);
  Request = Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(this, v115, v14, v42);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Request) )
    goto LABEL_26;
  if ( (Request & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)Request,
      ppvb);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return Request;
  }
  Request = Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendGetRequest(
              this,
              (LPCWSTR)UrlComponents.lpszUrlPath,
              v15,
              a4,
              (__int64)v97,
              (__int64)v99,
              (__int64)v101,
              (__int64)v103,
              (__int64)v105,
              a5);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Request) )
  {
LABEL_26:
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return Request;
  }
  if ( (Request & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)Request,
      ppvc);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return Request;
  }
  lpMultiByteStr = 0;
  *(_QWORD *)cbMultiByte = 0;
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData((__int64)this, (__int64)&lpMultiByteStr);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return Data;
  }
  if ( (Data & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)Data,
      ppvc);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return Data;
  }
  v88 = 0;
  if ( *(_QWORD *)cbMultiByte )
  {
    SystemTimeAsFileTime = 0;
    v47 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
            0xFDE9u,
            lpMultiByteStr,
            cbMultiByte[0]);
    v48 = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v47,
        ppvc);
      Windows::Internal::String::~String((Windows::Internal::String *)&SystemTimeAsFileTime);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
      std::wstring::_Tidy_deallocate(v105);
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::_Tidy_deallocate(v101);
      std::wstring::_Tidy_deallocate(v99);
      std::wstring::_Tidy_deallocate(v97);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
      std::wstring::_Tidy_deallocate(v96);
      return v48;
    }
    v49 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&SystemTimeAsFileTime, &v88);
    v50 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v49,
        ppvc);
      Windows::Internal::String::~String((Windows::Internal::String *)&SystemTimeAsFileTime);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
      std::wstring::_Tidy_deallocate(v105);
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::_Tidy_deallocate(v101);
      std::wstring::_Tidy_deallocate(v99);
      std::wstring::_Tidy_deallocate(v97);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
      std::wstring::_Tidy_deallocate(v96);
      return v50;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&SystemTimeAsFileTime);
  }
  else
  {
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v45 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
            hstringHeader_16.m128i_i64[1],
            &v88);
    v46 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v45,
        ppvc);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
      std::wstring::_Tidy_deallocate(v105);
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::_Tidy_deallocate(v101);
      std::wstring::_Tidy_deallocate(v99);
      std::wstring::_Tidy_deallocate(v97);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
      std::wstring::_Tidy_deallocate(v96);
      return v46;
    }
  }
  if ( *((_QWORD *)this + 6) )
  {
    SystemTime = 0;
    v109[0] = 0;
    v109[1] = si128;
    LOWORD(v109[0]) = 0;
    v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
    std::wstring::wstring(&hstringHeader, v51);
    v52 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::ConvertRfc7231DateToSystemTime(
            &hstringHeader,
            &SystemTime);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    if ( v52 < 0
      || (v52 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, v109), v52 < 0) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v71 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
        McTemplateU0dz_EventWriteTransfer(v72, AutopilotDownloadInvalidTimeConversion, (unsigned int)v52, v71);
      }
      v73 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
      v74 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v88, L"PolicyDownloadDate", v73);
      v75 = v74;
      if ( v74 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)(unsigned int)v74,
          ppvc);
        std::wstring::_Tidy_deallocate(v109);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
        std::wstring::_Tidy_deallocate(v105);
        std::wstring::_Tidy_deallocate(v103);
        std::wstring::_Tidy_deallocate(v101);
        std::wstring::_Tidy_deallocate(v99);
        std::wstring::_Tidy_deallocate(v97);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
        std::wstring::_Tidy_deallocate(v96);
        return v75;
      }
    }
    else
    {
      v53 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v109);
      v54 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v88, L"PolicyDownloadDate", v53);
      v55 = v54;
      if ( v54 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)(unsigned int)v54,
          ppvc);
        std::wstring::_Tidy_deallocate(v109);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
        std::wstring::_Tidy_deallocate(v105);
        std::wstring::_Tidy_deallocate(v103);
        std::wstring::_Tidy_deallocate(v101);
        std::wstring::_Tidy_deallocate(v99);
        std::wstring::_Tidy_deallocate(v97);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
        std::wstring::_Tidy_deallocate(v96);
        return v55;
      }
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      FileTime = 0;
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        v58 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xEF,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                v57);
        std::wstring::_Tidy_deallocate(v109);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
        std::wstring::_Tidy_deallocate(v105);
        std::wstring::_Tidy_deallocate(v103);
        std::wstring::_Tidy_deallocate(v101);
        std::wstring::_Tidy_deallocate(v99);
        std::wstring::_Tidy_deallocate(v97);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
        std::wstring::_Tidy_deallocate(v96);
        return v58;
      }
      v59 = Microsoft::Windows::Autopilot::AutopilotTime::CalculateTimeDelta(&SystemTimeAsFileTime, &FileTime, v56);
      MaximumAllowedTimeDriftInMinutes = Microsoft::Windows::Autopilot::AutopilotTime::GetMaximumAllowedTimeDriftInMinutes();
      v61 = MaximumAllowedTimeDriftInMinutes;
      v62 = -v59;
      if ( v59 > 0 )
        v62 = v59;
      if ( v62 >= MaximumAllowedTimeDriftInMinutes )
      {
        v110 = 0;
        hstringHeader = 0;
        hstringHeader_16 = si128;
        LOWORD(hstringHeader) = 0;
        FileTimeToSystemTime(&SystemTimeAsFileTime, &v110);
        Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&v110, &hstringHeader);
        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        {
          v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
          v64 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v109);
          McTemplateU0zzdd_EventWriteTransfer(v66, v65, v64, v63, v59, v61);
        }
        if ( SetSystemTime(&SystemTime)
          || (v70 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x5D,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
                      v69),
              v70 >= 0) )
        {
          if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(v67, AutopilotDownloadTimeSyncSucceeded, v68, 1, v114);
        }
        else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          McTemplateU0q_EventWriteTransfer(v67, AutopilotDownloadTimeSyncFailed, (unsigned int)v70);
        }
        std::wstring::_Tidy_deallocate(&hstringHeader);
      }
    }
    std::wstring::_Tidy_deallocate(v109);
  }
  if ( *((_QWORD *)this + 2)
    && (v76 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this),
        v77 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v88, L"PolicyDownloadCorrelationVector", v76),
        v78 = v77,
        v77 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v77,
      ppvc);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v78;
  }
  else
  {
    v79 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v88, v94);
    v80 = v79;
    if ( v79 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
      std::wstring::_Tidy_deallocate(v105);
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::_Tidy_deallocate(v101);
      std::wstring::_Tidy_deallocate(v99);
      std::wstring::_Tidy_deallocate(v97);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
      std::wstring::_Tidy_deallocate(v96);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v79,
        ppvc);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
      std::wstring::_Tidy_deallocate(v105);
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::_Tidy_deallocate(v101);
      std::wstring::_Tidy_deallocate(v99);
      std::wstring::_Tidy_deallocate(v97);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
      std::wstring::_Tidy_deallocate(v96);
      return v80;
    }
  }
}

```

## disassembly

```asm
0x180199ddc  mov     rax, rsp
0x180199ddf  push    rbx
0x180199de0  push    rsi
0x180199de1  push    rdi
0x180199de2  push    r12
0x180199de4  push    r13
0x180199de6  push    r14
0x180199de8  push    r15
0x180199dea  sub     rsp, 790h
0x180199df1  movaps  xmmword ptr [rax-48h], xmm6
0x180199df5  mov     rax, cs:__security_cookie
0x180199dfc  xor     rax, rsp
0x180199dff  mov     [rsp+7C8h+var_58], rax
0x180199e07  mov     r12, r9
0x180199e0a  mov     rsi, r8
0x180199e0d  mov     rbx, rdx
0x180199e10  mov     r14, rcx
0x180199e13  mov     r13, [rsp+7C8h+arg_20]
0x180199e1b  mov     rax, [rsp+7C8h+arg_30]
0x180199e23  mov     [rsp+7C8h+var_730], rax
0x180199e2b  mov     edi, 68h ; 'h'
0x180199e30  mov     r8d, edi; Size
0x180199e33  xor     edx, edx; Val
0x180199e35  lea     rcx, [rsp+7C8h+UrlComponents]; void *
0x180199e3d  call    memset_0
0x180199e42  mov     [rsp+7C8h+UrlComponents.dwStructSize], edi
0x180199e49  or      eax, 0FFFFFFFFh
0x180199e4c  mov     [rsp+7C8h+UrlComponents.dwSchemeLength], eax
0x180199e53  mov     [rsp+7C8h+UrlComponents.dwUrlPathLength], eax
0x180199e5a  xor     edx, edx; Val
0x180199e5c  mov     r8d, 200h; Size
0x180199e62  lea     rcx, [rsp+7C8h+var_468]; void *
0x180199e6a  call    memset_0
0x180199e6f  lea     rax, [rsp+7C8h+var_468]
0x180199e77  mov     [rsp+7C8h+UrlComponents.lpszHostName], rax
0x180199e7f  mov     [rsp+7C8h+UrlComponents.dwHostNameLength], 100h
0x180199e8a  mov     rcx, rbx
0x180199e8d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180199e92  lea     r9, [rsp+7C8h+UrlComponents]; lpUrlComponents
0x180199e9a  xor     r8d, r8d; dwFlags
0x180199e9d  xor     edx, edx; dwUrlLength
0x180199e9f  mov     rcx, rax; pwszUrl
0x180199ea2  call    cs:__imp_WinHttpCrackUrl
0x180199ea8  test    eax, eax
0x180199eaa  jnz     short loc_180199EC8
0x180199eac  mov     rcx, [rsp+7C8h]; this
0x180199eb4  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199ebb  lea     edx, [rdi+0Ah]; void *
0x180199ebe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180199ec3  jmp     loc_18019B184
0x180199ec8  mov     r8d, 5
0x180199ece  mov     rdx, [rsp+7C8h+UrlComponents.lpszScheme]
0x180199ed6  lea     rcx, aHttps_0; "https"
0x180199edd  call    cs:__imp__o__wcsnicmp
0x180199ee3  test    eax, eax
0x180199ee5  jnz     short loc_180199EF4
0x180199ee7  mov     edi, 1BBh
0x180199eec  mov     r15d, 800000h
0x180199ef2  jmp     short loc_180199F1D
0x180199ef4  mov     r8d, 4
0x180199efa  mov     rdx, [rsp+7C8h+UrlComponents.lpszScheme]
0x180199f02  lea     rcx, aHttp_0; "http"
0x180199f09  call    cs:__imp__o__wcsnicmp
0x180199f0f  test    eax, eax
0x180199f11  jnz     loc_18019B13B
0x180199f17  lea     edi, [rax+50h]
0x180199f1a  xor     r15d, r15d
0x180199f1d  xorps   xmm0, xmm0
0x180199f20  movups  [rsp+7C8h+var_6B8], xmm0
0x180199f28  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180199f30  movdqu  [rsp+7C8h+var_6A8], xmm6
0x180199f39  xor     eax, eax
0x180199f3b  mov     word ptr [rsp+7C8h+var_6B8], ax
0x180199f43  mov     rdx, rsi
0x180199f46  lea     rcx, [rsp+7C8h+hstringHeader]
0x180199f4e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180199f53  lea     r8, [rsp+7C8h+var_6B8]
0x180199f5b  mov     rdx, rax
0x180199f5e  call    ?AcquireMsaTicketWithRetry@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(std::wstring,std::wstring &)
0x180199f63  mov     ebx, eax
0x180199f65  xor     esi, esi
0x180199f67  test    eax, eax
0x180199f69  jns     short loc_180199F9C
0x180199f6b  mov     rcx, [rsp+7C8h]; this
0x180199f73  mov     r9d, eax; char *
0x180199f76  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199f7d  mov     edx, 8Ah; void *
0x180199f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199f87  nop
0x180199f88  lea     rcx, [rsp+7C8h+var_6B8]
0x180199f90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199f95  mov     eax, ebx
0x180199f97  jmp     loc_18019B184
0x180199f9c  mov     [rsp+7C8h+var_768], rsi
0x180199fa1  lea     rax, [rsp+7C8h+var_768]
0x180199fa6  mov     [rsp+7C8h+ppv], rax; int
0x180199fab  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180199fb2  xor     edx, edx; pUnkOuter
0x180199fb4  lea     r8d, [rdx+1]; dwClsContext
0x180199fb8  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180199fbf  call    cs:__imp_CoCreateInstance
0x180199fc5  mov     ebx, eax
0x180199fc7  test    eax, eax
0x180199fc9  jns     short loc_18019A007
0x180199fcb  mov     rcx, [rsp+7C8h]; this
0x180199fd3  mov     r9d, eax; char *
0x180199fd6  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199fdd  mov     edx, 8Dh; void *
0x180199fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199fe7  nop
0x180199fe8  lea     rcx, [rsp+7C8h+var_768]
0x180199fed  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180199ff2  nop
0x180199ff3  lea     rcx, [rsp+7C8h+var_6B8]
0x180199ffb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a000  mov     eax, ebx
0x18019a002  jmp     loc_18019B184
0x18019a007  xorps   xmm0, xmm0
0x18019a00a  movups  xmmword ptr [rsp+7C8h+var_698], xmm0
0x18019a012  movdqu  [rsp+7C8h+var_688], xmm6
0x18019a01b  mov     word ptr [rsp+7C8h+var_698], si
0x18019a023  mov     dl, 1
0x18019a025  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotRestoration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration> `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl(void)'::`2'::impl
0x18019a02c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18019a031  lea     r9, [rsp+7C8h+var_698]
0x18019a039  lea     r8, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18019a040  mov     rdx, [rsp+7C8h+var_768]
0x18019a045  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019a04a  mov     ebx, eax
0x18019a04c  test    eax, eax
0x18019a04e  jns     short loc_18019A09A
0x18019a050  mov     rcx, [rsp+7C8h]; this
0x18019a058  mov     r9d, eax; char *
0x18019a05b  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019a062  mov     edx, 93h; void *
0x18019a067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019a06c  nop
0x18019a06d  lea     rcx, [rsp+7C8h+var_698]
0x18019a075  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a07a  nop
0x18019a07b  lea     rcx, [rsp+7C8h+var_768]
0x18019a080  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019a085  nop
0x18019a086  lea     rcx, [rsp+7C8h+var_6B8]
0x18019a08e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a093  mov     eax, ebx
0x18019a095  jmp     loc_18019B184
0x18019a09a  xorps   xmm0, xmm0
0x18019a09d  movups  xmmword ptr [rsp+7C8h+var_678], xmm0
0x18019a0a5  movdqu  [rsp+7C8h+var_668], xmm6
0x18019a0ae  mov     word ptr [rsp+7C8h+var_678], si
0x18019a0b6  lea     r9, [rsp+7C8h+var_678]
0x18019a0be  lea     r8, aDevinfoMan; "./DevInfo/Man"
0x18019a0c5  mov     rdx, [rsp+7C8h+var_768]
0x18019a0ca  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019a0cf  mov     ebx, eax
0x18019a0d1  test    eax, eax
0x18019a0d3  jns     short loc_18019A12D
0x18019a0d5  mov     rcx, [rsp+7C8h]; this
0x18019a0dd  mov     r9d, eax; char *
0x18019a0e0  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019a0e7  mov     edx, 98h; void *
0x18019a0ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019a0f1  nop
0x18019a0f2  lea     rcx, [rsp+7C8h+var_678]
0x18019a0fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a0ff  nop
0x18019a100  lea     rcx, [rsp+7C8h+var_698]
0x18019a108  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a10d  nop
0x18019a10e  lea     rcx, [rsp+7C8h+var_768]
0x18019a113  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019a118  nop
0x18019a119  lea     rcx, [rsp+7C8h+var_6B8]
0x18019a121  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a126  mov     eax, ebx
0x18019a128  jmp     loc_18019B184
0x18019a12d  xorps   xmm0, xmm0
0x18019a130  movups  xmmword ptr [rsp+7C8h+var_658], xmm0
0x18019a138  movdqu  [rsp+7C8h+var_648], xmm6
0x18019a141  mov     word ptr [rsp+7C8h+var_658], si
0x18019a149  lea     r9, [rsp+7C8h+var_658]
0x18019a151  lea     r8, aDevinfoMod; "./DevInfo/Mod"
0x18019a158  mov     rdx, [rsp+7C8h+var_768]
0x18019a15d  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019a162  mov     ebx, eax
0x18019a164  test    eax, eax
0x18019a166  jns     short loc_18019A1CE
0x18019a168  mov     rcx, [rsp+7C8h]; this
0x18019a170  mov     r9d, eax; char *
0x18019a173  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019a17a  mov     edx, 9Bh; void *
0x18019a17f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019a184  nop
0x18019a185  lea     rcx, [rsp+7C8h+var_658]
0x18019a18d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a192  nop
0x18019a193  lea     rcx, [rsp+7C8h+var_678]
0x18019a19b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a1a0  nop
0x18019a1a1  lea     rcx, [rsp+7C8h+var_698]
0x18019a1a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a1ae  nop
0x18019a1af  lea     rcx, [rsp+7C8h+var_768]
0x18019a1b4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019a1b9  nop
0x18019a1ba  lea     rcx, [rsp+7C8h+var_6B8]
0x18019a1c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a1c7  mov     eax, ebx
0x18019a1c9  jmp     loc_18019B184
0x18019a1ce  xorps   xmm0, xmm0
0x18019a1d1  movups  xmmword ptr [rsp+7C8h+var_638], xmm0
0x18019a1d9  movdqu  [rsp+7C8h+var_628], xmm6
0x18019a1e2  mov     word ptr [rsp+7C8h+var_638], si
0x18019a1ea  lea     r9, [rsp+7C8h+var_638]
0x18019a1f2  lea     r8, aDevdetailSwv; "./DevDetail/SwV"
0x18019a1f9  mov     rdx, [rsp+7C8h+var_768]
0x18019a1fe  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019a203  mov     ebx, eax
0x18019a205  test    eax, eax
0x18019a207  jns     short loc_18019A27D
0x18019a209  mov     rcx, [rsp+7C8h]; this
0x18019a211  mov     r9d, eax; char *
0x18019a214  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019a21b  mov     edx, 9Eh; void *
0x18019a220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019a225  nop
0x18019a226  lea     rcx, [rsp+7C8h+var_638]
0x18019a22e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a233  nop
0x18019a234  lea     rcx, [rsp+7C8h+var_658]
0x18019a23c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a241  nop
0x18019a242  lea     rcx, [rsp+7C8h+var_678]
0x18019a24a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a24f  nop
0x18019a250  lea     rcx, [rsp+7C8h+var_698]
0x18019a258  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a25d  nop
0x18019a25e  lea     rcx, [rsp+7C8h+var_768]
0x18019a263  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019a268  nop
0x18019a269  lea     rcx, [rsp+7C8h+var_6B8]
0x18019a271  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a276  mov     eax, ebx
0x18019a278  jmp     loc_18019B184
0x18019a27d  xor     edx, edx; Val
0x18019a27f  mov     r8d, 118h; Size
0x18019a285  lea     rcx, [rsp+7C8h+VersionInformation.dwMajorVersion]; void *
0x18019a28d  call    memset_0
0x18019a292  mov     [rsp+7C8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18019a29d  lea     rcx, [rsp+7C8h+VersionInformation]; lpVersionInformation
0x18019a2a5  call    cs:__imp_GetVersionExW
0x18019a2ab  test    eax, eax
0x18019a2ad  jnz     short loc_18019A321
0x18019a2af  mov     rcx, [rsp+7C8h]; this
0x18019a2b7  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019a2be  mov     edx, 0A2h; void *
0x18019a2c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019a2c8  mov     ebx, eax
0x18019a2ca  lea     rcx, [rsp+7C8h+var_638]
0x18019a2d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a2d7  nop
0x18019a2d8  lea     rcx, [rsp+7C8h+var_658]
0x18019a2e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a2e5  nop
0x18019a2e6  lea     rcx, [rsp+7C8h+var_678]
0x18019a2ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a2f3  nop
0x18019a2f4  lea     rcx, [rsp+7C8h+var_698]
0x18019a2fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a301  nop
0x18019a302  lea     rcx, [rsp+7C8h+var_768]
0x18019a307  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019a30c  nop
0x18019a30d  lea     rcx, [rsp+7C8h+var_6B8]
0x18019a315  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a31a  mov     eax, ebx
0x18019a31c  jmp     loc_18019B184
0x18019a321  mov     [rsp+7C8h+pdwReturnedProductType], esi
0x18019a325  movzx   r9d, [rsp+7C8h+var_482]; dwSpMinorVersion
0x18019a32e  movzx   r8d, [rsp+7C8h+var_484]; dwSpMajorVersion
0x18019a337  lea     rax, [rsp+7C8h+pdwReturnedProductType]
0x18019a33c  mov     [rsp+7C8h+ppv], rax; int
0x18019a341  mov     edx, [rsp+7C8h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18019a348  mov     ecx, [rsp+7C8h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18019a34f  call    cs:__imp_GetProductInfo
0x18019a355  test    eax, eax
0x18019a357  jnz     short loc_18019A3CB
0x18019a359  mov     rcx, [rsp+7C8h]; this
0x18019a361  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019a368  mov     edx, 0AAh; void *
0x18019a36d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019a372  mov     ebx, eax
0x18019a374  lea     rcx, [rsp+7C8h+var_638]
0x18019a37c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a381  nop
0x18019a382  lea     rcx, [rsp+7C8h+var_658]
0x18019a38a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019a38f  nop
  ... truncated ...
```
