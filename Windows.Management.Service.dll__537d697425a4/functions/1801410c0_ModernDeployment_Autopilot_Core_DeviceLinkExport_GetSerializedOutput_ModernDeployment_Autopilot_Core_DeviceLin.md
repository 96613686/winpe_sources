# ModernDeployment::Autopilot::Core::DeviceLinkExport::GetSerializedOutput(ModernDeployment::Autopilot::Core::DeviceLinkInfo &,ModernDeployment::Autopilot::Core::DeviceLinkFormatFlags const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801410c0`
- end: `0x180141d14`
- name: `?GetSerializedOutput@DeviceLinkExport@Core@Autopilot@ModernDeployment@@SAJAEAVDeviceLinkInfo@234@AEBW4DeviceLinkFormatFlags@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3156`
- prototype: ``
- caller_count: `3`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180129d74`
- `0x180140b18`
- `0x1801b0018`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080c10`
- `0x180081d00`
- `0x180081d54`
- `0x180081f38`
- `0x180084574`
- `0x180086044`
- `0x180089660`
- `0x180089850`
- `0x18008a9c4`
- `0x18008aecc`
- `0x18008d290`
- `0x1800901c0`
- `0x1800964d4`
- `0x1800a1600`
- `0x180132294`
- `0x180136e28`
- `0x180137284`
- `0x1801388a8`
- `0x180138d20`
- `0x180140970`
- `0x1801410c0`
- `0x180142c50`
- `0x180144ec0`
- `0x1801453c0`
- `0x1801466b0`
- `0x180147198`
- `0x180147834`
- `0x1801478ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014144b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180141686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014144b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180141686`

## string_xrefs

- `0x18014131f`: `Windows.Data.Json.JsonObject`
- `0x18014152e`: `Windows.Data.Json.JsonObject`
- `0x180141119`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141160`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141198`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801411d5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18014120a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141250`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801412ce`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141356`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801413b2`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141408`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801414e4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18014155f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801415d1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141638`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801416ed`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801417c8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141876`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x1801419fb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141aaa`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141b6b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x180141c31`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkExport::GetSerializedOutput(
        __int64 a1,
        int *a2,
        __int64 a3)
{
  int v5; // ebx
  bool v6; // r13
  char v7; // cl
  int v8; // edi
  int v9; // esi
  int v10; // r15d
  int v11; // r14d
  __int64 v12; // rcx
  int JsonSerializationFieldNames; // eax
  __int64 v14; // r8
  unsigned int v15; // r12d
  int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  PCWSTR v26; // rdx
  int v27; // edi
  int CompressedContent; // eax
  unsigned int v29; // ebx
  int v30; // eax
  __int64 v31; // r8
  unsigned int v32; // ebx
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // eax
  unsigned int v36; // ebx
  PCWSTR StringRawBuffer; // rax
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  int v43; // eax
  unsigned int v44; // ebx
  int EnvelopeIncludedFields; // eax
  unsigned int v46; // ebx
  int AutopilotQrSchemaUri; // eax
  unsigned int v48; // ebx
  int v49; // eax
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  int v53; // eax
  unsigned int v54; // ebx
  int v55; // [rsp+20h] [rbp-1B8h]
  int v56; // [rsp+20h] [rbp-1B8h]
  int v57; // [rsp+20h] [rbp-1B8h]
  HSTRING_HEADER v60; // [rsp+40h] [rbp-198h] BYREF
  __int64 v61; // [rsp+58h] [rbp-180h]
  HSTRING string; // [rsp+60h] [rbp-178h] BYREF
  HSTRING v63; // [rsp+68h] [rbp-170h] BYREF
  int v64[4]; // [rsp+70h] [rbp-168h] BYREF
  __m128i si128; // [rsp+80h] [rbp-158h]
  __int128 v66; // [rsp+90h] [rbp-148h] BYREF
  __m128i v67; // [rsp+A0h] [rbp-138h]
  _BYTE v68[64]; // [rsp+B0h] [rbp-128h] BYREF
  _BYTE v69[24]; // [rsp+F0h] [rbp-E8h] BYREF
  int v70[4]; // [rsp+108h] [rbp-D0h] BYREF
  __m128i v71; // [rsp+118h] [rbp-C0h]
  __int128 v72; // [rsp+128h] [rbp-B0h] BYREF
  __m128i v73; // [rsp+138h] [rbp-A0h]
  _OWORD v74[2]; // [rsp+148h] [rbp-90h] BYREF
  _BYTE v75[24]; // [rsp+168h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+180h] [rbp-58h] BYREF
  __int64 v77; // [rsp+198h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
      (const char *)0x80004001LL,
      v55);
    return 2147500033LL;
  }
  v5 = *a2;
  v6 = (v5 & 2) != 0;
  v7 = v5 & 1;
  if ( (v5 & 2) != 0 )
  {
    if ( !v7 )
      goto LABEL_8;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
      (const char *)0x80070057LL,
      v55);
    return 2147942487LL;
  }
  if ( !v7 )
    goto LABEL_7;
LABEL_8:
  v8 = v5 & 0x40;
  v9 = v5 & 0x20;
  if ( (v5 & 0x20) != 0 && (v5 & 0x40) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
      (const char *)0x80070057LL,
      v55);
    return 2147942487LL;
  }
  v10 = v5 & 0x10;
  v11 = v5 & 8;
  if ( (v5 & 8) != 0 )
  {
    if ( (v5 & 0x10) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
        (const char *)0x80070057LL,
        v55);
      return 2147942487LL;
    }
  }
  else if ( (v5 & 0x10) == 0 )
  {
    goto LABEL_18;
  }
  if ( (v5 & 0x20) == 0 && (v5 & 0x40) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
      (const char *)0x80070057LL,
      v55);
    return 2147942487LL;
  }
LABEL_18:
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v68);
  LOBYTE(v12) = (v5 & 2) != 0;
  JsonSerializationFieldNames = ModernDeployment::Autopilot::Core::AutopilotConfig::GetJsonSerializationFieldNames(
                                  v12,
                                  v68);
  v15 = JsonSerializationFieldNames;
  if ( JsonSerializationFieldNames < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
      (const char *)(unsigned int)JsonSerializationFieldNames,
      v55);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
    return v15;
  }
  v16 = v5 & 4;
  if ( v11 || v10 || v9 || v8 )
  {
    *(_OWORD *)v64 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v64[0]) = 0;
    if ( v16 )
    {
      LOBYTE(v14) = v6;
      v27 = a1;
      CompressedContent = ModernDeployment::Autopilot::Core::DeviceLinkInfo::GetCompressedContent(a1, v68, v14, v64);
      v29 = CompressedContent;
      if ( CompressedContent < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x99,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)CompressedContent,
          v55);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v29;
      }
    }
    else
    {
      v63 = 0;
      string = 0;
      v61 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v60, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
      v30 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
              v61,
              &string);
      v32 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v30,
          v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v63);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v32;
      }
      LOBYTE(v31) = v6;
      v33 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::Serialize(a1, v68, v31, &string);
      v34 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v33,
          v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v63);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v34;
      }
      v35 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(string, &v63);
      v36 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v35,
          v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v63);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v36;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v63, 0);
      std::wstring::wstring(&hstringHeader, StringRawBuffer);
      v72 = 0;
      v73 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v72) = 0;
      v38 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8(&hstringHeader, &v72);
      v39 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v38,
          v55);
        std::string::_Tidy_deallocate(&v72);
        std::wstring::_Tidy_deallocate(&hstringHeader);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v63);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v39;
      }
      v66 = 0;
      v67 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v66) = 0;
      v40 = std::_String_val<std::_Simple_types<char>>::_Myptr(&v72);
      std::vector<unsigned char>::vector<unsigned char>(v69, v40, v40 + v73.m128i_i64[0]);
      v41 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertByteArrayToUnicodeB64(v69, &v66);
      v42 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v41,
          v55);
        std::vector<unsigned char>::_Tidy(v69);
        std::wstring::_Tidy_deallocate(&v66);
        std::string::_Tidy_deallocate(&v72);
        std::wstring::_Tidy_deallocate(&hstringHeader);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v63);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v42;
      }
      if ( v8 )
      {
        v43 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertToUriSafeB64(&v66, v64);
        v44 = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB7,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
            (const char *)(unsigned int)v43,
            v55);
          std::vector<unsigned char>::_Tidy(v69);
          std::wstring::_Tidy_deallocate(&v66);
          std::string::_Tidy_deallocate(&v72);
          std::wstring::_Tidy_deallocate(&hstringHeader);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          Windows::Internal::String::~String((Windows::Internal::String *)&v63);
          std::wstring::_Tidy_deallocate(v64);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
          return v44;
        }
      }
      else
      {
        std::wstring::operator=(v64, &v66);
      }
      std::vector<unsigned char>::_Tidy(v69);
      std::wstring::_Tidy_deallocate(&v66);
      std::string::_Tidy_deallocate(&v72);
      std::wstring::_Tidy_deallocate(&hstringHeader);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v63);
      v27 = a1;
    }
    if ( !v11 && !v10 )
    {
      std::wstring::operator=(a3, v64);
      std::wstring::_Tidy_deallocate(v64);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
      return 0;
    }
    *(_OWORD *)v70 = 0;
    v71 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v70[0]) = 0;
    v74[0] = 0;
    v74[1] = v71;
    LOWORD(v74[0]) = 0;
    EnvelopeIncludedFields = ModernDeployment::Autopilot::Core::AutopilotConfig::GetEnvelopeIncludedFields(
                               (unsigned int)(v11 != 0) + 1,
                               v74);
    v46 = EnvelopeIncludedFields;
    if ( EnvelopeIncludedFields < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCE,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
        (const char *)(unsigned int)EnvelopeIncludedFields,
        v55);
      std::wstring::_Tidy_deallocate(v74);
      std::wstring::_Tidy_deallocate(v70);
      std::wstring::_Tidy_deallocate(v64);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
      return v46;
    }
    ModernDeployment::Autopilot::Core::DeviceLinkEncoding::SplitSemicolonDelimitedString(v75, v74);
    if ( v11 )
    {
      v66 = 0;
      v67 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v66) = 0;
      AutopilotQrSchemaUri = ModernDeployment::Autopilot::Core::AutopilotConfig::GetAutopilotQrSchemaUri(&v66);
      v48 = AutopilotQrSchemaUri;
      if ( AutopilotQrSchemaUri < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)AutopilotQrSchemaUri,
          v55);
        std::wstring::_Tidy_deallocate(&v66);
        std::vector<std::wstring>::_Tidy(v75);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v48;
      }
      v49 = std::vector<std::wstring>::vector<std::wstring>(v69, v75);
      v50 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::PopulateUriScheme(
              v27,
              (unsigned int)&v66,
              v49,
              (unsigned int)v68,
              (__int64)v64,
              (__int64)v70);
      v51 = v50;
      if ( v50 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v50,
          v56);
        std::wstring::_Tidy_deallocate(&v66);
        std::vector<std::wstring>::_Tidy(v75);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v51;
      }
      std::wstring::_Tidy_deallocate(&v66);
    }
    else
    {
      v52 = std::vector<std::wstring>::vector<std::wstring>(v69, v75);
      v53 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::PopulateJsonEnvelope(
              v27,
              v52,
              (unsigned int)v68,
              (unsigned int)v64,
              (__int64)v70);
      v54 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v53,
          v57);
        std::vector<std::wstring>::_Tidy(v75);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v64);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v54;
      }
    }
    std::wstring::operator=(a3, v70);
    std::vector<std::wstring>::_Tidy(v75);
    std::wstring::_Tidy_deallocate(v74);
    std::wstring::_Tidy_deallocate(v70);
    std::wstring::_Tidy_deallocate(v64);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
    return 0;
  }
  else if ( v16 )
  {
    LOBYTE(v14) = v6;
    v17 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::GetCompressedContent(a1, v68, v14, a3);
    v18 = v17;
    if ( v17 >= 0 )
    {
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
        (const char *)(unsigned int)v17,
        v55);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
      return v18;
    }
  }
  else
  {
    v63 = 0;
    v77 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v19 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v77, &v63);
    v21 = v19;
    if ( v19 >= 0 )
    {
      LOBYTE(v20) = v6;
      v22 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::Serialize(a1, v68, v20, &v63);
      v23 = v22;
      if ( v22 >= 0 )
      {
        string = 0;
        v24 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v63, &string);
        v25 = v24;
        if ( v24 >= 0 )
        {
          v26 = WindowsGetStringRawBuffer(string, 0);
          std::wstring::assign(a3, v26);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8C,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
            (const char *)(unsigned int)v24,
            v55);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
          return v25;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
          (const char *)(unsigned int)v22,
          v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
        return v23;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkexport.cpp",
        (const char *)(unsigned int)v19,
        v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v68);
      return v21;
    }
  }
}

```

## disassembly

```asm
0x1801410c0  mov     [rsp+arg_8], rbx
0x1801410c5  mov     [rsp+arg_18], rsi
0x1801410ca  push    rdi
0x1801410cb  push    r12
0x1801410cd  push    r13
0x1801410cf  push    r14
0x1801410d1  push    r15
0x1801410d3  sub     rsp, 1B0h
0x1801410da  mov     rax, cs:__security_cookie
0x1801410e1  xor     rax, rsp
0x1801410e4  mov     [rsp+1D8h+var_38], rax
0x1801410ec  mov     [rsp+1D8h+var_1A0], r8
0x1801410f1  mov     rbx, rdx
0x1801410f4  mov     [rsp+1D8h+var_1A8], rcx
0x1801410f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180141100  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180141105  test    al, al
0x180141107  jnz     short loc_180141131
0x180141109  mov     rcx, [rsp+1D8h]; this
0x180141111  mov     ebx, 80004001h
0x180141116  mov     r9d, ebx; char *
0x180141119  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141120  mov     edx, 55h ; 'U'; void *
0x180141125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014112a  mov     eax, ebx
0x18014112c  jmp     loc_180141CE6
0x180141131  mov     ebx, [rbx]
0x180141133  bt      ebx, 1
0x180141137  setb    r13b
0x18014113b  mov     cl, bl
0x18014113d  and     cl, 1
0x180141140  bt      ebx, 1
0x180141144  jnb     short loc_18014114C
0x180141146  test    cl, cl
0x180141148  jnz     short loc_180141150
0x18014114a  jmp     short loc_180141178
0x18014114c  test    cl, cl
0x18014114e  jnz     short loc_180141178
0x180141150  mov     rcx, [rsp+1D8h]; this
0x180141158  mov     ebx, 80070057h
0x18014115d  mov     r9d, ebx; char *
0x180141160  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141167  mov     edx, 62h ; 'b'; void *
0x18014116c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141171  mov     eax, ebx
0x180141173  jmp     loc_180141CE6
0x180141178  mov     esi, ebx
0x18014117a  mov     edi, ebx
0x18014117c  and     edi, 40h
0x18014117f  and     esi, 20h
0x180141182  jz      short loc_1801411B0
0x180141184  test    edi, edi
0x180141186  jz      short loc_1801411B0
0x180141188  mov     rcx, [rsp+1D8h]; this
0x180141190  mov     ebx, 80070057h
0x180141195  mov     r9d, ebx; char *
0x180141198  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014119f  mov     edx, 68h ; 'h'; void *
0x1801411a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801411a9  mov     eax, ebx
0x1801411ab  jmp     loc_180141CE6
0x1801411b0  mov     r14d, ebx
0x1801411b3  mov     r15d, ebx
0x1801411b6  and     r15d, 10h
0x1801411ba  and     r14d, 8
0x1801411be  jz      short loc_1801411ED
0x1801411c0  test    r15d, r15d
0x1801411c3  jz      short loc_1801411F2
0x1801411c5  mov     rcx, [rsp+1D8h]; this
0x1801411cd  mov     ebx, 80070057h
0x1801411d2  mov     r9d, ebx; char *
0x1801411d5  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801411dc  mov     edx, 6Eh ; 'n'; void *
0x1801411e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801411e6  mov     eax, ebx
0x1801411e8  jmp     loc_180141CE6
0x1801411ed  test    r15d, r15d
0x1801411f0  jz      short loc_180141220
0x1801411f2  test    esi, esi
0x1801411f4  jnz     short loc_180141220
0x1801411f6  test    edi, edi
0x1801411f8  jnz     short loc_180141220
0x1801411fa  mov     rcx, [rsp+1D8h]; this
0x180141202  mov     ebx, 80070057h
0x180141207  mov     r9d, ebx; char *
0x18014120a  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141211  lea     edx, [rsi+74h]; void *
0x180141214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141219  mov     eax, ebx
0x18014121b  jmp     loc_180141CE6
0x180141220  lea     rcx, [rsp+1D8h+var_128]
0x180141228  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x18014122d  nop
0x18014122e  lea     rdx, [rsp+1D8h+var_128]
0x180141236  mov     cl, r13b
0x180141239  call    ?GetJsonSerializationFieldNames@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJ_NAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetJsonSerializationFieldNames(bool,std::unordered_map<std::wstring,std::wstring> &)
0x18014123e  mov     r12d, eax
0x180141241  test    eax, eax
0x180141243  jns     short loc_180141277
0x180141245  mov     rcx, [rsp+1D8h]; this
0x18014124d  mov     r9d, eax; char *
0x180141250  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141257  mov     edx, 79h ; 'y'; void *
0x18014125c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141261  nop
0x180141262  lea     rcx, [rsp+1D8h+var_128]
0x18014126a  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18014126f  mov     eax, r12d
0x180141272  jmp     loc_180141CE6
0x180141277  and     ebx, 4
0x18014127a  xor     r12d, r12d
0x18014127d  test    r14d, r14d
0x180141280  jnz     loc_18014148F
0x180141286  test    r15d, r15d
0x180141289  jnz     loc_18014148F
0x18014128f  test    esi, esi
0x180141291  jnz     loc_18014148F
0x180141297  test    edi, edi
0x180141299  jnz     loc_18014148F
0x18014129f  test    ebx, ebx
0x1801412a1  jz      short loc_180141308
0x1801412a3  mov     r9, [rsp+1D8h+var_1A0]
0x1801412a8  mov     r8b, r13b
0x1801412ab  lea     rdx, [rsp+1D8h+var_128]
0x1801412b3  mov     rcx, [rsp+1D8h+var_1A8]
0x1801412b8  call    ?GetCompressedContent@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::GetCompressedContent(std::unordered_map<std::wstring,std::wstring> const &,bool,std::wstring &)
0x1801412bd  mov     ebx, eax
0x1801412bf  test    eax, eax
0x1801412c1  jns     short loc_1801412F4
0x1801412c3  mov     rcx, [rsp+1D8h]; this
0x1801412cb  mov     r9d, eax; char *
0x1801412ce  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801412d5  mov     edx, 80h; void *
0x1801412da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801412df  nop
0x1801412e0  lea     rcx, [rsp+1D8h+var_128]
0x1801412e8  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801412ed  mov     eax, ebx
0x1801412ef  jmp     loc_180141CE6
0x1801412f4  lea     rcx, [rsp+1D8h+var_128]
0x1801412fc  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180141301  xor     eax, eax
0x180141303  jmp     loc_180141CE6
0x180141308  mov     [rsp+1D8h+var_170], r12
0x18014130d  mov     [rsp+1D8h+var_40], r12
0x180141315  mov     r9d, 1Ch; unsigned int
0x18014131b  lea     r8d, [r9+1]; unsigned int
0x18014131f  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180141326  lea     rcx, [rsp+1D8h+hstringHeader]; hstringHeader
0x18014132e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180141333  lea     rdx, [rsp+1D8h+var_170]
0x180141338  mov     rcx, [rsp+1D8h+var_40]
0x180141340  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180141345  mov     ebx, eax
0x180141347  test    eax, eax
0x180141349  jns     short loc_180141387
0x18014134b  mov     rcx, [rsp+1D8h]; this
0x180141353  mov     r9d, eax; char *
0x180141356  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014135d  mov     edx, 87h; void *
0x180141362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141367  nop
0x180141368  lea     rcx, [rsp+1D8h+var_170]
0x18014136d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141372  nop
0x180141373  lea     rcx, [rsp+1D8h+var_128]
0x18014137b  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180141380  mov     eax, ebx
0x180141382  jmp     loc_180141CE6
0x180141387  lea     r9, [rsp+1D8h+var_170]
0x18014138c  mov     r8b, r13b
0x18014138f  lea     rdx, [rsp+1D8h+var_128]
0x180141397  mov     rcx, [rsp+1D8h+var_1A8]
0x18014139c  call    ?Serialize@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::Serialize(std::unordered_map<std::wstring,std::wstring> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1801413a1  mov     ebx, eax
0x1801413a3  test    eax, eax
0x1801413a5  jns     short loc_1801413E3
0x1801413a7  mov     rcx, [rsp+1D8h]; this
0x1801413af  mov     r9d, eax; char *
0x1801413b2  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801413b9  mov     edx, 89h; void *
0x1801413be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801413c3  nop
0x1801413c4  lea     rcx, [rsp+1D8h+var_170]
0x1801413c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801413ce  nop
0x1801413cf  lea     rcx, [rsp+1D8h+var_128]
0x1801413d7  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801413dc  mov     eax, ebx
0x1801413de  jmp     loc_180141CE6
0x1801413e3  mov     [rsp+1D8h+string], r12
0x1801413e8  lea     rdx, [rsp+1D8h+string]
0x1801413ed  mov     rcx, [rsp+1D8h+var_170]
0x1801413f2  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1801413f7  mov     ebx, eax
0x1801413f9  test    eax, eax
0x1801413fb  jns     short loc_180141444
0x1801413fd  mov     rcx, [rsp+1D8h]; this
0x180141405  mov     r9d, eax; char *
0x180141408  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014140f  mov     edx, 8Ch; void *
0x180141414  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141419  nop
0x18014141a  lea     rcx, [rsp+1D8h+string]; this
0x18014141f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180141424  nop
0x180141425  lea     rcx, [rsp+1D8h+var_170]
0x18014142a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014142f  nop
0x180141430  lea     rcx, [rsp+1D8h+var_128]
0x180141438  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18014143d  mov     eax, ebx
0x18014143f  jmp     loc_180141CE6
0x180141444  xor     edx, edx; length
0x180141446  mov     rcx, [rsp+1D8h+string]; string
0x18014144b  call    cs:__imp_WindowsGetStringRawBuffer
0x180141452  nop     dword ptr [rax+rax+00h]
0x180141457  mov     rdx, rax
0x18014145a  mov     rcx, [rsp+1D8h+var_1A0]
0x18014145f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180141464  nop
0x180141465  lea     rcx, [rsp+1D8h+string]; this
0x18014146a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18014146f  nop
0x180141470  lea     rcx, [rsp+1D8h+var_170]
0x180141475  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014147a  nop
0x18014147b  lea     rcx, [rsp+1D8h+var_128]
0x180141483  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180141488  xor     eax, eax
0x18014148a  jmp     loc_180141CE6
0x18014148f  xorps   xmm0, xmm0
0x180141492  movups  xmmword ptr [rsp+1D8h+var_168], xmm0
0x180141497  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18014149f  movdqu  [rsp+1D8h+var_158], xmm1
0x1801414a8  mov     word ptr [rsp+1D8h+var_168], r12w
0x1801414ae  test    ebx, ebx
0x1801414b0  jz      short loc_180141515
0x1801414b2  lea     r9, [rsp+1D8h+var_168]
0x1801414b7  mov     r8b, r13b
0x1801414ba  lea     rdx, [rsp+1D8h+var_128]
0x1801414c2  mov     rdi, [rsp+1D8h+var_1A8]
0x1801414c7  mov     rcx, rdi
0x1801414ca  call    ?GetCompressedContent@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::GetCompressedContent(std::unordered_map<std::wstring,std::wstring> const &,bool,std::wstring &)
0x1801414cf  mov     ebx, eax
0x1801414d1  test    eax, eax
0x1801414d3  jns     loc_18014195A
0x1801414d9  mov     rcx, [rsp+1D8h]; this
0x1801414e1  mov     r9d, eax; char *
0x1801414e4  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801414eb  mov     edx, 99h; void *
0x1801414f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801414f5  nop
0x1801414f6  lea     rcx, [rsp+1D8h+var_168]
0x1801414fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141500  nop
0x180141501  lea     rcx, [rsp+1D8h+var_128]
0x180141509  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18014150e  mov     eax, ebx
0x180141510  jmp     loc_180141CE6
0x180141515  mov     [rsp+1D8h+var_170], r12
0x18014151a  mov     [rsp+1D8h+string], r12
0x18014151f  mov     [rsp+1D8h+var_180], r12
0x180141524  mov     r9d, 1Ch; unsigned int
0x18014152a  lea     r8d, [r9+1]; unsigned int
0x18014152e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180141535  lea     rcx, [rsp+1D8h+var_198]; hstringHeader
0x18014153a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18014153f  lea     rdx, [rsp+1D8h+string]
0x180141544  mov     rcx, [rsp+1D8h+var_180]
0x180141549  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18014154e  mov     ebx, eax
0x180141550  test    eax, eax
0x180141552  jns     short loc_1801415A6
0x180141554  mov     rcx, [rsp+1D8h]; this
0x18014155c  mov     r9d, eax; char *
0x18014155f  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141566  mov     edx, 0A0h; void *
0x18014156b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141570  nop
0x180141571  lea     rcx, [rsp+1D8h+string]
0x180141576  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014157b  nop
0x18014157c  lea     rcx, [rsp+1D8h+var_170]; this
0x180141581  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180141586  nop
0x180141587  lea     rcx, [rsp+1D8h+var_168]
0x18014158c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141591  nop
0x180141592  lea     rcx, [rsp+1D8h+var_128]
0x18014159a  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18014159f  mov     eax, ebx
0x1801415a1  jmp     loc_180141CE6
0x1801415a6  lea     r9, [rsp+1D8h+string]
0x1801415ab  mov     r8b, r13b
0x1801415ae  lea     rdx, [rsp+1D8h+var_128]
0x1801415b6  mov     rcx, [rsp+1D8h+var_1A8]
0x1801415bb  call    ?Serialize@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::Serialize(std::unordered_map<std::wstring,std::wstring> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1801415c0  mov     ebx, eax
0x1801415c2  test    eax, eax
  ... truncated ...
```
