# Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel(float)

- ea: `0x1402c6794`
- end: `0x1402c75b0`
- name: `?EvaluateUPMLModel@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@AEAAMM@Z`
- size: `3612`
- prototype: `float __fastcall(Windows::RebootDowntime::QualityUpdateDowntimeEvaluator *__hidden this, float)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1402c5eb0`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x140044b18`
- `0x140044f20`
- `0x140045404`
- `0x1400a3f7c`
- `0x1400a4b78`
- `0x1400c695c`
- `0x14018ad1c`
- `0x1401a2b3c`
- `0x1402ac0e4`
- `0x1402ac630`
- `0x1402b63c8`
- `0x1402bd2fc`
- `0x1402c00b0`
- `0x1402c0138`
- `0x1402c01e4`
- `0x1402c0270`
- `0x1402c02ec`
- `0x1402c5130`
- `0x1402c519c`
- `0x1402c66b8`
- `0x1402c6794`
- `0x1402c9320`
- `0x1402c94dc`
- `0x140379070`
- `0x1403790cc`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402c685a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402c685a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c737c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c73ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c73c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c737c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c73ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c73c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1402c680f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1402c680f`

## string_xrefs

- `0x1402c733f`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c7529`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c7553`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c7568`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c7586`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c759e`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
float __fastcall Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel(
        Windows::RebootDowntime::QualityUpdateDowntimeEvaluator *this,
        float a2)
{
  const char *v4; // r9
  HRESULT v5; // eax
  __int64 i; // rbx
  __int64 v7; // rdi
  void *v8; // rcx
  _QWORD *v9; // rax
  unsigned int v10; // edi
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rax
  void *v14; // rax
  __int64 v15; // rax
  LPVOID *v16; // xmm0_8
  __m128i v17; // xmm1
  LPVOID *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  void *v22; // rax
  __int64 v23; // rax
  __int128 *v24; // xmm0_8
  __m128i v25; // xmm1
  __int128 *v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rbx
  __int64 v29; // rax
  void *v30; // rax
  __int64 v31; // rax
  __int128 *v32; // xmm0_8
  __m128i v33; // xmm1
  __int128 *v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rbx
  __int64 v37; // rax
  void *v38; // rax
  __int64 v39; // rax
  __int128 *v40; // xmm0_8
  __m128i v41; // xmm1
  __int128 *v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rbx
  __int64 v45; // rax
  void *v46; // rax
  __int64 v47; // rax
  __int128 *v48; // xmm0_8
  __m128i v49; // xmm1
  __int128 *v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rbx
  __int64 v53; // rax
  void *v54; // rax
  __int64 v55; // rax
  __int128 *v56; // xmm0_8
  __m128i v57; // xmm1
  __int128 *v58; // rdx
  __int64 v59; // r8
  LPVOID v60; // rbx
  __int64 (__fastcall *v61)(LPVOID, unsigned __int64, _QWORD, const wchar_t *); // rdi
  _QWORD *v62; // rax
  int v63; // eax
  __int64 v64; // rbx
  __int64 (__fastcall *v65)(__int64, _QWORD, __int64, const wchar_t *); // rdi
  _QWORD *v66; // rax
  int v67; // eax
  int v68; // ebx
  bool v69; // bl
  void *v70; // rcx
  void *v71; // rcx
  void *v72; // rcx
  LPVOID v73; // rbx
  __int64 (__fastcall *v74)(LPVOID, __int64, _QWORD, const wchar_t *); // rdi
  _QWORD *v75; // rax
  int v76; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  int ppvb; // [rsp+28h] [rbp-E0h]
  int ppvc; // [rsp+28h] [rbp-E0h]
  __int128 Src_8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v83; // [rsp+58h] [rbp-B0h]
  __int64 v84; // [rsp+60h] [rbp-A8h]
  __int128 v85; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+78h] [rbp-90h]
  __int64 v87; // [rsp+80h] [rbp-88h]
  __int128 v88; // [rsp+88h] [rbp-80h] BYREF
  __m128i v89; // [rsp+98h] [rbp-70h]
  _BYTE v90[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v91[32]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 *v92; // [rsp+E8h] [rbp-20h] BYREF
  char v93; // [rsp+F0h] [rbp-18h]
  __int64 v94; // [rsp+F8h] [rbp-10h] BYREF
  float v95; // [rsp+100h] [rbp-8h] BYREF
  char v96; // [rsp+104h] [rbp-4h] BYREF
  LPVOID pv[2]; // [rsp+108h] [rbp+0h] BYREF
  __m128i v98; // [rsp+118h] [rbp+10h]
  unsigned int v99; // [rsp+128h] [rbp+20h] BYREF
  LPVOID v100; // [rsp+130h] [rbp+28h] BYREF
  __int128 v101; // [rsp+138h] [rbp+30h] BYREF
  __int64 v102; // [rsp+148h] [rbp+40h]
  __int64 v103; // [rsp+150h] [rbp+48h] BYREF
  __int128 v104; // [rsp+158h] [rbp+50h] BYREF
  __int64 v105; // [rsp+168h] [rbp+60h]
  void *v106[12]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  InitOnceExecuteOnce(
    &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
    `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1EFB,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\staging.h",
      v4);
  }
  v100 = 0;
  v5 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v100);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v101 = 0;
  v102 = 0;
  v92 = &v101;
  v93 = 1;
  v7 = *((_QWORD *)&Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3 + 1);
  for ( i = Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3; i != v7; i += 72 )
  {
    v8 = *(void **)(i + 48);
    v9 = (_QWORD *)(i + 32);
    if ( *(_QWORD *)(i + 56) > 7u )
      v9 = (_QWORD *)*v9;
    pv[0] = v9;
    pv[1] = v8;
    Src_8 = *(_OWORD *)pv;
    Windows::RebootDowntime::InputBuilder::GetInputForKey(*((_QWORD *)this + 1), &v85, &Src_8);
    if ( !(_BYTE)v86 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
    if ( SBYTE8(v85) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void_overloaded__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_2___Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_3____std::variant_unsigned_int_unsigned___int64__const___1_(retaddr);
    ppv = *(_DWORD *)(i + 68);
    Windows::RebootDowntime::AddCustomFeature(&v101, i);
  }
  v10 = 0;
  v11 = 0;
  do
  {
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v12 = std::to_wstring(v90, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC");
    v13 = std::wstring::append(&Src_8);
    v88 = *(_OWORD *)v13;
    v89 = *(__m128i *)(v13 + 16);
    *(_QWORD *)(v13 + 16) = 0;
    *(_QWORD *)(v13 + 24) = 7;
    *(_WORD *)v13 = 0;
    v14 = (void *)std::operator+<wchar_t>(v91, &v88, v12);
    v15 = std::wstring::append(v14);
    *(_OWORD *)pv = *(_OWORD *)v15;
    v16 = (LPVOID *)pv[0];
    v98 = *(__m128i *)(v15 + 16);
    v17 = v98;
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
    v18 = pv;
    if ( _mm_srli_si128(v17, 8).m128i_u64[0] > 7 )
      v18 = v16;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v18);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(v91);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v90);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v20 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTi");
    v21 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v21;
    v98 = *(__m128i *)(v21 + 16);
    *(_QWORD *)(v21 + 16) = 0;
    *(_QWORD *)(v21 + 24) = 7;
    *(_WORD *)v21 = 0;
    v22 = (void *)std::operator+<wchar_t>(v90, pv, v20);
    v23 = std::wstring::append(v22);
    v88 = *(_OWORD *)v23;
    v24 = (__int128 *)v88;
    v89 = *(__m128i *)(v23 + 16);
    v25 = v89;
    *(_QWORD *)(v23 + 16) = 0;
    *(_QWORD *)(v23 + 24) = 7;
    *(_WORD *)v23 = 0;
    v26 = &v88;
    if ( _mm_srli_si128(v25, 8).m128i_u64[0] > 7 )
      v26 = v24;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v26 + v27) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v26);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v28 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUS");
    v29 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v29;
    v98 = *(__m128i *)(v29 + 16);
    *(_QWORD *)(v29 + 16) = 0;
    *(_QWORD *)(v29 + 24) = 7;
    *(_WORD *)v29 = 0;
    v30 = (void *)std::operator+<wchar_t>(v90, pv, v28);
    v31 = std::wstring::append(v30);
    v88 = *(_OWORD *)v31;
    v32 = (__int128 *)v88;
    v89 = *(__m128i *)(v31 + 16);
    v33 = v89;
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    *(_WORD *)v31 = 0;
    v34 = &v88;
    if ( _mm_srli_si128(v33, 8).m128i_u64[0] > 7 )
      v34 = v32;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)v34 + v35) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v34);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v36 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC");
    v37 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v37;
    v98 = *(__m128i *)(v37 + 16);
    *(_QWORD *)(v37 + 16) = 0;
    *(_QWORD *)(v37 + 24) = 7;
    *(_WORD *)v37 = 0;
    v38 = (void *)std::operator+<wchar_t>(v90, pv, v36);
    v39 = std::wstring::append(v38);
    v88 = *(_OWORD *)v39;
    v40 = (__int128 *)v88;
    v89 = *(__m128i *)(v39 + 16);
    v41 = v89;
    *(_QWORD *)(v39 + 16) = 0;
    *(_QWORD *)(v39 + 24) = 7;
    *(_WORD *)v39 = 0;
    v42 = &v88;
    if ( _mm_srli_si128(v41, 8).m128i_u64[0] > 7 )
      v42 = v40;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v42);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasQUPresent(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v44 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeQU");
    v45 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v45;
    v98 = *(__m128i *)(v45 + 16);
    *(_QWORD *)(v45 + 16) = 0;
    *(_QWORD *)(v45 + 24) = 7;
    *(_WORD *)v45 = 0;
    v46 = (void *)std::operator+<wchar_t>(v90, pv, v44);
    v47 = std::wstring::append(v46);
    v88 = *(_OWORD *)v47;
    v48 = (__int128 *)v88;
    v89 = *(__m128i *)(v47 + 16);
    v49 = v89;
    *(_QWORD *)(v47 + 16) = 0;
    *(_QWORD *)(v47 + 24) = 7;
    *(_WORD *)v47 = 0;
    v50 = &v88;
    if ( _mm_srli_si128(v49, 8).m128i_u64[0] > 7 )
      v50 = v48;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v51 = -1;
    do
      ++v51;
    while ( *((_WORD *)v50 + v51) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v50);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasFUPresent(
      *((Windows::RebootDowntime::InputBuilder **)this + 1),
      v11);
    v52 = std::to_wstring(v91, v10);
    Src_8 = 0;
    v83 = 0;
    v84 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeFU");
    v53 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v53;
    v98 = *(__m128i *)(v53 + 16);
    *(_QWORD *)(v53 + 16) = 0;
    *(_QWORD *)(v53 + 24) = 7;
    *(_WORD *)v53 = 0;
    v54 = (void *)std::operator+<wchar_t>(v90, pv, v52);
    v55 = std::wstring::append(v54);
    v88 = *(_OWORD *)v55;
    v56 = (__int128 *)v88;
    v89 = *(__m128i *)(v55 + 16);
    v57 = v89;
    *(_QWORD *)(v55 + 16) = 0;
    *(_QWORD *)(v55 + 24) = 7;
    *(_WORD *)v55 = 0;
    v58 = &v88;
    if ( _mm_srli_si128(v57, 8).m128i_u64[0] > 7 )
      v58 = v56;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v59 = -1;
    do
      ++v59;
    while ( *((_WORD *)v58 + v59) );
    std::wstring::_Construct<1,wchar_t const *>(&v85, v58);
    Windows::RebootDowntime::AddCustomFeature(&v101, &v85);
    std::wstring::~wstring(&v85);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(pv);
    std::wstring::~wstring(&Src_8);
    std::wstring::~wstring(v91);
    ++v10;
    ++v11;
  }
  while ( (int)v10 < 6 );
  memset(v106, 0, sizeof(v106));
  Windows::CorrelationVector::CorrelationVector((Windows::CorrelationVector *)v106);
  v99 = 0;
  v94 = 0;
  v60 = v100;
  v61 = *(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v100 + 40LL);
  v62 = (_QWORD *)Windows::CorrelationVector::to_string(v106, v90);
  if ( v62[3] > 0xFu )
    v62 = (_QWORD *)*v62;
  ppva = (int)v62;
  v63 = v61(v60, 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v101 + 1) - v101) >> 3), v101, L"QU202506");
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v63,
      ppva);
  std::string::_Tidy_deallocate(v90);
  *(_QWORD *)&v85 = &v94;
  *((_QWORD *)&v85 + 1) = &v99;
  LOBYTE(v86) = 1;
  v103 = 0;
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v100)(
         v100,
         &GUID_68538015_9da0_4cb8_a6af_d52af2ea035b,
         &v103) >= 0 )
  {
    v95 = 0.0;
    pv[0] = 0;
    v64 = v103;
    v65 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v103 + 48LL);
    *(_QWORD *)&Src_8 = pv;
    *((_QWORD *)&Src_8 + 1) = 0;
    LOBYTE(v83) = 1;
    v66 = (_QWORD *)Windows::CorrelationVector::to_string(v106, v90);
    if ( v66[3] > 0xFu )
      v66 = (_QWORD *)*v66;
    ppvb = (int)v66;
    v67 = v65(v64, v99, v94, L"QUUPMLV1");
    v68 = v67;
    if ( v67 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)(unsigned int)v67,
        ppvb);
    v69 = v68 >= 0;
    std::string::_Tidy_deallocate(v90);
    if ( (_BYTE)v83 )
    {
      v70 = *(void **)Src_8;
      *(_QWORD *)Src_8 = *((_QWORD *)&Src_8 + 1);
      if ( v70 )
        CoTaskMemFree(v70);
    }
    if ( v69 )
    {
      if ( LODWORD(v95) != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
          (const char *)0x8000FFFFLL,
          ppvb);
      v71 = pv[0];
      a2 = *(float *)pv[0];
      pv[0] = 0;
      if ( v71 )
        CoTaskMemFree(v71);
      goto LABEL_57;
    }
    v72 = pv[0];
    pv[0] = 0;
    if ( v72 )
      CoTaskMemFree(v72);
  }
  v104 = 0;
  v105 = 0;
  v95 = a2;
  pv[0] = &v95;
  pv[1] = &v96;
  Src_8 = *(_OWORD *)pv;
  std::vector<float>::vector<float>(&v104, &Src_8);
  v73 = v100;
  v74 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v100 + 32LL);
  v75 = (_QWORD *)Windows::CorrelationVector::to_string(v106, v90);
  if ( v75[3] > 0xFu )
    v75 = (_QWORD *)*v75;
  ppvc = (int)v75;
  v76 = v74(v73, (__int64)(*((_QWORD *)&v104 + 1) - v104) >> 2, v104, L"QU202506");
  if ( v76 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v76,
      ppvc);
  std::string::_Tidy_deallocate(v90);
  std::vector<std::_Chrono_spec<wchar_t>>::~vector<std::_Chrono_spec<wchar_t>>(&v104);
LABEL_57:
  if ( v103 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v85);
  if ( v106[1] )
    operator delete(v106[1]);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v92);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v101);
  if ( v100 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v100 + 16LL))(v100);
  return a2;
}

```

## disassembly

```asm
0x1402c6794  mov     rax, rsp
0x1402c6797  mov     [rax+10h], rbx
0x1402c679b  mov     [rax+18h], rsi
0x1402c679f  mov     [rax+20h], rdi
0x1402c67a3  push    rbp
0x1402c67a4  push    r12
0x1402c67a6  push    r13
0x1402c67a8  push    r14
0x1402c67aa  push    r15
0x1402c67ac  lea     rbp, [rax-178h]
0x1402c67b3  sub     rsp, 250h
0x1402c67ba  movaps  xmmword ptr [rax-38h], xmm6
0x1402c67be  movaps  xmmword ptr [rax-48h], xmm7
0x1402c67c2  movaps  xmmword ptr [rax-58h], xmm8
0x1402c67c7  movaps  xmmword ptr [rax-68h], xmm9
0x1402c67cc  movaps  xmmword ptr [rax-78h], xmm10
0x1402c67d1  movaps  xmmword ptr [rax-88h], xmm11
0x1402c67d9  movaps  xmmword ptr [rax-98h], xmm12
0x1402c67e1  mov     rax, cs:__security_cookie
0x1402c67e8  xor     rax, rsp
0x1402c67eb  mov     [rbp+170h+var_A0], rax
0x1402c67f2  movaps  xmm6, xmm1
0x1402c67f5  mov     r14, rcx
0x1402c67f8  xor     r15d, r15d
0x1402c67fb  xor     r9d, r9d; Context
0x1402c67fe  xor     r8d, r8d; Parameter
0x1402c6801  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1402c6808  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x1402c680f  call    cs:__imp_InitOnceExecuteOnce
0x1402c6815  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, r15b; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x1402c681c  jz      short loc_1402C6839
0x1402c681e  mov     rbx, [rbp+178h]
0x1402c6825  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::GetImpl(void)'::`2'::impl
0x1402c682c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUDowntimeUPMLV1>::__private_IsEnabled(wil::ReportingKind)
0x1402c6831  test    al, al
0x1402c6833  jz      loc_1402C753B
0x1402c6839  mov     [rbp+170h+var_148], r15
0x1402c683d  lea     rax, [rbp+170h+var_148]
0x1402c6841  mov     [rsp+270h+ppv], rax; int
0x1402c6846  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1402c684d  xor     edx, edx; pUnkOuter
0x1402c684f  lea     r8d, [rdx+4]; dwClsContext
0x1402c6853  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1402c685a  call    cs:__imp_CoCreateInstance
0x1402c6860  mov     rcx, [rbp+178h]; this
0x1402c6867  test    eax, eax
0x1402c6869  js      loc_1402C7550
0x1402c686f  xorps   xmm1, xmm1
0x1402c6872  movdqu  [rbp+170h+var_140], xmm1
0x1402c6877  mov     [rbp+170h+var_130], r15
0x1402c687b  lea     rax, [rbp+170h+var_140]
0x1402c687f  mov     [rbp+170h+var_190], rax
0x1402c6883  mov     r12d, 1
0x1402c6889  mov     [rbp+170h+var_188], r12b
0x1402c688d  mov     rbx, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1402c6894  mov     rdi, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1402c689b  lea     r13d, [r12+6]
0x1402c68a0  cmp     rbx, rdi
0x1402c68a3  jz      loc_1402C6983
0x1402c68a9  lea     esi, [r12+3Fh]
0x1402c68ae  lea     r13d, [r12+43h]
0x1402c68b3  mov     rcx, [rbx+30h]
0x1402c68b7  lea     rax, [rbx+20h]
0x1402c68bb  cmp     qword ptr [rbx+38h], 7
0x1402c68c0  jbe     short loc_1402C68C5
0x1402c68c2  mov     rax, [rax]
0x1402c68c5  mov     [rbp+170h+pv], rax
0x1402c68c9  mov     [rbp+170h+pv+8], rcx
0x1402c68cd  movaps  xmm0, xmmword ptr [rbp+170h+pv]
0x1402c68d1  movdqa  [rsp+270h+Src+8], xmm0
0x1402c68d7  lea     r8, [rsp+270h+Src+8]
0x1402c68dc  lea     rdx, [rsp+270h+var_218+8]
0x1402c68e1  mov     rcx, [r14+8]
0x1402c68e5  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1402c68ea  mov     rcx, [rbp+178h]; this
0x1402c68f1  mov     al, byte ptr [rsp+270h+var_200]
0x1402c68f5  test    al, al
0x1402c68f7  jz      loc_1402C7580
0x1402c68fd  movsx   rax, byte ptr [rsp+270h+var_208]
0x1402c6903  add     rax, r12
0x1402c6906  jz      loc_1402C757A
0x1402c690c  lea     r9, [rbp+170h+var_140]
0x1402c6910  xorps   xmm2, xmm2
0x1402c6913  cmp     rax, 1
0x1402c6917  jz      short loc_1402C6941
0x1402c6919  mov     rcx, qword ptr [rsp+270h+var_218+8]
0x1402c691e  test    rcx, rcx
0x1402c6921  js      short loc_1402C692A
0x1402c6923  cvtsi2ss xmm2, rcx
0x1402c6928  jmp     short loc_1402C694A
0x1402c692a  mov     rax, rcx
0x1402c692d  shr     rax, 1
0x1402c6930  and     rcx, r12
0x1402c6933  or      rax, rcx
0x1402c6936  cvtsi2ss xmm2, rax
0x1402c693b  addss   xmm2, xmm2
0x1402c693f  jmp     short loc_1402C694A
0x1402c6941  mov     eax, dword ptr [rsp+270h+var_218+8]
0x1402c6945  cvtsi2ss xmm2, rax
0x1402c694a  mov     r8, r13
0x1402c694d  mov     rdx, rbx
0x1402c6950  mov     rcx, rsi
0x1402c6953  mov     rax, rbx
0x1402c6956  movss   xmm0, dword ptr [r13+rbx+0]
0x1402c695d  movss   dword ptr [rsp+270h+ppv], xmm0
0x1402c6963  movss   xmm3, dword ptr [rbx+rcx]
0x1402c6968  mov     rcx, r9
0x1402c696b  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1402c6970  add     rbx, 48h ; 'H'
0x1402c6974  cmp     rbx, rdi
0x1402c6977  jnz     loc_1402C68B3
0x1402c697d  mov     r13d, 7
0x1402c6983  mov     edi, r15d
0x1402c6986  mov     rsi, r15
0x1402c6989  movss   xmm9, cs:__real@42c80000
0x1402c6992  movss   xmm10, cs:__real@46610000
0x1402c699b  movss   xmm11, cs:__real@4e8f0d18
0x1402c69a4  movss   xmm12, cs:__real@41a00000
0x1402c69ad  movss   xmm8, cs:__real@3f800000
0x1402c69b6  mov     rdx, rsi; unsigned __int64
0x1402c69b9  mov     rcx, [r14+8]; this
0x1402c69bd  call    ?QueryPastDowntimeTotalNumerOfUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(unsigned __int64)
0x1402c69c2  xorps   xmm7, xmm7
0x1402c69c5  cvtsd2ss xmm7, xmm0
0x1402c69c9  mov     edx, edi
0x1402c69cb  lea     rcx, [rbp+170h+var_1D0]
0x1402c69cf  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1402c69d4  mov     rbx, rax
0x1402c69d7  xorps   xmm0, xmm0
0x1402c69da  movups  [rsp+270h+Src+8], xmm0
0x1402c69df  mov     [rsp+270h+var_220], r15
0x1402c69e4  mov     qword ptr [rsp+270h+var_218], r15
0x1402c69e9  mov     r8d, 6
0x1402c69ef  lea     rdx, aRsetuc; "RSeTUC"
0x1402c69f6  lea     rcx, [rsp+270h+Src+8]
0x1402c69fb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c6a00  nop
0x1402c6a01  mov     r8, r12
0x1402c6a04  lea     rdx, aN; "N"
0x1402c6a0b  lea     rcx, [rsp+270h+Src+8]; Src
0x1402c6a10  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c6a15  movups  xmm0, xmmword ptr [rax]
0x1402c6a18  movups  [rbp+170h+var_1F0], xmm0
0x1402c6a1c  movups  xmm1, xmmword ptr [rax+10h]
0x1402c6a20  movups  [rbp+170h+var_1E0], xmm1
0x1402c6a24  mov     [rax+10h], r15
0x1402c6a28  mov     [rax+18h], r13
0x1402c6a2c  mov     [rax], r15w
0x1402c6a30  mov     r8, rbx
0x1402c6a33  lea     rdx, [rbp+170h+var_1F0]
0x1402c6a37  lea     rcx, [rbp+170h+var_1B0]
0x1402c6a3b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1402c6a40  nop
0x1402c6a41  mov     r8d, 2
0x1402c6a47  lea     rdx, aV2; "V2"
0x1402c6a4e  mov     rcx, rax; Src
0x1402c6a51  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c6a56  movups  xmm0, xmmword ptr [rax]
0x1402c6a59  movups  xmmword ptr [rbp+170h+pv], xmm0
0x1402c6a5d  movups  xmm1, xmmword ptr [rax+10h]
0x1402c6a61  movups  [rbp+170h+var_160], xmm1
0x1402c6a65  mov     [rax+10h], r15
0x1402c6a69  mov     [rax+18h], r13
0x1402c6a6d  mov     [rax], r15w
0x1402c6a71  lea     rdx, [rbp+170h+pv]
0x1402c6a75  movq    rcx, xmm0
0x1402c6a7a  psrldq  xmm1, 8
0x1402c6a7f  movq    rax, xmm1
0x1402c6a84  cmp     rax, r13
0x1402c6a87  cmova   rdx, rcx
0x1402c6a8b  xorps   xmm0, xmm0
0x1402c6a8e  movups  [rsp+270h+var_218+8], xmm0
0x1402c6a93  mov     [rsp+270h+var_200], r15
0x1402c6a98  mov     [rsp+270h+var_1F8], r15
0x1402c6a9d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1402c6aa1  inc     r8
0x1402c6aa4  cmp     [rdx+r8*2], r15w
0x1402c6aa9  jnz     short loc_1402C6AA1
0x1402c6aab  lea     rcx, [rsp+270h+var_218+8]
0x1402c6ab0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c6ab5  nop
0x1402c6ab6  movss   dword ptr [rsp+270h+ppv], xmm9
0x1402c6abd  xorps   xmm3, xmm3
0x1402c6ac0  movaps  xmm2, xmm7
0x1402c6ac3  lea     rdx, [rsp+270h+var_218+8]
0x1402c6ac8  lea     rcx, [rbp+170h+var_140]
0x1402c6acc  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1402c6ad1  nop
0x1402c6ad2  lea     rcx, [rsp+270h+var_218+8]
0x1402c6ad7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6adc  nop
0x1402c6add  lea     rcx, [rbp+170h+pv]
0x1402c6ae1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6ae6  nop
0x1402c6ae7  lea     rcx, [rbp+170h+var_1B0]
0x1402c6aeb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6af0  nop
0x1402c6af1  lea     rcx, [rbp+170h+var_1F0]
0x1402c6af5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6afa  nop
0x1402c6afb  lea     rcx, [rsp+270h+Src+8]
0x1402c6b00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6b05  nop
0x1402c6b06  lea     rcx, [rbp+170h+var_1D0]
0x1402c6b0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6b0f  mov     rdx, rsi; unsigned __int64
0x1402c6b12  mov     rcx, [r14+8]; this
0x1402c6b16  call    ?QueryPastDowntimeDurationSeconds@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(unsigned __int64)
0x1402c6b1b  xorps   xmm7, xmm7
0x1402c6b1e  cvtsd2ss xmm7, xmm0
0x1402c6b22  mov     edx, edi
0x1402c6b24  lea     rcx, [rbp+170h+var_1B0]
0x1402c6b28  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1402c6b2d  mov     rbx, rax
0x1402c6b30  xorps   xmm0, xmm0
0x1402c6b33  movups  [rsp+270h+Src+8], xmm0
0x1402c6b38  mov     [rsp+270h+var_220], r15
0x1402c6b3d  mov     qword ptr [rsp+270h+var_218], r15
0x1402c6b42  mov     r8d, 5
0x1402c6b48  lea     rdx, aRseti; "RSeTi"
0x1402c6b4f  lea     rcx, [rsp+270h+Src+8]
0x1402c6b54  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c6b59  nop
0x1402c6b5a  mov     r8, r12
0x1402c6b5d  lea     rdx, aN; "N"
0x1402c6b64  lea     rcx, [rsp+270h+Src+8]; Src
0x1402c6b69  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c6b6e  movups  xmm0, xmmword ptr [rax]
0x1402c6b71  movups  xmmword ptr [rbp+170h+pv], xmm0
0x1402c6b75  movups  xmm1, xmmword ptr [rax+10h]
0x1402c6b79  movups  [rbp+170h+var_160], xmm1
0x1402c6b7d  mov     [rax+10h], r15
0x1402c6b81  mov     [rax+18h], r13
0x1402c6b85  mov     [rax], r15w
0x1402c6b89  mov     r8, rbx
0x1402c6b8c  lea     rdx, [rbp+170h+pv]
0x1402c6b90  lea     rcx, [rbp+170h+var_1D0]
0x1402c6b94  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1402c6b99  nop
0x1402c6b9a  mov     r8d, 2
0x1402c6ba0  lea     rdx, aV1; "V1"
0x1402c6ba7  mov     rcx, rax; Src
0x1402c6baa  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c6baf  movups  xmm0, xmmword ptr [rax]
0x1402c6bb2  movups  [rbp+170h+var_1F0], xmm0
0x1402c6bb6  movups  xmm1, xmmword ptr [rax+10h]
0x1402c6bba  movups  [rbp+170h+var_1E0], xmm1
0x1402c6bbe  mov     [rax+10h], r15
0x1402c6bc2  mov     [rax+18h], r13
0x1402c6bc6  mov     [rax], r15w
0x1402c6bca  lea     rdx, [rbp+170h+var_1F0]
0x1402c6bce  movq    rcx, xmm0
0x1402c6bd3  psrldq  xmm1, 8
0x1402c6bd8  movq    rax, xmm1
0x1402c6bdd  cmp     rax, r13
0x1402c6be0  cmova   rdx, rcx
0x1402c6be4  xorps   xmm0, xmm0
0x1402c6be7  movups  [rsp+270h+var_218+8], xmm0
0x1402c6bec  mov     [rsp+270h+var_200], r15
0x1402c6bf1  mov     [rsp+270h+var_1F8], r15
0x1402c6bf6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1402c6bfa  inc     r8
0x1402c6bfd  cmp     [rdx+r8*2], r15w
0x1402c6c02  jnz     short loc_1402C6BFA
0x1402c6c04  lea     rcx, [rsp+270h+var_218+8]
0x1402c6c09  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c6c0e  nop
0x1402c6c0f  movss   dword ptr [rsp+270h+ppv], xmm10
0x1402c6c16  xorps   xmm3, xmm3
0x1402c6c19  movaps  xmm2, xmm7
0x1402c6c1c  lea     rdx, [rsp+270h+var_218+8]
0x1402c6c21  lea     rcx, [rbp+170h+var_140]
0x1402c6c25  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1402c6c2a  nop
0x1402c6c2b  lea     rcx, [rsp+270h+var_218+8]
0x1402c6c30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6c35  nop
0x1402c6c36  lea     rcx, [rbp+170h+var_1F0]
0x1402c6c3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6c3f  nop
0x1402c6c40  lea     rcx, [rbp+170h+var_1D0]
0x1402c6c44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6c49  nop
0x1402c6c4a  lea     rcx, [rbp+170h+pv]
0x1402c6c4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6c53  nop
0x1402c6c54  lea     rcx, [rsp+270h+Src+8]
0x1402c6c59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6c5e  nop
0x1402c6c5f  lea     rcx, [rbp+170h+var_1B0]
0x1402c6c63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c6c68  mov     rdx, rsi; unsigned __int64
0x1402c6c6b  mov     rcx, [r14+8]; this
0x1402c6c6f  call    ?QueryPastDowntimeTotalSizeUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(unsigned __int64)
0x1402c6c74  xorps   xmm7, xmm7
0x1402c6c77  cvtsd2ss xmm7, xmm0
0x1402c6c7b  mov     edx, edi
0x1402c6c7d  lea     rcx, [rbp+170h+var_1B0]
0x1402c6c81  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1402c6c86  mov     rbx, rax
  ... truncated ...
```
