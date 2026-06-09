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
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC");
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
    std::wstring::_Construct<1,wchar_t const *>(&v96, v19);
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
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTi");
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
    std::wstring::_Construct<1,wchar_t const *>(&v96, v27);
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
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUS");
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
    std::wstring::_Construct<1,wchar_t const *>(&v96, v35);
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
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeTUC");
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
    std::wstring::_Construct<1,wchar_t const *>(&v96, v43);
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
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeQU");
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
    std::wstring::_Construct<1,wchar_t const *>(&v96, v51);
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
    std::wstring::_Construct<1,wchar_t const *>(&Src_8, L"RSeFU");
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
    std::wstring::_Construct<1,wchar_t const *>(&v96, v59);
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
  std::string::_Tidy_deallocate(v101);
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
    std::string::_Tidy_deallocate(v101);
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
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8, L"QUDowntimeUPMLV2");
      v72 = pv[0];
      pv[0] = 0;
      if ( v72 )
        CoTaskMemFree(v72);
      if ( v112 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v96);
      if ( v117[1] )
        operator delete(v117[1]);
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
    std::string::_Tidy_deallocate(v101);
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
      std::wstring::_Construct<1,wchar_t const *>(a2 + 8, L"QUDowntimeUPMLV1");
      v81 = pv[0];
      pv[0] = 0;
      if ( v81 )
        CoTaskMemFree(v81);
      if ( v112 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
      wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v96);
      if ( v117[1] )
        operator delete(v117[1]);
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
  std::string::_Tidy_deallocate(v101);
  *(float *)a2 = a3;
  *(_OWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a2 + 8, L"QU202506");
  std::vector<std::_Chrono_spec<wchar_t>>::~vector<std::_Chrono_spec<wchar_t>>(&v115);
  if ( v112 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
  wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(&v96);
  if ( v117[1] )
    operator delete(v117[1]);
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
