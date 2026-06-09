# ModernDeployment::Autopilot::Core::DeviceLinkManager::AcquireEnrollmentDiscoveryEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo> &)

- ea: `0x180128b08`
- end: `0x18012a234`
- name: `?AcquireEnrollmentDiscoveryEndpoint@DeviceLinkManager@Core@Autopilot@ModernDeployment@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@@Z`
- size: `5932`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180127f1c`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18006b708`
- `0x18006c694`
- `0x1800730b4`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800814a8`
- `0x1800839bc`
- `0x1800853a0`
- `0x1800887b8`
- `0x1800889a0`
- `0x180089b58`
- `0x18008a014`
- `0x18008c244`
- `0x18008dd00`
- `0x18008e438`
- `0x18008f068`
- `0x1800a13d8`
- `0x1800a3240`
- `0x1800ce0fc`
- `0x1800df644`
- `0x1801016a8`
- `0x180126738`
- `0x180126930`
- `0x180126d28`
- `0x180128b08`
- `0x18012aa9c`
- `0x18012baf4`
- `0x18012be88`
- `0x18012dfac`
- `0x180134e6c`
- `0x180135308`
- `0x18013ab68`
- `0x18013b2e0`
- `0x1801436c0`
- `0x18019f59c`
- `0x18019f6b4`
- `0x18019fd80`
- `0x18019fec0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012926d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012926d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a076`

## string_xrefs

- `0x180128fe3`: `Windows.Data.Json.JsonObject`
- `0x180128ef9`: `application/json`
- `0x180129808`: `application/json`
- `0x180128b5f`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180128be3`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180128c75`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180128d44`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180128dcf`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180128e54`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129028`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x1801290fc`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x1801291c5`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x1801292d9`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x1801294d2`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129713`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x1801298ce`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129962`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129b29`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129ca0`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129df5`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180129f2f`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x180128f86`: `X-DeviceLinkInfo`
- `0x1801290cc`: `deviceLinkInfo`

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
  std::wstring::operator=(a1 + 160, a2);
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
      (void *)0xD6,
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
      (void *)0xDA,
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
      (void *)0xE3,
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
      (void *)0xE7,
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
      (void *)0xEB,
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
      (void *)0x107,
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
        (void *)0x10B,
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
      (void *)0x110,
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
  v35 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8((__int64)v96, (__int64)v90);
  v36 = v35;
  v77 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
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
      (void *)0x12F,
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
        (void *)0x142,
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
                (void *)0x15A,
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
              (void *)0x159,
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
            (void *)0x156,
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
          (void *)0x154,
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
        (void *)0x146,
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
      (void *)0x13A,
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
0x180128b08  mov     rax, rsp
0x180128b0b  push    rbx
0x180128b0c  push    rsi
0x180128b0d  push    rdi
0x180128b0e  push    r12
0x180128b10  push    r13
0x180128b12  push    r14
0x180128b14  push    r15
0x180128b16  sub     rsp, 330h
0x180128b1d  movaps  xmmword ptr [rax-48h], xmm6
0x180128b21  mov     rax, cs:__security_cookie
0x180128b28  xor     rax, rsp
0x180128b2b  mov     [rsp+368h+var_58], rax
0x180128b33  mov     r12, r8
0x180128b36  mov     r14, rdx
0x180128b39  mov     r15, rcx
0x180128b3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180128b43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180128b48  xor     r13d, r13d
0x180128b4b  test    al, al
0x180128b4d  jnz     short loc_180128B77
0x180128b4f  mov     rcx, [rsp+368h]; this
0x180128b57  mov     ebx, 80004001h
0x180128b5c  mov     r9d, ebx; char *
0x180128b5f  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128b66  mov     edx, 0CAh; void *
0x180128b6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128b70  mov     eax, ebx
0x180128b72  jmp     loc_18012A208
0x180128b77  lea     rcx, [r15+0A0h]
0x180128b7e  mov     rdx, r14
0x180128b81  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180128b86  mov     rcx, r12
0x180128b89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180128b8e  mov     [rsp+368h+var_2C0], r13d
0x180128b96  lea     rcx, [r15+80h]
0x180128b9d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180128ba2  lea     r9, [rsp+368h+var_2C0]; int *
0x180128baa  lea     r8, aAcquireenrollm; "AcquireEnrollmentDiscoveryEndpoint"
0x180128bb1  mov     rdx, rax; unsigned __int16 *
0x180128bb4  lea     rcx, [rsp+368h+var_E8]; this
0x180128bbc  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x180128bc1  nop
0x180128bc2  mov     rcx, [r15+48h]; this
0x180128bc6  call    ?Initialize@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJXZ; ModernDeployment::Autopilot::Core::TpmOperations::Initialize(void)
0x180128bcb  mov     ebx, eax
0x180128bcd  mov     [rsp+368h+var_2C0], eax
0x180128bd4  test    eax, eax
0x180128bd6  jns     short loc_180128C09
0x180128bd8  mov     rcx, [rsp+368h]; this
0x180128be0  mov     r9d, eax; char *
0x180128be3  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128bea  mov     edx, 0D6h; void *
0x180128bef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128bf4  nop
0x180128bf5  lea     rcx, [rsp+368h+var_E8]; this
0x180128bfd  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180128c02  mov     eax, ebx
0x180128c04  jmp     loc_18012A208
0x180128c09  xorps   xmm0, xmm0
0x180128c0c  movups  [rsp+368h+var_270], xmm0
0x180128c14  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180128c1c  movdqu  [rsp+368h+var_260], xmm6
0x180128c25  mov     word ptr [rsp+368h+var_270], r13w
0x180128c2e  movups  [rsp+368h+var_230], xmm0
0x180128c36  movdqu  [rsp+368h+var_220], xmm6
0x180128c3f  mov     word ptr [rsp+368h+var_230], r13w
0x180128c48  lea     r8, [rsp+368h+var_230]
0x180128c50  lea     rdx, [rsp+368h+var_270]
0x180128c58  call    ?GetLinkIdInfo@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(std::wstring &,std::wstring &)
0x180128c5d  mov     ebx, eax
0x180128c5f  mov     [rsp+368h+var_2C0], eax
0x180128c66  test    eax, eax
0x180128c68  jns     short loc_180128CB7
0x180128c6a  mov     rcx, [rsp+368h]; this
0x180128c72  mov     r9d, eax; char *
0x180128c75  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128c7c  mov     edx, 0DAh; void *
0x180128c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128c86  nop
0x180128c87  lea     rcx, [rsp+368h+var_230]
0x180128c8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128c94  nop
0x180128c95  lea     rcx, [rsp+368h+var_270]
0x180128c9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128ca2  nop
0x180128ca3  lea     rcx, [rsp+368h+var_E8]; this
0x180128cab  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180128cb0  mov     eax, ebx
0x180128cb2  jmp     loc_18012A208
0x180128cb7  mov     rdx, r12
0x180128cba  lea     rcx, [rsp+368h+var_270]
0x180128cc2  call    ?IsDeviceLinkEndpointsOverrideOrCacheAvailable@Core@Autopilot@ModernDeployment@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::IsDeviceLinkEndpointsOverrideOrCacheAvailable(std::wstring const &,Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo> &)
0x180128cc7  test    al, al
0x180128cc9  jz      short loc_180128CFB
0x180128ccb  lea     rcx, [rsp+368h+var_230]
0x180128cd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128cd8  nop
0x180128cd9  lea     rcx, [rsp+368h+var_270]
0x180128ce1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128ce6  nop
0x180128ce7  lea     rcx, [rsp+368h+var_E8]; this
0x180128cef  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180128cf4  xor     eax, eax
0x180128cf6  jmp     loc_18012A208
0x180128cfb  xorps   xmm0, xmm0
0x180128cfe  movups  [rsp+368h+var_210], xmm0
0x180128d06  movdqu  [rsp+368h+var_200], xmm6
0x180128d0f  mov     word ptr [rsp+368h+var_210], r13w
0x180128d18  lea     r8, [rsp+368h+var_210]
0x180128d20  mov     edi, 1
0x180128d25  mov     ecx, edi
0x180128d27  call    ?GetHttpAgentVersionString@HttpRequestVersion@Autopilot@Windows@Microsoft@@SAJKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(ulong,ulong,std::wstring &)
0x180128d2c  mov     ebx, eax
0x180128d2e  mov     [rsp+368h+var_2C0], eax
0x180128d35  test    eax, eax
0x180128d37  jns     short loc_180128D94
0x180128d39  mov     rcx, [rsp+368h]; this
0x180128d41  mov     r9d, eax; char *
0x180128d44  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128d4b  mov     edx, 0E3h; void *
0x180128d50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128d55  nop
0x180128d56  lea     rcx, [rsp+368h+var_210]
0x180128d5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128d63  nop
0x180128d64  lea     rcx, [rsp+368h+var_230]
0x180128d6c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128d71  nop
0x180128d72  lea     rcx, [rsp+368h+var_270]
0x180128d7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128d7f  nop
0x180128d80  lea     rcx, [rsp+368h+var_E8]; this
0x180128d88  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180128d8d  mov     eax, ebx
0x180128d8f  jmp     loc_18012A208
0x180128d94  xorps   xmm0, xmm0
0x180128d97  movups  [rsp+368h+var_250], xmm0
0x180128d9f  movdqu  [rsp+368h+var_240], xmm6
0x180128da8  mov     word ptr [rsp+368h+var_250], r13w
0x180128db1  lea     rcx, [rsp+368h+var_250]
0x180128db9  call    ?GetDeviceLinkPreassociateDiscoveryUrl@DeviceLinkPolicyManager@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DeviceLinkPolicyManager::GetDeviceLinkPreassociateDiscoveryUrl(std::wstring &)
0x180128dbe  mov     ebx, eax
0x180128dc0  test    eax, eax
0x180128dc2  jns     short loc_180128E2D
0x180128dc4  mov     rcx, [rsp+368h]; this
0x180128dcc  mov     r9d, eax; char *
0x180128dcf  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128dd6  mov     edx, 0E7h; void *
0x180128ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128de0  nop
0x180128de1  lea     rcx, [rsp+368h+var_250]
0x180128de9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128dee  nop
0x180128def  lea     rcx, [rsp+368h+var_210]
0x180128df7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128dfc  nop
0x180128dfd  lea     rcx, [rsp+368h+var_230]
0x180128e05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128e0a  nop
0x180128e0b  lea     rcx, [rsp+368h+var_270]
0x180128e13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128e18  nop
0x180128e19  lea     rcx, [rsp+368h+var_E8]; this
0x180128e21  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180128e26  mov     eax, ebx
0x180128e28  jmp     loc_18012A208
0x180128e2d  mov     [rsp+368h+var_2F8], r13d
0x180128e32  lea     rcx, [rsp+368h+var_2F8]; unsigned int *
0x180128e37  call    ?GetDiscoveryDeviceLinkRequestLocation@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEAK@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetDiscoveryDeviceLinkRequestLocation(ulong &)
0x180128e3c  mov     ebx, eax
0x180128e3e  mov     [rsp+368h+var_2C0], eax
0x180128e45  test    eax, eax
0x180128e47  jns     short loc_180128EB2
0x180128e49  mov     rcx, [rsp+368h]; this
0x180128e51  mov     r9d, eax; char *
0x180128e54  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x180128e5b  mov     edx, 0EBh; void *
0x180128e60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128e65  nop
0x180128e66  lea     rcx, [rsp+368h+var_250]
0x180128e6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128e73  nop
0x180128e74  lea     rcx, [rsp+368h+var_210]
0x180128e7c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128e81  nop
0x180128e82  lea     rcx, [rsp+368h+var_230]
0x180128e8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128e8f  nop
0x180128e90  lea     rcx, [rsp+368h+var_270]
0x180128e98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128e9d  nop
0x180128e9e  lea     rcx, [rsp+368h+var_E8]; this
0x180128ea6  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180128eab  mov     eax, ebx
0x180128ead  jmp     loc_18012A208
0x180128eb2  mov     esi, [rsp+368h+var_2F8]
0x180128eb6  lea     eax, [rsi-1]
0x180128eb9  mov     ebx, esi
0x180128ebb  cmp     eax, 2
0x180128ebe  cmova   ebx, edi
0x180128ec1  lea     rcx, [rsp+368h+var_2B0]
0x180128ec9  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180128ece  nop
0x180128ecf  lea     rdx, aContentType; "Content-Type"
0x180128ed6  lea     rcx, [rsp+368h+hstringHeader]
0x180128ede  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180128ee3  nop
0x180128ee4  lea     rdx, [rsp+368h+hstringHeader]
0x180128eec  lea     rcx, [rsp+368h+var_2B0]
0x180128ef4  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180128ef9  lea     rdx, aApplicationJso; "application/json"
0x180128f00  mov     rcx, rax
0x180128f03  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180128f08  nop
0x180128f09  lea     rcx, [rsp+368h+hstringHeader]
0x180128f11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128f16  mov     rcx, [r15+28h]
0x180128f1a  mov     rax, [rcx]
0x180128f1d  lea     rdx, [rsp+368h+var_1D0]
0x180128f25  mov     rax, [rax+20h]
0x180128f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128f2e  nop
0x180128f2f  cmp     [rsp+368h+var_1C0], r13
0x180128f37  jz      short loc_180128F81
0x180128f39  lea     rdx, aXApcv; "X-APCV"
0x180128f40  lea     rcx, [rsp+368h+hstringHeader]
0x180128f48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180128f4d  nop
0x180128f4e  lea     rdx, [rsp+368h+hstringHeader]
0x180128f56  lea     rcx, [rsp+368h+var_2B0]
0x180128f5e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180128f63  lea     rdx, [rsp+368h+var_1D0]
0x180128f6b  mov     rcx, rax
0x180128f6e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180128f73  nop
0x180128f74  lea     rcx, [rsp+368h+hstringHeader]
0x180128f7c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128f81  test    dil, bl
0x180128f84  jz      short loc_180128FC9
0x180128f86  lea     rdx, aXDevicelinkinf; "X-DeviceLinkInfo"
0x180128f8d  lea     rcx, [rsp+368h+hstringHeader]
0x180128f95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180128f9a  nop
0x180128f9b  lea     rdx, [rsp+368h+hstringHeader]
0x180128fa3  lea     rcx, [rsp+368h+var_2B0]
0x180128fab  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180128fb0  mov     rdx, r14
0x180128fb3  mov     rcx, rax
0x180128fb6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180128fbb  nop
0x180128fbc  lea     rcx, [rsp+368h+hstringHeader]
0x180128fc4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180128fc9  mov     [rsp+368h+var_2B8], r13
0x180128fd1  mov     [rsp+368h+var_178], r13
0x180128fd9  mov     r9d, 1Ch; unsigned int
0x180128fdf  lea     r8d, [r9+1]; unsigned int
0x180128fe3  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180128fea  lea     rcx, [rsp+368h+hstringHeader]; hstringHeader
0x180128ff2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180128ff7  lea     rdx, [rsp+368h+var_2B8]
0x180128fff  mov     rcx, [rsp+368h+var_178]
0x180129007  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18012900c  mov     edi, eax
0x18012900e  mov     [rsp+368h+var_2C0], eax
0x180129015  test    eax, eax
0x180129017  jns     loc_1801290B8
0x18012901d  mov     rcx, [rsp+368h]; this
0x180129025  mov     r9d, eax; char *
0x180129028  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012902f  mov     edx, 107h; void *
0x180129034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129039  nop
0x18012903a  lea     rcx, [rsp+368h+var_2B8]
0x180129042  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180129047  nop
0x180129048  lea     rcx, [rsp+368h+var_1D0]
0x180129050  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129055  nop
0x180129056  lea     rdx, [rsp+368h+var_2B0]
0x18012905e  lea     rcx, [rsp+368h+var_2B0]
0x180129066  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x18012906b  nop
0x18012906c  lea     rcx, [rsp+368h+var_250]
0x180129074  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129079  nop
0x18012907a  lea     rcx, [rsp+368h+var_210]
0x180129082  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129087  nop
0x180129088  lea     rcx, [rsp+368h+var_230]
0x180129090  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129095  nop
0x180129096  lea     rcx, [rsp+368h+var_270]
0x18012909e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801290a3  nop
0x1801290a4  lea     rcx, [rsp+368h+var_E8]; this
0x1801290ac  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801290b1  mov     eax, edi
0x1801290b3  jmp     loc_18012A208
0x1801290b8  and     ebx, 2
  ... truncated ...
```
