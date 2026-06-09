# Cortana::ConstraintIndex::Search::SettingResultItem::ParseAllJsonProperties(Windows::Data::Json::JsonObject *)

- ea: `0x1800b7418`
- end: `0x1800b8404`
- name: `?ParseAllJsonProperties@SettingResultItem@Search@ConstraintIndex@Cortana@@AE$AAAXPE$AAVJsonObject@Json@Data@Windows@@@Z`
- size: `4076`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b645c`

## callees

- `0x1800049e0`
- `0x18000616e`
- `0x18000617a`
- `0x1800061aa`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff00`
- `0x18004086c`
- `0x18007e6b8`
- `0x1800801f0`
- `0x1800830d0`
- `0x180083160`
- `0x180092490`
- `0x180092e54`
- `0x1800930a8`
- `0x18009d9e4`
- `0x1800a50f8`
- `0x1800a9dcc`
- `0x1800abf48`
- `0x1800b5ed4`
- `0x1800b61b4`
- `0x1800b63fc`
- `0x1800b6820`
- `0x1800b68ac`
- `0x1800b6f40`
- `0x1800b7418`
- `0x1800b840c`
- `0x1800fb010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800b77ea`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800b7922`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800b77ea`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800b7922`

## string_xrefs

- `0x1800b7f5b`: `System.Comment`
- `0x1800b7775`: `SettingPaths`
- `0x1800b81e2`: `System.Tile.SmallLogoPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
__int64 __fastcall Cortana::ConstraintIndex::Search::SettingResultItem::ParseAllJsonProperties(_QWORD *a1, __int64 a2)
{
  int v3; // r12d
  __int64 v4; // rbx
  __int64 v5; // r14
  HRESULT v6; // eax
  char v7; // bl
  void (__fastcall *v8)(_QWORD *, HSTRING); // rdi
  __int64 v9; // rsi
  HSTRING CachedStringValue; // rbx
  HRESULT v11; // eax
  char v12; // bl
  void (__fastcall *v13)(_QWORD *, HSTRING); // rdi
  HSTRING v14; // rbx
  HRESULT v15; // eax
  char v16; // bl
  void (__fastcall *v17)(_QWORD *, HSTRING); // rdi
  HSTRING v18; // rbx
  HRESULT v19; // eax
  char v20; // bl
  void (__fastcall *v21)(_QWORD *, HSTRING); // rdi
  HSTRING v22; // rbx
  HRESULT v23; // eax
  char v24; // bl
  __int64 v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rsi
  __int64 Array; // rbx
  __int64 v30; // rdi
  __int64 v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // r13
  __int64 Object; // rbx
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rsi
  HRESULT v43; // eax
  char v44; // bl
  __int64 v45; // rdi
  HSTRING v46; // rbx
  HRESULT v47; // eax
  char v48; // bl
  HSTRING v49; // rbx
  HRESULT v50; // eax
  char v51; // bl
  HSTRING v52; // rbx
  _QWORD *v53; // rbx
  HSTRING v54; // rdi
  HSTRING v55; // rsi
  char v56; // bl
  __int64 v57; // rdx
  __int64 v58; // rcx
  HRESULT v59; // eax
  char v60; // bl
  void (__fastcall *v61)(_QWORD *, HSTRING); // rdi
  HSTRING v62; // rbx
  HRESULT v63; // eax
  char v64; // bl
  void (__fastcall *v65)(_QWORD *, HSTRING); // rdi
  HSTRING v66; // rbx
  HRESULT v67; // eax
  char v68; // bl
  void (__fastcall *v69)(_QWORD *, HSTRING); // rdi
  HSTRING v70; // rbx
  HRESULT v71; // eax
  char v72; // bl
  void (__fastcall *v73)(_QWORD *, HSTRING); // rdi
  HSTRING v74; // rbx
  HRESULT v75; // eax
  char v76; // bl
  void (__fastcall *v77)(_QWORD *, HSTRING); // rdi
  HSTRING v78; // rbx
  HRESULT v79; // eax
  char v80; // bl
  void (__fastcall *v81)(_QWORD *, HSTRING); // rdi
  HSTRING v82; // rbx
  HRESULT v83; // eax
  char v84; // bl
  void (__fastcall *v85)(_QWORD *, HSTRING); // rdi
  HSTRING v86; // rbx
  HRESULT v87; // eax
  char v88; // bl
  void (__fastcall *v89)(_QWORD *, HSTRING); // rdi
  HSTRING v90; // rbx
  HRESULT v91; // eax
  char v92; // bl
  void (__fastcall *v93)(_QWORD *, HSTRING); // rdi
  HSTRING v94; // rbx
  HSTRING v96; // [rsp+20h] [rbp-E0h]
  HSTRING v97; // [rsp+20h] [rbp-E0h]
  HSTRING v98; // [rsp+20h] [rbp-E0h]
  HSTRING v99; // [rsp+20h] [rbp-E0h]
  HSTRING v100; // [rsp+20h] [rbp-E0h]
  __int64 v101; // [rsp+20h] [rbp-E0h]
  HSTRING v102; // [rsp+20h] [rbp-E0h]
  HSTRING v103; // [rsp+20h] [rbp-E0h]
  HSTRING v104; // [rsp+20h] [rbp-E0h]
  HSTRING v105; // [rsp+20h] [rbp-E0h]
  HSTRING v106; // [rsp+20h] [rbp-E0h]
  HSTRING v107; // [rsp+20h] [rbp-E0h]
  HSTRING v108; // [rsp+20h] [rbp-E0h]
  HSTRING v109; // [rsp+20h] [rbp-E0h]
  HSTRING v110; // [rsp+20h] [rbp-E0h]
  HSTRING v111; // [rsp+20h] [rbp-E0h]
  HSTRING v112; // [rsp+20h] [rbp-E0h]
  HSTRING v113; // [rsp+20h] [rbp-E0h]
  __int64 v114; // [rsp+28h] [rbp-D8h]
  __int64 v115; // [rsp+28h] [rbp-D8h]
  HSTRING_HEADER v116; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v117; // [rsp+48h] [rbp-B8h]
  __int64 v118; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v119; // [rsp+58h] [rbp-A8h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v121; // [rsp+78h] [rbp-88h]
  __int64 v122; // [rsp+80h] [rbp-80h]
  __int64 v123; // [rsp+88h] [rbp-78h]
  __int64 v124; // [rsp+90h] [rbp-70h]
  __int64 v125; // [rsp+98h] [rbp-68h]
  __int64 v126; // [rsp+A0h] [rbp-60h]
  __int64 v127; // [rsp+A8h] [rbp-58h]
  HSTRING v128; // [rsp+B0h] [rbp-50h]
  __int64 v129; // [rsp+B8h] [rbp-48h]
  HSTRING v130; // [rsp+C0h] [rbp-40h]
  __int64 v131; // [rsp+C8h] [rbp-38h]
  __int64 v132; // [rsp+D0h] [rbp-30h]
  HSTRING v133; // [rsp+D8h] [rbp-28h]
  __int64 v134; // [rsp+E0h] [rbp-20h]
  void *v135; // [rsp+E8h] [rbp-18h]
  __int64 v136; // [rsp+F0h] [rbp-10h]
  __int64 v137; // [rsp+F8h] [rbp-8h]
  __int64 v138; // [rsp+100h] [rbp+0h]
  __int64 v139; // [rsp+108h] [rbp+8h]
  __int64 v140; // [rsp+110h] [rbp+10h]
  void *v141; // [rsp+118h] [rbp+18h]
  __int64 v142; // [rsp+120h] [rbp+20h]
  __int64 v143; // [rsp+128h] [rbp+28h]
  __int64 v144; // [rsp+130h] [rbp+30h]
  __int64 v145; // [rsp+138h] [rbp+38h]
  __int64 v146; // [rsp+140h] [rbp+40h]
  __int64 v147; // [rsp+148h] [rbp+48h]
  HSTRING v148; // [rsp+150h] [rbp+50h]
  __int64 v149; // [rsp+158h] [rbp+58h]
  HSTRING v150; // [rsp+160h] [rbp+60h]
  __int64 v151; // [rsp+168h] [rbp+68h]
  HSTRING v152; // [rsp+170h] [rbp+70h]
  HSTRING v153; // [rsp+178h] [rbp+78h]
  __int64 v154; // [rsp+180h] [rbp+80h]
  HSTRING v155; // [rsp+188h] [rbp+88h]
  __int64 v156; // [rsp+190h] [rbp+90h]
  HSTRING v157; // [rsp+198h] [rbp+98h]
  __int64 v158; // [rsp+1A0h] [rbp+A0h]
  HSTRING v159; // [rsp+1A8h] [rbp+A8h]
  __int64 v160; // [rsp+1B0h] [rbp+B0h]
  HSTRING v161; // [rsp+1B8h] [rbp+B8h]
  __int64 v162; // [rsp+1C0h] [rbp+C0h]
  __int64 v163; // [rsp+1C8h] [rbp+C8h]
  HSTRING v164; // [rsp+1D0h] [rbp+D0h]
  __int64 v165; // [rsp+1D8h] [rbp+D8h]
  HSTRING v166; // [rsp+1E0h] [rbp+E0h]
  __int64 v167; // [rsp+1E8h] [rbp+E8h]
  HSTRING v168; // [rsp+1F0h] [rbp+F0h]
  __int64 v169; // [rsp+1F8h] [rbp+F8h]
  HSTRING v170; // [rsp+200h] [rbp+100h]
  _QWORD v171[3]; // [rsp+208h] [rbp+108h] BYREF
  __int128 v172; // [rsp+220h] [rbp+120h] BYREF
  HSTRING v173; // [rsp+230h] [rbp+130h]
  HSTRING string; // [rsp+238h] [rbp+138h] BYREF
  __int64 v175; // [rsp+240h] [rbp+140h]
  _QWORD v176[2]; // [rsp+248h] [rbp+148h] BYREF
  _QWORD v177[2]; // [rsp+258h] [rbp+158h] BYREF
  _QWORD v178[2]; // [rsp+268h] [rbp+168h] BYREF

  v3 = 0;
  LODWORD(string) = 0;
  v175 = __abi_winrt_ptr_ctor(a2);
  v4 = __abi_winrt_cast_to(
         0,
         v175,
         _uuidof__AU__IIterable_PE_AAU__IKeyValuePair_PE_AAVString_Platform__PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows___Collections_Foundation_Windows__);
  Windows::Foundation::Collections::begin<Windows::Foundation::Collections::IKeyValuePair<Platform::String __gc *,Windows::Data::Json::IJsonValue __gc *> __gc *>(
    v177,
    v4);
  __abi_winrt_ptr_dtor(v4);
  v114 = __abi_winrt_cast_to(
           0,
           v175,
           _uuidof__AU__IIterable_PE_AAU__IKeyValuePair_PE_AAVString_Platform__PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows___Collections_Foundation_Windows__);
  v172 = 0;
  __abi_winrt_ptr_dtor(v114);
  while ( v177[0] )
  {
    v5 = __abi_winrt_ptr_ctor(v177[1]);
    v126 = v5;
    string = 0;
    v6 = WindowsCreateStringReference_0(L"System.ParsingName", 0x12u, &hstringHeader, &string);
    if ( v6 < 0 )
      __abi_WinRTraiseException(v6);
    v96 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v7 = Platform::String::operator==(v96, string);
    WindowsDeleteString_0(v96);
    if ( v7 )
    {
      v8 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 128LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v127 = v9;
      CachedStringValue = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v128 = CachedStringValue;
      v8(a1, CachedStringValue);
      WindowsDeleteString_0(CachedStringValue);
      goto LABEL_81;
    }
    string = 0;
    v11 = WindowsCreateStringReference_0(L"System.Setting.Glyph", 0x14u, &hstringHeader, &string);
    if ( v11 < 0 )
      __abi_WinRTraiseException(v11);
    v97 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v12 = Platform::String::operator==(v97, string);
    WindowsDeleteString_0(v97);
    if ( v12 )
    {
      v13 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 88LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v129 = v9;
      v14 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v130 = v14;
      v13(a1, v14);
      WindowsDeleteString_0(v14);
      goto LABEL_81;
    }
    string = 0;
    v15 = WindowsCreateStringReference_0(L"System.Setting.GlyphRtl", 0x17u, &hstringHeader, &string);
    if ( v15 < 0 )
      __abi_WinRTraiseException(v15);
    v98 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v16 = Platform::String::operator==(v98, string);
    WindowsDeleteString_0(v98);
    if ( v16 )
    {
      v17 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 96LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v131 = v9;
      v18 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v171[2] = v18;
      v17(a1, v18);
      WindowsDeleteString_0(v18);
      goto LABEL_81;
    }
    string = 0;
    v19 = WindowsCreateStringReference_0(L"System.Setting.FontFamily", 0x19u, &hstringHeader, &string);
    if ( v19 < 0 )
      __abi_WinRTraiseException(v19);
    v99 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v20 = Platform::String::operator==(v99, string);
    WindowsDeleteString_0(v99);
    if ( v20 )
    {
      v21 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 104LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v132 = v9;
      v22 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v133 = v22;
      v21(a1, v22);
      WindowsDeleteString_0(v22);
      goto LABEL_81;
    }
    string = 0;
    v23 = WindowsCreateStringReference_0(L"SettingPaths", 0xCu, &hstringHeader, &string);
    if ( v23 < 0 )
      __abi_WinRTraiseException(v23);
    v100 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v24 = Platform::String::operator==(v100, string);
    WindowsDeleteString_0(v100);
    if ( v24 )
    {
      v25 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v134 = v25;
      v26 = __abi_winrt_ptr_ctor(v25);
      v115 = v26;
      __abi_winrt_ptr_dtor(v25);
      v135 = Platform::Details::Heap::Allocate(0x88u, 0xB0u);
      v27 = Platform::Collections::Vector<Cortana::ConstraintIndex::Search::SettingPath __gc *,std::equal_to<Cortana::ConstraintIndex::Search::SettingPath __gc *>,1>::Vector<Cortana::ConstraintIndex::Search::SettingPath __gc *,std::equal_to<Cortana::ConstraintIndex::Search::SettingPath __gc *>,1>(v135);
      v136 = v27;
      v28 = __abi_winrt_ptr_ctor(v27);
      v122 = v28;
      __abi_winrt_ptr_dtor(v27);
      if ( (unsigned int)Windows::Storage::Streams::IDataReader::UnconsumedBufferLength::get(v26) != 4 )
        goto LABEL_53;
      Array = Windows::Data::Json::IJsonValue::GetArray(v26);
      v137 = Array;
      v30 = __abi_winrt_ptr_ctor(Array);
      v125 = v30;
      __abi_winrt_ptr_dtor(Array);
      v31 = __abi_winrt_cast_to(
              0,
              v30,
              _uuidof__AU__IVector_PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
      v138 = v31;
      Platform::Collections::VectorViewIterator<Platform::String __gc *>::VectorViewIterator<Platform::String __gc *>(
        &v118,
        v31);
      v3 |= 8u;
      __abi_winrt_ptr_dtor(v31);
      v32 = __abi_winrt_cast_to(
              0,
              v30,
              _uuidof__AU__IVector_PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows__);
      v139 = v32;
      Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint __gc *>(v178, v32);
      __abi_winrt_ptr_dtor(v32);
      v33 = v119;
      while ( 2 )
      {
        if ( v33 != v178[1] )
        {
          v34 = Platform::Collections::VectorIterator<Windows::Data::Json::IJsonValue __gc *>::operator*(&v118, v171);
          v35 = Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>::operator*(v34);
          v140 = v35;
          v36 = __abi_winrt_ptr_ctor(v35);
          v124 = v36;
          __abi_winrt_ptr_dtor(v35);
          __abi_winrt_ptr_dtor(v171[0]);
          if ( (unsigned int)Windows::Storage::Streams::IDataReader::UnconsumedBufferLength::get(v36) != 5 )
            goto LABEL_49;
          v141 = Platform::Details::Heap::Allocate(0x38u, 0x50u);
          v37 = Cortana::ConstraintIndex::Search::SettingPath::SettingPath(v141);
          v142 = v37;
          v38 = __abi_winrt_ptr_ctor(v37);
          v143 = v38;
          __abi_winrt_ptr_dtor(v37);
          Object = Windows::Data::Json::IJsonValue::GetObject(v36);
          v144 = Object;
          v40 = __abi_winrt_ptr_ctor(Object);
          v123 = v40;
          __abi_winrt_ptr_dtor(Object);
          v41 = __abi_winrt_cast_to(
                  0,
                  v40,
                  _uuidof__AU__IIterable_PE_AAU__IKeyValuePair_PE_AAVString_Platform__PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows___Collections_Foundation_Windows__);
          v145 = v41;
          Windows::Foundation::Collections::begin<Windows::Foundation::Collections::IKeyValuePair<Platform::String __gc *,Windows::Data::Json::IJsonValue __gc *> __gc *>(
            v176,
            v41);
          __abi_winrt_ptr_dtor(v41);
          v101 = __abi_winrt_cast_to(
                   0,
                   v40,
                   _uuidof__AU__IIterable_PE_AAU__IKeyValuePair_PE_AAVString_Platform__PE_AAUIJsonValue_Json_Data_Windows___Collections_Foundation_Windows___Collections_Foundation_Windows__);
          *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
          __abi_winrt_ptr_dtor(v101);
LABEL_22:
          if ( !v176[0] )
          {
            _lambda_c21b1ebc8d7645bf6362025326548cf8_::~_lambda_c21b1ebc8d7645bf6362025326548cf8_((_lambda_c21b1ebc8d7645bf6362025326548cf8_ *)&hstringHeader);
            _lambda_c21b1ebc8d7645bf6362025326548cf8_::~_lambda_c21b1ebc8d7645bf6362025326548cf8_((_lambda_c21b1ebc8d7645bf6362025326548cf8_ *)v176);
            v53 = a1 + 1;
            v54 = (HSTRING)(*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 200LL))(a1 + 1);
            v153 = v54;
            v3 |= 1u;
            LODWORD(string) = v3;
            if ( WindowsIsStringEmpty_0(v54)
              && (v121 = (HSTRING)(*(__int64 (__fastcall **)(_QWORD *))(*v53 + 192LL))(a1 + 1),
                  v3 |= 2u,
                  LODWORD(string) = v3,
                  WindowsIsStringEmpty_0(v121)) )
            {
              v55 = (HSTRING)(*(__int64 (__fastcall **)(_QWORD *))(*v53 + 184LL))(a1 + 1);
              v117 = v55;
              v3 |= 4u;
              if ( WindowsIsStringEmpty_0(v55) )
              {
                v56 = 1;
                goto LABEL_40;
              }
            }
            else
            {
              v55 = v117;
            }
            v56 = 0;
LABEL_40:
            if ( (v3 & 4) != 0 )
            {
              v3 &= ~4u;
              WindowsDeleteString_0(v55);
            }
            if ( (v3 & 2) != 0 )
            {
              v3 &= ~2u;
              WindowsDeleteString_0(v121);
            }
            if ( (v3 & 1) != 0 )
            {
              v3 &= ~1u;
              WindowsDeleteString_0(v54);
            }
            if ( v56 )
              Cortana::ConstraintIndex::Search::SettingResultItem::PopulateSettingPathIds(a1, v38);
            v28 = v122;
            _Append__Q__IVector_PE_AAUSettingPath_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows____Vector_PE_AAUSettingPath_Search_ConstraintIndex_Cortana__U__equal_to_PE_AAUSettingPath_Search_ConstraintIndex_Cortana___std___00_2Platform__UE_AAAXPE_AAUSettingPath_Search_ConstraintIndex_Cortana___Z(
              v122,
              v38);
            __abi_winrt_ptr_dtor(v123);
            __abi_winrt_ptr_dtor(v38);
            v36 = v124;
LABEL_49:
            __abi_winrt_ptr_dtor(v36);
            v33 = ++v119;
            continue;
          }
          v42 = __abi_winrt_ptr_ctor(v176[1]);
          v146 = v42;
          string = 0;
          v43 = WindowsCreateStringReference_0(L"System.Setting.PageID", 0x15u, &v116, &string);
          if ( v43 < 0 )
            __abi_WinRTraiseException(v43);
          v102 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v42);
          v44 = Platform::String::operator==(v102, string);
          WindowsDeleteString_0(v102);
          if ( v44 )
          {
            v45 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v42);
            v147 = v45;
            v46 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v45);
            v148 = v46;
            __abi_winrt_ptrto_string_assign(v38 + 32, v46);
            WindowsDeleteString_0(v46);
            goto LABEL_32;
          }
          string = 0;
          v47 = WindowsCreateStringReference_0(L"System.Setting.GroupID", 0x16u, &v116, &string);
          if ( v47 < 0 )
            __abi_WinRTraiseException(v47);
          v103 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v42);
          v48 = Platform::String::operator==(v103, string);
          WindowsDeleteString_0(v103);
          if ( v48 )
          {
            v45 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v42);
            v149 = v45;
            v49 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v45);
            v150 = v49;
            __abi_winrt_ptrto_string_assign(v38 + 40, v49);
            WindowsDeleteString_0(v49);
            goto LABEL_32;
          }
          string = 0;
          v50 = WindowsCreateStringReference_0(L"System.Setting.SettingID", 0x18u, &v116, &string);
          if ( v50 < 0 )
            __abi_WinRTraiseException(v50);
          v104 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v42);
          v51 = Platform::String::operator==(v104, string);
          WindowsDeleteString_0(v104);
          if ( v51 )
          {
            v45 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v42);
            v151 = v45;
            v52 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v45);
            v152 = v52;
            __abi_winrt_ptrto_string_assign(v38 + 48, v52);
            WindowsDeleteString_0(v52);
LABEL_32:
            __abi_winrt_ptr_dtor(v45);
          }
          __abi_winrt_ptr_dtor(v42);
          Platform::Collections::InputIterator<Windows::Foundation::Collections::IKeyValuePair<Platform::String __gc *,Windows::Data::Json::IJsonValue __gc *> __gc *>::operator++(v176);
          goto LABEL_22;
        }
        break;
      }
      __abi_winrt_ptr_dtor(v178[0]);
      __abi_winrt_ptr_dtor(v118);
      __abi_winrt_ptr_dtor(v125);
      v57 = v28 + 8;
      if ( !v28 )
        v57 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64))(*a1 + 168LL))(a1, v57);
      v26 = v115;
LABEL_53:
      __abi_winrt_ptr_dtor(v28);
      v58 = v26;
      goto LABEL_82;
    }
    string = 0;
    v59 = WindowsCreateStringReference_0(L"System.Setting.PageID", 0x15u, &v116, &string);
    if ( v59 < 0 )
      __abi_WinRTraiseException(v59);
    v105 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v60 = Platform::String::operator==(v105, string);
    WindowsDeleteString_0(v105);
    if ( v60 )
    {
      v61 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 72LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v154 = v9;
      v62 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v155 = v62;
      v61(a1, v62);
      WindowsDeleteString_0(v62);
LABEL_81:
      v58 = v9;
LABEL_82:
      __abi_winrt_ptr_dtor(v58);
      goto LABEL_83;
    }
    string = 0;
    v63 = WindowsCreateStringReference_0(L"System.Setting.GroupID", 0x16u, &v116, &string);
    if ( v63 < 0 )
      __abi_WinRTraiseException(v63);
    v106 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v64 = Platform::String::operator==(v106, string);
    WindowsDeleteString_0(v106);
    if ( v64 )
    {
      v65 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 64LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v156 = v9;
      v66 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v157 = v66;
      v65(a1, v66);
      WindowsDeleteString_0(v66);
      goto LABEL_81;
    }
    string = 0;
    v67 = WindowsCreateStringReference_0(L"System.Setting.SettingID", 0x18u, &v116, &string);
    if ( v67 < 0 )
      __abi_WinRTraiseException(v67);
    v107 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v68 = Platform::String::operator==(v107, string);
    WindowsDeleteString_0(v107);
    if ( v68 )
    {
      v69 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 56LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v158 = v9;
      v70 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v159 = v70;
      v69(a1, v70);
      WindowsDeleteString_0(v70);
      goto LABEL_81;
    }
    string = 0;
    v71 = WindowsCreateStringReference_0(L"System.Comment", 0xEu, &v116, &string);
    if ( v71 < 0 )
      __abi_WinRTraiseException(v71);
    v108 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v72 = Platform::String::operator==(v108, string);
    WindowsDeleteString_0(v108);
    if ( v72 )
    {
      v73 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 48LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v160 = v9;
      v74 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v161 = v74;
      v73(a1, v74);
      WindowsDeleteString_0(v74);
      goto LABEL_81;
    }
    string = 0;
    v75 = WindowsCreateStringReference_0(L"System.Setting.HostID", 0x15u, &v116, &string);
    if ( v75 < 0 )
      __abi_WinRTraiseException(v75);
    v109 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v76 = Platform::String::operator==(v109, string);
    WindowsDeleteString_0(v109);
    if ( v76 )
    {
      v77 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 152LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v162 = v9;
      v78 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v170 = v78;
      v77(a1, v78);
      WindowsDeleteString_0(v78);
      goto LABEL_81;
    }
    string = 0;
    v79 = WindowsCreateStringReference_0(L"System.Setting.SettingsEnvironmentID", 0x24u, &v116, &string);
    if ( v79 < 0 )
      __abi_WinRTraiseException(v79);
    v110 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v80 = Platform::String::operator==(v110, string);
    WindowsDeleteString_0(v110);
    if ( v80 )
    {
      v81 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 112LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v163 = v9;
      v82 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v164 = v82;
      v81(a1, v82);
      WindowsDeleteString_0(v82);
      goto LABEL_81;
    }
    string = 0;
    v83 = WindowsCreateStringReference_0(L"System.Setting.Condition", 0x18u, &v116, &string);
    if ( v83 < 0 )
      __abi_WinRTraiseException(v83);
    v111 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v84 = Platform::String::operator==(v111, string);
    WindowsDeleteString_0(v111);
    if ( v84 )
    {
      v85 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 120LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v165 = v9;
      v86 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v166 = v86;
      v85(a1, v86);
      WindowsDeleteString_0(v86);
      goto LABEL_81;
    }
    string = 0;
    v87 = WindowsCreateStringReference_0(L"System.Tile.SmallLogoPath", 0x19u, &v116, &string);
    if ( v87 < 0 )
      __abi_WinRTraiseException(v87);
    v112 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v88 = Platform::String::operator==(v112, string);
    WindowsDeleteString_0(v112);
    if ( v88 )
    {
      v89 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 80LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v167 = v9;
      v90 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v168 = v90;
      v89(a1, v90);
      WindowsDeleteString_0(v90);
      goto LABEL_81;
    }
    string = 0;
    v91 = WindowsCreateStringReference_0(L"System.AppUserModel.ActivationContext", 0x25u, &v116, &string);
    if ( v91 < 0 )
      __abi_WinRTraiseException(v91);
    v113 = (HSTRING)WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(v5);
    v92 = Platform::String::operator==(v113, string);
    WindowsDeleteString_0(v113);
    if ( v92 )
    {
      v93 = *(void (__fastcall **)(_QWORD *, HSTRING))(*a1 + 144LL);
      v9 = Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(v5);
      v169 = v9;
      v94 = (HSTRING)Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(v9);
      v173 = v94;
      v93(a1, v94);
      WindowsDeleteString_0(v94);
      goto LABEL_81;
    }
LABEL_83:
    __abi_winrt_ptr_dtor(v5);
    Platform::Collections::InputIterator<Windows::Foundation::Collections::IKeyValuePair<Platform::String __gc *,Windows::Data::Json::IJsonValue __gc *> __gc *>::operator++(v177);
  }
  _lambda_c21b1ebc8d7645bf6362025326548cf8_::~_lambda_c21b1ebc8d7645bf6362025326548cf8_((_lambda_c21b1ebc8d7645bf6362025326548cf8_ *)&v172);
  _lambda_c21b1ebc8d7645bf6362025326548cf8_::~_lambda_c21b1ebc8d7645bf6362025326548cf8_((_lambda_c21b1ebc8d7645bf6362025326548cf8_ *)v177);
  return __abi_winrt_ptr_dtor(v175);
}

```

## disassembly

```asm
0x1800b7418  mov     [rsp-8+arg_10], rbx
0x1800b741d  push    rbp
0x1800b741e  push    rsi
0x1800b741f  push    rdi
0x1800b7420  push    r12
0x1800b7422  push    r13
0x1800b7424  push    r14
0x1800b7426  push    r15
0x1800b7428  lea     rbp, [rsp-180h]
0x1800b7430  sub     rsp, 280h
0x1800b7437  mov     rax, cs:__security_cookie
0x1800b743e  xor     rax, rsp
0x1800b7441  mov     [rbp+1B0h+var_38], rax
0x1800b7448  mov     r15, rcx
0x1800b744b  mov     [rbp+1B0h+var_70], rdx
0x1800b7452  xor     r13d, r13d
0x1800b7455  mov     r12d, r13d
0x1800b7458  mov     dword ptr [rbp+1B0h+string], r13d
0x1800b745f  mov     rcx, rdx
0x1800b7462  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800b7467  mov     rdi, rax
0x1800b746a  mov     [rbp+1B0h+var_70], rax
0x1800b7471  lea     r8, __uuidof_?AU?$IIterable@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@
0x1800b7478  mov     rdx, rax
0x1800b747b  xor     ecx, ecx
0x1800b747d  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800b7482  mov     rbx, rax
0x1800b7485  mov     [rsp+2B0h+var_288], rax
0x1800b748a  mov     rdx, rax
0x1800b748d  lea     rcx, [rbp+1B0h+var_58]
0x1800b7494  call    ??$begin@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@YA?AV?$InputIterator@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@0Platform@@PE$AAU?$IIterable@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@012@@Z; Windows::Foundation::Collections::begin<Windows::Foundation::Collections::IKeyValuePair<Platform::String *,Windows::Data::Json::IJsonValue *> *>(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<Platform::String *,Windows::Data::Json::IJsonValue *> *> *)
0x1800b7499  nop
0x1800b749a  mov     rcx, rbx
0x1800b749d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b74a2  lea     r8, __uuidof_?AU?$IIterable@PE$AAU?$IKeyValuePair@PE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@
0x1800b74a9  mov     rdx, rdi
0x1800b74ac  xor     ecx, ecx
0x1800b74ae  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800b74b3  mov     [rsp+2B0h+var_288], rax
0x1800b74b8  xorps   xmm0, xmm0
0x1800b74bb  movdqu  [rbp+1B0h+var_90], xmm0
0x1800b74c3  mov     rcx, rax
0x1800b74c6  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b74cb  cmp     [rbp+1B0h+var_58], r13
0x1800b74d2  jz      loc_1800B832C
0x1800b74d8  mov     rcx, [rbp+1B0h+var_50]
0x1800b74df  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800b74e4  mov     r14, rax
0x1800b74e7  mov     [rbp+1B0h+var_210], rax
0x1800b74eb  mov     [rbp+1B0h+string], r13
0x1800b74f2  lea     r9, [rbp+1B0h+string]; string
0x1800b74f9  lea     r8, [rsp+2B0h+hstringHeader]; hstringHeader
0x1800b74fe  mov     edx, 12h; length
0x1800b7503  lea     rcx, aSystemParsingn; "System.ParsingName"
0x1800b750a  call    WindowsCreateStringReference_0
0x1800b750f  test    eax, eax
0x1800b7511  js      loc_1800B837C
0x1800b7517  mov     rcx, r14
0x1800b751a  call    ?get@Id@ISystemSettingEntryPoint@Profile@System@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(void)
0x1800b751f  mov     rdi, rax
0x1800b7522  mov     [rsp+2B0h+var_290], rax
0x1800b7527  mov     rdx, [rbp+1B0h+string]
0x1800b752e  mov     rcx, rax
0x1800b7531  call    ??8String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator==(Platform::String *,Platform::String *)
0x1800b7536  mov     bl, al
0x1800b7538  mov     rcx, rdi; string
0x1800b753b  call    WindowsDeleteString_0
0x1800b7540  test    bl, bl
0x1800b7542  jz      short loc_1800B7589
0x1800b7544  mov     rax, [r15]
0x1800b7547  mov     rdi, [rax+80h]
0x1800b754e  mov     rcx, r14
0x1800b7551  call    ?get@RequestedUri@IBackgroundTransferOperation@BackgroundTransfer@Networking@Windows@@UE$AAAPE$AAVUri@Foundation@5@XZ; Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(void)
0x1800b7556  mov     rsi, rax
0x1800b7559  mov     [rbp+1B0h+var_208], rax
0x1800b755d  mov     rcx, rax
0x1800b7560  call    ?GetCachedStringValue@SettingResultItem@Search@ConstraintIndex@Cortana@@CAPE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Z; Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(Windows::Data::Json::IJsonValue *)
0x1800b7565  mov     rbx, rax
0x1800b7568  mov     [rbp+1B0h+var_200], rax
0x1800b756c  mov     rdx, rax
0x1800b756f  mov     rcx, r15
0x1800b7572  mov     rax, rdi
0x1800b7575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b757a  nop
0x1800b757b  mov     rcx, rbx; string
0x1800b757e  call    WindowsDeleteString_0
0x1800b7583  nop
0x1800b7584  jmp     loc_1800B830A
0x1800b7589  mov     [rbp+1B0h+string], r13
0x1800b7590  lea     r9, [rbp+1B0h+string]; string
0x1800b7597  lea     r8, [rsp+2B0h+hstringHeader]; hstringHeader
0x1800b759c  mov     edx, 14h; length
0x1800b75a1  lea     rcx, aSystemSettingG; "System.Setting.Glyph"
0x1800b75a8  call    WindowsCreateStringReference_0
0x1800b75ad  test    eax, eax
0x1800b75af  js      loc_1800B83FC
0x1800b75b5  mov     rcx, r14
0x1800b75b8  call    ?get@Id@ISystemSettingEntryPoint@Profile@System@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(void)
0x1800b75bd  mov     rdi, rax
0x1800b75c0  mov     [rsp+2B0h+var_290], rax
0x1800b75c5  mov     rdx, [rbp+1B0h+string]
0x1800b75cc  mov     rcx, rax
0x1800b75cf  call    ??8String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator==(Platform::String *,Platform::String *)
0x1800b75d4  mov     bl, al
0x1800b75d6  mov     rcx, rdi; string
0x1800b75d9  call    WindowsDeleteString_0
0x1800b75de  test    bl, bl
0x1800b75e0  jz      short loc_1800B7624
0x1800b75e2  mov     rax, [r15]
0x1800b75e5  mov     rdi, [rax+58h]
0x1800b75e9  mov     rcx, r14
0x1800b75ec  call    ?get@RequestedUri@IBackgroundTransferOperation@BackgroundTransfer@Networking@Windows@@UE$AAAPE$AAVUri@Foundation@5@XZ; Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(void)
0x1800b75f1  mov     rsi, rax
0x1800b75f4  mov     [rbp+1B0h+var_1F8], rax
0x1800b75f8  mov     rcx, rax
0x1800b75fb  call    ?GetCachedStringValue@SettingResultItem@Search@ConstraintIndex@Cortana@@CAPE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Z; Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(Windows::Data::Json::IJsonValue *)
0x1800b7600  mov     rbx, rax
0x1800b7603  mov     [rbp+1B0h+var_1F0], rax
0x1800b7607  mov     rdx, rax
0x1800b760a  mov     rcx, r15
0x1800b760d  mov     rax, rdi
0x1800b7610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7615  nop
0x1800b7616  mov     rcx, rbx; string
0x1800b7619  call    WindowsDeleteString_0
0x1800b761e  nop
0x1800b761f  jmp     loc_1800B830A
0x1800b7624  mov     [rbp+1B0h+string], r13
0x1800b762b  lea     r9, [rbp+1B0h+string]; string
0x1800b7632  lea     r8, [rsp+2B0h+hstringHeader]; hstringHeader
0x1800b7637  mov     edx, 17h; length
0x1800b763c  lea     rcx, aSystemSettingG_0; "System.Setting.GlyphRtl"
0x1800b7643  call    WindowsCreateStringReference_0
0x1800b7648  test    eax, eax
0x1800b764a  js      loc_1800B83F4
0x1800b7650  mov     rcx, r14
0x1800b7653  call    ?get@Id@ISystemSettingEntryPoint@Profile@System@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(void)
0x1800b7658  mov     rdi, rax
0x1800b765b  mov     [rsp+2B0h+var_290], rax
0x1800b7660  mov     rdx, [rbp+1B0h+string]
0x1800b7667  mov     rcx, rax
0x1800b766a  call    ??8String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator==(Platform::String *,Platform::String *)
0x1800b766f  mov     bl, al
0x1800b7671  mov     rcx, rdi; string
0x1800b7674  call    WindowsDeleteString_0
0x1800b7679  test    bl, bl
0x1800b767b  jz      short loc_1800B76C2
0x1800b767d  mov     rax, [r15]
0x1800b7680  mov     rdi, [rax+60h]
0x1800b7684  mov     rcx, r14
0x1800b7687  call    ?get@RequestedUri@IBackgroundTransferOperation@BackgroundTransfer@Networking@Windows@@UE$AAAPE$AAVUri@Foundation@5@XZ; Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(void)
0x1800b768c  mov     rsi, rax
0x1800b768f  mov     [rbp+1B0h+var_1E8], rax
0x1800b7693  mov     rcx, rax
0x1800b7696  call    ?GetCachedStringValue@SettingResultItem@Search@ConstraintIndex@Cortana@@CAPE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Z; Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(Windows::Data::Json::IJsonValue *)
0x1800b769b  mov     rbx, rax
0x1800b769e  mov     [rbp+1B0h+var_98], rax
0x1800b76a5  mov     rdx, rax
0x1800b76a8  mov     rcx, r15
0x1800b76ab  mov     rax, rdi
0x1800b76ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b76b3  nop
0x1800b76b4  mov     rcx, rbx; string
0x1800b76b7  call    WindowsDeleteString_0
0x1800b76bc  nop
0x1800b76bd  jmp     loc_1800B830A
0x1800b76c2  mov     [rbp+1B0h+string], r13
0x1800b76c9  lea     r9, [rbp+1B0h+string]; string
0x1800b76d0  lea     r8, [rsp+2B0h+hstringHeader]; hstringHeader
0x1800b76d5  mov     edx, 19h; length
0x1800b76da  lea     rcx, aSystemSettingF; "System.Setting.FontFamily"
0x1800b76e1  call    WindowsCreateStringReference_0
0x1800b76e6  test    eax, eax
0x1800b76e8  js      loc_1800B83EC
0x1800b76ee  mov     rcx, r14
0x1800b76f1  call    ?get@Id@ISystemSettingEntryPoint@Profile@System@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(void)
0x1800b76f6  mov     rdi, rax
0x1800b76f9  mov     [rsp+2B0h+var_290], rax
0x1800b76fe  mov     rdx, [rbp+1B0h+string]
0x1800b7705  mov     rcx, rax
0x1800b7708  call    ??8String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator==(Platform::String *,Platform::String *)
0x1800b770d  mov     bl, al
0x1800b770f  mov     rcx, rdi; string
0x1800b7712  call    WindowsDeleteString_0
0x1800b7717  test    bl, bl
0x1800b7719  jz      short loc_1800B775D
0x1800b771b  mov     rax, [r15]
0x1800b771e  mov     rdi, [rax+68h]
0x1800b7722  mov     rcx, r14
0x1800b7725  call    ?get@RequestedUri@IBackgroundTransferOperation@BackgroundTransfer@Networking@Windows@@UE$AAAPE$AAVUri@Foundation@5@XZ; Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(void)
0x1800b772a  mov     rsi, rax
0x1800b772d  mov     [rbp+1B0h+var_1E0], rax
0x1800b7731  mov     rcx, rax
0x1800b7734  call    ?GetCachedStringValue@SettingResultItem@Search@ConstraintIndex@Cortana@@CAPE$AAVString@Platform@@PE$AAUIJsonValue@Json@Data@Windows@@@Z; Cortana::ConstraintIndex::Search::SettingResultItem::GetCachedStringValue(Windows::Data::Json::IJsonValue *)
0x1800b7739  mov     rbx, rax
0x1800b773c  mov     [rbp+1B0h+var_1D8], rax
0x1800b7740  mov     rdx, rax
0x1800b7743  mov     rcx, r15
0x1800b7746  mov     rax, rdi
0x1800b7749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b774e  nop
0x1800b774f  mov     rcx, rbx; string
0x1800b7752  call    WindowsDeleteString_0
0x1800b7757  nop
0x1800b7758  jmp     loc_1800B830A
0x1800b775d  mov     [rbp+1B0h+string], r13
0x1800b7764  lea     r9, [rbp+1B0h+string]; string
0x1800b776b  lea     r8, [rsp+2B0h+hstringHeader]; hstringHeader
0x1800b7770  mov     edx, 0Ch; length
0x1800b7775  lea     rcx, aSettingpaths; "SettingPaths"
0x1800b777c  call    WindowsCreateStringReference_0
0x1800b7781  test    eax, eax
0x1800b7783  js      loc_1800B83E4
0x1800b7789  mov     rcx, r14
0x1800b778c  call    ?get@Id@ISystemSettingEntryPoint@Profile@System@WindowsUdk@@UE$AAAPE$AAVString@Platform@@XZ; WindowsUdk::System::Profile::ISystemSettingEntryPoint::Id::get(void)
0x1800b7791  mov     rdi, rax
0x1800b7794  mov     [rsp+2B0h+var_290], rax
0x1800b7799  mov     rdx, [rbp+1B0h+string]
0x1800b77a0  mov     rcx, rax
0x1800b77a3  call    ??8String@Platform@@SA_NPE$AAV01@0@Z; Platform::String::operator==(Platform::String *,Platform::String *)
0x1800b77a8  mov     bl, al
0x1800b77aa  mov     rcx, rdi; string
0x1800b77ad  call    WindowsDeleteString_0
0x1800b77b2  test    bl, bl
0x1800b77b4  jz      loc_1800B7D60
0x1800b77ba  mov     rcx, r14
0x1800b77bd  call    ?get@RequestedUri@IBackgroundTransferOperation@BackgroundTransfer@Networking@Windows@@UE$AAAPE$AAVUri@Foundation@5@XZ; Windows::Networking::BackgroundTransfer::IBackgroundTransferOperation::RequestedUri::get(void)
0x1800b77c2  mov     rbx, rax
0x1800b77c5  mov     [rbp+1B0h+var_1D0], rax
0x1800b77c9  mov     rcx, rax
0x1800b77cc  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800b77d1  mov     rdi, rax
0x1800b77d4  mov     [rsp+2B0h+var_288], rax
0x1800b77d9  mov     rcx, rbx
0x1800b77dc  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b77e1  nop
0x1800b77e2  mov     edx, 0B0h
0x1800b77e7  lea     ecx, [rdx-28h]
0x1800b77ea  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1800b77f0  mov     [rbp+1B0h+var_1C8], rax
0x1800b77f4  mov     rcx, rax
0x1800b77f7  call    ??0?$Vector@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@U?$equal_to@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@@std@@$00@Collections@Platform@@QE$AAA@XZ; Platform::Collections::Vector<Cortana::ConstraintIndex::Search::SettingPath *,std::equal_to<Cortana::ConstraintIndex::Search::SettingPath *>,1>::Vector<Cortana::ConstraintIndex::Search::SettingPath *,std::equal_to<Cortana::ConstraintIndex::Search::SettingPath *>,1>(void)
0x1800b77fc  mov     rbx, rax
0x1800b77ff  mov     [rbp+1B0h+var_1C0], rax
0x1800b7803  mov     rcx, rax
0x1800b7806  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800b780b  mov     rsi, rax
0x1800b780e  mov     [rbp+1B0h+var_230], rax
0x1800b7812  mov     rcx, rbx
0x1800b7815  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b781a  nop
0x1800b781b  mov     rcx, rdi
0x1800b781e  call    ?get@UnconsumedBufferLength@IDataReader@Streams@Storage@Windows@@UE$AAAIXZ; Windows::Storage::Streams::IDataReader::UnconsumedBufferLength::get(void)
0x1800b7823  cmp     eax, 4
0x1800b7826  jnz     loc_1800B7D4F
0x1800b782c  mov     rcx, rdi
0x1800b782f  call    ?GetArray@IJsonValue@Json@Data@Windows@@UE$AAAPE$AAVJsonArray@234@XZ; Windows::Data::Json::IJsonValue::GetArray(void)
0x1800b7834  mov     rbx, rax
0x1800b7837  mov     [rbp+1B0h+var_1B8], rax
0x1800b783b  mov     rcx, rax
0x1800b783e  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800b7843  mov     rdi, rax
0x1800b7846  mov     [rbp+1B0h+var_218], rax
0x1800b784a  mov     rcx, rbx
0x1800b784d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b7852  lea     r8, __uuidof_?AU?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x1800b7859  mov     rdx, rdi
0x1800b785c  xor     ecx, ecx
0x1800b785e  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800b7863  mov     rbx, rax
0x1800b7866  mov     [rbp+1B0h+var_1B0], rax
0x1800b786a  mov     rdx, rax
0x1800b786d  lea     rcx, [rsp+2B0h+var_260]
0x1800b7872  call    ??0?$VectorViewIterator@PE$AAVString@Platform@@@Collections@Platform@@QEAA@PE$AAU?$IVectorView@PE$AAVString@Platform@@@1Foundation@Windows@@@Z; Platform::Collections::VectorViewIterator<Platform::String *>::VectorViewIterator<Platform::String *>(Windows::Foundation::Collections::IVectorView<Platform::String *> *)
0x1800b7877  or      r12d, 8
0x1800b787b  mov     rcx, rbx
0x1800b787e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b7883  lea     r8, __uuidof_?AU?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@
0x1800b788a  mov     rdx, rdi
0x1800b788d  xor     ecx, ecx
0x1800b788f  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800b7894  mov     rbx, rax
0x1800b7897  mov     [rbp+1B0h+var_1A8], rax
0x1800b789b  mov     rdx, rax
0x1800b789e  lea     rcx, [rbp+1B0h+var_48]
0x1800b78a5  call    ??$end@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@YA?AV?$VectorViewIterator@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@0Platform@@PE$AAU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@012@@Z; Windows::Foundation::Collections::end<WindowsUdk::System::Profile::SystemSettingEntryPoint *>(Windows::Foundation::Collections::IVectorView<WindowsUdk::System::Profile::SystemSettingEntryPoint *> *)
0x1800b78aa  nop
0x1800b78ab  mov     rcx, rbx
0x1800b78ae  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800b78b3  mov     rax, [rsp+2B0h+var_258]
0x1800b78b8  cmp     rax, [rbp+1B0h+var_40]
0x1800b78bf  jz      loc_1800B7D08
0x1800b78c5  lea     rdx, [rbp+1B0h+var_A8]
0x1800b78cc  lea     rcx, [rsp+2B0h+var_260]
0x1800b78d1  call    ??D?$VectorIterator@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Platform@@QEBA?AV?$VectorProxy@PE$AAUIJsonValue@Json@Data@Windows@@@Details@12@XZ; Platform::Collections::VectorIterator<Windows::Data::Json::IJsonValue *>::operator*(void)
0x1800b78d6  nop
0x1800b78d7  mov     rcx, rax
0x1800b78da  call    ??D?$VectorViewIterator@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Platform@@QEBAPE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@XZ; Platform::Collections::VectorViewIterator<Cortana::ConstraintIndex::Search::SettingResultItem *>::operator*(void)
0x1800b78df  mov     rbx, rax
0x1800b78e2  mov     [rbp+1B0h+var_1A0], rax
  ... truncated ...
```
