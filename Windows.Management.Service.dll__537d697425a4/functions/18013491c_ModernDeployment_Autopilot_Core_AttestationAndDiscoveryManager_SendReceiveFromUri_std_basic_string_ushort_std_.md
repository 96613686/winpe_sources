# ModernDeployment::Autopilot::Core::AttestationAndDiscoveryManager::SendReceiveFromUri(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18013491c`
- end: `0x180135949`
- name: `?SendReceiveFromUri@AttestationAndDiscoveryManager@Core@Autopilot@ModernDeployment@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000KKAEAV56@1AEAK1@Z`
- size: `4141`
- prototype: ``
- caller_count: `3`
- callee_count: `43`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012c0bc`
- `0x180130558`
- `0x1801d54fc`

## callees

- `0x18000b8f0`
- `0x18000b920`
- `0x180067398`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006cb94`
- `0x180077d0c`
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
- `0x18008af70`
- `0x18008d290`
- `0x18008edec`
- `0x18008f570`
- `0x1800901c0`
- `0x1800a4890`
- `0x1800d0440`
- `0x1800e1e8c`
- `0x18012a398`
- `0x180132254`
- `0x18013267c`
- `0x1801327e0`
- `0x180132b88`
- `0x18013491c`
- `0x180135a10`
- `0x180135ab4`
- `0x180138d20`
- `0x1801391f8`
- `0x18013b2b4`
- `0x18013ebb0`
- `0x18014733c`
- `0x180149168`
- `0x1801a4a04`
- `0x1801a4b1c`
- `0x1801a5204`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180135264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180135264`

## string_xrefs

- `0x180134e59`: `Windows.Data.Json.JsonObject`
- `0x180134a12`: `application/json`
- `0x180134b60`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180134c2e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180134cfa`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180134df6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180134e9b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180135094`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180135192`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801352d6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801354e9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180135698`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180135706`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x180135901`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\attestationanddiscoverymanager.cpp`
- `0x1801349c8`: `SendReceiveFromUri`
- `0x180134db0`: `deviceLinkJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
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
        _DWORD *a10,
        __int64 a11)
{
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  __m128i si128; // xmm6
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  int HttpAgentVersionString; // eax
  __int64 v21; // rcx
  unsigned int v22; // ebx
  int LinkIdInfo; // eax
  unsigned int v25; // ebx
  int PublicKeyId; // eax
  unsigned int v27; // ebx
  int DeviceLinkFromUefi; // eax
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdi
  __int64 v32; // r14
  const unsigned __int16 *v33; // rbx
  const unsigned __int16 *v34; // rax
  int v35; // eax
  unsigned int v36; // ebx
  int v37; // eax
  unsigned int v38; // ebx
  PCWSTR StringRawBuffer; // rdx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rdi
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 *v46; // r14
  __int64 v47; // rsi
  __int64 v48; // rbx
  __int64 v49; // rax
  int v50; // eax
  unsigned int v51; // ebx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rax
  int v57; // ebx
  int v58; // [rsp+20h] [rbp-408h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-3B8h] BYREF
  __int64 v60; // [rsp+88h] [rbp-3A0h]
  _DWORD *v61; // [rsp+90h] [rbp-398h]
  __int64 v62; // [rsp+98h] [rbp-390h]
  __int64 v63; // [rsp+A0h] [rbp-388h]
  __int64 v64; // [rsp+A8h] [rbp-380h]
  int v65; // [rsp+B0h] [rbp-378h] BYREF
  _BYTE v66[16]; // [rsp+B8h] [rbp-370h] BYREF
  struct Windows::Data::Json::IJsonObject *v67; // [rsp+C8h] [rbp-360h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-358h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-350h] BYREF
  __int64 v70; // [rsp+E0h] [rbp-348h]
  _OWORD v71[2]; // [rsp+E8h] [rbp-340h] BYREF
  _OWORD v72[2]; // [rsp+108h] [rbp-320h] BYREF
  _OWORD v73[2]; // [rsp+128h] [rbp-300h] BYREF
  _OWORD v74[2]; // [rsp+148h] [rbp-2E0h] BYREF
  _OWORD v75[2]; // [rsp+168h] [rbp-2C0h] BYREF
  _BYTE v76[16]; // [rsp+188h] [rbp-2A0h] BYREF
  __int64 v77; // [rsp+198h] [rbp-290h]
  _QWORD v78[3]; // [rsp+1A8h] [rbp-280h] BYREF
  _OWORD v79[2]; // [rsp+1C0h] [rbp-268h] BYREF
  _OWORD v80[2]; // [rsp+1E0h] [rbp-248h] BYREF
  _OWORD v81[2]; // [rsp+200h] [rbp-228h] BYREF
  _BYTE v82[32]; // [rsp+220h] [rbp-208h] BYREF
  _BYTE v83[80]; // [rsp+240h] [rbp-1E8h] BYREF
  _BYTE v84[8]; // [rsp+290h] [rbp-198h] BYREF
  _BYTE v85[16]; // [rsp+298h] [rbp-190h] BYREF
  __int64 v86; // [rsp+2A8h] [rbp-180h]
  _BYTE v87[64]; // [rsp+2D0h] [rbp-158h] BYREF
  _BYTE v88[64]; // [rsp+310h] [rbp-118h] BYREF
  _BYTE v89[64]; // [rsp+350h] [rbp-D8h] BYREF
  _BYTE v90[64]; // [rsp+390h] [rbp-98h] BYREF
  __int64 v91; // [rsp+3D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+0h]

  v62 = a2;
  v63 = a8;
  v64 = a9;
  v61 = a10;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v65 = 0;
    v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 96);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
      (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83,
      v14,
      L"SendReceiveFromUri",
      &v65);
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v66);
    std::wstring::wstring(&hstringHeader, L"Content-Type");
    v15 = std::map<std::wstring,std::wstring>::operator[](v66, &hstringHeader);
    std::wstring::assign(v15, L"application/json");
    std::wstring::_Tidy_deallocate(&hstringHeader);
    v71[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v71[1] = si128;
    LOWORD(v71[0]) = 0;
    if ( (int)ModernDeployment::Autopilot::Core::AutopilotConfig::GetDeviceLinkDownloadApiVersion(v71) < 0 )
      std::wstring::assign(v71, L"3.0");
    std::wstring::wstring(&hstringHeader, L"api-version");
    v17 = std::map<std::wstring,std::wstring>::operator[](v66, &hstringHeader);
    std::wstring::operator=(v17, v71);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 8) + 32LL))(*(_QWORD *)(a1 + 8), v76);
    if ( v77 )
    {
      std::wstring::wstring(&hstringHeader, L"X-APCV");
      v19 = std::map<std::wstring,std::wstring>::operator[](v66, &hstringHeader);
      std::wstring::operator=(v19, v76);
      std::wstring::_Tidy_deallocate(&hstringHeader);
    }
    v72[0] = 0;
    v72[1] = si128;
    LOWORD(v72[0]) = 0;
    HttpAgentVersionString = Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(a6, v18, v72);
    v22 = HttpAgentVersionString;
    v65 = HttpAgentVersionString;
    if ( HttpAgentVersionString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)HttpAgentVersionString,
        v58);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v22;
    }
    v73[0] = 0;
    v73[1] = si128;
    LOWORD(v73[0]) = 0;
    v75[0] = 0;
    v75[1] = si128;
    LOWORD(v75[0]) = 0;
    LinkIdInfo = ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(v21, v73, v75);
    v25 = LinkIdInfo;
    v65 = LinkIdInfo;
    if ( LinkIdInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)LinkIdInfo,
        v58);
      std::wstring::_Tidy_deallocate(v75);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v25;
    }
    v74[0] = 0;
    v74[1] = si128;
    LOWORD(v74[0]) = 0;
    PublicKeyId = ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(*(_QWORD *)(a1 + 56), v74);
    v27 = PublicKeyId;
    v65 = PublicKeyId;
    if ( PublicKeyId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)PublicKeyId,
        v58);
      std::wstring::_Tidy_deallocate(v74);
      std::wstring::_Tidy_deallocate(v75);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v27;
    }
    v79[0] = 0;
    v79[1] = si128;
    LOWORD(v79[0]) = 0;
    if ( !*(_QWORD *)(a5 + 16) || std::wstring::find(a5, L"deviceLinkJson", 0) != -1 )
    {
      ModernDeployment::Autopilot::Core::SignedJwt::SignedJwt((ModernDeployment::Autopilot::Core::SignedJwt *)v84);
      DeviceLinkFromUefi = ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadDeviceLinkFromUefi((struct ModernDeployment::Autopilot::Core::SignedJwt *)v84);
      v65 = DeviceLinkFromUefi;
      if ( DeviceLinkFromUefi >= 0
        || (wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xFD,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
              (const char *)(unsigned int)DeviceLinkFromUefi,
              v58),
            v65 >= 0) )
      {
        if ( v86 )
          std::wstring::operator=(v79, v85);
      }
      ModernDeployment::Autopilot::Core::SignedJwt::~SignedJwt((ModernDeployment::Autopilot::Core::SignedJwt *)v84);
    }
    v67 = 0;
    v60 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v29 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v60, &v67);
    v30 = v29;
    v65 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v29,
        v58);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      std::wstring::_Tidy_deallocate(v79);
      std::wstring::_Tidy_deallocate(v74);
      std::wstring::_Tidy_deallocate(v75);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v30;
    }
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v84, off_180219538, a3);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v87, off_180219530, v73);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v88, off_180219548, v74);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v89, off_180219540, a4);
    std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v90, off_180219528, v79);
    hstringHeader.Reserved.Reserved1 = v84;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v91;
    std::vector<std::tuple<std::wstring,std::wstring>>::vector<std::tuple<std::wstring,std::wstring>>(
      v78,
      &hstringHeader);
    `eh vector destructor iterator'(
      v84,
      0x40u,
      5u,
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>);
    v31 = v78[0];
    v32 = v78[1];
    while ( v31 != v32 )
    {
      if ( !*(_QWORD *)(a5 + 16) || std::wstring::find(a5, v31 + 32, 0) != -1 )
      {
        v33 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
        v34 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31 + 32);
        v35 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v67, v34, v33);
        v36 = v35;
        v65 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x117,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
            (const char *)(unsigned int)v35,
            v58);
          std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v78);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
          std::wstring::_Tidy_deallocate(v79);
          std::wstring::_Tidy_deallocate(v74);
          std::wstring::_Tidy_deallocate(v75);
          std::wstring::_Tidy_deallocate(v73);
          std::wstring::_Tidy_deallocate(v72);
          std::wstring::_Tidy_deallocate(v76);
          std::wstring::_Tidy_deallocate(v71);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v66,
            v66);
          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
          return v36;
        }
      }
      v31 += 64;
    }
    string = 0;
    v37 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v67, &string);
    v38 = v37;
    v65 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v37,
        v58);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      std::wstring::_Tidy_deallocate(v79);
      std::wstring::_Tidy_deallocate(v74);
      std::wstring::_Tidy_deallocate(v75);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v38;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v82, StringRawBuffer);
    v80[0] = 0;
    v80[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v80[0]) = 0;
    v40 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(v82, v80);
    v41 = v40;
    v65 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v40,
        v58);
      std::string::_Tidy_deallocate(v80);
      std::wstring::_Tidy_deallocate(v82);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      std::wstring::_Tidy_deallocate(v79);
      std::wstring::_Tidy_deallocate(v74);
      std::wstring::_Tidy_deallocate(v75);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v41;
    }
    v42 = v62;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v62);
      v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v82);
      McTemplateU0zz_EventWriteTransfer(v45, DeviceLinkWebRequest, v43, v44);
    }
    v69 = 0;
    v70 = 0;
    *v61 = 0;
    v81[0] = 0;
    v81[1] = si128;
    LOWORD(v81[0]) = 0;
    v46 = *(__int64 **)(a1 + 8);
    v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
    v48 = *v46;
    std::_String_val<std::_Simple_types<char>>::_Myptr(v80);
    v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
    v50 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v48 + 8))(v46, v49, v47, 1);
    v51 = v50;
    v65 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
        (const char *)(unsigned int)v50,
        (int)L"HTTP/1.1");
      std::wstring::_Tidy_deallocate(v81);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v69);
      std::string::_Tidy_deallocate(v80);
      std::wstring::_Tidy_deallocate(v82);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      std::wstring::_Tidy_deallocate(v79);
      std::wstring::_Tidy_deallocate(v74);
      std::wstring::_Tidy_deallocate(v75);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(v76);
      std::wstring::_Tidy_deallocate(v71);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v66,
        v66);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
      return v51;
    }
    v52 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(**(_QWORD **)(a1 + 8) + 32LL))(
            *(_QWORD *)(a1 + 8),
            &hstringHeader);
    std::wstring::operator=(v63, v52);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    v53 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(**(_QWORD **)(a1 + 8) + 40LL))(
            *(_QWORD *)(a1 + 8),
            &hstringHeader);
    std::wstring::operator=(v64, v53);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    if ( *v61 == 200 )
    {
      v56 = std::string::string(&hstringHeader, v69, v69 + v70);
      v57 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::Utf8ToUnicode(v56, a11);
      v65 = v57;
      std::string::_Tidy_deallocate(&hstringHeader);
      if ( v57 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x148,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
          (const char *)(unsigned int)v57,
          (int)L"HTTP/1.1");
        std::wstring::_Tidy_deallocate(v81);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v69);
        std::string::_Tidy_deallocate(v80);
        std::wstring::_Tidy_deallocate(v82);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v78);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
        std::wstring::_Tidy_deallocate(v79);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Tidy_deallocate(v75);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::_Tidy_deallocate(v72);
        std::wstring::_Tidy_deallocate(v76);
        std::wstring::_Tidy_deallocate(v71);
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
          v66,
          v66);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
        return (unsigned int)v57;
      }
    }
    else if ( v70 )
    {
      v54 = std::string::string(&hstringHeader, v69, v69 + v70);
      v55 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::Utf8ToUnicode(v54, a11);
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x142,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
          (const char *)(unsigned int)v55,
          (int)L"HTTP/1.1");
      std::string::_Tidy_deallocate(&hstringHeader);
    }
    std::wstring::_Tidy_deallocate(v81);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v69);
    std::string::_Tidy_deallocate(v80);
    std::wstring::_Tidy_deallocate(v82);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    std::vector<Microsoft::Windows::Autopilot::Diagnostics::StaticDataSourceEntries::WmiElementSourceEntry>::_Tidy(v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    std::wstring::_Tidy_deallocate(v79);
    std::wstring::_Tidy_deallocate(v74);
    std::wstring::_Tidy_deallocate(v75);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(v76);
    std::wstring::_Tidy_deallocate(v71);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v66,
      v66);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v83);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\attestationanddiscoverymanager.cpp",
      (const char *)0x80004001LL,
      v58);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18013491c  mov     rax, rsp
0x18013491f  push    rbx
0x180134920  push    rsi
0x180134921  push    rdi
0x180134922  push    r12
0x180134924  push    r13
0x180134926  push    r14
0x180134928  push    r15
0x18013492a  sub     rsp, 3F0h
0x180134931  movaps  xmmword ptr [rax-48h], xmm6
0x180134935  mov     rax, cs:__security_cookie
0x18013493c  xor     rax, rsp
0x18013493f  mov     [rsp+428h+var_58], rax
0x180134947  mov     rsi, r9
0x18013494a  mov     rdi, r8
0x18013494d  mov     [rsp+428h+var_390], rdx
0x180134955  mov     r13, rcx
0x180134958  mov     r15, [rsp+428h+arg_20]
0x180134960  mov     rax, [rsp+428h+arg_38]
0x180134968  mov     [rsp+428h+var_388], rax
0x180134970  mov     rax, [rsp+428h+arg_40]
0x180134978  mov     [rsp+428h+var_380], rax
0x180134980  mov     rax, [rsp+428h+arg_48]
0x180134988  mov     [rsp+428h+var_398], rax
0x180134990  mov     r12, [rsp+428h+arg_50]
0x180134998  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013499f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801349a4  xor     r14d, r14d
0x1801349a7  test    al, al
0x1801349a9  jz      loc_1801358F1
0x1801349af  mov     [rsp+428h+var_378], r14d
0x1801349b7  lea     rcx, [r13+60h]
0x1801349bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801349c0  lea     r9, [rsp+428h+var_378]; int *
0x1801349c8  lea     r8, aSendreceivefro; "SendReceiveFromUri"
0x1801349cf  mov     rdx, rax; unsigned __int16 *
0x1801349d2  lea     rcx, [rsp+428h+var_1E8]; this
0x1801349da  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x1801349df  nop
0x1801349e0  lea     rcx, [rsp+428h+var_370]
0x1801349e8  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1801349ed  nop
0x1801349ee  lea     rdx, aContentType; "Content-Type"
0x1801349f5  lea     rcx, [rsp+428h+hstringHeader]
0x1801349fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801349ff  nop
0x180134a00  lea     rdx, [rsp+428h+hstringHeader]
0x180134a05  lea     rcx, [rsp+428h+var_370]
0x180134a0d  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180134a12  lea     rdx, aApplicationJso; "application/json"
0x180134a19  mov     rcx, rax
0x180134a1c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180134a21  nop
0x180134a22  lea     rcx, [rsp+428h+hstringHeader]
0x180134a27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134a2c  xorps   xmm0, xmm0
0x180134a2f  movups  [rsp+428h+var_340], xmm0
0x180134a37  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180134a3f  movdqu  [rsp+428h+var_330], xmm6
0x180134a48  mov     word ptr [rsp+428h+var_340], r14w
0x180134a51  lea     rcx, [rsp+428h+var_340]
0x180134a59  call    ?GetDeviceLinkDownloadApiVersion@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetDeviceLinkDownloadApiVersion(std::wstring &)
0x180134a5e  test    eax, eax
0x180134a60  jns     short loc_180134A76
0x180134a62  lea     rdx, a30; "3.0"
0x180134a69  lea     rcx, [rsp+428h+var_340]
0x180134a71  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180134a76  lea     rdx, aApiVersion; "api-version"
0x180134a7d  lea     rcx, [rsp+428h+hstringHeader]
0x180134a82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180134a87  nop
0x180134a88  lea     rdx, [rsp+428h+hstringHeader]
0x180134a8d  lea     rcx, [rsp+428h+var_370]
0x180134a95  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180134a9a  lea     rdx, [rsp+428h+var_340]
0x180134aa2  mov     rcx, rax
0x180134aa5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180134aaa  nop
0x180134aab  lea     rcx, [rsp+428h+hstringHeader]
0x180134ab0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134ab5  mov     rcx, [r13+8]
0x180134ab9  mov     rax, [rcx]
0x180134abc  lea     rdx, [rsp+428h+var_2A0]
0x180134ac4  mov     rax, [rax+20h]
0x180134ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134acd  nop
0x180134ace  cmp     [rsp+428h+var_290], r14
0x180134ad6  jz      short loc_180134B17
0x180134ad8  lea     rdx, aXApcv; "X-APCV"
0x180134adf  lea     rcx, [rsp+428h+hstringHeader]
0x180134ae4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180134ae9  nop
0x180134aea  lea     rdx, [rsp+428h+hstringHeader]
0x180134aef  lea     rcx, [rsp+428h+var_370]
0x180134af7  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180134afc  lea     rdx, [rsp+428h+var_2A0]
0x180134b04  mov     rcx, rax
0x180134b07  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180134b0c  nop
0x180134b0d  lea     rcx, [rsp+428h+hstringHeader]
0x180134b12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134b17  xorps   xmm0, xmm0
0x180134b1a  movups  [rsp+428h+var_320], xmm0
0x180134b22  movdqu  [rsp+428h+var_310], xmm6
0x180134b2b  mov     word ptr [rsp+428h+var_320], r14w
0x180134b34  lea     r8, [rsp+428h+var_320]
0x180134b3c  mov     ecx, [rsp+428h+arg_28]
0x180134b43  call    ?GetHttpAgentVersionString@HttpRequestVersion@Autopilot@Windows@Microsoft@@SAJKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HttpRequestVersion::GetHttpAgentVersionString(ulong,ulong,std::wstring &)
0x180134b48  mov     ebx, eax
0x180134b4a  mov     [rsp+428h+var_378], eax
0x180134b51  test    eax, eax
0x180134b53  jns     short loc_180134BC6
0x180134b55  mov     rcx, [rsp+428h]; this
0x180134b5d  mov     r9d, eax; char *
0x180134b60  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180134b67  mov     edx, 0EAh; void *
0x180134b6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134b71  nop
0x180134b72  lea     rcx, [rsp+428h+var_320]
0x180134b7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134b7f  nop
0x180134b80  lea     rcx, [rsp+428h+var_2A0]
0x180134b88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134b8d  nop
0x180134b8e  lea     rcx, [rsp+428h+var_340]
0x180134b96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134b9b  nop
0x180134b9c  lea     rdx, [rsp+428h+var_370]
0x180134ba4  lea     rcx, [rsp+428h+var_370]
0x180134bac  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180134bb1  nop
0x180134bb2  lea     rcx, [rsp+428h+var_1E8]; this
0x180134bba  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180134bbf  mov     eax, ebx
0x180134bc1  jmp     loc_18013591D
0x180134bc6  xorps   xmm0, xmm0
0x180134bc9  movups  [rsp+428h+var_300], xmm0
0x180134bd1  movdqu  [rsp+428h+var_2F0], xmm6
0x180134bda  mov     word ptr [rsp+428h+var_300], r14w
0x180134be3  movups  [rsp+428h+var_2C0], xmm0
0x180134beb  movdqu  [rsp+428h+var_2B0], xmm6
0x180134bf4  mov     word ptr [rsp+428h+var_2C0], r14w
0x180134bfd  lea     r8, [rsp+428h+var_2C0]
0x180134c05  lea     rdx, [rsp+428h+var_300]
0x180134c0d  call    ?GetLinkIdInfo@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(std::wstring &,std::wstring &)
0x180134c12  mov     ebx, eax
0x180134c14  mov     [rsp+428h+var_378], eax
0x180134c1b  test    eax, eax
0x180134c1d  jns     loc_180134CB0
0x180134c23  mov     rcx, [rsp+428h]; this
0x180134c2b  mov     r9d, eax; char *
0x180134c2e  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180134c35  mov     edx, 0EFh; void *
0x180134c3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134c3f  nop
0x180134c40  lea     rcx, [rsp+428h+var_2C0]
0x180134c48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134c4d  nop
0x180134c4e  lea     rcx, [rsp+428h+var_300]
0x180134c56  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134c5b  nop
0x180134c5c  lea     rcx, [rsp+428h+var_320]
0x180134c64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134c69  nop
0x180134c6a  lea     rcx, [rsp+428h+var_2A0]
0x180134c72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134c77  nop
0x180134c78  lea     rcx, [rsp+428h+var_340]
0x180134c80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134c85  nop
0x180134c86  lea     rdx, [rsp+428h+var_370]
0x180134c8e  lea     rcx, [rsp+428h+var_370]
0x180134c96  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180134c9b  nop
0x180134c9c  lea     rcx, [rsp+428h+var_1E8]; this
0x180134ca4  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180134ca9  mov     eax, ebx
0x180134cab  jmp     loc_18013591D
0x180134cb0  xorps   xmm0, xmm0
0x180134cb3  movups  [rsp+428h+var_2E0], xmm0
0x180134cbb  movdqu  [rsp+428h+var_2D0], xmm6
0x180134cc4  mov     word ptr [rsp+428h+var_2E0], r14w
0x180134ccd  lea     rdx, [rsp+428h+var_2E0]
0x180134cd5  mov     rcx, [r13+38h]
0x180134cd9  call    ?GetPublicKeyId@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(std::wstring &)
0x180134cde  mov     ebx, eax
0x180134ce0  mov     [rsp+428h+var_378], eax
0x180134ce7  test    eax, eax
0x180134ce9  jns     loc_180134D8A
0x180134cef  mov     rcx, [rsp+428h]; this
0x180134cf7  mov     r9d, eax; char *
0x180134cfa  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180134d01  mov     edx, 0F2h; void *
0x180134d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134d0b  nop
0x180134d0c  lea     rcx, [rsp+428h+var_2E0]
0x180134d14  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134d19  nop
0x180134d1a  lea     rcx, [rsp+428h+var_2C0]
0x180134d22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134d27  nop
0x180134d28  lea     rcx, [rsp+428h+var_300]
0x180134d30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134d35  nop
0x180134d36  lea     rcx, [rsp+428h+var_320]
0x180134d3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134d43  nop
0x180134d44  lea     rcx, [rsp+428h+var_2A0]
0x180134d4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134d51  nop
0x180134d52  lea     rcx, [rsp+428h+var_340]
0x180134d5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134d5f  nop
0x180134d60  lea     rdx, [rsp+428h+var_370]
0x180134d68  lea     rcx, [rsp+428h+var_370]
0x180134d70  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180134d75  nop
0x180134d76  lea     rcx, [rsp+428h+var_1E8]; this
0x180134d7e  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180134d83  mov     eax, ebx
0x180134d85  jmp     loc_18013591D
0x180134d8a  xorps   xmm0, xmm0
0x180134d8d  movups  [rsp+428h+var_268], xmm0
0x180134d95  movdqu  [rsp+428h+var_258], xmm6
0x180134d9e  mov     word ptr [rsp+428h+var_268], r14w
0x180134da7  cmp     [r15+10h], r14
0x180134dab  jz      short loc_180134DC5
0x180134dad  xor     r8d, r8d
0x180134db0  lea     rdx, aDevicelinkjson; "deviceLinkJson"
0x180134db7  mov     rcx, r15
0x180134dba  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180134dbf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180134dc3  jz      short loc_180134E3F
0x180134dc5  lea     rcx, [rsp+428h+var_198]; this
0x180134dcd  call    ??0SignedJwt@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::SignedJwt::SignedJwt(void)
0x180134dd2  nop
0x180134dd3  lea     rcx, [rsp+428h+var_198]; struct ModernDeployment::Autopilot::Core::SignedJwt *
0x180134ddb  call    ?LoadDeviceLinkFromUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEAVSignedJwt@234@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadDeviceLinkFromUefi(ModernDeployment::Autopilot::Core::SignedJwt &)
0x180134de0  mov     [rsp+428h+var_378], eax
0x180134de7  mov     rcx, [rsp+428h]; this
0x180134def  test    eax, eax
0x180134df1  jns     short loc_180134E12
0x180134df3  mov     r9d, eax; char *
0x180134df6  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180134dfd  mov     edx, 0FDh; void *
0x180134e02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180134e07  mov     eax, [rsp+428h+var_378]
0x180134e0e  test    eax, eax
0x180134e10  js      short loc_180134E32
0x180134e12  cmp     [rsp+428h+var_180], r14
0x180134e1a  jz      short loc_180134E32
0x180134e1c  lea     rdx, [rsp+428h+var_190]
0x180134e24  lea     rcx, [rsp+428h+var_268]
0x180134e2c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180134e31  nop
0x180134e32  lea     rcx, [rsp+428h+var_198]; this
0x180134e3a  call    ??1SignedJwt@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::SignedJwt::~SignedJwt(void)
0x180134e3f  mov     [rsp+428h+var_360], r14
0x180134e47  mov     [rsp+428h+var_3A0], r14
0x180134e4f  mov     r9d, 1Ch; unsigned int
0x180134e55  lea     r8d, [r9+1]; unsigned int
0x180134e59  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180134e60  lea     rcx, [rsp+428h+hstringHeader]; hstringHeader
0x180134e65  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180134e6a  lea     rdx, [rsp+428h+var_360]
0x180134e72  mov     rcx, [rsp+428h+var_3A0]
0x180134e7a  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180134e7f  mov     ebx, eax
0x180134e81  mov     [rsp+428h+var_378], eax
0x180134e88  test    eax, eax
0x180134e8a  jns     loc_180134F47
0x180134e90  mov     rcx, [rsp+428h]; this
0x180134e98  mov     r9d, eax; char *
0x180134e9b  lea     r8, aOnecoreuapAdmi_158; "onecoreuap\\admin\\moderndeployment\\au"...
0x180134ea2  mov     edx, 107h; void *
0x180134ea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134eac  nop
0x180134ead  lea     rcx, [rsp+428h+var_360]
0x180134eb5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180134eba  nop
0x180134ebb  lea     rcx, [rsp+428h+var_268]
0x180134ec3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134ec8  nop
0x180134ec9  lea     rcx, [rsp+428h+var_2E0]
0x180134ed1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134ed6  nop
0x180134ed7  lea     rcx, [rsp+428h+var_2C0]
0x180134edf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134ee4  nop
0x180134ee5  lea     rcx, [rsp+428h+var_300]
0x180134eed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134ef2  nop
0x180134ef3  lea     rcx, [rsp+428h+var_320]
0x180134efb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134f00  nop
0x180134f01  lea     rcx, [rsp+428h+var_2A0]
0x180134f09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134f0e  nop
0x180134f0f  lea     rcx, [rsp+428h+var_340]
0x180134f17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
