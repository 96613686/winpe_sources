# Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::EvaluateUPMLModel2(float)

- ea: `0x1402c75b8`
- end: `0x1402c863c`
- name: `?EvaluateUPMLModel2@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@AEAA?AU?$pair@MV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@M@Z`
- size: `4228`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1402c5c30`

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
- `0x1402c5abc`
- `0x1402c66b8`
- `0x1402c75b8`
- `0x1402c9320`
- `0x140379070`
- `0x1403790cc`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402c7686`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1402c7686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c81de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c8237`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c835a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c83b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c8418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c81de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c8237`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c835a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c83b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1402c8418`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1402c763b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1402c763b`

## string_xrefs

- `0x1402c81a1`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c831d`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c859d`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c85c7`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c85dc`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c85fa`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c8612`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`
- `0x1402c862a`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\QualityUpdateDowntimeEvaluator.cpp`

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
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rax
  void *v29; // rax
  __int64 v30; // rax
  __int128 *v31; // xmm0_8
  __m128i v32; // xmm1
  __int128 *v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rbx
  __int64 v42; // rax
  void *v43; // rax
  __int64 v44; // rax
  __int128 *v45; // xmm0_8
  __m128i v46; // xmm1
  __int128 *v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rbx
  __int64 v56; // rax
  void *v57; // rax
  __int64 v58; // rax
  __int128 *v59; // xmm0_8
  __m128i v60; // xmm1
  __int128 *v61; // rdx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rbx
  __int64 v70; // rax
  void *v71; // rax
  __int64 v72; // rax
  __int128 *v73; // xmm0_8
  __m128i v74; // xmm1
  __int128 *v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // rbx
  __int64 v84; // rax
  void *v85; // rax
  __int64 v86; // rax
  __int128 *v87; // xmm0_8
  __m128i v88; // xmm1
  __int128 *v89; // rdx
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // rdx
  __int64 v93; // rdx
  __int64 v94; // rdx
  __int64 v95; // rdx
  __int64 v96; // rdx
  LPVOID v97; // rbx
  __int64 (__fastcall *v98)(LPVOID, unsigned __int64, _QWORD, const wchar_t *); // rsi
  _QWORD *v99; // rax
  int v100; // eax
  __int64 v101; // rbx
  __int64 (__fastcall *v102)(__int64, _QWORD, __int64, const wchar_t *); // rsi
  _QWORD *v103; // rax
  int v104; // eax
  int v105; // ebx
  bool v106; // bl
  void *v107; // rcx
  void *v108; // rcx
  void (*v109)(void); // rax
  __int64 v110; // rbx
  __int64 (__fastcall *v111)(__int64, _QWORD, __int64, const wchar_t *); // rsi
  _QWORD *v112; // rax
  int v113; // eax
  int v114; // ebx
  bool v115; // bl
  void *v116; // rcx
  void *v117; // rcx
  void *v118; // rcx
  LPVOID v119; // rbx
  __int64 (__fastcall *v120)(LPVOID, __int64, _QWORD, const wchar_t *); // rsi
  _QWORD *v121; // rax
  int v122; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  int ppvb; // [rsp+28h] [rbp-E0h]
  int ppvc; // [rsp+28h] [rbp-E0h]
  int ppvd; // [rsp+28h] [rbp-E0h]
  __int128 Src_8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v130; // [rsp+58h] [rbp-B0h]
  __int64 v131; // [rsp+60h] [rbp-A8h]
  __int128 v132; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v133; // [rsp+78h] [rbp-90h]
  __int64 v134; // [rsp+80h] [rbp-88h]
  __int128 v135; // [rsp+88h] [rbp-80h] BYREF
  __m128i v136; // [rsp+98h] [rbp-70h]
  _BYTE v137[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v138[32]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 *v139; // [rsp+E8h] [rbp-20h] BYREF
  char v140; // [rsp+F0h] [rbp-18h]
  __int64 v141; // [rsp+100h] [rbp-8h] BYREF
  float v142; // [rsp+108h] [rbp+0h] BYREF
  char v143; // [rsp+10Ch] [rbp+4h] BYREF
  LPVOID pv[2]; // [rsp+118h] [rbp+10h] BYREF
  __m128i v145; // [rsp+128h] [rbp+20h]
  unsigned int v146; // [rsp+138h] [rbp+30h] BYREF
  LPVOID v147; // [rsp+140h] [rbp+38h] BYREF
  __int64 v148; // [rsp+148h] [rbp+40h] BYREF
  __int128 v149; // [rsp+150h] [rbp+48h] BYREF
  __int64 v150; // [rsp+160h] [rbp+58h]
  __int128 v151; // [rsp+168h] [rbp+60h] BYREF
  __int64 v152; // [rsp+178h] [rbp+70h]
  void *v153[12]; // [rsp+188h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v141 = a2;
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
  v147 = 0;
  v6 = CoCreateInstance(
         &GUID_df43bfd6_da50_426f_af99_5b63385f586a,
         0,
         4u,
         &GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b,
         &v147);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v149 = 0;
  v150 = 0;
  v139 = &v149;
  v140 = 1;
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
    Windows::RebootDowntime::InputBuilder::GetInputForKey(*(_QWORD *)(a1 + 8), &v132, &Src_8);
    if ( !(_BYTE)v133 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
    if ( SBYTE8(v132) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void_overloaded__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_2___Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_6_::_lambda_3____std::variant_unsigned_int_unsigned___int64__const___1_(retaddr);
    ppv = *(_DWORD *)(i + 68);
    Windows::RebootDowntime::AddCustomFeature(&v149, i);
  }
  v11 = 0;
  v12 = 0;
  do
  {
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v13 = std::to_wstring(v137, v11);
    Src_8 = 0;
    v130 = 0;
    v131 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC", 6);
    v14 = std::wstring::append(&Src_8);
    v135 = *(_OWORD *)v14;
    v136 = *(__m128i *)(v14 + 16);
    *(_QWORD *)(v14 + 16) = 0;
    *(_QWORD *)(v14 + 24) = 7;
    *(_WORD *)v14 = 0;
    v15 = (void *)std::operator+<wchar_t>(v138, &v135, v13);
    v16 = std::wstring::append(v15);
    *(_OWORD *)pv = *(_OWORD *)v16;
    v17 = (LPVOID *)pv[0];
    v145 = *(__m128i *)(v16 + 16);
    v18 = v145;
    *(_QWORD *)(v16 + 16) = 0;
    *(_QWORD *)(v16 + 24) = 7;
    *(_WORD *)v16 = 0;
    v19 = pv;
    if ( _mm_srli_si128(v18, 8).m128i_u64[0] > 7 )
      v19 = v17;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    std::wstring::_Construct<1,wchar_t const *>(&v132, v19, v20);
    Windows::RebootDowntime::AddCustomFeature(&v149, &v132);
    std::wstring::~wstring(&v132, v21);
    std::wstring::~wstring(pv, v22);
    std::wstring::~wstring(v138, v23);
    std::wstring::~wstring(&v135, v24);
    std::wstring::~wstring(&Src_8, v25);
    std::wstring::~wstring(v137, v26);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v27 = std::to_wstring(v138, v11);
    Src_8 = 0;
    v130 = 0;
    v131 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTi", 5);
    v28 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v28;
    v145 = *(__m128i *)(v28 + 16);
    *(_QWORD *)(v28 + 16) = 0;
    *(_QWORD *)(v28 + 24) = 7;
    *(_WORD *)v28 = 0;
    v29 = (void *)std::operator+<wchar_t>(v137, pv, v27);
    v30 = std::wstring::append(v29);
    v135 = *(_OWORD *)v30;
    v31 = (__int128 *)v135;
    v136 = *(__m128i *)(v30 + 16);
    v32 = v136;
    *(_QWORD *)(v30 + 16) = 0;
    *(_QWORD *)(v30 + 24) = 7;
    *(_WORD *)v30 = 0;
    v33 = &v135;
    if ( _mm_srli_si128(v32, 8).m128i_u64[0] > 7 )
      v33 = v31;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    std::wstring::_Construct<1,wchar_t const *>(&v132, v33, v34);
    Windows::RebootDowntime::AddCustomFeature(&v149, &v132);
    std::wstring::~wstring(&v132, v35);
    std::wstring::~wstring(&v135, v36);
    std::wstring::~wstring(v137, v37);
    std::wstring::~wstring(pv, v38);
    std::wstring::~wstring(&Src_8, v39);
    std::wstring::~wstring(v138, v40);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v41 = std::to_wstring(v138, v11);
    Src_8 = 0;
    v130 = 0;
    v131 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUS", 6);
    v42 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v42;
    v145 = *(__m128i *)(v42 + 16);
    *(_QWORD *)(v42 + 16) = 0;
    *(_QWORD *)(v42 + 24) = 7;
    *(_WORD *)v42 = 0;
    v43 = (void *)std::operator+<wchar_t>(v137, pv, v41);
    v44 = std::wstring::append(v43);
    v135 = *(_OWORD *)v44;
    v45 = (__int128 *)v135;
    v136 = *(__m128i *)(v44 + 16);
    v46 = v136;
    *(_QWORD *)(v44 + 16) = 0;
    *(_QWORD *)(v44 + 24) = 7;
    *(_WORD *)v44 = 0;
    v47 = &v135;
    if ( _mm_srli_si128(v46, 8).m128i_u64[0] > 7 )
      v47 = v45;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)v47 + v48) );
    std::wstring::_Construct<1,wchar_t const *>(&v132, v47, v48);
    Windows::RebootDowntime::AddCustomFeature(&v149, &v132);
    std::wstring::~wstring(&v132, v49);
    std::wstring::~wstring(&v135, v50);
    std::wstring::~wstring(v137, v51);
    std::wstring::~wstring(pv, v52);
    std::wstring::~wstring(&Src_8, v53);
    std::wstring::~wstring(v138, v54);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v55 = std::to_wstring(v138, v11);
    Src_8 = 0;
    v130 = 0;
    v131 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC", 6);
    v56 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v56;
    v145 = *(__m128i *)(v56 + 16);
    *(_QWORD *)(v56 + 16) = 0;
    *(_QWORD *)(v56 + 24) = 7;
    *(_WORD *)v56 = 0;
    v57 = (void *)std::operator+<wchar_t>(v137, pv, v55);
    v58 = std::wstring::append(v57);
    v135 = *(_OWORD *)v58;
    v59 = (__int128 *)v135;
    v136 = *(__m128i *)(v58 + 16);
    v60 = v136;
    *(_QWORD *)(v58 + 16) = 0;
    *(_QWORD *)(v58 + 24) = 7;
    *(_WORD *)v58 = 0;
    v61 = &v135;
    if ( _mm_srli_si128(v60, 8).m128i_u64[0] > 7 )
      v61 = v59;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    v62 = -1;
    do
      ++v62;
    while ( *((_WORD *)v61 + v62) );
    std::wstring::_Construct<1,wchar_t const *>(&v132, v61, v62);
    Windows::RebootDowntime::AddCustomFeature(&v149, &v132);
    std::wstring::~wstring(&v132, v63);
    std::wstring::~wstring(&v135, v64);
    std::wstring::~wstring(v137, v65);
    std::wstring::~wstring(pv, v66);
    std::wstring::~wstring(&Src_8, v67);
    std::wstring::~wstring(v138, v68);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasQUPresent(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v69 = std::to_wstring(v138, v11);
    Src_8 = 0;
    v130 = 0;
    v131 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeQU", 5);
    v70 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v70;
    v145 = *(__m128i *)(v70 + 16);
    *(_QWORD *)(v70 + 16) = 0;
    *(_QWORD *)(v70 + 24) = 7;
    *(_WORD *)v70 = 0;
    v71 = (void *)std::operator+<wchar_t>(v137, pv, v69);
    v72 = std::wstring::append(v71);
    v135 = *(_OWORD *)v72;
    v73 = (__int128 *)v135;
    v136 = *(__m128i *)(v72 + 16);
    v74 = v136;
    *(_QWORD *)(v72 + 16) = 0;
    *(_QWORD *)(v72 + 24) = 7;
    *(_WORD *)v72 = 0;
    v75 = &v135;
    if ( _mm_srli_si128(v74, 8).m128i_u64[0] > 7 )
      v75 = v73;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    v76 = -1;
    do
      ++v76;
    while ( *((_WORD *)v75 + v76) );
    std::wstring::_Construct<1,wchar_t const *>(&v132, v75, v76);
    Windows::RebootDowntime::AddCustomFeature(&v149, &v132);
    std::wstring::~wstring(&v132, v77);
    std::wstring::~wstring(&v135, v78);
    std::wstring::~wstring(v137, v79);
    std::wstring::~wstring(pv, v80);
    std::wstring::~wstring(&Src_8, v81);
    std::wstring::~wstring(v138, v82);
    Windows::RebootDowntime::InputBuilder::QueryPastDowntimeWasFUPresent(
      *(Windows::RebootDowntime::InputBuilder **)(a1 + 8),
      v12);
    v83 = std::to_wstring(v138, v11);
    Src_8 = 0;
    v130 = 0;
    v131 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeFU", 5);
    v84 = std::wstring::append(&Src_8);
    *(_OWORD *)pv = *(_OWORD *)v84;
    v145 = *(__m128i *)(v84 + 16);
    *(_QWORD *)(v84 + 16) = 0;
    *(_QWORD *)(v84 + 24) = 7;
    *(_WORD *)v84 = 0;
    v85 = (void *)std::operator+<wchar_t>(v137, pv, v83);
    v86 = std::wstring::append(v85);
    v135 = *(_OWORD *)v86;
    v87 = (__int128 *)v135;
    v136 = *(__m128i *)(v86 + 16);
    v88 = v136;
    *(_QWORD *)(v86 + 16) = 0;
    *(_QWORD *)(v86 + 24) = 7;
    *(_WORD *)v86 = 0;
    v89 = &v135;
    if ( _mm_srli_si128(v88, 8).m128i_u64[0] > 7 )
      v89 = v87;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    v90 = -1;
    do
      ++v90;
    while ( *((_WORD *)v89 + v90) );
    std::wstring::_Construct<1,wchar_t const *>(&v132, v89, v90);
    Windows::RebootDowntime::AddCustomFeature(&v149, &v132);
    std::wstring::~wstring(&v132, v91);
    std::wstring::~wstring(&v135, v92);
    std::wstring::~wstring(v137, v93);
    std::wstring::~wstring(pv, v94);
    std::wstring::~wstring(&Src_8, v95);
    std::wstring::~wstring(v138, v96);
    ++v11;
    ++v12;
  }
  while ( (int)v11 < 6 );
  memset(v153, 0, sizeof(v153));
  Windows::CorrelationVector::CorrelationVector((Windows::CorrelationVector *)v153);
  v146 = 0;
  v141 = 0;
  v97 = v147;
  v98 = *(__int64 (__fastcall **)(LPVOID, unsigned __int64, _QWORD, const wchar_t *))(*(_QWORD *)v147 + 40LL);
  v99 = (_QWORD *)Windows::CorrelationVector::to_string(v153, v137);
  if ( v99[3] > 0xFu )
    v99 = (_QWORD *)*v99;
  ppva = (int)v99;
  v100 = v98(v97, 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v149 + 1) - v149) >> 3), v149, L"QU202506");
  if ( v100 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v100,
      ppva);
  std::string::_Tidy_deallocate(v137);
  *(_QWORD *)&v132 = &v141;
  *((_QWORD *)&v132 + 1) = &v146;
  LOBYTE(v133) = 1;
  v148 = 0;
  if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))v147)(
         v147,
         &GUID_68538015_9da0_4cb8_a6af_d52af2ea035b,
         &v148) >= 0 )
  {
    v142 = 0.0;
    pv[0] = 0;
    v101 = v148;
    v102 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v148 + 48LL);
    *(_QWORD *)&Src_8 = pv;
    *((_QWORD *)&Src_8 + 1) = 0;
    LOBYTE(v130) = 1;
    v103 = (_QWORD *)Windows::CorrelationVector::to_string(v153, v137);
    if ( v103[3] > 0xFu )
      v103 = (_QWORD *)*v103;
    ppvb = (int)v103;
    v104 = v102(v101, v146, v141, L"QUDowntimeUPMLV2");
    v105 = v104;
    if ( v104 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)(unsigned int)v104,
        ppvb);
    v106 = v105 >= 0;
    std::string::_Tidy_deallocate(v137);
    if ( (_BYTE)v130 )
    {
      v107 = *(void **)Src_8;
      *(_QWORD *)Src_8 = *((_QWORD *)&Src_8 + 1);
      if ( v107 )
        CoTaskMemFree(v107);
    }
    if ( v106 )
    {
      if ( LODWORD(v142) != 1 )
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
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8, L"QUDowntimeUPMLV2", 16);
      v108 = pv[0];
      pv[0] = 0;
      if ( v108 )
        CoTaskMemFree(v108);
      if ( v148 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v148 + 16LL))(v148);
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v132);
      if ( v153[1] )
        operator delete(v153[1]);
      goto LABEL_55;
    }
    v110 = v148;
    v111 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v148 + 48LL);
    *(_QWORD *)&Src_8 = pv;
    *((_QWORD *)&Src_8 + 1) = 0;
    LOBYTE(v130) = 1;
    v112 = (_QWORD *)Windows::CorrelationVector::to_string(v153, v137);
    if ( v112[3] > 0xFu )
      v112 = (_QWORD *)*v112;
    ppvc = (int)v112;
    v113 = v111(v110, v146, v141, L"QUDowntimeUPMLV1");
    v114 = v113;
    if ( v113 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
        (const char *)(unsigned int)v113,
        ppvc);
    v115 = v114 >= 0;
    std::string::_Tidy_deallocate(v137);
    if ( (_BYTE)v130 )
    {
      v116 = *(void **)Src_8;
      *(_QWORD *)Src_8 = *((_QWORD *)&Src_8 + 1);
      if ( v116 )
        CoTaskMemFree(v116);
    }
    if ( v115 )
    {
      if ( LODWORD(v142) != 1 )
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
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8, L"QUDowntimeUPMLV1", 16);
      v117 = pv[0];
      pv[0] = 0;
      if ( v117 )
        CoTaskMemFree(v117);
      if ( v148 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v148 + 16LL))(v148);
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v132);
      if ( v153[1] )
        operator delete(v153[1]);
LABEL_55:
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v139);
      std::vector<CustomFeature>::~vector<CustomFeature>(&v149);
      if ( v147 )
      {
        v109 = *(void (**)(void))(*(_QWORD *)v147 + 16LL);
LABEL_84:
        v109();
        return a2;
      }
      return a2;
    }
    v118 = pv[0];
    pv[0] = 0;
    if ( v118 )
      CoTaskMemFree(v118);
  }
  v151 = 0;
  v152 = 0;
  v142 = a3;
  pv[0] = &v142;
  pv[1] = &v143;
  Src_8 = *(_OWORD *)pv;
  std::vector<float>::vector<float>(&v151, &Src_8);
  v119 = v147;
  v120 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v147 + 32LL);
  v121 = (_QWORD *)Windows::CorrelationVector::to_string(v153, v137);
  if ( v121[3] > 0xFu )
    v121 = (_QWORD *)*v121;
  ppvd = (int)v121;
  v122 = v120(v119, (__int64)(*((_QWORD *)&v151 + 1) - v151) >> 2, v151, L"QU202506");
  if ( v122 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\QualityUpdateDowntimeEvaluator.cpp",
      (const char *)(unsigned int)v122,
      ppvd);
  std::string::_Tidy_deallocate(v137);
  *(float *)a2 = a3;
  *(_OWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a2 + 8, L"QU202506", 8);
  std::vector<std::_Chrono_spec<wchar_t>>::~vector<std::_Chrono_spec<wchar_t>>(&v151);
  if ( v148 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v148 + 16LL))(v148);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v132);
  if ( v153[1] )
    operator delete(v153[1]);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_1___(&v139);
  std::vector<CustomFeature>::~vector<CustomFeature>(&v149);
  if ( v147 )
  {
    v109 = *(void (**)(void))(*(_QWORD *)v147 + 16LL);
    goto LABEL_84;
  }
  return a2;
}

```

## disassembly

```asm
0x1402c75b8  mov     rax, rsp
0x1402c75bb  mov     [rax+18h], rbx
0x1402c75bf  mov     [rax+10h], rdx
0x1402c75c3  push    rbp
0x1402c75c4  push    rsi
0x1402c75c5  push    rdi
0x1402c75c6  push    r12
0x1402c75c8  push    r13
0x1402c75ca  push    r14
0x1402c75cc  push    r15
0x1402c75ce  lea     rbp, [rax-198h]
0x1402c75d5  sub     rsp, 260h
0x1402c75dc  movaps  xmmword ptr [rax-48h], xmm6
0x1402c75e0  movaps  xmmword ptr [rax-58h], xmm7
0x1402c75e4  movaps  xmmword ptr [rax-68h], xmm8
0x1402c75e9  movaps  xmmword ptr [rax-78h], xmm9
0x1402c75ee  movaps  xmmword ptr [rax-88h], xmm10
0x1402c75f6  movaps  xmmword ptr [rax-98h], xmm11
0x1402c75fe  movaps  xmmword ptr [rax-0A8h], xmm12
0x1402c7606  mov     rax, cs:__security_cookie
0x1402c760d  xor     rax, rsp
0x1402c7610  mov     [rbp+190h+var_B0], rax
0x1402c7617  movaps  xmm7, xmm2
0x1402c761a  mov     rdi, rdx
0x1402c761d  mov     r15, rcx
0x1402c7620  mov     [rbp+190h+var_198], rdx
0x1402c7624  xor     r12d, r12d
0x1402c7627  xor     r9d, r9d; Context
0x1402c762a  xor     r8d, r8d; Parameter
0x1402c762d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1402c7634  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x1402c763b  call    cs:__imp_InitOnceExecuteOnce
0x1402c7641  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, r12b; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x1402c7648  jz      short loc_1402C7665
0x1402c764a  mov     rbx, [rbp+198h]
0x1402c7651  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML>::GetImpl(void)'::`2'::impl
0x1402c7658  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QUV2UPML>::__private_IsEnabled(wil::ReportingKind)
0x1402c765d  test    al, al
0x1402c765f  jz      loc_1402C85AF
0x1402c7665  mov     [rbp+190h+var_158], r12
0x1402c7669  lea     rax, [rbp+190h+var_158]
0x1402c766d  mov     [rsp+290h+ppv], rax; int
0x1402c7672  lea     r9, _GUID_b0f85396_31fe_4a4a_9d82_691590c7d91b; riid
0x1402c7679  xor     edx, edx; pUnkOuter
0x1402c767b  lea     r8d, [rdx+4]; dwClsContext
0x1402c767f  lea     rcx, _GUID_df43bfd6_da50_426f_af99_5b63385f586a; rclsid
0x1402c7686  call    cs:__imp_CoCreateInstance
0x1402c768c  mov     rcx, [rbp+198h]; this
0x1402c7693  test    eax, eax
0x1402c7695  js      loc_1402C85C4
0x1402c769b  xorps   xmm1, xmm1
0x1402c769e  movdqu  [rbp+190h+var_148], xmm1
0x1402c76a3  mov     [rbp+190h+var_138], r12
0x1402c76a7  lea     rax, [rbp+190h+var_148]
0x1402c76ab  mov     [rbp+190h+var_1B0], rax
0x1402c76af  mov     r13d, 1
0x1402c76b5  mov     [rbp+190h+var_1A8], r13b
0x1402c76b9  mov     rbx, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1402c76c0  mov     rsi, qword ptr cs:?m_currentStateFeatures3@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@0V?$vector@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@V?$allocator@UQUFeature@QualityUpdateDowntimeEvaluator@RebootDowntime@Windows@@@std@@@std@@B+8; std::vector<Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::QUFeature> const Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::m_currentStateFeatures3
0x1402c76c7  cmp     rbx, rsi
0x1402c76ca  jz      loc_1402C77A0
0x1402c76d0  lea     r14d, [r13+3Fh]
0x1402c76d4  mov     rcx, [rbx+30h]
0x1402c76d8  lea     rax, [rbx+20h]
0x1402c76dc  cmp     qword ptr [rbx+38h], 7
0x1402c76e1  jbe     short loc_1402C76E6
0x1402c76e3  mov     rax, [rax]
0x1402c76e6  mov     [rbp+190h+pv], rax
0x1402c76ea  mov     [rbp+190h+pv+8], rcx
0x1402c76ee  movaps  xmm0, xmmword ptr [rbp+190h+pv]
0x1402c76f2  movdqa  [rsp+290h+Src+8], xmm0
0x1402c76f8  lea     r8, [rsp+290h+Src+8]
0x1402c76fd  lea     rdx, [rsp+290h+var_238+8]
0x1402c7702  mov     rcx, [r15+8]
0x1402c7706  call    ?GetInputForKey@InputBuilder@RebootDowntime@Windows@@QEAA?AV?$optional@V?$variant@I_K@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::RebootDowntime::InputBuilder::GetInputForKey(wil::basic_zstring_view<wchar_t>)
0x1402c770b  mov     rcx, [rbp+198h]; this
0x1402c7712  mov     al, byte ptr [rsp+290h+var_220]
0x1402c7716  test    al, al
0x1402c7718  jz      loc_1402C85F4
0x1402c771e  movsx   rax, byte ptr [rsp+290h+var_228]
0x1402c7724  add     rax, r13
0x1402c7727  jz      loc_1402C85EE
0x1402c772d  lea     r9, [rbp+190h+var_148]
0x1402c7731  xorps   xmm2, xmm2
0x1402c7734  cmp     rax, 1
0x1402c7738  jz      short loc_1402C7762
0x1402c773a  mov     rcx, qword ptr [rsp+290h+var_238+8]
0x1402c773f  test    rcx, rcx
0x1402c7742  js      short loc_1402C774B
0x1402c7744  cvtsi2ss xmm2, rcx
0x1402c7749  jmp     short loc_1402C776B
0x1402c774b  mov     rax, rcx
0x1402c774e  shr     rax, 1
0x1402c7751  and     rcx, r13
0x1402c7754  or      rax, rcx
0x1402c7757  cvtsi2ss xmm2, rax
0x1402c775c  addss   xmm2, xmm2
0x1402c7760  jmp     short loc_1402C776B
0x1402c7762  mov     eax, dword ptr [rsp+290h+var_238+8]
0x1402c7766  cvtsi2ss xmm2, rax
0x1402c776b  mov     r8d, 44h ; 'D'
0x1402c7771  mov     rdx, rbx
0x1402c7774  mov     rcx, r14
0x1402c7777  mov     rax, rbx
0x1402c777a  movss   xmm0, dword ptr [rbx+r8]
0x1402c7780  movss   dword ptr [rsp+290h+ppv], xmm0
0x1402c7786  movss   xmm3, dword ptr [rbx+rcx]
0x1402c778b  mov     rcx, r9
0x1402c778e  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1402c7793  add     rbx, 48h ; 'H'
0x1402c7797  cmp     rbx, rsi
0x1402c779a  jnz     loc_1402C76D4
0x1402c77a0  mov     esi, r12d
0x1402c77a3  mov     r14, r12
0x1402c77a6  movss   xmm9, cs:__real@42c80000
0x1402c77af  movss   xmm10, cs:__real@46610000
0x1402c77b8  movss   xmm11, cs:__real@4e8f0d18
0x1402c77c1  movss   xmm12, cs:__real@41a00000
0x1402c77ca  movss   xmm8, cs:__real@3f800000
0x1402c77d3  mov     rdx, r14; unsigned __int64
0x1402c77d6  mov     rcx, [r15+8]; this
0x1402c77da  call    ?QueryPastDowntimeTotalNumerOfUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalNumerOfUpdates(unsigned __int64)
0x1402c77df  xorps   xmm6, xmm6
0x1402c77e2  cvtsd2ss xmm6, xmm0
0x1402c77e6  mov     edx, esi
0x1402c77e8  lea     rcx, [rbp+190h+var_1F0]
0x1402c77ec  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1402c77f1  mov     rbx, rax
0x1402c77f4  xorps   xmm0, xmm0
0x1402c77f7  movups  [rsp+290h+Src+8], xmm0
0x1402c77fc  mov     [rsp+290h+var_240], r12
0x1402c7801  mov     qword ptr [rsp+290h+var_238], r12
0x1402c7806  mov     r8d, 6
0x1402c780c  lea     rdx, aRsetuc; "RSeTUC"
0x1402c7813  lea     rcx, [rsp+290h+Src+8]
0x1402c7818  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c781d  nop
0x1402c781e  mov     r8, r13
0x1402c7821  lea     rdx, aN; "N"
0x1402c7828  lea     rcx, [rsp+290h+Src+8]; Src
0x1402c782d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c7832  movups  xmm0, xmmword ptr [rax]
0x1402c7835  movups  [rbp+190h+var_210], xmm0
0x1402c7839  movups  xmm1, xmmword ptr [rax+10h]
0x1402c783d  movups  [rbp+190h+var_200], xmm1
0x1402c7841  mov     [rax+10h], r12
0x1402c7845  mov     qword ptr [rax+18h], 7
0x1402c784d  mov     [rax], r12w
0x1402c7851  mov     r8, rbx
0x1402c7854  lea     rdx, [rbp+190h+var_210]
0x1402c7858  lea     rcx, [rbp+190h+var_1D0]
0x1402c785c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1402c7861  nop
0x1402c7862  mov     r8d, 2
0x1402c7868  lea     rdx, aV2; "V2"
0x1402c786f  mov     rcx, rax; Src
0x1402c7872  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c7877  movups  xmm0, xmmword ptr [rax]
0x1402c787a  movups  xmmword ptr [rbp+190h+pv], xmm0
0x1402c787e  movups  xmm1, xmmword ptr [rax+10h]
0x1402c7882  movups  [rbp+190h+var_170], xmm1
0x1402c7886  mov     [rax+10h], r12
0x1402c788a  mov     qword ptr [rax+18h], 7
0x1402c7892  mov     [rax], r12w
0x1402c7896  lea     rdx, [rbp+190h+pv]
0x1402c789a  movq    rcx, xmm0
0x1402c789f  psrldq  xmm1, 8
0x1402c78a4  movq    rax, xmm1
0x1402c78a9  cmp     rax, 7
0x1402c78ad  cmova   rdx, rcx
0x1402c78b1  xorps   xmm0, xmm0
0x1402c78b4  movups  [rsp+290h+var_238+8], xmm0
0x1402c78b9  mov     [rsp+290h+var_220], r12
0x1402c78be  mov     [rsp+290h+var_218], r12
0x1402c78c3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1402c78c7  inc     r8
0x1402c78ca  cmp     [rdx+r8*2], r12w
0x1402c78cf  jnz     short loc_1402C78C7
0x1402c78d1  lea     rcx, [rsp+290h+var_238+8]
0x1402c78d6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c78db  nop
0x1402c78dc  movss   dword ptr [rsp+290h+ppv], xmm9
0x1402c78e3  xorps   xmm3, xmm3
0x1402c78e6  movaps  xmm2, xmm6
0x1402c78e9  lea     rdx, [rsp+290h+var_238+8]
0x1402c78ee  lea     rcx, [rbp+190h+var_148]
0x1402c78f2  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1402c78f7  nop
0x1402c78f8  lea     rcx, [rsp+290h+var_238+8]
0x1402c78fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7902  nop
0x1402c7903  lea     rcx, [rbp+190h+pv]
0x1402c7907  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c790c  nop
0x1402c790d  lea     rcx, [rbp+190h+var_1D0]
0x1402c7911  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7916  nop
0x1402c7917  lea     rcx, [rbp+190h+var_210]
0x1402c791b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7920  nop
0x1402c7921  lea     rcx, [rsp+290h+Src+8]
0x1402c7926  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c792b  nop
0x1402c792c  lea     rcx, [rbp+190h+var_1F0]
0x1402c7930  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7935  mov     rdx, r14; unsigned __int64
0x1402c7938  mov     rcx, [r15+8]; this
0x1402c793c  call    ?QueryPastDowntimeDurationSeconds@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeDurationSeconds(unsigned __int64)
0x1402c7941  xorps   xmm6, xmm6
0x1402c7944  cvtsd2ss xmm6, xmm0
0x1402c7948  mov     edx, esi
0x1402c794a  lea     rcx, [rbp+190h+var_1D0]
0x1402c794e  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1402c7953  mov     rbx, rax
0x1402c7956  xorps   xmm0, xmm0
0x1402c7959  movups  [rsp+290h+Src+8], xmm0
0x1402c795e  mov     [rsp+290h+var_240], r12
0x1402c7963  mov     qword ptr [rsp+290h+var_238], r12
0x1402c7968  mov     r8d, 5
0x1402c796e  lea     rdx, aRseti; "RSeTi"
0x1402c7975  lea     rcx, [rsp+290h+Src+8]
0x1402c797a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c797f  nop
0x1402c7980  mov     r8, r13
0x1402c7983  lea     rdx, aN; "N"
0x1402c798a  lea     rcx, [rsp+290h+Src+8]; Src
0x1402c798f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c7994  movups  xmm0, xmmword ptr [rax]
0x1402c7997  movups  xmmword ptr [rbp+190h+pv], xmm0
0x1402c799b  movups  xmm1, xmmword ptr [rax+10h]
0x1402c799f  movups  [rbp+190h+var_170], xmm1
0x1402c79a3  mov     [rax+10h], r12
0x1402c79a7  mov     qword ptr [rax+18h], 7
0x1402c79af  mov     [rax], r12w
0x1402c79b3  mov     r8, rbx
0x1402c79b6  lea     rdx, [rbp+190h+pv]
0x1402c79ba  lea     rcx, [rbp+190h+var_1F0]
0x1402c79be  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1402c79c3  nop
0x1402c79c4  mov     r8d, 2
0x1402c79ca  lea     rdx, aV1; "V1"
0x1402c79d1  mov     rcx, rax; Src
0x1402c79d4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1402c79d9  movups  xmm0, xmmword ptr [rax]
0x1402c79dc  movups  [rbp+190h+var_210], xmm0
0x1402c79e0  movups  xmm1, xmmword ptr [rax+10h]
0x1402c79e4  movups  [rbp+190h+var_200], xmm1
0x1402c79e8  mov     [rax+10h], r12
0x1402c79ec  mov     qword ptr [rax+18h], 7
0x1402c79f4  mov     [rax], r12w
0x1402c79f8  lea     rdx, [rbp+190h+var_210]
0x1402c79fc  movq    rcx, xmm0
0x1402c7a01  psrldq  xmm1, 8
0x1402c7a06  movq    rax, xmm1
0x1402c7a0b  cmp     rax, 7
0x1402c7a0f  cmova   rdx, rcx
0x1402c7a13  xorps   xmm0, xmm0
0x1402c7a16  movups  [rsp+290h+var_238+8], xmm0
0x1402c7a1b  mov     [rsp+290h+var_220], r12
0x1402c7a20  mov     [rsp+290h+var_218], r12
0x1402c7a25  or      r8, 0FFFFFFFFFFFFFFFFh
0x1402c7a29  inc     r8
0x1402c7a2c  cmp     [rdx+r8*2], r12w
0x1402c7a31  jnz     short loc_1402C7A29
0x1402c7a33  lea     rcx, [rsp+290h+var_238+8]
0x1402c7a38  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402c7a3d  nop
0x1402c7a3e  movss   dword ptr [rsp+290h+ppv], xmm10
0x1402c7a45  xorps   xmm3, xmm3
0x1402c7a48  movaps  xmm2, xmm6
0x1402c7a4b  lea     rdx, [rsp+290h+var_238+8]
0x1402c7a50  lea     rcx, [rbp+190h+var_148]
0x1402c7a54  call    ?AddCustomFeature@RebootDowntime@Windows@@YAXAEAV?$vector@UCustomFeature@@V?$allocator@UCustomFeature@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@MMM@Z; Windows::RebootDowntime::AddCustomFeature(std::vector<CustomFeature> &,std::wstring const &,float,float,float)
0x1402c7a59  nop
0x1402c7a5a  lea     rcx, [rsp+290h+var_238+8]
0x1402c7a5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7a64  nop
0x1402c7a65  lea     rcx, [rbp+190h+var_210]
0x1402c7a69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7a6e  nop
0x1402c7a6f  lea     rcx, [rbp+190h+var_1F0]
0x1402c7a73  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7a78  nop
0x1402c7a79  lea     rcx, [rbp+190h+pv]
0x1402c7a7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7a82  nop
0x1402c7a83  lea     rcx, [rsp+290h+Src+8]
0x1402c7a88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7a8d  nop
0x1402c7a8e  lea     rcx, [rbp+190h+var_1D0]
0x1402c7a92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402c7a97  mov     rdx, r14; unsigned __int64
0x1402c7a9a  mov     rcx, [r15+8]; this
0x1402c7a9e  call    ?QueryPastDowntimeTotalSizeUpdates@InputBuilder@RebootDowntime@Windows@@QEAAN_K@Z; Windows::RebootDowntime::InputBuilder::QueryPastDowntimeTotalSizeUpdates(unsigned __int64)
0x1402c7aa3  xorps   xmm6, xmm6
0x1402c7aa6  cvtsd2ss xmm6, xmm0
0x1402c7aaa  mov     edx, esi
0x1402c7aac  lea     rcx, [rbp+190h+var_1D0]
0x1402c7ab0  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1402c7ab5  mov     rbx, rax
  ... truncated ...
```
