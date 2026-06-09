# ModernDeployment::Autopilot::Core::AttestationAndDiscoveryManager::SendReceiveFromUri(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180130b9c`
- end: `0x180131ba5`
- name: `?SendReceiveFromUri@AttestationAndDiscoveryManager@Core@Autopilot@ModernDeployment@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000KK0AEAV56@1AEAK1@Z`
- size: `4105`
- prototype: ``
- caller_count: `3`
- callee_count: `41`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012840c`
- `0x18012c840`
- `0x1801cf704`

## callees

- `0x18000b820`
- `0x18000b850`
- `0x180067008`
- `0x180067a54`
- `0x18006b708`
- `0x18006c694`
- `0x18007748c`
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
- `0x18008a0a8`
- `0x18008c244`
- `0x18008dd00`
- `0x18008e438`
- `0x18008f068`
- `0x1800a3240`
- `0x1800a8180`
- `0x1800ce040`
- `0x1800df644`
- `0x180126738`
- `0x18012e50c`
- `0x18012e92c`
- `0x180130b9c`
- `0x180131c60`
- `0x180131d00`
- `0x180134e6c`
- `0x180135308`
- `0x180137338`
- `0x18013ab68`
- `0x1801432dc`
- `0x18019f59c`
- `0x18019f6b4`
- `0x18019fd80`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801314c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801314c6`

## string_xrefs

- `0x1801310bb`: `Windows.Data.Json.JsonObject`
- `0x180130c9a`: `application/json`
- `0x180131048`: `deviceLinkJson`
- `0x180130deb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180130eb9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180130f86`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801310fd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801312f6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801313f4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180131532`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180131745`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801318f4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180131962`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180131b5d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180130c50`: `SendReceiveFromUri`
- `0x180131088`: `SendReceiveFromUri_DeviceLinkBlobEmpty`

## pseudocode

```c
// Hidden C++ exception states: #wind=25 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::AttestationAndDiscoveryManager::SendReceiveFromUri(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11,
        __int64 a12)
{
  const unsigned __int16 *v15; // rax
  __int64 v16; // rax
  __m128i si128; // xmm6
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  int HttpAgentVersionString; // eax
  __int64 v22; // rcx
  unsigned int v23; // ebx
  int LinkIdInfo; // eax
  unsigned int v26; // ebx
  int PublicKeyId; // eax
  unsigned int v28; // ebx
  int v29; // ecx
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rdi
  __int64 v33; // r14
  const unsigned __int16 *v34; // rbx
  const unsigned __int16 *v35; // rax
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // eax
  unsigned int v39; // ebx
  PCWSTR StringRawBuffer; // rdx
  int v41; // eax
  unsigned int v42; // ebx
  __int64 v43; // rdi
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 *v47; // r14
  __int64 v48; // rsi
  __int64 v49; // rbx
  __int64 v50; // rax
  int v51; // eax
  unsigned int v52; // ebx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  int v58; // ebx
  int v59; // [rsp+20h] [rbp-408h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-3B8h] BYREF
  __int64 v61; // [rsp+88h] [rbp-3A0h]
  _DWORD *v62; // [rsp+90h] [rbp-398h]
  __int64 v63; // [rsp+98h] [rbp-390h]
  __int64 v64; // [rsp+A0h] [rbp-388h]
  __int64 v65; // [rsp+A8h] [rbp-380h]
  _BYTE v66[64]; // [rsp+B0h] [rbp-378h] BYREF
  _BYTE v67[64]; // [rsp+F0h] [rbp-338h] BYREF
  _BYTE v68[64]; // [rsp+130h] [rbp-2F8h] BYREF
  _BYTE v69[64]; // [rsp+170h] [rbp-2B8h] BYREF
  _BYTE v70[64]; // [rsp+1B0h] [rbp-278h] BYREF
  int v71; // [rsp+1F0h] [rbp-238h] BYREF
  _BYTE v72[16]; // [rsp+1F8h] [rbp-230h] BYREF
  struct Windows::Data::Json::IJsonObject *v73; // [rsp+208h] [rbp-220h] BYREF
  HSTRING string; // [rsp+210h] [rbp-218h] BYREF
  __int64 v75; // [rsp+218h] [rbp-210h] BYREF
  __int64 v76; // [rsp+220h] [rbp-208h]
  _OWORD v77[2]; // [rsp+228h] [rbp-200h] BYREF
  _OWORD v78[2]; // [rsp+248h] [rbp-1E0h] BYREF
  __int128 v79; // [rsp+268h] [rbp-1C0h] BYREF
  __int64 v80; // [rsp+278h] [rbp-1B0h]
  __int64 v81; // [rsp+280h] [rbp-1A8h]
  _OWORD v82[2]; // [rsp+288h] [rbp-1A0h] BYREF
  _OWORD v83[2]; // [rsp+2A8h] [rbp-180h] BYREF
  _OWORD v84[2]; // [rsp+2C8h] [rbp-160h] BYREF
  _BYTE v85[16]; // [rsp+2E8h] [rbp-140h] BYREF
  __int64 v86; // [rsp+2F8h] [rbp-130h]
  _QWORD v87[3]; // [rsp+308h] [rbp-120h] BYREF
  _OWORD v88[2]; // [rsp+320h] [rbp-108h] BYREF
  _OWORD v89[2]; // [rsp+340h] [rbp-E8h] BYREF
  _BYTE v90[32]; // [rsp+360h] [rbp-C8h] BYREF
  _BYTE v91[80]; // [rsp+380h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+0h]

  v63 = a2;
  v64 = a9;
  v65 = a10;
  v62 = a11;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v71 = 0;
    v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 96);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
      (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91,
      v15,
      L"SendReceiveFromUri",
      &v71);
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v72);
    std::wstring::wstring(&hstringHeader, L"Content-Type");
    v16 = std::map<std::wstring,std::wstring>::operator[](v72, &hstringHeader);
    std::wstring::assign(v16, L"application/json");
    std::wstring::_Tidy_deallocate(&hstringHeader);
    v77[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v77[1] = si128;
    LOWORD(v77[0]) = 0;
    if ( (int)ModernDeployment::Autopilot::Core::AutopilotConfig::GetDeviceLinkDownloadApiVersion(v77) < 0 )
      std::wstring::assign(v77, L"3.0");
    std::wstring::wstring(&hstringHeader, L"api-version");
    v18 = std::map<std::wstring,std::wstring>::operator[](v72, &hstringHeader);
    std::wstring::operator=(v18, v77);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 8) + 32LL))(*(_QWORD *)(a1 + 8), v85);
    if ( v86 )
    {
      std::wstring::wstring(&hstringHeader, L"X-APCV");
      v20 = std::map<std::wstring,std::wstring>::operator[](v72, &hstringHeader);
      std::wstring::operator=(v20, v85);
      std::wstring::_Tidy_deallocate(&hstringHeader);
    }
    v78[0] = 0;
    v78[1] = si128;
    LOWORD(v78[0]) = 0;
    HttpAgentVersionString = Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(a6, v19, v78);
    v23 = HttpAgentVersionString;
    v71 = HttpAgentVersionString;
    if ( HttpAgentVersionString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)HttpAgentVersionString,
        v59);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v23;
    }
    v82[0] = 0;
    v82[1] = si128;
    LOWORD(v82[0]) = 0;
    v84[0] = 0;
    v84[1] = si128;
    LOWORD(v84[0]) = 0;
    LinkIdInfo = ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(v22, v82, v84);
    v26 = LinkIdInfo;
    v71 = LinkIdInfo;
    if ( LinkIdInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)LinkIdInfo,
        v59);
      std::wstring::_Tidy_deallocate(v84);
      std::wstring::_Tidy_deallocate(v82);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v26;
    }
    v83[0] = 0;
    v83[1] = si128;
    LOWORD(v83[0]) = 0;
    PublicKeyId = ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(*(_QWORD *)(a1 + 56), v83);
    v28 = PublicKeyId;
    v71 = PublicKeyId;
    if ( PublicKeyId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)PublicKeyId,
        v59);
      std::wstring::_Tidy_deallocate(v83);
      std::wstring::_Tidy_deallocate(v84);
      std::wstring::_Tidy_deallocate(v82);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v28;
    }
    v79 = 0;
    v80 = 0;
    v81 = 7;
    LOWORD(v79) = 0;
    if ( !*(_QWORD *)(a5 + 16) || std::wstring::find(a5, L"deviceLinkJson", 0) != -1 )
    {
      std::wstring::operator=(&v79, a8);
      if ( !v80 && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dzqq_EventWriteTransfer(
          v29,
          (unsigned int)AutopilotMaaLoadAikFailed,
          -2147418113,
          (unsigned int)L"SendReceiveFromUri_DeviceLinkBlobEmpty",
          0,
          0);
    }
    v73 = 0;
    v61 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v30 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v61, &v73);
    v31 = v30;
    v71 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v30,
        v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      std::wstring::_Tidy_deallocate(&v79);
      std::wstring::_Tidy_deallocate(v83);
      std::wstring::_Tidy_deallocate(v84);
      std::wstring::_Tidy_deallocate(v82);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v31;
    }
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v66, off_180213548, a3);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v67, off_180213540, v82);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v68, off_180213530, v83);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v69, off_180213528, a4);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v70, off_180213538, &v79);
    hstringHeader.Reserved.Reserved1 = v66;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v71;
    std::vector<std::tuple<std::wstring,std::wstring>>::vector<std::tuple<std::wstring,std::wstring>>(
      v87,
      &hstringHeader);
    `eh vector destructor iterator'(
      v66,
      0x40u,
      5u,
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>);
    v32 = v87[0];
    v33 = v87[1];
    while ( v32 != v33 )
    {
      if ( !*(_QWORD *)(a5 + 16) || std::wstring::find(a5, v32 + 32, 0) != -1 )
      {
        v34 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
        v35 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32 + 32);
        v36 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v73, v35, v34);
        v37 = v36;
        v71 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11B,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
            (const char *)(unsigned int)v36,
            v59);
          std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v87);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
          std::wstring::_Tidy_deallocate(&v79);
          std::wstring::_Tidy_deallocate(v83);
          std::wstring::_Tidy_deallocate(v84);
          std::wstring::_Tidy_deallocate(v82);
          std::wstring::_Tidy_deallocate(v78);
          std::wstring::_Tidy_deallocate(v85);
          std::wstring::_Tidy_deallocate(v77);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v72,
            v72);
          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
          return v37;
        }
      }
      v32 += 64;
    }
    string = 0;
    v38 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v73, &string);
    v39 = v38;
    v71 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v38,
        v59);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      std::wstring::_Tidy_deallocate(&v79);
      std::wstring::_Tidy_deallocate(v83);
      std::wstring::_Tidy_deallocate(v84);
      std::wstring::_Tidy_deallocate(v82);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v39;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v90, StringRawBuffer);
    v88[0] = 0;
    v88[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v88[0]) = 0;
    v41 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8((__int64)v90, (__int64)v88);
    v42 = v41;
    v71 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v41,
        v59);
      std::string::_Tidy_deallocate(v88);
      std::wstring::_Tidy_deallocate(v90);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      std::wstring::_Tidy_deallocate(&v79);
      std::wstring::_Tidy_deallocate(v83);
      std::wstring::_Tidy_deallocate(v84);
      std::wstring::_Tidy_deallocate(v82);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v42;
    }
    v43 = v63;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
      McTemplateU0zz_EventWriteTransfer(v46, DeviceLinkWebRequest, v44, v45);
    }
    v75 = 0;
    v76 = 0;
    *v62 = 0;
    v89[0] = 0;
    v89[1] = si128;
    LOWORD(v89[0]) = 0;
    v47 = *(__int64 **)(a1 + 8);
    v48 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
    v49 = *v47;
    std::_String_val<std::_Simple_types<char>>::_Myptr(v88);
    v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v78);
    v51 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v49 + 8))(v47, v50, v48, 1);
    v52 = v51;
    v71 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v51,
        (int)L"HTTP/1.1");
      std::wstring::_Tidy_deallocate(v89);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v75);
      std::string::_Tidy_deallocate(v88);
      std::wstring::_Tidy_deallocate(v90);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v87);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      std::wstring::_Tidy_deallocate(&v79);
      std::wstring::_Tidy_deallocate(v83);
      std::wstring::_Tidy_deallocate(v84);
      std::wstring::_Tidy_deallocate(v82);
      std::wstring::_Tidy_deallocate(v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v77);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v72,
        v72);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
      return v52;
    }
    v53 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(**(_QWORD **)(a1 + 8) + 32LL))(
            *(_QWORD *)(a1 + 8),
            &hstringHeader);
    std::wstring::operator=(v64, v53);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    v54 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(**(_QWORD **)(a1 + 8) + 40LL))(
            *(_QWORD *)(a1 + 8),
            &hstringHeader);
    std::wstring::operator=(v65, v54);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    if ( *v62 == 200 )
    {
      v57 = std::string::string(&hstringHeader, v75, v75 + v76);
      v58 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::Utf8ToUnicode(v57, a12);
      v71 = v58;
      std::string::_Tidy_deallocate(&hstringHeader);
      if ( v58 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
          (const char *)(unsigned int)v58,
          (int)L"HTTP/1.1");
        std::wstring::_Tidy_deallocate(v89);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v75);
        std::string::_Tidy_deallocate(v88);
        std::wstring::_Tidy_deallocate(v90);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v87);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
        std::wstring::_Tidy_deallocate(&v79);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::_Tidy_deallocate(v84);
        std::wstring::_Tidy_deallocate(v82);
        std::wstring::_Tidy_deallocate(v78);
        std::wstring::_Tidy_deallocate(v85);
        std::wstring::_Tidy_deallocate(v77);
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
          v72,
          v72);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
        return (unsigned int)v58;
      }
    }
    else if ( v76 )
    {
      v55 = std::string::string(&hstringHeader, v75, v75 + v76);
      v56 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::Utf8ToUnicode(v55, a12);
      if ( v56 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
          (const char *)(unsigned int)v56,
          (int)L"HTTP/1.1");
      std::string::_Tidy_deallocate(&hstringHeader);
    }
    std::wstring::_Tidy_deallocate(v89);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v75);
    std::string::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v90);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v87);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    std::wstring::_Tidy_deallocate(&v79);
    std::wstring::_Tidy_deallocate(v83);
    std::wstring::_Tidy_deallocate(v84);
    std::wstring::_Tidy_deallocate(v82);
    std::wstring::_Tidy_deallocate(v78);
    std::wstring::_Tidy_deallocate(v85);
    std::wstring::_Tidy_deallocate(v77);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v72,
      v72);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v91);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
      (const char *)0x80004001LL,
      v59);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180130b9c  mov     rax, rsp
0x180130b9f  push    rbx
0x180130ba0  push    rsi
0x180130ba1  push    rdi
0x180130ba2  push    r12
0x180130ba4  push    r13
0x180130ba6  push    r14
0x180130ba8  push    r15
0x180130baa  sub     rsp, 3F0h
0x180130bb1  movaps  xmmword ptr [rax-48h], xmm6
0x180130bb5  mov     rax, cs:__security_cookie
0x180130bbc  xor     rax, rsp
0x180130bbf  mov     [rsp+428h+var_58], rax
0x180130bc7  mov     r14, r9
0x180130bca  mov     rsi, r8
0x180130bcd  mov     [rsp+428h+var_390], rdx
0x180130bd5  mov     r13, rcx
0x180130bd8  mov     r15, [rsp+428h+arg_20]
0x180130be0  mov     rdi, [rsp+428h+arg_38]
0x180130be8  mov     rax, [rsp+428h+arg_40]
0x180130bf0  mov     [rsp+428h+var_388], rax
0x180130bf8  mov     rax, [rsp+428h+arg_48]
0x180130c00  mov     [rsp+428h+var_380], rax
0x180130c08  mov     rax, [rsp+428h+arg_50]
0x180130c10  mov     [rsp+428h+var_398], rax
0x180130c18  mov     r12, [rsp+428h+arg_58]
0x180130c20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180130c27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180130c2c  test    al, al
0x180130c2e  jz      loc_180131B4D
0x180130c34  mov     [rsp+428h+var_238], 0
0x180130c3f  lea     rcx, [r13+60h]
0x180130c43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180130c48  lea     r9, [rsp+428h+var_238]; int *
0x180130c50  lea     r8, aSendreceivefro_0; "SendReceiveFromUri"
0x180130c57  mov     rdx, rax; unsigned __int16 *
0x180130c5a  lea     rcx, [rsp+428h+var_A8]; this
0x180130c62  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x180130c67  nop
0x180130c68  lea     rcx, [rsp+428h+var_230]
0x180130c70  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180130c75  nop
0x180130c76  lea     rdx, aContentType; "Content-Type"
0x180130c7d  lea     rcx, [rsp+428h+hstringHeader]
0x180130c82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180130c87  nop
0x180130c88  lea     rdx, [rsp+428h+hstringHeader]
0x180130c8d  lea     rcx, [rsp+428h+var_230]
0x180130c95  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180130c9a  lea     rdx, aApplicationJso; "application/json"
0x180130ca1  mov     rcx, rax
0x180130ca4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180130ca9  nop
0x180130caa  lea     rcx, [rsp+428h+hstringHeader]
0x180130caf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130cb4  xorps   xmm0, xmm0
0x180130cb7  movups  [rsp+428h+var_200], xmm0
0x180130cbf  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180130cc7  movdqu  [rsp+428h+var_1F0], xmm6
0x180130cd0  xor     eax, eax
0x180130cd2  mov     word ptr [rsp+428h+var_200], ax
0x180130cda  lea     rcx, [rsp+428h+var_200]
0x180130ce2  call    ?GetDeviceLinkDownloadApiVersion@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetDeviceLinkDownloadApiVersion(std::wstring &)
0x180130ce7  test    eax, eax
0x180130ce9  jns     short loc_180130CFF
0x180130ceb  lea     rdx, a30; "3.0"
0x180130cf2  lea     rcx, [rsp+428h+var_200]
0x180130cfa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180130cff  lea     rdx, aApiVersion; "api-version"
0x180130d06  lea     rcx, [rsp+428h+hstringHeader]
0x180130d0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180130d10  nop
0x180130d11  lea     rdx, [rsp+428h+hstringHeader]
0x180130d16  lea     rcx, [rsp+428h+var_230]
0x180130d1e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180130d23  lea     rdx, [rsp+428h+var_200]
0x180130d2b  mov     rcx, rax
0x180130d2e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180130d33  nop
0x180130d34  lea     rcx, [rsp+428h+hstringHeader]
0x180130d39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130d3e  mov     rcx, [r13+8]
0x180130d42  mov     rax, [rcx]
0x180130d45  lea     rdx, [rsp+428h+var_140]
0x180130d4d  mov     rax, [rax+20h]
0x180130d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180130d56  nop
0x180130d57  cmp     [rsp+428h+var_130], 0
0x180130d60  jz      short loc_180130DA1
0x180130d62  lea     rdx, aXApcv; "X-APCV"
0x180130d69  lea     rcx, [rsp+428h+hstringHeader]
0x180130d6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180130d73  nop
0x180130d74  lea     rdx, [rsp+428h+hstringHeader]
0x180130d79  lea     rcx, [rsp+428h+var_230]
0x180130d81  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180130d86  lea     rdx, [rsp+428h+var_140]
0x180130d8e  mov     rcx, rax
0x180130d91  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180130d96  nop
0x180130d97  lea     rcx, [rsp+428h+hstringHeader]
0x180130d9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130da1  xorps   xmm0, xmm0
0x180130da4  movups  [rsp+428h+var_1E0], xmm0
0x180130dac  movdqu  [rsp+428h+var_1D0], xmm6
0x180130db5  xor     eax, eax
0x180130db7  mov     word ptr [rsp+428h+var_1E0], ax
0x180130dbf  lea     r8, [rsp+428h+var_1E0]
0x180130dc7  mov     ecx, [rsp+428h+arg_28]
0x180130dce  call    ?GetHttpAgentVersionString@HttpRequestVersion@Autopilot@Windows@Microsoft@@SAJKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(ulong,ulong,std::wstring &)
0x180130dd3  mov     ebx, eax
0x180130dd5  mov     [rsp+428h+var_238], eax
0x180130ddc  test    eax, eax
0x180130dde  jns     short loc_180130E51
0x180130de0  mov     rcx, [rsp+428h]; this
0x180130de8  mov     r9d, eax; char *
0x180130deb  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180130df2  mov     edx, 0EDh; void *
0x180130df7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130dfc  nop
0x180130dfd  lea     rcx, [rsp+428h+var_1E0]
0x180130e05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130e0a  nop
0x180130e0b  lea     rcx, [rsp+428h+var_140]
0x180130e13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130e18  nop
0x180130e19  lea     rcx, [rsp+428h+var_200]
0x180130e21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130e26  nop
0x180130e27  lea     rdx, [rsp+428h+var_230]
0x180130e2f  lea     rcx, [rsp+428h+var_230]
0x180130e37  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180130e3c  nop
0x180130e3d  lea     rcx, [rsp+428h+var_A8]; this
0x180130e45  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180130e4a  mov     eax, ebx
0x180130e4c  jmp     loc_180131B79
0x180130e51  xorps   xmm0, xmm0
0x180130e54  movups  [rsp+428h+var_1A0], xmm0
0x180130e5c  movdqu  [rsp+428h+var_190], xmm6
0x180130e65  xor     eax, eax
0x180130e67  mov     word ptr [rsp+428h+var_1A0], ax
0x180130e6f  movups  [rsp+428h+var_160], xmm0
0x180130e77  movdqu  [rsp+428h+var_150], xmm6
0x180130e80  mov     word ptr [rsp+428h+var_160], ax
0x180130e88  lea     r8, [rsp+428h+var_160]
0x180130e90  lea     rdx, [rsp+428h+var_1A0]
0x180130e98  call    ?GetLinkIdInfo@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(std::wstring &,std::wstring &)
0x180130e9d  mov     ebx, eax
0x180130e9f  mov     [rsp+428h+var_238], eax
0x180130ea6  test    eax, eax
0x180130ea8  jns     loc_180130F3B
0x180130eae  mov     rcx, [rsp+428h]; this
0x180130eb6  mov     r9d, eax; char *
0x180130eb9  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180130ec0  mov     edx, 0F2h; void *
0x180130ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130eca  nop
0x180130ecb  lea     rcx, [rsp+428h+var_160]
0x180130ed3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130ed8  nop
0x180130ed9  lea     rcx, [rsp+428h+var_1A0]
0x180130ee1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130ee6  nop
0x180130ee7  lea     rcx, [rsp+428h+var_1E0]
0x180130eef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130ef4  nop
0x180130ef5  lea     rcx, [rsp+428h+var_140]
0x180130efd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130f02  nop
0x180130f03  lea     rcx, [rsp+428h+var_200]
0x180130f0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130f10  nop
0x180130f11  lea     rdx, [rsp+428h+var_230]
0x180130f19  lea     rcx, [rsp+428h+var_230]
0x180130f21  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180130f26  nop
0x180130f27  lea     rcx, [rsp+428h+var_A8]; this
0x180130f2f  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180130f34  mov     eax, ebx
0x180130f36  jmp     loc_180131B79
0x180130f3b  xorps   xmm0, xmm0
0x180130f3e  movups  [rsp+428h+var_180], xmm0
0x180130f46  movdqu  [rsp+428h+var_170], xmm6
0x180130f4f  xor     eax, eax
0x180130f51  mov     word ptr [rsp+428h+var_180], ax
0x180130f59  lea     rdx, [rsp+428h+var_180]
0x180130f61  mov     rcx, [r13+38h]
0x180130f65  call    ?GetPublicKeyId@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(std::wstring &)
0x180130f6a  mov     ebx, eax
0x180130f6c  mov     [rsp+428h+var_238], eax
0x180130f73  test    eax, eax
0x180130f75  jns     loc_180131016
0x180130f7b  mov     rcx, [rsp+428h]; this
0x180130f83  mov     r9d, eax; char *
0x180130f86  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180130f8d  mov     edx, 0F5h; void *
0x180130f92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130f97  nop
0x180130f98  lea     rcx, [rsp+428h+var_180]
0x180130fa0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130fa5  nop
0x180130fa6  lea     rcx, [rsp+428h+var_160]
0x180130fae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130fb3  nop
0x180130fb4  lea     rcx, [rsp+428h+var_1A0]
0x180130fbc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130fc1  nop
0x180130fc2  lea     rcx, [rsp+428h+var_1E0]
0x180130fca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130fcf  nop
0x180130fd0  lea     rcx, [rsp+428h+var_140]
0x180130fd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130fdd  nop
0x180130fde  lea     rcx, [rsp+428h+var_200]
0x180130fe6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130feb  nop
0x180130fec  lea     rdx, [rsp+428h+var_230]
0x180130ff4  lea     rcx, [rsp+428h+var_230]
0x180130ffc  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180131001  nop
0x180131002  lea     rcx, [rsp+428h+var_A8]; this
0x18013100a  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013100f  mov     eax, ebx
0x180131011  jmp     loc_180131B79
0x180131016  xorps   xmm0, xmm0
0x180131019  movups  [rsp+428h+var_1C0], xmm0
0x180131021  xor     ebx, ebx
0x180131023  mov     [rsp+428h+var_1B0], rbx
0x18013102b  mov     [rsp+428h+var_1A8], 7
0x180131037  mov     word ptr [rsp+428h+var_1C0], bx
0x18013103f  cmp     [r15+10h], rbx
0x180131043  jz      short loc_18013105D
0x180131045  xor     r8d, r8d
0x180131048  lea     rdx, aDevicelinkjson; "deviceLinkJson"
0x18013104f  mov     rcx, r15
0x180131052  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180131057  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013105b  jz      short loc_1801310A1
0x18013105d  mov     rdx, rdi
0x180131060  lea     rcx, [rsp+428h+var_1C0]
0x180131068  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013106d  cmp     [rsp+428h+var_1B0], rbx
0x180131075  jnz     short loc_1801310A1
0x180131077  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18013107e  jz      short loc_1801310A1
0x180131080  mov     dword ptr [rsp+428h+var_400], ebx
0x180131084  mov     [rsp+428h+var_408], ebx; int
0x180131088  lea     r9, aSendreceivefro; "SendReceiveFromUri_DeviceLinkBlobEmpty"
0x18013108f  mov     r8d, 8000FFFFh
0x180131095  lea     rdx, AutopilotMaaLoadAikFailed
0x18013109c  call    McTemplateU0dzqq_EventWriteTransfer
0x1801310a1  mov     [rsp+428h+var_220], rbx
0x1801310a9  mov     [rsp+428h+var_3A0], rbx
0x1801310b1  mov     r9d, 1Ch; unsigned int
0x1801310b7  lea     r8d, [r9+1]; unsigned int
0x1801310bb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801310c2  lea     rcx, [rsp+428h+hstringHeader]; hstringHeader
0x1801310c7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801310cc  lea     rdx, [rsp+428h+var_220]
0x1801310d4  mov     rcx, [rsp+428h+var_3A0]
0x1801310dc  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801310e1  mov     ebx, eax
0x1801310e3  mov     [rsp+428h+var_238], eax
0x1801310ea  test    eax, eax
0x1801310ec  jns     loc_1801311A9
0x1801310f2  mov     rcx, [rsp+428h]; this
0x1801310fa  mov     r9d, eax; char *
0x1801310fd  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180131104  mov     edx, 10Bh; void *
0x180131109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013110e  nop
0x18013110f  lea     rcx, [rsp+428h+var_220]
0x180131117  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013111c  nop
0x18013111d  lea     rcx, [rsp+428h+var_1C0]
0x180131125  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013112a  nop
0x18013112b  lea     rcx, [rsp+428h+var_180]
0x180131133  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131138  nop
0x180131139  lea     rcx, [rsp+428h+var_160]
0x180131141  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131146  nop
0x180131147  lea     rcx, [rsp+428h+var_1A0]
0x18013114f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131154  nop
0x180131155  lea     rcx, [rsp+428h+var_1E0]
0x18013115d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131162  nop
0x180131163  lea     rcx, [rsp+428h+var_140]
0x18013116b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131170  nop
0x180131171  lea     rcx, [rsp+428h+var_200]
0x180131179  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013117e  nop
0x18013117f  lea     rdx, [rsp+428h+var_230]
0x180131187  lea     rcx, [rsp+428h+var_230]
0x18013118f  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180131194  nop
  ... truncated ...
```
