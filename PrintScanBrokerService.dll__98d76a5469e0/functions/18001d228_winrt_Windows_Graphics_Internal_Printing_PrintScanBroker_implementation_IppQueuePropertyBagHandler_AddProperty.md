# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_AddPropertyToValueSet(winrt::Windows::Foundation::Collections::ValueSet &,winrt::hstring const &,winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x18001d228`
- end: `0x18001f4ec`
- name: `?_AddPropertyToValueSet@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXAEAUValueSet@Collections@Foundation@78@AEBUhstring@8@AEBUJsonObject@Json@Data@78@@Z`
- size: `8900`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *__hidden this, struct winrt::Windows::Foundation::Collections::ValueSet *, const struct winrt::hstring *, const struct winrt::Windows::Data::Json::JsonObject *)`
- caller_count: `1`
- callee_count: `89`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f5fc`

## callees

- `0x180002d40`
- `0x180003a00`
- `0x180003a48`
- `0x18000444c`
- `0x180005fd8`
- `0x180006b48`
- `0x180007314`
- `0x180007a58`
- `0x180008838`
- `0x18000fa2c`
- `0x18000fb60`
- `0x1800115a4`
- `0x180013068`
- `0x1800130ec`
- `0x180013170`
- `0x1800131f4`
- `0x180013334`
- `0x1800133e4`
- `0x180013b00`
- `0x180013b38`
- `0x180013c30`
- `0x180013d68`
- `0x180013e70`
- `0x180013fa8`
- `0x1800140e0`
- `0x18001421c`
- `0x18001435c`
- `0x1800154dc`
- `0x180017e6c`
- `0x180018224`
- `0x180018318`
- `0x18001836c`
- `0x1800183b0`
- `0x1800186cc`
- `0x180018ba0`
- `0x1800199a4`
- `0x180019a20`
- `0x180019b10`
- `0x180019b8c`
- `0x180019c00`
- `0x180019c74`
- `0x180019ce8`
- `0x180019d64`
- `0x180019dd8`
- `0x180019e4c`
- `0x180019ec0`
- `0x180019f3c`
- `0x180019fb0`
- `0x18001a02c`
- `0x18001a0a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001d43f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001d9f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001e703`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001eff5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001d43f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001d9f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001e703`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x18001eff5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18001d3ca`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18001f38c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18001d3ca`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18001f38c`

## string_xrefs

- `0x18001f492`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=111
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_AddPropertyToValueSet(
        winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this,
        struct winrt::Windows::Foundation::Collections::ValueSet *a2,
        const struct winrt::hstring *a3,
        const struct winrt::Windows::Data::Json::JsonObject *a4)
{
  int NamedNumber; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  double v16; // xmm0_8
  __int64 Double; // rax
  double v18; // xmm0_8
  __int64 Single; // rax
  winrt::hstring *NamedString; // rax
  const wchar_t *v21; // rax
  __int64 UInt64; // rax
  char16_t *v23; // rcx
  winrt::hstring *v24; // rax
  const wchar_t *v25; // rax
  __int64 Int64; // rax
  __int64 UInt32; // rax
  __int64 Int32; // rax
  __int64 UInt16; // rax
  __int64 Int16; // rax
  __int64 UInt8; // rax
  __int64 Char16; // rax
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  float v40; // xmm8_4
  float v41; // xmm7_4
  unsigned int v42; // xmm6_4
  unsigned int v43; // xmm1_4
  __int64 Rect; // rax
  float v45; // xmm6_4
  float v46; // xmm1_4
  __int64 Size; // rax
  float v48; // xmm6_4
  float v49; // xmm1_4
  __int64 Point; // rax
  __int64 v51; // rax
  __int64 Guid; // rax
  winrt::hstring *v53; // rax
  const wchar_t *v54; // rax
  __int64 v55; // rax
  unsigned int v56; // ebx
  __int64 v57; // rax
  __int64 String; // rax
  __int64 Boolean; // rax
  int v60; // ebx
  int v61; // r14d
  int v62; // eax
  const void *v63; // r12
  void *v64; // r14
  size_t v65; // rbx
  int v66; // r15d
  void (__fastcall ***v67)(_QWORD, __int64 *, __int64 **); // rcx
  int v68; // ebx
  int v69; // r14d
  __int64 v70; // rax
  unsigned int v71; // ecx
  __int64 BooleanArray; // rax
  int v73; // ebx
  int v74; // r14d
  int v75; // eax
  __int64 v76; // rax
  unsigned int v77; // ecx
  __int64 Char16Array; // rax
  _QWORD *v79; // rcx
  _BYTE *v80; // rdx
  __int64 v81; // rdx
  int v82; // r14d
  int v83; // r15d
  unsigned int v84; // ebx
  double v85; // xmm0_8
  __int64 v86; // rax
  unsigned int v87; // ecx
  __int64 DateTimeArray; // rax
  _BYTE *v89; // rdx
  int v90; // ebx
  int v91; // r14d
  double v92; // xmm0_8
  __int64 v93; // rax
  unsigned int v94; // ecx
  __int64 DoubleArray; // rax
  int v96; // ebx
  int v97; // r14d
  __int64 v98; // rax
  __int64 v99; // rax
  unsigned int v100; // ecx
  __int64 GuidArray; // rax
  int v102; // ebx
  int v103; // r14d
  int Number; // eax
  __int64 v105; // rax
  unsigned int v106; // ecx
  __int64 Int16Array; // rax
  int v108; // ebx
  int v109; // r14d
  int v110; // eax
  __int64 v111; // rax
  unsigned int v112; // ecx
  __int64 Int32Array; // rax
  int v114; // ebx
  int v115; // r14d
  winrt::hstring *v116; // rax
  const wchar_t *v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  unsigned int v120; // ecx
  __int64 Int64Array; // rax
  int v122; // ebx
  int v123; // r14d
  __m128 v124; // xmm6
  __m128 v125; // xmm1
  __int64 v126; // rax
  unsigned int v127; // ecx
  __int64 v128; // rax
  int v129; // ebx
  int v130; // r14d
  float v131; // xmm6_4
  float v132; // xmm7_4
  float v133; // xmm8_4
  float v134; // xmm1_4
  _DWORD *v135; // rdx
  __int64 v136; // rax
  unsigned int v137; // ecx
  __int64 v138; // rax
  int v139; // ebx
  int v140; // r14d
  float v141; // xmm1_4
  __int64 v142; // rax
  unsigned int v143; // ecx
  __int64 v144; // rax
  int v145; // ebx
  int v146; // r14d
  __m128 v147; // xmm6
  __m128 v148; // xmm1
  __int64 v149; // rax
  unsigned int v150; // ecx
  __int64 v151; // rax
  int v152; // ebx
  int v153; // r14d
  __int64 *v154; // rax
  _QWORD *v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // rax
  int v158; // ebx
  int v159; // r14d
  winrt::hstring *v160; // rax
  const wchar_t *v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  unsigned int v164; // ecx
  __int64 v165; // rax
  int v166; // ebx
  int v167; // eax
  __int64 v168; // rax
  unsigned int v169; // ecx
  __int64 v170; // rax
  int v171; // ebx
  int v172; // eax
  __int64 v173; // rax
  unsigned int v174; // ecx
  __int64 v175; // rax
  int v176; // ebx
  winrt::hstring *v177; // rax
  const wchar_t *v178; // rax
  unsigned __int64 v179; // rax
  __int64 v180; // rax
  unsigned int v181; // ecx
  __int64 v182; // rax
  unsigned int v183; // eax
  const char *v184; // [rsp+30h] [rbp-D8h]
  char16_t v185[4]; // [rsp+38h] [rbp-D0h] BYREF
  double v186; // [rsp+40h] [rbp-C8h] BYREF
  float pExceptionObject; // [rsp+48h] [rbp-C0h]
  float pExceptionObject_4; // [rsp+4Ch] [rbp-BCh]
  __int128 pExceptionObject_8; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE *v190; // [rsp+60h] [rbp-A8h]
  __int64 v191; // [rsp+68h] [rbp-A0h]
  _OWORD v192[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v193; // [rsp+98h] [rbp-70h] BYREF
  void *Src[2]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE *v195; // [rsp+B8h] [rbp-50h]
  _QWORD v196[4]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v197[4]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v198[4]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v199[4]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v200[32]; // [rsp+148h] [rbp+40h] BYREF
  _OWORD v201[2]; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+200h] [rbp+F8h]

  winrt::param::hstring::hstring((winrt::param::hstring *)v200, L"Type");
  NamedNumber = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                       a4,
                       v200);
  if ( NamedNumber > 1025 )
  {
    switch ( NamedNumber )
    {
      case 1026:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v102 = 0;
        DWORD2(v192[0]) = 0;
        v103 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v102 != v103 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          Number = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v185);
          LOWORD(v193) = Number;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              &v193);
          }
          else
          {
            **((_WORD **)&pExceptionObject_8 + 1) = Number;
            *((_QWORD *)&pExceptionObject_8 + 1) += 2LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v102;
        }
        v105 = winrt::com_array<short>::com_array<short>((__int64)v201, (__int64)&pExceptionObject_8);
        v106 = *(_DWORD *)(v105 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v105;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v106);
        Int16Array = winrt::Windows::Foundation::PropertyValue::CreateInt16Array(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          Int16Array);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
        v79 = (_QWORD *)pExceptionObject_8;
        if ( !(_QWORD)pExceptionObject_8 )
          return;
        v80 = v190;
        goto LABEL_92;
      case 1027:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v199);
        *(_QWORD *)&v192[0] = v185;
        v166 = 0;
        DWORD2(v192[0]) = 0;
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
          v185,
          v201);
        while ( v166 != DWORD2(v201[0]) )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          v167 = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(&v186);
          LOWORD(v193) = v167;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              &v193);
          }
          else
          {
            **((_WORD **)&pExceptionObject_8 + 1) = v167;
            *((_QWORD *)&pExceptionObject_8 + 1) += 2LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v166;
        }
        v168 = winrt::com_array<short>::com_array<short>((__int64)v201, (__int64)&pExceptionObject_8);
        v169 = *(_DWORD *)(v168 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v168;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v169);
        v170 = winrt::Windows::Foundation::PropertyValue::CreateUInt16Array(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v170);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
        std::vector<char16_t>::~vector<char16_t>(&pExceptionObject_8);
        return;
      case 1028:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v108 = 0;
        DWORD2(v192[0]) = 0;
        v109 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v108 != v109 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          v110 = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v185);
          LODWORD(v193) = v110;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              &v193);
          }
          else
          {
            **((_DWORD **)&pExceptionObject_8 + 1) = v110;
            *((_QWORD *)&pExceptionObject_8 + 1) += 4LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v108;
        }
        v111 = winrt::com_array<float>::com_array<float>((__int64)v201, (__int64)&pExceptionObject_8);
        v112 = *(_DWORD *)(v111 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v111;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v112);
        Int32Array = winrt::Windows::Foundation::PropertyValue::CreateInt32Array(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          Int32Array);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
        std::vector<unsigned int>::_Tidy(&pExceptionObject_8);
        return;
      case 1029:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v199);
        *(_QWORD *)&v192[0] = v185;
        v171 = 0;
        DWORD2(v192[0]) = 0;
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
          v185,
          v201);
        while ( v171 != DWORD2(v201[0]) )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          v172 = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(&v186);
          LODWORD(v193) = v172;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              &v193);
          }
          else
          {
            **((_DWORD **)&pExceptionObject_8 + 1) = v172;
            *((_QWORD *)&pExceptionObject_8 + 1) += 4LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v171;
        }
        v173 = winrt::com_array<float>::com_array<float>((__int64)v201, (__int64)&pExceptionObject_8);
        v174 = *(_DWORD *)(v173 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v173;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v174);
        v175 = winrt::Windows::Foundation::PropertyValue::CreateUInt32Array(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v175);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
        goto LABEL_81;
      case 1030:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v114 = 0;
        DWORD2(v192[0]) = 0;
        v115 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v114 != v115 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          v116 = (winrt::hstring *)winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
                                     v185,
                                     &v193);
          v117 = winrt::hstring::c_str(v116);
          v118 = wcstoll(v117, 0, 10);
          v186 = *(double *)&v118;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              &v186);
          }
          else
          {
            **((_QWORD **)&pExceptionObject_8 + 1) = v118;
            *((_QWORD *)&pExceptionObject_8 + 1) += 8LL;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v193);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v114;
        }
        v119 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)&pExceptionObject_8);
        v120 = *(_DWORD *)(v119 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v119;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v120);
        Int64Array = winrt::Windows::Foundation::PropertyValue::CreateInt64Array(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          Int64Array);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
        goto LABEL_154;
      case 1031:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v199);
        *(_QWORD *)&v192[0] = v185;
        v176 = 0;
        DWORD2(v192[0]) = 0;
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
          v185,
          v201);
        while ( v176 != DWORD2(v201[0]) )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          v177 = (winrt::hstring *)winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
                                     &v186,
                                     &v193);
          v178 = winrt::hstring::c_str(v177);
          v179 = wcstoull(v178, 0, 10);
          v196[0] = v179;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              v196);
          }
          else
          {
            **((_QWORD **)&pExceptionObject_8 + 1) = v179;
            *((_QWORD *)&pExceptionObject_8 + 1) += 8LL;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v193);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v176;
        }
        v180 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)&pExceptionObject_8);
        v181 = *(_DWORD *)(v180 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v180;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v181);
        v182 = winrt::Windows::Foundation::PropertyValue::CreateUInt64Array(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v182);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
        std::vector<unsigned __int64>::~vector<unsigned __int64>(&pExceptionObject_8);
        return;
      case 1032:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v199);
        *(_QWORD *)&v192[0] = v185;
        v139 = 0;
        DWORD2(v192[0]) = 0;
        v140 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v185);
        while ( v139 != v140 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          v141 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(&v186);
          *(float *)&v193 = v141;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<float>::_Emplace_reallocate<float>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              &v193);
          }
          else
          {
            **((float **)&pExceptionObject_8 + 1) = v141;
            *((_QWORD *)&pExceptionObject_8 + 1) += 4LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v139;
        }
        v142 = winrt::com_array<float>::com_array<float>((__int64)v201, (__int64)&pExceptionObject_8);
        v143 = *(_DWORD *)(v142 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v142;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v143);
        v144 = winrt::Windows::Foundation::PropertyValue::CreateSingleArray(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v144);
        if ( v186 != 0.0 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v186);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
        v79 = (_QWORD *)pExceptionObject_8;
        if ( !(_QWORD)pExceptionObject_8 )
          return;
        v81 = (unsigned __int64)&v190[-pExceptionObject_8] & 0xFFFFFFFFFFFFFFFCuLL;
        break;
      case 1033:
        *(_OWORD *)Src = 0;
        v195 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v90 = 0;
        DWORD2(v192[0]) = 0;
        v91 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v90 != v91 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          v92 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v185);
          v186 = v92;
          if ( Src[1] == v195 )
          {
            std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
              Src,
              Src[1],
              &v186);
          }
          else
          {
            *(double *)Src[1] = v92;
            Src[1] = (char *)Src[1] + 8;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v90;
        }
        v93 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)Src);
        v94 = *(_DWORD *)(v93 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v93;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v94);
        DoubleArray = winrt::Windows::Foundation::PropertyValue::CreateDoubleArray(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          DoubleArray);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
        goto LABEL_103;
      case 1034:
        *(_OWORD *)Src = 0;
        v195 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v73 = 0;
        DWORD2(v192[0]) = 0;
        v74 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v73 != v74 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          v75 = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v185);
          LOWORD(v193) = v75;
          if ( Src[1] == v195 )
          {
            std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(Src, Src[1], &v193);
          }
          else
          {
            *(_WORD *)Src[1] = v75;
            Src[1] = (char *)Src[1] + 2;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v73;
        }
        v76 = winrt::com_array<short>::com_array<short>((__int64)v201, (__int64)Src);
        v77 = *(_DWORD *)(v76 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v76;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v77);
        Char16Array = winrt::Windows::Foundation::PropertyValue::CreateChar16Array(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          Char16Array);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
        v79 = Src[0];
        if ( !Src[0] )
          return;
        v80 = v195;
LABEL_92:
        v81 = 2 * ((v80 - (_BYTE *)v79) >> 1);
        break;
      case 1035:
        pExceptionObject_8 = 0;
        v190 = 0;
        v191 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v68 = 0;
        DWORD2(v192[0]) = 0;
        v69 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v68 != v69 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          LOBYTE(v193) = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetBoolean(v185);
          v201[0] = *(_OWORD *)std::vector<bool>::end(&pExceptionObject_8, &v186);
          std::vector<bool>::_Insert_n(
            (unsigned int)&pExceptionObject_8,
            (unsigned int)Src,
            (unsigned int)v201,
            1,
            (__int64)&v193);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v68;
        }
        v70 = winrt::com_array<bool>::com_array<bool>((__int64)v201, (unsigned __int64 *)&pExceptionObject_8);
        v71 = *(_DWORD *)(v70 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v70;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v71);
        BooleanArray = winrt::Windows::Foundation::PropertyValue::CreateBooleanArray(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          BooleanArray);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
LABEL_81:
        std::vector<unsigned int>::_Tidy(&pExceptionObject_8);
        return;
      case 1036:
        *(_OWORD *)Src = 0;
        v195 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v199);
        *(_QWORD *)&v192[0] = v185;
        v152 = 0;
        DWORD2(v192[0]) = 0;
        v153 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v185);
        while ( v152 != v153 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          v154 = (__int64 *)winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
                              &v186,
                              v196);
          v155 = Src[1];
          if ( Src[1] == v195 )
          {
            std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(Src, Src[1], v154);
          }
          else
          {
            v156 = *v154;
            *v154 = 0;
            *v155 = v156;
            Src[1] = (char *)Src[1] + 8;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(v196);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v152;
        }
        winrt::com_array<winrt::hstring>::com_array<winrt::hstring>(
          (__int64)v201,
          (struct winrt::impl::hstring_header *)Src[0],
          (winrt::impl **)Src[1]);
        *(_QWORD *)&v192[0] = *(_QWORD *)&v201[0];
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), DWORD2(v201[0]));
        v157 = winrt::Windows::Foundation::PropertyValue::CreateStringArray(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v157);
        if ( v186 != 0.0 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v186);
        winrt::com_array<winrt::hstring>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
        if ( !Src[0] )
          return;
        std::_Destroy_range<winrt::hstring *,winrt::hstring *>(Src[0], Src[1]);
        v79 = Src[0];
LABEL_104:
        v89 = v195;
        goto LABEL_105;
      case 1038:
        *(_OWORD *)Src = 0;
        v195 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          &v193,
          v198);
        *(_QWORD *)&v192[0] = &v193;
        v82 = 0;
        DWORD2(v192[0]) = 0;
        v83 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v193);
        while ( v82 != v83 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
            v185,
            v196);
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"LowPart");
          v84 = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                       v196,
                       v197);
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"HighPart");
          v85 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                  v196,
                  &pExceptionObject_8);
          *(_QWORD *)&v186 = v84 | ((unsigned __int64)(unsigned int)(int)v85 << 32);
          if ( Src[1] == v195 )
          {
            std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
              Src,
              Src[1],
              &v186);
          }
          else
          {
            *(_QWORD *)Src[1] = v84 | ((unsigned __int64)(unsigned int)(int)v85 << 32);
            Src[1] = (char *)Src[1] + 8;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v82;
        }
        v86 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)Src);
        v87 = *(_DWORD *)(v86 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v86;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v87);
        DateTimeArray = winrt::Windows::Foundation::PropertyValue::CreateDateTimeArray(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          DateTimeArray);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v193);
LABEL_103:
        v79 = Src[0];
        if ( Src[0] )
          goto LABEL_104;
        return;
      case 1039:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v199);
        *(_QWORD *)&v192[0] = v185;
        v158 = 0;
        DWORD2(v192[0]) = 0;
        v159 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v185);
        while ( v158 != v159 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          v160 = (winrt::hstring *)winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
                                     &v186,
                                     &v193);
          v161 = winrt::hstring::c_str(v160);
          v162 = wcstoll(v161, 0, 10);
          v196[0] = v162;
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              v196);
          }
          else
          {
            **((_QWORD **)&pExceptionObject_8 + 1) = v162;
            *((_QWORD *)&pExceptionObject_8 + 1) += 8LL;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v193);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v158;
        }
        v163 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)&pExceptionObject_8);
        v164 = *(_DWORD *)(v163 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v163;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v164);
        v165 = winrt::Windows::Foundation::PropertyValue::CreateTimeSpanArray(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v165);
        if ( v186 != 0.0 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v186);
        goto LABEL_164;
      case 1040:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v196,
          v198);
        *(_QWORD *)&v192[0] = v196;
        v96 = 0;
        DWORD2(v192[0]) = 0;
        v97 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
        while ( v96 != v97 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, v185);
          v98 = winrt::impl::consume_Windows_Devices_Printers_IVirtualPrinterSupportedFormat<winrt::Windows::Devices::Printers::IVirtualPrinterSupportedFormat>::MaxSupportedVersion(
                  v185,
                  &v186);
          v193 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(v98, Src);
          winrt::guid::parse<std::basic_string_view<unsigned short>>(v201, &v193);
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<winrt::guid>::_Emplace_reallocate<winrt::guid>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              v201);
          }
          else
          {
            **((_OWORD **)&pExceptionObject_8 + 1) = v201[0];
            *((_QWORD *)&pExceptionObject_8 + 1) += 16LL;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v186);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
          DWORD2(v192[0]) = ++v96;
        }
        v99 = winrt::com_array<winrt::guid>::com_array<winrt::guid>((__int64)v201, (__int64)&pExceptionObject_8);
        v100 = *(_DWORD *)(v99 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v99;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v100);
        GuidArray = winrt::Windows::Foundation::PropertyValue::CreateGuidArray(v185, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          GuidArray);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
        goto LABEL_124;
      case 1041:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v198);
        *(_QWORD *)&v192[0] = v185;
        v122 = 0;
        DWORD2(v192[0]) = 0;
        v123 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v185);
        while ( v122 != v123 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
            &v186,
            &v193);
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Y");
          v124 = 0;
          v124.m128_f32[0] = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                               &v193,
                               v197);
          winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"X");
          v125 = 0;
          v125.m128_f32[0] = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                               &v193,
                               Src);
          v196[0] = __PAIR64__(v124.m128_u32[0], v125.m128_u32[0]);
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<winrt::Windows::Foundation::Size>::_Emplace_reallocate<winrt::Windows::Foundation::Size>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              v196);
          }
          else
          {
            v196[0] = _mm_unpacklo_ps(v125, v124).m128_u64[0];
            **((_QWORD **)&pExceptionObject_8 + 1) = v196[0];
            *((_QWORD *)&pExceptionObject_8 + 1) += 8LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v193);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v122;
        }
        v126 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)&pExceptionObject_8);
        v127 = *(_DWORD *)(v126 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v126;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v127);
        v128 = winrt::Windows::Foundation::PropertyValue::CreatePointArray(&v186, v192);
        v197[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v197,
          v128);
        if ( v186 != 0.0 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v186);
LABEL_164:
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
        goto LABEL_154;
      case 1042:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          &v193,
          v199);
        *(_QWORD *)&v192[0] = &v193;
        v145 = 0;
        DWORD2(v192[0]) = 0;
        v146 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v193);
        while ( v145 != v146 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
            &v186,
            v196);
          winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Height");
          v147 = 0;
          v147.m128_f32[0] = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                               v196,
                               v198);
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Width");
          v148 = 0;
          v148.m128_f32[0] = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                               v196,
                               v197);
          *(_DWORD *)v185 = v148.m128_i32[0];
          *(_DWORD *)&v185[2] = v147.m128_i32[0];
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<winrt::Windows::Foundation::Size>::_Emplace_reallocate<winrt::Windows::Foundation::Size>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              v185);
          }
          else
          {
            *(_QWORD *)v185 = _mm_unpacklo_ps(v148, v147).m128_u64[0];
            **((_QWORD **)&pExceptionObject_8 + 1) = *(_QWORD *)v185;
            *((_QWORD *)&pExceptionObject_8 + 1) += 8LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v145;
        }
        v149 = winrt::com_array<double>::com_array<double>((__int64)v201, (__int64)&pExceptionObject_8);
        v150 = *(_DWORD *)(v149 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v149;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v150);
        v151 = winrt::Windows::Foundation::PropertyValue::CreateSizeArray(&v186, v192);
        v198[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v198,
          v151);
        if ( v186 != 0.0 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v186);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v193);
LABEL_154:
        v79 = (_QWORD *)pExceptionObject_8;
        if ( !(_QWORD)pExceptionObject_8 )
          return;
        v89 = v190;
LABEL_105:
        v81 = (v89 - (_BYTE *)v79) & 0xFFFFFFFFFFFFFFF8uLL;
        break;
      case 1043:
        pExceptionObject_8 = 0;
        v190 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v198, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
          a4,
          v185,
          v198);
        *(_QWORD *)&v192[0] = v185;
        v129 = 0;
        DWORD2(v192[0]) = 0;
        v130 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v185);
        while ( v129 != v130 )
        {
          winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v192, &v186);
          winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
            &v186,
            &v193);
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Height");
          v131 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                   &v193,
                   v197);
          winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"Width");
          v132 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                   &v193,
                   Src);
          winrt::param::hstring::hstring((winrt::param::hstring *)v196, L"Y");
          v133 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                   &v193,
                   v196);
          winrt::param::hstring::hstring((winrt::param::hstring *)v199, L"X");
          v134 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                   &v193,
                   v199);
          *(_QWORD *)&v201[0] = __PAIR64__(LODWORD(v133), LODWORD(v134));
          *((_QWORD *)&v201[0] + 1) = __PAIR64__(LODWORD(v131), LODWORD(v132));
          v135 = (_DWORD *)*((_QWORD *)&pExceptionObject_8 + 1);
          if ( *((_BYTE **)&pExceptionObject_8 + 1) == v190 )
          {
            std::vector<winrt::guid>::_Emplace_reallocate<winrt::guid>(
              &pExceptionObject_8,
              *((_QWORD *)&pExceptionObject_8 + 1),
              v201);
          }
          else
          {
            **((_DWORD **)&pExceptionObject_8 + 1) = LODWORD(v134);
            v135[1] = LODWORD(v133);
            v135[2] = LODWORD(v132);
            v135[3] = LODWORD(v131);
            *((_QWORD *)&pExceptionObject_8 + 1) += 16LL;
          }
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v193);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
          DWORD2(v192[0]) = ++v129;
        }
        v136 = winrt::com_array<winrt::guid>::com_array<winrt::guid>((__int64)v201, (__int64)&pExceptionObject_8);
        v137 = *(_DWORD *)(v136 + 8);
        *(_QWORD *)&v192[0] = *(_QWORD *)v136;
        *((_QWORD *)&v192[0] + 1) = __PAIR64__(HIDWORD(Src[1]), v137);
        v138 = winrt::Windows::Foundation::PropertyValue::CreateRectArray(&v186, v192);
        v199[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v199,
          v138);
        if ( v186 != 0.0 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v186);
        winrt::com_array<short>::clear(v201);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
LABEL_124:
        v79 = (_QWORD *)pExceptionObject_8;
        if ( !(_QWORD)pExceptionObject_8 )
          return;
        v81 = (unsigned __int64)&v190[-pExceptionObject_8] & 0xFFFFFFFFFFFFFFF0uLL;
        break;
      default:
        goto LABEL_234;
    }
    std::_Deallocate<16>(v79, v81);
  }
  else
  {
    if ( NamedNumber != 1025 )
    {
      if ( NamedNumber <= 10 )
      {
        if ( NamedNumber == 10 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
            a4,
            &pExceptionObject_8);
          Char16 = winrt::Windows::Foundation::PropertyValue::CreateChar16((char16_t)v185);
          Src[0] = *(void **)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            Src,
            Char16);
          goto LABEL_59;
        }
        v8 = NamedNumber - 1;
        if ( !v8 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
            a4,
            &pExceptionObject_8);
          UInt8 = winrt::Windows::Foundation::PropertyValue::CreateUInt8((unsigned __int8)v185);
          Src[0] = *(void **)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            Src,
            UInt8);
          goto LABEL_59;
        }
        v9 = v8 - 1;
        if ( !v9 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
            a4,
            &pExceptionObject_8);
          Int16 = winrt::Windows::Foundation::PropertyValue::CreateInt16((__int16)v185);
          Src[0] = *(void **)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            Src,
            Int16);
          goto LABEL_59;
        }
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( !v11 )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
              a4,
              &pExceptionObject_8);
            Int32 = winrt::Windows::Foundation::PropertyValue::CreateInt32((int)v185);
            Src[0] = *(void **)a3;
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
              a2,
              Src,
              Int32);
            goto LABEL_59;
          }
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  if ( v15 == 1 )
                  {
                    winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
                    v16 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                            a4,
                            &pExceptionObject_8);
                    Double = winrt::Windows::Foundation::PropertyValue::CreateDouble(v16);
                    Src[0] = *(void **)a3;
                    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
                      a2,
                      Src,
                      Double);
                    goto LABEL_59;
                  }
LABEL_234:
                  v183 = wil::verify_hresult<long>(2205548546LL);
                  wil::details::in1diag3::Throw_HrMsg(
                    retaddr,
                    (void *)0x239,
                    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
                    (const char *)v183,
                    (int)"Invalid property type in IPP Queue Property Bag!",
                    v184);
                }
                winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
                v18 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                        a4,
                        &pExceptionObject_8);
                Single = winrt::Windows::Foundation::PropertyValue::CreateSingle(*(float *)&v18);
                Src[0] = *(void **)a3;
                winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
                  a2,
                  Src,
                  Single);
LABEL_59:
                if ( *(_QWORD *)v185 )
                  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
                return;
              }
              winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
              NamedString = (winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                                a4,
                                                v185,
                                                &pExceptionObject_8);
              v21 = winrt::hstring::c_str(NamedString);
              wcstoull(v21, 0, 10);
              UInt64 = winrt::Windows::Foundation::PropertyValue::CreateUInt64((unsigned __int64)&v186);
              Src[0] = *(void **)a3;
              winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
                a2,
                Src,
                UInt64);
              winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
              v23 = v185;
LABEL_48:
              winrt::handle_type<winrt::impl::hstring_traits>::close(v23);
              return;
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
            v24 = (winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                      a4,
                                      &v186,
                                      &pExceptionObject_8);
            v25 = winrt::hstring::c_str(v24);
            wcstoll(v25, 0, 10);
            Int64 = winrt::Windows::Foundation::PropertyValue::CreateInt64((__int64)v185);
            Src[0] = *(void **)a3;
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
              a2,
              Src,
              Int64);
            if ( *(_QWORD *)v185 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
LABEL_47:
            v23 = (char16_t *)&v186;
            goto LABEL_48;
          }
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
            a4,
            &pExceptionObject_8);
          UInt32 = winrt::Windows::Foundation::PropertyValue::CreateUInt32((unsigned int)&v186);
          Src[0] = *(void **)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            Src,
            UInt32);
        }
        else
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
            a4,
            &pExceptionObject_8);
          UInt16 = winrt::Windows::Foundation::PropertyValue::CreateUInt16((unsigned __int16)&v186);
          Src[0] = *(void **)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            Src,
            UInt16);
        }
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v186);
        return;
      }
      v33 = NamedNumber - 11;
      if ( !v33 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
          a4,
          v197);
        Boolean = winrt::Windows::Foundation::PropertyValue::CreateBoolean((bool)v185);
        *(_QWORD *)&pExceptionObject_8 = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          &pExceptionObject_8,
          Boolean);
        goto LABEL_59;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
        *(_QWORD *)&pExceptionObject_8 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                                      a4,
                                                      &v186,
                                                      v197);
        String = winrt::Windows::Foundation::PropertyValue::CreateString((const struct winrt::param::hstring *)v185);
        Src[0] = *(void **)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          Src,
          String);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
        goto LABEL_47;
      }
      v35 = v34 - 2;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( !v36 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
          v53 = (winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                    a4,
                                    v196,
                                    v197);
          v54 = winrt::hstring::c_str(v53);
          v186 = COERCE_DOUBLE(wcstoll(v54, 0, 10));
          v55 = winrt::Windows::Foundation::PropertyValue::CreateTimeSpan(v185, &v186);
          *(_QWORD *)&pExceptionObject_8 = *(_QWORD *)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            &pExceptionObject_8,
            v55);
          if ( *(_QWORD *)v185 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
          v23 = (char16_t *)v196;
          goto LABEL_48;
        }
        v37 = v36 - 1;
        if ( !v37 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
          v51 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                  a4,
                  &v186,
                  v197);
          v192[0] = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(v51, v196);
          winrt::guid::parse<std::basic_string_view<unsigned short>>(v201, v192);
          Guid = winrt::Windows::Foundation::PropertyValue::CreateGuid((const struct winrt::guid *)v185);
          *(_QWORD *)&pExceptionObject_8 = *(_QWORD *)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            &pExceptionObject_8,
            Guid);
          if ( *(_QWORD *)v185 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
          goto LABEL_47;
        }
        v38 = v37 - 1;
        if ( v38 )
        {
          v39 = v38 - 1;
          if ( v39 )
          {
            if ( v39 != 1 )
              goto LABEL_234;
            winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Value");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
              a4,
              &v193,
              &pExceptionObject_8);
            winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"Height");
            v40 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                    &v193,
                    Src);
            winrt::param::hstring::hstring((winrt::param::hstring *)v192, L"Width");
            v41 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                    &v193,
                    v192);
            winrt::param::hstring::hstring((winrt::param::hstring *)v201, L"Y");
            *(float *)&v42 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                               &v193,
                               v201);
            winrt::param::hstring::hstring((winrt::param::hstring *)v196, L"X");
            *(float *)&v43 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                               &v193,
                               v196);
            v186 = COERCE_DOUBLE(__PAIR64__(v42, v43));
            pExceptionObject = v41;
            pExceptionObject_4 = v40;
            Rect = winrt::Windows::Foundation::PropertyValue::CreateRect((const struct winrt::Windows::Foundation::Rect *)v185);
            v197[0] = *(_QWORD *)a3;
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
              a2,
              v197,
              Rect);
            if ( *(_QWORD *)v185 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
          }
          else
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
              a4,
              &v193,
              v197);
            winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Height");
            v45 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                    &v193,
                    &pExceptionObject_8);
            winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"Width");
            v46 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                    &v193,
                    Src);
            *(float *)v185 = v46;
            *(float *)&v185[2] = v45;
            Size = winrt::Windows::Foundation::PropertyValue::CreateSize((const struct winrt::Windows::Foundation::Size *)v196);
            *(_QWORD *)&v192[0] = *(_QWORD *)a3;
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
              a2,
              v192,
              Size);
            if ( v196[0] )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v196);
          }
        }
        else
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
            a4,
            &v193,
            v197);
          winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"Y");
          v48 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                  &v193,
                  &pExceptionObject_8);
          winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"X");
          v49 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                  &v193,
                  Src);
          *(float *)v185 = v49;
          *(float *)&v185[2] = v48;
          Point = winrt::Windows::Foundation::PropertyValue::CreatePoint((const struct winrt::Windows::Foundation::Point *)v196);
          *(_QWORD *)&v192[0] = *(_QWORD *)a3;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a2,
            v192,
            Point);
          if ( v196[0] )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v196);
        }
      }
      else
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
          a4,
          &v193,
          v197);
        winrt::param::hstring::hstring((winrt::param::hstring *)&pExceptionObject_8, L"LowPart");
        v56 = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                     &v193,
                     &pExceptionObject_8);
        winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"HighPart");
        *(_QWORD *)&v186 = v56
                         | ((unsigned __int64)(unsigned int)(int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                                                   &v193,
                                                                   Src) << 32);
        v57 = winrt::Windows::Foundation::PropertyValue::CreateDateTime(v185, &v186);
        *(_QWORD *)&v192[0] = *(_QWORD *)a3;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          a2,
          v192,
          v57);
        if ( *(_QWORD *)v185 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v185);
      }
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v193);
      return;
    }
    *(_OWORD *)Src = 0;
    v195 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v197, L"Value");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
      a4,
      v196,
      v197);
    *(_QWORD *)&v201[0] = v196;
    v60 = 0;
    DWORD2(v201[0]) = 0;
    v61 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(v196);
    while ( v60 != v61 )
    {
      winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(v201, v185);
      v62 = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v185);
      LOBYTE(v193) = v62;
      if ( Src[1] == v195 )
        std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(Src, Src[1], &v193);
      else
        *(_BYTE *)Src[1]++ = v62;
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v185);
      DWORD2(v201[0]) = ++v60;
    }
    v63 = Src[0];
    v64 = 0;
    *(_QWORD *)&v201[0] = 0;
    DWORD2(v201[0]) = 0;
    v65 = (char *)Src[1] - (char *)Src[0];
    v66 = 0;
    if ( LODWORD(Src[1]) != LODWORD(Src[0]) )
    {
      v64 = WINRT_IMPL_CoTaskMemAlloc((unsigned int)v65);
      *(_QWORD *)&v201[0] = v64;
      if ( !v64 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject_8);
        throw (std::bad_alloc *)&pExceptionObject_8;
      }
      DWORD2(v201[0]) = v65;
      v66 = v65;
    }
    memmove_0(v64, v63, v65);
    *(_QWORD *)&v192[0] = v64;
    DWORD2(v192[0]) = v66;
    *(_QWORD *)v185 = v192;
    v186 = COERCE_DOUBLE(&qword_180060BE8);
    _InterlockedIncrement64(&qword_180060BE8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> )
    {
      _lambda_5c7d259f10cac4e39ffbc4169655b057_::operator()(
        v185,
        &v193,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
      _InterlockedDecrement64(&qword_180060BE8);
    }
    else
    {
      _InterlockedDecrement64(&qword_180060BE8);
      winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_5c7d259f10cac4e39ffbc4169655b057_ &>(
        v67,
        (__int64)&v193,
        (__int64)v185);
    }
    v198[0] = *(_QWORD *)a3;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      a2,
      v198,
      &v193);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v193);
    winrt::com_array<short>::clear(v201);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v196);
    std::vector<unsigned char>::_Tidy(Src);
  }
}

```

## disassembly

```asm
0x18001d228  mov     rax, rsp
0x18001d22b  mov     [rax+8], rbx
0x18001d22f  push    rbp
0x18001d230  push    rsi
0x18001d231  push    rdi
0x18001d232  push    r12
0x18001d234  push    r13
0x18001d236  push    r14
0x18001d238  push    r15
0x18001d23a  lea     rbp, [rax-0F8h]
0x18001d241  sub     rsp, 1C0h
0x18001d248  movaps  xmmword ptr [rax-48h], xmm6
0x18001d24c  movaps  xmmword ptr [rax-58h], xmm7
0x18001d250  movaps  xmmword ptr [rax-68h], xmm8
0x18001d255  mov     rax, cs:__security_cookie
0x18001d25c  xor     rax, rsp
0x18001d25f  mov     [rbp+0F0h+var_70], rax
0x18001d266  mov     rbx, r9
0x18001d269  mov     rdi, r8
0x18001d26c  mov     rsi, rdx
0x18001d26f  xor     r13d, r13d
0x18001d272  lea     rdx, aType_0; "Type"
0x18001d279  lea     rcx, [rbp+0F0h+var_B0]; this
0x18001d27d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d282  lea     rdx, [rbp+0F0h+var_B0]
0x18001d286  mov     rcx, rbx
0x18001d289  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d28e  cvttsd2si ecx, xmm0
0x18001d292  mov     eax, 401h
0x18001d297  cmp     ecx, eax
0x18001d299  jg      loc_18001DD61
0x18001d29f  jz      loc_18001DBC7
0x18001d2a5  cmp     ecx, 0Ah
0x18001d2a8  jg      loc_18001D676
0x18001d2ae  jz      loc_18001D62D
0x18001d2b4  sub     ecx, 1
0x18001d2b7  jz      loc_18001D5E4
0x18001d2bd  sub     ecx, 1
0x18001d2c0  jz      loc_18001D59B
0x18001d2c6  sub     ecx, 1
0x18001d2c9  jz      loc_18001D514
0x18001d2cf  sub     ecx, 1
0x18001d2d2  jz      loc_18001D4CB
0x18001d2d8  sub     ecx, 1
0x18001d2db  jz      loc_18001D481
0x18001d2e1  sub     ecx, 1
0x18001d2e4  jz      loc_18001D40A
0x18001d2ea  sub     ecx, 1
0x18001d2ed  jz      loc_18001D395
0x18001d2f3  sub     ecx, 1
0x18001d2f6  jz      short loc_18001D349
0x18001d2f8  cmp     ecx, 1
0x18001d2fb  jnz     def_18001DD84; jumptable 000000018001DD84 default case, case 1037
0x18001d301  lea     rdx, aValue; "Value"
0x18001d308  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d30d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d312  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d317  mov     rcx, rbx
0x18001d31a  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d31f  movaps  xmm1, xmm0
0x18001d322  lea     rcx, [rsp+1F0h+var_1C0]
0x18001d327  call    ?CreateDouble@PropertyValue@Foundation@Windows@winrt@@SA@N@Z; winrt::Windows::Foundation::PropertyValue::CreateDouble(double)
0x18001d32c  nop
0x18001d32d  mov     rdx, [rdi]
0x18001d330  mov     [rbp+0F0h+Src], rdx
0x18001d334  mov     r8, rax
0x18001d337  lea     rdx, [rbp+0F0h+Src]
0x18001d33b  mov     rcx, rsi
0x18001d33e  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d343  nop
0x18001d344  jmp     loc_18001DBAD
0x18001d349  lea     rdx, aValue; "Value"
0x18001d350  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d355  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d35a  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d35f  mov     rcx, rbx
0x18001d362  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d367  xorps   xmm1, xmm1
0x18001d36a  cvtsd2ss xmm1, xmm0
0x18001d36e  lea     rcx, [rsp+1F0h+var_1C0]
0x18001d373  call    ?CreateSingle@PropertyValue@Foundation@Windows@winrt@@SA@M@Z; winrt::Windows::Foundation::PropertyValue::CreateSingle(float)
0x18001d378  nop
0x18001d379  mov     rcx, [rdi]
0x18001d37c  mov     [rbp+0F0h+Src], rcx
0x18001d380  mov     r8, rax
0x18001d383  lea     rdx, [rbp+0F0h+Src]
0x18001d387  mov     rcx, rsi
0x18001d38a  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d38f  nop
0x18001d390  jmp     loc_18001DBAD
0x18001d395  lea     rdx, aValue; "Value"
0x18001d39c  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d3a1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d3a6  lea     r8, [rsp+1F0h+pExceptionObject+8]
0x18001d3ab  lea     rdx, [rsp+1F0h+var_1C0]
0x18001d3b0  mov     rcx, rbx
0x18001d3b3  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18001d3b8  nop
0x18001d3b9  mov     rcx, rax; this
0x18001d3bc  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001d3c1  mov     rcx, rax; String
0x18001d3c4  xor     edx, edx; EndPtr
0x18001d3c6  lea     r8d, [rdx+0Ah]; Radix
0x18001d3ca  call    cs:__imp_wcstoull
0x18001d3d0  mov     rdx, rax
0x18001d3d3  lea     rcx, [rsp+1F0h+var_1B8]; unsigned __int64
0x18001d3d8  call    ?CreateUInt64@PropertyValue@Foundation@Windows@winrt@@SA@_K@Z; winrt::Windows::Foundation::PropertyValue::CreateUInt64(unsigned __int64)
0x18001d3dd  nop
0x18001d3de  mov     rcx, [rdi]
0x18001d3e1  mov     [rbp+0F0h+Src], rcx
0x18001d3e5  mov     r8, rax
0x18001d3e8  lea     rdx, [rbp+0F0h+Src]
0x18001d3ec  mov     rcx, rsi
0x18001d3ef  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d3f4  nop
0x18001d3f5  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18001d3fa  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001d3ff  nop
0x18001d400  lea     rcx, [rsp+1F0h+var_1C0]
0x18001d405  jmp     loc_18001D9B8
0x18001d40a  lea     rdx, aValue; "Value"
0x18001d411  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d416  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d41b  lea     r8, [rsp+1F0h+pExceptionObject+8]
0x18001d420  lea     rdx, [rsp+1F0h+var_1B8]
0x18001d425  mov     rcx, rbx
0x18001d428  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18001d42d  nop
0x18001d42e  mov     rcx, rax; this
0x18001d431  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001d436  mov     rcx, rax; String
0x18001d439  xor     edx, edx; EndPtr
0x18001d43b  lea     r8d, [rdx+0Ah]; Radix
0x18001d43f  call    cs:__imp_wcstoll
0x18001d445  mov     rdx, rax
0x18001d448  lea     rcx, [rsp+1F0h+var_1C0]; __int64
0x18001d44d  call    ?CreateInt64@PropertyValue@Foundation@Windows@winrt@@SA@_J@Z; winrt::Windows::Foundation::PropertyValue::CreateInt64(__int64)
0x18001d452  nop
0x18001d453  mov     rcx, [rdi]
0x18001d456  mov     [rbp+0F0h+Src], rcx
0x18001d45a  mov     r8, rax
0x18001d45d  lea     rdx, [rbp+0F0h+Src]
0x18001d461  mov     rcx, rsi
0x18001d464  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d469  nop
0x18001d46a  cmp     qword ptr [rsp+1F0h+var_1C0], r13
0x18001d46f  jz      short loc_18001D47C
0x18001d471  lea     rcx, [rsp+1F0h+var_1C0]
0x18001d476  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d47b  nop
0x18001d47c  jmp     loc_18001D9B3
0x18001d481  lea     rdx, aValue; "Value"
0x18001d488  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d48d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d492  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d497  mov     rcx, rbx
0x18001d49a  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d49f  cvttsd2si rdx, xmm0
0x18001d4a4  lea     rcx, [rsp+1F0h+var_1B8]; unsigned int
0x18001d4a9  call    ?CreateUInt32@PropertyValue@Foundation@Windows@winrt@@SA@I@Z; winrt::Windows::Foundation::PropertyValue::CreateUInt32(uint)
0x18001d4ae  nop
0x18001d4af  mov     rcx, [rdi]
0x18001d4b2  mov     [rbp+0F0h+Src], rcx
0x18001d4b6  mov     r8, rax
0x18001d4b9  lea     rdx, [rbp+0F0h+Src]
0x18001d4bd  mov     rcx, rsi
0x18001d4c0  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d4c5  nop
0x18001d4c6  jmp     loc_18001D558
0x18001d4cb  lea     rdx, aValue; "Value"
0x18001d4d2  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d4d7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d4dc  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d4e1  mov     rcx, rbx
0x18001d4e4  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d4e9  cvttsd2si edx, xmm0
0x18001d4ed  lea     rcx, [rsp+1F0h+var_1C0]; int
0x18001d4f2  call    ?CreateInt32@PropertyValue@Foundation@Windows@winrt@@SA@H@Z; winrt::Windows::Foundation::PropertyValue::CreateInt32(int)
0x18001d4f7  nop
0x18001d4f8  mov     rcx, [rdi]
0x18001d4fb  mov     [rbp+0F0h+Src], rcx
0x18001d4ff  mov     r8, rax
0x18001d502  lea     rdx, [rbp+0F0h+Src]
0x18001d506  mov     rcx, rsi
0x18001d509  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d50e  nop
0x18001d50f  jmp     loc_18001DBAD
0x18001d514  lea     rdx, aValue; "Value"
0x18001d51b  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d520  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d525  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d52a  mov     rcx, rbx
0x18001d52d  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d532  cvttsd2si edx, xmm0
0x18001d536  lea     rcx, [rsp+1F0h+var_1B8]; unsigned __int16
0x18001d53b  call    ?CreateUInt16@PropertyValue@Foundation@Windows@winrt@@SA@G@Z; winrt::Windows::Foundation::PropertyValue::CreateUInt16(ushort)
0x18001d540  nop
0x18001d541  mov     rcx, [rdi]
0x18001d544  mov     [rbp+0F0h+Src], rcx
0x18001d548  mov     r8, rax
0x18001d54b  lea     rdx, [rbp+0F0h+Src]
0x18001d54f  mov     rcx, rsi
0x18001d552  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d557  nop
0x18001d558  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18001d55d  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001d562  mov     rcx, [rbp+0F0h+var_70]
0x18001d569  xor     rcx, rsp; StackCookie
0x18001d56c  call    __security_check_cookie
0x18001d571  lea     r11, [rsp+1F0h+var_30]
0x18001d579  mov     rbx, [r11+40h]
0x18001d57d  movaps  xmm6, xmmword ptr [r11-10h]
0x18001d582  movaps  xmm7, xmmword ptr [r11-20h]
0x18001d587  movaps  xmm8, xmmword ptr [r11-30h]
0x18001d58c  mov     rsp, r11
0x18001d58f  pop     r15
0x18001d591  pop     r14
0x18001d593  pop     r13
0x18001d595  pop     r12
0x18001d597  pop     rdi
0x18001d598  pop     rsi
0x18001d599  pop     rbp
0x18001d59a  retn
0x18001d59b  lea     rdx, aValue; "Value"
0x18001d5a2  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d5a7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d5ac  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d5b1  mov     rcx, rbx
0x18001d5b4  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d5b9  cvttsd2si edx, xmm0
0x18001d5bd  lea     rcx, [rsp+1F0h+var_1C0]; __int16
0x18001d5c2  call    ?CreateInt16@PropertyValue@Foundation@Windows@winrt@@SA@F@Z; winrt::Windows::Foundation::PropertyValue::CreateInt16(short)
0x18001d5c7  nop
0x18001d5c8  mov     rcx, [rdi]
0x18001d5cb  mov     [rbp+0F0h+Src], rcx
0x18001d5cf  mov     r8, rax
0x18001d5d2  lea     rdx, [rbp+0F0h+Src]
0x18001d5d6  mov     rcx, rsi
0x18001d5d9  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d5de  nop
0x18001d5df  jmp     loc_18001DBAD
0x18001d5e4  lea     rdx, aValue; "Value"
0x18001d5eb  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d5f0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d5f5  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d5fa  mov     rcx, rbx
0x18001d5fd  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d602  cvttsd2si edx, xmm0
0x18001d606  lea     rcx, [rsp+1F0h+var_1C0]; unsigned __int8
0x18001d60b  call    ?CreateUInt8@PropertyValue@Foundation@Windows@winrt@@SA@E@Z; winrt::Windows::Foundation::PropertyValue::CreateUInt8(uchar)
0x18001d610  nop
0x18001d611  mov     rcx, [rdi]
0x18001d614  mov     [rbp+0F0h+Src], rcx
0x18001d618  mov     r8, rax
0x18001d61b  lea     rdx, [rbp+0F0h+Src]
0x18001d61f  mov     rcx, rsi
0x18001d622  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d627  nop
0x18001d628  jmp     loc_18001DBAD
0x18001d62d  lea     rdx, aValue; "Value"
0x18001d634  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d639  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d63e  lea     rdx, [rsp+1F0h+pExceptionObject+8]
0x18001d643  mov     rcx, rbx
0x18001d646  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18001d64b  cvttsd2si edx, xmm0
0x18001d64f  lea     rcx, [rsp+1F0h+var_1C0]; char16_t
0x18001d654  call    ?CreateChar16@PropertyValue@Foundation@Windows@winrt@@SA@_S@Z; winrt::Windows::Foundation::PropertyValue::CreateChar16(char16_t)
0x18001d659  nop
0x18001d65a  mov     rcx, [rdi]
0x18001d65d  mov     [rbp+0F0h+Src], rcx
0x18001d661  mov     r8, rax
0x18001d664  lea     rdx, [rbp+0F0h+Src]
0x18001d668  mov     rcx, rsi
0x18001d66b  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18001d670  nop
0x18001d671  jmp     loc_18001DBAD
0x18001d676  sub     ecx, 0Bh
0x18001d679  jz      loc_18001DB6B
0x18001d67f  sub     ecx, 1
0x18001d682  jz      loc_18001DB03
0x18001d688  sub     ecx, 2
0x18001d68b  jz      loc_18001DA43
0x18001d691  sub     ecx, 1
0x18001d694  jz      loc_18001D9C2
0x18001d69a  sub     ecx, 1
0x18001d69d  jz      loc_18001D934
0x18001d6a3  sub     ecx, 1
0x18001d6a6  jz      loc_18001D880
0x18001d6ac  sub     ecx, 1
0x18001d6af  jz      loc_18001D7CC
0x18001d6b5  cmp     ecx, 1
0x18001d6b8  jnz     def_18001DD84; jumptable 000000018001DD84 default case, case 1037
0x18001d6be  lea     rdx, aValue; "Value"
0x18001d6c5  lea     rcx, [rsp+1F0h+pExceptionObject+8]; this
0x18001d6ca  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001d6cf  lea     r8, [rsp+1F0h+pExceptionObject+8]
0x18001d6d4  lea     rdx, [rbp+0F0h+var_160]
0x18001d6d8  mov     rcx, rbx
0x18001d6db  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
  ... truncated ...
```
