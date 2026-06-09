# Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl(tagDIAGTRACK_SCENARIO_INFORMATION,__MIDL_UtcApiStructures_0001,wchar_t const *,int,int,__MIDL_UtcApiStructures_0004,ulong,wchar_t const * *,wchar_t const * *,std::function<void (long,_GUID,_GUID)> const &,ulong *,_GUID *)

- ea: `0x1801f9dc4`
- end: `0x1801fbff2`
- name: `?EscalateScenarioImpl@UtcApiManager@Diagnostics@Microsoft@@AEAAJUtagDIAGTRACK_SCENARIO_INFORMATION@@W4__MIDL_UtcApiStructures_0001@@PEB_WHHW4__MIDL_UtcApiStructures_0004@@KPEAPEB_W4AEBV?$function@$$A6AXJU_GUID@@0@Z@std@@PEAKPEAU_GUID@@@Z`
- size: `8750`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, unsigned int, const WCHAR *, int, int, unsigned int, unsigned int, __int64, __int64, __int64, _DWORD *, GUID *)`
- caller_count: `4`
- callee_count: `70`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f3070`
- `0x1801f9cc0`
- `0x180288ff0`
- `0x18028ad30`

## callees

- `0x180002a28`
- `0x180006ed8`
- `0x1800074f4`
- `0x18001b3f8`
- `0x1800249a0`
- `0x18002afd8`
- `0x18002b770`
- `0x18002b9c0`
- `0x18002ba00`
- `0x18002cb04`
- `0x18002df00`
- `0x180030174`
- `0x180038034`
- `0x180049d00`
- `0x18004b6ac`
- `0x18004ffa4`
- `0x180052240`
- `0x18005ea74`
- `0x180064e8c`
- `0x18006a814`
- `0x18007b274`
- `0x180081278`
- `0x18008a4ec`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008ab10`
- `0x18008abf4`
- `0x18008bce0`
- `0x180096888`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800b47f0`
- `0x1800b6204`
- `0x1800bc658`
- `0x1800bfdf8`
- `0x1800c2588`
- `0x1800cf7d8`
- `0x1800faa3c`
- `0x180105618`
- `0x18010af6c`
- `0x18010c974`
- `0x1801245e0`
- `0x180124720`
- `0x180135dac`
- `0x18013b624`
- `0x180142fcc`
- `0x1801639c8`
- `0x1801652d4`
- `0x180166420`
- `0x180166500`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801fa27c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801fa27c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801fa9a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801fa9a7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801fa893`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801fa893`

## string_xrefs

- `0x1801f9f8a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa03d`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa101`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa1c5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa29a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa37e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa43c`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa4f2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa6f1`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa7b6`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fa8ae`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801faab2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fade0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbbd5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbc0e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbdfa`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbe8b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbf1e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbf59`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fbf94`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801fac0a`: `ScenarioApiCompleted_0`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        const WCHAR *a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        _DWORD *a12,
        GUID *a13)
{
  _DWORD *v15; // rdx
  GUID *v16; // rcx
  int v17; // ecx
  __int64 v18; // r9
  char v19; // r15
  int RpcImpersonationToken; // eax
  unsigned int v21; // ebx
  __int64 v23; // rcx
  unsigned int i; // ebx
  _QWORD *v25; // rcx
  WCHAR *v26; // rcx
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  Microsoft::Diagnostics::ScenarioManager *v28; // rax
  int ScenarioById; // eax
  unsigned int v30; // ebx
  std::_Ref_count_base *v31; // r14
  int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r8
  HRESULT v36; // eax
  __int64 v37; // rax
  std::_Ref_count_base *v38; // rdi
  __int64 *v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rcx
  char v42; // di
  __int64 v43; // rdx
  __int64 v44; // rax
  char v45; // bl
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // r8
  __int64 v50; // r8
  _QWORD *v51; // rax
  __int128 v52; // xmm6
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // r8
  _QWORD *v56; // rax
  int v57; // eax
  const char *v58; // r9
  __int64 v59; // rdx
  struct Microsoft::Diagnostics::MetadataEngine *MetadataEngine; // rax
  _QWORD *v61; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v62; // rax
  _QWORD *v63; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v64; // rax
  _QWORD *v65; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v66; // rax
  _QWORD *v67; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v68; // rax
  _QWORD *v69; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v70; // rax
  _QWORD *v71; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v72; // rax
  _QWORD *v73; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v74; // rax
  _QWORD *v75; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v76; // rax
  _QWORD *v77; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v78; // rax
  _QWORD *v79; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v80; // rax
  _QWORD *v81; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v82; // rax
  _QWORD *v83; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v84; // rax
  _QWORD *v85; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v86; // rax
  _QWORD *v87; // rax
  _QWORD *v88; // rax
  _QWORD *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // r8
  struct Microsoft::Diagnostics::ScenarioCounterStorage *v92; // rbx
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // r8
  __int64 v101; // rbx
  _QWORD *v102; // rax
  __int64 v103; // rbx
  int v104; // ecx
  int v105; // r8d
  int v106; // r9d
  __int64 v107; // rdx
  __int64 v108; // rdx
  int v109; // eax
  struct Microsoft::Diagnostics::EscalationEngine *EscalationEngine; // rbx
  __int64 v111; // rax
  __int64 v112; // r12
  __int64 v113; // r9
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // r8
  _QWORD *v117; // rax
  __int128 v118; // xmm6
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // r8
  _QWORD *v122; // rax
  int v123; // eax
  unsigned int v124; // ebx
  unsigned int v125; // ebx
  unsigned int v126; // ebx
  unsigned int v127; // [rsp+20h] [rbp-C48h]
  int v128; // [rsp+20h] [rbp-C48h]
  int v129; // [rsp+20h] [rbp-C48h]
  bool v130; // [rsp+140h] [rbp-B28h] BYREF
  _BYTE v131[3]; // [rsp+141h] [rbp-B27h] BYREF
  _DWORD v132[3]; // [rsp+144h] [rbp-B24h] BYREF
  __int128 v133; // [rsp+150h] [rbp-B18h] BYREF
  struct _GUID *v134; // [rsp+160h] [rbp-B08h] BYREF
  char v135; // [rsp+168h] [rbp-B00h]
  _BYTE v136[4]; // [rsp+170h] [rbp-AF8h] BYREF
  _WORD v137[6]; // [rsp+174h] [rbp-AF4h] BYREF
  std::_Ref_count_base *v138[2]; // [rsp+180h] [rbp-AE8h] BYREF
  unsigned int v139; // [rsp+190h] [rbp-AD8h] BYREF
  __int64 v140; // [rsp+198h] [rbp-AD0h] BYREF
  __int64 v141; // [rsp+1A0h] [rbp-AC8h]
  _DWORD *v142; // [rsp+1A8h] [rbp-AC0h] BYREF
  int v143; // [rsp+1B0h] [rbp-AB8h]
  int CurrentScenarioEscalationsByType; // [rsp+1B4h] [rbp-AB4h] BYREF
  int v145; // [rsp+1B8h] [rbp-AB0h] BYREF
  _BYTE v146[16]; // [rsp+1C0h] [rbp-AA8h] BYREF
  std::_Ref_count_base *v147[2]; // [rsp+1D0h] [rbp-A98h] BYREF
  std::_Ref_count_base *v148[2]; // [rsp+1E0h] [rbp-A88h] BYREF
  unsigned int v149[2]; // [rsp+1F0h] [rbp-A78h] BYREF
  GUID *v150; // [rsp+1F8h] [rbp-A70h] BYREF
  __int64 v151; // [rsp+200h] [rbp-A68h]
  int v152; // [rsp+208h] [rbp-A60h] BYREF
  int v153; // [rsp+20Ch] [rbp-A5Ch] BYREF
  int CurrentScenarioReportsByType; // [rsp+210h] [rbp-A58h] BYREF
  __int64 v155; // [rsp+218h] [rbp-A50h] BYREF
  struct Microsoft::Diagnostics::ScenarioCounterStorage *ScenarioCounterStorage; // [rsp+220h] [rbp-A48h] BYREF
  char *v157; // [rsp+228h] [rbp-A40h] BYREF
  __int64 v158; // [rsp+230h] [rbp-A38h] BYREF
  int v159; // [rsp+238h] [rbp-A30h]
  __int64 v160; // [rsp+240h] [rbp-A28h]
  _QWORD *v161; // [rsp+248h] [rbp-A20h] BYREF
  _QWORD v162[3]; // [rsp+250h] [rbp-A18h] BYREF
  _QWORD *v163; // [rsp+268h] [rbp-A00h] BYREF
  _QWORD *v164; // [rsp+270h] [rbp-9F8h] BYREF
  _QWORD *v165; // [rsp+278h] [rbp-9F0h] BYREF
  _QWORD *v166; // [rsp+280h] [rbp-9E8h] BYREF
  const wchar_t *v167; // [rsp+288h] [rbp-9E0h] BYREF
  _QWORD *v168; // [rsp+290h] [rbp-9D8h] BYREF
  _QWORD *v169; // [rsp+298h] [rbp-9D0h] BYREF
  _QWORD *v170; // [rsp+2A0h] [rbp-9C8h] BYREF
  _QWORD *v171; // [rsp+2A8h] [rbp-9C0h] BYREF
  _QWORD *v172; // [rsp+2B0h] [rbp-9B8h] BYREF
  _QWORD *v173; // [rsp+2B8h] [rbp-9B0h] BYREF
  _BYTE v174[8]; // [rsp+2C0h] [rbp-9A8h] BYREF
  std::_Ref_count_base *v175; // [rsp+2C8h] [rbp-9A0h]
  unsigned int *v176; // [rsp+2D0h] [rbp-998h] BYREF
  int v177; // [rsp+2D8h] [rbp-990h]
  _QWORD *v178; // [rsp+2E0h] [rbp-988h] BYREF
  _QWORD *v179; // [rsp+2E8h] [rbp-980h] BYREF
  _BYTE v180[16]; // [rsp+2F0h] [rbp-978h] BYREF
  _QWORD *v181; // [rsp+300h] [rbp-968h] BYREF
  __int64 v182; // [rsp+308h] [rbp-960h] BYREF
  int v183; // [rsp+310h] [rbp-958h]
  _BYTE v184[16]; // [rsp+318h] [rbp-950h] BYREF
  _BYTE v185[16]; // [rsp+328h] [rbp-940h] BYREF
  _BYTE v186[16]; // [rsp+338h] [rbp-930h] BYREF
  _BYTE v187[16]; // [rsp+348h] [rbp-920h] BYREF
  _BYTE v188[16]; // [rsp+358h] [rbp-910h] BYREF
  _BYTE v189[16]; // [rsp+368h] [rbp-900h] BYREF
  _BYTE v190[16]; // [rsp+378h] [rbp-8F0h] BYREF
  _BYTE v191[16]; // [rsp+388h] [rbp-8E0h] BYREF
  _OWORD v192[2]; // [rsp+398h] [rbp-8D0h] BYREF
  __int128 v193; // [rsp+3B8h] [rbp-8B0h] BYREF
  __m128i si128; // [rsp+3C8h] [rbp-8A0h]
  _QWORD v195[2]; // [rsp+3D8h] [rbp-890h] BYREF
  __int64 v196; // [rsp+3E8h] [rbp-880h]
  unsigned __int64 v197; // [rsp+3F0h] [rbp-878h]
  PWSTR pszPathOut[4]; // [rsp+3F8h] [rbp-870h] BYREF
  __int128 v199; // [rsp+418h] [rbp-850h] BYREF
  __int64 v200; // [rsp+428h] [rbp-840h]
  _BYTE v201[4]; // [rsp+438h] [rbp-830h] BYREF
  int v202; // [rsp+43Ch] [rbp-82Ch]
  _BYTE v203[4]; // [rsp+440h] [rbp-828h] BYREF
  GUID Buf1; // [rsp+444h] [rbp-824h] BYREF
  _BYTE v205[32]; // [rsp+458h] [rbp-810h] BYREF
  _BYTE v206[32]; // [rsp+478h] [rbp-7F0h] BYREF
  _BYTE v207[72]; // [rsp+498h] [rbp-7D0h] BYREF
  _BYTE v208[8]; // [rsp+4E0h] [rbp-788h] BYREF
  _BYTE v209[64]; // [rsp+4E8h] [rbp-780h] BYREF
  _BYTE v210[16]; // [rsp+528h] [rbp-740h] BYREF
  _BYTE v211[40]; // [rsp+538h] [rbp-730h] BYREF
  _BYTE v212[40]; // [rsp+560h] [rbp-708h] BYREF
  _BYTE v213[40]; // [rsp+588h] [rbp-6E0h] BYREF
  _BYTE v214[40]; // [rsp+5B0h] [rbp-6B8h] BYREF
  _BYTE v215[40]; // [rsp+5D8h] [rbp-690h] BYREF
  _BYTE v216[40]; // [rsp+600h] [rbp-668h] BYREF
  _BYTE v217[40]; // [rsp+628h] [rbp-640h] BYREF
  _BYTE v218[40]; // [rsp+650h] [rbp-618h] BYREF
  _BYTE v219[40]; // [rsp+678h] [rbp-5F0h] BYREF
  _BYTE v220[40]; // [rsp+6A0h] [rbp-5C8h] BYREF
  _BYTE v221[40]; // [rsp+6C8h] [rbp-5A0h] BYREF
  _BYTE v222[40]; // [rsp+6F0h] [rbp-578h] BYREF
  _BYTE v223[40]; // [rsp+718h] [rbp-550h] BYREF
  _BYTE v224[48]; // [rsp+740h] [rbp-528h] BYREF
  int v225[176]; // [rsp+770h] [rbp-4F8h] BYREF
  _BYTE v226[344]; // [rsp+A30h] [rbp-238h] BYREF
  _BYTE v227[80]; // [rsp+B88h] [rbp-E0h] BYREF
  int v228[14]; // [rsp+BD8h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C68h] [rbp+0h]

  v139 = a3;
  v155 = a1;
  CurrentScenarioEscalationsByType = a5;
  v145 = a6;
  v160 = a11;
  v15 = a12;
  v142 = a12;
  v16 = a13;
  v150 = a13;
  if ( (unsigned int)dword_1804543B0 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
    {
      v130 = *(_QWORD *)(v18 + 56) == 0;
      *(_QWORD *)v149 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
        v17,
        (unsigned int)byte_1803ECD95,
        a3,
        v18,
        (__int64)v149,
        (__int64)&v130);
      a3 = v139;
    }
    v15 = v142;
    v16 = v150;
  }
  v134 = a2;
  v19 = 1;
  v135 = 1;
  if ( !a4 || !a9 || !a10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v127);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2147942487LL;
  }
  if ( v15 )
    *v15 = 0;
  if ( v16 )
    *v16 = GUID_NULL;
  if ( a3 > 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v127);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2147942487LL;
  }
  if ( a7 > 2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v127);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2147942487LL;
  }
  *(_QWORD *)&v132[1] = 0;
  v192[0] = 0;
  v192[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v192[0]) = 0;
  RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(v16, &v132[1], v192);
  v21 = RpcImpersonationToken;
  if ( RpcImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)RpcImpersonationToken,
      v127);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return v21;
  }
  std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(&v140);
  for ( i = 0; i < a8; ++i )
  {
    if ( !*(_QWORD *)(a9 + 8LL * i) || !*(_QWORD *)(a10 + 8LL * i) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v127);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
      std::wstring::_Tidy_deallocate(v192);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
      v135 = 0;
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
      return 2147942487LL;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<wchar_t const * &,wchar_t const * &>(
      &v140,
      v138);
  }
  Microsoft::Diagnostics::UtcApiManager::ProcessApiMetaProperties(v23, v201, &v132[1], &v140);
  *(_QWORD *)v149 = v202;
  std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(v146, v155 + 224, v149);
  if ( !v146[8] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C5102BLL,
      v127);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2277838891LL;
  }
  std::wstring::wstring(v195, a4);
  v25 = v195;
  if ( v197 > 7 )
    v25 = (_QWORD *)v195[0];
  if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v25, v196, 0, 47) != -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v127);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2147942487LL;
  }
  std::wstring::wstring(pszPathOut, v196, 0);
  v26 = (WCHAR *)pszPathOut;
  if ( pszPathOut[3] > (PWSTR)7 )
    v26 = pszPathOut[0];
  if ( PathCchCanonicalizeEx(v26, (size_t)pszPathOut[2] + 1, a4, 1u) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v127);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2147942487LL;
  }
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_180463150, 0, 0) )
  {
    v126 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1FD,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
             (const char *)0x15,
             v127);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return v126;
  }
  if ( !_InterlockedCompareExchange64((_QWORD *)&xmmword_180463190 + 1, 0, 0) )
  {
    v125 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x203,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
             (const char *)0x15,
             v127);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return v125;
  }
  ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::ScenarioManager::GetScenarioState(ScenarioManager, v136, a2);
  if ( v136[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51005LL,
      v127);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2277838853LL;
  }
  *(_OWORD *)v148 = 0;
  v28 = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  ScenarioById = Microsoft::Diagnostics::ScenarioManager::TryGetScenarioById(v28, a2);
  v30 = ScenarioById;
  if ( ScenarioById < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)ScenarioById,
      v127);
    if ( v148[1] )
      std::_Ref_count_base::_Decref(v148[1]);
LABEL_39:
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return v30;
  }
  v31 = v148[0];
  if ( !v148[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51005LL,
      v127);
    if ( v148[1] )
      std::_Ref_count_base::_Decref(v148[1]);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2277838853LL;
  }
  v32 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v148[0] + 336LL))(v148[0]);
  v143 = v32;
  if ( *(_WORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _WORD *))(*(_QWORD *)v31 + 80LL))(v31, v137) == 1 )
  {
    if ( !(unsigned __int8)Microsoft::Diagnostics::ApiServer::IsRpcCallerUif(v33, &v132[1]) )
    {
      v132[0] = v32;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::GetImpl'::`2'::impl) )
        goto LABEL_62;
    }
    LOBYTE(v34) = 1;
    Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(&gs_lifetimeManager, v132, v34);
    if ( a7 )
    {
      if ( (v132[0] & 0x200) == 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)0x87C5101BLL,
          v127);
        if ( v148[1] )
          std::_Ref_count_base::_Decref(v148[1]);
        goto LABEL_55;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::GetImpl'::`2'::impl) )
      {
        v193 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v193) = 0;
        Microsoft::Diagnostics::Utils::Os::GetDeviceClass(&v193);
        v147[0] = (std::_Ref_count_base *)L"Windows.Desktop";
        v147[1] = (std::_Ref_count_base *)15;
        *(_OWORD *)v138 = *(_OWORD *)std::wstring::operator std::wstring_view(&v193, &v158, v35);
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v138, v147)
          && SLOBYTE(v132[0]) >= 0
          && !(unsigned __int8)Microsoft::Diagnostics::ApiServer::SoftIsAdminCheck(&v132[1]) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x87C5101BLL,
            v127);
          std::wstring::_Tidy_deallocate(&v193);
          if ( v148[1] )
            std::_Ref_count_base::_Decref(v148[1]);
LABEL_55:
          std::wstring::_Tidy_deallocate(pszPathOut);
          std::wstring::_Tidy_deallocate(v195);
          std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
          std::wstring::_Tidy_deallocate(v192);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
          v135 = 0;
          Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
          return 2277838875LL;
        }
        std::wstring::_Tidy_deallocate(&v193);
      }
    }
    v32 &= ~0x80u;
  }
  v132[0] = v32;
  v143 = v32;
LABEL_62:
  *(_OWORD *)v147 = 0;
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    v36 = CoCreateGuid(&Buf1);
    v30 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v36,
        v127);
      if ( v148[1] )
        std::_Ref_count_base::_Decref(v148[1]);
      goto LABEL_39;
    }
  }
  if ( v150 )
    *v150 = Buf1;
  v37 = std::make_shared<Microsoft::Diagnostics::ScenarioInst,std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> &,_GUID &>(
          v138,
          v148,
          &Buf1);
  std::shared_ptr<Concurrency::details::_Task_impl<std::shared_ptr<Microsoft::Diagnostics::HttpResponse>>>::operator=(
    v147,
    v37);
  if ( v138[1] )
    std::_Ref_count_base::_Decref(v138[1]);
  v38 = v147[0];
  GetSystemTimeAsFileTime((LPFILETIME)((char *)v147[0] + 36));
  *((_BYTE *)v38 + 72) = 1;
  v39 = (__int64 *)((char *)v38 + 80);
  if ( (__int64 *)((char *)v38 + 80) != &v140 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear((char *)v38 + 80);
    v40 = *v39;
    *v39 = v140;
    v140 = v40;
    v41 = *((_QWORD *)v38 + 11);
    *((_QWORD *)v38 + 11) = v141;
    v141 = v41;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)v38 + 96,
    &v132[1]);
  std::wstring::operator=((char *)v38 + 104, v192);
  v42 = 0;
  v130 = 0;
  (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD *))(*(_QWORD *)v31 + 264LL))(v31, v162);
  if ( v139 == 1 )
  {
    v42 = 1;
    v130 = 1;
    v44 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v31 + 272LL))(v31, &v193);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IActionDef const>>::operator=(v162, v44);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(&v193);
  }
  if ( v162[0] == v162[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51057LL,
      v127);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(v162);
    if ( v147[1] )
      std::_Ref_count_base::_Decref(v147[1]);
    if ( v148[1] )
      std::_Ref_count_base::_Decref(v148[1]);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v195);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
    std::wstring::_Tidy_deallocate(v192);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
    v135 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
    return 2277838935LL;
  }
  else
  {
    v45 = (v42 ^ 1) - 4;
    v131[0] = v45;
    if ( v142 )
    {
      LOBYTE(v43) = (v42 ^ 1) - 4;
      v46 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 224LL))(v31, v43);
      *v142 = v46 + 5000;
    }
    v47 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v31 + 72LL))(v31);
    LOBYTE(v48) = 1;
    Microsoft::Diagnostics::Utils::String::StringFromGuidW(v205, v47, v48);
    Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v205);
    v157 = (char *)v147[0] + 12;
    LOBYTE(v49) = 1;
    Microsoft::Diagnostics::Utils::String::StringFromGuidW(v206, (char *)v147[0] + 12, v49);
    Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v206);
    *(_QWORD *)&v133 = L"ScenarioApiCompleted_0";
    *((_QWORD *)&v133 + 1) = 22;
    Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
      (unsigned int)v225,
      (unsigned int)&v133,
      0x1000000,
      0,
      0,
      0);
    v51 = (_QWORD *)std::wstring::operator std::wstring_view(v206, v138, v50);
    std::wstring::_Assign<wchar_t>(v226, *v51, v51[1]);
    (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v31 + 88LL))(v31, v138);
    *(_QWORD *)&v133 = L"ScenarioName";
    *((_QWORD *)&v133 + 1) = 12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v225, (int)v228);
    *(_QWORD *)&v133 = L"ScenarioId";
    *((_QWORD *)&v133 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v225, v228, &v133, v205);
    v52 = *(_OWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v31 + 88LL))(v31, &v158);
    v53 = std::wstring::wstring(&v199, L"Scenario:");
    *(_OWORD *)v138 = v52;
    v54 = Microsoft::Diagnostics::operator+(&v193, v53, v138);
    v56 = (_QWORD *)std::wstring::operator std::wstring_view(v54, &v176, v55);
    std::wstring::_Assign<wchar_t>(v227, *v56, v56[1]);
    std::wstring::_Tidy_deallocate(&v193);
    std::wstring::_Tidy_deallocate(&v199);
    *(_OWORD *)v138 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v142, v138);
    v57 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v225);
    if ( v57 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v57,
        v128);
    if ( dword_1804543B0 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x400000002LL) )
    {
      ScenarioCounterStorage = Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v193 = 0;
      si128.m128i_i64[0] = 0;
      v137[0] = 0;
      v199 = 0;
      v200 = 0;
      LOWORD(v139) = 0;
      try
      {
        v137[0] = Microsoft::Diagnostics::ScenarioInst::PopulateTriggerInfoTlg();
        LOWORD(v139) = Microsoft::Diagnostics::ScenarioInst::PopulateSelectFieldsTlg(v147[0], &v199);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x2AD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          v58);
        v19 = v135;
        v31 = v148[0];
        v143 = v132[0];
        v42 = v130;
        a5 = CurrentScenarioEscalationsByType;
        a6 = v145;
        v45 = v131[0];
      }
      v59 = 0x400000002LL;
      if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x400000002LL) )
      {
        v182 = v199;
        v183 = (unsigned __int16)(WORD4(v199) - v199);
        v176 = &v139;
        v177 = 2;
        v158 = v193;
        v159 = (unsigned __int16)(WORD4(v193) - v193);
        v138[0] = (std::_Ref_count_base *)v137;
        LODWORD(v138[1]) = 2;
        MetadataEngine = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_1803854C0;
        v61 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(MetadataEngine, v207, &v133);
        if ( v61[3] > 7u )
          v61 = (_QWORD *)*v61;
        v173 = v61;
        v62 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385480;
        v63 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v62, v224, &v133);
        if ( v63[3] > 7u )
          v63 = (_QWORD *)*v63;
        v178 = v63;
        v64 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385490;
        v65 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v64, v223, &v133);
        if ( v65[3] > 7u )
          v65 = (_QWORD *)*v65;
        v179 = v65;
        v66 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_1803854A0;
        v67 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v66, v222, &v133);
        if ( v67[3] > 7u )
          v67 = (_QWORD *)*v67;
        v181 = v67;
        v68 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_1803854B0;
        v69 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v68, v221, &v133);
        if ( v69[3] > 7u )
          v69 = (_QWORD *)*v69;
        v163 = v69;
        v70 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385440;
        v71 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v70, v220, &v133);
        if ( v71[3] > 7u )
          v71 = (_QWORD *)*v71;
        v164 = v71;
        v72 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385450;
        v73 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v72, v219, &v133);
        if ( v73[3] > 7u )
          v73 = (_QWORD *)*v73;
        v165 = v73;
        v74 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385460;
        v75 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v74, v218, &v133);
        if ( v75[3] > 7u )
          v75 = (_QWORD *)*v75;
        v166 = v75;
        v167 = L"0";
        v76 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385470;
        v77 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v76, v217, &v133);
        if ( v77[3] > 7u )
          v77 = (_QWORD *)*v77;
        v172 = v77;
        v78 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385400;
        v79 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v78, v216, &v133);
        if ( v79[3] > 7u )
          v79 = (_QWORD *)*v79;
        v168 = v79;
        v80 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385410;
        v81 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v80, v215, &v133);
        if ( v81[3] > 7u )
          v81 = (_QWORD *)*v81;
        v169 = v81;
        v82 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385420;
        v83 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v82, v214, &v133);
        if ( v83[3] > 7u )
          v83 = (_QWORD *)*v83;
        v170 = v83;
        v84 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_180385430;
        v85 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v84, v213, &v133);
        if ( v85[3] > 7u )
          v85 = (_QWORD *)*v85;
        v171 = v85;
        v86 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v133 = *(_OWORD *)&off_1803853F0;
        v87 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v86, v212, &v133);
        if ( v87[3] > 7u )
          v87 = (_QWORD *)*v87;
        v161 = v87;
        v151 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 136LL))(
                             v31,
                             v191)
                         + 8);
        v88 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 136LL))(v31, v185);
        *(_QWORD *)&v133 = _tlgWrapBinary<wchar_t,2>(v186, *v88, (unsigned int)v151);
        v151 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 128LL))(
                             v31,
                             v187)
                         + 8);
        v89 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 128LL))(v31, v188);
        v151 = _tlgWrapBinary<wchar_t,2>(v189, *v89, (unsigned int)v151);
        v131[0] = v45;
        LOBYTE(v90) = -4;
        v145 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 192LL))(v31, v90);
        LOBYTE(v91) = -4;
        v92 = ScenarioCounterStorage;
        CurrentScenarioEscalationsByType = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioEscalationsByType(
                                             ScenarioCounterStorage,
                                             v31,
                                             v91);
        LOBYTE(v93) = -3;
        v132[0] = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 192LL))(v31, v93);
        LOBYTE(v94) = -3;
        v152 = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioEscalationsByType(v92, v31, v94);
        LOBYTE(v95) = -4;
        v153 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v95);
        LOBYTE(v96) = -4;
        CurrentScenarioReportsByType = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(
                                         v92,
                                         v31,
                                         v96);
        LOBYTE(v97) = -5;
        LODWORD(v155) = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v97);
        LOBYTE(v98) = -5;
        v149[0] = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(v92, v31, v98);
        LOBYTE(v99) = -3;
        LODWORD(v150) = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v99);
        LOBYTE(v100) = -3;
        LODWORD(v142) = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(v92, v31, v100);
        v101 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(
                             v31,
                             v190)
                         + 8);
        v102 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v184);
        v103 = _tlgWrapBinary<wchar_t,2>(v180, *v102, (unsigned int)v101);
        ScenarioCounterStorage = (struct Microsoft::Diagnostics::ScenarioCounterStorage *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v31 + 72LL))(v31);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
          v104,
          (unsigned int)word_1803EC9CA,
          v105,
          v106,
          (__int64)&ScenarioCounterStorage,
          (__int64)&v157,
          v103,
          (__int64)&v142,
          (__int64)&v150,
          (__int64)v149,
          (__int64)&v155,
          (__int64)&CurrentScenarioReportsByType,
          (__int64)&v153,
          (__int64)&v152,
          (__int64)v132,
          (__int64)&CurrentScenarioEscalationsByType,
          (__int64)&v145,
          (__int64)v131,
          v151,
          v133,
          (__int64)&v161,
          (__int64)&v171,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v172,
          (__int64)&v167,
          (__int64)&v166,
          (__int64)&v165,
          (__int64)&v164,
          (__int64)&v163,
          (__int64)&v181,
          (__int64)&v179,
          (__int64)&v178,
          (__int64)&v173,
          (__int64)v138,
          (__int64)&v158,
          (__int64)&v176,
          (__int64)&v182);
        std::wstring::_Tidy_deallocate(v212);
        std::wstring::_Tidy_deallocate(v213);
        std::wstring::_Tidy_deallocate(v214);
        std::wstring::_Tidy_deallocate(v215);
        std::wstring::_Tidy_deallocate(v216);
        std::wstring::_Tidy_deallocate(v217);
        std::wstring::_Tidy_deallocate(v218);
        std::wstring::_Tidy_deallocate(v219);
        std::wstring::_Tidy_deallocate(v220);
        std::wstring::_Tidy_deallocate(v221);
        std::wstring::_Tidy_deallocate(v222);
        std::wstring::_Tidy_deallocate(v223);
        std::wstring::_Tidy_deallocate(v224);
        std::wstring::_Tidy_deallocate(v207);
      }
      std::vector<enum gsl::byte>::_Tidy(&v199, v59);
      std::vector<enum gsl::byte>::_Tidy(&v193, v107);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v225);
    v131[0] = a6 != 0;
    v130 = a5 != 0;
    LOBYTE(v108) = a7;
    v109 = Microsoft::Diagnostics::EscalationUploadAction::_from_integral(&v139, v108);
    std::make_shared<Microsoft::Diagnostics::EscalationWorkItemOverrides,Microsoft::Diagnostics::EscalationUploadAction,std::wstring &,bool,bool,bool &>(
      (unsigned int)v174,
      v109,
      (unsigned int)pszPathOut,
      (unsigned int)&v130,
      (__int64)v131,
      (__int64)v203);
    v208[0] = v201[0];
    std::function<void (long,_GUID,_GUID)>::function<void (long,_GUID,_GUID)>(v209, v160);
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      v210,
      v147);
    std::wstring::wstring(v211, v205);
    EscalationEngine = Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    *(_QWORD *)&v133 = v138;
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      v138,
      v174);
    v112 = v111;
    std::function_void___cdecl_long__::function_void___cdecl_long____Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2____0_(
      v207,
      v208);
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      &v158,
      v147);
    LOBYTE(v113) = v42;
    v132[0] = Microsoft::Diagnostics::EscalationEngine::Execute(EscalationEngine, v31, v114, v113, v143, v115, v112);
    v138[0] = (std::_Ref_count_base *)L"EscalateApiFinished_0";
    v138[1] = (std::_Ref_count_base *)21;
    Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
      (unsigned int)v225,
      (unsigned int)v138,
      0x1000000,
      0,
      0,
      0);
    v117 = (_QWORD *)std::wstring::operator std::wstring_view(v206, v180, v116);
    std::wstring::_Assign<wchar_t>(v226, *v117, v117[1]);
    (*(void (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v180);
    v138[0] = (std::_Ref_count_base *)L"ScenarioName";
    v138[1] = (std::_Ref_count_base *)12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v225, (int)v228);
    v138[0] = (std::_Ref_count_base *)L"ScenarioId";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v225, v228, v138, v205);
    v138[0] = (std::_Ref_count_base *)L"HRESULT";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v225, (int)v228);
    v118 = *(_OWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v180);
    v119 = std::wstring::wstring(&v199, L"Scenario:");
    *(_OWORD *)v138 = v118;
    v120 = Microsoft::Diagnostics::operator+(&v193, v119, v138);
    v122 = (_QWORD *)std::wstring::operator std::wstring_view(v120, v184, v121);
    std::wstring::_Assign<wchar_t>(v227, *v122, v122[1]);
    std::wstring::_Tidy_deallocate(&v193);
    std::wstring::_Tidy_deallocate(&v199);
    *(_OWORD *)v138 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v142, v138);
    v123 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v225);
    if ( v123 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x326,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v123,
        v129);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v225);
    v124 = v132[0];
    if ( v132[0] >= 0 )
    {
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2_::__lambda_2_(v208);
      if ( v175 )
        std::_Ref_count_base::_Decref(v175);
      std::wstring::_Tidy_deallocate(v206);
      std::wstring::_Tidy_deallocate(v205);
      std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(v162);
      if ( v147[1] )
        std::_Ref_count_base::_Decref(v147[1]);
      if ( v148[1] )
        std::_Ref_count_base::_Decref(v148[1]);
      std::wstring::_Tidy_deallocate(pszPathOut);
      std::wstring::_Tidy_deallocate(v195);
      std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
      std::wstring::_Tidy_deallocate(v192);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
      if ( v19 )
      {
        v135 = 0;
        Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x329,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)v132[0],
        v129);
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2_::__lambda_2_(v208);
      if ( v175 )
        std::_Ref_count_base::_Decref(v175);
      std::wstring::_Tidy_deallocate(v206);
      std::wstring::_Tidy_deallocate(v205);
      std::vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>::~vector<std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>>(v162);
      if ( v147[1] )
        std::_Ref_count_base::_Decref(v147[1]);
      if ( v148[1] )
        std::_Ref_count_base::_Decref(v148[1]);
      std::wstring::_Tidy_deallocate(pszPathOut);
      std::wstring::_Tidy_deallocate(v195);
      std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v146);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v140);
      std::wstring::_Tidy_deallocate(v192);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v132[1]);
      if ( v19 )
      {
        v135 = 0;
        Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v134);
      }
      return v124;
    }
  }
}

```

## disassembly

```asm
0x1801f9dc4  mov     rax, rsp
0x1801f9dc7  push    rbx
0x1801f9dc8  push    rsi
0x1801f9dc9  push    rdi
0x1801f9dca  push    r12
0x1801f9dcc  push    r13
0x1801f9dce  push    r14
0x1801f9dd0  push    r15
0x1801f9dd2  sub     rsp, 0C30h
0x1801f9dd9  movaps  xmmword ptr [rax-48h], xmm6
0x1801f9ddd  mov     rax, cs:__security_cookie
0x1801f9de4  xor     rax, rsp
0x1801f9de7  mov     [rsp+0C68h+var_58], rax
0x1801f9def  mov     r14, r9
0x1801f9df2  mov     [rsp+0C68h+var_AD8], r8d
0x1801f9dfa  mov     rdi, rdx
0x1801f9dfd  mov     [rsp+0C68h+var_A50], rcx
0x1801f9e05  mov     eax, [rsp+0C68h+arg_20]
0x1801f9e0c  mov     [rsp+0C68h+var_AB4], eax
0x1801f9e13  mov     eax, [rsp+0C68h+arg_28]
0x1801f9e1a  mov     [rsp+0C68h+var_AB0], eax
0x1801f9e21  mov     r12, [rsp+0C68h+arg_40]
0x1801f9e29  mov     r13, [rsp+0C68h+arg_48]
0x1801f9e31  mov     r9, [rsp+0C68h+arg_50]
0x1801f9e39  mov     [rsp+0C68h+var_A28], r9
0x1801f9e41  mov     rdx, [rsp+0C68h+arg_58]
0x1801f9e49  mov     [rsp+0C68h+var_AC0], rdx
0x1801f9e51  mov     rcx, [rsp+0C68h+arg_60]
0x1801f9e59  mov     [rsp+0C68h+var_A70], rcx
0x1801f9e61  mov     eax, cs:dword_1804543B0
0x1801f9e67  cmp     eax, 4
0x1801f9e6a  jbe     loc_1801FA026
0x1801f9e70  mov     edx, 2000h
0x1801f9e75  lea     rcx, dword_1804543B0
0x1801f9e7c  call    _tlgKeywordOn
0x1801f9e81  xor     esi, esi
0x1801f9e83  test    al, al
0x1801f9e85  jz      short loc_1801F9EC9
0x1801f9e87  cmp     [r9+38h], rsi
0x1801f9e8b  setz    [rsp+0C68h+var_B28]
0x1801f9e93  mov     qword ptr [rsp+0C68h+var_A78], rdi
0x1801f9e9b  lea     rax, [rsp+0C68h+var_B28]
0x1801f9ea3  mov     [rsp+0C68h+var_C40], rax
0x1801f9ea8  lea     rax, [rsp+0C68h+var_A78]
0x1801f9eb0  mov     qword ptr [rsp+0C68h+var_C48], rax; int
0x1801f9eb5  lea     rdx, byte_1803ECD95
0x1801f9ebc  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x1801f9ec1  mov     r8d, [rsp+0C68h+var_AD8]
0x1801f9ec9  mov     rdx, [rsp+0C68h+var_AC0]
0x1801f9ed1  mov     rcx, [rsp+0C68h+var_A70]
0x1801f9ed9  mov     [rsp+0C68h+var_B08], rdi
0x1801f9ee1  mov     r15d, 1
0x1801f9ee7  mov     [rsp+0C68h+var_B00], r15b
0x1801f9eef  test    r14, r14
0x1801f9ef2  jz      loc_1801FBF84
0x1801f9ef8  test    r12, r12
0x1801f9efb  jz      loc_1801FBF84
0x1801f9f01  test    r13, r13
0x1801f9f04  jz      loc_1801FBF84
0x1801f9f0a  test    rdx, rdx
0x1801f9f0d  jz      short loc_1801F9F11
0x1801f9f0f  mov     [rdx], esi
0x1801f9f11  test    rcx, rcx
0x1801f9f14  jz      short loc_1801F9F21
0x1801f9f16  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801f9f1d  movdqu  xmmword ptr [rcx], xmm0
0x1801f9f21  cmp     r8d, r15d
0x1801f9f24  ja      loc_1801FBF49
0x1801f9f2a  cmp     [rsp+0C68h+arg_30], 2
0x1801f9f32  ja      loc_1801FBF0E
0x1801f9f38  mov     qword ptr [rsp+0C68h+var_B24+4], rsi
0x1801f9f40  xorps   xmm0, xmm0
0x1801f9f43  movups  [rsp+0C68h+var_8D0], xmm0
0x1801f9f4b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801f9f53  movdqu  [rsp+0C68h+var_8C0], xmm1
0x1801f9f5c  mov     word ptr [rsp+0C68h+var_8D0], si
0x1801f9f64  lea     r8, [rsp+0C68h+var_8D0]
0x1801f9f6c  lea     rdx, [rsp+0C68h+var_B24+4]
0x1801f9f74  call    ?GetRpcImpersonationToken@ApiServer@Diagnostics@Microsoft@@IEBAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::wstring &)
0x1801f9f79  mov     ebx, eax
0x1801f9f7b  test    eax, eax
0x1801f9f7d  jns     short loc_1801F9FD4
0x1801f9f7f  mov     rcx, [rsp+0C68h]; this
0x1801f9f87  mov     r9d, eax; char *
0x1801f9f8a  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801f9f91  mov     edx, 1CFh; void *
0x1801f9f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f9f9b  nop
0x1801f9f9c  lea     rcx, [rsp+0C68h+var_8D0]
0x1801f9fa4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801f9fa9  nop
0x1801f9faa  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801f9fb2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f9fb7  nop
0x1801f9fb8  mov     [rsp+0C68h+var_B00], sil
0x1801f9fc0  lea     rcx, [rsp+0C68h+var_B08]
0x1801f9fc8  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801f9fcd  mov     eax, ebx
0x1801f9fcf  jmp     loc_1801FBFC6
0x1801f9fd4  lea     rcx, [rsp+0C68h+var_AD0]
0x1801f9fdc  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x1801f9fe1  nop
0x1801f9fe2  mov     ebx, esi
0x1801f9fe4  cmp     ebx, [rsp+0C68h+arg_38]
0x1801f9feb  jnb     loc_1801FA095
0x1801f9ff1  mov     eax, ebx
0x1801f9ff3  lea     r8, [r12+rax*8]
0x1801f9ff7  cmp     [r8], rsi
0x1801f9ffa  jz      short loc_1801FA02D
0x1801f9ffc  lea     r9, ds:0[rax*8]
0x1801fa004  add     r9, r13
0x1801fa007  cmp     [r9], rsi
0x1801fa00a  jz      short loc_1801FA02D
0x1801fa00c  lea     rdx, [rsp+0C68h+var_AE8]
0x1801fa014  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa01c  call    ??$_Emplace@AEAPEB_WAEAPEB_W@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEAPEB_W0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<wchar_t const * &,wchar_t const * &>(wchar_t const * &,wchar_t const * &)
0x1801fa021  add     ebx, r15d
0x1801fa024  jmp     short loc_1801F9FE4
0x1801fa026  xor     esi, esi
0x1801fa028  jmp     loc_1801F9ED9
0x1801fa02d  mov     rcx, [rsp+0C68h]; this
0x1801fa035  mov     ebx, 80070057h
0x1801fa03a  mov     r9d, ebx; char *
0x1801fa03d  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa044  mov     edx, 1D8h; void *
0x1801fa049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa04e  nop
0x1801fa04f  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa057  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa05c  nop
0x1801fa05d  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa065  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa06a  nop
0x1801fa06b  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa073  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa078  nop
0x1801fa079  mov     [rsp+0C68h+var_B00], sil
0x1801fa081  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa089  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa08e  mov     eax, ebx
0x1801fa090  jmp     loc_1801FBFC6
0x1801fa095  lea     r9, [rsp+0C68h+var_AD0]
0x1801fa09d  lea     r8, [rsp+0C68h+var_B24+4]
0x1801fa0a5  lea     rdx, [rsp+0C68h+var_830]
0x1801fa0ad  call    ?ProcessApiMetaProperties@UtcApiManager@Diagnostics@Microsoft@@AEAA?AV?$tuple@U_GUID@@_NJ_N@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@5@@Z; Microsoft::Diagnostics::UtcApiManager::ProcessApiMetaProperties(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::map<std::wstring,std::wstring> &)
0x1801fa0b2  movsxd  rax, [rsp+0C68h+var_82C]
0x1801fa0ba  mov     qword ptr [rsp+0C68h+var_A78], rax
0x1801fa0c2  mov     rdx, [rsp+0C68h+var_A50]
0x1801fa0ca  add     rdx, 0E0h
0x1801fa0d1  lea     r8, [rsp+0C68h+var_A78]
0x1801fa0d9  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa0e1  call    ??$?0_JU?$ratio@$00$0DOI@@std@@@?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@AEAVrecursive_timed_mutex@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(std::recursive_timed_mutex &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801fa0e6  nop
0x1801fa0e7  cmp     [rsp+0C68h+var_AA0], sil
0x1801fa0ef  jnz     short loc_1801FA167
0x1801fa0f1  mov     rcx, [rsp+0C68h]; this
0x1801fa0f9  mov     ebx, 87C5102Bh
0x1801fa0fe  mov     r9d, ebx; char *
0x1801fa101  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa108  mov     edx, 1E7h; void *
0x1801fa10d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa112  nop
0x1801fa113  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa11b  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa120  nop
0x1801fa121  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa129  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa12e  nop
0x1801fa12f  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa137  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa13c  nop
0x1801fa13d  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa145  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa14a  nop
0x1801fa14b  mov     [rsp+0C68h+var_B00], sil
0x1801fa153  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa15b  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa160  mov     eax, ebx
0x1801fa162  jmp     loc_1801FBFC6
0x1801fa167  mov     rdx, r14
0x1801fa16a  lea     rcx, [rsp+0C68h+var_890]
0x1801fa172  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801fa177  nop
0x1801fa178  lea     rcx, [rsp+0C68h+var_890]
0x1801fa180  mov     r13d, 7
0x1801fa186  cmp     [rsp+0C68h+var_878], r13
0x1801fa18e  cmova   rcx, [rsp+0C68h+var_890]
0x1801fa197  lea     r9d, [r13+28h]
0x1801fa19b  xor     r8d, r8d
0x1801fa19e  mov     rdx, [rsp+0C68h+var_880]
0x1801fa1a6  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1801fa1ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801fa1af  jz      loc_1801FA239
0x1801fa1b5  mov     rcx, [rsp+0C68h]; this
0x1801fa1bd  mov     ebx, 80070057h
0x1801fa1c2  mov     r9d, ebx; char *
0x1801fa1c5  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa1cc  mov     edx, 1F0h; void *
0x1801fa1d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa1d6  nop
0x1801fa1d7  lea     rcx, [rsp+0C68h+var_890]
0x1801fa1df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa1e4  nop
0x1801fa1e5  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa1ed  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa1f2  nop
0x1801fa1f3  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa1fb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa200  nop
0x1801fa201  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa209  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa20e  nop
0x1801fa20f  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa217  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa21c  nop
0x1801fa21d  mov     [rsp+0C68h+var_B00], sil
0x1801fa225  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa22d  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa232  mov     eax, ebx
0x1801fa234  jmp     loc_1801FBFC6
0x1801fa239  xor     r8d, r8d
0x1801fa23c  mov     rdx, [rsp+0C68h+var_880]
0x1801fa244  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa24c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801fa251  nop
0x1801fa252  mov     rdx, [rsp+0C68h+var_860]
0x1801fa25a  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa262  cmp     [rsp+0C68h+var_858], r13
0x1801fa26a  cmova   rcx, [rsp+0C68h+pszPathOut]; pszPathOut
0x1801fa273  inc     rdx; cchPathOut
0x1801fa276  mov     r9d, r15d; dwFlags
0x1801fa279  mov     r8, r14; pszPathIn
0x1801fa27c  call    cs:__imp_PathCchCanonicalizeEx
0x1801fa282  test    eax, eax
0x1801fa284  jns     loc_1801FA31C
0x1801fa28a  mov     rcx, [rsp+0C68h]; this
0x1801fa292  mov     ebx, 80070057h
0x1801fa297  mov     r9d, ebx; char *
0x1801fa29a  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa2a1  mov     edx, 1F7h; void *
0x1801fa2a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa2ab  nop
0x1801fa2ac  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa2b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa2b9  nop
0x1801fa2ba  lea     rcx, [rsp+0C68h+var_890]
0x1801fa2c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa2c7  nop
0x1801fa2c8  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa2d0  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa2d5  nop
0x1801fa2d6  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa2de  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa2e3  nop
0x1801fa2e4  lea     rcx, [rsp+0C68h+var_8D0]
0x1801fa2ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa2f1  nop
0x1801fa2f2  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801fa2fa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801fa2ff  nop
0x1801fa300  mov     [rsp+0C68h+var_B00], sil
0x1801fa308  lea     rcx, [rsp+0C68h+var_B08]
0x1801fa310  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801fa315  mov     eax, ebx
0x1801fa317  jmp     loc_1801FBFC6
0x1801fa31c  xor     eax, eax
0x1801fa31e  lock cmpxchg qword ptr cs:xmmword_180463150, rsi
0x1801fa327  jz      loc_1801FBE7D
0x1801fa32d  xor     eax, eax
0x1801fa32f  lock cmpxchg qword ptr cs:xmmword_180463190+8, rsi
0x1801fa338  jz      loc_1801FBDEC
0x1801fa33e  lea     r12, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1801fa345  mov     rcx, r12; this
0x1801fa348  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x1801fa34d  mov     r8, rdi
0x1801fa350  lea     rdx, [rsp+0C68h+var_AF8]
0x1801fa358  mov     rcx, rax
0x1801fa35b  call    ?GetScenarioState@ScenarioManager@Diagnostics@Microsoft@@QEBA?AVScenarioActivityState@23@AEBU_GUID@@@Z; Microsoft::Diagnostics::ScenarioManager::GetScenarioState(_GUID const &)
0x1801fa360  cmp     [rsp+0C68h+var_AF8], sil
0x1801fa368  jz      loc_1801FA400
0x1801fa36e  mov     rcx, [rsp+0C68h]; this
0x1801fa376  mov     ebx, 87C51005h
0x1801fa37b  mov     r9d, ebx; char *
0x1801fa37e  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801fa385  mov     edx, 20Ah; void *
0x1801fa38a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa38f  nop
0x1801fa390  lea     rcx, [rsp+0C68h+pszPathOut]
0x1801fa398  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa39d  nop
0x1801fa39e  lea     rcx, [rsp+0C68h+var_890]
0x1801fa3a6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801fa3ab  nop
0x1801fa3ac  lea     rcx, [rsp+0C68h+var_AA8]
0x1801fa3b4  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801fa3b9  nop
0x1801fa3ba  lea     rcx, [rsp+0C68h+var_AD0]
0x1801fa3c2  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801fa3c7  nop
0x1801fa3c8  lea     rcx, [rsp+0C68h+var_8D0]
  ... truncated ...
```
