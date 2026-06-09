# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_CreateJsonObjectFromProperty(winrt::Windows::Foundation::IPropertyValue const &)

- ea: `0x18001fd3c`
- end: `0x180022504`
- name: `?_CreateJsonObjectFromProperty@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUJsonObject@Json@Data@78@AEBUIPropertyValue@Foundation@78@@Z`
- size: `10184`
- prototype: `struct winrt::Windows::Data::Json::JsonObject __high(const struct winrt::Windows::Foundation::IPropertyValue *)`
- caller_count: `1`
- callee_count: `58`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f93c`

## callees

- `0x180002d40`
- `0x180006b48`
- `0x180007a58`
- `0x18000fa48`
- `0x18000fb60`
- `0x180017d1c`
- `0x180017dc4`
- `0x180018134`
- `0x1800181ac`
- `0x180018224`
- `0x18001867c`
- `0x1800198e8`
- `0x180019a94`
- `0x18001a190`
- `0x18001a69c`
- `0x18001adac`
- `0x18001ae00`
- `0x18001af6c`
- `0x18001afbc`
- `0x18001b0bc`
- `0x18001b110`
- `0x18001b19c`
- `0x18001b1f0`
- `0x18001b340`
- `0x18001b390`
- `0x18001b41c`
- `0x18001b46c`
- `0x18001b4f8`
- `0x18001b54c`
- `0x18001b5d8`
- `0x18001b62c`
- `0x18001b9a4`
- `0x18001b9f4`
- `0x18001bdf4`
- `0x18001be44`
- `0x18001bed0`
- `0x18001bf24`
- `0x18001bfb0`
- `0x18001c000`
- `0x18001c0ec`
- `0x18001c14c`
- `0x18001c1d8`
- `0x18001c264`
- `0x18001c2b4`
- `0x18001c340`
- `0x18001c394`
- `0x18001c420`
- `0x18001c474`
- `0x18001c500`
- `0x18001c550`

## string_xrefs

- `0x180020b5d`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180021f29`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180021f94`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x1800224a9`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=110
struct IUnknown *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_CreateJsonObjectFromProperty(
        __int64 a1,
        struct IUnknown *a2,
        __int64 *a3)
{
  int v5; // ebx
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rbx
  double Double; // xmm0_8
  __int64 v10; // rbx
  __int64 v11; // rbx
  double Single; // xmm0_8
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 UInt64; // rax
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 Int64; // rax
  __int64 v19; // rbx
  __int64 v20; // rbx
  double UInt32; // xmm0_8
  __int64 v22; // rbx
  __int64 v23; // rbx
  double Int32; // xmm0_8
  __int64 v25; // rbx
  __int64 v26; // rbx
  double UInt16; // xmm0_8
  __int64 v28; // rbx
  __int64 v29; // rbx
  double Int16; // xmm0_8
  __int64 v31; // rbx
  __int64 v32; // rbx
  double UInt8; // xmm0_8
  __int64 v34; // rbx
  __int64 v35; // rbx
  double Char16; // xmm0_8
  __int64 v37; // rbx
  __int64 v38; // rbx
  __int64 v39; // rbx
  __int64 v40; // rbx
  __int64 v41; // rbx
  __int64 v42; // rbx
  __int64 v43; // rbx
  __int64 v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rbx
  __int64 v47; // rbx
  __int64 v48; // rbx
  __int64 v49; // rbx
  __int64 Guid; // rax
  __int64 v51; // rbx
  struct IUnknown *v52; // rcx
  __int64 v53; // rbx
  __int64 v54; // rcx
  unsigned int v55; // eax
  __int64 v56; // rbx
  __int64 v57; // rbx
  __int64 v58; // rbx
  __int64 v59; // rbx
  struct IUnknownVtbl *lpVtbl; // rbx
  __int64 QueryInterface_high; // rax
  __int64 v62; // rdi
  __int64 v63; // rbx
  __int64 v64; // rbx
  __int64 v65; // rbx
  __int64 v66; // rdi
  __int64 v67; // r14
  __int64 v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rdi
  __int64 v71; // r14
  __int64 BooleanValue; // rax
  __int64 v73; // rbx
  __int64 v74; // rbx
  __int64 v75; // rdi
  __int64 v76; // rax
  __int64 v77; // rbx
  __int64 v78; // r14
  __int64 v79; // r15
  __int64 v80; // rbx
  __int64 v81; // rbx
  __int64 v82; // rbx
  __int64 v83; // rbx
  __int64 v84; // rdi
  __int64 v85; // rax
  __int64 v86; // rbx
  __int64 v87; // rdi
  __int64 v88; // rbx
  __int64 v89; // rax
  __int64 v90; // rbx
  __int64 v91; // rbx
  __int64 v92; // rdi
  __int64 NumberValue; // rax
  __int64 v94; // rbx
  __int64 v95; // rbx
  __int64 v96; // rdi
  __int64 v97; // rax
  __int64 v98; // rbx
  _QWORD *v99; // rdi
  __int64 v100; // r14
  __int64 StringValue; // rax
  __int64 v102; // rbx
  __int64 v103; // rdi
  __int64 v104; // r14
  __int64 v105; // rbx
  __int64 v106; // rbx
  __int64 v107; // rbx
  __int64 v108; // rdi
  __int64 v109; // r14
  __int64 v110; // rbx
  __int64 v111; // rbx
  __int64 v112; // rbx
  __int64 v113; // rbx
  __int64 v114; // rbx
  __int64 v115; // rbx
  __int64 v116; // rdi
  __int64 v117; // rax
  __int64 v118; // rbx
  __int64 v119; // rdi
  __int64 v120; // r14
  __int64 v121; // rbx
  __int64 v122; // rbx
  unsigned __int64 v123; // r15
  __int64 v124; // rdi
  __int64 v125; // r12
  unsigned int v126; // ecx
  unsigned __int64 v127; // rbx
  __int64 v128; // rax
  __int64 v129; // rbx
  _QWORD *v130; // rdi
  __int64 v131; // r14
  __int64 v132; // rax
  __int64 v133; // rbx
  __int64 v134; // rdi
  __int64 v135; // rax
  __int64 v136; // rbx
  __int64 v137; // rbx
  __int64 v138; // rdi
  __int64 v139; // rax
  _QWORD *v140; // rdi
  __int64 v141; // r14
  __int64 v142; // rax
  __int64 v143; // rbx
  unsigned int v145; // eax
  int v146; // [rsp+20h] [rbp-A9h]
  bool v147[8]; // [rsp+30h] [rbp-99h] BYREF
  struct IUnknown v148; // [rsp+38h] [rbp-91h] BYREF
  struct IUnknown v149; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v150[4]; // [rsp+48h] [rbp-81h] BYREF
  struct IUnknown v151; // [rsp+68h] [rbp-61h] BYREF
  _OWORD v152[2]; // [rsp+70h] [rbp-59h] BYREF
  int v153; // [rsp+90h] [rbp-39h]
  _BYTE v154[16]; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v155[8]; // [rsp+A8h] [rbp-21h] BYREF
  _BYTE v156[16]; // [rsp+B0h] [rbp-19h] BYREF
  struct IUnknown *v157; // [rsp+C0h] [rbp-9h]
  _BYTE v158[24]; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v157 = a2;
  winrt::Windows::Data::Json::JsonObject::JsonObject(a2);
  v5 = 1;
  v153 = 1;
  LODWORD(v151.lpVtbl) = 0;
  v6 = *a3;
  *(_DWORD *)v158 = 0;
  *(_OWORD *)&v158[8] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v6 + 48LL))(v6, &v151);
  winrt::check_hresult(&v149, v7, v158);
  if ( SLODWORD(v151.lpVtbl) > 1025 )
  {
    switch ( LODWORD(v151.lpVtbl) )
    {
      case 0x402:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt16Array(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
        v91 = *(_QWORD *)&v152[0];
        v92 = *(_QWORD *)&v152[0] + 2LL * DWORD2(v152[0]);
        while ( v91 != v92 )
        {
          NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v149,
            NumberValue);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          v91 += 2;
        }
        v94 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v94);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v149.lpVtbl )
          goto LABEL_111;
        v148.lpVtbl = 0;
        goto LABEL_112;
      case 0x403:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt16Array(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v133 = *(_QWORD *)v158;
        v134 = *(_QWORD *)v158 + 2LL * *(unsigned int *)&v158[8];
        while ( v133 != v134 )
        {
          v135 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            v135);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          v133 += 2;
        }
        goto LABEL_158;
      case 0x404:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt32Array(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
        v95 = *(_QWORD *)&v152[0];
        v96 = *(_QWORD *)&v152[0] + 4LL * DWORD2(v152[0]);
        while ( v95 != v96 )
        {
          v97 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v149,
            v97);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          v95 += 4;
        }
        v98 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v98);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v149.lpVtbl )
          goto LABEL_111;
        v148.lpVtbl = 0;
        goto LABEL_112;
      case 0x405:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt32Array(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v137 = *(_QWORD *)v158;
        v138 = *(_QWORD *)v158 + 4LL * *(unsigned int *)&v158[8];
        while ( v137 != v138 )
        {
          v139 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            v139);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          v137 += 4;
        }
LABEL_158:
        v136 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v136);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
        winrt::impl::require_one<winrt::Windows::Data::Json::IJsonObject,winrt::Windows::Data::Json::IJsonValue>::operator winrt::Windows::Data::Json::IJsonValue(
          &v148,
          v147);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v147);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::com_array<short>::clear(v158);
        return a2;
      case 0x406:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt64Array(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
        v99 = *(_QWORD **)&v152[0];
        v100 = *(_QWORD *)&v152[0] + 8LL * DWORD2(v152[0]);
        while ( v99 != (_QWORD *)v100 )
        {
          winrt::impl::hstring_convert<__int64>(v147, *v99);
          v5 |= 4u;
          v153 = v5;
          v150[0] = *(_QWORD *)v147;
          StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v154);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v149,
            StringValue);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v147);
          ++v99;
        }
        v102 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v102);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v149.lpVtbl )
          goto LABEL_111;
        v148.lpVtbl = 0;
        goto LABEL_112;
      case 0x407:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt64Array(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v140 = *(_QWORD **)v158;
        v141 = *(_QWORD *)v158 + 8LL * *(unsigned int *)&v158[8];
        while ( v140 != (_QWORD *)v141 )
        {
          winrt::impl::hstring_convert<unsigned __int64>(v147, *v140);
          v5 |= 0x40u;
          v153 = v5;
          v150[0] = *(_QWORD *)v147;
          v142 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v152);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            v142);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v147);
          ++v140;
        }
        goto LABEL_166;
      case 0x408:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetSingleArray(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
        v115 = *(_QWORD *)v158;
        v116 = *(_QWORD *)v158 + 4LL * *(unsigned int *)&v158[8];
        while ( v115 != v116 )
        {
          v117 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v149,
            v117);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          v115 += 4;
        }
        v118 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v118);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
        if ( v149.lpVtbl )
        {
          *(_QWORD *)v147 = 0;
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v149.lpVtbl->QueryInterface)(
            v149.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            v147);
          v148.lpVtbl = *(struct IUnknownVtbl **)v147;
        }
        else
        {
          v148.lpVtbl = 0;
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          &v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
        winrt::com_array<short>::clear(v158);
        return a2;
      case 0x409:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetDoubleArray(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
        v83 = *(_QWORD *)&v152[0];
        v84 = *(_QWORD *)&v152[0] + 8LL * DWORD2(v152[0]);
        while ( v83 != v84 )
        {
          v85 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v149,
            v85);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          v83 += 8;
        }
        v86 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v86);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v149.lpVtbl )
          goto LABEL_111;
        v148.lpVtbl = 0;
        goto LABEL_112;
      case 0x40A:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetChar16Array(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v151);
        v74 = *(_QWORD *)&v152[0];
        v75 = *(_QWORD *)&v152[0] + 2LL * DWORD2(v152[0]);
        while ( v74 != v75 )
        {
          v76 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v151,
            v76);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          v74 += 2;
        }
        v77 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v77);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        if ( v151.lpVtbl )
          goto LABEL_64;
        v149.lpVtbl = 0;
        goto LABEL_65;
      case 0x40B:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetBooleanArray(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v151);
        v70 = *(_QWORD *)&v152[0];
        v71 = *(_QWORD *)&v152[0] + DWORD2(v152[0]);
        while ( v70 != v71 )
        {
          BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v147);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v151,
            BooleanValue);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          ++v70;
        }
        v73 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v73);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        if ( v151.lpVtbl )
        {
LABEL_64:
          v148.lpVtbl = 0;
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, struct IUnknown *))v151.lpVtbl->QueryInterface)(
            v151.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            &v148);
          v149.lpVtbl = v148.lpVtbl;
        }
        else
        {
          v149.lpVtbl = 0;
        }
LABEL_65:
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          &v149);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v151);
        winrt::com_array<short>::clear(v152);
        return a2;
      case 0x40C:
        v123 = 0;
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetStringArray(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v124 = *(_QWORD *)v158;
        v125 = *(_QWORD *)v158 + 8LL * *(unsigned int *)&v158[8];
        while ( v124 != v125 )
        {
          if ( *(_QWORD *)v124 )
            v126 = *(_DWORD *)(*(_QWORD *)v124 + 4LL);
          else
            v126 = 0;
          v127 = 2LL * v126;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x358,
            (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
            (const char *)0x80070057LL,
            v127 > 0x2800,
            (bool)"String in array property exceeds the maximum allowed size of 10KB!",
            *(const char **)v147);
          v123 += v127;
          v150[0] = *(_QWORD *)v124;
          v128 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v152);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            v128);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          v124 += 8;
        }
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x35E,
          (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
          (const char *)0x80070057LL,
          v123 > 0x2800,
          (bool)"Total size of strings in array exceeds the maximum allowed size of 10KB!",
          *(const char **)v147);
        v129 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v129);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
        winrt::impl::require_one<winrt::Windows::Data::Json::IJsonObject,winrt::Windows::Data::Json::IJsonValue>::operator winrt::Windows::Data::Json::IJsonValue(
          &v148,
          v147);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v147);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::com_array<winrt::hstring>::clear(v158);
        return a2;
      case 0x40E:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetDateTimeArray(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v78 = *(_QWORD *)&v152[0];
        v79 = *(_QWORD *)&v152[0] + 8LL * DWORD2(v152[0]);
        while ( v78 != v79 )
        {
          winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
          v80 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"LowPart");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v80);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v155);
          v81 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"HighPart");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v81);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          if ( v149.lpVtbl )
          {
            *(_QWORD *)v147 = 0;
            (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v149.lpVtbl->QueryInterface)(
              v149.lpVtbl,
              winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
              v147);
            v151.lpVtbl = *(struct IUnknownVtbl **)v147;
          }
          else
          {
            v151.lpVtbl = 0;
          }
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            &v151);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v151);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
          v78 += 8;
        }
        v82 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v82);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v148.lpVtbl )
        {
          *(_QWORD *)v147 = 0;
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v148.lpVtbl->QueryInterface)(
            v148.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            v147);
          v149.lpVtbl = *(struct IUnknownVtbl **)v147;
        }
        else
        {
          v149.lpVtbl = 0;
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          &v149);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::com_array<short>::clear(v152);
        return a2;
      case 0x40F:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetTimeSpanArray(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v130 = *(_QWORD **)v158;
        v131 = *(_QWORD *)v158 + 8LL * *(unsigned int *)&v158[8];
        while ( v130 != (_QWORD *)v131 )
        {
          winrt::impl::hstring_convert<__int64>(v147, *v130);
          v5 |= 0x10u;
          v153 = v5;
          v150[0] = *(_QWORD *)v147;
          v132 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v152);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            v132);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v147);
          ++v130;
        }
        goto LABEL_166;
      case 0x410:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetGuidArray(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
        v87 = *(_QWORD *)&v152[0];
        v88 = *(_QWORD *)&v152[0] + 16LL * DWORD2(v152[0]);
        while ( v87 != v88 )
        {
          v150[0] = *(_QWORD *)winrt::to_hstring(v155, v87);
          v89 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v154);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v149,
            v89);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v155);
          v87 += 16;
        }
        v90 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v90);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v149.lpVtbl )
        {
LABEL_111:
          *(_QWORD *)v147 = 0;
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v149.lpVtbl->QueryInterface)(
            v149.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            v147);
          v148.lpVtbl = *(struct IUnknownVtbl **)v147;
        }
        else
        {
          v148.lpVtbl = 0;
        }
LABEL_112:
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          &v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
        winrt::com_array<short>::clear(v152);
        return a2;
      case 0x411:
        v152[0] = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetPointArray(
          a3,
          v152);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v151);
        v103 = *(_QWORD *)&v152[0];
        v104 = *(_QWORD *)&v152[0] + 8LL * DWORD2(v152[0]);
        while ( v103 != v104 )
        {
          winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
          v105 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"X");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v105);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          v106 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Y");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v106);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v155);
          if ( v149.lpVtbl )
          {
            *(_QWORD *)v147 = 0;
            (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v149.lpVtbl->QueryInterface)(
              v149.lpVtbl,
              winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
              v147);
            v148.lpVtbl = *(struct IUnknownVtbl **)v147;
          }
          else
          {
            v148.lpVtbl = 0;
          }
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v151,
            &v148);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
          v103 += 8;
        }
        v107 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v107);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
        if ( v151.lpVtbl )
        {
          *(_QWORD *)v147 = 0;
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v151.lpVtbl->QueryInterface)(
            v151.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            v147);
          v148.lpVtbl = *(struct IUnknownVtbl **)v147;
        }
        else
        {
          v148.lpVtbl = 0;
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          &v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v151);
        winrt::com_array<short>::clear(v152);
        return a2;
      case 0x412:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetSizeArray(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v148);
        v119 = *(_QWORD *)v158;
        v120 = *(_QWORD *)v158 + 8LL * *(unsigned int *)&v158[8];
        while ( v119 != v120 )
        {
          winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
          v121 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Height");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v121);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          v122 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Width");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v122);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v156);
          winrt::impl::require_one<winrt::Windows::Data::Json::IJsonObject,winrt::Windows::Data::Json::IJsonValue>::operator winrt::Windows::Data::Json::IJsonValue(
            &v149,
            v147);
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v148,
            v147);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
          v119 += 8;
        }
LABEL_166:
        v143 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v143);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
        winrt::impl::require_one<winrt::Windows::Data::Json::IJsonObject,winrt::Windows::Data::Json::IJsonValue>::operator winrt::Windows::Data::Json::IJsonValue(
          &v148,
          v147);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v147);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::com_array<short>::clear(v158);
        return a2;
      case 0x413:
        *(_OWORD *)v158 = 0u;
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetRectArray(
          a3,
          v158);
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v151);
        v108 = *(_QWORD *)v158;
        v109 = *(_QWORD *)v158 + 16LL * *(unsigned int *)&v158[8];
        while ( v108 != v109 )
        {
          winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
          v110 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Height");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v110);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v154);
          v111 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Width");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v111);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v155);
          v112 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"X");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v112);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v156);
          v113 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Y");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v149,
            v150,
            v113);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
          if ( v149.lpVtbl )
          {
            *(_QWORD *)v147 = 0;
            (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v149.lpVtbl->QueryInterface)(
              v149.lpVtbl,
              winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
              v147);
            v148.lpVtbl = *(struct IUnknownVtbl **)v147;
          }
          else
          {
            v148.lpVtbl = 0;
          }
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v151,
            &v148);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
          v108 += 16;
        }
        v114 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v114);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v152);
        if ( v151.lpVtbl )
        {
          *(_QWORD *)v147 = 0;
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, bool *))v151.lpVtbl->QueryInterface)(
            v151.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            v147);
          v148.lpVtbl = *(struct IUnknownVtbl **)v147;
        }
        else
        {
          v148.lpVtbl = 0;
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          &v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v151);
        winrt::com_array<short>::clear(v158);
        return a2;
      default:
        goto LABEL_168;
    }
  }
  if ( LODWORD(v151.lpVtbl) != 1025 )
  {
    if ( SLODWORD(v151.lpVtbl) <= 10 )
    {
      switch ( LODWORD(v151.lpVtbl) )
      {
        case 0xA:
          v35 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v35);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          Char16 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetChar16(a3);
          v37 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(Char16);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v37);
          goto LABEL_53;
        case 1:
          v32 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v32);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          UInt8 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt8(a3);
          v34 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(UInt8);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v34);
          goto LABEL_53;
        case 2:
          v29 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v29);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          Int16 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt16(a3);
          v31 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(Int16);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v31);
          goto LABEL_53;
        case 3:
          v26 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v26);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          UInt16 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt16(a3);
          v28 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(UInt16);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v28);
          goto LABEL_53;
        case 4:
          v23 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v23);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          Int32 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt32(a3);
          v25 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(Int32);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v25);
          goto LABEL_53;
        case 5:
          v20 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v20);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          UInt32 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt32(a3);
          v22 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(UInt32);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v22);
          goto LABEL_53;
        case 6:
          v17 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v17);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          Int64 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt64(a3);
          winrt::impl::hstring_convert<__int64>(&v148, Int64);
          v153 = 3;
          *(struct IUnknown *)v158 = v148;
          v19 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v147);
          winrt::param::hstring::hstring((winrt::param::hstring *)v152, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v152,
            v19);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          break;
        case 7:
          v14 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v14);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          UInt64 = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt64(a3);
          winrt::impl::hstring_convert<unsigned __int64>(&v148, UInt64);
          v153 = 33;
          *(struct IUnknown *)v158 = v148;
          v16 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v147);
          winrt::param::hstring::hstring((winrt::param::hstring *)v152, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v152,
            v16);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          break;
        case 8:
          v11 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v11);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          Single = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetSingle(a3);
          v13 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(Single);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v13);
          goto LABEL_53;
        case 9:
          v8 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Type");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v8);
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          Double = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetDouble(a3);
          v10 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(Double);
          winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            a2,
            v158,
            v10);
LABEL_53:
          winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
          return a2;
        default:
LABEL_168:
          v145 = wil::verify_hresult<long>(2205548546LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3C8,
            (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
            (const char *)v145,
            v146);
      }
      goto LABEL_40;
    }
    switch ( LODWORD(v151.lpVtbl) )
    {
      case 0xB:
        v64 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v64);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetBoolean(a3);
        v65 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v147);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v65);
        goto LABEL_53;
      case 0xC:
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
          a3,
          &v148);
        lpVtbl = v148.lpVtbl;
        if ( v148.lpVtbl )
          QueryInterface_high = HIDWORD(v148.lpVtbl->QueryInterface);
        else
          QueryInterface_high = 0;
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x34A,
          (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
          (const char *)0x80070057LL,
          (unsigned __int64)(2 * QueryInterface_high) > 0x2800,
          (bool)"String property size exceeds the maximum allowed size of 10KB!",
          *(const char **)v147);
        v62 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v62);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        v150[0] = lpVtbl;
        v63 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v149);
        winrt::param::hstring::hstring((winrt::param::hstring *)v158, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v158,
          v63);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
        break;
      case 0xE:
        winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetDateTime(
          a3,
          v152);
        v57 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"LowPart");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          &v149,
          v150,
          v57);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        v58 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"HighPart");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          &v149,
          v150,
          v58);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        v59 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v59);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        if ( !v149.lpVtbl )
        {
          v151.lpVtbl = 0;
          goto LABEL_46;
        }
        goto LABEL_45;
      case 0xF:
        v53 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v53);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        v148.lpVtbl = 0;
        v54 = *a3;
        *(_DWORD *)v158 = 0;
        *(_OWORD *)&v158[8] = 0;
        v55 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v54 + 176LL))(v54, &v148);
        winrt::check_hresult(&v149, v55, v158);
        winrt::impl::hstring_convert<__int64>(&v149, v148.lpVtbl);
        v153 = 9;
        v150[0] = v149.lpVtbl;
        v56 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v147);
        winrt::param::hstring::hstring((winrt::param::hstring *)v152, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v152,
          v56);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        v52 = &v149;
        goto LABEL_41;
      case 0x10:
        v49 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
        winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v150,
          v49);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        Guid = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetGuid(
                 a3,
                 v158);
        v150[0] = *(_QWORD *)winrt::to_hstring(&v148, Guid);
        v51 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v147);
        winrt::param::hstring::hstring((winrt::param::hstring *)v152, L"Value");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v152,
          v51);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
        break;
      default:
        switch ( LODWORD(v151.lpVtbl) )
        {
          case 0x11:
            winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetPoint(
              a3,
              v152);
            v46 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"X");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v46);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetPoint(
              a3,
              v156);
            v47 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Y");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v47);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            v48 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              a2,
              v150,
              v48);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
            if ( !v149.lpVtbl )
            {
              v151.lpVtbl = 0;
              goto LABEL_46;
            }
            break;
          case 0x12:
            winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetSize(
              a3,
              v152);
            v43 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Height");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v43);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetSize(
              a3,
              v156);
            v44 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Width");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v44);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            v45 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              a2,
              v150,
              v45);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
            winrt::impl::require_one<winrt::Windows::Data::Json::IJsonObject,winrt::Windows::Data::Json::IJsonValue>::operator winrt::Windows::Data::Json::IJsonValue(
              &v149,
              &v148);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              a2,
              v150,
              &v148);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
LABEL_47:
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
            return a2;
          case 0x13:
            winrt::Windows::Data::Json::JsonObject::JsonObject(&v149);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetRect(
              a3,
              v158);
            v38 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Height");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v38);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetRect(
              a3,
              v152);
            v39 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Width");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v39);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetRect(
              a3,
              v156);
            v40 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"X");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v40);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetRect(
              a3,
              v154);
            v41 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Y");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              &v149,
              v150,
              v41);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
            v42 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
            winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
            winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
              a2,
              v150,
              v42);
            winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
            if ( !v149.lpVtbl )
            {
              v151.lpVtbl = 0;
LABEL_46:
              winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                a2,
                v150,
                &v151);
              winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v151);
              goto LABEL_47;
            }
            break;
          default:
            goto LABEL_168;
        }
LABEL_45:
        v148.lpVtbl = 0;
        (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, struct IUnknown *))v149.lpVtbl->QueryInterface)(
          v149.lpVtbl,
          winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
          &v148);
        v151.lpVtbl = v148.lpVtbl;
        goto LABEL_46;
    }
LABEL_40:
    v52 = &v148;
LABEL_41:
    winrt::handle_type<winrt::impl::hstring_traits>::close(v52);
    return a2;
  }
  v152[0] = 0u;
  winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt8Array(
    a3,
    v152);
  winrt::Windows::Data::Json::JsonArray::JsonArray(&v149);
  v66 = *(_QWORD *)&v152[0];
  v67 = *(_QWORD *)&v152[0] + DWORD2(v152[0]);
  while ( v66 != v67 )
  {
    v68 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
      &v149,
      v68);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
    ++v66;
  }
  v69 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
  winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Type");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    v150,
    v69);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v147);
  winrt::impl::require_one<winrt::Windows::Data::Json::IJsonObject,winrt::Windows::Data::Json::IJsonValue>::operator winrt::Windows::Data::Json::IJsonValue(
    &v149,
    &v148);
  winrt::param::hstring::hstring((winrt::param::hstring *)v150, L"Value");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    v150,
    &v148);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v148);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v149);
  winrt::com_array<short>::clear(v152);
  return a2;
}

```

## disassembly

```asm
0x18001fd3c  mov     [rsp-8+arg_0], rbx
0x18001fd41  push    rbp
0x18001fd42  push    rsi
0x18001fd43  push    rdi
0x18001fd44  push    r12
0x18001fd46  push    r13
0x18001fd48  push    r14
0x18001fd4a  push    r15
0x18001fd4c  lea     rbp, [rsp-27h]
0x18001fd51  sub     rsp, 0F0h
0x18001fd58  mov     rax, cs:__security_cookie
0x18001fd5f  xor     rax, rsp
0x18001fd62  mov     [rbp+57h+var_38], rax
0x18001fd66  mov     rdi, r8
0x18001fd69  mov     rsi, rdx
0x18001fd6c  mov     [rbp+57h+var_60], rdx
0x18001fd70  xor     r13d, r13d
0x18001fd73  mov     [rbp+57h+var_90], r13d
0x18001fd77  mov     rcx, rdx; this
0x18001fd7a  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18001fd7f  lea     ebx, [r13+1]
0x18001fd83  mov     [rbp+57h+var_90], ebx
0x18001fd86  mov     dword ptr [rbp+57h+var_B8], r13d
0x18001fd8a  mov     rcx, [rdi]
0x18001fd8d  mov     dword ptr [rbp+57h+var_58], r13d
0x18001fd91  xorps   xmm0, xmm0
0x18001fd94  movdqu  [rbp+57h+var_58+8], xmm0
0x18001fd99  mov     rax, [rcx]
0x18001fd9c  lea     rdx, [rbp+57h+var_B8]
0x18001fda0  mov     rax, [rax+30h]
0x18001fda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fda9  lea     r8, [rbp+57h+var_58]
0x18001fdad  mov     edx, eax
0x18001fdaf  lea     rcx, [rsp+120h+var_E0]
0x18001fdb4  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001fdb9  mov     ecx, dword ptr [rbp+57h+var_B8]
0x18001fdbc  mov     eax, 401h
0x18001fdc1  cmp     ecx, eax
0x18001fdc3  jg      loc_180020D7C
0x18001fdc9  jz      loc_180020C7F
0x18001fdcf  cmp     ecx, 0Ah
0x18001fdd2  jg      loc_180020380
0x18001fdd8  jz      loc_1800202FC
0x18001fdde  sub     ecx, ebx
0x18001fde0  jz      loc_180020278
0x18001fde6  sub     ecx, ebx
0x18001fde8  jz      loc_1800201F4
0x18001fdee  sub     ecx, ebx
0x18001fdf0  jz      loc_180020170
0x18001fdf6  sub     ecx, ebx
0x18001fdf8  jz      loc_1800200EF
0x18001fdfe  sub     ecx, ebx
0x18001fe00  jz      loc_18002006C
0x18001fe06  sub     ecx, ebx
0x18001fe08  jz      loc_18001FFC7
0x18001fe0e  sub     ecx, ebx
0x18001fe10  jz      loc_18001FF22
0x18001fe16  sub     ecx, ebx
0x18001fe18  jz      loc_18001FEA2
0x18001fe1e  cmp     ecx, ebx
0x18001fe20  jnz     def_180020D9F; jumptable 0000000180020D9F default case, case 1037
0x18001fe26  movsd   xmm1, cs:__real@4022000000000000
0x18001fe2e  lea     rcx, [rsp+120h+var_F0]
0x18001fe33  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001fe38  mov     rbx, rax
0x18001fe3b  lea     rdx, aType_0; "Type"
0x18001fe42  lea     rcx, [rbp+57h+var_58]; this
0x18001fe46  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001fe4b  mov     r8, rbx
0x18001fe4e  lea     rdx, [rbp+57h+var_58]
0x18001fe52  mov     rcx, rsi
0x18001fe55  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fe5a  nop
0x18001fe5b  lea     rcx, [rsp+120h+var_F0]; this
0x18001fe60  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fe65  mov     rcx, rdi
0x18001fe68  call    ?GetDouble@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetDouble(void)
0x18001fe6d  movaps  xmm1, xmm0
0x18001fe70  lea     rcx, [rsp+120h+var_F0]
0x18001fe75  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001fe7a  mov     rbx, rax
0x18001fe7d  lea     rdx, aValue; "Value"
0x18001fe84  lea     rcx, [rbp+57h+var_58]; this
0x18001fe88  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001fe8d  mov     r8, rbx
0x18001fe90  lea     rdx, [rbp+57h+var_58]
0x18001fe94  mov     rcx, rsi
0x18001fe97  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fe9c  nop
0x18001fe9d  jmp     loc_180020C70
0x18001fea2  movsd   xmm1, cs:__real@4020000000000000
0x18001feaa  lea     rcx, [rsp+120h+var_F0]
0x18001feaf  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001feb4  mov     rbx, rax
0x18001feb7  lea     rdx, aType_0; "Type"
0x18001febe  lea     rcx, [rbp+57h+var_58]; this
0x18001fec2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001fec7  mov     r8, rbx
0x18001feca  lea     rdx, [rbp+57h+var_58]
0x18001fece  mov     rcx, rsi
0x18001fed1  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fed6  nop
0x18001fed7  lea     rcx, [rsp+120h+var_F0]; this
0x18001fedc  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fee1  mov     rcx, rdi
0x18001fee4  call    ?GetSingle@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetSingle(void)
0x18001fee9  xorps   xmm1, xmm1
0x18001feec  cvtss2sd xmm1, xmm0
0x18001fef0  lea     rcx, [rsp+120h+var_F0]
0x18001fef5  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001fefa  mov     rbx, rax
0x18001fefd  lea     rdx, aValue; "Value"
0x18001ff04  lea     rcx, [rbp+57h+var_58]; this
0x18001ff08  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001ff0d  mov     r8, rbx
0x18001ff10  lea     rdx, [rbp+57h+var_58]
0x18001ff14  mov     rcx, rsi
0x18001ff17  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001ff1c  nop
0x18001ff1d  jmp     loc_180020C70
0x18001ff22  movsd   xmm1, cs:__real@401c000000000000
0x18001ff2a  lea     rcx, [rsp+120h+var_F0]
0x18001ff2f  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001ff34  mov     rbx, rax
0x18001ff37  lea     rdx, aType_0; "Type"
0x18001ff3e  lea     rcx, [rbp+57h+var_58]; this
0x18001ff42  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001ff47  mov     r8, rbx
0x18001ff4a  lea     rdx, [rbp+57h+var_58]
0x18001ff4e  mov     rcx, rsi
0x18001ff51  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001ff56  nop
0x18001ff57  lea     rcx, [rsp+120h+var_F0]; this
0x18001ff5c  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001ff61  mov     rcx, rdi
0x18001ff64  call    ?GetUInt64@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt64(void)
0x18001ff69  mov     rdx, rax
0x18001ff6c  lea     rcx, [rsp+120h+var_E8]
0x18001ff71  call    ??$hstring_convert@_K@impl@winrt@@YA?AUhstring@1@_K@Z; winrt::impl::hstring_convert<unsigned __int64>(unsigned __int64)
0x18001ff76  mov     [rbp+57h+var_90], 21h ; '!'
0x18001ff7d  mov     rax, [rsp+120h+var_E8]
0x18001ff82  mov     qword ptr [rbp+57h+var_58], rax
0x18001ff86  lea     rdx, [rbp+57h+var_58]
0x18001ff8a  lea     rcx, [rsp+120h+var_F0]; struct winrt::param::hstring *
0x18001ff8f  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18001ff94  mov     rbx, rax
0x18001ff97  lea     rdx, aValue; "Value"
0x18001ff9e  lea     rcx, [rbp+57h+var_B0]; this
0x18001ffa2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001ffa7  mov     r8, rbx
0x18001ffaa  lea     rdx, [rbp+57h+var_B0]
0x18001ffae  mov     rcx, rsi
0x18001ffb1  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001ffb6  nop
0x18001ffb7  lea     rcx, [rsp+120h+var_F0]; this
0x18001ffbc  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001ffc1  nop
0x18001ffc2  jmp     loc_1800208CD
0x18001ffc7  movsd   xmm1, cs:__real@4018000000000000
0x18001ffcf  lea     rcx, [rsp+120h+var_F0]
0x18001ffd4  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18001ffd9  mov     rbx, rax
0x18001ffdc  lea     rdx, aType_0; "Type"
0x18001ffe3  lea     rcx, [rbp+57h+var_58]; this
0x18001ffe7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001ffec  mov     r8, rbx
0x18001ffef  lea     rdx, [rbp+57h+var_58]
0x18001fff3  mov     rcx, rsi
0x18001fff6  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001fffb  nop
0x18001fffc  lea     rcx, [rsp+120h+var_F0]; this
0x180020001  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180020006  mov     rcx, rdi
0x180020009  call    ?GetInt64@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt64(void)
0x18002000e  mov     rdx, rax
0x180020011  lea     rcx, [rsp+120h+var_E8]
0x180020016  call    ??$hstring_convert@_J@impl@winrt@@YA?AUhstring@1@_J@Z; winrt::impl::hstring_convert<__int64>(__int64)
0x18002001b  mov     [rbp+57h+var_90], 3
0x180020022  mov     rax, [rsp+120h+var_E8]
0x180020027  mov     qword ptr [rbp+57h+var_58], rax
0x18002002b  lea     rdx, [rbp+57h+var_58]
0x18002002f  lea     rcx, [rsp+120h+var_F0]; struct winrt::param::hstring *
0x180020034  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180020039  mov     rbx, rax
0x18002003c  lea     rdx, aValue; "Value"
0x180020043  lea     rcx, [rbp+57h+var_B0]; this
0x180020047  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002004c  mov     r8, rbx
0x18002004f  lea     rdx, [rbp+57h+var_B0]
0x180020053  mov     rcx, rsi
0x180020056  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18002005b  nop
0x18002005c  lea     rcx, [rsp+120h+var_F0]; this
0x180020061  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180020066  nop
0x180020067  jmp     loc_1800208CD
0x18002006c  movsd   xmm1, cs:__real@4014000000000000
0x180020074  lea     rcx, [rsp+120h+var_F0]
0x180020079  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18002007e  mov     rbx, rax
0x180020081  lea     rdx, aType_0; "Type"
0x180020088  lea     rcx, [rbp+57h+var_58]; this
0x18002008c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180020091  mov     r8, rbx
0x180020094  lea     rdx, [rbp+57h+var_58]
0x180020098  mov     rcx, rsi
0x18002009b  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800200a0  nop
0x1800200a1  lea     rcx, [rsp+120h+var_F0]; this
0x1800200a6  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800200ab  mov     rcx, rdi
0x1800200ae  call    ?GetUInt32@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt32(void)
0x1800200b3  mov     eax, eax
0x1800200b5  xorps   xmm1, xmm1
0x1800200b8  cvtsi2sd xmm1, rax
0x1800200bd  lea     rcx, [rsp+120h+var_F0]
0x1800200c2  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800200c7  mov     rbx, rax
0x1800200ca  lea     rdx, aValue; "Value"
0x1800200d1  lea     rcx, [rbp+57h+var_58]; this
0x1800200d5  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800200da  mov     r8, rbx
0x1800200dd  lea     rdx, [rbp+57h+var_58]
0x1800200e1  mov     rcx, rsi
0x1800200e4  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800200e9  nop
0x1800200ea  jmp     loc_180020C70
0x1800200ef  movsd   xmm1, cs:__real@4010000000000000
0x1800200f7  lea     rcx, [rsp+120h+var_F0]
0x1800200fc  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x180020101  mov     rbx, rax
0x180020104  lea     rdx, aType_0; "Type"
0x18002010b  lea     rcx, [rbp+57h+var_58]; this
0x18002010f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180020114  mov     r8, rbx
0x180020117  lea     rdx, [rbp+57h+var_58]
0x18002011b  mov     rcx, rsi
0x18002011e  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180020123  nop
0x180020124  lea     rcx, [rsp+120h+var_F0]; this
0x180020129  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002012e  mov     rcx, rdi
0x180020131  call    ?GetInt32@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInt32(void)
0x180020136  movd    xmm1, eax
0x18002013a  cvtdq2pd xmm1, xmm1
0x18002013e  lea     rcx, [rsp+120h+var_F0]
0x180020143  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x180020148  mov     rbx, rax
0x18002014b  lea     rdx, aValue; "Value"
0x180020152  lea     rcx, [rbp+57h+var_58]; this
0x180020156  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002015b  mov     r8, rbx
0x18002015e  lea     rdx, [rbp+57h+var_58]
0x180020162  mov     rcx, rsi
0x180020165  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18002016a  nop
0x18002016b  jmp     loc_180020C70
0x180020170  movsd   xmm1, cs:__real@4008000000000000
0x180020178  lea     rcx, [rsp+120h+var_F0]
0x18002017d  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x180020182  mov     rbx, rax
0x180020185  lea     rdx, aType_0; "Type"
0x18002018c  lea     rcx, [rbp+57h+var_58]; this
0x180020190  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180020195  mov     r8, rbx
0x180020198  lea     rdx, [rbp+57h+var_58]
0x18002019c  mov     rcx, rsi
0x18002019f  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800201a4  nop
0x1800201a5  lea     rcx, [rsp+120h+var_F0]; this
0x1800201aa  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800201af  mov     rcx, rdi
0x1800201b2  call    ?GetUInt16@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetUInt16(void)
0x1800201b7  movzx   eax, ax
0x1800201ba  movd    xmm1, eax
0x1800201be  cvtdq2pd xmm1, xmm1
0x1800201c2  lea     rcx, [rsp+120h+var_F0]
0x1800201c7  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800201cc  mov     rbx, rax
0x1800201cf  lea     rdx, aValue; "Value"
0x1800201d6  lea     rcx, [rbp+57h+var_58]; this
0x1800201da  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800201df  mov     r8, rbx
0x1800201e2  lea     rdx, [rbp+57h+var_58]
0x1800201e6  mov     rcx, rsi
0x1800201e9  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800201ee  nop
0x1800201ef  jmp     loc_180020C70
0x1800201f4  movsd   xmm1, cs:__real@4000000000000000
0x1800201fc  lea     rcx, [rsp+120h+var_F0]
0x180020201  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x180020206  mov     rbx, rax
0x180020209  lea     rdx, aType_0; "Type"
0x180020210  lea     rcx, [rbp+57h+var_58]; this
0x180020214  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180020219  mov     r8, rbx
0x18002021c  lea     rdx, [rbp+57h+var_58]
0x180020220  mov     rcx, rsi
0x180020223  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180020228  nop
  ... truncated ...
```
