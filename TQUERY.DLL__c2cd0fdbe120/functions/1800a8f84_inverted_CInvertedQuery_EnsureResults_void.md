# inverted::CInvertedQuery::_EnsureResults(void)

- ea: `0x1800a8f84`
- end: `0x1800aabea`
- name: `?_EnsureResults@CInvertedQuery@inverted@@AEAAXXZ`
- size: `7270`
- prototype: `void __fastcall(inverted::CInvertedQuery *__hidden this)`
- caller_count: `9`
- callee_count: `92`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a8610`
- `0x1800a8ea0`
- `0x1800a8ed0`
- `0x1800a8f00`
- `0x1800a8f30`
- `0x1800a8f60`
- `0x18010cb90`
- `0x18026b490`
- `0x18026b590`

## callees

- `0x18002f2c0`
- `0x180030a84`
- `0x1800324c8`
- `0x180036d60`
- `0x180038f08`
- `0x180047e78`
- `0x180048cc0`
- `0x18004d9d8`
- `0x180050858`
- `0x180056fd8`
- `0x180082120`
- `0x180087834`
- `0x180087880`
- `0x180088bc8`
- `0x18009d124`
- `0x18009e510`
- `0x18009e614`
- `0x1800a4af8`
- `0x1800a83e0`
- `0x1800a8f84`
- `0x1800ab364`
- `0x1800ae484`
- `0x1800d613c`
- `0x1800ebb44`
- `0x18010e10c`
- `0x180116190`
- `0x1801183f0`
- `0x18013cd74`
- `0x18013e868`
- `0x180143bdc`
- `0x180145ab0`
- `0x1801470bc`
- `0x1801470d4`
- `0x180147190`
- `0x18014e2ac`
- `0x18014e2f0`
- `0x1801535f0`
- `0x180153610`
- `0x18015365c`
- `0x1801774f0`
- `0x1801781b0`
- `0x180188d90`
- `0x180188e04`
- `0x1801895bc`
- `0x180189cce`
- `0x18019b924`
- `0x1801aa81c`
- `0x1801b0524`
- `0x1801b2c64`
- `0x1801b2d20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a9432`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a9432`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a9ab6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a9ca5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a9e9f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800aa128`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800aa31b`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800aa541`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a9ab6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a9ca5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800a9e9f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800aa128`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800aa31b`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800aa541`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800a920e`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800a920e`

## string_xrefs

- `0x1800aaacd`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800aaae3`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800aaaf9`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800aab0f`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800aab25`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800aab3b`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall inverted::CInvertedQuery::_EnsureResults(inverted::CInvertedQuery *this)
{
  volatile signed __int32 *v2; // rcx
  char *v3; // r14
  struct _GUID *v4; // rbx
  _QWORD *v5; // r13
  char *v6; // r12
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 *v13; // r15
  __int64 v14; // rbx
  unsigned __int64 v15; // rsi
  unsigned int v16; // eax
  int v17; // r8d
  __int64 v18; // rcx
  void **v19; // r13
  __int64 v20; // r8
  _QWORD *v21; // rax
  __int64 v22; // rdx
  void *v23; // rax
  __int64 v24; // rbx
  gsl::details *v25; // rcx
  __int64 v26; // r14
  void *v27; // rsi
  __int64 v28; // rsi
  __int64 v29; // r13
  struct _GUID v30; // xmm6
  struct _GUID v31; // xmm7
  unsigned __int8 date_argument; // r15
  int type; // ebx
  unsigned __int8 operation; // r12
  __int64 v35; // r14
  int v36; // ecx
  int v37; // ebx
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  int v41; // ebx
  __int64 v42; // xmm6_8
  unsigned __int64 i; // rsi
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rcx
  inverted::CInvertedQuery *v47; // rcx
  char IsEnabled; // al
  __int16 v49; // dx
  __int64 v50; // rbx
  unsigned int v51; // r14d
  unsigned int v52; // edx
  unsigned int v53; // eax
  _QWORD *v54; // r13
  unsigned int *v55; // r15
  __int64 v56; // rbx
  _QWORD *v57; // r12
  __int64 v58; // rax
  __int64 v59; // rdx
  void *v60; // rsi
  unsigned int v61; // ecx
  void *v62; // rax
  const char *v63; // r9
  _QWORD *v64; // rdx
  unsigned __int64 v65; // rcx
  void **v66; // rax
  unsigned __int64 v67; // rdx
  char v68; // r14
  __int64 v69; // rax
  struct _GUID *v70; // rdx
  unsigned int v71; // r14d
  unsigned int v72; // edx
  unsigned int v73; // eax
  _QWORD *v74; // r13
  unsigned int *v75; // r15
  __int64 v76; // rbx
  _QWORD *v77; // r12
  __int64 v78; // rax
  __int64 v79; // rdx
  void *v80; // rsi
  unsigned int v81; // ecx
  void *v82; // rax
  const char *v83; // r9
  _QWORD *v84; // rdx
  unsigned __int64 v85; // rcx
  void **v86; // rax
  unsigned __int64 v87; // rdx
  char v88; // r14
  __int64 v89; // rax
  unsigned int v90; // r14d
  unsigned int v91; // edx
  unsigned int v92; // eax
  _QWORD *v93; // r13
  unsigned int *v94; // r15
  __int64 v95; // rbx
  _QWORD *v96; // r12
  __int64 v97; // rax
  __int64 v98; // rdx
  void *v99; // rsi
  unsigned int v100; // ecx
  void *v101; // rax
  const char *v102; // r9
  _QWORD *v103; // rdx
  unsigned __int64 v104; // rcx
  void **v105; // rax
  unsigned __int64 v106; // rdx
  char v107; // r14
  __int64 v108; // rax
  char v109; // al
  __int64 v110; // r15
  __int16 v111; // dx
  __int64 v112; // rbx
  unsigned int v113; // r14d
  unsigned int v114; // edx
  unsigned int v115; // eax
  _QWORD *v116; // r13
  unsigned int *v117; // r15
  __int64 v118; // rbx
  _QWORD *v119; // r12
  __int64 v120; // rax
  __int64 v121; // rdx
  void *v122; // rsi
  unsigned int v123; // ecx
  void *v124; // rax
  const char *v125; // r9
  _QWORD *v126; // rdx
  unsigned __int64 v127; // rcx
  void **v128; // rax
  unsigned __int64 v129; // rdx
  char v130; // r14
  __int64 v131; // rax
  char *v132; // rdx
  unsigned int v133; // r14d
  unsigned int v134; // edx
  unsigned int v135; // eax
  _QWORD *v136; // r13
  unsigned int *v137; // r15
  __int64 v138; // rbx
  _QWORD *v139; // r12
  __int64 v140; // rax
  __int64 v141; // rdx
  void *v142; // rsi
  unsigned int v143; // ecx
  void *v144; // rax
  const char *v145; // r9
  _QWORD *v146; // rdx
  unsigned __int64 v147; // rcx
  void **v148; // rax
  unsigned __int64 v149; // rdx
  char v150; // r14
  __int64 v151; // rax
  __int64 v152; // rbx
  __int64 v153; // rsi
  unsigned int v154; // r14d
  unsigned int v155; // edx
  unsigned int v156; // eax
  _QWORD *v157; // r13
  unsigned int *v158; // r15
  __int64 v159; // rbx
  _QWORD *v160; // r12
  __int64 v161; // rax
  __int64 v162; // rdx
  void *v163; // rsi
  unsigned int v164; // ecx
  void *v165; // rax
  const char *v166; // r9
  _QWORD *v167; // rdx
  unsigned __int64 v168; // rcx
  void **v169; // rax
  unsigned __int64 v170; // rdx
  char v171; // r14
  __int64 v172; // rax
  __int64 v173; // rcx
  __int64 v174; // r8
  __int64 v175; // rcx
  __int64 v176; // r8
  __int64 v177; // rcx
  __int64 v178; // rsi
  unsigned __int64 k; // r14
  __int64 m; // rbx
  __int64 v181; // rcx
  unsigned int v182; // ebx
  _QWORD *v183; // rax
  __int64 v184; // rax
  unsigned int v185; // eax
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  DWORD LastError; // ebx
  __int64 v190; // rax
  int v191; // [rsp+20h] [rbp-428h]
  unsigned int v192; // [rsp+20h] [rbp-428h]
  unsigned int v193; // [rsp+40h] [rbp-408h] BYREF
  void *v194; // [rsp+48h] [rbp-400h] BYREF
  __int64 v195; // [rsp+50h] [rbp-3F8h] BYREF
  unsigned __int64 j; // [rsp+58h] [rbp-3F0h] BYREF
  struct _GUID v197; // [rsp+60h] [rbp-3E8h] BYREF
  __int64 v198; // [rsp+70h] [rbp-3D8h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-3D0h] BYREF
  _QWORD v200[2]; // [rsp+80h] [rbp-3C8h] BYREF
  struct _GUID v201; // [rsp+90h] [rbp-3B8h] BYREF
  inverted::CInvertedQuery *v202; // [rsp+A0h] [rbp-3A8h] BYREF
  __int64 v203; // [rsp+A8h] [rbp-3A0h] BYREF
  char v204[8]; // [rsp+B0h] [rbp-398h] BYREF
  char v205[8]; // [rsp+B8h] [rbp-390h] BYREF
  char v206[8]; // [rsp+C0h] [rbp-388h] BYREF
  char v207[8]; // [rsp+C8h] [rbp-380h] BYREF
  struct inverted::IFreshTest *v208; // [rsp+D0h] [rbp-378h] BYREF
  std::_Ref_count_base *v209; // [rsp+D8h] [rbp-370h]
  __int64 v210; // [rsp+E0h] [rbp-368h] BYREF
  __int128 v211; // [rsp+E8h] [rbp-360h]
  __int128 v212; // [rsp+F8h] [rbp-350h] BYREF
  __int64 v213; // [rsp+108h] [rbp-340h]
  _BYTE v214[56]; // [rsp+110h] [rbp-338h] BYREF
  __int64 v215; // [rsp+148h] [rbp-300h]
  _QWORD v216[3]; // [rsp+150h] [rbp-2F8h] BYREF
  _BYTE v217[168]; // [rsp+168h] [rbp-2E0h] BYREF
  int v218; // [rsp+210h] [rbp-238h]
  _QWORD v219[42]; // [rsp+2A0h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]

  v202 = this;
  pv = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55927663>::GetImpl'::`2'::impl) )
  {
    v2 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>>((struct wil::details::IFailureCallback *)v214)
                                     + 56);
    pv = (LPVOID)v2;
    if ( v2 )
      _InterlockedIncrement(v2 + 70);
    tip2::test_watcher<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_watcher<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(v214);
  }
  v3 = (char *)this + 440;
  if ( !*((_QWORD *)this + 58) && !*((_BYTE *)this + 188) )
  {
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v219);
    v219[0] = &SearchIndexerTelemetry::EnsureResultsActivity::`vftable';
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    {
      v4 = (struct _GUID *)(*(__int64 (__fastcall **)(inverted::CInvertedQuery *))(*(_QWORD *)this + 264LL))(this);
      wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v216);
      v216[0] = &SearchIndexerTelemetry::EnsureResultsActivity::`vftable';
      v197 = *v4;
      SearchIndexerTelemetry::EnsureResultsActivity::StartActivity(
        (SearchIndexerTelemetry::EnsureResultsActivity *)v216,
        &v197);
      SearchIndexerTelemetry::EnsureResultsActivity::operator=(v219, v216);
      SearchIndexerTelemetry::EnsureResultsActivity::~EnsureResultsActivity((SearchIndexerTelemetry::EnsureResultsActivity *)v216);
    }
    if ( !*((_QWORD *)this + 13) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55927663>::GetImpl'::`2'::impl) )
      {
        v184 = tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(
                 &pv,
                 &v202);
        *(_DWORD *)(tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(v184)
                  + 272) = -2147418113;
        tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(&v202);
        tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::complete(&pv);
      }
      v185 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x348,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\query.cpp",
        (const char *)v185,
        v191);
    }
    (*(void (__fastcall **)(_QWORD, struct inverted::IFreshTest **, char *))(**((_QWORD **)this + 3) + 184LL))(
      *((_QWORD *)this + 3),
      &v208,
      (char *)this + 440);
    v5 = (_QWORD *)((char *)this + 480);
    inverted::CScanRestrictions::SetFreshTest(*((inverted::CScanRestrictions **)this + 60), v208);
    try
    {
      *((_BYTE *)this + 188) = 1;
      v203 = *((_QWORD *)this + 13);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v203 + 72LL))(v203);
      v6 = (char *)this + 320;
      dynamic_sparse_bit<unsigned __int64>::Empty((char *)this + 320);
      v7 = *v5;
      v8 = *((_QWORD *)this + 19);
      if ( v8 )
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 112LL))(v8);
      else
        v9 = 0;
      inverted::CScanRestrictions::SetWidFilter(v7, v9);
      ETWLog::Log(L"QUERY: Starting - Decoders: %d", (__int64)(*((_QWORD *)this + 56) - *((_QWORD *)this + 55)) >> 4);
      v197.Data1 = 0;
      *(_QWORD *)v197.Data4 = -1;
      CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v197);
      (*(void (__fastcall **)(_QWORD, char *, inverted::CInvertedQuery *, char *, _DWORD, char *))(**((_QWORD **)this + 13)
                                                                                                 + 24LL))(
        *((_QWORD *)this + 13),
        (char *)this + 440,
        this,
        (char *)this + 480,
        *((_DWORD *)this + 30),
        (char *)this + 320);
      CImpersonateSystem::~CImpersonateSystem((HANDLE *)&v197);
      inverted::CScanRestrictions::SetWidFilter(*v5, (char *)this + 320);
      if ( !g_fETWLoggingChecked )
        ETWLog::CheckEnabled();
      if ( g_fETWLoggingEnabled || EventEnabled(Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging) )
      {
        v11 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size((char *)this + 320);
        ETWLog::Log(L"QUERY: Filter Executed - Results: %d  (before trimming)", v11);
      }
      v12 = *v5;
      if ( !**(_BYTE **)(*v5 + 168LL) && !**(_BYTE **)(v12 + 176) && !**(_BYTE **)(v12 + 160) )
      {
        LOBYTE(v10) = *((_BYTE *)this + 189);
        (*(void (__fastcall **)(_QWORD, __int64, char *, char *))(**((_QWORD **)this + 5) + 32LL))(
          *((_QWORD *)this + 5),
          v10,
          (char *)this + 24,
          (char *)this + 320);
      }
      inverted::TrimDecoders((char *)this + 440, (char *)this + 480);
      v13 = (__int64 *)((char *)this + 344);
      v14 = *((_QWORD *)this + 43);
      if ( v14 == *((_QWORD *)this + 44) )
        v14 = *((_QWORD *)this + 44);
      else
        *((_QWORD *)this + 44) = v14;
      v15 = 0;
      v193 = 0;
      v16 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size((char *)this + 320);
      std::vector<unsigned int>::insert((char *)this + 344, v200, v14, v16, &v193);
      dynamic_sparse_bit<unsigned __int64>::CopyTo<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>>(
        (_DWORD)this + 320,
        (unsigned int)v200,
        v17,
        *v13,
        *((_QWORD *)this + 44));
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57813035>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57813035>::GetImpl'::`2'::impl)
        && *((_QWORD *)this + 44) == *v13 )
      {
        SearchIndexerTelemetryAggregatedLow::ZeroResultQuery();
      }
      ETWLog::Log(
        L"QUERY: Filter Executed - Results: %d, Decoders: %d  (after trimming)",
        (__int64)(*((_QWORD *)this + 44) - *((_QWORD *)this + 43)) >> 2,
        (__int64)(*((_QWORD *)this + 56) - *((_QWORD *)this + 55)) >> 4);
      if ( (*((_BYTE *)this + 120) & 1) != 0 )
      {
        v18 = *v5;
        if ( !**(_BYTE **)(*v5 + 168LL) && !**(_BYTE **)(v18 + 176) && !**(_BYTE **)(v18 + 160) )
        {
          v19 = (void **)((char *)this + 368);
          v20 = *((_QWORD *)this + 46);
          if ( v20 == *((_QWORD *)this + 47) )
            v20 = *((_QWORD *)this + 47);
          else
            *((_QWORD *)this + 47) = v20;
          std::vector<unsigned short>::insert(
            (char *)this + 368,
            v200,
            v20,
            (__int64)(*((_QWORD *)this + 44) - *((_QWORD *)this + 43)) >> 2,
            &dword_1803195E4);
          v192 = (*((_QWORD *)this + 44) - *v13) >> 2;
          (*(void (__fastcall **)(_QWORD, char *, inverted::CInvertedQuery *, char *))(**((_QWORD **)this + 13) + 32LL))(
            *((_QWORD *)this + 13),
            (char *)this + 440,
            this,
            (char *)this + 320);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60586217>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60586217>::GetImpl'::`2'::impl)
            && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60977300>::GetImpl'::`2'::impl) )
          {
            v21 = (_QWORD *)(*(__int64 (__fastcall **)(inverted::CInvertedQuery *))(*(_QWORD *)this + 280LL))(this);
            if ( v21[3] > 7u )
              v21 = (_QWORD *)*v21;
            if ( !(unsigned int)_o__wcsicmp(v21, L"explorer.exe")
              && fc::config_vector<inverted::reranking_point>::size(qword_180369748) )
            {
              j = 0;
              tip2::tip_test<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>::start_and_watch_errors(
                &j,
                v214);
              wil::com_ptr_t<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>,wil::err_returncode_policy>(&j);
              v22 = *((_QWORD *)this + 47);
              v23 = *v19;
              v212 = 0;
              v213 = 0;
              v194 = v23;
              v195 = v22;
              std::vector<unsigned short>::_Construct_n<unsigned short *,unsigned short *>(
                &v212,
                (v22 - (__int64)v23) >> 1,
                &v194,
                &v195);
              v24 = *v13;
              gsl::details::extent_type<-1>::extent_type<-1>(
                &v197,
                (__int64)(*((_QWORD *)this + 44) - *((_QWORD *)this + 43)) >> 2);
              *(_QWORD *)v197.Data4 = v24;
              v26 = *(_QWORD *)&v197.Data1;
              if ( *(_QWORD *)&v197.Data1 == -1
                || !v24 && *(_QWORD *)&v197.Data1
                || (v27 = *v19,
                    gsl::details::extent_type<-1>::extent_type<-1>(
                      &v201,
                      (__int64)(*((_QWORD *)this + 47) - *((_QWORD *)this + 46)) >> 1),
                    *(_QWORD *)v201.Data4 = v27,
                    *(_QWORD *)&v201.Data1 == -1)
                || !v27 && *(_QWORD *)&v201.Data1 )
              {
                gsl::details::terminate(v25);
              }
              v216[0] = this;
              v216[1] = v26;
              v216[2] = v24;
              `eh vector constructor iterator'(
                v217,
                0x18u,
                7u,
                std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>,
                std::vector<inverted::L1RankerUtils::RankingInput>::~vector<inverted::L1RankerUtils::RankingInput>);
              v218 = 0;
              inverted::L1RankerUtils::ExtractUniqueDateFields(&v210);
              inverted::L1RankerUtils::PrefetchedRankingData::Prefetch(v216, &v210);
              v28 = fc::config_vector<inverted::reranking_point>::begin(qword_180369748);
              v29 = fc::config_vector<inverted::reranking_comp>::end(qword_180369748);
              if ( v28 != v29 )
              {
                v30 = v197;
                v31 = v201;
                do
                {
                  date_argument = inverted::reranking_comp::get_date_argument(v28);
                  type = inverted::reranking_func::get_type(v28 + 200);
                  operation = inverted::reranking_comp::get_operation(v28);
                  v35 = v215;
                  v195 = v215;
                  if ( v215 )
                    _InterlockedIncrement((volatile signed __int32 *)(v215 + 376));
                  tip2::details::shared_data<0,0,0>::begin_update(v35 + 8);
                  if ( (unsigned __int8)type < 7u )
                    ++*(_DWORD *)(v35 + 4LL * (unsigned __int8)type + 304);
                  if ( date_argument < 7u )
                    ++*(_DWORD *)(v35 + 4LL * date_argument + 332);
                  if ( operation < 4u )
                    ++*(_DWORD *)(v35 + 4LL * operation + 360);
                  tip2::test_data_control<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>::~test_data_control<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>(&v195);
                  v37 = type - 1;
                  if ( v37 )
                  {
                    v38 = v37 - 1;
                    if ( v38 )
                    {
                      v39 = v38 - 1;
                      if ( v39 )
                      {
                        v40 = v39 - 1;
                        if ( v40 )
                        {
                          v41 = v40 - 1;
                          if ( v41 )
                          {
                            if ( v41 == 1 )
                            {
                              v197 = v31;
                              v201 = v30;
                              inverted::RankerBase<inverted::DefaultLogDecayRankerCompute>::Rank(
                                v36,
                                (unsigned int)&v201,
                                (unsigned int)&v197,
                                (unsigned int)v216,
                                v28);
                            }
                          }
                          else
                          {
                            v197 = v31;
                            v201 = v30;
                            inverted::RankerBase<inverted::ExponentialRankerCompute>::Rank(
                              v36,
                              (unsigned int)&v201,
                              (unsigned int)&v197,
                              (unsigned int)v216,
                              v28);
                          }
                        }
                        else
                        {
                          v197 = v31;
                          v201 = v30;
                          inverted::RankerBase<inverted::PowerRankerCompute>::Rank(
                            v36,
                            (unsigned int)&v201,
                            (unsigned int)&v197,
                            (unsigned int)v216,
                            v28);
                        }
                      }
                      else
                      {
                        v197 = v31;
                        v201 = v30;
                        inverted::RankerBase<inverted::PiecewiseLinearRankerCompute>::Rank(
                          v36,
                          (unsigned int)&v201,
                          (unsigned int)&v197,
                          (unsigned int)v216,
                          v28);
                      }
                    }
                    else
                    {
                      v197 = v31;
                      v201 = v30;
                      inverted::RankerBase<inverted::GeneralizedLogisticRankerCompute>::Rank(
                        v36,
                        (unsigned int)&v201,
                        (unsigned int)&v197,
                        (unsigned int)v216,
                        v28);
                    }
                  }
                  else
                  {
                    v197 = v31;
                    v201 = v30;
                    inverted::RankerBase<inverted::ConstantRankerCompute>::Rank(
                      v36,
                      (unsigned int)&v201,
                      (unsigned int)&v197,
                      (unsigned int)v216,
                      v28);
                  }
                  v28 += 1224;
                }
                while ( v28 != v29 );
                v6 = (char *)this + 320;
                v13 = (__int64 *)((char *)this + 344);
              }
              fc::config_property_base::ensure_initialized((fc::config_property_base *)qword_1803697D8);
              v42 = qword_180369800;
              fc::config_property_base::ensure_initialized((fc::config_property_base *)qword_180369810);
              *(_QWORD *)&v197.Data1 = v42;
              *(_QWORD *)v197.Data4 = qword_180369838;
              v19 = (void **)((char *)this + 368);
              std::transform_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_unsigned_short______std::_Vector_iterator_std::_Vector_val_std::_Simple_types_unsigned_short_______lambda_f2b62082712d575e3850a1bbf46e330c___(
                (unsigned int)v200,
                *((_QWORD *)this + 46),
                *((_QWORD *)this + 47),
                *((_QWORD *)this + 46),
                (__int64)&v197);
              for ( i = 0; i < (__int64)(*((_QWORD *)this + 47) - *((_QWORD *)this + 46)) >> 1; ++i )
              {
                v44 = v215;
                v195 = v215;
                if ( v215 )
                  _InterlockedIncrement((volatile signed __int32 *)(v215 + 376));
                tip2::details::shared_data<0,0,0>::begin_update(v44 + 8);
                v45 = *((unsigned __int16 *)*v19 + i);
                v46 = *(unsigned __int16 *)(v212 + 2 * i);
                if ( *((unsigned __int16 *)*v19 + i) - (int)v46 <= 0 )
                {
                  if ( *((unsigned __int16 *)*v19 + i) - (int)v46 >= 0 )
                  {
                    ++*(_DWORD *)(v44 + 280);
                  }
                  else
                  {
                    ++*(_DWORD *)(v44 + 276);
                    *(_QWORD *)(v44 + 296) += v46 - v45;
                  }
                }
                else
                {
                  ++*(_DWORD *)(v44 + 272);
                  *(_QWORD *)(v44 + 288) += (unsigned int)v45 - (unsigned __int64)(unsigned int)v46;
                }
                tip2::test_data_control<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>::~test_data_control<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>(&v195);
              }
              tip2::details::shared_data<0,0,0>::complete_without_lock(v215 + 8);
              v15 = 0;
              if ( v210 )
              {
                std::_Deallocate<16>(v210, (*((_QWORD *)&v211 + 1) - v210) & 0xFFFFFFFFFFFFFFFCuLL);
                v210 = 0;
                v211 = 0;
              }
              `eh vector destructor iterator'(
                v217,
                0x18u,
                7u,
                std::vector<inverted::L1RankerUtils::RankingInput>::~vector<inverted::L1RankerUtils::RankingInput>);
              std::vector<unsigned short>::_Tidy(&v212);
              tip2::test_watcher<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>::~test_watcher<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>(v214);
              v3 = (char *)this + 440;
            }
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59871929>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59871929>::GetImpl'::`2'::impl) )
            {
              if ( (*(unsigned __int8 (__fastcall **)(inverted::CInvertedQuery *))(*(_QWORD *)this + 240LL))(this) )
              {
                for ( j = 0; ; j = v15 )
                {
                  while ( 1 )
                  {
                    if ( v15 >= (__int64)(*((_QWORD *)this + 47) - (_QWORD)*v19) >> 1 )
                      goto LABEL_248;
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53998201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53998201>::GetImpl'::`2'::impl) )
                      break;
                    if ( *((unsigned __int16 *)*v19 + v15) > dword_1803682E8 )
                      goto LABEL_165;
                    v50 = 4 * v15;
                    v195 = 4 * v15;
                    v90 = *(_DWORD *)(4 * v15 + *v13);
                    v193 = v90;
                    v91 = v90 >> *(_DWORD *)(*(_QWORD *)v6 + 20LL);
                    v92 = *((_DWORD *)this + 82);
                    if ( v91 < v92 )
                    {
                      v93 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6);
                    }
                    else if ( v91 >= *((_DWORD *)v6 + 3) )
                    {
                      v93 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6);
                    }
                    else
                    {
                      v93 = (_QWORD *)(*((_QWORD *)v6 + 2) + 8LL * (v91 - v92));
                    }
                    if ( !*v93 )
                    {
                      v94 = *(unsigned int **)v6;
                      v95 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v6 + 48LL);
                      v96 = (_QWORD *)(v95 + 16);
                      v97 = *(_QWORD *)(v95 + 24);
                      if ( *(_QWORD *)(v95 + 16) == v97 )
                      {
                        v98 = *(unsigned int *)(v95 + 8);
                        if ( (unsigned int)v98 >= v94[7] )
                        {
                          v101 = _aligned_malloc(8LL * v94[7], v94[8]);
                          v99 = v101;
                          v194 = v101;
                          if ( !v101 )
                            wil::details::in1diag3::_Throw_NullAlloc(
                              retaddr,
                              (void *)0x430,
                              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                              v102);
                          v103 = *(_QWORD **)(v95 + 48);
                          if ( v103 == *(_QWORD **)(v95 + 56) )
                          {
                            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                              v95 + 40,
                              v103,
                              &v194);
                            v99 = v194;
                          }
                          else
                          {
                            *v103 = v101;
                            *(_QWORD *)(v95 + 48) += 8LL;
                          }
                          v104 = v94[6] * ((__int64)(*(_QWORD *)(v95 + 48) - *(_QWORD *)(v95 + 40)) >> 3);
                          v198 = v104;
                          if ( v104 > (__int64)(*(_QWORD *)(v95 + 32) - *v96) >> 3 )
                          {
                            if ( v104 > 0x1FFFFFFFFFFFFFFFLL )
                              std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v104);
                            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v96, &v198);
                          }
                          *(_QWORD *)v95 = v99;
                          v100 = v94[2];
                          v90 = v193;
                        }
                        else
                        {
                          v99 = (void *)(*(_QWORD *)v95 + 8 * v98);
                          v100 = v98 + v94[2];
                        }
                        *(_DWORD *)(v95 + 8) = v100;
                      }
                      else
                      {
                        v105 = (void **)(v97 - 8);
                        v99 = *v105;
                        *(_QWORD *)(v95 + 24) = v105;
                      }
                      *v93 = v99;
                      memset_0(v99, 0, v94[1]);
                      v50 = v195;
                      v15 = j;
                      v6 = (char *)this + 320;
                      v13 = (__int64 *)((char *)this + 344);
                    }
                    v106 = *(unsigned int *)(*(_QWORD *)v6 + 16LL) & ((unsigned __int64)v90 >> 6);
                    v107 = v90 & 0x3F;
                    v108 = *(_QWORD *)(*v93 + 8 * v106);
                    if ( (v108 & (1LL << v107)) != 0 )
                      *(_QWORD *)(*v93 + 8 * v106) = (1LL << v107) ^ v108;
                    v19 = (void **)((char *)this + 368);
                    std::vector<unsigned short>::erase((char *)this + 368, v207, *((_QWORD *)this + 46) + 2 * v15);
                    v70 = &v201;
LABEL_164:
                    std::vector<unsigned int>::erase(v13, v70, v50 + *v13);
                  }
                  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_56091827>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56091827>::GetImpl'::`2'::impl);
                  v49 = *((_WORD *)*v19 + v15);
                  if ( !IsEnabled )
                  {
                    if ( v49 )
                      goto LABEL_165;
                    v50 = 4 * v15;
                    v195 = 4 * v15;
                    v71 = *(_DWORD *)(4 * v15 + *v13);
                    v193 = v71;
                    v72 = v71 >> *(_DWORD *)(*(_QWORD *)v6 + 20LL);
                    v73 = *((_DWORD *)this + 82);
                    if ( v72 < v73 )
                    {
                      v74 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6);
                    }
                    else if ( v72 >= *((_DWORD *)v6 + 3) )
                    {
                      v74 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6);
                    }
                    else
                    {
                      v74 = (_QWORD *)(*((_QWORD *)v6 + 2) + 8LL * (v72 - v73));
                    }
                    if ( !*v74 )
                    {
                      v75 = *(unsigned int **)v6;
                      v76 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v6 + 48LL);
                      v77 = (_QWORD *)(v76 + 16);
                      v78 = *(_QWORD *)(v76 + 24);
                      if ( *(_QWORD *)(v76 + 16) == v78 )
                      {
                        v79 = *(unsigned int *)(v76 + 8);
                        if ( (unsigned int)v79 >= v75[7] )
                        {
                          v82 = _aligned_malloc(8LL * v75[7], v75[8]);
                          v80 = v82;
                          v194 = v82;
                          if ( !v82 )
                            wil::details::in1diag3::_Throw_NullAlloc(
                              retaddr,
                              (void *)0x430,
                              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                              v83);
                          v84 = *(_QWORD **)(v76 + 48);
                          if ( v84 == *(_QWORD **)(v76 + 56) )
                          {
                            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                              v76 + 40,
                              v84,
                              &v194);
                            v80 = v194;
                          }
                          else
                          {
                            *v84 = v82;
                            *(_QWORD *)(v76 + 48) += 8LL;
                          }
                          v85 = v75[6] * ((__int64)(*(_QWORD *)(v76 + 48) - *(_QWORD *)(v76 + 40)) >> 3);
                          v198 = v85;
                          if ( v85 > (__int64)(*(_QWORD *)(v76 + 32) - *v77) >> 3 )
                          {
                            if ( v85 > 0x1FFFFFFFFFFFFFFFLL )
                              std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v85);
                            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v77, &v198);
                          }
                          *(_QWORD *)v76 = v80;
                          v81 = v75[2];
                          v71 = v193;
                        }
                        else
                        {
                          v80 = (void *)(*(_QWORD *)v76 + 8 * v79);
                          v81 = v79 + v75[2];
                        }
                        *(_DWORD *)(v76 + 8) = v81;
                      }
                      else
                      {
                        v86 = (void **)(v78 - 8);
                        v80 = *v86;
                        *(_QWORD *)(v76 + 24) = v86;
                      }
                      *v74 = v80;
                      memset_0(v80, 0, v75[1]);
                      v50 = v195;
                      v15 = j;
                      v6 = (char *)this + 320;
                      v13 = (__int64 *)((char *)this + 344);
                    }
                    v87 = *(unsigned int *)(*(_QWORD *)v6 + 16LL) & ((unsigned __int64)v71 >> 6);
                    v88 = v71 & 0x3F;
                    v89 = *(_QWORD *)(*v74 + 8 * v87);
                    if ( (v89 & (1LL << v88)) != 0 )
                      *(_QWORD *)(*v74 + 8 * v87) = (1LL << v88) ^ v89;
                    v19 = (void **)((char *)this + 368);
                    std::vector<unsigned short>::erase((char *)this + 368, v205, *((_QWORD *)this + 46) + 2 * v15);
                    v70 = (struct _GUID *)v206;
                    goto LABEL_164;
                  }
                  if ( v49 == 1001 || !v49 )
                  {
                    v50 = 4 * v15;
                    v198 = 4 * v15;
                    v51 = *(_DWORD *)(4 * v15 + *v13);
                    v193 = v51;
                    v52 = v51 >> *(_DWORD *)(*(_QWORD *)v6 + 20LL);
                    v53 = *((_DWORD *)this + 82);
                    if ( v52 < v53 )
                    {
                      v54 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6);
                    }
                    else if ( v52 >= *((_DWORD *)v6 + 3) )
                    {
                      v54 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6);
                    }
                    else
                    {
                      v54 = (_QWORD *)(*((_QWORD *)v6 + 2) + 8LL * (v52 - v53));
                    }
                    if ( !*v54 )
                    {
                      v55 = *(unsigned int **)v6;
                      v56 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v6 + 48LL);
                      v57 = (_QWORD *)(v56 + 16);
                      v58 = *(_QWORD *)(v56 + 24);
                      if ( *(_QWORD *)(v56 + 16) == v58 )
                      {
                        v59 = *(unsigned int *)(v56 + 8);
                        if ( (unsigned int)v59 >= v55[7] )
                        {
                          v62 = _aligned_malloc(8LL * v55[7], v55[8]);
                          v60 = v62;
                          v194 = v62;
                          if ( !v62 )
                            wil::details::in1diag3::_Throw_NullAlloc(
                              retaddr,
                              (void *)0x430,
                              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                              v63);
                          v64 = *(_QWORD **)(v56 + 48);
                          if ( v64 == *(_QWORD **)(v56 + 56) )
                          {
                            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                              v56 + 40,
                              v64,
                              &v194);
                            v60 = v194;
                          }
                          else
                          {
                            *v64 = v62;
                            *(_QWORD *)(v56 + 48) += 8LL;
                          }
                          v65 = v55[6] * ((__int64)(*(_QWORD *)(v56 + 48) - *(_QWORD *)(v56 + 40)) >> 3);
                          v195 = v65;
                          if ( v65 > (__int64)(*(_QWORD *)(v56 + 32) - *v57) >> 3 )
                          {
                            if ( v65 > 0x1FFFFFFFFFFFFFFFLL )
                              std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v65);
                            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v57, &v195);
                          }
                          *(_QWORD *)v56 = v60;
                          v61 = v55[2];
                          v51 = v193;
                        }
                        else
                        {
                          v60 = (void *)(*(_QWORD *)v56 + 8 * v59);
                          v61 = v59 + v55[2];
                        }
                        *(_DWORD *)(v56 + 8) = v61;
                      }
                      else
                      {
                        v66 = (void **)(v58 - 8);
                        v60 = *v66;
                        *(_QWORD *)(v56 + 24) = v66;
                      }
                      *v54 = v60;
                      memset_0(v60, 0, v55[1]);
                      v50 = v198;
                      v15 = j;
                      v6 = (char *)this + 320;
                      v13 = (__int64 *)((char *)this + 344);
                    }
                    v67 = *(unsigned int *)(*(_QWORD *)v6 + 16LL) & ((unsigned __int64)v51 >> 6);
                    v68 = v51 & 0x3F;
                    v69 = *(_QWORD *)(*v54 + 8 * v67);
                    if ( (v69 & (1LL << v68)) != 0 )
                      *(_QWORD *)(*v54 + 8 * v67) = (1LL << v68) ^ v69;
                    v19 = (void **)((char *)this + 368);
                    std::vector<unsigned short>::erase((char *)this + 368, v200, *((_QWORD *)this + 46) + 2 * v15);
                    v70 = (struct _GUID *)v204;
                    goto LABEL_164;
                  }
LABEL_165:
                  ++v15;
                }
              }
            }
            else
            {
              if ( !byte_180368FD0 )
              {
                inverted::CInvertedQuery::ReadThresholdFromRegistry(v47);
                byte_180368FD0 = 1;
              }
LABEL_168:
              j = v15;
              while ( v15 < (__int64)(*((_QWORD *)this + 47) - (_QWORD)*v19) >> 1 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53998201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53998201>::GetImpl'::`2'::impl) )
                {
                  v109 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_56091827>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56091827>::GetImpl'::`2'::impl);
                  v110 = 2 * v15;
                  v195 = 2 * v15;
                  v111 = *((_WORD *)*v19 + v15);
                  if ( v109 )
                  {
                    if ( v111 != 1001 && v111 )
                    {
LABEL_222:
                      ++v15;
                      v13 = (__int64 *)((char *)this + 344);
                      goto LABEL_168;
                    }
                    v112 = 4 * v15;
                    v200[0] = 4 * v15;
                    v113 = *(_DWORD *)(4 * v15 + *((_QWORD *)this + 43));
                    v193 = v113;
                    v114 = v113 >> *(_DWORD *)(*(_QWORD *)v6 + 20LL);
                    v115 = *((_DWORD *)this + 82);
                    if ( v114 < v115 )
                    {
                      v116 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6);
                    }
                    else if ( v114 >= *((_DWORD *)v6 + 3) )
                    {
                      v116 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6);
                    }
                    else
                    {
                      v116 = (_QWORD *)(*((_QWORD *)v6 + 2) + 8LL * (v114 - v115));
                    }
                    if ( !*v116 )
                    {
                      v117 = *(unsigned int **)v6;
                      v118 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v6 + 48LL);
                      v119 = (_QWORD *)(v118 + 16);
                      v120 = *(_QWORD *)(v118 + 24);
                      if ( *(_QWORD *)(v118 + 16) == v120 )
                      {
                        v121 = *(unsigned int *)(v118 + 8);
                        if ( (unsigned int)v121 >= v117[7] )
                        {
                          v124 = _aligned_malloc(8LL * v117[7], v117[8]);
                          v122 = v124;
                          v194 = v124;
                          if ( !v124 )
                            wil::details::in1diag3::_Throw_NullAlloc(
                              retaddr,
                              (void *)0x430,
                              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                              v125);
                          v126 = *(_QWORD **)(v118 + 48);
                          if ( v126 == *(_QWORD **)(v118 + 56) )
                          {
                            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                              v118 + 40,
                              v126,
                              &v194);
                            v122 = v194;
                          }
                          else
                          {
                            *v126 = v124;
                            *(_QWORD *)(v118 + 48) += 8LL;
                          }
                          v127 = v117[6] * ((__int64)(*(_QWORD *)(v118 + 48) - *(_QWORD *)(v118 + 40)) >> 3);
                          v198 = v127;
                          if ( v127 > (__int64)(*(_QWORD *)(v118 + 32) - *v119) >> 3 )
                          {
                            if ( v127 > 0x1FFFFFFFFFFFFFFFLL )
                              std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v127);
                            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v119, &v198);
                          }
                          *(_QWORD *)v118 = v122;
                          v123 = v117[2];
                          v113 = v193;
                        }
                        else
                        {
                          v122 = (void *)(*(_QWORD *)v118 + 8 * v121);
                          v123 = v121 + v117[2];
                        }
                        *(_DWORD *)(v118 + 8) = v123;
                      }
                      else
                      {
                        v128 = (void **)(v120 - 8);
                        v122 = *v128;
                        *(_QWORD *)(v118 + 24) = v128;
                      }
                      *v116 = v122;
                      memset_0(v122, 0, v117[1]);
                      v112 = v200[0];
                      v15 = j;
                      v110 = v195;
                      v6 = (char *)this + 320;
                    }
                    v129 = ((unsigned __int64)v113 >> 6) & *(unsigned int *)(*(_QWORD *)v6 + 16LL);
                    v130 = v113 & 0x3F;
                    v131 = *(_QWORD *)(*v116 + 8 * v129);
                    if ( (v131 & (1LL << v130)) != 0 )
                      *(_QWORD *)(*v116 + 8 * v129) = (1LL << v130) ^ v131;
                    v19 = (void **)((char *)this + 368);
                    std::vector<unsigned short>::erase((char *)this + 368, &v201, v110 + *((_QWORD *)this + 46));
                    v132 = v207;
                  }
                  else
                  {
                    if ( v111 )
                      goto LABEL_222;
                    v112 = 4 * v15;
                    v198 = 4 * v15;
                    v133 = *(_DWORD *)(4 * v15 + *((_QWORD *)this + 43));
                    v193 = v133;
                    v134 = v133 >> *(_DWORD *)(*(_QWORD *)v6 + 20LL);
                    v135 = *((_DWORD *)this + 82);
                    if ( v134 < v135 )
                    {
                      v136 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6);
                    }
                    else if ( v134 >= *((_DWORD *)v6 + 3) )
                    {
                      v136 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6);
                    }
                    else
                    {
                      v136 = (_QWORD *)(*((_QWORD *)v6 + 2) + 8LL * (v134 - v135));
                    }
                    if ( !*v136 )
                    {
                      v137 = *(unsigned int **)v6;
                      v138 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v6 + 48LL);
                      v139 = (_QWORD *)(v138 + 16);
                      v140 = *(_QWORD *)(v138 + 24);
                      if ( *(_QWORD *)(v138 + 16) == v140 )
                      {
                        v141 = *(unsigned int *)(v138 + 8);
                        if ( (unsigned int)v141 >= v137[7] )
                        {
                          v144 = _aligned_malloc(8LL * v137[7], v137[8]);
                          v142 = v144;
                          v194 = v144;
                          if ( !v144 )
                            wil::details::in1diag3::_Throw_NullAlloc(
                              retaddr,
                              (void *)0x430,
                              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                              v145);
                          v146 = *(_QWORD **)(v138 + 48);
                          if ( v146 == *(_QWORD **)(v138 + 56) )
                          {
                            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                              v138 + 40,
                              v146,
                              &v194);
                            v142 = v194;
                          }
                          else
                          {
                            *v146 = v144;
                            *(_QWORD *)(v138 + 48) += 8LL;
                          }
                          v147 = v137[6] * ((__int64)(*(_QWORD *)(v138 + 48) - *(_QWORD *)(v138 + 40)) >> 3);
                          v200[0] = v147;
                          if ( v147 > (__int64)(*(_QWORD *)(v138 + 32) - *v139) >> 3 )
                          {
                            if ( v147 > 0x1FFFFFFFFFFFFFFFLL )
                              std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v147);
                            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v139, v200);
                          }
                          *(_QWORD *)v138 = v142;
                          v143 = v137[2];
                          v133 = v193;
                        }
                        else
                        {
                          v142 = (void *)(*(_QWORD *)v138 + 8 * v141);
                          v143 = v141 + v137[2];
                        }
                        *(_DWORD *)(v138 + 8) = v143;
                      }
                      else
                      {
                        v148 = (void **)(v140 - 8);
                        v142 = *v148;
                        *(_QWORD *)(v138 + 24) = v148;
                      }
                      *v136 = v142;
                      memset_0(v142, 0, v137[1]);
                      v112 = v198;
                      v15 = j;
                      v110 = v195;
                      v6 = (char *)this + 320;
                    }
                    v149 = ((unsigned __int64)v133 >> 6) & *(unsigned int *)(*(_QWORD *)v6 + 16LL);
                    v150 = v133 & 0x3F;
                    v151 = *(_QWORD *)(*v136 + 8 * v149);
                    if ( (v151 & (1LL << v150)) != 0 )
                      *(_QWORD *)(*v136 + 8 * v149) = (1LL << v150) ^ v151;
                    v19 = (void **)((char *)this + 368);
                    std::vector<unsigned short>::erase((char *)this + 368, v206, v110 + *((_QWORD *)this + 46));
                    v132 = v205;
                  }
                  v13 = (__int64 *)((char *)this + 344);
                  std::vector<unsigned int>::erase((char *)this + 344, v132, v112 + *((_QWORD *)this + 43));
                }
                else
                {
                  v152 = 2 * v15;
                  v198 = 2 * v15;
                  if ( *((unsigned __int16 *)*v19 + v15) > dword_1803682E8 )
                  {
                    ++v15;
                    goto LABEL_168;
                  }
                  v153 = 4 * v15;
                  v194 = (void *)v153;
                  v154 = *(_DWORD *)(v153 + *v13);
                  v193 = v154;
                  v155 = v154 >> *(_DWORD *)(*(_QWORD *)v6 + 20LL);
                  v156 = *((_DWORD *)this + 82);
                  if ( v155 < v156 )
                  {
                    v157 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v6);
                  }
                  else if ( v155 >= *((_DWORD *)v6 + 3) )
                  {
                    v157 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v6);
                  }
                  else
                  {
                    v157 = (_QWORD *)(*((_QWORD *)v6 + 2) + 8LL * (v155 - v156));
                  }
                  if ( !*v157 )
                  {
                    v158 = *(unsigned int **)v6;
                    v159 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v6 + 48LL);
                    v160 = (_QWORD *)(v159 + 16);
                    v161 = *(_QWORD *)(v159 + 24);
                    if ( *(_QWORD *)(v159 + 16) == v161 )
                    {
                      v162 = *(unsigned int *)(v159 + 8);
                      if ( (unsigned int)v162 >= v158[7] )
                      {
                        v165 = _aligned_malloc(8LL * v158[7], v158[8]);
                        v163 = v165;
                        v195 = (__int64)v165;
                        if ( !v165 )
                          wil::details::in1diag3::_Throw_NullAlloc(
                            retaddr,
                            (void *)0x430,
                            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                            v166);
                        v167 = *(_QWORD **)(v159 + 48);
                        if ( v167 == *(_QWORD **)(v159 + 56) )
                        {
                          std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                            v159 + 40,
                            v167,
                            &v195);
                          v163 = (void *)v195;
                        }
                        else
                        {
                          *v167 = v165;
                          *(_QWORD *)(v159 + 48) += 8LL;
                        }
                        v168 = v158[6] * ((__int64)(*(_QWORD *)(v159 + 48) - *(_QWORD *)(v159 + 40)) >> 3);
                        v200[0] = v168;
                        if ( v168 > (__int64)(*(_QWORD *)(v159 + 32) - *v160) >> 3 )
                        {
                          if ( v168 > 0x1FFFFFFFFFFFFFFFLL )
                            std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v168);
                          std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v160, v200);
                        }
                        *(_QWORD *)v159 = v163;
                        v164 = v158[2];
                        v154 = v193;
                      }
                      else
                      {
                        v163 = (void *)(*(_QWORD *)v159 + 8 * v162);
                        v164 = v162 + v158[2];
                      }
                      *(_DWORD *)(v159 + 8) = v164;
                    }
                    else
                    {
                      v169 = (void **)(v161 - 8);
                      v163 = *v169;
                      *(_QWORD *)(v159 + 24) = v169;
                    }
                    *v157 = v163;
                    memset_0(v163, 0, v158[1]);
                    v152 = v198;
                    v153 = (__int64)v194;
                    v6 = (char *)this + 320;
                    v13 = (__int64 *)((char *)this + 344);
                  }
                  v170 = ((unsigned __int64)v154 >> 6) & *(unsigned int *)(*(_QWORD *)v6 + 16LL);
                  v171 = v154 & 0x3F;
                  v172 = *(_QWORD *)(*v157 + 8 * v170);
                  if ( (v172 & (1LL << v171)) != 0 )
                    *(_QWORD *)(*v157 + 8 * v170) = (1LL << v171) ^ v172;
                  v19 = (void **)((char *)this + 368);
                  std::vector<unsigned short>::erase((char *)this + 368, v204, v152 + *((_QWORD *)this + 46));
                  std::vector<unsigned int>::erase(v13, &v197, v153 + *v13);
                  v15 = j;
                }
              }
LABEL_248:
              v3 = (char *)this + 440;
            }
          }
          v5 = (_QWORD *)((char *)this + 480);
        }
      }
      if ( (*((_BYTE *)this + 120) & 2) != 0 )
      {
        v173 = *v5;
        if ( !**(_BYTE **)(*v5 + 168LL) && !**(_BYTE **)(v173 + 176) && !**(_BYTE **)(v173 + 160) )
        {
          v174 = *((_QWORD *)this + 49);
          if ( v174 == *((_QWORD *)this + 50) )
            v174 = *((_QWORD *)this + 50);
          else
            *((_QWORD *)this + 50) = v174;
          LOWORD(v193) = 0;
          std::vector<unsigned short>::insert((char *)this + 392, &v197, v174, (v13[1] - *v13) >> 2, &v193);
          v192 = (*((_QWORD *)this + 44) - *v13) >> 2;
          (*(void (__fastcall **)(_QWORD, char *, inverted::CInvertedQuery *, char *))(**((_QWORD **)this + 13) + 40LL))(
            *((_QWORD *)this + 13),
            v3,
            this,
            v6);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
      {
        if ( (*((_BYTE *)this + 120) & 0x10) != 0 )
        {
          v175 = *v5;
          if ( !**(_BYTE **)(*v5 + 168LL) && !**(_BYTE **)(v175 + 176) && !**(_BYTE **)(v175 + 160) )
          {
            v176 = *((_QWORD *)this + 52);
            if ( v176 == *((_QWORD *)this + 53) )
              v176 = *((_QWORD *)this + 53);
            else
              *((_QWORD *)this + 53) = v176;
            v193 = 0;
            std::vector<unsigned int>::insert((char *)this + 416, &v197, v176, (v13[1] - *v13) >> 2, &v193);
            v192 = (*((_QWORD *)this + 44) - *v13) >> 2;
            (*(void (__fastcall **)(_QWORD, char *, inverted::CInvertedQuery *, char *))(**((_QWORD **)this + 13) + 48LL))(
              *((_QWORD *)this + 13),
              v3,
              this,
              v6);
          }
        }
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57568202>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57568202>::GetImpl'::`2'::impl)
        && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56090771>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56090771>::GetImpl'::`2'::impl) )
      {
        *((_DWORD *)this + 30) |= 4u;
      }
      if ( (*((_BYTE *)this + 120) & 4) != 0 )
      {
        v177 = *v5;
        if ( !**(_BYTE **)(*v5 + 168LL) && !**(_BYTE **)(v177 + 176) && !**(_BYTE **)(v177 + 160) )
        {
          inverted::CPidWids::Clear((inverted::CInvertedQuery *)((char *)this + 584));
          v192 = (_DWORD)this + 584;
          (*(void (__fastcall **)(_QWORD, char *, inverted::CInvertedQuery *, char *))(**((_QWORD **)this + 13) + 56LL))(
            *((_QWORD *)this + 13),
            v3,
            this,
            v6);
        }
      }
      std::shared_ptr<inverted::IFreshTest>::operator=(v3 + 24, &v208);
      std::shared_ptr<inverted::IInvertedIndex>::reset((char *)this + 152);
      *((_BYTE *)this + 188) = 0;
      inverted::CCursorEvaluationGuard::~CCursorEvaluationGuard((inverted::CCursorEvaluationGuard *)&v203);
      v178 = *(_QWORD *)(*v5 + 184LL);
      for ( k = 0; k < *(_QWORD *)(v178 + 56); ++k )
      {
        for ( m = *(_QWORD *)(*(_QWORD *)(v178 + 48) + 8 * k); m; m = *(_QWORD *)(m + 72) )
          sparse_bit_allocator<unsigned __int64>::CAllocatorState::clear(m + 8);
      }
    }
    catch ( ... )
    {
      inverted::CInvertedQuery::_Clear(v202);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55927663>::GetImpl'::`2'::impl) )
      {
        LastError = GetLastError();
        v190 = tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(
                 &pv,
                 &v202);
        *(_DWORD *)(tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(v190)
                  + 272) = LastError;
        tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(&v202);
        tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::complete(&pv);
      }
      throw;
    }
    v181 = *v5;
    if ( **(_BYTE **)(*v5 + 168LL) || **(_BYTE **)(v181 + 176) || **(_BYTE **)(v181 + 160) )
    {
      inverted::CInvertedQuery::_Clear(this);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55927663>::GetImpl'::`2'::impl) )
      {
        v186 = tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(
                 &pv,
                 &v203);
        *(_DWORD *)(tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(v186)
                  + 272) = 1223;
        tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(&v203);
        v187 = tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(
                 &pv,
                 &v203);
        v188 = tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(v187);
        tip2::details::shared_data<0,0,0>::complete(v188 + 8);
        tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(&v203);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4D5,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\query.cpp",
        (const char *)0x4C7,
        v192);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    {
      v182 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v5 + 248LL) + 16LL))(*(_QWORD *)(*v5 + 248LL));
      v197 = *(struct _GUID *)(*(__int64 (__fastcall **)(inverted::CInvertedQuery *))(*(_QWORD *)this + 264LL))(this);
      SearchIndexerTelemetry::EnsureResultsActivity::Stop(
        (SearchIndexerTelemetry::EnsureResultsActivity *)v219,
        &v197,
        v182);
    }
    if ( v209 )
      std::_Ref_count_base::_Decref(v209);
    SearchIndexerTelemetry::EnsureResultsActivity::~EnsureResultsActivity((SearchIndexerTelemetry::EnsureResultsActivity *)v219);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55927663>::GetImpl'::`2'::impl) )
  {
    v183 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::operator->(
                       &pv,
                       &v202);
    tip2::details::shared_data<0,0,0>::complete_helper(*v183 + 8LL, 2048, 10);
    tip2::test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_data_control<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(&v202);
  }
  wil::com_ptr_t<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>,wil::err_returncode_policy>(&pv);
}

```

## disassembly

```asm
0x1800a8f84  mov     rax, rsp
0x1800a8f87  mov     [rax+10h], rbx
0x1800a8f8b  mov     [rax+18h], rsi
0x1800a8f8f  push    rdi
0x1800a8f90  push    r12
0x1800a8f92  push    r13
0x1800a8f94  push    r14
0x1800a8f96  push    r15
0x1800a8f98  sub     rsp, 420h
0x1800a8f9f  movaps  xmmword ptr [rax-38h], xmm6
0x1800a8fa3  movaps  xmmword ptr [rax-48h], xmm7
0x1800a8fa7  mov     rax, cs:__security_cookie
0x1800a8fae  xor     rax, rsp
0x1800a8fb1  mov     [rsp+448h+var_58], rax
0x1800a8fb9  mov     rdi, rcx
0x1800a8fbc  mov     [rsp+448h+var_3A8], rcx
0x1800a8fc4  xor     r15d, r15d
0x1800a8fc7  mov     [rsp+448h+pv], r15
0x1800a8fcc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55927663@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55927663@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663> `wil::Feature<__WilFeatureTraits_Feature_55927663>::GetImpl(void)'::`2'::impl
0x1800a8fd3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55927663@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55927663>::__private_IsEnabled(void)
0x1800a8fd8  test    al, al
0x1800a8fda  jz      short loc_1800A901D
0x1800a8fdc  lea     rcx, [rsp+448h+var_338]; struct wil::details::IFailureCallback *
0x1800a8fe4  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_EnsureResultsFailureTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800a8fe9  mov     rcx, [rax+38h]
0x1800a8fed  mov     rax, [rsp+448h+pv]
0x1800a8ff2  mov     [rsp+448h+pv], rcx
0x1800a8ff7  test    rcx, rcx
0x1800a8ffa  jz      short loc_1800A9003
0x1800a8ffc  lock inc dword ptr [rcx+118h]
0x1800a9003  test    rax, rax
0x1800a9006  jz      short loc_1800A9010
0x1800a9008  mov     rcx, rax; pv
0x1800a900b  call    ?Release@?$merged_data@U_tip_EnsureResultsFailureTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>::Release(void)
0x1800a9010  lea     rcx, [rsp+448h+var_338]
0x1800a9018  call    ??1?$test_watcher@V?$merged_data@U_tip_EnsureResultsFailureTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>::~test_watcher<tip2::details::merged_data<_tip_EnsureResultsFailureTest,_tip_EnsureResultsFailureTest>>(void)
0x1800a901d  lea     r14, [rdi+1B8h]
0x1800a9024  cmp     [r14+18h], r15
0x1800a9028  jnz     loc_1800AA9CD
0x1800a902e  cmp     [rdi+0BCh], r15b
0x1800a9035  jnz     loc_1800AA9CD
0x1800a903b  lea     rdx, aEnsureresultsa; "EnsureResultsActivity"
0x1800a9042  lea     rcx, [rsp+448h+var_1A8]; struct wil::details::IFailureCallback *
0x1800a904a  call    ??0?$ActivityBase@VSearchIndexerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800a904f  lea     rsi, ??_7EnsureResultsActivity@SearchIndexerTelemetry@@6B@; const SearchIndexerTelemetry::EnsureResultsActivity::`vftable'
0x1800a9056  mov     [rsp+448h+var_1A8], rsi
0x1800a905e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59422362@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362> `wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl(void)'::`2'::impl
0x1800a9065  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(void)
0x1800a906a  test    al, al
0x1800a906c  jz      short loc_1800A90DD
0x1800a906e  mov     rax, [rdi]
0x1800a9071  mov     rcx, rdi
0x1800a9074  mov     rax, [rax+108h]
0x1800a907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9080  mov     rbx, rax
0x1800a9083  lea     rdx, aEnsureresultsa; "EnsureResultsActivity"
0x1800a908a  lea     rcx, [rsp+448h+var_2F8]; struct wil::details::IFailureCallback *
0x1800a9092  call    ??0?$ActivityBase@VSearchIndexerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800a9097  mov     [rsp+448h+var_2F8], rsi
0x1800a909f  movups  xmm0, xmmword ptr [rbx]
0x1800a90a2  movdqu  xmmword ptr [rsp+448h+var_3E8.Data1], xmm0
0x1800a90a8  lea     rdx, [rsp+448h+var_3E8]; struct _GUID
0x1800a90ad  lea     rcx, [rsp+448h+var_2F8]; this
0x1800a90b5  call    ?StartActivity@EnsureResultsActivity@SearchIndexerTelemetry@@QEAAXU_GUID@@@Z; SearchIndexerTelemetry::EnsureResultsActivity::StartActivity(_GUID)
0x1800a90ba  nop
0x1800a90bb  lea     rdx, [rsp+448h+var_2F8]
0x1800a90c3  lea     rcx, [rsp+448h+var_1A8]
0x1800a90cb  call    ??4EnsureResultsActivity@SearchIndexerTelemetry@@QEAAAEAV01@$$QEAV01@@Z; SearchIndexerTelemetry::EnsureResultsActivity::operator=(SearchIndexerTelemetry::EnsureResultsActivity &&)
0x1800a90d0  lea     rcx, [rsp+448h+var_2F8]; this
0x1800a90d8  call    ??1EnsureResultsActivity@SearchIndexerTelemetry@@QEAA@XZ; SearchIndexerTelemetry::EnsureResultsActivity::~EnsureResultsActivity(void)
0x1800a90dd  cmp     [rdi+68h], r15
0x1800a90e1  jz      loc_1800AAA55
0x1800a90e7  mov     rcx, [rdi+18h]
0x1800a90eb  mov     rax, [rcx]
0x1800a90ee  mov     r8, r14
0x1800a90f1  lea     rdx, [rsp+448h+var_378]
0x1800a90f9  mov     rax, [rax+0B8h]
0x1800a9100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9105  nop
0x1800a9106  lea     r13, [rdi+1E0h]
0x1800a910d  mov     rdx, [rsp+448h+var_378]; struct inverted::IFreshTest *
0x1800a9115  mov     rcx, [r13+0]; this
0x1800a9119  call    ?SetFreshTest@CScanRestrictions@inverted@@QEAAXPEAUIFreshTest@2@@Z; inverted::CScanRestrictions::SetFreshTest(inverted::IFreshTest *)
0x1800a911e  nop
0x1800a911f  mov     byte ptr [rdi+0BCh], 1
0x1800a9126  mov     rcx, [rdi+68h]
0x1800a912a  mov     [rsp+448h+var_3A0], rcx
0x1800a9132  mov     rax, [rcx]
0x1800a9135  mov     rax, [rax+48h]
0x1800a9139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a913e  nop
0x1800a913f  lea     r12, [rdi+140h]
0x1800a9146  mov     rcx, r12
0x1800a9149  call    ?Empty@?$dynamic_sparse_bit@_K@@QEAAXXZ; dynamic_sparse_bit<unsigned __int64>::Empty(void)
0x1800a914e  mov     rbx, [r13+0]
0x1800a9152  mov     rcx, [rdi+98h]
0x1800a9159  test    rcx, rcx
0x1800a915c  jz      short loc_1800A916C
0x1800a915e  mov     rax, [rcx]
0x1800a9161  mov     rax, [rax+70h]
0x1800a9165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a916a  jmp     short loc_1800A916F
0x1800a916c  mov     rax, r15
0x1800a916f  mov     rdx, rax
0x1800a9172  mov     rcx, rbx
0x1800a9175  call    ?SetWidFilter@CScanRestrictions@inverted@@QEAAXPEBU?$dynamic_sparse_bit@_K@@@Z; inverted::CScanRestrictions::SetWidFilter(dynamic_sparse_bit<unsigned __int64> const *)
0x1800a917a  mov     rdx, [r14+8]
0x1800a917e  sub     rdx, [r14]
0x1800a9181  sar     rdx, 4
0x1800a9185  lea     rcx, aQueryStartingD; "QUERY: Starting - Decoders: %d"
0x1800a918c  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800a9191  mov     [rsp+448h+var_3E8.Data1], r15d
0x1800a9196  mov     qword ptr [rsp+448h+var_3E8.Data4], 0FFFFFFFFFFFFFFFFh
0x1800a919f  lea     rcx, [rsp+448h+var_3E8]; this
0x1800a91a4  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1800a91a9  nop
0x1800a91aa  mov     r10, [rdi+68h]
0x1800a91ae  mov     rax, [r10]
0x1800a91b1  mov     [rsp+448h+var_420], r12
0x1800a91b6  mov     ecx, [rdi+78h]
0x1800a91b9  mov     dword ptr [rsp+448h+var_428], ecx
0x1800a91bd  mov     r9, r13
0x1800a91c0  mov     r8, rdi
0x1800a91c3  mov     rdx, r14
0x1800a91c6  mov     rcx, r10
0x1800a91c9  mov     rax, [rax+18h]
0x1800a91cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a91d2  nop
0x1800a91d3  lea     rcx, [rsp+448h+var_3E8]; this
0x1800a91d8  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800a91dd  mov     rdx, r12
0x1800a91e0  mov     rcx, [r13+0]
0x1800a91e4  call    ?SetWidFilter@CScanRestrictions@inverted@@QEAAXPEBU?$dynamic_sparse_bit@_K@@@Z; inverted::CScanRestrictions::SetWidFilter(dynamic_sparse_bit<unsigned __int64> const *)
0x1800a91e9  cmp     cs:?g_fETWLoggingChecked@@3_NA, r15b; bool g_fETWLoggingChecked
0x1800a91f0  jnz     short loc_1800A91F7
0x1800a91f2  call    ?CheckEnabled@ETWLog@@CAXXZ; ETWLog::CheckEnabled(void)
0x1800a91f7  cmp     cs:?g_fETWLoggingEnabled@@3_NA, r15b; bool g_fETWLoggingEnabled
0x1800a91fe  jnz     short loc_1800A9218
0x1800a9200  lea     rdx, MSSearchTraceId_ETWLogging; EventDescriptor
0x1800a9207  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x1800a920e  call    cs:__imp_EventEnabled
0x1800a9214  test    al, al
0x1800a9216  jz      short loc_1800A922E
0x1800a9218  mov     rcx, r12
0x1800a921b  call    ?size@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAKAEBU?$dynamic_sparse_bit@_K@@@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size(dynamic_sparse_bit<unsigned __int64> const &)
0x1800a9220  mov     edx, eax
0x1800a9222  lea     rcx, aQueryFilterExe; "QUERY: Filter Executed - Results: %d  ("...
0x1800a9229  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800a922e  mov     rcx, [r13+0]
0x1800a9232  mov     rax, [rcx+0A8h]
0x1800a9239  cmp     [rax], r15b
0x1800a923c  jnz     short loc_1800A9273
0x1800a923e  mov     rax, [rcx+0B0h]
0x1800a9245  cmp     [rax], r15b
0x1800a9248  jnz     short loc_1800A9273
0x1800a924a  mov     rax, [rcx+0A0h]
0x1800a9251  cmp     [rax], r15b
0x1800a9254  jnz     short loc_1800A9273
0x1800a9256  mov     rcx, [rdi+28h]
0x1800a925a  mov     rax, [rcx]
0x1800a925d  mov     r9, r12
0x1800a9260  lea     r8, [rdi+18h]
0x1800a9264  mov     dl, [rdi+0BDh]
0x1800a926a  mov     rax, [rax+20h]
0x1800a926e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9273  mov     rdx, r13
0x1800a9276  mov     rcx, r14
0x1800a9279  call    ?TrimDecoders@inverted@@YAXPEAV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@std@@AEBV?$shared_ptr@VCScanRestrictions@inverted@@@3@@Z; inverted::TrimDecoders(std::vector<std::shared_ptr<inverted::IDecoder>> *,std::shared_ptr<inverted::CScanRestrictions> const &)
0x1800a927e  lea     r15, [rdi+158h]
0x1800a9285  mov     rbx, [r15]
0x1800a9288  cmp     rbx, [r15+8]
0x1800a928c  jz      short loc_1800A9294
0x1800a928e  mov     [r15+8], rbx
0x1800a9292  jmp     short loc_1800A9298
0x1800a9294  mov     rbx, [r15+8]
0x1800a9298  xor     esi, esi
0x1800a929a  mov     [rsp+448h+var_408], esi
0x1800a929e  mov     rcx, r12
0x1800a92a1  call    ?size@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAKAEBU?$dynamic_sparse_bit@_K@@@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size(dynamic_sparse_bit<unsigned __int64> const &)
0x1800a92a6  mov     r9d, eax
0x1800a92a9  lea     rax, [rsp+448h+var_408]
0x1800a92ae  mov     [rsp+448h+var_428], rax
0x1800a92b3  mov     r8, rbx
0x1800a92b6  lea     rdx, [rsp+448h+var_3C8]
0x1800a92be  mov     rcx, r15
0x1800a92c1  call    ?insert@?$vector@IV?$allocator@I@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@_KAEBI@Z; std::vector<uint>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uint>>>,unsigned __int64,uint const &)
0x1800a92c6  mov     rax, [rdi+160h]
0x1800a92cd  mov     [rsp+448h+var_428], rax
0x1800a92d2  mov     r9, [r15]
0x1800a92d5  lea     rdx, [rsp+448h+var_3C8]
0x1800a92dd  mov     rcx, r12
0x1800a92e0  call    ??$CopyTo@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@@?$dynamic_sparse_bit@_K@@QEBA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@KV12@0@Z; dynamic_sparse_bit<unsigned __int64>::CopyTo<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>>(ulong,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>)
0x1800a92e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57813035@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57813035@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57813035> `wil::Feature<__WilFeatureTraits_Feature_57813035>::GetImpl(void)'::`2'::impl
0x1800a92ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57813035@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57813035>::__private_IsEnabled(void)
0x1800a92f1  test    al, al
0x1800a92f3  jz      short loc_1800A9303
0x1800a92f5  mov     rax, [r15+8]
0x1800a92f9  cmp     rax, [r15]
0x1800a92fc  jnz     short loc_1800A9303
0x1800a92fe  call    ?ZeroResultQuery@SearchIndexerTelemetryAggregatedLow@@SAXXZ; SearchIndexerTelemetryAggregatedLow::ZeroResultQuery(void)
0x1800a9303  mov     r8, [r14+8]
0x1800a9307  sub     r8, [r14]
0x1800a930a  sar     r8, 4
0x1800a930e  mov     rdx, [r15+8]
0x1800a9312  sub     rdx, [r15]
0x1800a9315  sar     rdx, 2
0x1800a9319  lea     rcx, aQueryFilterExe_0; "QUERY: Filter Executed - Results: %d, D"...
0x1800a9320  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800a9325  test    byte ptr [rdi+78h], 1
0x1800a9329  jz      loc_1800AA6AD
0x1800a932f  mov     rcx, [r13+0]
0x1800a9333  mov     rax, [rcx+0A8h]
0x1800a933a  cmp     [rax], sil
0x1800a933d  jnz     loc_1800AA6AD
0x1800a9343  mov     rax, [rcx+0B0h]
0x1800a934a  cmp     [rax], sil
0x1800a934d  jnz     loc_1800AA6AD
0x1800a9353  mov     rax, [rcx+0A0h]
0x1800a935a  cmp     [rax], sil
0x1800a935d  jnz     loc_1800AA6AD
0x1800a9363  lea     r13, [rdi+170h]
0x1800a936a  mov     r8, [r13+0]
0x1800a936e  cmp     r8, [r13+8]
0x1800a9372  jz      short loc_1800A937A
0x1800a9374  mov     [r13+8], r8
0x1800a9378  jmp     short loc_1800A937E
0x1800a937a  mov     r8, [r13+8]
0x1800a937e  mov     r9, [r15+8]
0x1800a9382  sub     r9, [r15]
0x1800a9385  sar     r9, 2
0x1800a9389  lea     rax, dword_1803195E4
0x1800a9390  mov     [rsp+448h+var_428], rax
0x1800a9395  lea     rdx, [rsp+448h+var_3C8]
0x1800a939d  mov     rcx, r13
0x1800a93a0  call    ?insert@?$vector@GV?$allocator@G@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@2@_KAEBG@Z; std::vector<ushort>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,unsigned __int64,ushort const &)
0x1800a93a5  mov     r10, [rdi+68h]
0x1800a93a9  mov     r8, [r15]
0x1800a93ac  mov     rax, [r10]
0x1800a93af  mov     rdx, [rdi+160h]
0x1800a93b6  sub     rdx, r8
0x1800a93b9  sar     rdx, 2
0x1800a93bd  mov     rcx, [r13+0]
0x1800a93c1  mov     [rsp+448h+var_418], rcx
0x1800a93c6  mov     [rsp+448h+var_420], r8
0x1800a93cb  mov     dword ptr [rsp+448h+var_428], edx
0x1800a93cf  mov     r9, r12
0x1800a93d2  mov     r8, rdi
0x1800a93d5  mov     rdx, r14
0x1800a93d8  mov     rcx, r10
0x1800a93db  mov     rax, [rax+20h]
0x1800a93df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60586217@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60586217@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60586217> `wil::Feature<__WilFeatureTraits_Feature_60586217>::GetImpl(void)'::`2'::impl
0x1800a93eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60586217@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60586217>::__private_IsEnabled(void)
0x1800a93f0  test    al, al
0x1800a93f2  jz      loc_1800A9963
0x1800a93f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60977300@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60977300@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300> `wil::Feature<__WilFeatureTraits_Feature_60977300>::GetImpl(void)'::`2'::impl
0x1800a93ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60977300@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300>::__private_IsEnabled(void)
0x1800a9404  test    al, al
0x1800a9406  jz      loc_1800A9963
0x1800a940c  mov     rax, [rdi]
0x1800a940f  mov     rcx, rdi
0x1800a9412  mov     rax, [rax+118h]
0x1800a9419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a941e  cmp     qword ptr [rax+18h], 7
0x1800a9423  jbe     short loc_1800A9428
0x1800a9425  mov     rax, [rax]
0x1800a9428  lea     rdx, aExplorerExe; "explorer.exe"
0x1800a942f  mov     rcx, rax
0x1800a9432  call    cs:__imp__o__wcsicmp
0x1800a9438  test    eax, eax
0x1800a943a  jnz     loc_1800A9963
0x1800a9440  lea     rcx, qword_180369748
0x1800a9447  call    ?size@?$config_vector@Ureranking_point@inverted@@@fc@@QEBA_KXZ; fc::config_vector<inverted::reranking_point>::size(void)
0x1800a944c  test    rax, rax
0x1800a944f  jz      loc_1800A9963
0x1800a9455  mov     [rsp+448h+var_3F0], rsi
0x1800a945a  lea     rdx, [rsp+448h+var_338]
0x1800a9462  lea     rcx, [rsp+448h+var_3F0]
0x1800a9467  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_L1RankerQueryTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_L1RankerQueryTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>>::start_and_watch_errors(void)
0x1800a946c  lea     rcx, [rsp+448h+var_3F0]
0x1800a9471  call    ??1?$com_ptr_t@V?$merged_data@U_tip_L1RankerQueryTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_L1RankerQueryTipTest,_tip_L1RankerQueryTipTest>,wil::err_returncode_policy>(void)
0x1800a9476  nop
0x1800a9477  mov     rdx, [rdi+178h]
0x1800a947e  mov     rax, [r13+0]
0x1800a9482  xorps   xmm0, xmm0
0x1800a9485  movdqu  [rsp+448h+var_350], xmm0
0x1800a948e  mov     [rsp+448h+var_340], rsi
0x1800a9496  mov     [rsp+448h+var_400], rax
0x1800a949b  mov     [rsp+448h+var_3F8], rdx
0x1800a94a0  sub     rdx, rax
0x1800a94a3  sar     rdx, 1
0x1800a94a6  lea     r9, [rsp+448h+var_3F8]
0x1800a94ab  lea     r8, [rsp+448h+var_400]
0x1800a94b0  lea     rcx, [rsp+448h+var_350]
0x1800a94b8  call    ??$_Construct_n@PEAGPEAG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K$$QEAPEAG1@Z; std::vector<ushort>::_Construct_n<ushort *,ushort *>(unsigned __int64,ushort * &&,ushort * &&)
0x1800a94bd  nop
0x1800a94be  mov     rbx, [r15]
0x1800a94c1  mov     rdx, [r15+8]
0x1800a94c5  sub     rdx, rbx
0x1800a94c8  sar     rdx, 2
  ... truncated ...
```
