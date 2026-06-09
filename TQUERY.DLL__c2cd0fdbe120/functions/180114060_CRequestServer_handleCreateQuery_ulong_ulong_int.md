# CRequestServer::handleCreateQuery(ulong,ulong &,int)

- ea: `0x180114060`
- end: `0x180115b19`
- name: `?handleCreateQuery@CRequestServer@@AEAA?AW4RequestState@@KAEAKH@Z`
- size: `6841`
- prototype: ``
- caller_count: `2`
- callee_count: `84`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180114050`
- `0x180201220`

## callees

- `0x18002be24`
- `0x180036d60`
- `0x180038f08`
- `0x18005cd60`
- `0x18005ce7c`
- `0x1800601c0`
- `0x1800650a0`
- `0x180065160`
- `0x180065188`
- `0x1800656a8`
- `0x1800663c0`
- `0x180066f08`
- `0x180067350`
- `0x1800674ac`
- `0x180067814`
- `0x180068e90`
- `0x1800690f8`
- `0x180069160`
- `0x18006a73c`
- `0x18006a95c`
- `0x18006b050`
- `0x18006c870`
- `0x1800703f4`
- `0x1800709e0`
- `0x180070fb4`
- `0x180072768`
- `0x180075268`
- `0x18008a098`
- `0x18008b084`
- `0x18008bd64`
- `0x18008c14c`
- `0x18008cfbc`
- `0x18008e438`
- `0x18008fd9c`
- `0x1800953e0`
- `0x1800a4764`
- `0x1800ae510`
- `0x1800af0dc`
- `0x1800c52f8`
- `0x1800deeec`
- `0x1800e5c94`
- `0x1800e7194`
- `0x1800ef5c8`
- `0x1800ef7a8`
- `0x1800f1ae0`
- `0x1800f4878`
- `0x1800f5a0c`
- `0x1800fb7b0`
- `0x1800fecc4`
- `0x1801010e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180114528`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18011455d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180114528`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18011455d`
- `OLEAUT32!__imp_SysFreeString` at `0x180114e2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180114e2c`

## string_xrefs

- `0x180114a6e`: `IndexerQueryExecutionService`
- `0x18011411e`: `HandleCreateQueryActivity`
- `0x180114151`: `HandleCreateQueryActivity`
- `0x180115a34`: `[Query] DoCreateQuery - GetPropertyDatabase failed 0x%x\n`
- `0x1801159ca`: `[Query] DoCreateQuery - QI for property mapper failed 0x%x\n`
- `0x18011598b`: `[Query] CRequestServer::DoCreateQuery, GetPropertyMapper failed\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
__int64 __fastcall CRequestServer::handleCreateQuery(unsigned int *a1, int a2, _DWORD *a3, int a4)
{
  CRequestServer *v6; // r14
  struct ICiCDocStore **v7; // rdi
  int v8; // eax
  _QWORD *v9; // rbx
  int v10; // eax
  int v11; // eax
  char *v12; // rcx
  char *v13; // rbx
  unsigned int v14; // edx
  struct CRestriction *v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // r8
  struct ICiCDocStore *v18; // rax
  CPidMapper *v19; // rdi
  char *v20; // rbx
  char IsEnabled; // al
  _BYTE *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rdx
  _QWORD *v25; // rax
  int v26; // edx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // r12d
  __int64 v30; // rbx
  int v31; // eax
  struct ICiCDocStore **v32; // r12
  int v33; // eax
  int v34; // eax
  int v35; // edi
  const wchar_t *v36; // r9
  unsigned int v37; // edi
  unsigned int v38; // edi
  CPidMapper *v39; // r14
  struct CColumnGroupArray *v40; // r12
  unsigned int v41; // edx
  struct CSortSets *v42; // rbx
  CPidRemapper *v43; // rdi
  int v44; // eax
  unsigned int v45; // r15d
  int v46; // r15d
  int v47; // eax
  __int64 v48; // r12
  int v49; // eax
  char *v50; // r15
  __int64 v51; // rax
  bool v52; // r14
  unsigned int v53; // r12d
  unsigned int v54; // r15d
  bool v55; // r14
  __int64 v56; // r14
  int v57; // r12d
  int v58; // eax
  unsigned int v59; // r14d
  int v60; // eax
  int v61; // eax
  CRequestServer *v62; // r14
  int v63; // eax
  int v64; // eax
  int v65; // ecx
  unsigned int v66; // eax
  unsigned int v67; // r8d
  OLECHAR *v68; // rcx
  int v69; // eax
  __int64 v70; // rax
  unsigned __int64 v71; // rdx
  __int64 v72; // rax
  CSortSet *v73; // rbx
  int v74; // r8d
  unsigned int i; // esi
  __int64 v76; // rdx
  _QWORD *v77; // rcx
  std::_Ref_count_base *v78; // rax
  const struct CSortSet *v79; // rbx
  __int64 *v80; // rsi
  __int64 v81; // rdi
  const wchar_t *v82; // r9
  CRequestServer *v83; // rax
  char *v84; // rdi
  unsigned __int64 v85; // rdx
  char *v86; // rax
  int *v87; // r14
  __int64 VIQuery; // rax
  __int64 *v89; // rdi
  unsigned int v90; // edx
  unsigned int v92; // eax
  unsigned int v93; // eax
  unsigned int v94; // eax
  unsigned int v95; // eax
  unsigned int v96; // eax
  unsigned int v97; // eax
  unsigned int v98; // eax
  unsigned int v99; // eax
  unsigned int v100; // eax
  int v101; // [rsp+20h] [rbp-1058h]
  int v102; // [rsp+20h] [rbp-1058h]
  int v103; // [rsp+20h] [rbp-1058h]
  int v104; // [rsp+20h] [rbp-1058h]
  struct ICiCDocStore **v105; // [rsp+20h] [rbp-1058h]
  struct ICiAdminParams *v106; // [rsp+28h] [rbp-1050h]
  struct UserSID *v107; // [rsp+38h] [rbp-1040h]
  int v108; // [rsp+40h] [rbp-1038h]
  unsigned int v109; // [rsp+80h] [rbp-FF8h] BYREF
  int v110; // [rsp+84h] [rbp-FF4h] BYREF
  struct ICiCDocStore *v111; // [rsp+88h] [rbp-FF0h] BYREF
  struct CColumnGroupArray *v112; // [rsp+90h] [rbp-FE8h] BYREF
  unsigned int v113[2]; // [rsp+98h] [rbp-FE0h] BYREF
  struct ICiCQuerySession *v114; // [rsp+A0h] [rbp-FD8h] BYREF
  CPidMapper *v115; // [rsp+A8h] [rbp-FD0h] BYREF
  __int64 v116; // [rsp+B0h] [rbp-FC8h] BYREF
  _BYTE *v117; // [rsp+B8h] [rbp-FC0h]
  char *v118; // [rsp+C0h] [rbp-FB8h]
  unsigned int v119[2]; // [rsp+C8h] [rbp-FB0h] BYREF
  void *v120; // [rsp+D0h] [rbp-FA8h]
  CRequestServer *v121; // [rsp+D8h] [rbp-FA0h]
  struct ICiCDocStore **v122; // [rsp+E0h] [rbp-F98h]
  int *v123; // [rsp+E8h] [rbp-F90h]
  wchar_t **v124; // [rsp+F0h] [rbp-F88h]
  char *v125; // [rsp+F8h] [rbp-F80h]
  __int64 v126; // [rsp+100h] [rbp-F78h] BYREF
  __int64 v127; // [rsp+108h] [rbp-F70h] BYREF
  __int64 v128; // [rsp+110h] [rbp-F68h] BYREF
  struct CSortSets *v129[2]; // [rsp+118h] [rbp-F60h] BYREF
  struct ICiAdminParams *v130; // [rsp+128h] [rbp-F50h] BYREF
  __int64 *v131; // [rsp+130h] [rbp-F48h]
  __int64 v132; // [rsp+138h] [rbp-F40h] BYREF
  void *v133; // [rsp+140h] [rbp-F38h] BYREF
  CPidRemapper *v134; // [rsp+148h] [rbp-F30h] BYREF
  __int64 v135; // [rsp+150h] [rbp-F28h] BYREF
  void *v136; // [rsp+158h] [rbp-F20h]
  CPidRemapper *v137; // [rsp+160h] [rbp-F18h] BYREF
  __int64 v138; // [rsp+168h] [rbp-F10h] BYREF
  std::_Ref_count_base *v139; // [rsp+170h] [rbp-F08h]
  _DWORD *v140; // [rsp+178h] [rbp-F00h]
  struct CColumnGroupArray *v141; // [rsp+180h] [rbp-EF8h] BYREF
  _QWORD v142[2]; // [rsp+188h] [rbp-EF0h] BYREF
  __int64 v143; // [rsp+198h] [rbp-EE0h] BYREF
  HANDLE TokenHandle; // [rsp+1A0h] [rbp-ED8h] BYREF
  std::_Ref_count_base *v145[2]; // [rsp+1A8h] [rbp-ED0h] BYREF
  struct CLangList *v146; // [rsp+1B8h] [rbp-EC0h] BYREF
  DWORD ReturnLength; // [rsp+1C0h] [rbp-EB8h] BYREF
  void *Block; // [rsp+1C8h] [rbp-EB0h]
  _QWORD v149[2]; // [rsp+1D0h] [rbp-EA8h] BYREF
  int v150; // [rsp+1E0h] [rbp-E98h]
  int *v151; // [rsp+1E8h] [rbp-E90h]
  char *v152; // [rsp+1F0h] [rbp-E88h]
  struct ICiCDocStore **v153; // [rsp+1F8h] [rbp-E80h]
  _QWORD v154[2]; // [rsp+200h] [rbp-E78h] BYREF
  __int64 v155; // [rsp+210h] [rbp-E68h] BYREF
  int v156; // [rsp+218h] [rbp-E60h]
  _QWORD v157[4]; // [rsp+220h] [rbp-E58h] BYREF
  __int16 v158; // [rsp+240h] [rbp-E38h]
  unsigned int v159; // [rsp+248h] [rbp-E30h]
  unsigned int v160; // [rsp+24Ch] [rbp-E2Ch]
  bool v161; // [rsp+250h] [rbp-E28h]
  void *v162; // [rsp+258h] [rbp-E20h]
  int v163; // [rsp+260h] [rbp-E18h]
  __int64 v164; // [rsp+270h] [rbp-E08h] BYREF
  struct CRestriction **v165; // [rsp+278h] [rbp-E00h]
  unsigned int v166; // [rsp+300h] [rbp-D78h]
  _BYTE v167[160]; // [rsp+310h] [rbp-D68h] BYREF
  struct CRestriction *v168; // [rsp+3B0h] [rbp-CC8h] BYREF
  std::_Ref_count_base *v169; // [rsp+3B8h] [rbp-CC0h]
  __int128 v170; // [rsp+3C0h] [rbp-CB8h] BYREF
  __int64 v171; // [rsp+3D0h] [rbp-CA8h]
  __int64 v172; // [rsp+3D8h] [rbp-CA0h]
  __int64 *v173; // [rsp+3E0h] [rbp-C98h] BYREF
  int v174; // [rsp+3E8h] [rbp-C90h]
  GUID v175; // [rsp+3ECh] [rbp-C8Ch]
  int v176; // [rsp+3FCh] [rbp-C7Ch]
  _DWORD v177[8]; // [rsp+400h] [rbp-C78h] BYREF
  _DWORD v178[4]; // [rsp+420h] [rbp-C58h] BYREF
  _QWORD v179[4]; // [rsp+430h] [rbp-C48h] BYREF
  wchar_t *v180; // [rsp+450h] [rbp-C28h] BYREF
  unsigned int v181; // [rsp+45Ch] [rbp-C1Ch]
  unsigned int v182; // [rsp+460h] [rbp-C18h]
  wchar_t *v183; // [rsp+464h] [rbp-C14h] BYREF
  char v184; // [rsp+474h] [rbp-C04h] BYREF
  _BYTE v185[40]; // [rsp+488h] [rbp-BF0h] BYREF
  int v186; // [rsp+4B0h] [rbp-BC8h] BYREF
  void *v187; // [rsp+4B8h] [rbp-BC0h]
  _BYTE v188[64]; // [rsp+4C0h] [rbp-BB8h] BYREF
  _QWORD v189[4]; // [rsp+500h] [rbp-B78h] BYREF
  __int64 v190; // [rsp+520h] [rbp-B58h] BYREF
  int v191; // [rsp+528h] [rbp-B50h]
  DBID v192; // [rsp+530h] [rbp-B48h]
  __int16 v193; // [rsp+550h] [rbp-B28h]
  unsigned int v194; // [rsp+558h] [rbp-B20h]
  _QWORD v195[42]; // [rsp+570h] [rbp-B08h] BYREF
  _QWORD v196[42]; // [rsp+6C0h] [rbp-9B8h] BYREF
  _QWORD v197[261]; // [rsp+810h] [rbp-868h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1078h] [rbp+0h]

  v140 = a3;
  v6 = (CRequestServer *)a1;
  v121 = (CRequestServer *)a1;
  v129[1] = (struct CSortSets *)a1;
  v136 = a3;
  if ( (byte_180368442 & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(&Microsoft_Windows_Search_Core_Context, MSSearchTraceId_ServerQuery_Create, a1[64]);
  if ( (*((_BYTE *)v6 + 112) & 1) == 0 )
  {
    v93 = wil::verify_hresult<long>(2147942405LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v93,
      v101);
  }
  v7 = (struct ICiCDocStore **)((char *)v6 + 104);
  v122 = (struct ICiCDocStore **)((char *)v6 + 104);
  if ( !*((_QWORD *)v6 + 13) || (v131 = (__int64 *)((char *)v6 + 128), *((_QWORD *)v6 + 16)) )
  {
    v92 = wil::verify_hresult<long>(3221225485LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8EA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v92,
      v101);
  }
  wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v195);
  v195[0] = &SearchIndexerTelemetry::HandleCreateQueryActivity::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
  {
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v197);
    v197[0] = &SearchIndexerTelemetry::HandleCreateQueryActivity::`vftable';
    SearchIndexerTelemetry::HandleCreateQueryActivity::StartActivity((SearchIndexerTelemetry::HandleCreateQueryActivity *)v197);
    SearchIndexerTelemetry::HandleCreateQueryActivity::operator=(v195, v197);
    SearchIndexerTelemetry::HandleCreateQueryActivity::~HandleCreateQueryActivity((SearchIndexerTelemetry::HandleCreateQueryActivity *)v197);
  }
  if ( a4 )
  {
    v110 = 0;
    v8 = (*(__int64 (__fastcall **)(struct ICiCDocStore *, int *))(*(_QWORD *)*v7 + 80LL))(*v7, &v110);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8FB,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)v8,
        v101);
    if ( v110 )
    {
      v94 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8FF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)v94,
        v101);
    }
  }
  v9 = (_QWORD *)((char *)v6 + 120);
  if ( !*((_QWORD *)v6 + 15) )
  {
    v116 = 0;
    v10 = (*(__int64 (__fastcall **)(struct ICiCDocStore *, __int64 *))(*(_QWORD *)*v7 + 32LL))(*v7, &v116);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x908,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)v10,
        v101);
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v116)(
            v116,
            &GUID_8e4225c5_886c_4a40_914f_01765e175def,
            (__int64)v6 + 120);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)v11,
        v101);
    ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v116);
  }
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v9 + 48LL))(*v9, 30);
  v155 = *v9;
  v156 = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v155 + 48LL))(v155, 32);
  v12 = (char *)*((_QWORD *)v6 + 22);
  v120 = v12;
  v13 = (char *)v6 + 624;
  if ( v12 )
    v13 = v12;
  v163 = *((_DWORD *)v6 + 46);
  *((_QWORD *)v6 + 22) = 0;
  *((_DWORD *)v6 + 46) = 0;
  v162 = v12;
  v116 = 0;
  TCountedGrowableArrayOfPointer<CRestriction,16>::TCountedGrowableArrayOfPointer<CRestriction,16>(&v164);
  v129[0] = 0;
  v128 = 0;
  CRowsetProperties::CRowsetProperties((CRowsetProperties *)&v180, v14);
  v115 = 0;
  v137 = (CPidRemapper *)operator new(0x20u);
  v112 = CColumnGroupArray::CColumnGroupArray(v137);
  v141 = v112;
  v119[0] = 0;
  UnPickle(
    *((_DWORD *)v6 + 22) & 0xFFFEFFFF,
    (__int64)&v128,
    (CRowsetProperties *)&v180,
    (__int64)&v115,
    v112,
    (__int64)v119,
    (__int64)(v13 + 16),
    a2 - 16);
  if ( v166 > 1 )
  {
    v95 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x938,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v95,
      v102);
  }
  v15 = 0;
  v168 = 0;
  if ( v166 == 1 )
  {
    v15 = *v165;
    v168 = *v165;
  }
  v16 = v116;
  if ( !v116 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x93F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0x80070057LL,
      v102);
  v119[1] = -1;
  v118 = (char *)v6 + 264;
  v17 = *((_QWORD *)v6 + 33);
  if ( *(_BYTE *)(v17 + 384) )
  {
    v111 = 0;
    CRequestServer::_FindReplacementVolumeCatalog(v6, v15, *(_WORD *)(v17 + 386), &v119[1], &v111);
    if ( v111 )
    {
      XInterface<ICiCDocStore>::Free((char *)v6 + 104);
      v18 = v111;
      v111 = 0;
      *v7 = v18;
    }
    ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v111);
  }
  v123 = (int *)((char *)v6 + 256);
  v19 = v115;
  *((_DWORD *)v115 + 16) = *((_DWORD *)v6 + 64);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) )
  {
    v124 = &v183;
    v20 = &v184;
  }
  else
  {
    v124 = 0;
    v20 = 0;
  }
  v125 = v20;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60977300>::GetImpl'::`2'::impl);
  v22 = v185;
  if ( !IsEnabled )
    v22 = 0;
  v117 = v22;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    SearchIndexerTelemetry::HandleCreateQueryActivity::HandleCreateQueryCorrID<_GUID const &>(v195, v20);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    v23 = (void *)*((_QWORD *)v6 + 41);
  else
    v23 = 0;
  PerUserCatalogNameForCorruption::SetCatalog(v23);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
  {
    v24 = 0;
    if ( *((_DWORD *)v19 + 4) )
    {
      while ( 1 )
      {
        v25 = (_QWORD *)CDynArray<CInGroupSortAggregSet>::Get(v19, v24);
        if ( *v25 == v28 && v25[1] == v27 )
          break;
        v24 = (unsigned int)(v26 + 1);
        if ( (unsigned int)v24 >= *((_DWORD *)v19 + 4) )
          goto LABEL_40;
      }
      v31 = CRequestServer::SwitchToSystemCatalog(v6);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x972,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
          (const char *)(unsigned int)v31,
          v102);
    }
  }
LABEL_40:
  v29 = 1;
  v110 = 1;
  v30 = v128;
  if ( v128 )
  {
    v29 = *(_DWORD *)v128 + 1;
    v110 = v29;
  }
  CDynArrayInPlace<unsigned long>::SetExactSize((char *)v6 + 560, v29);
  CDynArrayInPlace<unsigned long>::SetExactSize((char *)v6 + 576, v29);
  CDynArray<CTableColumnSet>::SetExactSize((char *)v6 + 592, v29 + 1);
  CDynArray<CTableColumnSet>::SetExactSize((char *)v6 + 608, v29 + 1);
  if ( 4 * (unsigned __int64)v29 + 24 > 0x1300 )
  {
    v96 = wil::verify_hresult<long>(3221225485LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x989,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v96,
      v102);
  }
  v32 = v122;
  v153 = v122;
  v127 = 0;
  v33 = (*(__int64 (__fastcall **)(struct ICiCDocStore *, __int64 *))(*(_QWORD *)*v122 + 32LL))(*v122, &v127);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x991,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v33,
      v102);
  v135 = 0;
  v34 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v127)(v127, &IID_ICiFrameworkQuery, &v135);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x995,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v34,
      v102);
  v126 = 0;
  v35 = (*(__int64 (__fastcall **)(struct ICiCDocStore *, __int64 *))(*(_QWORD *)*v32 + 64LL))(*v32, &v126);
  if ( v35 < 0 )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x9A1,
      (unsigned int)L"[Query] CRequestServer::DoCreateQuery, GetPropertyMapper failed\n",
      v36);
    v97 = wil::verify_hresult<long>((unsigned int)v35);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9A2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v97,
      v102);
  }
  TCountedGrowableArrayOfPointer<CRestriction,16>::TCountedGrowableArrayOfPointer<CRestriction,16>(v167);
  v37 = v166;
  v186 = 16;
  v187 = v188;
  XGrowable<unsigned long,5>::SetSize(&v186, 16);
  XGrowable<unsigned long,5>::SetSize(&v186, v37);
  v149[0] = 0;
  v149[1] = 0;
  v150 = 1;
  CTKPLiteHashMap<TLMString<32,32,1024>,CWordTableEntry>::Init(v149);
  v154[0] = &CPidConverter::`vftable';
  v154[1] = v126;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 8LL))(v126);
  *((_QWORD *)v115 + 5) = v154;
  v38 = 0;
  if ( *((_DWORD *)v112 + 4) )
  {
    v39 = v115;
    v40 = v112;
    do
    {
      v41 = *(_DWORD *)CDynArray<CInGroupSortAggregSet>::Get(v40, v38);
      CPidMapper::PidToRealPid(v39, v41);
      ++v38;
    }
    while ( v38 < *((_DWORD *)v40 + 4) );
    v6 = v121;
    v32 = v122;
  }
  v137 = (CPidRemapper *)operator new(0x58u);
  v107 = (struct UserSID *)v30;
  v42 = v129[0];
  v43 = (CPidRemapper *)CPidRemapper::CPidRemapper(v137, v102, v16, v129[0], (__int64)v107);
  v134 = v43;
  v177[0] = 1231625360;
  v177[1] = 270171671;
  v177[2] = 531625;
  v177[3] = -1446171093;
  v177[4] = 1;
  v177[6] = 5;
  CPidRemapper::NameToReal(v43, (const struct CFullPropSpec *)v177);
  v133 = 0;
  v44 = CPidRemapper::QueryInterface(v43, &IID_ICiQueryPropertyMapper, &v133);
  v45 = v44;
  if ( v44 < 0 )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x9CA,
      (unsigned int)L"[Query] DoCreateQuery - QI for property mapper failed 0x%x\n",
      (const wchar_t *)(unsigned int)v44);
    v98 = wil::verify_hresult<long>(v45);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9CB,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v98,
      v103);
  }
  v46 = *((_DWORD *)v43 + 2) != 0 ? 0x80 : 0;
  v109 = *((_DWORD *)v43 + 3) != 0;
  v132 = 0;
  v47 = (**(__int64 (__fastcall ***)(struct ICiCDocStore *, GUID *, __int64 *))*v32)(
          *v32,
          &GUID_487988ac_86f6_46c1_af89_9a407f39146e,
          &v132);
  if ( v47 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D3,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v47,
      v103);
  v114 = 0;
  v48 = v132;
  v111 = *(struct ICiCDocStore **)(*(_QWORD *)v132 + 64LL);
  IsCDPLEnabled();
  v49 = ((__int64 (__fastcall *)(__int64, struct ICiCQuerySession **, _QWORD))v111)(v48, &v114, v109 | v46);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v49,
      v103);
  v50 = v118;
  v152 = v118;
  v51 = QueryFromSession(&v138, v114);
  std::shared_ptr<inverted::ICatalogStorage>::operator=((char *)v6 + 136, v51);
  if ( v139 )
    std::_Ref_count_base::_Decref(v139);
  v113[0] = 0;
  v109 = 0;
  GetQueryTelemetryInfo((char *)v6 + 136, v113, &v109);
  memset(v157, 0, sizeof(v157));
  v158 = 0;
  v52 = *(_QWORD *)(*(_QWORD *)v50 + 408LL) != 0;
  BaseTelemetryAggregatedEvent::StartEvent((BaseTelemetryAggregatedEvent *)v157);
  v53 = v113[0];
  v159 = v113[0];
  v54 = v109;
  v160 = v109;
  v161 = v52;
  v55 = *(_QWORD *)(*(_QWORD *)v118 + 408LL) != 0;
  wil::ActivityBase<SearchIndexerDiagnosticsLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerDiagnosticsLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v196);
  v196[0] = &SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionService::`vftable';
  SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionService::StartActivity(
    (SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionService *)v196,
    v53,
    v54,
    v55);
  CreateScreenOnQueryEvent(&v138);
  v56 = v138;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 8LL))(v138);
  v178[0] = 2048;
  v57 = v110;
  v178[2] = v110;
  (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v56 + 24LL))(v56, v178);
  v143 = 0;
  v58 = (*(__int64 (__fastcall **)(struct ICiCQuerySession *, __int64 *))(*(_QWORD *)v114 + 104LL))(v114, &v143);
  v59 = v58;
  if ( v58 < 0 )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x9EE,
      (unsigned int)L"[Query] DoCreateQuery - GetPropertyDatabase failed 0x%x\n",
      (const wchar_t *)(unsigned int)v58);
    v99 = wil::verify_hresult<long>(v59);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9EF,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v99,
      v103);
  }
  if ( v143 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v143 + 72LL))(v143, 0);
  TokenHandle = 0;
  v60 = (*(__int64 (__fastcall **)(struct ICiCQuerySession *, HANDLE *))(*(_QWORD *)v114 + 112LL))(v114, &TokenHandle);
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v60,
      v103);
  UserSID::UserSID(&ReturnLength, TokenHandle);
  *(_OWORD *)v145 = 0;
  v130 = 0;
  v61 = (*(__int64 (__fastcall **)(__int64, struct ICiAdminParams **))(*(_QWORD *)v127 + 80LL))(v127, &v130);
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9FF,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v61,
      v103);
  v137 = v130;
  v62 = v121;
  if ( *((_DWORD *)v121 + 23) && !CRequestServer::IsValidRemoteRestriction(v121, v168) )
  {
    v100 = wil::verify_hresult<long>(2147747608LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)v100,
      v103);
  }
  v146 = 0;
  v63 = (*(__int64 (__fastcall **)(__int64, struct CLangList **))(*(_QWORD *)v135 + 40LL))(v135, &v146);
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v63,
      v103);
  memset_0(&v190, 0, 0x48u);
  v190 = 34;
  v191 = 0;
  v192 = DB_NULLID;
  v193 = 3;
  v194 = v182;
  v176 = 0;
  v174 = 1;
  v175 = DBPROPSET_ROWSET;
  v173 = &v190;
  v64 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 **))(**((_QWORD **)v62 + 35) + 40LL))(
          *((_QWORD *)v62 + 35),
          1,
          &v173);
  if ( v64 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v64,
      v103);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) )
  {
    memset_0(v197, 0, 0x90u);
    v113[0] = 0;
    v142[0] = v197;
    v142[1] = v113;
    lambda_6d05f395b6a86eb164d9118f3fa7a524_::operator()(v142, v124, 17);
    lambda_6d05f395b6a86eb164d9118f3fa7a524_::operator()(v142, v125, 18);
    if ( v113[0] )
    {
      v172 = 629145848;
      *((_QWORD *)&v170 + 1) = v113[0] | 0xA7AC77ED00000000uLL;
      v171 = 0x200098A711CEF8D7LL;
      *(_QWORD *)&v170 = v197;
      v65 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *))(**((_QWORD **)v62 + 35) + 40LL))(
              *((_QWORD *)v62 + 35),
              1,
              &v170);
      LODWORD(v111) = v65;
      v66 = 0;
      v109 = 0;
      v67 = v113[0];
      if ( v113[0] )
      {
        do
        {
          v68 = (OLECHAR *)v197[9 * v66 + 7];
          if ( v68 )
          {
            SysFreeString(v68);
            v67 = v113[0];
            v66 = v109;
          }
          v109 = ++v66;
        }
        while ( v66 < v67 );
        v65 = (int)v111;
      }
      if ( v65 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA55,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
          (const char *)(unsigned int)v65,
          v103);
    }
  }
  v104 = (int)v133;
  v69 = (*(__int64 (__fastcall **)(struct ICiCQuerySession *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v114 + 24LL))(
          v114,
          *((unsigned int *)v115 + 4),
          *((_QWORD *)v115 + 1),
          *((_QWORD *)v62 + 35));
  if ( v69 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v69,
      v104);
  v121 = v62;
  v142[0] = v131;
  v151 = v123;
  LODWORD(v111) = v57;
  CRestrictionParser::CRestrictionParser(
    (CRestrictionParser *)v197,
    v115,
    v112,
    v114,
    v146,
    v130,
    (unsigned int)v180,
    (struct UserSID *)&ReturnLength,
    *v122,
    *((_DWORD *)v62 + 23) == 1,
    *(_BYTE *)(*(_QWORD *)v118 + 384LL),
    *((const wchar_t **)v62 + 41),
    *((const wchar_t **)v62 + 53),
    *(_WORD *)(*(_QWORD *)v118 + 386LL),
    *(struct IFTEPluginLocator **)(*(_QWORD *)v118 + 192LL));
  v70 = CRestrictionParser::Parse(v197, &v168, v168);
  std::shared_ptr<inverted::ICatalogStorage>::operator=(v145, v70);
  if ( v169 )
    std::_Ref_count_base::_Decref(v169);
  CRestrictionParser::~CRestrictionParser((CRestrictionParser *)v197);
  if ( *(_BYTE *)(*(_QWORD *)v118 + 384LL) && v145[0] )
    ConvertOperatorToCatalogWIDs(v145[0]);
  if ( !v42 )
    goto LABEL_85;
  v71 = 0;
  if ( !*((_DWORD *)v42 + 4) )
    goto LABEL_85;
  while ( 1 )
  {
    v72 = CDynArray<CInGroupSortAggregSet>::Get(v42, v71);
    if ( !*(_DWORD *)v72 )
      break;
    v71 = (unsigned int)(v71 + 1);
    if ( (unsigned int)v71 >= *((_DWORD *)v42 + 4) )
      goto LABEL_85;
  }
  v79 = *(const struct CSortSet **)(v72 + 16);
  if ( v79 )
  {
    v168 = (struct CRestriction *)operator new(0x10u);
    v73 = CSortSet::CSortSet(v168, v79);
  }
  else
  {
LABEL_85:
    v73 = 0;
  }
  *(_QWORD *)v113 = v73;
  if ( SearchIndexerTraceProvider::IsEnabled(4u, v71) )
    CRequestServer::NoCheckRetailTraceQuery(
      (int)v62,
      *v123,
      v74,
      v16,
      (__int64)&v164,
      (__int64)v73,
      (__int64)&v180,
      v115,
      v108,
      (__int64)v112,
      (__int64)v119);
  v112 = 0;
  CreateScopeInfo((struct IUnknown *)v114);
  if ( byte_180367DD0 )
  {
    v170 = 0;
    v171 = 0;
    (*(void (__fastcall **)(struct CColumnGroupArray *, __int128 *))(*(_QWORD *)v112 + 104LL))(v112, &v170);
    for ( i = 0; i < (unsigned __int64)((__int64)(*((_QWORD *)&v170 + 1) - v170) >> 5); ++i )
    {
      std::wstring::wstring(v189, v170 + 32LL * i);
      std::wstring::wstring(v179, v76);
      v77 = v189;
      if ( v189[3] > 7u )
        v77 = (_QWORD *)v189[0];
      GetProtocolHelper(v77, v179);
      LODWORD(v168) = 2;
      v78 = (std::_Ref_count_base *)v179;
      if ( v179[3] > 7u )
        v78 = (std::_Ref_count_base *)v179[0];
      v169 = v78;
      (*(void (__fastcall **)(__int64, struct CRestriction **))(*(_QWORD *)v138 + 24LL))(v138, &v168);
      std::wstring::_Tidy_deallocate(v179);
      std::wstring::_Tidy_deallocate(v189);
    }
    std::vector<std::wstring>::_Tidy(&v170);
  }
  v80 = (__int64 *)v122;
  v136 = operator new(0x168u);
  v81 = CQueryOptimizer::CQueryOptimizer(
          (_DWORD)v136,
          (unsigned int)&v114,
          *v80,
          (unsigned int)v145,
          (__int64)v105,
          (__int64)v106,
          (__int64)v43,
          (__int64)&v180,
          (__int64)&v141,
          (__int64)&v186,
          (__int64)v149);
  v168 = (struct CRestriction *)v81;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) )
  {
    if ( v124 )
      *(_OWORD *)(v81 + 296) = *(_OWORD *)v124;
    if ( v125 )
      *(_OWORD *)(v81 + 312) = *(_OWORD *)v125;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60977300>::GetImpl'::`2'::impl)
    && v117 )
  {
    std::wstring::operator=(v81 + 328, v117);
  }
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
    (const wchar_t *)0xAE1,
    (unsigned int)L"[Proxy] Rowset props flags: 0x%x\n",
    (const wchar_t *)(unsigned int)v180);
  v82 = (const wchar_t *)v181;
  if ( (char)v180 < 0 )
    v82 = 0;
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
    (const wchar_t *)0xAE2,
    (unsigned int)L"[Proxy] Rowset props maxresults: %d\n",
    v82);
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
    (const wchar_t *)0xAE3,
    (unsigned int)L"[Proxy] Rowset props cmdtimeout: %d\n",
    (const wchar_t *)v182);
  v83 = v121;
  v84 = (char *)v121 + 648;
  *((_DWORD *)v121 + 161) = 1;
  *((_QWORD *)v83 + 79) = v62;
  SearchIndexerTraceProvider::IsEnabled(4u, v85);
  if ( ((unsigned int)v180 & 0x80000) != 0 )
  {
    v86 = (char *)operator new(0x820u);
    v136 = v86;
    *((_QWORD *)v86 + 1) = v86 + 24;
    *((_QWORD *)v86 + 2) = 1025;
    *((_WORD *)v86 + 12) = 0;
    *(_QWORD *)v86 = &TLMString<1024,512,1048576>::`vftable';
    *((_QWORD *)v62 + 39) = v86;
  }
  v87 = v123;
  VIQuery = CreateVIQuery(
              (unsigned int)&v168,
              (unsigned int)&v116,
              (unsigned int)v129,
              (unsigned int)&v128,
              (__int64)&v134,
              *v80,
              v57,
              (__int64)v84,
              *v123,
              (__int64)&ReturnLength,
              *(_BYTE *)(*(_QWORD *)v118 + 384LL),
              v119[1],
              (__int64)v112);
  v89 = v131;
  *v131 = VIQuery;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) )
  {
    if ( v124 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v89 + 328LL))(*v89);
    if ( v125 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v89 + 344LL))(*v89);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60977300>::GetImpl'::`2'::impl)
    && v117 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)*v89 + 392LL))(*v89);
  }
  *((_DWORD *)v121 + 160) = 0;
  v156 = 2;
  SearchIndexerTelemetryAggregatedMedium::IndexerQueryExecutionService::Stop((SearchIndexerTelemetryAggregatedMedium::IndexerQueryExecutionService *)v157);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 16LL))(v138);
  wil::ActivityBase<SearchIndexerDiagnosticsLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v196);
  *v140 = 4 * (_DWORD)v111 + 24;
  if ( (byte_180368442 & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      MSSearchTraceId_ServerQuery_Start,
      (unsigned int)*v87);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v195);
  XPtr<CQueryOptimizer>::~XPtr<CQueryOptimizer>(&v168);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v112);
  if ( v73 )
    CSortSet::`scalar deleting destructor'(v73, v90);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v137);
  if ( v145[1] )
    std::_Ref_count_base::_Decref(v145[1]);
  operator delete(Block);
  if ( v139 )
    std::_Ref_count_base::_Decref(v139);
  SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionService::~IndexerQueryExecutionService((SearchIndexerDiagnosticTelemetry::IndexerQueryExecutionService *)v196);
  SearchIndexerTelemetryAggregatedMedium::IndexerQueryExecutionService::~IndexerQueryExecutionService((SearchIndexerTelemetryAggregatedMedium::IndexerQueryExecutionService *)v157);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v114);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v132);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v133);
  CFullPropSpec::~CFullPropSpec((CFullPropSpec *)v177);
  XInterface<CPidRemapper>::~XInterface<CPidRemapper>(&v134);
  CPidConverter::~CPidConverter((CPidConverter *)v154);
  CTKPLiteHashMapContainer<TLMString<32,32,1024>,CWordTableEntry>::~CTKPLiteHashMapContainer<TLMString<32,32,1024>,CWordTableEntry>(v149);
  if ( v187 != v188 )
  {
    operator delete(v187);
    v187 = v188;
    v186 = 16;
  }
  TCountedGrowableArrayOfPointer<CRestriction,16>::~TCountedGrowableArrayOfPointer<CRestriction,16>(v167);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v126);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v135);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v127);
  PerUserCatalogNameForCorruption::SetCatalog(0);
  XPtr<CColumnGroupArray>::~XPtr<CColumnGroupArray>(&v141);
  XPtr<CPidMapper>::~XPtr<CPidMapper>(&v115);
  std::wstring::_Tidy_deallocate(v185);
  XPtr<CCategorizationSet>::~XPtr<CCategorizationSet>(&v128);
  XPtr<CSortSets>::~XPtr<CSortSets>(v129);
  TCountedGrowableArrayOfPointer<CRestriction,16>::~TCountedGrowableArrayOfPointer<CRestriction,16>(&v164);
  XPtr<CColumnSet>::~XPtr<CColumnSet>(&v116);
  operator delete(v120);
  CPerfCounterSmartClass::~CPerfCounterSmartClass((CPerfCounterSmartClass *)&v155);
  SearchIndexerTelemetry::HandleCreateQueryActivity::~HandleCreateQueryActivity((SearchIndexerTelemetry::HandleCreateQueryActivity *)v195);
  return 0;
}

```

## disassembly

```asm
0x180114060  push    rbx
0x180114062  push    rsi
0x180114063  push    rdi
0x180114064  push    r12
0x180114066  push    r13
0x180114068  push    r14
0x18011406a  push    r15
0x18011406c  mov     eax, 1040h
0x180114071  call    _alloca_probe
0x180114076  sub     rsp, rax
0x180114079  mov     rax, cs:__security_cookie
0x180114080  xor     rax, rsp
0x180114083  mov     [rsp+1078h+var_40], rax
0x18011408b  mov     ebx, r9d
0x18011408e  mov     rax, r8
0x180114091  mov     [rsp+1078h+var_F00], rax
0x180114099  mov     esi, edx
0x18011409b  mov     r14, rcx
0x18011409e  mov     [rsp+1078h+var_FA0], rcx
0x1801140a6  mov     [rsp+1078h+var_F58], rcx
0x1801140ae  mov     [rsp+1078h+var_F20], rax
0x1801140b6  test    cs:byte_180368442, 10h
0x1801140bd  jz      short loc_1801140D9
0x1801140bf  mov     r8d, [rcx+100h]
0x1801140c6  lea     rdx, MSSearchTraceId_ServerQuery_Create
0x1801140cd  lea     rcx, Microsoft_Windows_Search_Core_Context
0x1801140d4  call    McTemplateU0q_EventWriteTransfer
0x1801140d9  mov     eax, [r14+70h]
0x1801140dd  mov     r15d, 1
0x1801140e3  and     eax, r15d
0x1801140e6  xor     r13d, r13d
0x1801140e9  test    al, al
0x1801140eb  jz      loc_180115859
0x1801140f1  lea     rdi, [r14+68h]
0x1801140f5  mov     [rsp+1078h+var_F98], rdi
0x1801140fd  cmp     [rdi], r13
0x180114100  jz      loc_180115832
0x180114106  lea     rax, [r14+80h]
0x18011410d  mov     [rsp+1078h+var_F48], rax
0x180114115  cmp     [rax], r13
0x180114118  jnz     loc_180115832
0x18011411e  lea     rdx, aHandlecreatequ; "HandleCreateQueryActivity"
0x180114125  lea     rcx, [rsp+1078h+var_B08]; struct wil::details::IFailureCallback *
0x18011412d  call    ??0?$ActivityBase@VSearchIndexerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180114132  lea     r12, ??_7HandleCreateQueryActivity@SearchIndexerTelemetry@@6B@; const SearchIndexerTelemetry::HandleCreateQueryActivity::`vftable'
0x180114139  mov     [rsp+1078h+var_B08], r12
0x180114141  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59422362@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362> `wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl(void)'::`2'::impl
0x180114148  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(void)
0x18011414d  test    al, al
0x18011414f  jz      short loc_18011419C
0x180114151  lea     rdx, aHandlecreatequ; "HandleCreateQueryActivity"
0x180114158  lea     rcx, [rsp+1078h+var_868]; struct wil::details::IFailureCallback *
0x180114160  call    ??0?$ActivityBase@VSearchIndexerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180114165  mov     [rsp+1078h+var_868], r12
0x18011416d  lea     rcx, [rsp+1078h+var_868]; this
0x180114175  call    ?StartActivity@HandleCreateQueryActivity@SearchIndexerTelemetry@@QEAAXXZ; SearchIndexerTelemetry::HandleCreateQueryActivity::StartActivity(void)
0x18011417a  lea     rdx, [rsp+1078h+var_868]
0x180114182  lea     rcx, [rsp+1078h+var_B08]
0x18011418a  call    ??4HandleCreateQueryActivity@SearchIndexerTelemetry@@QEAAAEAV01@$$QEAV01@@Z; SearchIndexerTelemetry::HandleCreateQueryActivity::operator=(SearchIndexerTelemetry::HandleCreateQueryActivity &&)
0x18011418f  lea     rcx, [rsp+1078h+var_868]; this
0x180114197  call    ??1HandleCreateQueryActivity@SearchIndexerTelemetry@@QEAA@XZ; SearchIndexerTelemetry::HandleCreateQueryActivity::~HandleCreateQueryActivity(void)
0x18011419c  test    ebx, ebx
0x18011419e  jz      short loc_1801141DD
0x1801141a0  mov     [rsp+1078h+var_FF4], r13d
0x1801141a8  mov     rcx, [rdi]
0x1801141ab  mov     rax, [rcx]
0x1801141ae  lea     rdx, [rsp+1078h+var_FF4]
0x1801141b6  mov     rax, [rax+50h]
0x1801141ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801141bf  mov     rcx, [rsp+1078h]; this
0x1801141c7  test    eax, eax
0x1801141c9  js      loc_180115880
0x1801141cf  cmp     [rsp+1078h+var_FF4], r13d
0x1801141d7  jnz     loc_180115895
0x1801141dd  lea     rbx, [r14+78h]
0x1801141e1  cmp     [rbx], r13
0x1801141e4  jnz     short loc_18011424F
0x1801141e6  mov     [rsp+1078h+var_FC8], r13
0x1801141ee  mov     rcx, [rdi]
0x1801141f1  mov     rax, [rcx]
0x1801141f4  lea     rdx, [rsp+1078h+var_FC8]
0x1801141fc  mov     rax, [rax+20h]
0x180114200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114205  mov     rcx, [rsp+1078h]; this
0x18011420d  test    eax, eax
0x18011420f  js      loc_1801158BC
0x180114215  mov     rcx, [rsp+1078h+var_FC8]
0x18011421d  mov     rax, [rcx]
0x180114220  mov     r8, rbx
0x180114223  lea     rdx, _GUID_8e4225c5_886c_4a40_914f_01765e175def
0x18011422a  mov     rax, [rax]
0x18011422d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114232  mov     rcx, [rsp+1078h]; this
0x18011423a  test    eax, eax
0x18011423c  js      loc_1801158D1
0x180114242  lea     rcx, [rsp+1078h+var_FC8]; void *
0x18011424a  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x18011424f  mov     rcx, [rbx]
0x180114252  mov     rax, [rcx]
0x180114255  mov     edx, 1Eh
0x18011425a  mov     rax, [rax+30h]
0x18011425e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114263  mov     rcx, [rbx]
0x180114266  mov     [rsp+1078h+var_E68], rcx
0x18011426e  mov     [rsp+1078h+var_E60], r13d
0x180114276  mov     rax, [rcx]
0x180114279  mov     r12d, 20h ; ' '
0x18011427f  mov     edx, r12d
0x180114282  mov     rax, [rax+30h]
0x180114286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011428b  nop
0x18011428c  mov     rcx, [r14+0B0h]
0x180114293  mov     [rsp+1078h+var_FA8], rcx
0x18011429b  test    rcx, rcx
0x18011429e  lea     rbx, [r14+270h]
0x1801142a5  jz      short loc_1801142AA
0x1801142a7  mov     rbx, rcx
0x1801142aa  mov     eax, [r14+0B8h]
0x1801142b1  mov     [rsp+1078h+var_E18], eax
0x1801142b8  mov     [r14+0B0h], r13
0x1801142bf  mov     [r14+0B8h], r13d
0x1801142c6  mov     [rsp+1078h+var_E20], rcx
0x1801142ce  mov     [rsp+1078h+var_FC8], r13
0x1801142d6  lea     rcx, [rsp+1078h+var_E08]
0x1801142de  call    ??0?$TCountedGrowableArrayOfPointer@VCRestriction@@$0BA@@@QEAA@XZ; TCountedGrowableArrayOfPointer<CRestriction,16>::TCountedGrowableArrayOfPointer<CRestriction,16>(void)
0x1801142e3  nop
0x1801142e4  mov     [rsp+1078h+var_F60], r13
0x1801142ec  mov     [rsp+1078h+var_F68], r13
0x1801142f4  lea     rcx, [rsp+1078h+var_C28]; this
0x1801142fc  call    ??0CRowsetProperties@@QEAA@K@Z; CRowsetProperties::CRowsetProperties(ulong)
0x180114301  nop
0x180114302  mov     [rsp+1078h+var_FD0], r13
0x18011430a  mov     rcx, r12; Size
0x18011430d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180114312  mov     [rsp+1078h+var_F18], rax
0x18011431a  mov     rcx, rax; this
0x18011431d  call    ??0CColumnGroupArray@@QEAA@XZ; CColumnGroupArray::CColumnGroupArray(void)
0x180114322  mov     [rsp+1078h+var_FE8], rax
0x18011432a  mov     [rsp+1078h+var_EF8], rax
0x180114332  mov     [rsp+1078h+var_FB0], r13d
0x18011433a  lea     edx, [rsi-10h]
0x18011433d  lea     r8, [rbx+10h]
0x180114341  mov     ecx, [r14+58h]
0x180114345  btr     ecx, 10h; int
0x180114349  mov     dword ptr [rsp+1078h+var_1028], edx; int
0x18011434d  mov     qword ptr [rsp+1078h+var_1030], r8; __int64
0x180114352  lea     rdx, [rsp+1078h+var_FB0]
0x18011435a  mov     [rsp+1078h+var_1038], rdx; __int64
0x18011435f  mov     [rsp+1078h+var_1040], rax; CColumnGroupArray *
0x180114364  lea     rax, [rsp+1078h+var_FD0]
0x18011436c  mov     [rsp+1078h+var_1048], rax; __int64
0x180114371  lea     rax, [rsp+1078h+var_C28]
0x180114379  mov     [rsp+1078h+var_1050], rax; CRowsetProperties *
0x18011437e  lea     rax, [rsp+1078h+var_F68]
0x180114386  mov     [rsp+1078h+var_1058], rax; int
0x18011438b  lea     r9, [rsp+1078h+var_F60]
0x180114393  lea     r8, [rsp+1078h+var_E08]
0x18011439b  lea     rdx, [rsp+1078h+var_FC8]
0x1801143a3  call    ?UnPickle@@YAXHAEAV?$XPtr@VCColumnSet@@@@AEAV?$TCountedGrowableArrayOfPointer@VCRestriction@@$0BA@@@AEAV?$XPtr@VCSortSets@@@@AEAV?$XPtr@VCCategorizationSet@@@@AEAVCRowsetProperties@@AEAV?$XPtr@VCPidMapper@@@@AEAVCColumnGroupArray@@AEAKPEAEK@Z; UnPickle(int,XPtr<CColumnSet> &,TCountedGrowableArrayOfPointer<CRestriction,16> &,XPtr<CSortSets> &,XPtr<CCategorizationSet> &,CRowsetProperties &,XPtr<CPidMapper> &,CColumnGroupArray &,ulong &,uchar *,ulong)
0x1801143a8  cmp     [rsp+1078h+var_D78], r15d
0x1801143b0  ja      loc_1801158E6
0x1801143b6  mov     rdx, r13
0x1801143b9  mov     [rsp+1078h+var_CC8], rdx
0x1801143c1  jnz     short loc_1801143D6
0x1801143c3  mov     rax, [rsp+1078h+var_E00]
0x1801143cb  mov     rdx, [rax]; struct CRestriction *
0x1801143ce  mov     [rsp+1078h+var_CC8], rdx
0x1801143d6  mov     rsi, [rsp+1078h+var_FC8]
0x1801143de  test    rsi, rsi
0x1801143e1  setz    al
0x1801143e4  mov     rcx, [rsp+1078h]; this
0x1801143ec  test    al, al
0x1801143ee  jnz     loc_18011590D
0x1801143f4  mov     [rsp+1078h+var_FB0+4], 0FFFFFFFFh
0x1801143ff  lea     rax, [r14+108h]
0x180114406  mov     [rsp+1078h+var_FB8], rax
0x18011440e  mov     r8, [rax]
0x180114411  cmp     [r8+180h], r13b
0x180114418  jz      short loc_180114479
0x18011441a  mov     [rsp+1078h+var_FF0], r13
0x180114422  lea     rax, [rsp+1078h+var_FF0]
0x18011442a  mov     [rsp+1078h+var_1058], rax; int
0x18011442f  lea     r9, [rsp+1078h+var_FB0+4]; unsigned int *
0x180114437  movzx   r8d, word ptr [r8+182h]; wchar_t
0x18011443f  mov     rcx, r14; this
0x180114442  call    ?_FindReplacementVolumeCatalog@CRequestServer@@AEAAXPEAVCRestriction@@_WPEAKPEAPEAUICiCDocStore@@@Z; CRequestServer::_FindReplacementVolumeCatalog(CRestriction *,wchar_t,ulong *,ICiCDocStore * *)
0x180114447  cmp     [rsp+1078h+var_FF0], r13
0x18011444f  jz      short loc_18011446C
0x180114451  mov     rcx, rdi
0x180114454  call    ?Free@?$XInterface@UICiCDocStore@@@@QEAAXXZ; XInterface<ICiCDocStore>::Free(void)
0x180114459  mov     rax, [rsp+1078h+var_FF0]
0x180114461  mov     [rsp+1078h+var_FF0], r13
0x180114469  mov     [rdi], rax
0x18011446c  lea     rcx, [rsp+1078h+var_FF0]; void *
0x180114474  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x180114479  lea     rax, [r14+100h]
0x180114480  mov     [rsp+1078h+var_F90], rax
0x180114488  mov     eax, [rax]
0x18011448a  mov     rdi, [rsp+1078h+var_FD0]
0x180114492  mov     [rdi+40h], eax
0x180114495  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57994465@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465> `wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl(void)'::`2'::impl
0x18011449c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(void)
0x1801144a1  test    al, al
0x1801144a3  jz      short loc_1801144BF
0x1801144a5  lea     r12, [rsp+1078h+var_C18+4]
0x1801144ad  mov     [rsp+1078h+var_F88], r12
0x1801144b5  lea     rbx, [rsp+1078h+var_C04]
0x1801144bd  jmp     short loc_1801144CA
0x1801144bf  mov     [rsp+1078h+var_F88], r13
0x1801144c7  mov     rbx, r13
0x1801144ca  mov     [rsp+1078h+var_F80], rbx
0x1801144d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60977300@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60977300@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300> `wil::Feature<__WilFeatureTraits_Feature_60977300>::GetImpl(void)'::`2'::impl
0x1801144d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60977300@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60977300>::__private_IsEnabled(void)
0x1801144de  lea     rcx, [rsp+1078h+var_BF0]
0x1801144e6  test    al, al
0x1801144e8  cmovz   rcx, r13
0x1801144ec  mov     [rsp+1078h+var_FC0], rcx
0x1801144f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59422362@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362> `wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl(void)'::`2'::impl
0x1801144fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(void)
0x180114500  test    al, al
0x180114502  jz      short loc_180114514
0x180114504  mov     rdx, rbx
0x180114507  lea     rcx, [rsp+1078h+var_B08]
0x18011450f  call    ??$HandleCreateQueryCorrID@AEBU_GUID@@@HandleCreateQueryActivity@SearchIndexerTelemetry@@QEAAXAEBU_GUID@@@Z; SearchIndexerTelemetry::HandleCreateQueryActivity::HandleCreateQueryCorrID<_GUID const &>(_GUID const &)
0x180114514  xor     r9d, r9d; Context
0x180114517  xor     r8d, r8d; Parameter
0x18011451a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180114521  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180114528  call    cs:__imp_InitOnceExecuteOnce
0x18011452e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r13b; bool g_isPerUserCatalogEnabled
0x180114535  jz      short loc_180114540
0x180114537  mov     rcx, [r14+148h]
0x18011453e  jmp     short loc_180114543
0x180114540  mov     rcx, r13; lpTlsValue
0x180114543  call    PerUserCatalogNameForCorruption__SetCatalog
0x180114548  nop
0x180114549  xor     r9d, r9d; Context
0x18011454c  xor     r8d, r8d; Parameter
0x18011454f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180114556  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18011455d  call    cs:__imp_InitOnceExecuteOnce
0x180114563  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r13b; bool g_isPerUserCatalogEnabled
0x18011456a  jz      short loc_1801145A2
0x18011456c  mov     edx, r13d
0x18011456f  cmp     [rdi+10h], r13d
0x180114573  jbe     short loc_1801145A2
0x180114575  mov     r8, cs:qword_1802F69C0
0x18011457c  mov     r9, cs:qword_1802F69B8
0x180114583  mov     rcx, rdi
0x180114586  call    ?Get@?$CDynArray@VCInGroupSortAggregSet@@@@QEBAPEAVCInGroupSortAggregSet@@I@Z; CDynArray<CInGroupSortAggregSet>::Get(uint)
0x18011458b  cmp     [rax], r9
0x18011458e  jnz     short loc_18011459A
0x180114590  cmp     [rax+8], r8
0x180114594  jz      loc_180114621
0x18011459a  add     edx, r15d
0x18011459d  cmp     edx, [rdi+10h]
0x1801145a0  jb      short loc_180114583
0x1801145a2  mov     r12d, r15d
0x1801145a5  mov     [rsp+1078h+var_FF4], r15d
0x1801145ad  mov     rbx, [rsp+1078h+var_F68]
0x1801145b5  test    rbx, rbx
0x1801145b8  jz      short loc_1801145C8
0x1801145ba  mov     r12d, [rbx]
0x1801145bd  add     r12d, r15d
0x1801145c0  mov     [rsp+1078h+var_FF4], r12d
0x1801145c8  lea     rcx, [r14+230h]
0x1801145cf  mov     edx, r12d
0x1801145d2  call    ?SetExactSize@?$CDynArrayInPlace@K@@QEAAXI@Z; CDynArrayInPlace<ulong>::SetExactSize(uint)
0x1801145d7  lea     rcx, [r14+240h]
0x1801145de  mov     edx, r12d
0x1801145e1  call    ?SetExactSize@?$CDynArrayInPlace@K@@QEAAXI@Z; CDynArrayInPlace<ulong>::SetExactSize(uint)
0x1801145e6  lea     rcx, [r14+250h]
0x1801145ed  lea     edx, [r12+1]
0x1801145f2  call    ?SetExactSize@?$CDynArray@VCTableColumnSet@@@@QEAAXI@Z; CDynArray<CTableColumnSet>::SetExactSize(uint)
0x1801145f7  lea     rcx, [r14+260h]
0x1801145fe  lea     edx, [r12+1]
0x180114603  call    ?SetExactSize@?$CDynArray@VCTableColumnSet@@@@QEAAXI@Z; CDynArray<CTableColumnSet>::SetExactSize(uint)
0x180114608  mov     eax, r12d
0x18011460b  lea     rax, ds:18h[rax*4]
0x180114613  cmp     rax, 1300h
0x180114619  ja      loc_180115925
0x18011461f  jmp     short loc_18011463E
0x180114621  mov     rcx, r14; this
0x180114624  call    ?SwitchToSystemCatalog@CRequestServer@@AEAAJXZ; CRequestServer::SwitchToSystemCatalog(void)
0x180114629  mov     rcx, [rsp+1078h]; this
0x180114631  test    eax, eax
0x180114633  js      loc_18011594C
0x180114639  jmp     loc_1801145A2
0x18011463e  mov     r12, [rsp+1078h+var_F98]
0x180114646  mov     [rsp+1078h+var_E80], r12
0x18011464e  mov     [rsp+1078h+var_F70], r13
0x180114656  mov     rcx, [r12]
0x18011465a  mov     rax, [rcx]
0x18011465d  lea     rdx, [rsp+1078h+var_F70]
0x180114665  mov     rax, [rax+20h]
0x180114669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011466e  mov     rcx, [rsp+1078h]; this
0x180114676  test    eax, eax
0x180114678  js      loc_180115961
0x18011467e  mov     [rsp+1078h+var_F28], r13
  ... truncated ...
```
