# ModernDeployment::Autopilot::Core::DeviceLinkExport::GetSerializedOutput(ModernDeployment::Autopilot::Core::DeviceLinkInfo &,ModernDeployment::Autopilot::Core::DeviceLinkFormatFlags const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18013d01c`
- end: `0x18013dc64`
- name: `?GetSerializedOutput@DeviceLinkExport@Core@Autopilot@ModernDeployment@@SAJAEAVDeviceLinkInfo@234@AEBW4DeviceLinkFormatFlags@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180126134`
- `0x18012ef90`
- `0x18013ca74`
- `0x1801aa614`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x1800801fc`
- `0x180081280`
- `0x1800812d4`
- `0x1800814a8`
- `0x1800839bc`
- `0x1800853a0`
- `0x1800887b8`
- `0x1800889a0`
- `0x180089b58`
- `0x18008a014`
- `0x18008c244`
- `0x18008f068`
- `0x1800951d0`
- `0x1800a0084`
- `0x18012e54c`
- `0x180132fb8`
- `0x180133408`
- `0x180134a00`
- `0x180134e6c`
- `0x18013c8d0`
- `0x18013d01c`
- `0x18013eb64`
- `0x180140dc4`
- `0x1801412c0`
- `0x1801425b0`
- `0x180143138`
- `0x1801437d4`
- `0x18014388c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013d3a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013d5dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013d3a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013d5dc`

## string_xrefs

- `0x18013d27b`: `Windows.Data.Json.JsonObject`
- `0x18013d484`: `Windows.Data.Json.JsonObject`
- `0x18013d075`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d0bc`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d0f4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d131`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d166`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d1ac`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d22a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d2b2`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d30e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d364`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d43a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d4b5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d527`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d58e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d63d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d718`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d7c6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d94b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013d9fa`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013dabb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`
- `0x18013db81`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkexport.cpp`

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
      v38 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::UnicodeToUtf8((__int64)&hstringHeader, (__int64)&v72);
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
0x18013d01c  mov     [rsp+arg_8], rbx
0x18013d021  mov     [rsp+arg_18], rsi
0x18013d026  push    rdi
0x18013d027  push    r12
0x18013d029  push    r13
0x18013d02b  push    r14
0x18013d02d  push    r15
0x18013d02f  sub     rsp, 1B0h
0x18013d036  mov     rax, cs:__security_cookie
0x18013d03d  xor     rax, rsp
0x18013d040  mov     [rsp+1D8h+var_38], rax
0x18013d048  mov     [rsp+1D8h+var_1A0], r8
0x18013d04d  mov     rbx, rdx
0x18013d050  mov     [rsp+1D8h+var_1A8], rcx
0x18013d055  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013d05c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013d061  test    al, al
0x18013d063  jnz     short loc_18013D08D
0x18013d065  mov     rcx, [rsp+1D8h]; this
0x18013d06d  mov     ebx, 80004001h
0x18013d072  mov     r9d, ebx; char *
0x18013d075  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d07c  mov     edx, 55h ; 'U'; void *
0x18013d081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d086  mov     eax, ebx
0x18013d088  jmp     loc_18013DC36
0x18013d08d  mov     ebx, [rbx]
0x18013d08f  bt      ebx, 1
0x18013d093  setb    r13b
0x18013d097  mov     cl, bl
0x18013d099  and     cl, 1
0x18013d09c  bt      ebx, 1
0x18013d0a0  jnb     short loc_18013D0A8
0x18013d0a2  test    cl, cl
0x18013d0a4  jnz     short loc_18013D0AC
0x18013d0a6  jmp     short loc_18013D0D4
0x18013d0a8  test    cl, cl
0x18013d0aa  jnz     short loc_18013D0D4
0x18013d0ac  mov     rcx, [rsp+1D8h]; this
0x18013d0b4  mov     ebx, 80070057h
0x18013d0b9  mov     r9d, ebx; char *
0x18013d0bc  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d0c3  mov     edx, 62h ; 'b'; void *
0x18013d0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d0cd  mov     eax, ebx
0x18013d0cf  jmp     loc_18013DC36
0x18013d0d4  mov     esi, ebx
0x18013d0d6  mov     edi, ebx
0x18013d0d8  and     edi, 40h
0x18013d0db  and     esi, 20h
0x18013d0de  jz      short loc_18013D10C
0x18013d0e0  test    edi, edi
0x18013d0e2  jz      short loc_18013D10C
0x18013d0e4  mov     rcx, [rsp+1D8h]; this
0x18013d0ec  mov     ebx, 80070057h
0x18013d0f1  mov     r9d, ebx; char *
0x18013d0f4  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d0fb  mov     edx, 68h ; 'h'; void *
0x18013d100  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d105  mov     eax, ebx
0x18013d107  jmp     loc_18013DC36
0x18013d10c  mov     r14d, ebx
0x18013d10f  mov     r15d, ebx
0x18013d112  and     r15d, 10h
0x18013d116  and     r14d, 8
0x18013d11a  jz      short loc_18013D149
0x18013d11c  test    r15d, r15d
0x18013d11f  jz      short loc_18013D14E
0x18013d121  mov     rcx, [rsp+1D8h]; this
0x18013d129  mov     ebx, 80070057h
0x18013d12e  mov     r9d, ebx; char *
0x18013d131  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d138  mov     edx, 6Eh ; 'n'; void *
0x18013d13d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d142  mov     eax, ebx
0x18013d144  jmp     loc_18013DC36
0x18013d149  test    r15d, r15d
0x18013d14c  jz      short loc_18013D17C
0x18013d14e  test    esi, esi
0x18013d150  jnz     short loc_18013D17C
0x18013d152  test    edi, edi
0x18013d154  jnz     short loc_18013D17C
0x18013d156  mov     rcx, [rsp+1D8h]; this
0x18013d15e  mov     ebx, 80070057h
0x18013d163  mov     r9d, ebx; char *
0x18013d166  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d16d  lea     edx, [rsi+74h]; void *
0x18013d170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d175  mov     eax, ebx
0x18013d177  jmp     loc_18013DC36
0x18013d17c  lea     rcx, [rsp+1D8h+var_128]
0x18013d184  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x18013d189  nop
0x18013d18a  lea     rdx, [rsp+1D8h+var_128]
0x18013d192  mov     cl, r13b
0x18013d195  call    ?GetJsonSerializationFieldNames@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJ_NAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetJsonSerializationFieldNames(bool,std::unordered_map<std::wstring,std::wstring> &)
0x18013d19a  mov     r12d, eax
0x18013d19d  test    eax, eax
0x18013d19f  jns     short loc_18013D1D3
0x18013d1a1  mov     rcx, [rsp+1D8h]; this
0x18013d1a9  mov     r9d, eax; char *
0x18013d1ac  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d1b3  mov     edx, 79h ; 'y'; void *
0x18013d1b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d1bd  nop
0x18013d1be  lea     rcx, [rsp+1D8h+var_128]
0x18013d1c6  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d1cb  mov     eax, r12d
0x18013d1ce  jmp     loc_18013DC36
0x18013d1d3  and     ebx, 4
0x18013d1d6  xor     r12d, r12d
0x18013d1d9  test    r14d, r14d
0x18013d1dc  jnz     loc_18013D3E5
0x18013d1e2  test    r15d, r15d
0x18013d1e5  jnz     loc_18013D3E5
0x18013d1eb  test    esi, esi
0x18013d1ed  jnz     loc_18013D3E5
0x18013d1f3  test    edi, edi
0x18013d1f5  jnz     loc_18013D3E5
0x18013d1fb  test    ebx, ebx
0x18013d1fd  jz      short loc_18013D264
0x18013d1ff  mov     r9, [rsp+1D8h+var_1A0]
0x18013d204  mov     r8b, r13b
0x18013d207  lea     rdx, [rsp+1D8h+var_128]
0x18013d20f  mov     rcx, [rsp+1D8h+var_1A8]
0x18013d214  call    ?GetCompressedContent@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::GetCompressedContent(std::unordered_map<std::wstring,std::wstring> const &,bool,std::wstring &)
0x18013d219  mov     ebx, eax
0x18013d21b  test    eax, eax
0x18013d21d  jns     short loc_18013D250
0x18013d21f  mov     rcx, [rsp+1D8h]; this
0x18013d227  mov     r9d, eax; char *
0x18013d22a  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d231  mov     edx, 80h; void *
0x18013d236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d23b  nop
0x18013d23c  lea     rcx, [rsp+1D8h+var_128]
0x18013d244  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d249  mov     eax, ebx
0x18013d24b  jmp     loc_18013DC36
0x18013d250  lea     rcx, [rsp+1D8h+var_128]
0x18013d258  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d25d  xor     eax, eax
0x18013d25f  jmp     loc_18013DC36
0x18013d264  mov     [rsp+1D8h+var_170], r12
0x18013d269  mov     [rsp+1D8h+var_40], r12
0x18013d271  mov     r9d, 1Ch; unsigned int
0x18013d277  lea     r8d, [r9+1]; unsigned int
0x18013d27b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18013d282  lea     rcx, [rsp+1D8h+hstringHeader]; hstringHeader
0x18013d28a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18013d28f  lea     rdx, [rsp+1D8h+var_170]
0x18013d294  mov     rcx, [rsp+1D8h+var_40]
0x18013d29c  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18013d2a1  mov     ebx, eax
0x18013d2a3  test    eax, eax
0x18013d2a5  jns     short loc_18013D2E3
0x18013d2a7  mov     rcx, [rsp+1D8h]; this
0x18013d2af  mov     r9d, eax; char *
0x18013d2b2  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d2b9  mov     edx, 87h; void *
0x18013d2be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d2c3  nop
0x18013d2c4  lea     rcx, [rsp+1D8h+var_170]
0x18013d2c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d2ce  nop
0x18013d2cf  lea     rcx, [rsp+1D8h+var_128]
0x18013d2d7  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d2dc  mov     eax, ebx
0x18013d2de  jmp     loc_18013DC36
0x18013d2e3  lea     r9, [rsp+1D8h+var_170]
0x18013d2e8  mov     r8b, r13b
0x18013d2eb  lea     rdx, [rsp+1D8h+var_128]
0x18013d2f3  mov     rcx, [rsp+1D8h+var_1A8]
0x18013d2f8  call    ?Serialize@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::Serialize(std::unordered_map<std::wstring,std::wstring> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18013d2fd  mov     ebx, eax
0x18013d2ff  test    eax, eax
0x18013d301  jns     short loc_18013D33F
0x18013d303  mov     rcx, [rsp+1D8h]; this
0x18013d30b  mov     r9d, eax; char *
0x18013d30e  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d315  mov     edx, 89h; void *
0x18013d31a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d31f  nop
0x18013d320  lea     rcx, [rsp+1D8h+var_170]
0x18013d325  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d32a  nop
0x18013d32b  lea     rcx, [rsp+1D8h+var_128]
0x18013d333  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d338  mov     eax, ebx
0x18013d33a  jmp     loc_18013DC36
0x18013d33f  mov     [rsp+1D8h+string], r12
0x18013d344  lea     rdx, [rsp+1D8h+string]
0x18013d349  mov     rcx, [rsp+1D8h+var_170]
0x18013d34e  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18013d353  mov     ebx, eax
0x18013d355  test    eax, eax
0x18013d357  jns     short loc_18013D3A0
0x18013d359  mov     rcx, [rsp+1D8h]; this
0x18013d361  mov     r9d, eax; char *
0x18013d364  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d36b  mov     edx, 8Ch; void *
0x18013d370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d375  nop
0x18013d376  lea     rcx, [rsp+1D8h+string]; this
0x18013d37b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013d380  nop
0x18013d381  lea     rcx, [rsp+1D8h+var_170]
0x18013d386  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d38b  nop
0x18013d38c  lea     rcx, [rsp+1D8h+var_128]
0x18013d394  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d399  mov     eax, ebx
0x18013d39b  jmp     loc_18013DC36
0x18013d3a0  xor     edx, edx; length
0x18013d3a2  mov     rcx, [rsp+1D8h+string]; string
0x18013d3a7  call    cs:__imp_WindowsGetStringRawBuffer
0x18013d3ad  mov     rdx, rax
0x18013d3b0  mov     rcx, [rsp+1D8h+var_1A0]
0x18013d3b5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013d3ba  nop
0x18013d3bb  lea     rcx, [rsp+1D8h+string]; this
0x18013d3c0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013d3c5  nop
0x18013d3c6  lea     rcx, [rsp+1D8h+var_170]
0x18013d3cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d3d0  nop
0x18013d3d1  lea     rcx, [rsp+1D8h+var_128]
0x18013d3d9  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d3de  xor     eax, eax
0x18013d3e0  jmp     loc_18013DC36
0x18013d3e5  xorps   xmm0, xmm0
0x18013d3e8  movups  xmmword ptr [rsp+1D8h+var_168], xmm0
0x18013d3ed  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18013d3f5  movdqu  [rsp+1D8h+var_158], xmm1
0x18013d3fe  mov     word ptr [rsp+1D8h+var_168], r12w
0x18013d404  test    ebx, ebx
0x18013d406  jz      short loc_18013D46B
0x18013d408  lea     r9, [rsp+1D8h+var_168]
0x18013d40d  mov     r8b, r13b
0x18013d410  lea     rdx, [rsp+1D8h+var_128]
0x18013d418  mov     rdi, [rsp+1D8h+var_1A8]
0x18013d41d  mov     rcx, rdi
0x18013d420  call    ?GetCompressedContent@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::GetCompressedContent(std::unordered_map<std::wstring,std::wstring> const &,bool,std::wstring &)
0x18013d425  mov     ebx, eax
0x18013d427  test    eax, eax
0x18013d429  jns     loc_18013D8AA
0x18013d42f  mov     rcx, [rsp+1D8h]; this
0x18013d437  mov     r9d, eax; char *
0x18013d43a  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d441  mov     edx, 99h; void *
0x18013d446  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d44b  nop
0x18013d44c  lea     rcx, [rsp+1D8h+var_168]
0x18013d451  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d456  nop
0x18013d457  lea     rcx, [rsp+1D8h+var_128]
0x18013d45f  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d464  mov     eax, ebx
0x18013d466  jmp     loc_18013DC36
0x18013d46b  mov     [rsp+1D8h+var_170], r12
0x18013d470  mov     [rsp+1D8h+string], r12
0x18013d475  mov     [rsp+1D8h+var_180], r12
0x18013d47a  mov     r9d, 1Ch; unsigned int
0x18013d480  lea     r8d, [r9+1]; unsigned int
0x18013d484  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18013d48b  lea     rcx, [rsp+1D8h+var_198]; hstringHeader
0x18013d490  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18013d495  lea     rdx, [rsp+1D8h+string]
0x18013d49a  mov     rcx, [rsp+1D8h+var_180]
0x18013d49f  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18013d4a4  mov     ebx, eax
0x18013d4a6  test    eax, eax
0x18013d4a8  jns     short loc_18013D4FC
0x18013d4aa  mov     rcx, [rsp+1D8h]; this
0x18013d4b2  mov     r9d, eax; char *
0x18013d4b5  lea     r8, aOnecoreuapAdmi_68; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d4bc  mov     edx, 0A0h; void *
0x18013d4c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d4c6  nop
0x18013d4c7  lea     rcx, [rsp+1D8h+string]
0x18013d4cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013d4d1  nop
0x18013d4d2  lea     rcx, [rsp+1D8h+var_170]; this
0x18013d4d7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013d4dc  nop
0x18013d4dd  lea     rcx, [rsp+1D8h+var_168]
0x18013d4e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d4e7  nop
0x18013d4e8  lea     rcx, [rsp+1D8h+var_128]
0x18013d4f0  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18013d4f5  mov     eax, ebx
0x18013d4f7  jmp     loc_18013DC36
0x18013d4fc  lea     r9, [rsp+1D8h+string]
0x18013d501  mov     r8b, r13b
0x18013d504  lea     rdx, [rsp+1D8h+var_128]
0x18013d50c  mov     rcx, [rsp+1D8h+var_1A8]
0x18013d511  call    ?Serialize@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::Serialize(std::unordered_map<std::wstring,std::wstring> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18013d516  mov     ebx, eax
0x18013d518  test    eax, eax
0x18013d51a  jns     short loc_18013D56E
  ... truncated ...
```
