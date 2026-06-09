# Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel2(float)

- ea: `0x1800d8a18`
- end: `0x1800d9a9c`
- name: `?EvaluateUPMLModel2@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@AEAA?AU?$pair@MV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@M@Z`
- size: `4228`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d7090`

## callees

- `0x18000edb0`
- `0x180010890`
- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18002e168`
- `0x18002e698`
- `0x18002ea8c`
- `0x18003007c`
- `0x180098664`
- `0x1800b8ae0`
- `0x1800ba814`
- `0x1800bad50`
- `0x1800c4d00`
- `0x1800cd700`
- `0x1800d0674`
- `0x1800d06fc`
- `0x1800d07a8`
- `0x1800d0834`
- `0x1800d08b0`
- `0x1800d5f38`
- `0x1800d5fa4`
- `0x1800d6c64`
- `0x1800d7b18`
- `0x1800d8a18`
- `0x1800da780`
- `0x1800dd930`
- `0x1800dddf4`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d963e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d97ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d963e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d97ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9878`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d8ae6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d8ae6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d8a9b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d8a9b`

## string_xrefs

- `0x1800d9601`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d977d`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d99fd`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d9a27`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d9a3c`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d9a5a`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d9a72`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1800d9a8a`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel2(
        __int64 a1,
        __int64 a2,
        float a3)
{
  const char *v5; // r9
  HRESULT v6; // eax
  __int64 i; // rbx
  __int64 v8; // rsi
  void *v9; // rcx
  _QWORD *v10; // rax
  unsigned int v11; // esi
  unsigned __int64 v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rax
  void *v15; // rax
  __int64 v16; // rax
  LPVOID *v17; // xmm0_8
  __m128i v18; // xmm1
  LPVOID *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rbx
  __int64 v22; // rax
  void *v23; // rax
  __int64 v24; // rax
  __int128 *v25; // xmm0_8
  __m128i v26; // xmm1
  __int128 *v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rax
  void *v31; // rax
  __int64 v32; // rax
  __int128 *v33; // xmm0_8
  __m128i v34; // xmm1
  __int128 *v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rbx
  __int64 v38; // rax
  void *v39; // rax
  __int64 v40; // rax
  __int128 *v41; // xmm0_8
  __m128i v42; // xmm1
  __int128 *v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // rax
  void *v47; // rax
  __int64 v48; // rax
  __int128 *v49; // xmm0_8
  __m128i v50; // xmm1
  __int128 *v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rbx
  __int64 v54; // rax
  void *v55; // rax
  __int64 v56; // rax
  __int128 *v57; // xmm0_8
  __m128i v58; // xmm1
  __int128 *v59; // rdx
  __int64 v60; // r8
  LPVOID v61; // rbx
  __int64 (__fastcall *v62)(LPVOID, unsigned __int64, _QWORD, const wchar_t *); // rsi
  _QWORD *v63; // rax
  int v64; // eax
  __int64 v65; // rbx
  __int64 (__fastcall *v66)(__int64, _QWORD, __int64, const wchar_t *); // rsi
  _QWORD *v67; // rax
  int v68; // eax
  int v69; // ebx
  bool v70; // bl
  void *v71; // rcx
  void *v72; // rcx
  void (*v73)(void); // rax
  __int64 v74; // rbx
  __int64 (__fastcall *v75)(__int64, _QWORD, __int64, const wchar_t *); // rsi
  _QWORD *v76; // rax
  int v77; // eax
  int v78; // ebx
  bool v79; // bl
  void *v80; // rcx
  void *v81; // rcx
  void *v82; // rcx
  LPVOID v83; // rbx
  __int64 (__fastcall *v84)(LPVOID, __int64, _QWORD, const wchar_t *); // rsi
  _QWORD *v85; // rax
  int v86; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  int ppvb; // [rsp+28h] [rbp-E0h]
  int ppvc; // [rsp+28h] [rbp-E0h]
  int ppvd; // [rsp+28h] [rbp-E0h]
  __int128 Src_8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v94; // [rsp+58h] [rbp-B0h]
  __int64 v95; // [rsp+60h] [rbp-A8h]
  __int128 v96; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v97; // [rsp+78h] [rbp-90h]
  __int64 v98; // [rsp+80h] [rbp-88h]
  __int128 v99; // [rsp+88h] [rbp-80h] BYREF
  __m128i v100; // [rsp+98h] [rbp-70h]
  _BYTE v101[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v102[32]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 *v103; // [rsp+E8h] [rbp-20h] BYREF
  char v104; // [rsp+F0h] [rbp-18h]
  __int64 v105; // [rsp+100h] [rbp-8h] BYREF
  float v106; // [rsp+108h] [rbp+0h] BYREF
  char v107; // [rsp+10Ch] [rbp+4h] BYREF
  LPVOID pv[2]; // [rsp+118h] [rbp+10h] BYREF
  __m128i v109; // [rsp+128h] [rbp+20h]
  unsigned int v110; // [rsp+138h] [rbp+30h] BYREF
  LPVOID v111; // [rsp+140h] [rbp+38h] BYREF
  __int64 v112; // [rsp+148h] [rbp+40h] BYREF
  __int128 v113; // [rsp+150h] [rbp+48h] BYREF
  __int64 v114; // [rsp+160h] [rbp+58h]
  __int128 v115; // [rsp+168h] [rbp+60h] BYREF
  __int64 v116; // [rsp+178h] [rbp+70h]
  void *v117[12]; // [rsp+188h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v105 = a2;
  InitOnceExecuteOnce(
    &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
    `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1EFB,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\staging.h",
      v5);
  }
  v111 = 0;
  v6 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v111);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v113 = 0;
  v114 = 0;
  v103 = &v113;
  v104 = 1;
  v8 = *((_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 + 1);
  for ( i = Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3; i != v8; i += 72 )
  {
    v9 = *(void **)(i + 48);
    v10 = (_QWORD *)(i + 32);
    if ( *(_QWORD *)(i + 56) > 7u )
      v10 = (_QWORD *)*v10;
    pv[0] = v10;
    pv[1] = v9;
    Src_8 = *(_OWORD *)pv;
    Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), &v96, &Src_8);
    if ( !(_BYTE)v97 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
    if ( SBYTE8(v96) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void_overloaded__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_2___Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_3____std::variant_unsigned_int_unsigned___int64__const___1_(retaddr);
    ppv = *(_DWORD *)(i + 68);
    Windows::RebootDowntime::AddCustomFeature(&v113, i);
  }
  v11 = 0;
  v12 = 0;
  do
  {
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v13 = std::to_wstring(v101, v11);
    Src_8 = 0;
    v94 = 0;
    v95 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8);
    v14 = std::wstring::append(&Src_8);
    v99 = *(_OWORD *)v14;
    v100 = *(__m128i *)(v14 + 16);
    *(_QWORD *)(v14 + 16) = 0;
    *(_QWORD *)(v14 + 24) = 7;
    *(_WORD *)v14 = 0;
    v15 = (void *)std::operator+<wchar_t>(v102, &v99, v13);
    v16 = std::wstring::append(v15);
    *(_OWORD *)pv = *(_OWORD *)v16;
    v17 = (LPVOID *)pv[0];
    v109 = *(__m128i *)(v16 + 16);
    v18 = v109;
    *(_QWORD *)(v16 + 16) = 0;
    *(_QWORD *)(v16 + 24) = 7;
    *(_WORD *)v16 = 0;
    v19 = pv;
    if ( _mm_srli_si128(v18, 8).m128i_u64[0] > 7 )
      v19 = v17;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    std::wstring::_Construct<1,wchar_t const *>(&v96);
    Windows::RebootDowntime::AddCustomFeature(&v113, &v96);
    std::wstring::~wstring(&v96);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(v102);
    std::wstring::~wstring(&v99);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v101);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v21 = std::to_wstring(v102, v11);
    Src_8 = 0;
    v94 = 0;
    v95 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8);
    v22 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v22;
    v109 = *(__m128i *)(v22 + 16);
    *(_QWORD *)(v22 + 16) = 0;
    *(_QWORD *)(v22 + 24) = 7;
    *(_WORD *)v22 = 0;
    v23 = (void *)std::operator+<wchar_t>(v101, pv, v21);
    v24 = std::wstring::append(v23);
    v99 = *(_OWORD *)v24;
    v25 = (__int128 *)v99;
    v100 = *(__m128i *)(v24 + 16);
    v26 = v100;
    *(_QWORD *)(v24 + 16) = 0;
    *(_QWORD *)(v24 + 24) = 7;
    *(_WORD *)v24 = 0;
    v27 = &v99;
    if ( _mm_srli_si128(v26, 8).m128i_u64[0] > 7 )
      v27 = v25;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    std::wstring::_Construct<1,wchar_t const *>(&v96);
    Windows::RebootDowntime::AddCustomFeature(&v113, &v96);
    std::wstring::~wstring(&v96);
    std::wstring::~wstring(&v99);
    std::wstring::~wstring(v101);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v102);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v29 = std::to_wstring(v102, v11);
    Src_8 = 0;
    v94 = 0;
    v95 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8);
    v30 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v30;
    v109 = *(__m128i *)(v30 + 16);
    *(_QWORD *)(v30 + 16) = 0;
    *(_QWORD *)(v30 + 24) = 7;
    *(_WORD *)v30 = 0;
    v31 = (void *)std::operator+<wchar_t>(v101, pv, v29);
    v32 = std::wstring::append(v31);
    v99 = *(_OWORD *)v32;
    v33 = (__int128 *)v99;
    v100 = *(__m128i *)(v32 + 16);
    v34 = v100;
    *(_QWORD *)(v32 + 16) = 0;
    *(_QWORD *)(v32 + 24) = 7;
    *(_WORD *)v32 = 0;
    v35 = &v99;
    if ( _mm_srli_si128(v34, 8).m128i_u64[0] > 7 )
      v35 = v33;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v36 = -1;
    do
      ++v36;
    while ( *((_WORD *)v35 + v36) );
    std::wstring::_Construct<1,wchar_t const *>(&v96);
    Windows::RebootDowntime::AddCustomFeature(&v113, &v96);
    std::wstring::~wstring(&v96);
    std::wstring::~wstring(&v99);
    std::wstring::~wstring(v101);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v102);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v37 = std::to_wstring(v102, v11);
    Src_8 = 0;
    v94 = 0;
    v95 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8);
    v38 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v38;
    v109 = *(__m128i *)(v38 + 16);
    *(_QWORD *)(v38 + 16) = 0;
    *(_QWORD *)(v38 + 24) = 7;
    *(_WORD *)v38 = 0;
    v39 = (void *)std::operator+<wchar_t>(v101, pv, v37);
    v40 = std::wstring::append(v39);
    v99 = *(_OWORD *)v40;
    v41 = (__int128 *)v99;
    v100 = *(__m128i *)(v40 + 16);
    v42 = v100;
    *(_QWORD *)(v40 + 16) = 0;
    *(_QWORD *)(v40 + 24) = 7;
    *(_WORD *)v40 = 0;
    v43 = &v99;
    if ( _mm_srli_si128(v42, 8).m128i_u64[0] > 7 )
      v43 = v41;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v43 + v44) );
    std::wstring::_Construct<1,wchar_t const *>(&v96);
    Windows::RebootDowntime::AddCustomFeature(&v113, &v96);
    std::wstring::~wstring(&v96);
    std::wstring::~wstring(&v99);
    std::wstring::~wstring(v101);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v102);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasQUPresent(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v45 = std::to_wstring(v102, v11);
    Src_8 = 0;
    v94 = 0;
    v95 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8);
    v46 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v46;
    v109 = *(__m128i *)(v46 + 16);
    *(_QWORD *)(v46 + 16) = 0;
    *(_QWORD *)(v46 + 24) = 7;
    *(_WORD *)v46 = 0;
    v47 = (void *)std::operator+<wchar_t>(v101, pv, v45);
    v48 = std::wstring::append(v47);
    v99 = *(_OWORD *)v48;
    v49 = (__int128 *)v99;
    v100 = *(__m128i *)(v48 + 16);
    v50 = v100;
    *(_QWORD *)(v48 + 16) = 0;
    *(_QWORD *)(v48 + 24) = 7;
    *(_WORD *)v48 = 0;
    v51 = &v99;
    if ( _mm_srli_si128(v50, 8).m128i_u64[0] > 7 )
      v51 = v49;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)v51 + v52) );
    std::wstring::_Construct<1,wchar_t const *>(&v96);
    Windows::RebootDowntime::AddCustomFeature(&v113, &v96);
    std::wstring::~wstring(&v96);
    std::wstring::~wstring(&v99);
    std::wstring::~wstring(v101);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v102);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasFUPresent(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v53 = std::to_wstring(v102, v11);
    Src_8 = 0;
    v94 = 0;
    v95 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8);
    v54 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v54;
    v109 = *(__m128i *)(v54 + 16);
    *(_QWORD *)(v54 + 16) = 0;
    *(_QWORD *)(v54 + 24) = 7;
    *(_WORD *)v54 = 0;
    v55 = (void *)std::operator+<wchar_t>(v101, pv, v53);
    v56 = std::wstring::append(v55);
    v99 = *(_OWORD *)v56;
    v57 = (__int128 *)v99;
    v100 = *(__m128i *)(v56 + 16);
    v58 = v100;
    *(_QWORD *)(v56 + 16) = 0;
    *(_QWORD *)(v56 + 24) = 7;
    *(_WORD *)v56 = 0;
    v59 = &v99;
    if ( _mm_srli_si128(v58, 8).m128i_u64[0] > 7 )
      v59 = v57;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v60 = -1;
    do
      ++v60;
    while ( *((_WORD *)v59 + v60) );
    std::wstring::_Construct<1,wchar_t const *>(&v96);
    Windows::RebootDowntime::AddCustomFeature(&v113, &v96);
    std::wstring::~wstring(&v96);
    std::wstring::~wstring(&v99);
    std::wstring::~wstring(v101);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v102);
    ++v11;
    ++v12;
  }
  while ( (int)v11 < 6 );
  memset(v117, 0, sizeof(v117));
  Windows::CorrelationVector::CorrelationVector((Windows::CorrelationVector *)v117);
  v110 = 0;
  v105 = 0;
  v61 = v111;
  v62 = *(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v111 + 40LL);
  v63 = (_QWORD *)Windows::CorrelationVector::to_string(v117, v101);
  if ( v63[3] > 0xFu )
    v63 = (_QWORD *)*v63;
  ppva = (int)v63;
  v64 = v62(v61, 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v113 + 1) - v113) >> 3), v113, L"QU202506");
  if ( v64 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v64,
      ppva);
  std::string::~string(v101);
  *(_QWORD *)&v96 = &v105;
  *((_QWORD *)&v96 + 1) = &v110;
  LOBYTE(v97) = 1;
  v112 = 0;
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v111)(
         v111,
         &GUID_68538015_9da0_4cb8_a6af_d52af2ea035b,
         &v112) >= 0 )
  {
    v106 = 0.0;
    pv[0] = 0;
    v65 = v112;
    v66 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v112 + 48LL);
    *(_QWORD *)&Src_8 = pv;
    *((_QWORD *)&Src_8 + 1) = 0;
    LOBYTE(v94) = 1;
    v67 = (_QWORD *)Windows::CorrelationVector::to_string(v117, v101);
    if ( v67[3] > 0xFu )
      v67 = (_QWORD *)*v67;
    ppvb = (int)v67;
    v68 = v66(v65, v110, v105, L"QUDowntimeUPMLV2");
    v69 = v68;
    if ( v68 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)(unsigned int)v68,
        ppvb);
    v70 = v69 >= 0;
    std::string::~string(v101);
    if ( (_BYTE)v94 )
    {
      v71 = *(void **)Src_8;
      *(_QWORD *)Src_8 = *((_QWORD *)&Src_8 + 1);
      if ( v71 )
        CoTaskMemFree(v71);
    }
    if ( v70 )
    {
      if ( LODWORD(v106) != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
          (const char *)0x8000FFFFLL,
          ppvb);
      *(_DWORD *)a2 = *(_DWORD *)pv[0];
      *(_OWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8);
      v72 = pv[0];
      pv[0] = 0;
      if ( v72 )
        CoTaskMemFree(v72);
      if ( v112 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v96);
      if ( v117[1] )
        operator delete(v117[1], (const struct std::nothrow_t *)0x90);
      goto LABEL_55;
    }
    v74 = v112;
    v75 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v112 + 48LL);
    *(_QWORD *)&Src_8 = pv;
    *((_QWORD *)&Src_8 + 1) = 0;
    LOBYTE(v94) = 1;
    v76 = (_QWORD *)Windows::CorrelationVector::to_string(v117, v101);
    if ( v76[3] > 0xFu )
      v76 = (_QWORD *)*v76;
    ppvc = (int)v76;
    v77 = v75(v74, v110, v105, L"QUDowntimeUPMLV1");
    v78 = v77;
    if ( v77 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)(unsigned int)v77,
        ppvc);
    v79 = v78 >= 0;
    std::string::~string(v101);
    if ( (_BYTE)v94 )
    {
      v80 = *(void **)Src_8;
      *(_QWORD *)Src_8 = *((_QWORD *)&Src_8 + 1);
      if ( v80 )
        CoTaskMemFree(v80);
    }
    if ( v79 )
    {
      if ( LODWORD(v106) != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14A,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
          (const char *)0x8000FFFFLL,
          ppvc);
      *(_DWORD *)a2 = *(_DWORD *)pv[0];
      *(_OWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8);
      v81 = pv[0];
      pv[0] = 0;
      if ( v81 )
        CoTaskMemFree(v81);
      if ( v112 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v96);
      if ( v117[1] )
        operator delete(v117[1], (const struct std::nothrow_t *)0x90);
LABEL_55:
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v103);
      std::vector<CustomFeature>::~vector<CustomFeature>(&v113);
      if ( v111 )
      {
        v73 = *(void (**)(void))(*(_QWORD *)v111 + 16LL);
LABEL_84:
        v73();
        return a2;
      }
      return a2;
    }
    v82 = pv[0];
    pv[0] = 0;
    if ( v82 )
      CoTaskMemFree(v82);
  }
  v115 = 0;
  v116 = 0;
  v106 = a3;
  pv[0] = &v106;
  pv[1] = &v107;
  Src_8 = *(_OWORD *)pv;
  std::vector<float>::vector<float>(&v115, &Src_8);
  v83 = v111;
  v84 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v111 + 32LL);
  v85 = (_QWORD *)Windows::CorrelationVector::to_string(v117, v101);
  if ( v85[3] > 0xFu )
    v85 = (_QWORD *)*v85;
  ppvd = (int)v85;
  v86 = v84(v83, (__int64)(*((_QWORD *)&v115 + 1) - v115) >> 2, v115, L"QU202506");
  if ( v86 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v86,
      ppvd);
  std::string::~string(v101);
  *(float *)a2 = a3;
  *(_OWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a2 + 8);
  std::vector<enum SystemInterface::Usage::LogonEvent>::~vector<enum SystemInterface::Usage::LogonEvent>(&v115);
  if ( v112 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v96);
  if ( v117[1] )
    operator delete(v117[1], (const struct std::nothrow_t *)0x90);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v103);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v113);
  if ( v111 )
  {
    v73 = *(void (**)(void))(*(_QWORD *)v111 + 16LL);
    goto LABEL_84;
  }
  return a2;
}

```

## disassembly

```asm
0x1800d8a18  mov     rax, rsp
0x1800d8a1b  mov     [rax+18h], rbx
0x1800d8a1f  mov     [rax+10h], rdx
0x1800d8a23  push    rbp
0x1800d8a24  push    rsi
0x1800d8a25  push    rdi
0x1800d8a26  push    r12
0x1800d8a28  push    r13
0x1800d8a2a  push    r14
0x1800d8a2c  push    r15
0x1800d8a2e  lea     rbp, [rax-198h]
0x1800d8a35  sub     rsp, 260h
0x1800d8a3c  movaps  xmmword ptr [rax-48h], xmm6
0x1800d8a40  movaps  xmmword ptr [rax-58h], xmm7
0x1800d8a44  movaps  xmmword ptr [rax-68h], xmm8
0x1800d8a49  movaps  xmmword ptr [rax-78h], xmm9
0x1800d8a4e  movaps  xmmword ptr [rax-88h], xmm10
0x1800d8a56  movaps  xmmword ptr [rax-98h], xmm11
0x1800d8a5e  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800d8a66  mov     rax, cs:__security_cookie
0x1800d8a6d  xor     rax, rsp
0x1800d8a70  mov     [rbp+190h+var_B0], rax
0x1800d8a77  movaps  xmm7, xmm2
0x1800d8a7a  mov     rdi, rdx
0x1800d8a7d  mov     r15, rcx
0x1800d8a80  mov     [rbp+190h+var_198], rdx
0x1800d8a84  xor     r12d, r12d
0x1800d8a87  xor     r9d, r9d; Context
0x1800d8a8a  xor     r8d, r8d; Parameter
0x1800d8a8d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800d8a94  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x1800d8a9b  call    cs:__imp_InitOnceExecuteOnce
0x1800d8aa1  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, r12b; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x1800d8aa8  jz      short loc_1800D8AC5
0x1800d8aaa  mov     rbx, [rbp+198h]
0x1800d8ab1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML>::GetImpl(void)'::`2'::impl
0x1800d8ab8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML>::__private_IsEnabled(wil::ReportingKind)
0x1800d8abd  test    al, al
0x1800d8abf  jz      loc_1800D9A0F
0x1800d8ac5  mov     [rbp+190h+var_158], r12
0x1800d8ac9  lea     rax, [rbp+190h+var_158]
0x1800d8acd  mov     [rsp+290h+ppv], rax; int
0x1800d8ad2  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1800d8ad9  xor     edx, edx; pUnkOuter
0x1800d8adb  lea     r8d, [rdx+4]; dwClsContext
0x1800d8adf  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1800d8ae6  call    cs:__imp_CoCreateInstance
0x1800d8aec  mov     rcx, [rbp+198h]; this
0x1800d8af3  test    eax, eax
0x1800d8af5  js      loc_1800D9A24
0x1800d8afb  xorps   xmm1, xmm1
0x1800d8afe  movdqu  [rbp+190h+var_148], xmm1
0x1800d8b03  mov     [rbp+190h+var_138], r12
0x1800d8b07  lea     rax, [rbp+190h+var_148]
0x1800d8b0b  mov     [rbp+190h+var_1B0], rax
0x1800d8b0f  mov     r13d, 1
0x1800d8b15  mov     [rbp+190h+var_1A8], r13b
0x1800d8b19  mov     rbx, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800d8b20  mov     rsi, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1800d8b27  cmp     rbx, rsi
0x1800d8b2a  jz      loc_1800D8C00
0x1800d8b30  lea     r14d, [r13+3Fh]
0x1800d8b34  mov     rcx, [rbx+30h]
0x1800d8b38  lea     rax, [rbx+20h]
0x1800d8b3c  cmp     qword ptr [rbx+38h], 7
0x1800d8b41  jbe     short loc_1800D8B46
0x1800d8b43  mov     rax, [rax]
0x1800d8b46  mov     [rbp+190h+pv], rax
0x1800d8b4a  mov     [rbp+190h+pv+8], rcx
0x1800d8b4e  movaps  xmm0, xmmword ptr [rbp+190h+pv]
0x1800d8b52  movdqa  [rsp+290h+Src+8], xmm0
0x1800d8b58  lea     r8, [rsp+290h+Src+8]
0x1800d8b5d  lea     rdx, [rsp+290h+var_238+8]
0x1800d8b62  mov     rcx, [r15+8]
0x1800d8b66  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1800d8b6b  mov     rcx, [rbp+198h]; this
0x1800d8b72  mov     al, byte ptr [rsp+290h+var_220]
0x1800d8b76  test    al, al
0x1800d8b78  jz      loc_1800D9A54
0x1800d8b7e  movsx   rax, byte ptr [rsp+290h+var_228]
0x1800d8b84  add     rax, r13
0x1800d8b87  jz      loc_1800D9A4E
0x1800d8b8d  lea     r9, [rbp+190h+var_148]
0x1800d8b91  xorps   xmm2, xmm2
0x1800d8b94  cmp     rax, 1
0x1800d8b98  jz      short loc_1800D8BC2
0x1800d8b9a  mov     rcx, qword ptr [rsp+290h+var_238+8]
0x1800d8b9f  test    rcx, rcx
0x1800d8ba2  js      short loc_1800D8BAB
0x1800d8ba4  cvtsi2ss xmm2, rcx
0x1800d8ba9  jmp     short loc_1800D8BCB
0x1800d8bab  mov     rax, rcx
0x1800d8bae  shr     rax, 1
0x1800d8bb1  and     rcx, r13
0x1800d8bb4  or      rax, rcx
0x1800d8bb7  cvtsi2ss xmm2, rax
0x1800d8bbc  addss   xmm2, xmm2
0x1800d8bc0  jmp     short loc_1800D8BCB
0x1800d8bc2  mov     eax, dword ptr [rsp+290h+var_238+8]
0x1800d8bc6  cvtsi2ss xmm2, rax
0x1800d8bcb  mov     r8d, 44h ; 'D'
0x1800d8bd1  mov     rdx, rbx
0x1800d8bd4  mov     rcx, r14
0x1800d8bd7  mov     rax, rbx
0x1800d8bda  movss   xmm0, dword ptr [rbx+r8]
0x1800d8be0  movss   dword ptr [rsp+290h+ppv], xmm0
0x1800d8be6  movss   xmm3, dword ptr [rbx+rcx]
0x1800d8beb  mov     rcx, r9
0x1800d8bee  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d8bf3  add     rbx, 48h ; 'H'
0x1800d8bf7  cmp     rbx, rsi
0x1800d8bfa  jnz     loc_1800D8B34
0x1800d8c00  mov     esi, r12d
0x1800d8c03  mov     r14, r12
0x1800d8c06  movss   xmm9, cs:__real@42c80000
0x1800d8c0f  movss   xmm10, cs:__real@46610000
0x1800d8c18  movss   xmm11, cs:__real@4e8f0d18
0x1800d8c21  movss   xmm12, cs:__real@41a00000
0x1800d8c2a  movss   xmm8, cs:__real@3f800000
0x1800d8c33  mov     rdx, r14; unsigned __int64
0x1800d8c36  mov     rcx, [r15+8]; this
0x1800d8c3a  call    ?QueryPastDowntimeTotalNumerOfUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(unsigned __int64)
0x1800d8c3f  xorps   xmm6, xmm6
0x1800d8c42  cvtsd2ss xmm6, xmm0
0x1800d8c46  mov     edx, esi
0x1800d8c48  lea     rcx, [rbp+190h+var_1F0]
0x1800d8c4c  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d8c51  mov     rbx, rax
0x1800d8c54  xorps   xmm0, xmm0
0x1800d8c57  movups  [rsp+290h+Src+8], xmm0
0x1800d8c5c  mov     [rsp+290h+var_240], r12
0x1800d8c61  mov     qword ptr [rsp+290h+var_238], r12
0x1800d8c66  mov     r8d, 6
0x1800d8c6c  lea     rdx, aRsetuc; "RSeTUC"
0x1800d8c73  lea     rcx, [rsp+290h+Src+8]
0x1800d8c78  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d8c7d  nop
0x1800d8c7e  mov     r8, r13
0x1800d8c81  lea     rdx, aN; "N"
0x1800d8c88  lea     rcx, [rsp+290h+Src+8]; Src
0x1800d8c8d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d8c92  movups  xmm0, xmmword ptr [rax]
0x1800d8c95  movups  [rbp+190h+var_210], xmm0
0x1800d8c99  movups  xmm1, xmmword ptr [rax+10h]
0x1800d8c9d  movups  [rbp+190h+var_200], xmm1
0x1800d8ca1  mov     [rax+10h], r12
0x1800d8ca5  mov     qword ptr [rax+18h], 7
0x1800d8cad  mov     [rax], r12w
0x1800d8cb1  mov     r8, rbx
0x1800d8cb4  lea     rdx, [rbp+190h+var_210]
0x1800d8cb8  lea     rcx, [rbp+190h+var_1D0]
0x1800d8cbc  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d8cc1  nop
0x1800d8cc2  mov     r8d, 2
0x1800d8cc8  lea     rdx, aV2; "V2"
0x1800d8ccf  mov     rcx, rax; Src
0x1800d8cd2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d8cd7  movups  xmm0, xmmword ptr [rax]
0x1800d8cda  movups  xmmword ptr [rbp+190h+pv], xmm0
0x1800d8cde  movups  xmm1, xmmword ptr [rax+10h]
0x1800d8ce2  movups  [rbp+190h+var_170], xmm1
0x1800d8ce6  mov     [rax+10h], r12
0x1800d8cea  mov     qword ptr [rax+18h], 7
0x1800d8cf2  mov     [rax], r12w
0x1800d8cf6  lea     rdx, [rbp+190h+pv]
0x1800d8cfa  movq    rcx, xmm0
0x1800d8cff  psrldq  xmm1, 8
0x1800d8d04  movq    rax, xmm1
0x1800d8d09  cmp     rax, 7
0x1800d8d0d  cmova   rdx, rcx
0x1800d8d11  xorps   xmm0, xmm0
0x1800d8d14  movups  [rsp+290h+var_238+8], xmm0
0x1800d8d19  mov     [rsp+290h+var_220], r12
0x1800d8d1e  mov     [rsp+290h+var_218], r12
0x1800d8d23  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d8d27  inc     r8
0x1800d8d2a  cmp     [rdx+r8*2], r12w
0x1800d8d2f  jnz     short loc_1800D8D27
0x1800d8d31  lea     rcx, [rsp+290h+var_238+8]
0x1800d8d36  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d8d3b  nop
0x1800d8d3c  movss   dword ptr [rsp+290h+ppv], xmm9
0x1800d8d43  xorps   xmm3, xmm3
0x1800d8d46  movaps  xmm2, xmm6
0x1800d8d49  lea     rdx, [rsp+290h+var_238+8]
0x1800d8d4e  lea     rcx, [rbp+190h+var_148]
0x1800d8d52  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d8d57  nop
0x1800d8d58  lea     rcx, [rsp+290h+var_238+8]; void *
0x1800d8d5d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8d62  nop
0x1800d8d63  lea     rcx, [rbp+190h+pv]; void *
0x1800d8d67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8d6c  nop
0x1800d8d6d  lea     rcx, [rbp+190h+var_1D0]; void *
0x1800d8d71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8d76  nop
0x1800d8d77  lea     rcx, [rbp+190h+var_210]; void *
0x1800d8d7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8d80  nop
0x1800d8d81  lea     rcx, [rsp+290h+Src+8]; void *
0x1800d8d86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8d8b  nop
0x1800d8d8c  lea     rcx, [rbp+190h+var_1F0]; void *
0x1800d8d90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8d95  mov     rdx, r14; unsigned __int64
0x1800d8d98  mov     rcx, [r15+8]; this
0x1800d8d9c  call    ?QueryPastDowntimeDurationSeconds@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(unsigned __int64)
0x1800d8da1  xorps   xmm6, xmm6
0x1800d8da4  cvtsd2ss xmm6, xmm0
0x1800d8da8  mov     edx, esi
0x1800d8daa  lea     rcx, [rbp+190h+var_1D0]
0x1800d8dae  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d8db3  mov     rbx, rax
0x1800d8db6  xorps   xmm0, xmm0
0x1800d8db9  movups  [rsp+290h+Src+8], xmm0
0x1800d8dbe  mov     [rsp+290h+var_240], r12
0x1800d8dc3  mov     qword ptr [rsp+290h+var_238], r12
0x1800d8dc8  mov     r8d, 5
0x1800d8dce  lea     rdx, aRseti; "RSeTi"
0x1800d8dd5  lea     rcx, [rsp+290h+Src+8]
0x1800d8dda  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d8ddf  nop
0x1800d8de0  mov     r8, r13
0x1800d8de3  lea     rdx, aN; "N"
0x1800d8dea  lea     rcx, [rsp+290h+Src+8]; Src
0x1800d8def  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d8df4  movups  xmm0, xmmword ptr [rax]
0x1800d8df7  movups  xmmword ptr [rbp+190h+pv], xmm0
0x1800d8dfb  movups  xmm1, xmmword ptr [rax+10h]
0x1800d8dff  movups  [rbp+190h+var_170], xmm1
0x1800d8e03  mov     [rax+10h], r12
0x1800d8e07  mov     qword ptr [rax+18h], 7
0x1800d8e0f  mov     [rax], r12w
0x1800d8e13  mov     r8, rbx
0x1800d8e16  lea     rdx, [rbp+190h+pv]
0x1800d8e1a  lea     rcx, [rbp+190h+var_1F0]
0x1800d8e1e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d8e23  nop
0x1800d8e24  mov     r8d, 2
0x1800d8e2a  lea     rdx, aV1; "V1"
0x1800d8e31  mov     rcx, rax; Src
0x1800d8e34  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800d8e39  movups  xmm0, xmmword ptr [rax]
0x1800d8e3c  movups  [rbp+190h+var_210], xmm0
0x1800d8e40  movups  xmm1, xmmword ptr [rax+10h]
0x1800d8e44  movups  [rbp+190h+var_200], xmm1
0x1800d8e48  mov     [rax+10h], r12
0x1800d8e4c  mov     qword ptr [rax+18h], 7
0x1800d8e54  mov     [rax], r12w
0x1800d8e58  lea     rdx, [rbp+190h+var_210]
0x1800d8e5c  movq    rcx, xmm0
0x1800d8e61  psrldq  xmm1, 8
0x1800d8e66  movq    rax, xmm1
0x1800d8e6b  cmp     rax, 7
0x1800d8e6f  cmova   rdx, rcx
0x1800d8e73  xorps   xmm0, xmm0
0x1800d8e76  movups  [rsp+290h+var_238+8], xmm0
0x1800d8e7b  mov     [rsp+290h+var_220], r12
0x1800d8e80  mov     [rsp+290h+var_218], r12
0x1800d8e85  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d8e89  inc     r8
0x1800d8e8c  cmp     [rdx+r8*2], r12w
0x1800d8e91  jnz     short loc_1800D8E89
0x1800d8e93  lea     rcx, [rsp+290h+var_238+8]
0x1800d8e98  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800d8e9d  nop
0x1800d8e9e  movss   dword ptr [rsp+290h+ppv], xmm10
0x1800d8ea5  xorps   xmm3, xmm3
0x1800d8ea8  movaps  xmm2, xmm6
0x1800d8eab  lea     rdx, [rsp+290h+var_238+8]
0x1800d8eb0  lea     rcx, [rbp+190h+var_148]
0x1800d8eb4  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1800d8eb9  nop
0x1800d8eba  lea     rcx, [rsp+290h+var_238+8]; void *
0x1800d8ebf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8ec4  nop
0x1800d8ec5  lea     rcx, [rbp+190h+var_210]; void *
0x1800d8ec9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8ece  nop
0x1800d8ecf  lea     rcx, [rbp+190h+var_1F0]; void *
0x1800d8ed3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8ed8  nop
0x1800d8ed9  lea     rcx, [rbp+190h+pv]; void *
0x1800d8edd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8ee2  nop
0x1800d8ee3  lea     rcx, [rsp+290h+Src+8]; void *
0x1800d8ee8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8eed  nop
0x1800d8eee  lea     rcx, [rbp+190h+var_1D0]; void *
0x1800d8ef2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d8ef7  mov     rdx, r14; unsigned __int64
0x1800d8efa  mov     rcx, [r15+8]; this
0x1800d8efe  call    ?QueryPastDowntimeTotalSizeUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(unsigned __int64)
0x1800d8f03  xorps   xmm6, xmm6
0x1800d8f06  cvtsd2ss xmm6, xmm0
0x1800d8f0a  mov     edx, esi
0x1800d8f0c  lea     rcx, [rbp+190h+var_1D0]
0x1800d8f10  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800d8f15  mov     rbx, rax
  ... truncated ...
```
