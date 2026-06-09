# ModernDeployment::Autopilot::Core::DeviceLinkManager::AcquireEnrollmentDiscoveryEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo> &)

- ea: `0x18012c798`
- end: `0x18012dec7`
- name: `?AcquireEnrollmentDiscoveryEndpoint@DeviceLinkManager@Core@Autopilot@ModernDeployment@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@@Z`
- size: `5935`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012bbc8`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006cb94`
- `0x180073768`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081f38`
- `0x180084574`
- `0x180086044`
- `0x180089660`
- `0x180089850`
- `0x18008a9c4`
- `0x18008aecc`
- `0x18008d290`
- `0x18008edec`
- `0x18008f570`
- `0x1800901c0`
- `0x1800a29e0`
- `0x1800a4890`
- `0x1800d04fc`
- `0x1800e1e8c`
- `0x1801048f4`
- `0x18012a398`
- `0x18012a598`
- `0x18012a9a8`
- `0x18012c798`
- `0x18012e754`
- `0x18012f804`
- `0x18012fb98`
- `0x180131cb4`
- `0x180138d20`
- `0x1801391f8`
- `0x18013ebb0`
- `0x18013f340`
- `0x180147720`
- `0x1801a4a04`
- `0x1801a4b1c`
- `0x1801a5204`
- `0x1801a534c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012ceee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012dcdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012dd03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012ceee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012dcdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012dd03`

## string_xrefs

- `0x18012cc64`: `Windows.Data.Json.JsonObject`
- `0x18012cc07`: `X-DeviceLinkInfo`
- `0x18012cb7a`: `application/json`
- `0x18012d48f`: `application/json`
- `0x18012c7ef`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012c864`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012c8f6`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012c9c5`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012ca50`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012cad5`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012cca9`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012cd7d`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012ce46`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012cf60`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012d159`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012d39a`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012d555`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012d5e9`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012d7b0`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012d927`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012da7c`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012dbb6`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012cd4d`: `deviceLinkInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkManager::AcquireEnrollmentDiscoveryEndpoint(
        __int64 a1,
        _BYTE *a2,
        __int64 a3)
{
  const unsigned __int16 *v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __m128i si128; // xmm6
  int LinkIdInfo; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int HttpAgentVersionString; // eax
  unsigned int v16; // ebx
  int DeviceLinkPreassociateDiscoveryUrl; // eax
  unsigned int v18; // ebx
  int DiscoveryDeviceLinkRequestLocation; // eax
  unsigned int v20; // ebx
  char v21; // si
  char v22; // bl
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // edi
  int v28; // ebx
  const unsigned __int16 *v29; // rax
  int v30; // eax
  unsigned int v31; // edi
  int v32; // eax
  unsigned int v33; // edi
  PCWSTR StringRawBuffer; // rdx
  int v35; // eax
  unsigned int v36; // edi
  _BYTE *v37; // rcx
  int v38; // ebx
  int v39; // eax
  int v40; // ecx
  __int64 *v41; // r14
  __int64 v42; // rbx
  __int64 v43; // rsi
  __int64 v44; // rax
  int v45; // eax
  unsigned int v46; // ebx
  int v47; // eax
  unsigned int v48; // ebx
  __int64 v49; // rax
  __int64 v50; // rdi
  int v51; // ebx
  int v52; // eax
  __int64 v53; // rax
  int v54; // ebx
  __int64 v55; // rdi
  int v56; // ebx
  int v57; // eax
  int DiscoveryUrlFromResponseJsonString; // eax
  unsigned int v59; // ebx
  int v60; // eax
  unsigned int v61; // ebx
  int v62; // eax
  unsigned int v63; // ebx
  unsigned int v64; // ebx
  PCWSTR v65; // rax
  PCWSTR v66; // rax
  __int64 v67; // rdi
  int v68; // ebx
  int v69; // eax
  int v70; // [rsp+20h] [rbp-348h]
  const char *v71; // [rsp+20h] [rbp-348h]
  int v72; // [rsp+20h] [rbp-348h]
  unsigned int v73; // [rsp+70h] [rbp-2F8h] BYREF
  _DWORD v74[3]; // [rsp+74h] [rbp-2F4h] BYREF
  HSTRING v75; // [rsp+80h] [rbp-2E8h] BYREF
  _BYTE v76[32]; // [rsp+88h] [rbp-2E0h] BYREF
  int v77; // [rsp+A8h] [rbp-2C0h] BYREF
  struct Windows::Data::Json::IJsonObject *v78; // [rsp+B0h] [rbp-2B8h] BYREF
  _BYTE v79[16]; // [rsp+B8h] [rbp-2B0h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-2A0h] BYREF
  unsigned int v81; // [rsp+D0h] [rbp-298h]
  HSTRING v82; // [rsp+D8h] [rbp-290h] BYREF
  HSTRING v83; // [rsp+E0h] [rbp-288h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-280h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-278h]
  _OWORD v86[2]; // [rsp+F8h] [rbp-270h] BYREF
  _OWORD v87[2]; // [rsp+118h] [rbp-250h] BYREF
  _OWORD v88[2]; // [rsp+138h] [rbp-230h] BYREF
  _OWORD v89[2]; // [rsp+158h] [rbp-210h] BYREF
  _OWORD v90[2]; // [rsp+178h] [rbp-1F0h] BYREF
  _BYTE v91[16]; // [rsp+198h] [rbp-1D0h] BYREF
  __int64 v92; // [rsp+1A8h] [rbp-1C0h]
  _OWORD v93[2]; // [rsp+1B8h] [rbp-1B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1D8h] [rbp-190h] BYREF
  __int64 v95; // [rsp+1F0h] [rbp-178h]
  _BYTE v96[32]; // [rsp+1F8h] [rbp-170h] BYREF
  _OWORD v97[2]; // [rsp+218h] [rbp-150h] BYREF
  _BYTE v98[32]; // [rsp+238h] [rbp-130h] BYREF
  _BYTE v99[40]; // [rsp+258h] [rbp-110h] BYREF
  _BYTE v100[80]; // [rsp+280h] [rbp-E8h] BYREF
  _BYTE v101[32]; // [rsp+2D0h] [rbp-98h] BYREF
  _BYTE v102[32]; // [rsp+2F0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80004001LL,
      v70);
    return 2147500033LL;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
  v77 = 0;
  v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 128);
  Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
    (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100,
    v7,
    L"AcquireEnrollmentDiscoveryEndpoint",
    &v77);
  v8 = ModernDeployment::Autopilot::Core::TpmOperations::Initialize(*(ModernDeployment::Autopilot::Core::TpmOperations **)(a1 + 72));
  v10 = v8;
  v77 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)v8,
      v70);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v10;
  }
  v86[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v86[1] = si128;
  LOWORD(v86[0]) = 0;
  v88[0] = 0;
  v88[1] = si128;
  LOWORD(v88[0]) = 0;
  LinkIdInfo = ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(v9, v86, v88);
  v13 = LinkIdInfo;
  v77 = LinkIdInfo;
  if ( LinkIdInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)LinkIdInfo,
      v70);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v13;
  }
  if ( (unsigned __int8)ModernDeployment::Autopilot::Core::IsDeviceLinkEndpointsOverrideOrCacheAvailable(v86, a3) )
  {
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return 0;
  }
  v89[0] = 0;
  v89[1] = si128;
  LOWORD(v89[0]) = 0;
  HttpAgentVersionString = Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(1, v14, v89);
  v16 = HttpAgentVersionString;
  v77 = HttpAgentVersionString;
  if ( HttpAgentVersionString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)HttpAgentVersionString,
      v70);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v16;
  }
  v87[0] = 0;
  v87[1] = si128;
  LOWORD(v87[0]) = 0;
  DeviceLinkPreassociateDiscoveryUrl = Microsoft::Windows::Autopilot::DeviceLinkPolicyManager::GetDeviceLinkPreassociateDiscoveryUrl(v87);
  v18 = DeviceLinkPreassociateDiscoveryUrl;
  if ( DeviceLinkPreassociateDiscoveryUrl < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)DeviceLinkPreassociateDiscoveryUrl,
      v70);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v18;
  }
  v73 = 0;
  DiscoveryDeviceLinkRequestLocation = ModernDeployment::Autopilot::Core::AutopilotConfig::GetDiscoveryDeviceLinkRequestLocation(&v73);
  v20 = DiscoveryDeviceLinkRequestLocation;
  v77 = DiscoveryDeviceLinkRequestLocation;
  if ( DiscoveryDeviceLinkRequestLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)DiscoveryDeviceLinkRequestLocation,
      v70);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v20;
  }
  v21 = v73;
  v22 = v73;
  if ( v73 - 1 > 2 )
    v22 = 1;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v79);
  std::wstring::wstring(&hstringHeader, L"Content-Type");
  v23 = std::map<std::wstring,std::wstring>::operator[](v79, &hstringHeader);
  std::wstring::assign(v23, L"application/json");
  std::wstring::_Tidy_deallocate(&hstringHeader);
  (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 40) + 32LL))(*(_QWORD *)(a1 + 40), v91);
  if ( v92 )
  {
    std::wstring::wstring(&hstringHeader, L"X-APCV");
    v24 = std::map<std::wstring,std::wstring>::operator[](v79, &hstringHeader);
    std::wstring::operator=(v24, v91);
    std::wstring::_Tidy_deallocate(&hstringHeader);
  }
  if ( (v22 & 1) != 0 )
  {
    std::wstring::wstring(&hstringHeader, L"X-DeviceLinkInfo");
    v25 = std::map<std::wstring,std::wstring>::operator[](v79, &hstringHeader);
    std::wstring::operator=(v25, a2);
    std::wstring::_Tidy_deallocate(&hstringHeader);
  }
  v78 = 0;
  v95 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v26 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v95, &v78);
  v27 = v26;
  v77 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)v26,
      v70);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    std::wstring::_Tidy_deallocate(v91);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v79,
      v79);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v27;
  }
  v28 = v22 & 2;
  if ( v28 )
  {
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v30 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v78, L"deviceLinkInfo", v29);
    v31 = v30;
    v77 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
        (const char *)(unsigned int)v30,
        v70);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      std::wstring::_Tidy_deallocate(v91);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v79,
        v79);
      std::wstring::_Tidy_deallocate(v87);
      std::wstring::_Tidy_deallocate(v89);
      std::wstring::_Tidy_deallocate(v88);
      std::wstring::_Tidy_deallocate(v86);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
      return v31;
    }
  }
  string = 0;
  v32 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v78, &string);
  v33 = v32;
  v77 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)v32,
      v70);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    std::wstring::_Tidy_deallocate(v91);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v79,
      v79);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v33;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v96, StringRawBuffer);
  v90[0] = 0;
  v90[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v90[0]) = 0;
  v35 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(v96, v90);
  v36 = v35;
  v77 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)v35,
      v70);
    std::string::_Tidy_deallocate(v90);
    std::wstring::_Tidy_deallocate(v96);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    std::wstring::_Tidy_deallocate(v91);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v79,
      v79);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v36;
  }
  if ( v28 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v37 = v96;
      goto LABEL_35;
    }
  }
  else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    v37 = a2;
LABEL_35:
    v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v87);
    McTemplateU0zzd_EventWriteTransfer(v40, (unsigned int)RequestDeviceLinkUrl, v39, v38, v21);
  }
  v84 = 0;
  v85 = 0;
  v81 = 0;
  v93[0] = 0;
  v93[1] = si128;
  LOWORD(v93[0]) = 0;
  v41 = *(__int64 **)(a1 + 40);
  v42 = *v41;
  std::_String_val<std::_Simple_types<char>>::_Myptr(v90);
  v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v87);
  v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v89);
  v71 = L"HTTP/1.1";
  v45 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD))(v42 + 8))(v41, v44, v43, 0);
  v46 = v45;
  v77 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)v45,
      (int)L"HTTP/1.1");
    std::wstring::_Tidy_deallocate(v93);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
    std::string::_Tidy_deallocate(v90);
    std::wstring::_Tidy_deallocate(v96);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    std::wstring::_Tidy_deallocate(v91);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v79,
      v79);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v46;
  }
  (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 40) + 32LL))(*(_QWORD *)(a1 + 40), v99);
  (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 40) + 40LL))(*(_QWORD *)(a1 + 40), v98);
  if ( v81 == 200 )
    goto LABEL_43;
  v47 = ModernDeployment::Autopilot::Core::ProcessFailedRequest(v81, v99, v98, &v84);
  v48 = v47;
  v77 = v47;
  if ( v47 == -2130460659 )
  {
    std::wstring::_Tidy_deallocate(v98);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v93);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
    std::string::_Tidy_deallocate(v90);
    std::wstring::_Tidy_deallocate(v96);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    std::wstring::_Tidy_deallocate(v91);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v79,
      v79);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return 2164506637LL;
  }
  if ( v47 >= 0 )
  {
LABEL_43:
    if ( std::wstring::find(v93, L"application/json", 0) == -1 )
    {
      v49 = std::operator+<unsigned short>(v76, L"Unexpected response - content type mismatch (", v93);
      std::operator+<unsigned short>(&hstringHeader, v49, L")");
      std::wstring::_Tidy_deallocate(v76);
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
        v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v98);
        v52 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v99);
        McTemplateU0zzzd_EventWriteTransfer(v81, (unsigned int)RequestDeviceLinkUrlFailed, v52, v51, v50, v81);
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
        (const char *)0x8103C012LL,
        (int)v71);
      std::wstring::_Tidy_deallocate(&hstringHeader);
    }
    v97[0] = 0;
    v97[1] = si128;
    LOWORD(v97[0]) = 0;
    v53 = std::string::string(v76, v84, v84 + v85);
    v54 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::Utf8ToUnicode(v53, v97);
    v77 = v54;
    std::string::_Tidy_deallocate(v76);
    if ( v54 >= 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      {
        v55 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v97);
        v56 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v98);
        v57 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v99);
        McTemplateU0zzzd_EventWriteTransfer(v81, (unsigned int)RequestDeviceLinkUrlSucceeded, v57, v56, v55, v81);
      }
      v73 = 0;
      v83 = 0;
      v82 = 0;
      v74[0] = 0;
      DiscoveryUrlFromResponseJsonString = ModernDeployment::Autopilot::Core::ExtractDiscoveryUrlFromResponseJsonString(
                                             (unsigned int)v97,
                                             (unsigned int)v86,
                                             (unsigned int)&v83,
                                             (unsigned int)&v82,
                                             (__int64)&v73,
                                             (__int64)v74);
      v59 = DiscoveryUrlFromResponseJsonString;
      v77 = DiscoveryUrlFromResponseJsonString;
      if ( DiscoveryUrlFromResponseJsonString >= 0 )
      {
        *(_QWORD *)&v74[1] = v82;
        v75 = v83;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
        v60 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::DiscoveryUrlRequestInfo,ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo,HSTRING__ *,HSTRING__ *,enum ModernDeployment::Autopilot::Core::DiscoveryUrlRequestResult &>(
                a3,
                &v75,
                &v74[1],
                &v73);
        v61 = v60;
        v77 = v60;
        if ( v60 >= 0 )
        {
          v62 = ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteCachedDiscoveryInfo(v86, &v83, &v82);
          v63 = v62;
          v77 = v62;
          if ( v62 >= 0 )
          {
            v64 = v74[0];
            v77 = v74[0];
            if ( v74[0] >= 0 )
            {
              v65 = WindowsGetStringRawBuffer(v83, 0);
              std::wstring::wstring(v102, v65);
              v66 = WindowsGetStringRawBuffer(v82, 0);
              std::wstring::wstring(v101, v66);
              if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
              {
                v67 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v86);
                v68 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v101);
                v69 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v102);
                McTemplateU0zzzd_EventWriteTransfer(v73, (unsigned int)RequestDeviceLinkUrlResult, v69, v68, v67, v73);
              }
              std::wstring::_Tidy_deallocate(v101);
              std::wstring::_Tidy_deallocate(v102);
              Windows::Internal::String::~String((Windows::Internal::String *)&v82);
              Windows::Internal::String::~String((Windows::Internal::String *)&v83);
              std::wstring::_Tidy_deallocate(v97);
              std::wstring::_Tidy_deallocate(v98);
              std::wstring::_Tidy_deallocate(v99);
              std::wstring::_Tidy_deallocate(v93);
              wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
              std::string::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
              std::wstring::_Tidy_deallocate(v91);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v79,
                v79);
              std::wstring::_Tidy_deallocate(v87);
              std::wstring::_Tidy_deallocate(v89);
              std::wstring::_Tidy_deallocate(v88);
              std::wstring::_Tidy_deallocate(v86);
              Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x155,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
                (const char *)v74[0],
                v72);
              Windows::Internal::String::~String((Windows::Internal::String *)&v82);
              Windows::Internal::String::~String((Windows::Internal::String *)&v83);
              std::wstring::_Tidy_deallocate(v97);
              std::wstring::_Tidy_deallocate(v98);
              std::wstring::_Tidy_deallocate(v99);
              std::wstring::_Tidy_deallocate(v93);
              wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
              std::string::_Tidy_deallocate(v90);
              std::wstring::_Tidy_deallocate(v96);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
              std::wstring::_Tidy_deallocate(v91);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v79,
                v79);
              std::wstring::_Tidy_deallocate(v87);
              std::wstring::_Tidy_deallocate(v89);
              std::wstring::_Tidy_deallocate(v88);
              std::wstring::_Tidy_deallocate(v86);
              Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
              return v64;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x154,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
              (const char *)(unsigned int)v62,
              v72);
            Windows::Internal::String::~String((Windows::Internal::String *)&v82);
            Windows::Internal::String::~String((Windows::Internal::String *)&v83);
            std::wstring::_Tidy_deallocate(v97);
            std::wstring::_Tidy_deallocate(v98);
            std::wstring::_Tidy_deallocate(v99);
            std::wstring::_Tidy_deallocate(v93);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
            std::string::_Tidy_deallocate(v90);
            std::wstring::_Tidy_deallocate(v96);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
            std::wstring::_Tidy_deallocate(v91);
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
              v79,
              v79);
            std::wstring::_Tidy_deallocate(v87);
            std::wstring::_Tidy_deallocate(v89);
            std::wstring::_Tidy_deallocate(v88);
            std::wstring::_Tidy_deallocate(v86);
            Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
            return v63;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x151,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
            (const char *)(unsigned int)v60,
            v72);
          Windows::Internal::String::~String((Windows::Internal::String *)&v82);
          Windows::Internal::String::~String((Windows::Internal::String *)&v83);
          std::wstring::_Tidy_deallocate(v97);
          std::wstring::_Tidy_deallocate(v98);
          std::wstring::_Tidy_deallocate(v99);
          std::wstring::_Tidy_deallocate(v93);
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
          std::string::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v96);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
          std::wstring::_Tidy_deallocate(v91);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v79,
            v79);
          std::wstring::_Tidy_deallocate(v87);
          std::wstring::_Tidy_deallocate(v89);
          std::wstring::_Tidy_deallocate(v88);
          std::wstring::_Tidy_deallocate(v86);
          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
          return v61;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
          (const char *)(unsigned int)DiscoveryUrlFromResponseJsonString,
          v72);
        Windows::Internal::String::~String((Windows::Internal::String *)&v82);
        Windows::Internal::String::~String((Windows::Internal::String *)&v83);
        std::wstring::_Tidy_deallocate(v97);
        std::wstring::_Tidy_deallocate(v98);
        std::wstring::_Tidy_deallocate(v99);
        std::wstring::_Tidy_deallocate(v93);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
        std::string::_Tidy_deallocate(v90);
        std::wstring::_Tidy_deallocate(v96);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
        std::wstring::_Tidy_deallocate(v91);
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
          v79,
          v79);
        std::wstring::_Tidy_deallocate(v87);
        std::wstring::_Tidy_deallocate(v89);
        std::wstring::_Tidy_deallocate(v88);
        std::wstring::_Tidy_deallocate(v86);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
        return v59;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
        (const char *)(unsigned int)v54,
        (int)v71);
      std::wstring::_Tidy_deallocate(v97);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::_Tidy_deallocate(v99);
      std::wstring::_Tidy_deallocate(v93);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
      std::string::_Tidy_deallocate(v90);
      std::wstring::_Tidy_deallocate(v96);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      std::wstring::_Tidy_deallocate(v91);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v79,
        v79);
      std::wstring::_Tidy_deallocate(v87);
      std::wstring::_Tidy_deallocate(v89);
      std::wstring::_Tidy_deallocate(v88);
      std::wstring::_Tidy_deallocate(v86);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
      return (unsigned int)v54;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)(unsigned int)v47,
      (int)L"HTTP/1.1");
    std::wstring::_Tidy_deallocate(v98);
    std::wstring::_Tidy_deallocate(v99);
    std::wstring::_Tidy_deallocate(v93);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v84);
    std::string::_Tidy_deallocate(v90);
    std::wstring::_Tidy_deallocate(v96);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    std::wstring::_Tidy_deallocate(v91);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v79,
      v79);
    std::wstring::_Tidy_deallocate(v87);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v86);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v100);
    return v48;
  }
}

```

## disassembly

```asm
0x18012c798  mov     rax, rsp
0x18012c79b  push    rbx
0x18012c79c  push    rsi
0x18012c79d  push    rdi
0x18012c79e  push    r12
0x18012c7a0  push    r13
0x18012c7a2  push    r14
0x18012c7a4  push    r15
0x18012c7a6  sub     rsp, 330h
0x18012c7ad  movaps  xmmword ptr [rax-48h], xmm6
0x18012c7b1  mov     rax, cs:__security_cookie
0x18012c7b8  xor     rax, rsp
0x18012c7bb  mov     [rsp+368h+var_58], rax
0x18012c7c3  mov     r12, r8
0x18012c7c6  mov     r14, rdx
0x18012c7c9  mov     r15, rcx
0x18012c7cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18012c7d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18012c7d8  xor     r13d, r13d
0x18012c7db  test    al, al
0x18012c7dd  jnz     short loc_18012C807
0x18012c7df  mov     rcx, [rsp+368h]; this
0x18012c7e7  mov     ebx, 80004001h
0x18012c7ec  mov     r9d, ebx; char *
0x18012c7ef  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012c7f6  mov     edx, 0CAh; void *
0x18012c7fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c800  mov     eax, ebx
0x18012c802  jmp     loc_18012DE9B
0x18012c807  mov     rcx, r12
0x18012c80a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012c80f  mov     [rsp+368h+var_2C0], r13d
0x18012c817  lea     rcx, [r15+80h]
0x18012c81e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012c823  lea     r9, [rsp+368h+var_2C0]; int *
0x18012c82b  lea     r8, aAcquireenrollm; "AcquireEnrollmentDiscoveryEndpoint"
0x18012c832  mov     rdx, rax; unsigned __int16 *
0x18012c835  lea     rcx, [rsp+368h+var_E8]; this
0x18012c83d  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x18012c842  nop
0x18012c843  mov     rcx, [r15+48h]; this
0x18012c847  call    ?Initialize@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::TpmOperations::Initialize(void)
0x18012c84c  mov     ebx, eax
0x18012c84e  mov     [rsp+368h+var_2C0], eax
0x18012c855  test    eax, eax
0x18012c857  jns     short loc_18012C88A
0x18012c859  mov     rcx, [rsp+368h]; this
0x18012c861  mov     r9d, eax; char *
0x18012c864  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012c86b  mov     edx, 0D1h; void *
0x18012c870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c875  nop
0x18012c876  lea     rcx, [rsp+368h+var_E8]; this
0x18012c87e  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012c883  mov     eax, ebx
0x18012c885  jmp     loc_18012DE9B
0x18012c88a  xorps   xmm0, xmm0
0x18012c88d  movups  [rsp+368h+var_270], xmm0
0x18012c895  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18012c89d  movdqu  [rsp+368h+var_260], xmm6
0x18012c8a6  mov     word ptr [rsp+368h+var_270], r13w
0x18012c8af  movups  [rsp+368h+var_230], xmm0
0x18012c8b7  movdqu  [rsp+368h+var_220], xmm6
0x18012c8c0  mov     word ptr [rsp+368h+var_230], r13w
0x18012c8c9  lea     r8, [rsp+368h+var_230]
0x18012c8d1  lea     rdx, [rsp+368h+var_270]
0x18012c8d9  call    ?GetLinkIdInfo@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(std::wstring &,std::wstring &)
0x18012c8de  mov     ebx, eax
0x18012c8e0  mov     [rsp+368h+var_2C0], eax
0x18012c8e7  test    eax, eax
0x18012c8e9  jns     short loc_18012C938
0x18012c8eb  mov     rcx, [rsp+368h]; this
0x18012c8f3  mov     r9d, eax; char *
0x18012c8f6  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012c8fd  mov     edx, 0D5h; void *
0x18012c902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c907  nop
0x18012c908  lea     rcx, [rsp+368h+var_230]
0x18012c910  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c915  nop
0x18012c916  lea     rcx, [rsp+368h+var_270]
0x18012c91e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c923  nop
0x18012c924  lea     rcx, [rsp+368h+var_E8]; this
0x18012c92c  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012c931  mov     eax, ebx
0x18012c933  jmp     loc_18012DE9B
0x18012c938  mov     rdx, r12
0x18012c93b  lea     rcx, [rsp+368h+var_270]
0x18012c943  call    ?IsDeviceLinkEndpointsOverrideOrCacheAvailable@Core@Autopilot@ModernDeployment@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::IsDeviceLinkEndpointsOverrideOrCacheAvailable(std::wstring const &,Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo> &)
0x18012c948  test    al, al
0x18012c94a  jz      short loc_18012C97C
0x18012c94c  lea     rcx, [rsp+368h+var_230]
0x18012c954  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c959  nop
0x18012c95a  lea     rcx, [rsp+368h+var_270]
0x18012c962  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c967  nop
0x18012c968  lea     rcx, [rsp+368h+var_E8]; this
0x18012c970  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012c975  xor     eax, eax
0x18012c977  jmp     loc_18012DE9B
0x18012c97c  xorps   xmm0, xmm0
0x18012c97f  movups  [rsp+368h+var_210], xmm0
0x18012c987  movdqu  [rsp+368h+var_200], xmm6
0x18012c990  mov     word ptr [rsp+368h+var_210], r13w
0x18012c999  lea     r8, [rsp+368h+var_210]
0x18012c9a1  mov     edi, 1
0x18012c9a6  mov     ecx, edi
0x18012c9a8  call    ?GetHttpAgentVersionString@HttpRequestVersion@Autopilot@Windows@Microsoft@@SAJKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(ulong,ulong,std::wstring &)
0x18012c9ad  mov     ebx, eax
0x18012c9af  mov     [rsp+368h+var_2C0], eax
0x18012c9b6  test    eax, eax
0x18012c9b8  jns     short loc_18012CA15
0x18012c9ba  mov     rcx, [rsp+368h]; this
0x18012c9c2  mov     r9d, eax; char *
0x18012c9c5  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012c9cc  mov     edx, 0DEh; void *
0x18012c9d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c9d6  nop
0x18012c9d7  lea     rcx, [rsp+368h+var_210]
0x18012c9df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c9e4  nop
0x18012c9e5  lea     rcx, [rsp+368h+var_230]
0x18012c9ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c9f2  nop
0x18012c9f3  lea     rcx, [rsp+368h+var_270]
0x18012c9fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ca00  nop
0x18012ca01  lea     rcx, [rsp+368h+var_E8]; this
0x18012ca09  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012ca0e  mov     eax, ebx
0x18012ca10  jmp     loc_18012DE9B
0x18012ca15  xorps   xmm0, xmm0
0x18012ca18  movups  [rsp+368h+var_250], xmm0
0x18012ca20  movdqu  [rsp+368h+var_240], xmm6
0x18012ca29  mov     word ptr [rsp+368h+var_250], r13w
0x18012ca32  lea     rcx, [rsp+368h+var_250]
0x18012ca3a  call    ?GetDeviceLinkPreassociateDiscoveryUrl@DeviceLinkPolicyManager@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DeviceLinkPolicyManager::GetDeviceLinkPreassociateDiscoveryUrl(std::wstring &)
0x18012ca3f  mov     ebx, eax
0x18012ca41  test    eax, eax
0x18012ca43  jns     short loc_18012CAAE
0x18012ca45  mov     rcx, [rsp+368h]; this
0x18012ca4d  mov     r9d, eax; char *
0x18012ca50  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012ca57  mov     edx, 0E2h; void *
0x18012ca5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ca61  nop
0x18012ca62  lea     rcx, [rsp+368h+var_250]
0x18012ca6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ca6f  nop
0x18012ca70  lea     rcx, [rsp+368h+var_210]
0x18012ca78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ca7d  nop
0x18012ca7e  lea     rcx, [rsp+368h+var_230]
0x18012ca86  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ca8b  nop
0x18012ca8c  lea     rcx, [rsp+368h+var_270]
0x18012ca94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ca99  nop
0x18012ca9a  lea     rcx, [rsp+368h+var_E8]; this
0x18012caa2  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012caa7  mov     eax, ebx
0x18012caa9  jmp     loc_18012DE9B
0x18012caae  mov     [rsp+368h+var_2F8], r13d
0x18012cab3  lea     rcx, [rsp+368h+var_2F8]; unsigned int *
0x18012cab8  call    ?GetDiscoveryDeviceLinkRequestLocation@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEAK@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetDiscoveryDeviceLinkRequestLocation(ulong &)
0x18012cabd  mov     ebx, eax
0x18012cabf  mov     [rsp+368h+var_2C0], eax
0x18012cac6  test    eax, eax
0x18012cac8  jns     short loc_18012CB33
0x18012caca  mov     rcx, [rsp+368h]; this
0x18012cad2  mov     r9d, eax; char *
0x18012cad5  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012cadc  mov     edx, 0E6h; void *
0x18012cae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012cae6  nop
0x18012cae7  lea     rcx, [rsp+368h+var_250]
0x18012caef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012caf4  nop
0x18012caf5  lea     rcx, [rsp+368h+var_210]
0x18012cafd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cb02  nop
0x18012cb03  lea     rcx, [rsp+368h+var_230]
0x18012cb0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cb10  nop
0x18012cb11  lea     rcx, [rsp+368h+var_270]
0x18012cb19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cb1e  nop
0x18012cb1f  lea     rcx, [rsp+368h+var_E8]; this
0x18012cb27  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012cb2c  mov     eax, ebx
0x18012cb2e  jmp     loc_18012DE9B
0x18012cb33  mov     esi, [rsp+368h+var_2F8]
0x18012cb37  lea     eax, [rsi-1]
0x18012cb3a  mov     ebx, esi
0x18012cb3c  cmp     eax, 2
0x18012cb3f  cmova   ebx, edi
0x18012cb42  lea     rcx, [rsp+368h+var_2B0]
0x18012cb4a  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18012cb4f  nop
0x18012cb50  lea     rdx, aContentType; "Content-Type"
0x18012cb57  lea     rcx, [rsp+368h+hstringHeader]
0x18012cb5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cb64  nop
0x18012cb65  lea     rdx, [rsp+368h+hstringHeader]
0x18012cb6d  lea     rcx, [rsp+368h+var_2B0]
0x18012cb75  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18012cb7a  lea     rdx, aApplicationJso; "application/json"
0x18012cb81  mov     rcx, rax
0x18012cb84  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18012cb89  nop
0x18012cb8a  lea     rcx, [rsp+368h+hstringHeader]
0x18012cb92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cb97  mov     rcx, [r15+28h]
0x18012cb9b  mov     rax, [rcx]
0x18012cb9e  lea     rdx, [rsp+368h+var_1D0]
0x18012cba6  mov     rax, [rax+20h]
0x18012cbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012cbaf  nop
0x18012cbb0  cmp     [rsp+368h+var_1C0], r13
0x18012cbb8  jz      short loc_18012CC02
0x18012cbba  lea     rdx, aXApcv; "X-APCV"
0x18012cbc1  lea     rcx, [rsp+368h+hstringHeader]
0x18012cbc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cbce  nop
0x18012cbcf  lea     rdx, [rsp+368h+hstringHeader]
0x18012cbd7  lea     rcx, [rsp+368h+var_2B0]
0x18012cbdf  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18012cbe4  lea     rdx, [rsp+368h+var_1D0]
0x18012cbec  mov     rcx, rax
0x18012cbef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012cbf4  nop
0x18012cbf5  lea     rcx, [rsp+368h+hstringHeader]
0x18012cbfd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cc02  test    dil, bl
0x18012cc05  jz      short loc_18012CC4A
0x18012cc07  lea     rdx, aXDevicelinkinf; "X-DeviceLinkInfo"
0x18012cc0e  lea     rcx, [rsp+368h+hstringHeader]
0x18012cc16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012cc1b  nop
0x18012cc1c  lea     rdx, [rsp+368h+hstringHeader]
0x18012cc24  lea     rcx, [rsp+368h+var_2B0]
0x18012cc2c  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18012cc31  mov     rdx, r14
0x18012cc34  mov     rcx, rax
0x18012cc37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012cc3c  nop
0x18012cc3d  lea     rcx, [rsp+368h+hstringHeader]
0x18012cc45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cc4a  mov     [rsp+368h+var_2B8], r13
0x18012cc52  mov     [rsp+368h+var_178], r13
0x18012cc5a  mov     r9d, 1Ch; unsigned int
0x18012cc60  lea     r8d, [r9+1]; unsigned int
0x18012cc64  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18012cc6b  lea     rcx, [rsp+368h+hstringHeader]; hstringHeader
0x18012cc73  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18012cc78  lea     rdx, [rsp+368h+var_2B8]
0x18012cc80  mov     rcx, [rsp+368h+var_178]
0x18012cc88  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18012cc8d  mov     edi, eax
0x18012cc8f  mov     [rsp+368h+var_2C0], eax
0x18012cc96  test    eax, eax
0x18012cc98  jns     loc_18012CD39
0x18012cc9e  mov     rcx, [rsp+368h]; this
0x18012cca6  mov     r9d, eax; char *
0x18012cca9  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012ccb0  mov     edx, 102h; void *
0x18012ccb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ccba  nop
0x18012ccbb  lea     rcx, [rsp+368h+var_2B8]
0x18012ccc3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012ccc8  nop
0x18012ccc9  lea     rcx, [rsp+368h+var_1D0]
0x18012ccd1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ccd6  nop
0x18012ccd7  lea     rdx, [rsp+368h+var_2B0]
0x18012ccdf  lea     rcx, [rsp+368h+var_2B0]
0x18012cce7  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x18012ccec  nop
0x18012cced  lea     rcx, [rsp+368h+var_250]
0x18012ccf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ccfa  nop
0x18012ccfb  lea     rcx, [rsp+368h+var_210]
0x18012cd03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cd08  nop
0x18012cd09  lea     rcx, [rsp+368h+var_230]
0x18012cd11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cd16  nop
0x18012cd17  lea     rcx, [rsp+368h+var_270]
0x18012cd1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012cd24  nop
0x18012cd25  lea     rcx, [rsp+368h+var_E8]; this
0x18012cd2d  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18012cd32  mov     eax, edi
0x18012cd34  jmp     loc_18012DE9B
0x18012cd39  and     ebx, 2
0x18012cd3c  jz      loc_18012CE0D
0x18012cd42  mov     rcx, r14
0x18012cd45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
  ... truncated ...
```
