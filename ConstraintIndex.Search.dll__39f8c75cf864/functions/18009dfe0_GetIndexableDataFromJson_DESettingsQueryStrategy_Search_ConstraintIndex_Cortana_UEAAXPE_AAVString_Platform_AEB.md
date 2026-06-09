# ?GetIndexableDataFromJson@DESettingsQueryStrategy@Search@ConstraintIndex@Cortana@@UEAAXPE$AAVString@Platform@@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@std@@@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@8@AEAP$01E$AAV?$Array@E$00@6@3@Z

- ea: `0x18009dfe0`
- end: `0x18009e7f5`
- name: `?GetIndexableDataFromJson@DESettingsQueryStrategy@Search@ConstraintIndex@Cortana@@UEAAXPE$AAVString@Platform@@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@std@@@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@8@AEAP$01E$AAV?$Array@E$00@6@3@Z`
- size: `2069`
- prototype: ``
- caller_count: `0`
- callee_count: `53`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18000616e`
- `0x18000617a`
- `0x18000619e`
- `0x1800062a0`
- `0x180009e14`
- `0x180009fa0`
- `0x18000a218`
- `0x18000c860`
- `0x18000cd60`
- `0x18000cdb0`
- `0x18000cdf0`
- `0x180011728`
- `0x18003a4a0`
- `0x18003a660`
- `0x18003c088`
- `0x18003e940`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff8c`
- `0x18006cec0`
- `0x1800754d8`
- `0x1800755c0`
- `0x18007e6b8`
- `0x1800801f0`
- `0x180083160`
- `0x180092490`
- `0x180092e54`
- `0x1800999d0`
- `0x18009a954`
- `0x18009b798`
- `0x18009b864`
- `0x18009bb04`
- `0x18009bcdc`
- `0x18009bef0`
- `0x18009bf2c`
- `0x18009bf9c`
- `0x18009c93c`
- `0x18009ca1c`
- `0x18009ccc4`
- `0x18009d2dc`
- `0x18009d904`
- `0x18009d98c`
- `0x18009d9e4`
- `0x18009da18`
- `0x18009dfe0`
- `0x18009e998`
- `0x18009f284`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009e3a8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009e3a8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18009e2c5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18009e2c5`

## string_xrefs

- `0x18009e6eb`: `shellcommon\shell\cortana\constraintindex\src\Search\DESettingsQueryStrategy.cpp`
- `0x18009e70b`: `shellcommon\shell\cortana\constraintindex\src\Search\DESettingsQueryStrategy.cpp`
- `0x18009e30b`: `System.Comment`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
void __fastcall Cortana::ConstraintIndex::Search::DESettingsQueryStrategy::GetIndexableDataFromJson(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v9; // r13
  __int64 v10; // rbx
  __int64 v11; // rbx
  int v12; // esi
  __int64 i; // r12
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 Object; // rbx
  __int64 v17; // r14
  HRESULT v18; // eax
  __int64 Tokens; // rdi
  HSTRING JsonPropertyAsString; // rbx
  HSTRING v21; // r13
  const wchar_t *StringRawBuffer_0; // rax
  unsigned __int64 v23; // rdx
  int v24; // eax
  HRESULT v25; // eax
  __int64 v26; // rdi
  HSTRING v27; // rbx
  HSTRING v28; // r13
  const WCHAR *v29; // rax
  const char *v30; // r9
  __int64 v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rdi
  __int64 v34; // rcx
  unsigned int v35; // edi
  __int64 v36; // r14
  HRESULT v37; // eax
  char HasKey; // bl
  unsigned int v39; // r14d
  HRESULT v40; // eax
  __int64 v41; // rdi
  HSTRING v42; // rbx
  PCWSTR v43; // rax
  __int64 v44; // rax
  const WCHAR *v45; // rax
  int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+40h] [rbp-C0h]
  HSTRING v49; // [rsp+48h] [rbp-B8h]
  __int64 DataAsByteArray; // [rsp+48h] [rbp-B8h]
  __int64 v51; // [rsp+48h] [rbp-B8h]
  __int64 v52; // [rsp+50h] [rbp-B0h]
  __int64 v53; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+60h] [rbp-A0h]
  __int64 v55; // [rsp+68h] [rbp-98h]
  HSTRING v56; // [rsp+70h] [rbp-90h]
  HSTRING v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER v60; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v61[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-38h]
  __int64 v63; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+D8h] [rbp-28h]
  HSTRING v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  HSTRING v67; // [rsp+F0h] [rbp-10h]
  HSTRING v68; // [rsp+F8h] [rbp-8h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  __int64 v71; // [rsp+110h] [rbp+10h] BYREF
  HSTRING_HEADER v72; // [rsp+120h] [rbp+20h] BYREF
  HSTRING v73; // [rsp+138h] [rbp+38h]
  _BYTE v74[24]; // [rsp+140h] [rbp+40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+158h] [rbp+58h] BYREF
  HSTRING_HEADER v76; // [rsp+170h] [rbp+70h] BYREF
  HSTRING string; // [rsp+188h] [rbp+88h] BYREF
  __int64 v78; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v79[16]; // [rsp+198h] [rbp+98h] BYREF
  UINT32 length[4]; // [rsp+1A8h] [rbp+A8h]
  _BYTE v81[32]; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v82[3]; // [rsp+1D8h] [rbp+D8h] BYREF
  _BYTE v83[120]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v84[16]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v85[24]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v86[120]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v87[16]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v88[24]; // [rsp+318h] [rbp+218h] BYREF
  _QWORD v89[42]; // [rsp+330h] [rbp+230h] BYREF
  CHAR v90[256]; // [rsp+480h] [rbp+380h] BYREF
  CHAR MultiByteStr[272]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR pszPath[264]; // [rsp+690h] [rbp+590h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F8h] [rbp+7F8h]

  v55 = a1;
  v9 = a5;
  v59 = a5;
  v58 = a6;
  LODWORD(string) = 0;
  memset_0(v89, 0, sizeof(v89));
  wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v89);
  v89[0] = &ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::`vftable';
  ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::StartActivity((ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *)v89);
  v78 = 0;
  memset_0(v86, 0, 0xA0u);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v86);
  std::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>(v87);
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v88);
  if ( (unsigned __int8)Windows::Data::Json::JsonArray::TryParse(a2, &v78) )
  {
    memset_0(v83, 0, 0xA0u);
    v10 = std::vector<std::string>::vector<std::string>(v74, a4);
    std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v83);
    std::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>(v84);
    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v85);
    Cortana::ConstraintIndex::Search::DEInputFileWriter::MapSynonymData(v83, v10);
    std::vector<std::string>::_Tidy(v10);
    v11 = __abi_winrt_cast_to(
            0,
            v78,
            _uuidof__AU__IVector_PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
    Platform::Collections::VectorViewIterator<Platform::String __gc *>::VectorViewIterator<Platform::String __gc *>(
      &v53,
      v11);
    v12 = 4;
    __abi_winrt_ptr_dtor(v11);
    v47 = __abi_winrt_cast_to(
            0,
            v78,
            _uuidof__AU__IVector_PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
    Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint __gc *>(v82, v47);
    __abi_winrt_ptr_dtor(v47);
    for ( i = v54; i != v82[1]; v54 = i )
    {
      v14 = Platform::Collections::VectorIterator<Windows::Data::Json::IJsonValue __gc *>::operator*(&v53, &v71);
      v15 = Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::operator*(v14);
      v62 = v15;
      v48 = __abi_winrt_ptr_ctor(v15);
      __abi_winrt_ptr_dtor(v15);
      __abi_winrt_ptr_dtor(v71);
      Object = Windows::Data::Json::IJsonValue::GetObject(v48);
      v63 = Object;
      v17 = __abi_winrt_ptr_ctor(Object);
      v52 = v17;
      __abi_winrt_ptr_dtor(Object);
      string = 0;
      v18 = WindowsCreateStringReference_0(L"System.ParsingName", 0x12u, &hstringHeader, &string);
      if ( v18 < 0 )
        __abi_WinRTraiseException(v18);
      Tokens = Windows::Data::Text::IWordsSegmenter::GetTokens(v17, string);
      v64 = Tokens;
      JsonPropertyAsString = (HSTRING)Cortana::Common::JsonPropertyStoreHelper::GetJsonPropertyAsString(Tokens);
      v65 = JsonPropertyAsString;
      v21 = (HSTRING)__abi_winrt_ptrto_string_ctor(JsonPropertyAsString);
      v57 = v21;
      WindowsDeleteString_0(JsonPropertyAsString);
      __abi_winrt_ptr_dtor(Tokens);
      StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v21, 0);
      v24 = StringCchCopyW(pszPath, v23, StringRawBuffer_0);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\DESettingsQueryStrategy.cpp",
          (const char *)(unsigned int)v24,
          lpMultiByteStr);
      PathRemoveExtensionW(pszPath);
      memset(v81, 0, sizeof(v81));
      Platform::StringReference::StringReference((HSTRING_HEADER *)v81, pszPath);
      string = 0;
      v25 = WindowsCreateStringReference_0(L"System.Comment", 0xEu, &v76, &string);
      if ( v25 < 0 )
        __abi_WinRTraiseException(v25);
      v26 = Windows::Data::Text::IWordsSegmenter::GetTokens(v17, string);
      v66 = v26;
      v27 = (HSTRING)Cortana::Common::JsonPropertyStoreHelper::GetJsonPropertyAsString(v26);
      v67 = v27;
      v28 = (HSTRING)__abi_winrt_ptrto_string_ctor(v27);
      v68 = v28;
      WindowsDeleteString_0(v27);
      __abi_winrt_ptr_dtor(v26);
      v29 = WindowsGetStringRawBuffer_0(*(HSTRING *)&v81[24], 0);
      if ( !WideCharToMultiByte(0xFDE9u, 0, v29, -1, MultiByteStr, 260, 0, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x71,
          (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\DESettingsQueryStrategy.cpp",
          v30);
      if ( a3[1]
        && (std::string::string(v61, MultiByteStr),
            v12 |= 1u,
            LODWORD(string) = v12,
            std::_Tree<std::_Tmap_traits<std::string,std::pair<unsigned int,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<unsigned int,unsigned __int64>>>,0>>::_Find_lower_bound<std::string>(
              a3,
              &v60,
              v61),
            v31 = *(_QWORD *)&v60.Reserved.Reserved2[16],
            (unsigned __int8)std::_Tree<std::_Tmap_traits<std::string,std::pair<unsigned int,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<unsigned int,unsigned __int64>>>,0>>::_Lower_bound_duplicate<std::string>(
                               v32,
                               *(_QWORD *)&v60.Reserved.Reserved2[16],
                               v61))
        && v31 != *a3 )
      {
        std::string::string(v79, MultiByteStr);
        v12 |= 2u;
        LODWORD(string) = v12;
        std::_Tree<std::_Tmap_traits<std::string,std::pair<unsigned int,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<unsigned int,unsigned __int64>>>,0>>::_Find_lower_bound<std::string>(
          a3,
          &v60,
          v79);
        v33 = *(_QWORD *)&v60.Reserved.Reserved2[16];
        if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::string,std::pair<unsigned int,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<unsigned int,unsigned __int64>>>,0>>::_Lower_bound_duplicate<std::string>(
                                 v34,
                                 *(_QWORD *)&v60.Reserved.Reserved2[16],
                                 v79) )
          std::_Xout_of_range("invalid map<K, T> key");
        v35 = *(_DWORD *)(v33 + 64);
      }
      else
      {
        v35 = 64000;
      }
      if ( (v12 & 2) != 0 )
      {
        v12 &= ~2u;
        std::string::_Tidy_deallocate(v79);
      }
      if ( (v12 & 1) != 0 )
      {
        v12 &= ~1u;
        std::string::_Tidy_deallocate(v61);
      }
      lpMultiByteStr = (int)v28;
      Cortana::ConstraintIndex::Search::DEInputFileWriter::AddItem(v86, *(_QWORD *)(v55 + 24), v35, *(_QWORD *)&v81[24]);
      Cortana::ConstraintIndex::Search::DEInputFileWriter::AddSynonymItemWithWordBreaking(v83, v35, v28);
      v36 = __abi_winrt_cast_to(
              0,
              v17,
              _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
      v69 = v36;
      string = 0;
      v37 = WindowsCreateStringReference_0(L"System.HighKeywords", 0x13u, &v60, &string);
      if ( v37 < 0 )
        __abi_WinRTraiseException(v37);
      HasKey = Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::HasKey(
                 v36,
                 string);
      __abi_winrt_ptr_dtor(v36);
      if ( HasKey )
      {
        v39 = v35 + 5000;
        if ( (int)(v35 + 5000) > 64000 )
          v39 = 64000;
        string = 0;
        v40 = WindowsCreateStringReference_0(L"System.HighKeywords", 0x13u, &v60, &string);
        if ( v40 < 0 )
          __abi_WinRTraiseException(v40);
        v41 = Windows::Data::Text::IWordsSegmenter::GetTokens(v52, string);
        v70 = v41;
        v49 = (HSTRING)Cortana::Common::JsonPropertyStoreHelper::GetJsonPropertyAsString(v41);
        v56 = (HSTRING)__abi_winrt_ptrto_string_ctor(v49);
        WindowsDeleteString_0(v49);
        __abi_winrt_ptr_dtor(v41);
        memset_0(v90, 0, 0xF8u);
        v42 = v56;
        v43 = WindowsGetStringRawBuffer_0(v56, 0);
        std::wstring::wstring(v61, v43);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
          v90,
          v61);
        std::wstring::_Tidy_deallocate(v61);
        std::wstring::wstring(v79);
        while ( 1 )
        {
          v44 = std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v90, v79);
          if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v44 + 4LL) + v44 + 16) & 6) != 0 )
            break;
          v45 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v79);
          Platform::StringReference::Init(&v72, v45, length[0]);
          Cortana::ConstraintIndex::Search::DEInputFileWriter::AddSynonymItem(v83, v39, v28, v73);
          WindowsDeleteString_0(v73);
        }
        std::wstring::_Tidy_deallocate(v79);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v90);
        WindowsDeleteString_0(v42);
      }
      WindowsDeleteString_0(v28);
      WindowsDeleteString_0(*(HSTRING *)&v81[24]);
      WindowsDeleteString_0(v57);
      __abi_winrt_ptr_dtor(v52);
      __abi_winrt_ptr_dtor(v48);
      ++i;
    }
    __abi_winrt_ptr_dtor(v82[0]);
    __abi_winrt_ptr_dtor(v53);
    DataAsByteArray = Cortana::ConstraintIndex::Search::DEInputFileWriter::GetDataAsByteArray(v83);
    __abi_winrt_ptrto_array_assign<unsigned char,1>(v58, DataAsByteArray);
    __abi_winrt_ptr_dtor(DataAsByteArray);
    Cortana::ConstraintIndex::Search::DEInputFileWriter::~DEInputFileWriter((Cortana::ConstraintIndex::Search::DEInputFileWriter *)v83);
    v9 = v59;
  }
  v51 = Cortana::ConstraintIndex::Search::DEInputFileWriter::GetDataAsByteArray(v86);
  __abi_winrt_ptrto_array_assign<unsigned char,1>(v9, v51);
  __abi_winrt_ptr_dtor(v51);
  wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v89);
  Cortana::ConstraintIndex::Search::DEInputFileWriter::~DEInputFileWriter((Cortana::ConstraintIndex::Search::DEInputFileWriter *)v86);
  __abi_winrt_ptr_dtor(v78);
  ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::~DESettingsQueryStrategy_GetIndexableDataFromJson((ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *)v89);
}

```

## disassembly

```asm
0x18009dfe0  push    rbp
0x18009dfe2  push    rbx
0x18009dfe3  push    rsi
0x18009dfe4  push    rdi
0x18009dfe5  push    r12
0x18009dfe7  push    r13
0x18009dfe9  push    r14
0x18009dfeb  push    r15
0x18009dfed  lea     rbp, [rsp-7B8h]
0x18009dff5  sub     rsp, 8B8h
0x18009dffc  mov     rax, cs:__security_cookie
0x18009e003  xor     rax, rsp
0x18009e006  mov     [rbp+7F0h+var_50], rax
0x18009e00d  mov     rdi, r9
0x18009e010  mov     r15, r8
0x18009e013  mov     rbx, rdx
0x18009e016  mov     [rsp+8F0h+var_888], rcx
0x18009e01b  mov     r13, [rbp+7F0h+arg_20]
0x18009e022  mov     [rbp+7F0h+var_868], r13
0x18009e026  mov     r14, [rbp+7F0h+arg_28]
0x18009e02d  mov     [rbp+7F0h+var_870], r14
0x18009e031  mov     dword ptr [rbp+7F0h+string], 0
0x18009e03b  xor     edx, edx; Val
0x18009e03d  mov     r8d, 150h; Size
0x18009e043  lea     rcx, [rbp+7F0h+var_5C0]; void *
0x18009e04a  call    memset_0
0x18009e04f  lea     rcx, [rbp+7F0h+var_5C0]; struct wil::details::IFailureCallback *
0x18009e056  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009e05b  lea     rax, ??_7DESettingsQueryStrategy_GetIndexableDataFromJson@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::`vftable'
0x18009e062  mov     [rbp+7F0h+var_5C0], rax
0x18009e069  lea     rcx, [rbp+7F0h+var_5C0]; this
0x18009e070  call    ?StartActivity@DESettingsQueryStrategy_GetIndexableDataFromJson@ConstraintIndexTelemetry@@QEAAXXZ; ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::StartActivity(void)
0x18009e075  nop
0x18009e076  mov     [rbp+7F0h+var_760], 0
0x18009e081  mov     esi, 0A0h
0x18009e086  mov     r8d, esi; Size
0x18009e089  xor     edx, edx; Val
0x18009e08b  lea     rcx, [rbp+7F0h+var_660]; void *
0x18009e092  call    memset_0
0x18009e097  lea     rcx, [rbp+7F0h+var_660]
0x18009e09e  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(void)
0x18009e0a3  nop
0x18009e0a4  lea     rcx, [rbp+7F0h+var_5E8]
0x18009e0ab  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@UCaseInsensitiveLess@Search@ConstraintIndex@Cortana@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>(void)
0x18009e0b0  lea     rcx, [rbp+7F0h+var_5D8]
0x18009e0b7  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18009e0bc  nop
0x18009e0bd  lea     rdx, [rbp+7F0h+var_760]
0x18009e0c4  mov     rcx, rbx
0x18009e0c7  call    ?TryParse@JsonArray@Json@Data@Windows@@SA_NPE$AAVString@Platform@@PEAPE$AAV1234@@Z; Windows::Data::Json::JsonArray::TryParse(Platform::String *,Windows::Data::Json::JsonArray * *)
0x18009e0cc  test    al, al
0x18009e0ce  jz      loc_18009E777
0x18009e0d4  mov     r8d, esi; Size
0x18009e0d7  xor     edx, edx; Val
0x18009e0d9  lea     rcx, [rbp+7F0h+var_700]; void *
0x18009e0e0  call    memset_0
0x18009e0e5  mov     rdx, rdi
0x18009e0e8  lea     rcx, [rbp+7F0h+var_7B0]
0x18009e0ec  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::string>::vector<std::string>(std::vector<std::string> const &)
0x18009e0f1  mov     rbx, rax
0x18009e0f4  mov     [rsp+8F0h+var_8B0], rax
0x18009e0f9  lea     rcx, [rbp+7F0h+var_700]
0x18009e100  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(void)
0x18009e105  nop
0x18009e106  lea     rcx, [rbp+7F0h+var_688]
0x18009e10d  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@UCaseInsensitiveLess@Search@ConstraintIndex@Cortana@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>::map<std::string,std::vector<std::string>,Cortana::ConstraintIndex::Search::CaseInsensitiveLess,std::allocator<std::pair<std::string const,std::vector<std::string>>>>(void)
0x18009e112  nop
0x18009e113  lea     rcx, [rbp+7F0h+var_678]
0x18009e11a  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18009e11f  nop
0x18009e120  mov     rdx, rbx
0x18009e123  lea     rcx, [rbp+7F0h+var_700]
0x18009e12a  call    ?MapSynonymData@DEInputFileWriter@Search@ConstraintIndex@Cortana@@AEAAXAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; Cortana::ConstraintIndex::Search::DEInputFileWriter::MapSynonymData(std::vector<std::string> &)
0x18009e12f  nop
0x18009e130  mov     rcx, rbx
0x18009e133  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18009e138  nop
0x18009e139  lea     r8, __uuidof_?AU?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x18009e140  mov     rdx, [rbp+7F0h+var_760]
0x18009e147  xor     ecx, ecx
0x18009e149  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009e14e  mov     rbx, rax
0x18009e151  mov     [rsp+8F0h+var_8B0], rax
0x18009e156  mov     rdx, rax
0x18009e159  lea     rcx, [rsp+8F0h+var_898]
0x18009e15e  call    ??0?$VectorViewIterator@PE$AAVString@Platform@@@Collections@Platform@@QEAA@PE$AAU?$IVectorView@PE$AAVString@Platform@@@1Foundation@Windows@@@Z; Platform::Collections::VectorViewIterator<Platform::String *>::VectorViewIterator<Platform::String *>(Windows::Foundation::Collections::IVectorView<Platform::String *> *)
0x18009e163  mov     esi, 4
0x18009e168  mov     rcx, rbx
0x18009e16b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e170  lea     r8, __uuidof_?AU?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x18009e177  mov     rdx, [rbp+7F0h+var_760]
0x18009e17e  xor     ecx, ecx
0x18009e180  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009e185  mov     rbx, rax
0x18009e188  mov     [rsp+8F0h+var_8B0], rax
0x18009e18d  mov     rdx, rax
0x18009e190  lea     rcx, [rbp+7F0h+var_718]
0x18009e197  call    ??$end@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@YA?AV?$VectorViewIterator@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@0Platform@@PE$AAU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@012@@Z; Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint *>(Windows::Foundation::Collections::IVectorView<WindowsUdk::System::Profile::SystemSettingEntryPoint *> *)
0x18009e19c  nop
0x18009e19d  mov     rcx, rbx
0x18009e1a0  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e1a5  mov     r12, [rsp+8F0h+var_890]
0x18009e1aa  cmp     r12, [rbp+7F0h+var_710]
0x18009e1b1  jz      loc_18009E725
0x18009e1b7  lea     rdx, [rbp+7F0h+var_7E0]
0x18009e1bb  lea     rcx, [rsp+8F0h+var_898]
0x18009e1c0  call    ??D?$VectorIterator@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Platform@@QEBA?AV?$VectorProxy@PE$AAUIJsonValue@Json@Data@Windows@@@Details@12@XZ; Platform::Collections::VectorIterator<Windows::Data::Json::IJsonValue *>::operator*(void)
0x18009e1c5  nop
0x18009e1c6  mov     rcx, rax
0x18009e1c9  call    ??D?$VectorViewIterator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Platform@@QEBAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@XZ; Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem *>::operator*(void)
0x18009e1ce  mov     rbx, rax
0x18009e1d1  mov     [rbp+7F0h+var_828], rax
0x18009e1d5  mov     rcx, rax
0x18009e1d8  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009e1dd  mov     rdi, rax
0x18009e1e0  mov     [rsp+8F0h+var_8B0], rax
0x18009e1e5  mov     rcx, rbx
0x18009e1e8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e1ed  nop
0x18009e1ee  mov     rcx, [rbp+7F0h+var_7E0]
0x18009e1f2  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e1f7  nop
0x18009e1f8  mov     rcx, rdi
0x18009e1fb  call    ?GetObject@IJsonValue@Json@Data@Windows@@UE$AAAPE$AAVJsonObject@234@XZ; Windows::Data::Json::IJsonValue::GetObject(void)
0x18009e200  mov     rbx, rax
0x18009e203  mov     [rbp+7F0h+var_820], rax
0x18009e207  mov     rcx, rax
0x18009e20a  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009e20f  mov     r14, rax
0x18009e212  mov     [rsp+8F0h+var_8A0], rax
0x18009e217  mov     rcx, rbx
0x18009e21a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e21f  nop
0x18009e220  mov     [rbp+7F0h+string], 0
0x18009e22b  lea     r9, [rbp+7F0h+string]; string
0x18009e232  lea     r8, [rbp+7F0h+hstringHeader]; hstringHeader
0x18009e236  mov     edx, 12h; length
0x18009e23b  lea     rcx, aSystemParsingn; "System.ParsingName"
0x18009e242  call    WindowsCreateStringReference_0
0x18009e247  test    eax, eax
0x18009e249  js      loc_18009E71D
0x18009e24f  mov     rdx, [rbp+7F0h+string]
0x18009e256  mov     rcx, r14
0x18009e259  call    ?GetTokens@IWordsSegmenter@Text@Data@Windows@@UE$AAAPE$AAU?$IVectorView@PE$AAVWordSegment@Text@Data@Windows@@@Collections@Foundation@4@PE$AAVString@Platform@@@Z; Windows::Data::Text::IWordsSegmenter::GetTokens(Platform::String *)
0x18009e25e  mov     rdi, rax
0x18009e261  mov     [rbp+7F0h+var_818], rax
0x18009e265  mov     rcx, rax
0x18009e268  call    ?GetJsonPropertyAsString@JsonPropertyStoreHelper@Common@Cortana@@SAPE$AAVString@Platform@@PE$AAVJsonObject@Json@Data@Windows@@@Z; Cortana::Common::JsonPropertyStoreHelper::GetJsonPropertyAsString(Windows::Data::Json::JsonObject *)
0x18009e26d  mov     rbx, rax
0x18009e270  mov     [rbp+7F0h+var_810], rax
0x18009e274  mov     rcx, rax
0x18009e277  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009e27c  mov     r13, rax
0x18009e27f  mov     [rsp+8F0h+var_878], rax
0x18009e284  mov     rcx, rbx; string
0x18009e287  call    WindowsDeleteString_0
0x18009e28c  nop
0x18009e28d  mov     rcx, rdi
0x18009e290  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e295  nop
0x18009e296  xor     edx, edx; length
0x18009e298  mov     rcx, r13; string
0x18009e29b  call    WindowsGetStringRawBuffer_0
0x18009e2a0  mov     r8, rax; wchar_t *
0x18009e2a3  lea     rcx, [rbp+7F0h+pszPath]; wchar_t *
0x18009e2aa  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18009e2af  mov     rcx, [rbp+7F8h]; this
0x18009e2b6  test    eax, eax
0x18009e2b8  js      loc_18009E708
0x18009e2be  lea     rcx, [rbp+7F0h+pszPath]; pszPath
0x18009e2c5  call    cs:__imp_PathRemoveExtensionW
0x18009e2cb  xorps   xmm0, xmm0
0x18009e2ce  movups  xmmword ptr [rbp+7F0h+var_738], xmm0
0x18009e2d5  movups  xmmword ptr [rbp+7F0h+var_738+10h], xmm0
0x18009e2dc  lea     rdx, [rbp+7F0h+pszPath]; sourceString
0x18009e2e3  lea     rcx, [rbp+7F0h+var_738]; hstringHeader
0x18009e2ea  call    ??0StringReference@Platform@@QEAA@PEB_W@Z; Platform::StringReference::StringReference(wchar_t const *)
0x18009e2ef  nop
0x18009e2f0  mov     [rbp+7F0h+string], 0
0x18009e2fb  lea     r9, [rbp+7F0h+string]; string
0x18009e302  lea     r8, [rbp+7F0h+var_780]; hstringHeader
0x18009e306  mov     edx, 0Eh; length
0x18009e30b  lea     rcx, aSystemComment; "System.Comment"
0x18009e312  call    WindowsCreateStringReference_0
0x18009e317  test    eax, eax
0x18009e319  js      loc_18009E700
0x18009e31f  mov     rdx, [rbp+7F0h+string]
0x18009e326  mov     rcx, r14
0x18009e329  call    ?GetTokens@IWordsSegmenter@Text@Data@Windows@@UE$AAAPE$AAU?$IVectorView@PE$AAVWordSegment@Text@Data@Windows@@@Collections@Foundation@4@PE$AAVString@Platform@@@Z; Windows::Data::Text::IWordsSegmenter::GetTokens(Platform::String *)
0x18009e32e  mov     rdi, rax
0x18009e331  mov     [rbp+7F0h+var_808], rax
0x18009e335  mov     rcx, rax
0x18009e338  call    ?GetJsonPropertyAsString@JsonPropertyStoreHelper@Common@Cortana@@SAPE$AAVString@Platform@@PE$AAVJsonObject@Json@Data@Windows@@@Z; Cortana::Common::JsonPropertyStoreHelper::GetJsonPropertyAsString(Windows::Data::Json::JsonObject *)
0x18009e33d  mov     rbx, rax
0x18009e340  mov     [rbp+7F0h+var_800], rax
0x18009e344  mov     rcx, rax
0x18009e347  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009e34c  mov     r13, rax
0x18009e34f  mov     [rbp+7F0h+var_7F8], rax
0x18009e353  mov     rcx, rbx; string
0x18009e356  call    WindowsDeleteString_0
0x18009e35b  nop
0x18009e35c  mov     rcx, rdi
0x18009e35f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009e364  nop
0x18009e365  xor     edx, edx; length
0x18009e367  mov     rcx, qword ptr [rbp+7F0h+var_738+18h]; string
0x18009e36e  call    WindowsGetStringRawBuffer_0
0x18009e373  mov     rbx, [rbp+7F8h]
0x18009e37a  xor     edi, edi
0x18009e37c  mov     [rsp+8F0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18009e381  mov     [rsp+8F0h+lpDefaultChar], rdi; lpDefaultChar
0x18009e386  mov     [rsp+8F0h+cbMultiByte], 104h; cbMultiByte
0x18009e38e  lea     rcx, [rbp+7F0h+MultiByteStr]
0x18009e395  mov     [rsp+8F0h+lpMultiByteStr], rcx; lpMultiByteStr
0x18009e39a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18009e39e  mov     r8, rax; lpWideCharStr
0x18009e3a1  xor     edx, edx; dwFlags
0x18009e3a3  mov     ecx, 0FDE9h; CodePage
0x18009e3a8  call    cs:__imp_WideCharToMultiByte
0x18009e3ae  test    eax, eax
0x18009e3b0  jz      loc_18009E6EB
0x18009e3b6  cmp     [r15+8], rdi
0x18009e3ba  jbe     loc_18009E453
0x18009e3c0  lea     rdx, [rbp+7F0h+MultiByteStr]
0x18009e3c7  lea     rcx, [rbp+7F0h+var_848]
0x18009e3cb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18009e3d0  nop
0x18009e3d1  or      esi, 1
0x18009e3d4  mov     dword ptr [rbp+7F0h+string], esi
0x18009e3da  lea     r8, [rbp+7F0h+var_848]
0x18009e3de  lea     rdx, [rbp+7F0h+var_860]
0x18009e3e2  mov     rcx, r15
0x18009e3e5  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::pair<uint,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<uint,unsigned __int64>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18009e3ea  lea     r8, [rbp+7F0h+var_848]
0x18009e3ee  mov     rbx, qword ptr [rbp+7F0h+var_860.Reserved+10h]
0x18009e3f2  mov     rdx, rbx
0x18009e3f5  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::pair<uint,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<uint,unsigned __int64>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::pair<uint,unsigned __int64>>,void *> * const,std::string const &)
0x18009e3fa  test    al, al
0x18009e3fc  jz      short loc_18009E453
0x18009e3fe  cmp     rbx, [r15]
0x18009e401  jz      short loc_18009E453
0x18009e403  lea     rdx, [rbp+7F0h+MultiByteStr]
0x18009e40a  lea     rcx, [rbp+7F0h+var_758]
0x18009e411  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18009e416  nop
0x18009e417  or      esi, 2
0x18009e41a  mov     dword ptr [rbp+7F0h+string], esi
0x18009e420  lea     r8, [rbp+7F0h+var_758]
0x18009e427  lea     rdx, [rbp+7F0h+var_860]
0x18009e42b  mov     rcx, r15
0x18009e42e  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::pair<uint,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<uint,unsigned __int64>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18009e433  lea     r8, [rbp+7F0h+var_758]
0x18009e43a  mov     rdi, qword ptr [rbp+7F0h+var_860.Reserved+10h]
0x18009e43e  mov     rdx, rdi
0x18009e441  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@I_K@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::pair<uint,unsigned __int64>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<uint,unsigned __int64>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::pair<uint,unsigned __int64>>,void *> * const,std::string const &)
0x18009e446  test    al, al
0x18009e448  jz      loc_18009E6CE
0x18009e44e  mov     edi, [rdi+40h]
0x18009e451  jmp     short loc_18009E458
0x18009e453  mov     edi, 0FA00h
0x18009e458  test    sil, 2
0x18009e45c  jz      short loc_18009E46E
0x18009e45e  and     esi, 0FFFFFFFDh
0x18009e461  lea     rcx, [rbp+7F0h+var_758]
0x18009e468  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009e46d  nop
0x18009e46e  test    sil, 1
0x18009e472  jz      short loc_18009E480
0x18009e474  and     esi, 0FFFFFFFEh
0x18009e477  lea     rcx, [rbp+7F0h+var_848]
0x18009e47b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009e480  mov     dword ptr [rsp+8F0h+lpDefaultChar], edi
0x18009e484  mov     [rsp+8F0h+cbMultiByte], edi
0x18009e488  mov     [rsp+8F0h+lpMultiByteStr], r13
0x18009e48d  mov     r9, qword ptr [rbp+7F0h+var_738+18h]
0x18009e494  mov     r8d, edi
0x18009e497  mov     rax, [rsp+8F0h+var_888]
0x18009e49c  mov     rdx, [rax+18h]
0x18009e4a0  lea     rcx, [rbp+7F0h+var_660]
0x18009e4a7  call    ?AddItem@DEInputFileWriter@Search@ConstraintIndex@Cortana@@QEAAXPE$AAVString@Platform@@H00HH@Z; Cortana::ConstraintIndex::Search::DEInputFileWriter::AddItem(Platform::String *,int,Platform::String *,Platform::String *,int,int)
0x18009e4ac  mov     r8, r13
0x18009e4af  mov     edx, edi
0x18009e4b1  lea     rcx, [rbp+7F0h+var_700]
0x18009e4b8  call    ?AddSynonymItemWithWordBreaking@DEInputFileWriter@Search@ConstraintIndex@Cortana@@QEAAXHPE$AAVString@Platform@@@Z; Cortana::ConstraintIndex::Search::DEInputFileWriter::AddSynonymItemWithWordBreaking(int,Platform::String *)
0x18009e4bd  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x18009e4c4  mov     rdx, r14
0x18009e4c7  xor     ecx, ecx
0x18009e4c9  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009e4ce  mov     r14, rax
0x18009e4d1  mov     [rbp+7F0h+var_7F0], rax
0x18009e4d5  mov     [rbp+7F0h+string], 0
0x18009e4e0  lea     r9, [rbp+7F0h+string]; string
0x18009e4e7  lea     r8, [rbp+7F0h+var_860]; hstringHeader
0x18009e4eb  mov     edx, 13h; length
0x18009e4f0  lea     rcx, aSystemHighkeyw; "System.HighKeywords"
0x18009e4f7  call    WindowsCreateStringReference_0
0x18009e4fc  test    eax, eax
0x18009e4fe  js      loc_18009E6E3
0x18009e504  mov     rdx, [rbp+7F0h+string]
  ... truncated ...
```
