# Microsoft::Windows::Autopilot::DdsNetworkWrapper::RequestProfileJson(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18019f170`
- end: `0x1801a0580`
- name: `?RequestProfileJson@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `5136`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b4164`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067398`
- `0x180067e34`
- `0x180067e54`
- `0x18006841c`
- `0x18006e43c`
- `0x180077de0`
- `0x180080bac`
- `0x1800810f0`
- `0x180081150`
- `0x180081294`
- `0x180081cac`
- `0x180084574`
- `0x180086044`
- `0x18008a67c`
- `0x18008a9c4`
- `0x18008aecc`
- `0x18008b34c`
- `0x18008bf28`
- `0x18008c9a8`
- `0x18008f570`
- `0x18008fe3c`
- `0x1800901c0`
- `0x1800e1e8c`
- `0x18018408c`
- `0x18019d6fc`
- `0x18019d9a0`
- `0x18019eea0`
- `0x18019f0e0`
- `0x18019f170`
- `0x1801a0588`
- `0x1801a09b0`
- `0x1801a0e78`
- `0x1801b5440`
- `0x1801b5744`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18019f277`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18019f2a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18019f277`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18019f2a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019f365`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019f365`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18019ffea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18019ffea`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18019f651`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18019f651`
- `api-ms-win-core-sysinfo-l1-2-0!SetSystemTime` at `0x1801a018c`
- `api-ms-win-core-sysinfo-l1-2-0!SetSystemTime` at `0x1801a018c`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18019f701`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18019f701`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801a012a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801a012a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1801a000e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1801a000e`
- `WINHTTP!WinHttpCrackUrl` at `0x18019f236`
- `WINHTTP!WinHttpCrackUrl` at `0x18019f236`

## string_xrefs

- `0x18019fc16`: `Windows.Data.Json.JsonObject`
- `0x18019f24e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f31c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f382`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f407`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f48c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f51f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f5c0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f669`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f719`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f7c7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019f8df`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019fa41`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019fb6b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019fc51`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019fd12`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019fdd0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019ff42`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a002a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a0261`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a0349`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a0400`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a053b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a01a6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`

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
  unsigned int v44; // ebx
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
  LPVOID *ppvc; // [rsp+20h] [rbp-7A8h]
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
  char v114; // [rsp+350h] [rbp-478h] BYREF
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
      (int)ppvc);
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
  v44 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(this, &lpMultiByteStr);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v44) )
  {
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v44;
  }
  if ( (v44 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)v44,
      (int)ppvc);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&lpMultiByteStr);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v97);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v87);
    std::wstring::_Tidy_deallocate(v96);
    return v44;
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
        (int)ppvc);
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
        (int)ppvc);
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
        (int)ppvc);
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
          (int)ppvc);
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
          (int)ppvc);
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
          {
            ppvc = (LPVOID *)&v114;
            McGenEventWrite_EventWriteTransfer(v67, AutopilotDownloadTimeSyncSucceeded, v68, 1);
          }
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
      (int)ppvc);
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
        (int)ppvc);
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
0x18019f170  mov     rax, rsp
0x18019f173  push    rbx
0x18019f174  push    rsi
0x18019f175  push    rdi
0x18019f176  push    r12
0x18019f178  push    r13
0x18019f17a  push    r14
0x18019f17c  push    r15
0x18019f17e  sub     rsp, 790h
0x18019f185  movaps  xmmword ptr [rax-48h], xmm6
0x18019f189  mov     rax, cs:__security_cookie
0x18019f190  xor     rax, rsp
0x18019f193  mov     [rsp+7C8h+var_58], rax
0x18019f19b  mov     r12, r9
0x18019f19e  mov     rsi, r8
0x18019f1a1  mov     rbx, rdx
0x18019f1a4  mov     r14, rcx
0x18019f1a7  mov     r13, [rsp+7C8h+arg_20]
0x18019f1af  mov     rax, [rsp+7C8h+arg_30]
0x18019f1b7  mov     [rsp+7C8h+var_730], rax
0x18019f1bf  mov     edi, 68h ; 'h'
0x18019f1c4  mov     r8d, edi; Size
0x18019f1c7  xor     edx, edx; Val
0x18019f1c9  lea     rcx, [rsp+7C8h+UrlComponents]; void *
0x18019f1d1  call    memset_0
0x18019f1d6  mov     [rsp+7C8h+UrlComponents.dwStructSize], edi
0x18019f1dd  or      eax, 0FFFFFFFFh
0x18019f1e0  mov     [rsp+7C8h+UrlComponents.dwSchemeLength], eax
0x18019f1e7  mov     [rsp+7C8h+UrlComponents.dwUrlPathLength], eax
0x18019f1ee  xor     edx, edx; Val
0x18019f1f0  mov     r8d, 200h; Size
0x18019f1f6  lea     rcx, [rsp+7C8h+var_468]; void *
0x18019f1fe  call    memset_0
0x18019f203  lea     rax, [rsp+7C8h+var_468]
0x18019f20b  mov     [rsp+7C8h+UrlComponents.lpszHostName], rax
0x18019f213  mov     [rsp+7C8h+UrlComponents.dwHostNameLength], 100h
0x18019f21e  mov     rcx, rbx
0x18019f221  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019f226  lea     r9, [rsp+7C8h+UrlComponents]; lpUrlComponents
0x18019f22e  xor     r8d, r8d; dwFlags
0x18019f231  xor     edx, edx; dwUrlLength
0x18019f233  mov     rcx, rax; pwszUrl
0x18019f236  call    cs:__imp_WinHttpCrackUrl
0x18019f23d  nop     dword ptr [rax+rax+00h]
0x18019f242  test    eax, eax
0x18019f244  jnz     short loc_18019F262
0x18019f246  mov     rcx, [rsp+7C8h]; this
0x18019f24e  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f255  lea     edx, [rdi+0Ah]; void *
0x18019f258  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019f25d  jmp     loc_1801A0554
0x18019f262  mov     r8d, 5
0x18019f268  mov     rdx, [rsp+7C8h+UrlComponents.lpszScheme]
0x18019f270  lea     rcx, aHttps_0; "https"
0x18019f277  call    cs:__imp__o__wcsnicmp
0x18019f27e  nop     dword ptr [rax+rax+00h]
0x18019f283  test    eax, eax
0x18019f285  jnz     short loc_18019F294
0x18019f287  mov     edi, 1BBh
0x18019f28c  mov     r15d, 800000h
0x18019f292  jmp     short loc_18019F2C3
0x18019f294  mov     r8d, 4
0x18019f29a  mov     rdx, [rsp+7C8h+UrlComponents.lpszScheme]
0x18019f2a2  lea     rcx, aHttp_0; "http"
0x18019f2a9  call    cs:__imp__o__wcsnicmp
0x18019f2b0  nop     dword ptr [rax+rax+00h]
0x18019f2b5  test    eax, eax
0x18019f2b7  jnz     loc_1801A050B
0x18019f2bd  lea     edi, [rax+50h]
0x18019f2c0  xor     r15d, r15d
0x18019f2c3  xorps   xmm0, xmm0
0x18019f2c6  movups  [rsp+7C8h+var_6B8], xmm0
0x18019f2ce  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18019f2d6  movdqu  [rsp+7C8h+var_6A8], xmm6
0x18019f2df  xor     eax, eax
0x18019f2e1  mov     word ptr [rsp+7C8h+var_6B8], ax
0x18019f2e9  mov     rdx, rsi
0x18019f2ec  lea     rcx, [rsp+7C8h+hstringHeader]
0x18019f2f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18019f2f9  lea     r8, [rsp+7C8h+var_6B8]
0x18019f301  mov     rdx, rax
0x18019f304  call    ?AcquireMsaTicketWithRetry@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(std::wstring,std::wstring &)
0x18019f309  mov     ebx, eax
0x18019f30b  xor     esi, esi
0x18019f30d  test    eax, eax
0x18019f30f  jns     short loc_18019F342
0x18019f311  mov     rcx, [rsp+7C8h]; this
0x18019f319  mov     r9d, eax; char *
0x18019f31c  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f323  mov     edx, 8Ah; void *
0x18019f328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f32d  nop
0x18019f32e  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f336  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f33b  mov     eax, ebx
0x18019f33d  jmp     loc_1801A0554
0x18019f342  mov     [rsp+7C8h+var_768], rsi
0x18019f347  lea     rax, [rsp+7C8h+var_768]
0x18019f34c  mov     [rsp+7C8h+ppv], rax; int
0x18019f351  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18019f358  xor     edx, edx; pUnkOuter
0x18019f35a  lea     r8d, [rdx+1]; dwClsContext
0x18019f35e  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18019f365  call    cs:__imp_CoCreateInstance
0x18019f36c  nop     dword ptr [rax+rax+00h]
0x18019f371  mov     ebx, eax
0x18019f373  test    eax, eax
0x18019f375  jns     short loc_18019F3B3
0x18019f377  mov     rcx, [rsp+7C8h]; this
0x18019f37f  mov     r9d, eax; char *
0x18019f382  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f389  mov     edx, 8Dh; void *
0x18019f38e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f393  nop
0x18019f394  lea     rcx, [rsp+7C8h+var_768]
0x18019f399  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f39e  nop
0x18019f39f  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f3a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f3ac  mov     eax, ebx
0x18019f3ae  jmp     loc_1801A0554
0x18019f3b3  xorps   xmm0, xmm0
0x18019f3b6  movups  xmmword ptr [rsp+7C8h+var_698], xmm0
0x18019f3be  movdqu  [rsp+7C8h+var_688], xmm6
0x18019f3c7  mov     word ptr [rsp+7C8h+var_698], si
0x18019f3cf  mov     dl, 1
0x18019f3d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotRestoration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration> `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl(void)'::`2'::impl
0x18019f3d8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18019f3dd  lea     r9, [rsp+7C8h+var_698]
0x18019f3e5  lea     r8, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18019f3ec  mov     rdx, [rsp+7C8h+var_768]
0x18019f3f1  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019f3f6  mov     ebx, eax
0x18019f3f8  test    eax, eax
0x18019f3fa  jns     short loc_18019F446
0x18019f3fc  mov     rcx, [rsp+7C8h]; this
0x18019f404  mov     r9d, eax; char *
0x18019f407  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f40e  mov     edx, 93h; void *
0x18019f413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f418  nop
0x18019f419  lea     rcx, [rsp+7C8h+var_698]
0x18019f421  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f426  nop
0x18019f427  lea     rcx, [rsp+7C8h+var_768]
0x18019f42c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f431  nop
0x18019f432  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f43a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f43f  mov     eax, ebx
0x18019f441  jmp     loc_1801A0554
0x18019f446  xorps   xmm0, xmm0
0x18019f449  movups  xmmword ptr [rsp+7C8h+var_678], xmm0
0x18019f451  movdqu  [rsp+7C8h+var_668], xmm6
0x18019f45a  mov     word ptr [rsp+7C8h+var_678], si
0x18019f462  lea     r9, [rsp+7C8h+var_678]
0x18019f46a  lea     r8, aDevinfoMan; "./DevInfo/Man"
0x18019f471  mov     rdx, [rsp+7C8h+var_768]
0x18019f476  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019f47b  mov     ebx, eax
0x18019f47d  test    eax, eax
0x18019f47f  jns     short loc_18019F4D9
0x18019f481  mov     rcx, [rsp+7C8h]; this
0x18019f489  mov     r9d, eax; char *
0x18019f48c  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f493  mov     edx, 98h; void *
0x18019f498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f49d  nop
0x18019f49e  lea     rcx, [rsp+7C8h+var_678]
0x18019f4a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f4ab  nop
0x18019f4ac  lea     rcx, [rsp+7C8h+var_698]
0x18019f4b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f4b9  nop
0x18019f4ba  lea     rcx, [rsp+7C8h+var_768]
0x18019f4bf  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f4c4  nop
0x18019f4c5  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f4cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f4d2  mov     eax, ebx
0x18019f4d4  jmp     loc_1801A0554
0x18019f4d9  xorps   xmm0, xmm0
0x18019f4dc  movups  xmmword ptr [rsp+7C8h+var_658], xmm0
0x18019f4e4  movdqu  [rsp+7C8h+var_648], xmm6
0x18019f4ed  mov     word ptr [rsp+7C8h+var_658], si
0x18019f4f5  lea     r9, [rsp+7C8h+var_658]
0x18019f4fd  lea     r8, aDevinfoMod; "./DevInfo/Mod"
0x18019f504  mov     rdx, [rsp+7C8h+var_768]
0x18019f509  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019f50e  mov     ebx, eax
0x18019f510  test    eax, eax
0x18019f512  jns     short loc_18019F57A
0x18019f514  mov     rcx, [rsp+7C8h]; this
0x18019f51c  mov     r9d, eax; char *
0x18019f51f  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f526  mov     edx, 9Bh; void *
0x18019f52b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f530  nop
0x18019f531  lea     rcx, [rsp+7C8h+var_658]
0x18019f539  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f53e  nop
0x18019f53f  lea     rcx, [rsp+7C8h+var_678]
0x18019f547  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f54c  nop
0x18019f54d  lea     rcx, [rsp+7C8h+var_698]
0x18019f555  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f55a  nop
0x18019f55b  lea     rcx, [rsp+7C8h+var_768]
0x18019f560  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f565  nop
0x18019f566  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f56e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f573  mov     eax, ebx
0x18019f575  jmp     loc_1801A0554
0x18019f57a  xorps   xmm0, xmm0
0x18019f57d  movups  xmmword ptr [rsp+7C8h+var_638], xmm0
0x18019f585  movdqu  [rsp+7C8h+var_628], xmm6
0x18019f58e  mov     word ptr [rsp+7C8h+var_638], si
0x18019f596  lea     r9, [rsp+7C8h+var_638]
0x18019f59e  lea     r8, aDevdetailSwv; "./DevDetail/SwV"
0x18019f5a5  mov     rdx, [rsp+7C8h+var_768]
0x18019f5aa  call    ?LookupValueFromCsp@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEAUIConfigManager2@@QEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::LookupValueFromCsp(IConfigManager2 *,ushort * const,std::wstring &)
0x18019f5af  mov     ebx, eax
0x18019f5b1  test    eax, eax
0x18019f5b3  jns     short loc_18019F629
0x18019f5b5  mov     rcx, [rsp+7C8h]; this
0x18019f5bd  mov     r9d, eax; char *
0x18019f5c0  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f5c7  mov     edx, 9Eh; void *
0x18019f5cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f5d1  nop
0x18019f5d2  lea     rcx, [rsp+7C8h+var_638]
0x18019f5da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f5df  nop
0x18019f5e0  lea     rcx, [rsp+7C8h+var_658]
0x18019f5e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f5ed  nop
0x18019f5ee  lea     rcx, [rsp+7C8h+var_678]
0x18019f5f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f5fb  nop
0x18019f5fc  lea     rcx, [rsp+7C8h+var_698]
0x18019f604  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f609  nop
0x18019f60a  lea     rcx, [rsp+7C8h+var_768]
0x18019f60f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f614  nop
0x18019f615  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f61d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f622  mov     eax, ebx
0x18019f624  jmp     loc_1801A0554
0x18019f629  xor     edx, edx; Val
0x18019f62b  mov     r8d, 118h; Size
0x18019f631  lea     rcx, [rsp+7C8h+VersionInformation.dwMajorVersion]; void *
0x18019f639  call    memset_0
0x18019f63e  mov     [rsp+7C8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18019f649  lea     rcx, [rsp+7C8h+VersionInformation]; lpVersionInformation
0x18019f651  call    cs:__imp_GetVersionExW
0x18019f658  nop     dword ptr [rax+rax+00h]
0x18019f65d  test    eax, eax
0x18019f65f  jnz     short loc_18019F6D3
0x18019f661  mov     rcx, [rsp+7C8h]; this
0x18019f669  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f670  mov     edx, 0A2h; void *
0x18019f675  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019f67a  mov     ebx, eax
0x18019f67c  lea     rcx, [rsp+7C8h+var_638]
0x18019f684  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f689  nop
0x18019f68a  lea     rcx, [rsp+7C8h+var_658]
0x18019f692  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f697  nop
0x18019f698  lea     rcx, [rsp+7C8h+var_678]
0x18019f6a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f6a5  nop
0x18019f6a6  lea     rcx, [rsp+7C8h+var_698]
0x18019f6ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f6b3  nop
0x18019f6b4  lea     rcx, [rsp+7C8h+var_768]
0x18019f6b9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f6be  nop
0x18019f6bf  lea     rcx, [rsp+7C8h+var_6B8]
0x18019f6c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f6cc  mov     eax, ebx
0x18019f6ce  jmp     loc_1801A0554
0x18019f6d3  mov     [rsp+7C8h+pdwReturnedProductType], esi
0x18019f6d7  movzx   r9d, [rsp+7C8h+var_482]; dwSpMinorVersion
0x18019f6e0  movzx   r8d, [rsp+7C8h+var_484]; dwSpMajorVersion
0x18019f6e9  lea     rax, [rsp+7C8h+pdwReturnedProductType]
0x18019f6ee  mov     [rsp+7C8h+ppv], rax; int
0x18019f6f3  mov     edx, [rsp+7C8h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18019f6fa  mov     ecx, [rsp+7C8h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18019f701  call    cs:__imp_GetProductInfo
0x18019f708  nop     dword ptr [rax+rax+00h]
0x18019f70d  test    eax, eax
0x18019f70f  jnz     short loc_18019F783
0x18019f711  mov     rcx, [rsp+7C8h]; this
0x18019f719  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f720  mov     edx, 0AAh; void *
0x18019f725  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019f72a  mov     ebx, eax
  ... truncated ...
```
