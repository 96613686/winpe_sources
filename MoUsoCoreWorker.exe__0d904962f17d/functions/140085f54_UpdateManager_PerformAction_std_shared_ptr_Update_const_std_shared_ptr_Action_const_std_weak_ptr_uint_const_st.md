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
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rcx
  const struct Update *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 *v24; // rax
  __int64 v25; // rcx
  volatile signed __int32 *v26; // r13
  UpdateDatabase **v27; // r12
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // r8
  __m128i v31; // xmm8
  __int64 System; // rax
  __int64 v33; // rdi
  __int64 UpdateRelatedActivityId; // rbx
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // r8
  __int64 v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rbx
  int v43; // edi
  _QWORD *v44; // rax
  unsigned __int64 v45; // xmm1_8
  _QWORD *v46; // rcx
  int v47; // ebx
  _QWORD *v48; // rax
  _QWORD *v49; // rax
  _QWORD *v50; // rax
  __int128 *v51; // rax
  __int128 v52; // xmm7
  __int64 v53; // xmm6_8
  bool IsApproved; // al
  __int64 v55; // rdi
  _QWORD *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rsi
  __int64 (__fastcall *v59)(__int64, _QWORD *, const struct Update **, _QWORD, int, _DWORD, const struct Update *); // rdi
  const struct Update *v60; // rbx
  __int64 *v61; // rax
  __int64 v62; // rbx
  const struct Update *v63; // rsi
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 *v66; // rbx
  __int64 *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 *v70; // rbx
  __int64 *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 *v74; // rbx
  __int64 *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 *v78; // rbx
  __int64 *v79; // rax
  __int64 v80; // rdx
  UpdateDatabase *v81; // rsi
  _QWORD *v82; // rbx
  _QWORD *v83; // rax
  __int64 v84; // rcx
  __int128 v85; // kr30_16
  volatile signed __int32 *v86; // r12
  __int128 v87; // kr40_16
  __int64 v88; // r9
  volatile signed __int32 *v89; // rdx
  __int64 v90; // rsi
  const struct Update *v91; // rax
  __int64 v92; // rax
  RTL_SRWLOCK *v93; // rcx
  const struct Update *v94; // rax
  __int64 v95; // rsi
  __int64 v96; // rbx
  __int64 v97; // rax
  unsigned int v98; // ebx
  char v99; // al
  const struct Update *v100; // rcx
  __int64 (__fastcall *v101)(const struct Update *, __int128 *); // rax
  int v102; // eax
  int v103; // r8d
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // r8
  char v107; // al
  const struct Update *v108; // rcx
  __int64 (__fastcall *v109)(const struct Update *, __int128 *); // rax
  int v110; // esi
  __int64 v111; // rsi
  unsigned int *v112; // rbx
  int v113; // esi
  _QWORD *v114; // rax
  wil *v115; // r9
  __int64 v116; // rdx
  __int64 v117; // rdx
  wil *v118; // rcx
  UpdateDatabase **v119; // rbx
  _QWORD *v120; // rbx
  const char *v121; // r9
  __int64 *v122; // rax
  __int64 i; // rax
  __int64 v124; // rbx
  void *traits_2_unsigned_short; // rax
  const char *v126; // r9
  __int64 v127; // r11
  __int64 v128; // rax
  __int128 *v129; // rax
  _QWORD *updated; // rax
  __int64 v131; // rcx
  __int64 v132; // rax
  const char *v133; // r9
  __int64 v134; // r11
  __int64 v135; // rax
  __int64 v136; // rbx
  void (__fastcall *v137)(__int64, _QWORD, __int128 *, _OWORD *, __int128 *); // rsi
  __int128 v138; // xmm6
  _QWORD *v139; // rax
  __int64 v140; // rcx
  __int128 *v141; // rax
  void (__fastcall *v142)(__int64, _QWORD, __int128 *); // rbx
  __int64 v143; // rbx
  __int64 v144; // rbx
  void (__fastcall *v145)(__int64, __int128 *, _OWORD *, __int128 *); // rsi
  __int128 *v146; // rax
  _QWORD *v147; // rax
  __int64 v148; // rcx
  __int128 *v149; // rcx
  __int64 v150; // rsi
  __int128 v151; // xmm6
  _QWORD *v152; // rax
  __int64 v153; // rcx
  void (__fastcall *v154)(__int64, __int128 *); // rbx
  const char *v155; // r9
  __int64 v156; // rbx
  void (__fastcall *v157)(__int64, __int64, __int128 *, __int128 *); // r15
  __int64 v158; // rax
  const char *v159; // r9
  __int64 v160; // r11
  __int64 v161; // rax
  __int64 PrimaryKey; // rax
  volatile signed __int32 *v163; // rbx
  volatile signed __int32 *v164; // rbx
  volatile signed __int32 *v165; // rbx
  volatile signed __int32 *v166; // rbx
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rdi
  void (__fastcall *v171)(__int64, __int128 *, const std::exception *); // rbx
  wil *v172; // rcx
  int v173; // [rsp+20h] [rbp-778h]
  int v174; // [rsp+20h] [rbp-778h]
  char v175[8]; // [rsp+70h] [rbp-728h] BYREF
  __int64 v176; // [rsp+78h] [rbp-720h] BYREF
  __int128 v177; // [rsp+80h] [rbp-718h] BYREF
  __int64 v178; // [rsp+90h] [rbp-708h]
  __int64 v179; // [rsp+98h] [rbp-700h]
  __m128i v180; // [rsp+A0h] [rbp-6F8h] BYREF
  _DWORD v181[4]; // [rsp+B0h] [rbp-6E8h] BYREF
  __int128 v182; // [rsp+C0h] [rbp-6D8h] BYREF
  _QWORD v183[2]; // [rsp+E0h] [rbp-6B8h] BYREF
  unsigned int v184; // [rsp+F0h] [rbp-6A8h]
  unsigned int *v185; // [rsp+F8h] [rbp-6A0h]
  _QWORD *v186; // [rsp+100h] [rbp-698h]
  __int128 v187; // [rsp+110h] [rbp-688h] BYREF
  __m128i v188; // [rsp+120h] [rbp-678h] BYREF
  __int128 v189; // [rsp+130h] [rbp-668h] BYREF
  __int64 v190; // [rsp+140h] [rbp-658h]
  UpdateDatabase **v191; // [rsp+148h] [rbp-650h]
  __int64 DiscoveryTime; // [rsp+150h] [rbp-648h]
  __int64 v193; // [rsp+158h] [rbp-640h]
  unsigned int *v194; // [rsp+160h] [rbp-638h]
  __int64 *v195; // [rsp+168h] [rbp-630h]
  __int128 v196; // [rsp+170h] [rbp-628h] BYREF
  _OWORD v197[2]; // [rsp+180h] [rbp-618h] BYREF
  _QWORD v198[2]; // [rsp+1A0h] [rbp-5F8h] BYREF
  __int128 v199; // [rsp+1B0h] [rbp-5E8h]
  __m128i v200; // [rsp+1C0h] [rbp-5D8h] BYREF
  __int128 v201; // [rsp+1D0h] [rbp-5C8h] BYREF
  __int64 v202; // [rsp+1E0h] [rbp-5B8h]
  const struct Update **v203; // [rsp+1E8h] [rbp-5B0h]
  const struct Update *v204; // [rsp+1F0h] [rbp-5A8h]
  _BYTE v205[16]; // [rsp+1F8h] [rbp-5A0h] BYREF
  _QWORD v206[3]; // [rsp+208h] [rbp-590h] BYREF
  _QWORD v207[4]; // [rsp+220h] [rbp-578h] BYREF
  _QWORD v208[4]; // [rsp+240h] [rbp-558h] BYREF
  _OWORD v209[7]; // [rsp+260h] [rbp-538h] BYREF
  const std::exception *v210; // [rsp+2D0h] [rbp-4C8h] BYREF
  _BYTE v211[56]; // [rsp+2E0h] [rbp-4B8h] BYREF
  wil *v212; // [rsp+318h] [rbp-480h]
  _QWORD v213[4]; // [rsp+320h] [rbp-478h] BYREF
  __int128 v214; // [rsp+340h] [rbp-458h]
  __int64 v215; // [rsp+350h] [rbp-448h]
  char v216; // [rsp+370h] [rbp-428h]
  __int64 v217; // [rsp+378h] [rbp-420h]
  char v218[16]; // [rsp+380h] [rbp-418h] BYREF
  __int64 v219; // [rsp+390h] [rbp-408h]
  char v220; // [rsp+3C0h] [rbp-3D8h]
  char v221; // [rsp+3F8h] [rbp-3A0h]
  char v222[64]; // [rsp+400h] [rbp-398h] BYREF
  char v223[64]; // [rsp+440h] [rbp-358h] BYREF
  char v224[64]; // [rsp+480h] [rbp-318h] BYREF
  __int128 v225; // [rsp+4C0h] [rbp-2D8h] BYREF
  __int64 v226; // [rsp+4D0h] [rbp-2C8h]
  unsigned __int64 v227; // [rsp+4D8h] [rbp-2C0h]
  char v228; // [rsp+4E0h] [rbp-2B8h]
  __int128 v229; // [rsp+4F0h] [rbp-2A8h] BYREF
  const struct Update *v230; // [rsp+500h] [rbp-298h] BYREF
  volatile signed __int32 *v231; // [rsp+508h] [rbp-290h]
  __int128 v232; // [rsp+510h] [rbp-288h] BYREF
  __int64 v233; // [rsp+520h] [rbp-278h]
  __int64 v234; // [rsp+528h] [rbp-270h]
  _QWORD v235[4]; // [rsp+530h] [rbp-268h] BYREF
  _QWORD v236[4]; // [rsp+550h] [rbp-248h] BYREF
  __int128 v237; // [rsp+570h] [rbp-228h] BYREF
  __int64 v238; // [rsp+580h] [rbp-218h]
  __int64 v239; // [rsp+588h] [rbp-210h]
  __int128 v240; // [rsp+590h] [rbp-208h]
  __int64 v241; // [rsp+5A0h] [rbp-1F8h]
  char v242; // [rsp+5C0h] [rbp-1D8h]
  __int64 v243; // [rsp+5C8h] [rbp-1D0h]
  char v244[16]; // [rsp+5D0h] [rbp-1C8h] BYREF
  __int64 v245; // [rsp+5E0h] [rbp-1B8h]
  char v246; // [rsp+610h] [rbp-188h]
  char v247; // [rsp+648h] [rbp-150h]
  char v248[64]; // [rsp+650h] [rbp-148h] BYREF
  char v249[64]; // [rsp+690h] [rbp-108h] BYREF
  char v250[64]; // [rsp+6D0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+798h] [rbp+0h]

  v186 = a4;
  v8 = a3;
  v185 = a2;
  v190 = a1;
  v202 = a1;
  v194 = a2;
  v203 = a3;
  LODWORD(v176) = 0;
  v201 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl'::`2'::impl);
  v11 = *v8;
  v12 = IsEnabled == 0;
  v13 = *(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)*v8 + 24LL);
  if ( v12 )
  {
    v17 = v13(v11, &v177);
    v181[0] = 12;
    v19 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<3600,1>>,wchar_t const (&)[16],std::wstring>(
            &v180,
            v181,
            v18,
            v17);
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v201, v19);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
  }
  else
  {
    v175[0] = 1;
    v14 = v13(v11, &v177);
    v181[0] = 12;
    v16 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<3600,1>>,wchar_t const (&)[16],std::wstring,bool>(
            (unsigned int)&v180,
            (unsigned int)v181,
            v15,
            v14,
            (__int64)v175);
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v201, v16);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
  }
  std::wstring::~wstring(&v177);
  v199 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_IncreasedProgressCallbacks>::GetImpl'::`2'::impl) )
  {
    v188 = 0;
    UpdateManager::GetUxBroker(a1, &v188);
    if ( v188.m128i_i64[0] )
    {
      v175[0] = 1;
      v207[0] = a1;
      v21 = v8[1];
      if ( v21 )
        _InterlockedIncrement((volatile signed __int32 *)v21 + 2);
      v207[1] = *v8;
      v207[2] = v8[1];
      v22 = a4[1];
      if ( v22 )
        _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
      v207[3] = *a4;
      v208[0] = a4[1];
      v208[1] = a7;
      v23 = UX::Broker::MinProgressFrequency(v20, v183);
      v24 = (__int64 *)std::make_shared_watchdog_timer_std::chrono::duration___int64_std::ratio_1_1_____UpdateManager::PerformAction_::_13_::_lambda_1__bool_(
                         &v180,
                         v23,
                         v207,
                         v175);
      v25 = *v24;
      v26 = (volatile signed __int32 *)v24[1];
      *v24 = 0;
      v24[1] = 0;
      v200 = 0u;
      *(_QWORD *)&v199 = v25;
      *((_QWORD *)&v199 + 1) = v26;
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v200);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v180);
      UpdateManager::PerformAction_::_13_::_lambda_1_::__lambda_1_(v207);
    }
    else
    {
      v26 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
    }
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v188);
  }
  else
  {
    v26 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
  }
  v213[0] = *v8;
  v213[1] = 0;
  v27 = (UpdateDatabase **)(a1 + 16);
  v191 = (UpdateDatabase **)(a1 + 16);
  v213[2] = *(_QWORD *)(a1 + 16);
  v213[3] = 0;
  v214 = 0;
  v215 = 0;
  v216 = 0;
  v217 = 0;
  std::set<std::wstring>::set<std::wstring>(v218);
  v219 = 0;
  v220 = 0;
  v221 = 0;
  std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v222);
  std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v223);
  std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(v224);
  v195 = (__int64 *)(a1 + 32);
  v28 = *(_QWORD *)(a1 + 32);
  v177 = 0;
  v178 = 0;
  v179 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v177, &psz);
  v180 = *(__m128i *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v182, L"Update priority");
  v29 = DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
          v28,
          (unsigned int)&v225,
          (unsigned int)&v180,
          (unsigned int)v213,
          (__int64)&v177);
  v181[0] = (unsigned __int8)std::operator==<wchar_t>(v29, L"Low", v30);
  std::wstring::~wstring(&v225);
  std::wstring::~wstring(&v177);
  UpdateDatabase::GetAndIncrementCV(*v27, &v230, *v8);
  v232 = 0;
  v233 = 0;
  v234 = 7;
  LOWORD(v232) = 0;
  UpdateDatabase::GetUpdateActionDelayDetails(*v27, &v225, *v8);
  v31 = 0;
  v200 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    System = SystemInterface::Providers::GetSystem(v198);
    v33 = *(_QWORD *)System + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v193 = *(_QWORD *)(*(_QWORD *)(v33 + 8) + 128LL);
    UpdateRelatedActivityId = UpdateDatabase::GetUpdateRelatedActivityId(*v27, v207, *v8);
    v35 = (_QWORD *)SystemInterface::Providers::GetSystem(v183);
    v36 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v35 + 40LL))(*v35, v206);
    LOBYTE(v37) = 1;
    v38 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64))(*(_QWORD *)*v36 + 448LL))(*v36, v197, v37);
    v39 = (_QWORD *)std::optional<std::wstring>::value_or<std::wstring>(UpdateRelatedActivityId, &v177, v38);
    v40 = v39[2];
    if ( v39[3] > 7u )
      v39 = (_QWORD *)*v39;
    v188.m128i_i64[0] = (__int64)v39;
    v188.m128i_i64[1] = v40;
    v180 = v188;
    v189 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v182);
    v41 = ((__int64 (__fastcall *)(__int64, __int128 *, __int128 *, __m128i *))v193)(v33 + 8, &v187, &v189, &v180);
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v200, v41);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v187);
    std::wstring::~wstring(&v177);
    std::wstring::~wstring(v197);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v206);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v183);
    if ( LOBYTE(v208[0]) )
      std::wstring::~wstring(v207);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v198);
    v31 = _mm_load_si128(&v200);
  }
  UpdateDatabase::ReleaseUpdateActionTags(*v27, v236, *v8);
  v42 = *v195;
  v177 = 0;
  v178 = 0;
  v179 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v177, L"Performance");
  v43 = 48;
  v184 = 48;
  LODWORD(v176) = 48;
  v180 = *(__m128i *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v189, L"Update deferral mode");
  DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
    v42,
    (unsigned int)v235,
    (unsigned int)&v180,
    (unsigned int)v213,
    (__int64)&v177);
  std::wstring::~wstring(&v177);
  v229 = 0;
  v44 = (_QWORD *)SystemInterface::Providers::GetSystem(&v182);
  v198[0] = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*v44 + 40LL))(*v44, v197);
  v183[0] = *(_QWORD *)(*(_QWORD *)v198[0] + 152LL);
  v206[0] = &v188;
  v188 = 0;
  v45 = _mm_srli_si128(v31, 8).m128i_u64[0];
  v193 = v45;
  if ( v45 )
    _InterlockedIncrement((volatile signed __int32 *)(v45 + 8));
  v188 = v31;
  DiscoveryTime = UpdateDatabase::GetDiscoveryTime(*v27, &v187, *v8);
  v46 = v236;
  if ( v236[3] > 7u )
    v46 = (_QWORD *)v236[0];
  *(_QWORD *)&v189 = v46;
  *((_QWORD *)&v189 + 1) = v236[2];
  v47 = (_BYTE)v226 != 0 ? v225 : 0;
  v204 = v230;
  v48 = v235;
  if ( v235[3] > 7u )
    v48 = (_QWORD *)v235[0];
  v180.m128i_i64[0] = (__int64)v48;
  v180.m128i_i64[1] = v235[2];
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 128LL))(*a4) )
  {
    v49 = (_QWORD *)SystemInterface::Service::GetSystem(&v196);
    LODWORD(v176) = 49;
    v50 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v49 + 72LL))(*v49, v205);
    v43 = 51;
    v184 = 51;
    LODWORD(v176) = 51;
    v51 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v50 + 256LL))(*v50, &v177);
  }
  else
  {
    LOBYTE(v226) = 0;
    v51 = &v225;
  }
  v52 = *v51;
  v53 = *((_QWORD *)v51 + 2);
  IsApproved = UpdateDatabase::IsApproved(*v27, *v8);
  v225 = v52;
  v226 = v53;
  LOBYTE(v173) = IsApproved;
  ((void (__fastcall *)(_QWORD, __int128 *, const struct Update **, _QWORD, int, _DWORD, __int128 *, __m128i *, const struct Update *, int, __int128 *, __int64, __m128i *))v183[0])(
    v198[0],
    &v229,
    v8,
    *a4,
    v173,
    v181[0],
    &v225,
    &v180,
    v204,
    v47,
    &v189,
    DiscoveryTime,
    &v188);
  if ( (v43 & 2) != 0 )
  {
    v43 &= ~2u;
    v184 = v43;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v205);
  }
  if ( (v43 & 1) != 0 )
  {
    v184 = v43 & 0xFFFFFFFE;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v196);
  }
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v197);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v182);
  UpdateDatabase::SetUpdateLastAttemptTime(*v27, *v8);
  v55 = 0;
  DiscoveryTime = 0;
  if ( UpdateDatabase::IsOobeApproved(*v27, *v8)
    || (*(unsigned __int8 (__fastcall **)(const struct Update *))(*(_QWORD *)*v8 + 408LL))(*v8) )
  {
    v56 = (_QWORD *)SystemInterface::Providers::GetSystem(v197);
    v57 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v56 + 40LL))(*v56, &v182);
    v58 = *(_QWORD *)v57;
    v59 = *(__int64 (__fastcall **)(__int64, _QWORD *, const struct Update **, _QWORD, int, _DWORD, const struct Update *))(**(_QWORD **)v57 + 160LL);
    v60 = v230;
    LOBYTE(v174) = UpdateDatabase::IsApproved(*v27, *v8);
    v61 = (__int64 *)v59(v58, v183, v8, *v186, v174, v181[0], v60);
    v55 = *v61;
    *v61 = 0;
    DiscoveryTime = v55;
    if ( v183[0] )
      (**(void (__fastcall ***)(_QWORD, __int64))v183[0])(v183[0], 1);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v182);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v197);
  }
  v62 = *v195;
  LODWORD(v176) = 10;
  v182 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                      v197,
                      L"Max action attempts per unit time");
  LODWORD(v62) = DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<int>(
                   v62,
                   &v182,
                   v213,
                   &v176);
  v63 = *v8;
  v64 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v186 + 8LL))(*v186, &v177);
  Update::AddActionAttempt(v63, v64, (unsigned int)v62);
  std::wstring::~wstring(&v177);
  UpdateDatabase::SetUpdateActionAttempts(*v27, *v8);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::GetImpl'::`2'::impl) )
  {
    v176 = 0;
    web::json::value::object(&v176);
    v65 = std::wstring::wstring(&v225, v236);
    v66 = (__int64 *)web::json::value::string(v183, v65);
    v177 = 0;
    v178 = 0;
    v179 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v177, L"Tags");
    v67 = (__int64 *)web::json::value::operator[](&v176, &v177);
    if ( v67 != v66 )
    {
      v68 = *v67;
      *v67 = *v66;
      *v66 = v68;
    }
    std::wstring::~wstring(&v177);
    if ( v183[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v183[0] + 192LL))(v183[0], 1);
    v69 = std::wstring::wstring(&v225, v235);
    v70 = (__int64 *)web::json::value::string(v183, v69);
    v177 = 0;
    v178 = 0;
    v179 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v177, L"DeferralMode");
    v71 = (__int64 *)web::json::value::operator[](&v176, &v177);
    if ( v71 != v70 )
    {
      v72 = *v71;
      *v71 = *v70;
      *v70 = v72;
    }
    std::wstring::~wstring(&v177);
    if ( v183[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v183[0] + 192LL))(v183[0], 1);
    v73 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v229 + 32LL))(v229, &v225);
    v74 = (__int64 *)web::json::value::string(v183, v73);
    v177 = 0;
    v178 = 0;
    v179 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v177, L"AID");
    v75 = (__int64 *)web::json::value::operator[](&v176, &v177);
    if ( v75 != v74 )
    {
      v76 = *v75;
      *v75 = *v74;
      *v74 = v76;
    }
    std::wstring::~wstring(&v177);
    if ( v183[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v183[0] + 192LL))(v183[0], 1);
    if ( v31.m128i_i64[0] )
    {
      v77 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v31.m128i_i64[0] + 16LL))(
              v31.m128i_i64[0],
              &v225);
      v78 = (__int64 *)web::json::value::string(v183, v77);
      v177 = 0;
      v178 = 0;
      v179 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v177, L"RAID");
      v79 = (__int64 *)web::json::value::operator[](&v176, &v177);
      if ( v79 != v78 )
      {
        v80 = *v79;
        *v79 = *v78;
        *v78 = v80;
      }
      std::wstring::~wstring(&v177);
      if ( v183[0] )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v183[0] + 192LL))(v183[0], 1);
    }
    v81 = *v27;
    v82 = v186;
    v83 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v186 + 8LL))(*v186, &v177);
    v84 = v83[2];
    if ( v83[3] > 7u )
      v83 = (_QWORD *)*v83;
    v180.m128i_i64[0] = (__int64)v83;
    v180.m128i_i64[1] = v84;
    v182 = (__int128)v180;
    UpdateDatabase::UpdateActionAttemptDiagnostic(v81, *v8);
    std::wstring::~wstring(&v177);
    if ( v176 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v176 + 192LL))(v176, 1);
  }
  else
  {
    v82 = v186;
  }
  memset(v209, 0, sizeof(v209));
  v85 = 0u;
  if ( *((_QWORD *)&v229 + 1) )
  {
    v85 = v229;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v229 + 1) + 12LL));
  }
  v86 = (volatile signed __int32 *)*((_QWORD *)&v201 + 1);
  v87 = 0u;
  if ( *((_QWORD *)&v201 + 1) )
  {
    v87 = v201;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v201 + 1) + 12LL));
  }
  v88 = 0;
  v89 = 0;
  if ( v26 )
  {
    v88 = v199;
    v89 = v26;
    _InterlockedIncrement(v26 + 3);
  }
  v90 = v190;
  *(_QWORD *)&v209[0] = v190;
  v91 = v8[1];
  if ( v91 )
    _InterlockedIncrement((volatile signed __int32 *)v91 + 2);
  *((_QWORD *)&v209[0] + 1) = *v8;
  *(_QWORD *)&v209[1] = v8[1];
  v92 = v82[1];
  if ( v92 )
    _InterlockedIncrement((volatile signed __int32 *)(v92 + 8));
  *((_QWORD *)&v209[1] + 1) = *v82;
  *(_QWORD *)&v209[2] = v82[1];
  *(_OWORD *)((char *)&v209[2] + 8) = v85;
  *((_QWORD *)&v209[3] + 1) = a5;
  v209[4] = __PAIR128__(a7, a6);
  v209[5] = v87;
  *(_QWORD *)&v209[6] = v88;
  *((_QWORD *)&v209[6] + 1) = v89;
  UpdateDatabase::SetWorkBit(*v191, *v8, 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateStateDiagnostics>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateStateDiagnostics>::GetImpl'::`2'::impl) )
  {
    v93 = *(RTL_SRWLOCK **)(v90 + 48);
    v187 = 0;
    v94 = v8[1];
    if ( v94 )
      _InterlockedIncrement((volatile signed __int32 *)v94 + 2);
    v187 = *(_OWORD *)v8;
    CallbackManager::UpdateActionStarted(v93);
  }
  v95 = *v195;
  LODWORD(v176) = 720;
  v237 = 0;
  v238 = 0;
  v239 = *v82;
  v240 = 0;
  v96 = *(_QWORD *)(v190 + 776);
  v97 = (*(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)*v8 + 8LL))(*v8, &v177);
  v241 = *(_QWORD *)ScanManager::GetProvider(v96, &v225, v97);
  v242 = 0;
  v243 = 0;
  std::set<std::wstring>::set<std::wstring>(v244);
  v245 = 0;
  v246 = 0;
  v247 = 0;
  std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v248);
  std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v249);
  std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(v250);
  v182 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                      v197,
                      L"Update action timeout in minutes");
  v98 = DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<int>(v95, &v182, &v237, &v176);
  LODWORD(v176) = v98;
  SystemInterface::Providers::ConditionContext::~ConditionContext((SystemInterface::Providers::ConditionContext *)&v237);
  ActionState::~ActionState((ActionState *)&v225);
  v188 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl) )
  {
    v99 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl'::`2'::impl);
    v100 = *v8;
    v12 = v99 == 0;
    v101 = *(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)*v8 + 24LL);
    if ( v12 )
    {
      v105 = v101(v100, &v177);
      v104 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<60,1>> const &,wchar_t const (&)[14],std::wstring>(
               &v182,
               &v176,
               v106,
               v105);
    }
    else
    {
      v175[0] = 1;
      v102 = v101(v100, &v177);
      v104 = std::make_shared<Threads::Watchdog,std::chrono::duration<int,std::ratio<60,1>> const &,wchar_t const (&)[14],std::wstring,bool>(
               (unsigned int)&v182,
               (unsigned int)&v176,
               v103,
               v102,
               (__int64)v175);
    }
    std::shared_ptr<_EXCEPTION_RECORD const>::operator=(&v188, v104);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v182);
    std::wstring::~wstring(&v177);
  }
  else
  {
    v107 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Bugfix_TelemetryImprovements_59300384>::GetImpl'::`2'::impl);
    v108 = *v8;
    v12 = v107 == 0;
    *(_QWORD *)&v187 = &v225;
    v109 = *(__int64 (__fastcall **)(const struct Update *, __int128 *))(*(_QWORD *)v108 + 24LL);
    if ( v12 )
    {
      v111 = v109(v108, &v225);
      v177 = 0;
      v178 = 0;
      v179 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v177, L"Action Global");
      Threads::Watchdog::Watchdog(&v237, v98, &v177, v111);
    }
    else
    {
      v110 = v109(v108, &v225);
      v177 = 0;
      v178 = 0;
      v179 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v177, L"Action Global");
      Threads::Watchdog::Watchdog((unsigned int)&v237, v98, (unsigned int)&v177, v110, 1);
    }
    watchdog_timer::~watchdog_timer((watchdog_timer *)&v237);
  }
  v112 = v185;
  v198[0] = v185 + 6;
  *((_BYTE *)v185 + 24) = 0;
  v113 = v184 | 4;
  LODWORD(v176) = v184 | 4;
  try
  {
    (*(void (**)(void))(*(_QWORD *)*v8 + 344LL))();
    v183[0] = *v8;
    v212 = 0;
    v114 = operator new(0x78u);
    *v114 = &off_1403C6B00;
    UpdateManager::PerformAction_::_2_::_lambda_2_::_lambda_2_(v114 + 1, v209);
    v212 = v115;
    v116 = Update::PerformAction(v183[0], (unsigned int)&v177, *v186, (unsigned int)v211, (__int64)&v230);
    std::optional<ActionResult>::operator=(v112, v116);
    std::_Optional_construct_base<ActionResult>::~_Optional_construct_base<ActionResult>(&v177);
    v118 = v212;
    if ( v212 )
    {
      LOBYTE(v117) = v212 != (wil *)v211;
      (*(void (__fastcall **)(wil *, __int64))(*(_QWORD *)v212 + 32LL))(v212, v117);
    }
  }
  catch ( const std::exception *v210 )
  {
    v168 = SystemInterface::Providers::GetSystem(&v196);
    v169 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v168 + 8LL) + 4LL)
                                                                    + *(_QWORD *)v168
                                                                    + 8LL)
                                                        + 104LL))(
             *(_QWORD *)v168 + *(int *)(*(_QWORD *)(*(_QWORD *)v168 + 8LL) + 4LL) + 8LL,
             v197);
    v170 = *(_QWORD *)v169;
    v171 = *(void (__fastcall **)(__int64, __int128 *, const std::exception *))(**(_QWORD **)v169 + 264LL);
    v182 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v205, L"Action");
    v171(v170, &v182, v210);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v197);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v196);
    *(_QWORD *)&v182 = (unsigned int)wil::ResultFromCaughtException(v172);
    std::set<enum UMAction>::set<enum UMAction>((char *)&v182 + 8);
    std::optional<ActionResult>::optional<ActionResult>(&v177, &v182);
    std::optional<ActionResult>::operator=(v194, &v177);
    std::_Optional_construct_base<ActionResult>::~_Optional_construct_base<ActionResult>(&v177);
    ActionResult::~ActionResult((ActionResult *)&v182);
    v193 = v200.m128i_i64[1];
    v190 = v202;
    v8 = v203;
    v185 = v194;
    v113 = v176;
    v55 = DiscoveryTime;
    v26 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
    v86 = (volatile signed __int32 *)*((_QWORD *)&v201 + 1);
  }
  catch ( ... )
  {
    *(_QWORD *)&v182 = (unsigned int)wil::ResultFromCaughtException(v118);
    std::set<enum UMAction>::set<enum UMAction>((char *)&v182 + 8);
    std::optional<ActionResult>::optional<ActionResult>(&v177, &v182);
    std::optional<ActionResult>::operator=(v194, &v177);
    std::_Optional_construct_base<ActionResult>::~_Optional_construct_base<ActionResult>(&v177);
    ActionResult::~ActionResult((ActionResult *)&v182);
    v193 = v200.m128i_i64[1];
    v190 = v202;
    v8 = v203;
    v185 = v194;
    v113 = v176;
    v55 = DiscoveryTime;
    v26 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
    v86 = (volatile signed __int32 *)*((_QWORD *)&v201 + 1);
  }
  v119 = v191;
  UpdateDatabase::UpdateUpdate(*v191, *v8);
  UpdateDatabase::SetWorkBit(*v119, *v8, 0);
  if ( *(_BYTE *)v198[0] )
  {
    v120 = (_QWORD *)**((_QWORD **)v185 + 1);
    while ( 1 )
    {
      v186 = v120;
      if ( *((_BYTE *)v120 + 25) )
        break;
      try
      {
        UpdateManager::RunFollowupAction(v190, *((unsigned int *)v120 + 7), *v8, &v230);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x632,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\UpdateManager.cpp",
          v121);
        v86 = (volatile signed __int32 *)*((_QWORD *)&v201 + 1);
        v26 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
        v193 = v200.m128i_i64[1];
        v55 = DiscoveryTime;
        v120 = v186;
        v113 = v176;
        v190 = v202;
        v185 = v194;
        v8 = v203;
      }
      v122 = (__int64 *)v120[2];
      if ( *((_BYTE *)v122 + 25) )
      {
        for ( i = v120[1]; !*(_BYTE *)(i + 25) && v120 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v120 = (_QWORD *)i;
        v120 = (_QWORD *)i;
      }
      else
      {
        do
        {
          v120 = v122;
          v122 = (__int64 *)*v122;
        }
        while ( !*((_BYTE *)v122 + 25) );
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
    {
      v124 = *v195;
      v177 = 0;
      v178 = 0;
      v179 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v177, L"Performance");
      LODWORD(v176) = v113 | 8;
      traits_2_unsigned_short = (void *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                          L"Update deferral mode",
                                          &unk_140400DFA,
                                          0);
      if ( traits_2_unsigned_short == &unk_140400DFA
        || (v128 = ((__int64)traits_2_unsigned_short - v127) >> 1, v128 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v126);
      }
      v180.m128i_i64[0] = v127;
      v180.m128i_i64[1] = v128;
      v182 = (__int128)v180;
      DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
        v124,
        (unsigned int)&v225,
        (unsigned int)&v182,
        (unsigned int)v213,
        (__int64)&v177);
      std::wstring::~wstring(&v177);
      v183[0] = v229;
      v198[0] = *(_QWORD *)(*(_QWORD *)v229 + 16LL);
      v129 = &v225;
      if ( v227 > 7 )
        v129 = (__int128 *)v225;
      v180.m128i_i64[0] = (__int64)v129;
      v180.m128i_i64[1] = v226;
      updated = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v191, &v177, *v8);
      v131 = updated[2];
      if ( updated[3] > 7u )
        updated = (_QWORD *)*updated;
      *(_QWORD *)&v189 = updated;
      *((_QWORD *)&v189 + 1) = v131;
      v132 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
               L"Completed",
               &unk_1403FE374,
               0);
      if ( v132 == v134 || (v135 = (v132 - (__int64)L"Completed") >> 1, v135 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v133);
      *(_QWORD *)&v187 = L"Completed";
      *((_QWORD *)&v187 + 1) = v135;
      v182 = (__int128)v180;
      v197[0] = v189;
      v196 = v187;
      ((void (__fastcall *)(_QWORD, _QWORD, __int128 *, _OWORD *, __int128 *))v198[0])(
        v183[0],
        *v185,
        &v196,
        v197,
        &v182);
      std::wstring::~wstring(&v177);
      std::wstring::~wstring(&v225);
    }
    else
    {
      v136 = v229;
      v137 = *(void (__fastcall **)(__int64, _QWORD, __int128 *, _OWORD *, __int128 *))(*(_QWORD *)v229 + 16LL);
      v138 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v205);
      v139 = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v191, &v177, *v8);
      v140 = v139[2];
      if ( v139[3] > 7u )
        v139 = (_QWORD *)*v139;
      v180.m128i_i64[0] = (__int64)v139;
      v180.m128i_i64[1] = v140;
      v141 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v189, L"Completed");
      v182 = v138;
      v197[0] = v180;
      v196 = *v141;
      v137(v136, *v185, &v196, v197, &v182);
      std::wstring::~wstring(&v177);
    }
    if ( v55 )
    {
      v142 = *(void (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v55 + 8LL);
      v182 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v197, L"Completed");
      v142(v55, *v185, &v182);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
    {
      v143 = *v195;
      v177 = 0;
      v178 = 0;
      v179 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v177, L"Performance");
      LODWORD(v176) = v113 | 0x40;
      v182 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v197, L"Update deferral mode");
      DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<std::wstring>(
        v143,
        (unsigned int)&v225,
        (unsigned int)&v182,
        (unsigned int)v213,
        (__int64)&v177);
      std::wstring::~wstring(&v177);
      v144 = v229;
      v145 = *(void (__fastcall **)(__int64, __int128 *, _OWORD *, __int128 *))(*(_QWORD *)v229 + 24LL);
      v146 = &v225;
      if ( v227 > 7 )
        v146 = (__int128 *)v225;
      v180.m128i_i64[0] = (__int64)v146;
      v180.m128i_i64[1] = v226;
      v147 = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v191, &v177, *v8);
      v148 = v147[2];
      if ( v147[3] > 7u )
        v147 = (_QWORD *)*v147;
      *(_QWORD *)&v189 = v147;
      *((_QWORD *)&v189 + 1) = v148;
      v182 = (__int128)v180;
      v197[0] = v189;
      v196 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v205, L"Aborted");
      v145(v144, &v196, v197, &v182);
      std::wstring::~wstring(&v177);
      v149 = &v225;
    }
    else
    {
      v150 = v229;
      v183[0] = *(_QWORD *)(*(_QWORD *)v229 + 24LL);
      v151 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v205);
      v152 = (_QWORD *)UpdateDatabase::ReleaseUpdateActionTags(*v119, &v177, *v8);
      v153 = v152[2];
      if ( v152[3] > 7u )
        v152 = (_QWORD *)*v152;
      v180.m128i_i64[0] = (__int64)v152;
      v180.m128i_i64[1] = v153;
      v182 = v151;
      v197[0] = v180;
      v196 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v189, L"Aborted");
      ((void (__fastcall *)(__int64, __int128 *, _OWORD *, __int128 *))v183[0])(v150, &v196, v197, &v182);
      v149 = &v177;
    }
    std::wstring::~wstring(v149);
    if ( v55 )
    {
      v154 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v55 + 16LL);
      v182 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v197, L"Aborted");
      v154(v55, &v182);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    v183[0] = *v191;
    v198[0] = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v229 + 32LL))(v229, &v177);
    v204 = *v8;
    InitOnceExecuteOnce(
      &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
      `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1EFB,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\Staging.h",
        v155);
    }
    v156 = *(_QWORD *)v183[0];
    v157 = *(void (__fastcall **)(__int64, __int64, __int128 *, __int128 *))(**(_QWORD **)v183[0] + 136LL);
    std::wstring::wstring(&v225, v198[0]);
    v228 = 4;
    v158 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
             L"UpdateRelatedActivityId",
             L"UpdateGroup",
             0);
    if ( v158 == v160 || (v161 = (v158 - (__int64)L"UpdateRelatedActivityId") >> 1, v161 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v159);
    v180.m128i_i64[0] = (__int64)L"UpdateRelatedActivityId";
    v180.m128i_i64[1] = v161;
    PrimaryKey = UpdateDatabase::GetPrimaryKey(v207, v204);
    v182 = (__int128)v180;
    v157(v156, PrimaryKey, &v182, &v225);
    std::wstring::~wstring(v208);
    std::wstring::~wstring(v207);
    if ( v228 != -1 && v228 && v228 != 1 && v228 != 2 && v228 != 3 )
      std::wstring::~wstring(&v225);
    std::wstring::~wstring(&v177);
  }
  v163 = (volatile signed __int32 *)v188.m128i_i64[1];
  if ( v188.m128i_i64[1] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v188.m128i_i64[1] + 8)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v163)(v163);
      if ( !_InterlockedDecrement(v163 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v163 + 8LL))(v163);
    }
  }
  UpdateManager::PerformAction_::_2_::_lambda_2_::__lambda_2_(v209);
  if ( v55 )
    (**(void (__fastcall ***)(__int64, __int64))v55)(v55, 1);
  v164 = (volatile signed __int32 *)*((_QWORD *)&v229 + 1);
  if ( *((_QWORD *)&v229 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v229 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v164)(v164);
      if ( _InterlockedExchangeAdd(v164 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v164 + 8LL))(v164);
    }
  }
  std::wstring::~wstring(v235);
  std::wstring::~wstring(v236);
  v165 = (volatile signed __int32 *)v193;
  if ( v193 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v193 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v165)(v165);
      if ( _InterlockedExchangeAdd(v165 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v165 + 8LL))(v165);
    }
  }
  std::wstring::~wstring(&v232);
  v166 = v231;
  if ( v231 )
  {
    if ( _InterlockedExchangeAdd(v231 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v166)(v166);
      if ( _InterlockedExchangeAdd(v166 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v166 + 8LL))(v166);
    }
  }
  SystemInterface::Providers::ConditionContext::~ConditionContext((SystemInterface::Providers::ConditionContext *)v213);
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  if ( v86 )
  {
    if ( _InterlockedExchangeAdd(v86 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
      if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
    }
  }
  return v185;
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
