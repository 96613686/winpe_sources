# UpdateManager::PerformAction(std::shared_ptr<Update> const &,std::shared_ptr<Action> const &,std::weak_ptr<uint> const &,std::weak_ptr<std::optional<std::chrono::duration<__int64,std::ratio<1,1>>>> const &,std::weak_ptr<std::optional<ProgressCallbackData>> const &)

- ea: `0x140085f54`
- end: `0x140087fb1`
- name: `?PerformAction@UpdateManager@@AEAA?AV?$optional@UActionResult@@@std@@AEBV?$shared_ptr@VUpdate@@@3@AEBV?$shared_ptr@VAction@@@3@AEBV?$weak_ptr@I@3@AEBV?$weak_ptr@V?$optional@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@std@@@3@AEBV?$weak_ptr@V?$optional@UProgressCallbackData@@@std@@@3@@Z`
- size: `8285`
- prototype: ``
- caller_count: `2`
- callee_count: `75`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14009baa0`
- `0x1400b9f40`

## callees

- `0x140024de0`
- `0x140028fa4`
- `0x14002cc08`
- `0x14002cc9c`
- `0x140040184`
- `0x140043284`
- `0x1400447ac`
- `0x140045404`
- `0x140045a8c`
- `0x140045b0c`
- `0x1400462a8`
- `0x140057a20`
- `0x140075c08`
- `0x140078144`
- `0x1400788b8`
- `0x140079bb4`
- `0x140079c7c`
- `0x14007a074`
- `0x14007a2b4`
- `0x14007e798`
- `0x140085f54`
- `0x140088a70`
- `0x140088b74`
- `0x140088c78`
- `0x14009e490`
- `0x14009eb48`
- `0x1400a38a4`
- `0x1400a390c`
- `0x1400a39dc`
- `0x1400a3cb0`
- `0x1400a4bf8`
- `0x1400a5688`
- `0x1400a5ecc`
- `0x1400a5fcc`
- `0x1400a60bc`
- `0x1400a6160`
- `0x1400a61c8`
- `0x1400a6288`
- `0x1400a62e8`
- `0x1400a6388`
- `0x1400a6488`
- `0x1400a8280`
- `0x1400a985c`
- `0x1400a9974`
- `0x1400a9b68`
- `0x1400aaa08`
- `0x1400b54c0`
- `0x1400b54fc`
- `0x1400b553c`
- `0x1400b55f4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140087be5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140087be5`

## string_xrefs

- `0x140087f56`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140087f70`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140087f8a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1400876cd`: `Completed`
- `0x1400877ed`: `Completed`
- `0x14008787b`: `Completed`
- `0x1400862e7`: `Update priority`
- `0x1400865d3`: `Update deferral mode`
- `0x1400875ae`: `Update deferral mode`
- `0x140087918`: `Update deferral mode`
- `0x140086a1e`: `Max action attempts per unit time`
- `0x1400870bd`: `Update action timeout in minutes`
- `0x140087c4f`: `UpdateRelatedActivityId`
- `0x140087c64`: `UpdateRelatedActivityId`
- `0x140087c45`: `UpdateGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=76
unsigned int *__fastcall UpdateManager::PerformAction(
        __int64 a1,
        unsigned int *a2,
        const struct Update **a3,
        _QWORD *a4,
        __int64 a5,
        unsigned __int64 a6,
        unsigned __int64 a7)
{
  const struct Update **v8; // r15
  char IsEnabled; // al
  const struct Update *v11; // rcx
  bool v12; // zf
  __int64 (__fastcall *v13)(const struct Update *, __int128 *); // rax
  int v14; // eax
  int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  const struct Update *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 *v25; // rax
  __int64 v26; // rcx
  volatile signed __int32 *v27; // r13
  UpdateDatabase **v28; // r12
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rdx
  __m128i v34; // xmm8
  __int64 System; // rax
  __int64 v36; // rdi
  __int64 UpdateRelatedActivityId; // rbx
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rbx
  int v49; // edi
  __int64 v50; // rdx
  _QWORD *v51; // rax
  unsigned __int64 v52; // xmm1_8
  _QWORD *v53; // rcx
  int v54; // ebx
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  _QWORD *v57; // rax
  __int128 *v58; // rax
  __int128 v59; // xmm7
  __int64 v60; // xmm6_8
  bool IsApproved; // al
  __int64 v62; // rdi
  _QWORD *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rsi
  __int64 (__fastcall *v66)(__int64, _QWORD *, const struct Update **, _QWORD, int, _DWORD, const struct Update *); // rdi
  const struct Update *v67; // rbx
  __int64 *v68; // rax
  __int64 v69; // rbx
  const struct Update *v70; // rsi
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 *v74; // rbx
  __int64 *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 *v78; // rbx
  __int64 *v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rax
  __int64 *v82; // rbx
  __int64 *v83; // rax
  __int64 v84; // rdx
  __int64 v85; // rax
  __int64 *v86; // rbx
  __int64 *v87; // rax
  __int64 v88; // rdx
  UpdateDatabase *v89; // rsi
  _QWORD *v90; // rbx
  _QWORD *v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int128 v94; // kr30_16
  volatile signed __int32 *v95; // r12
  __int128 v96; // kr40_16
  __int64 v97; // r9
  volatile signed __int32 *v98; // rdx
  __int64 v99; // rsi
  const struct Update *v100; // rax
  __int64 v101; // rax
  RTL_SRWLOCK *v102; // rcx
  const struct Update *v103; // rax
  __int64 v104; // rsi
  __int64 v105; // rbx
  __int64 v106; // rax
  unsigned int v107; // ebx
  char v108; // al
  const struct Update *v109; // rcx
  __int64 (__fastcall *v110)(const struct Update *, __int128 *); // rax
  int v111; // eax
  int v112; // r8d
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // rdx
  char v117; // al
  const struct Update *v118; // rcx
  __int64 (__fastcall *v119)(const struct Update *, __int128 *); // rax
  int v120; // esi
  __int64 v121; // rsi
  unsigned int *v122; // rbx
  int v123; // esi
  _QWORD *v124; // rax
  wil *v125; // r9
  __int64 v126; // rdx
  __int64 v127; // rdx
  wil *v128; // rcx
  UpdateDatabase **v129; // rbx
  _QWORD *v130; // rbx
  const char *v131; // r9
  __int64 *v132; // rax
  __int64 i; // rax
  __int64 v134; // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v136; // r9
  __int64 v137; // r11
  __int64 v138; // rax
  __int64 v139; // rdx
  __int128 *v140; // rax
  _QWORD *updated; // rax
  __int64 v142; // rcx
  __int64 v143; // rax
  const char *v144; // r9
  __int64 v145; // r11
  __int64 v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rdx
  __int64 v149; // rbx
  void (__fastcall *v150)(__int64, _QWORD, __int128 *, _OWORD *, __int128 *); // rsi
  __int128 v151; // xmm6
  _QWORD *v152; // rax
  __int64 v153; // rcx
  __int128 *v154; // rax
  __int64 v155; // rdx
  void (__fastcall *v156)(__int64, _QWORD, __int128 *); // rbx
  __int64 v157; // rbx
  __int64 v158; // rdx
  __int64 v159; // rbx
  void (__fastcall *v160)(__int64, __int128 *, _OWORD *, __int128 *); // rsi
  __int128 *v161; // rax
  _QWORD *v162; // rax
  __int64 v163; // rcx
  __int64 v164; // rdx
  __int64 v165; // rdx
  __int128 *v166; // rcx
  __int64 v167; // rsi
  __int128 v168; // xmm6
  _QWORD *v169; // rax
  __int64 v170; // rcx
  void (__fastcall *v171)(__int64, __int128 *); // rbx
  const char *v172; // r9
  __int64 v173; // rbx
  void (__fastcall *v174)(__int64, __int64, __int128 *, __int128 *); // r15
  __int64 v175; // rax
  const char *v176; // r9
  __int64 v177; // r11
  __int64 v178; // rax
  __int64 PrimaryKey; // rax
  __int64 v180; // rdx
  __int64 v181; // rdx
  __int64 v182; // rdx
  volatile signed __int32 *v183; // rbx
  __int64 v184; // rdx
  volatile signed __int32 *v185; // rbx
  __int64 v186; // rdx
  __int64 v187; // rdx
  volatile signed __int32 *v188; // rbx
  volatile signed __int32 *v189; // rbx
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rdi
  void (__fastcall *v194)(__int64, __int128 *, const std::exception *); // rbx
  wil *v195; // rcx
  int v196; // [rsp+20h] [rbp-778h]
  int v197; // [rsp+20h] [rbp-778h]
  char v198[8]; // [rsp+70h] [rbp-728h] BYREF
  __int64 v199; // [rsp+78h] [rbp-720h] BYREF
  __int128 v200; // [rsp+80h] [rbp-718h] BYREF
  __int64 v201; // [rsp+90h] [rbp-708h]
  __int64 v202; // [rsp+98h] [rbp-700h]
  __m128i v203; // [rsp+A0h] [rbp-6F8h] BYREF
  _DWORD v204[4]; // [rsp+B0h] [rbp-6E8h] BYREF
  __int128 v205; // [rsp+C0h] [rbp-6D8h] BYREF
  _QWORD v206[2]; // [rsp+E0h] [rbp-6B8h] BYREF
  unsigned int v207; // [rsp+F0h] [rbp-6A8h]
  unsigned int *v208; // [rsp+F8h] [rbp-6A0h]
  _QWORD *v209; // [rsp+100h] [rbp-698h]
  __int128 v210; // [rsp+110h] [rbp-688h] BYREF
  __m128i v211; // [rsp+120h] [rbp-678h] BYREF
  __int128 v212; // [rsp+130h] [rbp-668h] BYREF
  __int64 v213; // [rsp+140h] [rbp-658h]
  UpdateDatabase **v214; // [rsp+148h] [rbp-650h]
  __int64 DiscoveryTime; // [rsp+150h] [rbp-648h]
  __int64 v216; // [rsp+158h] [rbp-640h]
  unsigned int *v217; // [rsp+160h] [rbp-638h]
  __int64 *v218; // [rsp+168h] [rbp-630h]
  __int128 v219; // [rsp+170h] [rbp-628h] BYREF
  _OWORD v220[2]; // [rsp+180h] [rbp-618h] BYREF
  _QWORD v221[2]; // [rsp+1A0h] [rbp-5F8h] BYREF
  __int128 v222; // [rsp+1B0h] [rbp-5E8h]
  __m128i v223; // [rsp+1C0h] [rbp-5D8h] BYREF
  __int128 v224; // [rsp+1D0h] [rbp-5C8h] BYREF
  __int64 v225; // [rsp+1E0h] [rbp-5B8h]
  const struct Update **v226; // [rsp+1E8h] [rbp-5B0h]
  const struct Update *v227; // [rsp+1F0h] [rbp-5A8h]
  _BYTE v228[16]; // [rsp+1F8h] [rbp-5A0h] BYREF
  _QWORD v229[3]; // [rsp+208h] [rbp-590h] BYREF
  _QWORD v230[4]; // [rsp+220h] [rbp-578h] BYREF
  _QWORD v231[4]; // [rsp+240h] [rbp-558h] BYREF
  _OWORD v232[7]; // [rsp+260h] [rbp-538h] BYREF
  const std::exception *v233; // [rsp+2D0h] [rbp-4C8h] BYREF
  _BYTE v234[56]; // [rsp+2E0h] [rbp-4B8h] BYREF
  wil *v235; // [rsp+318h] [rbp-480h]
  _QWORD v236[4]; // [rsp+320h] [rbp-478h] BYREF
  __int128 v237; // [rsp+340h] [rbp-458h]
  __int64 v238; // [rsp+350h] [rbp-448h]
  char v239; // [rsp+370h] [rbp-428h]
  __int64 v240; // [rsp+378h] [rbp-420h]
  char v241[16]; // [rsp+380h] [rbp-418h] BYREF
  __int64 v242; // [rsp+390h] [rbp-408h]
  char v243; // [rsp+3C0h] [rbp-3D8h]
  char v244; // [rsp+3F8h] [rbp-3A0h]
  char v245[64]; // [rsp+400h] [rbp-398h] BYREF
  char v246[64]; // [rsp+440h] [rbp-358h] BYREF
  char v247[64]; // [rsp+480h] [rbp-318h] BYREF
  __int128 v248; // [rsp+4C0h] [rbp-2D8h] BYREF
  __int64 v249; // [rsp+4D0h] [rbp-2C8h]
  unsigned __int64 v250; // [rsp+4D8h] [rbp-2C0h]
  char v251; // [rsp+4E0h] [rbp-2B8h]
  __int128 v252; // [rsp+4F0h] [rbp-2A8h] BYREF
  const struct Update *v253; // [rsp+500h] [rbp-298h] BYREF
  volatile signed __int32 *v254; // [rsp+508h] [rbp-290h]
  __int128 v255; // [rsp+510h] [rbp-288h] BYREF
  __int64 v256; // [rsp+520h] [rbp-278h]
  __int64 v257; // [rsp+528h] [rbp-270h]
  _QWORD v258[4]; // [rsp+530h] [rbp-268h] BYREF
  _QWORD v259[4]; // [rsp+550h] [rbp-248h] BYREF
  __int128 v260; // [rsp+570h] [rbp-228h] BYREF
  __int64 v261; // [rsp+580h] [rbp-218h]
  __int64 v262; // [rsp+588h] [rbp-210h]
  __int128 v263; // [rsp+590h] [rbp-208h]
  __int64 v264; // [rsp+5A0h] [rbp-1F8h]
  char v265; // [rsp+5C0h] [rbp-1D8h]
  __int64 v266; // [rsp+5C8h] [rbp-1D0h]
  char v267[16]; // [rsp+5D0h] [rbp-1C8h] BYREF
  __int64 v268; // [rsp+5E0h] [rbp-1B8h]
  char v269; // [rsp+610h] [rbp-188h]
  char v270; // [rsp+648h] [rbp-150h]
  char v271[64]; // [rsp+650h] [rbp-148h] BYREF
  char v272[64]; // [rsp+690h] [rbp-108h] BYREF
  char v273[64]; // [rsp+6D0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+798h] [rbp+0h]

  v209 = a4;
  v8 = a3;
  v208 = a2;
  v213 = a1;
  v225 = a1;
  v217 = a2;
  v226 = a3;
  LODWORD(v199) = 0;
  v224 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl'::`2'::impl);
  v11 = *v8;
  v12 = IsEnabled == 0;
  v13 = *(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)*v8 + 24LL);
  if ( v12 )
  {
    v18 = v13(v11, &v200);
    v204[0] = 12;
    v20 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<3600,1>>,wchar_t const (&)[16],std::wstring>(
            &v203,
            v204,
            v19,
            v18);
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v224, v20);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v203);
  }
  else
  {
    v198[0] = 1;
    v14 = v13(v11, &v200);
    v204[0] = 12;
    v16 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<3600,1>>,wchar_t const (&)[16],std::wstring,bool>(
            (unsigned int)&v203,
            (unsigned int)v204,
            v15,
            v14,
            (__int64)v198);
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v224, v16);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v203);
  }
  std::wstring::~wstring(&v200, v17);
  v222 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks>::GetImpl'::`2'::impl) )
  {
    v211 = 0;
    UpdateManager::GetUxBroker(a1, &v211);
    if ( v211.m128i_i64[0] )
    {
      v198[0] = 1;
      v230[0] = a1;
      v22 = v8[1];
      if ( v22 )
        _InterlockedIncrement((volatile signed __int32 *)v22 + 2);
      v230[1] = *v8;
      v230[2] = v8[1];
      v23 = a4[1];
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      v230[3] = *a4;
      v231[0] = a4[1];
      v231[1] = a7;
      v24 = UX::Broker::MinProgressFrequency(v21, v206);
      v25 = (__int64 *)std::make_shared_watchdog_timer_std::chrono::duration___int64_std::ratio_1_1_____UpdateManager::PerformAction_::_13_::_lambda_1__bool_(
                         &v203,
                         v24,
                         v230,
                         v198);
      v26 = *v25;
      v27 = (volatile signed __int32 *)v25[1];
      *v25 = 0;
      v25[1] = 0;
      v223 = 0u;
      *(_QWORD *)&v222 = v26;
      *((_QWORD *)&v222 + 1) = v27;
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v223);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v203);
      UpdateManager::PerformAction_::_13_::_lambda_1_::__lambda_1_(v230);
    }
    else
    {
      v27 = (volatile signed __int32 *)*((_QWORD *)&v222 + 1);
    }
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v211);
  }
  else
  {
    v27 = (volatile signed __int32 *)*((_QWORD *)&v222 + 1);
  }
  v236[0] = *v8;
  v236[1] = 0;
  v28 = (UpdateDatabase **)(a1 + 16);
  v214 = (UpdateDatabase **)(a1 + 16);
  v236[2] = *(_QWORD *)(a1 + 16);
  v236[3] = 0;
  v237 = 0;
  v238 = 0;
  v239 = 0;
  v240 = 0;
  std::set<std::wstring>::set<std::wstring>(v241);
  v242 = 0;
  v243 = 0;
  v244 = 0;
  std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v245);
  std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v246);
  std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(v247);
  v218 = (__int64 *)(a1 + 32);
  v29 = *(_QWORD *)(a1 + 32);
  v200 = 0;
  v201 = 0;
  v202 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v200, &psz, 0);
  v203 = *(__m128i *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v205, L"Update priority");
  v30 = DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
          v29,
          (unsigned int)&v248,
          (unsigned int)&v203,
          (unsigned int)v236,
          (__int64)&v200);
  v204[0] = (unsigned __int8)std::operator==<wchar_t>(v30, L"Low", v31);
  std::wstring::~wstring(&v248, v32);
  std::wstring::~wstring(&v200, v33);
  UpdateDatabase::GetAndIncrementCV(*v28, &v253, *v8);
  v255 = 0;
  v256 = 0;
  v257 = 7;
  LOWORD(v255) = 0;
  UpdateDatabase::GetUpdateActionDelayDetails(*v28, &v248, *v8);
  v34 = 0;
  v223 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    System = SystemInterface::Providers::GetSystem(v221);
    v36 = *(_QWORD *)System + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v216 = *(_QWORD *)(*(_QWORD *)(v36 + 8) + 128LL);
    UpdateRelatedActivityId = UpdateDatabase::GetUpdateRelatedActivityId(*v28, v230, *v8);
    v38 = (_QWORD *)SystemInterface::Providers::GetSystem(v206);
    v39 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v38 + 40LL))(*v38, v229);
    LOBYTE(v40) = 1;
    v41 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64))(*(_QWORD *)*v39 + 448LL))(*v39, v220, v40);
    v42 = (_QWORD *)std::optional<std::wstring>::value_or<std::wstring>(UpdateRelatedActivityId, &v200, v41);
    v43 = v42[2];
    if ( v42[3] > 7u )
      v42 = (_QWORD *)*v42;
    v211.m128i_i64[0] = (__int64)v42;
    v211.m128i_i64[1] = v43;
    v203 = v211;
    v212 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v205);
    v44 = ((__int64 (__fastcall *)(__int64, __int128 *, __int128 *, __m128i *))v216)(v36 + 8, &v210, &v212, &v203);
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v223, v44);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v210);
    std::wstring::~wstring(&v200, v45);
    std::wstring::~wstring(v220, v46);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v229);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v206);
    if ( LOBYTE(v231[0]) )
      std::wstring::~wstring(v230, v47);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v221);
    v34 = _mm_load_si128(&v223);
  }
  UpdateDatabase::ReleaseUpdateActionTags(*v28, v259, *v8);
  v48 = *v218;
  v200 = 0;
  v201 = 0;
  v202 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v200, L"Performance", 11);
  v49 = 48;
  v207 = 48;
  LODWORD(v199) = 48;
  v203 = *(__m128i *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v212, L"Update deferral mode");
  DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
    v48,
    (unsigned int)v258,
    (unsigned int)&v203,
    (unsigned int)v236,
    (__int64)&v200);
  std::wstring::~wstring(&v200, v50);
  v252 = 0;
  v51 = (_QWORD *)SystemInterface::Providers::GetSystem(&v205);
  v221[0] = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*v51 + 40LL))(*v51, v220);
  v206[0] = *(_QWORD *)(*(_QWORD *)v221[0] + 152LL);
  v229[0] = &v211;
  v211 = 0;
  v52 = _mm_srli_si128(v34, 8).m128i_u64[0];
  v216 = v52;
  if ( v52 )
    _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
  v211 = v34;
  DiscoveryTime = UpdateDatabase::GetDiscoveryTime(*v28, &v210, *v8);
  v53 = v259;
  if ( v259[3] > 7u )
    v53 = (_QWORD *)v259[0];
  *(_QWORD *)&v212 = v53;
  *((_QWORD *)&v212 + 1) = v259[2];
  v54 = (_BYTE)v249 != 0 ? v248 : 0;
  v227 = v253;
  v55 = v258;
  if ( v258[3] > 7u )
    v55 = (_QWORD *)v258[0];
  v203.m128i_i64[0] = (__int64)v55;
  v203.m128i_i64[1] = v258[2];
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 128LL))(*a4) )
  {
    v56 = (_QWORD *)SystemInterface::Service::GetSystem(&v219);
    LODWORD(v199) = 49;
    v57 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v56 + 72LL))(*v56, v228);
    v49 = 51;
    v207 = 51;
    LODWORD(v199) = 51;
    v58 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v57 + 256LL))(*v57, &v200);
  }
  else
  {
    LOBYTE(v249) = 0;
    v58 = &v248;
  }
  v59 = *v58;
  v60 = *((_QWORD *)v58 + 2);
  IsApproved = UpdateDatabase::IsApproved(*v28, *v8);
  v248 = v59;
  v249 = v60;
  LOBYTE(v196) = IsApproved;
  ((void (__fastcall *)(_QWORD, __int128 *, const struct Update **, _QWORD, int, _DWORD, __int128 *, __m128i *, const struct Update *, int, __int128 *, __int64, __m128i *))v206[0])(
    v221[0],
    &v252,
    v8,
    *a4,
    v196,
    v204[0],
    &v248,
    &v203,
    v227,
    v54,
    &v212,
    DiscoveryTime,
    &v211);
  if ( (v49 & 2) != 0 )
  {
    v49 &= ~2u;
    v207 = v49;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v228);
  }
  if ( (v49 & 1) != 0 )
  {
    v207 = v49 & 0xFFFFFFFE;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v219);
  }
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v220);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v205);
  UpdateDatabase::SetUpdateLastAttemptTime(*v28, *v8);
  v62 = 0;
  DiscoveryTime = 0;
  if ( UpdateDatabase::IsOobeApproved(*v28, *v8)
    || (*(unsigned __int8 (__fastcall **)(const struct Update *))(*(_QWORD *)*v8 + 408LL))(*v8) )
  {
    v63 = (_QWORD *)SystemInterface::Providers::GetSystem(v220);
    v64 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v63 + 40LL))(*v63, &v205);
    v65 = *(_QWORD *)v64;
    v66 = *(__int64 (__fastcall **)(__int64, _QWORD *, const struct Update **, _QWORD, int, _DWORD, const struct Update *))(**(_QWORD **)v64 + 160LL);
    v67 = v253;
    LOBYTE(v197) = UpdateDatabase::IsApproved(*v28, *v8);
    v68 = (__int64 *)v66(v65, v206, v8, *v209, v197, v204[0], v67);
    v62 = *v68;
    *v68 = 0;
    DiscoveryTime = v62;
    if ( v206[0] )
      (**(void (__fastcall ***)(_QWORD, __int64))v206[0])(v206[0], 1);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v205);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v220);
  }
  v69 = *v218;
  LODWORD(v199) = 10;
  v205 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                      v220,
                      L"Max action attempts per unit time");
  LODWORD(v69) = DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<int>(
                   v69,
                   &v205,
                   v236,
                   &v199);
  v70 = *v8;
  v71 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v209 + 8LL))(*v209, &v200);
  Update::AddActionAttempt(v70, v71, (unsigned int)v69);
  std::wstring::~wstring(&v200, v72);
  UpdateDatabase::SetUpdateActionAttempts(*v28, *v8);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::GetImpl'::`2'::impl) )
  {
    v199 = 0;
    web::json::value::object(&v199);
    v73 = std::wstring::wstring(&v248, v259);
    v74 = (__int64 *)web::json::value::string(v206, v73);
    v200 = 0;
    v201 = 0;
    v202 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v200, L"Tags", 4);
    v75 = (__int64 *)web::json::value::operator[](&v199, &v200);
    if ( v75 != v74 )
    {
      v76 = *v75;
      *v75 = *v74;
      *v74 = v76;
    }
    std::wstring::~wstring(&v200, v76);
    if ( v206[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v206[0] + 192LL))(v206[0], 1);
    v77 = std::wstring::wstring(&v248, v258);
    v78 = (__int64 *)web::json::value::string(v206, v77);
    v200 = 0;
    v201 = 0;
    v202 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v200, L"DeferralMode", 12);
    v79 = (__int64 *)web::json::value::operator[](&v199, &v200);
    if ( v79 != v78 )
    {
      v80 = *v79;
      *v79 = *v78;
      *v78 = v80;
    }
    std::wstring::~wstring(&v200, v80);
    if ( v206[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v206[0] + 192LL))(v206[0], 1);
    v81 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v252 + 32LL))(v252, &v248);
    v82 = (__int64 *)web::json::value::string(v206, v81);
    v200 = 0;
    v201 = 0;
    v202 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v200, L"AID", 3);
    v83 = (__int64 *)web::json::value::operator[](&v199, &v200);
    if ( v83 != v82 )
    {
      v84 = *v83;
      *v83 = *v82;
      *v82 = v84;
    }
    std::wstring::~wstring(&v200, v84);
    if ( v206[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v206[0] + 192LL))(v206[0], 1);
    if ( v34.m128i_i64[0] )
    {
      v85 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v34.m128i_i64[0] + 16LL))(
              v34.m128i_i64[0],
              &v248);
      v86 = (__int64 *)web::json::value::string(v206, v85);
      v200 = 0;
      v201 = 0;
      v202 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v200, L"RAID", 4);
      v87 = (__int64 *)web::json::value::operator[](&v199, &v200);
      if ( v87 != v86 )
      {
        v88 = *v87;
        *v87 = *v86;
        *v86 = v88;
      }
      std::wstring::~wstring(&v200, v88);
      if ( v206[0] )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v206[0] + 192LL))(v206[0], 1);
    }
    v89 = *v28;
    v90 = v209;
    v91 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v209 + 8LL))(*v209, &v200);
    v92 = v91[2];
    if ( v91[3] > 7u )
      v91 = (_QWORD *)*v91;
    v203.m128i_i64[0] = (__int64)v91;
    v203.m128i_i64[1] = v92;
    v205 = (__int128)v203;
    UpdateDatabase::UpdateActionAttemptDiagnostic(v89, *v8);
    std::wstring::~wstring(&v200, v93);
    if ( v199 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v199 + 192LL))(v199, 1);
  }
  else
  {
    v90 = v209;
  }
  memset(v232, 0, sizeof(v232));
  v94 = 0u;
  if ( *((_QWORD *)&v252 + 1) )
  {
    v94 = v252;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v252 + 1) + 12LL));
  }
  v95 = (volatile signed __int32 *)*((_QWORD *)&v224 + 1);
  v96 = 0u;
  if ( *((_QWORD *)&v224 + 1) )
  {
    v96 = v224;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v224 + 1) + 12LL));
  }
  v97 = 0;
  v98 = 0;
  if ( v27 )
  {
    v97 = v222;
    v98 = v27;
    _InterlockedIncrement(v27 + 3);
  }
  v99 = v213;
  *(_QWORD *)&v232[0] = v213;
  v100 = v8[1];
  if ( v100 )
    _InterlockedIncrement((volatile signed __int32 *)v100 + 2);
  *((_QWORD *)&v232[0] + 1) = *v8;
  *(_QWORD *)&v232[1] = v8[1];
  v101 = v90[1];
  if ( v101 )
    _InterlockedIncrement((volatile signed __int32 *)(v101 + 8));
  *((_QWORD *)&v232[1] + 1) = *v90;
  *(_QWORD *)&v232[2] = v90[1];
  *(_OWORD *)((char *)&v232[2] + 8) = v94;
  *((_QWORD *)&v232[3] + 1) = a5;
  v232[4] = __PAIR128__(a7, a6);
  v232[5] = v96;
  *(_QWORD *)&v232[6] = v97;
  *((_QWORD *)&v232[6] + 1) = v98;
  UpdateDatabase::SetWorkBit(*v214, *v8, 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateStateDiagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateStateDiagnostics>::GetImpl'::`2'::impl) )
  {
    v102 = *(RTL_SRWLOCK **)(v99 + 48);
    v210 = 0;
    v103 = v8[1];
    if ( v103 )
      _InterlockedIncrement((volatile signed __int32 *)v103 + 2);
    v210 = *(_OWORD *)v8;
    CallbackManager::UpdateActionStarted(v102);
  }
  v104 = *v218;
  LODWORD(v199) = 720;
  v260 = 0;
  v261 = 0;
  v262 = *v90;
  v263 = 0;
  v105 = *(_QWORD *)(v213 + 776);
  v106 = (*(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)*v8 + 8LL))(*v8, &v200);
  v264 = *(_QWORD *)ScanManager::GetProvider(v105, &v248, v106);
  v265 = 0;
  v266 = 0;
  std::set<std::wstring>::set<std::wstring>(v267);
  v268 = 0;
  v269 = 0;
  v270 = 0;
  std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v271);
  std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v272);
  std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(v273);
  v205 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                      v220,
                      L"Update action timeout in minutes");
  v107 = DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<int>(v104, &v205, &v260, &v199);
  LODWORD(v199) = v107;
  SystemInterface::Providers::ConditionContext::~ConditionContext((SystemInterface::Providers::ConditionContext *)&v260);
  ActionState::~ActionState((ActionState *)&v248);
  v211 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl) )
  {
    v108 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl'::`2'::impl);
    v109 = *v8;
    v12 = v108 == 0;
    v110 = *(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)*v8 + 24LL);
    if ( v12 )
    {
      v114 = v110(v109, &v200);
      v113 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<60,1>> const &,wchar_t const (&)[14],std::wstring>(
               &v205,
               &v199,
               v115,
               v114);
    }
    else
    {
      v198[0] = 1;
      v111 = v110(v109, &v200);
      v113 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<60,1>> const &,wchar_t const (&)[14],std::wstring,bool>(
               (unsigned int)&v205,
               (unsigned int)&v199,
               v112,
               v111,
               (__int64)v198);
    }
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v211, v113);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v205);
    std::wstring::~wstring(&v200, v116);
  }
  else
  {
    v117 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl'::`2'::impl);
    v118 = *v8;
    v12 = v117 == 0;
    *(_QWORD *)&v210 = &v248;
    v119 = *(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)v118 + 24LL);
    if ( v12 )
    {
      v121 = v119(v118, &v248);
      v200 = 0;
      v201 = 0;
      v202 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v200, L"Action Global", 13);
      Threads::Watchdog::Watchdog(&v260, v107, &v200, v121);
    }
    else
    {
      v120 = v119(v118, &v248);
      v200 = 0;
      v201 = 0;
      v202 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v200, L"Action Global", 13);
      Threads::Watchdog::Watchdog((unsigned int)&v260, v107, (unsigned int)&v200, v120, 1);
    }
    watchdog_timer::~watchdog_timer((watchdog_timer *)&v260);
  }
  v122 = v208;
  v221[0] = v208 + 6;
  *((_BYTE *)v208 + 24) = 0;
  v123 = v207 | 4;
  LODWORD(v199) = v207 | 4;
  try
  {
    (*(void (**)(void))(*(_QWORD *)*v8 + 344LL))();
    v206[0] = *v8;
    v235 = 0;
    v124 = operator new(0x78u);
    *v124 = &off_1403C6B00;
    UpdateManager::PerformAction_::_2_::_lambda_2_::_lambda_2_(v124 + 1, v232);
    v235 = v125;
    v126 = Update::PerformAction(v206[0], (unsigned int)&v200, *v209, (unsigned int)v234, (__int64)&v253);
    std::optional<ActionResult>::operator=(v122, v126);
    std::_Optional_construct_base<ActionResult>::~_Optional_construct_base<ActionResult>(&v200);
    v128 = v235;
    if ( v235 )
    {
      LOBYTE(v127) = v235 != (wil *)v234;
      (*(void (__fastcall **)(wil *, __int64))(*(_QWORD *)v235 + 32LL))(v235, v127);
    }
  }
  catch ( const std::exception *v233 )
  {
    v191 = SystemInterface::Providers::GetSystem(&v219);
    v192 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v191 + 8LL) + 4LL)
                                                                    + *(_QWORD *)v191
                                                                    + 8LL)
                                                        + 104LL))(
             *(_QWORD *)v191 + *(int *)(*(_QWORD *)(*(_QWORD *)v191 + 8LL) + 4LL) + 8LL,
             v220);
    v193 = *(_QWORD *)v192;
    v194 = *(void (__fastcall **)(__int64, __int128 *, const std::exception *))(**(_QWORD **)v192 + 264LL);
    v205 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v228, L"Action");
    v194(v193, &v205, v233);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v220);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v219);
    *(_QWORD *)&v205 = (unsigned int)wil::ResultFromCaughtException(v195);
    std::set<enum UMAction>::set<enum UMAction>((char *)&v205 + 8);
    std::optional<ActionResult>::optional<ActionResult>(&v200, &v205);
    std::optional<ActionResult>::operator=(v217, &v200);
    std::_Optional_construct_base<ActionResult>::~_Optional_construct_base<ActionResult>(&v200);
    ActionResult::~ActionResult((ActionResult *)&v205);
    v216 = v223.m128i_i64[1];
    v213 = v225;
    v8 = v226;
    v208 = v217;
    v123 = v199;
    v62 = DiscoveryTime;
    v27 = (volatile signed __int32 *)*((_QWORD *)&v222 + 1);
    v95 = (volatile signed __int32 *)*((_QWORD *)&v224 + 1);
  }
  catch ( ... )
  {
    *(_QWORD *)&v205 = (unsigned int)wil::ResultFromCaughtException(v128);
    std::set<enum UMAction>::set<enum UMAction>((char *)&v205 + 8);
    std::optional<ActionResult>::optional<ActionResult>(&v200, &v205);
    std::optional<ActionResult>::operator=(v217, &v200);
    std::_Optional_construct_base<ActionResult>::~_Optional_construct_base<ActionResult>(&v200);
    ActionResult::~ActionResult((ActionResult *)&v205);
    v216 = v223.m128i_i64[1];
    v213 = v225;
    v8 = v226;
    v208 = v217;
    v123 = v199;
    v62 = DiscoveryTime;
    v27 = (volatile signed __int32 *)*((_QWORD *)&v222 + 1);
    v95 = (volatile signed __int32 *)*((_QWORD *)&v224 + 1);
  }
  v129 = v214;
  UpdateDatabase::UpdateUpdate(*v214, *v8);
  UpdateDatabase::SetWorkBit(*v129, *v8, 0);
  if ( *(_BYTE *)v221[0] )
  {
    v130 = (_QWORD *)**((_QWORD **)v208 + 1);
    while ( 1 )
    {
      v209 = v130;
      if ( *((_BYTE *)v130 + 25) )
        break;
      try
      {
        UpdateManager::RunFollowupAction(v213, *((unsigned int *)v130 + 7), *v8, &v253);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x632,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\UpdateManager.cpp",
          v131);
        v95 = (volatile signed __int32 *)*((_QWORD *)&v224 + 1);
        v27 = (volatile signed __int32 *)*((_QWORD *)&v222 + 1);
        v216 = v223.m128i_i64[1];
        v62 = DiscoveryTime;
        v130 = v209;
        v123 = v199;
        v213 = v225;
        v208 = v217;
        v8 = v226;
      }
      v132 = (__int64 *)v130[2];
      if ( *((_BYTE *)v132 + 25) )
      {
        for ( i = v130[1]; !*(_BYTE *)(i + 25) && v130 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v130 = (_QWORD *)i;
        v130 = (_QWORD *)i;
      }
      else
      {
        do
        {
          v130 = v132;
          v132 = (__int64 *)*v132;
        }
        while ( !*((_BYTE *)v132 + 25) );
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
    {
      v134 = *v218;
      v200 = 0;
      v201 = 0;
      v202 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v200, L"Performance", 11);
      LODWORD(v199) = v123 | 8;
      traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                             L"Update deferral mode",
                                             word_140400DFA,
                                             0);
      if ( traits_2_unsigned_short == word_140400DFA
        || (v138 = ((__int64)traits_2_unsigned_short - v137) >> 1, v138 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v136);
      }
      v203.m128i_i64[0] = v137;
      v203.m128i_i64[1] = v138;
      v205 = (__int128)v203;
      DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
        v134,
        (unsigned int)&v248,
        (unsigned int)&v205,
        (unsigned int)v236,
        (__int64)&v200);
      std::wstring::~wstring(&v200, v139);
      v206[0] = v252;
      v221[0] = *(_QWORD *)(*(_QWORD *)v252 + 16LL);
      v140 = &v248;
      if ( v250 > 7 )
        v140 = (__int128 *)v248;
      v203.m128i_i64[0] = (__int64)v140;
      v203.m128i_i64[1] = v249;
      updated = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v214, &v200, *v8);
      v142 = updated[2];
      if ( updated[3] > 7u )
        updated = (_QWORD *)*updated;
      *(_QWORD *)&v212 = updated;
      *((_QWORD *)&v212 + 1) = v142;
      v143 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
               L"Completed",
               &dword_1403FE374,
               0);
      if ( v143 == v145 || (v146 = (v143 - (__int64)L"Completed") >> 1, v146 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v144);
      *(_QWORD *)&v210 = L"Completed";
      *((_QWORD *)&v210 + 1) = v146;
      v205 = (__int128)v203;
      v220[0] = v212;
      v219 = v210;
      ((void (__fastcall *)(_QWORD, _QWORD, __int128 *, _OWORD *, __int128 *))v221[0])(
        v206[0],
        *v208,
        &v219,
        v220,
        &v205);
      std::wstring::~wstring(&v200, v147);
      std::wstring::~wstring(&v248, v148);
    }
    else
    {
      v149 = v252;
      v150 = *(void (__fastcall **)(__int64, _QWORD, __int128 *, _OWORD *, __int128 *))(*(_QWORD *)v252 + 16LL);
      v151 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v228);
      v152 = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v214, &v200, *v8);
      v153 = v152[2];
      if ( v152[3] > 7u )
        v152 = (_QWORD *)*v152;
      v203.m128i_i64[0] = (__int64)v152;
      v203.m128i_i64[1] = v153;
      v154 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v212, L"Completed");
      v205 = v151;
      v220[0] = v203;
      v219 = *v154;
      v150(v149, *v208, &v219, v220, &v205);
      std::wstring::~wstring(&v200, v155);
    }
    if ( v62 )
    {
      v156 = *(void (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v62 + 8LL);
      v205 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v220, L"Completed");
      v156(v62, *v208, &v205);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
    {
      v157 = *v218;
      v200 = 0;
      v201 = 0;
      v202 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v200, L"Performance", 11);
      LODWORD(v199) = v123 | 0x40;
      v205 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v220, L"Update deferral mode");
      DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
        v157,
        (unsigned int)&v248,
        (unsigned int)&v205,
        (unsigned int)v236,
        (__int64)&v200);
      std::wstring::~wstring(&v200, v158);
      v159 = v252;
      v160 = *(void (__fastcall **)(__int64, __int128 *, _OWORD *, __int128 *))(*(_QWORD *)v252 + 24LL);
      v161 = &v248;
      if ( v250 > 7 )
        v161 = (__int128 *)v248;
      v203.m128i_i64[0] = (__int64)v161;
      v203.m128i_i64[1] = v249;
      v162 = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v214, &v200, *v8);
      v163 = v162[2];
      if ( v162[3] > 7u )
        v162 = (_QWORD *)*v162;
      *(_QWORD *)&v212 = v162;
      *((_QWORD *)&v212 + 1) = v163;
      v205 = (__int128)v203;
      v220[0] = v212;
      v219 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v228, L"Aborted");
      v160(v159, &v219, v220, &v205);
      std::wstring::~wstring(&v200, v164);
      v166 = &v248;
    }
    else
    {
      v167 = v252;
      v206[0] = *(_QWORD *)(*(_QWORD *)v252 + 24LL);
      v168 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v228);
      v169 = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v129, &v200, *v8);
      v170 = v169[2];
      if ( v169[3] > 7u )
        v169 = (_QWORD *)*v169;
      v203.m128i_i64[0] = (__int64)v169;
      v203.m128i_i64[1] = v170;
      v205 = v168;
      v220[0] = v203;
      v219 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v212, L"Aborted");
      ((void (__fastcall *)(__int64, __int128 *, _OWORD *, __int128 *))v206[0])(v167, &v219, v220, &v205);
      v166 = &v200;
    }
    std::wstring::~wstring(v166, v165);
    if ( v62 )
    {
      v171 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v62 + 16LL);
      v205 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v220, L"Aborted");
      v171(v62, &v205);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    v206[0] = *v214;
    v221[0] = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v252 + 32LL))(v252, &v200);
    v227 = *v8;
    InitOnceExecuteOnce(
      &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
      `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1EFB,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\Staging.h",
        v172);
    }
    v173 = *(_QWORD *)v206[0];
    v174 = *(void (__fastcall **)(__int64, __int64, __int128 *, __int128 *))(**(_QWORD **)v206[0] + 136LL);
    std::wstring::wstring(&v248, v221[0]);
    v251 = 4;
    v175 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
             L"UpdateRelatedActivityId",
             L"UpdateGroup",
             0);
    if ( v175 == v177 || (v178 = (v175 - (__int64)L"UpdateRelatedActivityId") >> 1, v178 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v176);
    v203.m128i_i64[0] = (__int64)L"UpdateRelatedActivityId";
    v203.m128i_i64[1] = v178;
    PrimaryKey = UpdateDatabase::GetPrimaryKey(v230, v227);
    v205 = (__int128)v203;
    v174(v173, PrimaryKey, &v205, &v248);
    std::wstring::~wstring(v231, v180);
    std::wstring::~wstring(v230, v181);
    if ( v251 != -1 && v251 && v251 != 1 && v251 != 2 && v251 != 3 )
      std::wstring::~wstring(&v248, v182);
    std::wstring::~wstring(&v200, v182);
  }
  v183 = (volatile signed __int32 *)v211.m128i_i64[1];
  if ( v211.m128i_i64[1] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v211.m128i_i64[1] + 8)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v183)(v183);
      if ( !_InterlockedDecrement(v183 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v183 + 8LL))(v183);
    }
  }
  UpdateManager::PerformAction_::_2_::_lambda_2_::__lambda_2_(v232);
  if ( v62 )
    (**(void (__fastcall ***)(__int64, __int64))v62)(v62, 1);
  v185 = (volatile signed __int32 *)*((_QWORD *)&v252 + 1);
  if ( *((_QWORD *)&v252 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v252 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v185)(v185);
      if ( _InterlockedExchangeAdd(v185 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v185 + 8LL))(v185);
    }
  }
  std::wstring::~wstring(v258, v184);
  std::wstring::~wstring(v259, v186);
  v188 = (volatile signed __int32 *)v216;
  if ( v216 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v216 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v188)(v188);
      if ( _InterlockedExchangeAdd(v188 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v188 + 8LL))(v188);
    }
  }
  std::wstring::~wstring(&v255, v187);
  v189 = v254;
  if ( v254 )
  {
    if ( _InterlockedExchangeAdd(v254 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v189)(v189);
      if ( _InterlockedExchangeAdd(v189 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v189 + 8LL))(v189);
    }
  }
  SystemInterface::Providers::ConditionContext::~ConditionContext((SystemInterface::Providers::ConditionContext *)v236);
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  if ( v95 )
  {
    if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
      if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
    }
  }
  return v208;
}

```

## disassembly

```asm
0x140085f54  mov     rax, rsp
0x140085f57  push    rbx
0x140085f58  push    rsi
0x140085f59  push    rdi
0x140085f5a  push    r12
0x140085f5c  push    r13
0x140085f5e  push    r14
0x140085f60  push    r15
0x140085f62  sub     rsp, 760h
0x140085f69  movaps  xmmword ptr [rax-48h], xmm6
0x140085f6d  movaps  xmmword ptr [rax-58h], xmm7
0x140085f71  movaps  xmmword ptr [rax-68h], xmm8
0x140085f76  movaps  xmmword ptr [rax-78h], xmm9
0x140085f7b  mov     rax, cs:__security_cookie
0x140085f82  xor     rax, rsp
0x140085f85  mov     [rsp+798h+var_88], rax
0x140085f8d  mov     rsi, r9
0x140085f90  mov     [rsp+798h+var_698], r9
0x140085f98  mov     r15, r8
0x140085f9b  mov     [rsp+798h+var_6A0], rdx
0x140085fa3  mov     rbx, rcx
0x140085fa6  mov     [rsp+798h+var_658], rcx
0x140085fae  mov     [rsp+798h+var_5B8], rcx
0x140085fb6  mov     [rsp+798h+var_638], rdx
0x140085fbe  mov     [rsp+798h+var_5B0], r8
0x140085fc6  xor     r14d, r14d
0x140085fc9  mov     dword ptr [rsp+798h+var_720], r14d
0x140085fce  xorps   xmm1, xmm1
0x140085fd1  movdqu  [rsp+798h+var_5C8], xmm1
0x140085fda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl(void)'::`2'::impl
0x140085fe1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(void)
0x140085fe6  mov     rcx, [r15]
0x140085fe9  lea     rdx, [rsp+798h+var_718]
0x140085ff1  test    al, al
0x140085ff3  mov     rax, [rcx]
0x140085ff6  mov     rax, [rax+18h]
0x140085ffa  jz      short loc_140086054
0x140085ffc  mov     [rsp+798h+var_728], 1
0x140086001  call    _guard_dispatch_icall
0x140086006  nop
0x140086007  mov     [rsp+798h+var_6E8], 0Ch
0x140086012  lea     rcx, [rsp+798h+var_728]
0x140086017  mov     [rsp+798h+var_778], rcx
0x14008601c  mov     r9, rax
0x14008601f  lea     rdx, [rsp+798h+var_6E8]
0x140086027  lea     rcx, [rsp+798h+var_6F8]
0x14008602f  call    ??$make_shared@UWatchdog@Threads@@V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@AEAY0BA@$$CB_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@_N@std@@YA?AV?$shared_ptr@UWatchdog@Threads@@@0@$$QEAV?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@0@AEAY0BA@$$CB_W$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEA_N@Z; std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<3600,1>>,wchar_t const (&)[16],std::wstring,bool>(std::chrono::duration<int,std::ratio<3600,1>> &&,wchar_t const (&)[16],std::wstring &&,bool &&)
0x140086034  mov     rdx, rax
0x140086037  lea     rcx, [rsp+798h+var_5C8]
0x14008603f  call    ??4?$shared_ptr@$$CBU_EXCEPTION_RECORD@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_EXCEPTION_RECORD const>::operator=(std::shared_ptr<_EXCEPTION_RECORD const> &&)
0x140086044  lea     rcx, [rsp+798h+var_6F8]; void *
0x14008604c  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140086051  nop
0x140086052  jmp     short loc_14008609B
0x140086054  call    _guard_dispatch_icall
0x140086059  nop
0x14008605a  mov     [rsp+798h+var_6E8], 0Ch
0x140086065  mov     r9, rax
0x140086068  lea     rdx, [rsp+798h+var_6E8]
0x140086070  lea     rcx, [rsp+798h+var_6F8]
0x140086078  call    ??$make_shared@UWatchdog@Threads@@V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@AEAY0BA@$$CB_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@std@@YA?AV?$shared_ptr@UWatchdog@Threads@@@0@$$QEAV?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@0@AEAY0BA@$$CB_W$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<3600,1>>,wchar_t const (&)[16],std::wstring>(std::chrono::duration<int,std::ratio<3600,1>> &&,wchar_t const (&)[16],std::wstring &&)
0x14008607d  mov     rdx, rax
0x140086080  lea     rcx, [rsp+798h+var_5C8]
0x140086088  call    ??4?$shared_ptr@$$CBU_EXCEPTION_RECORD@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_EXCEPTION_RECORD const>::operator=(std::shared_ptr<_EXCEPTION_RECORD const> &&)
0x14008608d  lea     rcx, [rsp+798h+var_6F8]; void *
0x140086095  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x14008609a  nop
0x14008609b  lea     rcx, [rsp+798h+var_718]
0x1400860a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400860a8  xorps   xmm1, xmm1
0x1400860ab  movdqu  [rsp+798h+var_5E8], xmm1
0x1400860b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks> `wil::Feature<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks>::GetImpl(void)'::`2'::impl
0x1400860bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks>::__private_IsEnabled(void)
0x1400860c0  test    al, al
0x1400860c2  jz      loc_1400861F0
0x1400860c8  xorps   xmm0, xmm0
0x1400860cb  movups  [rsp+798h+var_678], xmm0
0x1400860d3  lea     rdx, [rsp+798h+var_678]
0x1400860db  mov     rcx, rbx
0x1400860de  call    ?GetUxBroker@UpdateManager@@QEAA?AV?$shared_ptr@VBroker@UX@@@std@@XZ; UpdateManager::GetUxBroker(void)
0x1400860e3  nop
0x1400860e4  cmp     qword ptr [rsp+798h+var_678], r14
0x1400860ec  jz      loc_1400861D9
0x1400860f2  mov     [rsp+798h+var_728], 1
0x1400860f7  mov     [rsp+798h+var_578], rbx
0x1400860ff  mov     rax, [r15+8]
0x140086103  test    rax, rax
0x140086106  jz      short loc_14008610C
0x140086108  lock inc dword ptr [rax+8]
0x14008610c  mov     rax, [r15]
0x14008610f  mov     [rsp+798h+var_570], rax
0x140086117  mov     rax, [r15+8]
0x14008611b  mov     [rsp+798h+var_568], rax
0x140086123  mov     rax, [rsi+8]
0x140086127  test    rax, rax
0x14008612a  jz      short loc_140086130
0x14008612c  lock inc dword ptr [rax+8]
0x140086130  mov     rax, [rsi]
0x140086133  mov     [rsp+798h+var_560], rax
0x14008613b  mov     rax, [rsi+8]
0x14008613f  mov     [rsp+798h+var_558], rax
0x140086147  mov     rax, [rsp+798h+arg_30]
0x14008614f  mov     [rsp+798h+var_550], rax
0x140086157  lea     rdx, [rsp+798h+var_6B8]
0x14008615f  call    ?MinProgressFrequency@Broker@UX@@QEBA?AV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@XZ; UX::Broker::MinProgressFrequency(void)
0x140086164  lea     r9, [rsp+798h+var_728]
0x140086169  lea     r8, [rsp+798h+var_578]
0x140086171  mov     rdx, rax
0x140086174  lea     rcx, [rsp+798h+var_6F8]
0x14008617c  call    std__make_shared_watchdog_timer_std__chrono__duration___int64_std__ratio_1_1_____UpdateManager__PerformAction____13____lambda_1__bool_
0x140086181  mov     rcx, [rax]
0x140086184  mov     r13, [rax+8]
0x140086188  mov     [rax], r14
0x14008618b  mov     [rax+8], r14
0x14008618f  mov     qword ptr [rsp+798h+var_5D8], r14
0x140086197  mov     qword ptr [rsp+798h+var_5E8], rcx
0x14008619f  mov     qword ptr [rsp+798h+var_5D8+8], r14
0x1400861a7  mov     qword ptr [rsp+798h+var_5E8+8], r13
0x1400861af  lea     rcx, [rsp+798h+var_5D8]; void *
0x1400861b7  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x1400861bc  lea     rcx, [rsp+798h+var_6F8]; void *
0x1400861c4  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x1400861c9  nop
0x1400861ca  lea     rcx, [rsp+798h+var_578]
0x1400861d2  call    _UpdateManager__PerformAction____13____lambda_1_____lambda_1_
0x1400861d7  jmp     short loc_1400861E1
0x1400861d9  mov     r13, qword ptr [rsp+798h+var_5E8+8]
0x1400861e1  lea     rcx, [rsp+798h+var_678]; void *
0x1400861e9  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x1400861ee  jmp     short loc_1400861F8
0x1400861f0  mov     r13, qword ptr [rsp+798h+var_5E8+8]
0x1400861f8  mov     rax, [r15]
0x1400861fb  mov     [rsp+798h+var_478], rax
0x140086203  mov     [rsp+798h+var_470], r14
0x14008620b  lea     r12, [rbx+10h]
0x14008620f  mov     [rsp+798h+var_650], r12
0x140086217  mov     rax, [r12]
0x14008621b  mov     [rsp+798h+var_468], rax
0x140086223  mov     [rsp+798h+var_460], r14
0x14008622b  xorps   xmm0, xmm0
0x14008622e  movdqa  [rsp+798h+var_458], xmm0
0x140086237  mov     [rsp+798h+var_448], r14
0x14008623f  mov     [rsp+798h+var_428], r14b
0x140086247  mov     [rsp+798h+var_420], r14
0x14008624f  lea     rcx, [rsp+798h+var_418]
0x140086257  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x14008625c  nop
0x14008625d  xorps   xmm9, xmm9
0x140086261  movsd   [rsp+798h+var_408], xmm9
0x14008626b  mov     [rsp+798h+var_3D8], r14b
0x140086273  mov     [rsp+798h+var_3A0], r14b
0x14008627b  lea     rcx, [rsp+798h+var_398]
0x140086283  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(void)
0x140086288  nop
0x140086289  lea     rcx, [rsp+798h+var_358]
0x140086291  call    ??0?$unordered_map@_KV?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@std@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KV?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(void)
0x140086296  nop
0x140086297  lea     rcx, [rsp+798h+var_318]
0x14008629f  call    ??0?$unordered_map@_KV?$basic_zstring_view@_W@wil@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KV?$basic_zstring_view@_W@wil@@@std@@@4@@std@@QEAA@XZ; std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(void)
0x1400862a4  nop
0x1400862a5  lea     rax, [rbx+20h]
0x1400862a9  mov     [rsp+798h+var_630], rax
0x1400862b1  mov     rbx, [rax]
0x1400862b4  xorps   xmm0, xmm0
0x1400862b7  movups  [rsp+798h+var_718], xmm0
0x1400862bf  mov     [rsp+798h+var_708], r14
0x1400862c7  mov     [rsp+798h+var_700], r14
0x1400862cf  xor     r8d, r8d
0x1400862d2  lea     rdx, psz
0x1400862d9  lea     rcx, [rsp+798h+var_718]
0x1400862e1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400862e6  nop
0x1400862e7  lea     rdx, aUpdatePriority; "Update priority"
0x1400862ee  lea     rcx, [rsp+798h+var_6D8]
0x1400862f6  call    ??$?0$0BA@@?$basic_zstring_view@_W@wil@@QEAA@AEAY0BA@$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[16])
0x1400862fb  movups  xmm0, xmmword ptr [rax]
0x1400862fe  movdqu  [rsp+798h+var_6F8], xmm0
0x140086307  lea     rax, [rsp+798h+var_718]
0x14008630f  mov     [rsp+798h+var_778], rax
0x140086314  lea     r9, [rsp+798h+var_478]
0x14008631c  lea     r8, [rsp+798h+var_6F8]
0x140086324  lea     rdx, [rsp+798h+var_2D8]
0x14008632c  mov     rcx, rbx
0x14008632f  call    ??$QueryOrDefault@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$DecisionEngine@VConditionContext@Providers@SystemInterface@@@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@AEBVConditionContext@Providers@SystemInterface@@AEBV12@_N@Z; DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(wil::basic_zstring_view<wchar_t>,SystemInterface::Providers::ConditionContext const &,std::wstring const &,bool)
0x140086334  lea     rdx, aLow; "Low"
0x14008633b  mov     rcx, rax
0x14008633e  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W@Z; std::operator==<wchar_t>(std::wstring const &,wchar_t const * const)
0x140086343  movzx   eax, al
0x140086346  mov     [rsp+798h+var_6E8], eax
0x14008634d  lea     rcx, [rsp+798h+var_2D8]
0x140086355  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008635a  nop
0x14008635b  lea     rcx, [rsp+798h+var_718]
0x140086363  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086368  mov     r8, [r15]
0x14008636b  lea     rdx, [rsp+798h+var_298]
0x140086373  mov     rcx, [r12]
0x140086377  call    ?GetAndIncrementCV@UpdateDatabase@@QEAA?AV?$shared_ptr@VCorrelationVector@Telemetry@SystemInterface@@@std@@AEBVUpdate@@@Z; UpdateDatabase::GetAndIncrementCV(Update const &)
0x14008637c  xorps   xmm0, xmm0
0x14008637f  movups  [rsp+798h+var_288], xmm0
0x140086387  mov     [rsp+798h+var_278], r14
0x14008638f  mov     [rsp+798h+var_270], 7
0x14008639b  mov     word ptr [rsp+798h+var_288], r14w
0x1400863a4  mov     r8, [r15]
0x1400863a7  lea     rdx, [rsp+798h+var_2D8]
0x1400863af  mov     rcx, [r12]
0x1400863b3  call    ?GetUpdateActionDelayDetails@UpdateDatabase@@QEBA?AV?$optional@U?$pair@IV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@@std@@AEBVUpdate@@@Z; UpdateDatabase::GetUpdateActionDelayDetails(Update const &)
0x1400863b8  xorps   xmm8, xmm8
0x1400863bc  movdqa  [rsp+798h+var_5D8], xmm8
0x1400863c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x1400863cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x1400863d2  test    al, al
0x1400863d4  jz      loc_14008656E
0x1400863da  lea     rcx, [rsp+798h+var_5F8]
0x1400863e2  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1400863e7  nop
0x1400863e8  mov     rdx, [rax]
0x1400863eb  mov     rax, [rdx+8]
0x1400863ef  movsxd  rdi, dword ptr [rax+4]
0x1400863f3  add     rdi, rdx
0x1400863f6  mov     rax, [rdi+8]
0x1400863fa  mov     rax, [rax+80h]
0x140086401  mov     [rsp+798h+var_640], rax
0x140086409  mov     r8, [r15]
0x14008640c  lea     rdx, [rsp+798h+var_578]
0x140086414  mov     rcx, [r12]
0x140086418  call    ?GetUpdateRelatedActivityId@UpdateDatabase@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBVUpdate@@@Z; UpdateDatabase::GetUpdateRelatedActivityId(Update const &)
0x14008641d  mov     rbx, rax
0x140086420  lea     rcx, [rsp+798h+var_6B8]
0x140086428  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14008642d  nop
0x14008642e  mov     rcx, [rax]
0x140086431  mov     rdx, [rcx]
0x140086434  mov     rax, [rdx+28h]
0x140086438  lea     rdx, [rsp+798h+var_590]
0x140086440  call    _guard_dispatch_icall
0x140086445  nop
0x140086446  mov     rcx, [rax]
0x140086449  mov     rax, [rcx]
0x14008644c  mov     r8b, 1
0x14008644f  lea     rdx, [rsp+798h+var_618]
0x140086457  mov     rax, [rax+1C0h]
0x14008645e  call    _guard_dispatch_icall
0x140086463  nop
0x140086464  mov     r8, rax
0x140086467  lea     rdx, [rsp+798h+var_718]
0x14008646f  mov     rcx, rbx
0x140086472  call    ??$value_or@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::optional<std::wstring>::value_or<std::wstring>(std::wstring &&)
0x140086477  nop
0x140086478  mov     rcx, [rax+10h]
0x14008647c  cmp     qword ptr [rax+18h], 7
0x140086481  jbe     short loc_140086486
0x140086483  mov     rax, [rax]
0x140086486  mov     qword ptr [rsp+798h+var_678], rax
0x14008648e  mov     qword ptr [rsp+798h+var_678+8], rcx
0x140086496  movaps  xmm0, [rsp+798h+var_678]
0x14008649e  movdqa  [rsp+798h+var_6F8], xmm0
0x1400864a7  lea     rcx, [rsp+798h+var_6D8]
0x1400864af  call    ??$?0$00@?$basic_zstring_view@_W@wil@@QEAA@AEAY00$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[1])
0x1400864b4  movups  xmm0, xmmword ptr [rax]
0x1400864b7  movdqu  [rsp+798h+var_668], xmm0
0x1400864c0  lea     r9, [rsp+798h+var_6F8]
0x1400864c8  lea     r8, [rsp+798h+var_668]
0x1400864d0  lea     rdx, [rsp+798h+var_688]
0x1400864d8  lea     rcx, [rdi+8]
0x1400864dc  mov     rax, [rsp+798h+var_640]
0x1400864e4  call    _guard_dispatch_icall
0x1400864e9  mov     rdx, rax
0x1400864ec  lea     rcx, [rsp+798h+var_5D8]
0x1400864f4  call    ??4?$shared_ptr@$$CBU_EXCEPTION_RECORD@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_EXCEPTION_RECORD const>::operator=(std::shared_ptr<_EXCEPTION_RECORD const> &&)
0x1400864f9  lea     rcx, [rsp+798h+var_688]; void *
0x140086501  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140086506  nop
0x140086507  lea     rcx, [rsp+798h+var_718]
0x14008650f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086514  nop
0x140086515  lea     rcx, [rsp+798h+var_618]
0x14008651d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086522  nop
0x140086523  lea     rcx, [rsp+798h+var_590]; void *
0x14008652b  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140086530  nop
0x140086531  lea     rcx, [rsp+798h+var_6B8]; void *
0x140086539  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x14008653e  nop
0x14008653f  cmp     byte ptr [rsp+798h+var_558], r14b
0x140086547  jz      short loc_140086557
0x140086549  lea     rcx, [rsp+798h+var_578]
0x140086551  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086556  nop
0x140086557  lea     rcx, [rsp+798h+var_5F8]; void *
0x14008655f  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140086564  movdqa  xmm8, [rsp+798h+var_5D8]
0x14008656e  mov     r8, [r15]
0x140086571  lea     rdx, [rsp+798h+var_248]
0x140086579  mov     rcx, [r12]
0x14008657d  call    ?ReleaseUpdateActionTags@UpdateDatabase@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVUpdate@@@Z; UpdateDatabase::ReleaseUpdateActionTags(Update const &)
0x140086582  nop
0x140086583  mov     rbx, [rsp+798h+var_630]
0x14008658b  mov     rbx, [rbx]
  ... truncated ...
```
