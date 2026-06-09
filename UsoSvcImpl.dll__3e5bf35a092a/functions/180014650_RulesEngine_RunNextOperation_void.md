# RulesEngine::RunNextOperation(void)

- ea: `0x180014650`
- end: `0x1800164e7`
- name: `?RunNextOperation@RulesEngine@@AEAAXXZ`
- size: `7831`
- prototype: `void __fastcall(RulesEngine *__hidden this)`
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800187f0`

## callees

- `0x180009074`
- `0x18000c524`
- `0x18000efe8`
- `0x18000f83c`
- `0x180010890`
- `0x1800112d0`
- `0x1800114bc`
- `0x180011680`
- `0x180011948`
- `0x180011c58`
- `0x180011d20`
- `0x180012b40`
- `0x180012f38`
- `0x1800141e4`
- `0x1800145d4`
- `0x180014650`
- `0x180016760`
- `0x180016864`
- `0x180016b5c`
- `0x1800172fc`
- `0x18001a3e4`
- `0x18001a6d4`
- `0x18001a898`
- `0x18001aa80`
- `0x18001aee4`
- `0x18001af50`
- `0x18001b064`
- `0x18001b0d4`
- `0x18001b1ec`
- `0x18001b254`
- `0x18001b2bc`
- `0x18001b3d4`
- `0x18001b43c`
- `0x18001b554`
- `0x18001c098`
- `0x18001e5b8`
- `0x18001e5f4`
- `0x18002e064`
- `0x18002e168`
- `0x180031edc`
- `0x180032028`
- `0x1800420e0`
- `0x180042e00`
- `0x180042e48`
- `0x180062e94`
- `0x18006ea28`
- `0x180070188`
- `0x1800dd930`
- `0x1800dddf4`
- `0x1800e4630`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180015c6c`
- `ntdll!RtlPublishWnfStateData` at `0x180015c6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800146d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014739`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800146d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014739`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18001505d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800154c6`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180016168`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18001505d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800154c6`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180016168`

## string_xrefs

- `0x18001635d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180016377`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180016391`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800163ab`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180016404`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800164d4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800158eb`: `ScanBeforeInitialLogonBlockFeatureUpdates`
- `0x18001479f`: `RulesOperation: Attempting a database backup`
- `0x180014f5c`: `RulesOperation: Setting a timer for 2 hours post DEP OOBE Complete`
- `0x180015a39`: `RulesOperation: Setting a timer for 2 hours post DEP OOBE Complete`
- `0x180015ab5`: `DepOobeCompleteSchedulerTimeInMinutes`
- `0x180015364`: `RulesOperation: Attempting to run one-time configuration tasks based on DEP OOBE Complete signal`
- `0x180015463`: `Setting the USO cached OobeCompleteTimestamp`
- `0x1800152c0`: `OobeCompleteAppsScan`
- `0x180016096`: `ConfigProvider`
- `0x1800163c0`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1800163ea`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
void __fastcall RulesEngine::RunNextOperation(RulesEngine *this)
{
  char v2; // r15
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // r8
  int v8; // eax
  const char *v9; // r9
  unsigned __int64 v10; // r10
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // rsi
  bool v15; // zf
  unsigned __int64 v16; // rax
  int v17; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  __int64 *v25; // rax
  __int64 (__fastcall *v26)(__int64, int *, int *); // rbx
  __int16 *v27; // rax
  const char *v28; // r9
  __int64 v29; // r11
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // edi
  volatile signed __int32 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  __int64 *v35; // rax
  __int64 v36; // rcx
  UsoScheduler *v37; // rbx
  UsoScheduler *v38; // rbx
  __int64 v39; // rdx
  __int64 *v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rax
  const char *v43; // r9
  __int64 v44; // r11
  __int64 v45; // rax
  __int64 v46; // rax
  volatile signed __int32 *v47; // rbx
  volatile signed __int32 *v48; // rbx
  __int64 *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdi
  int (__fastcall *v52)(__int64, __int128 *, int *); // rbx
  __int64 v53; // rbx
  _QWORD *v54; // rax
  signed __int64 v55; // rcx
  int CoreWorker; // eax
  wil::details::in1diag3 *v57; // rcx
  __int64 v58; // rdx
  __int64 *v59; // rax
  __int64 v60; // rbx
  _QWORD *v61; // rdi
  __int128 v62; // xmm1
  UsoScheduler *v63; // rcx
  __int64 *v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rax
  const char *v67; // r9
  __int64 v68; // r11
  __int64 v69; // rax
  __int64 v70; // rax
  volatile signed __int32 *v71; // rbx
  volatile signed __int32 *v72; // rbx
  __int64 *v73; // rax
  __int64 v74; // rax
  __int64 v75; // rbx
  __int64 (__fastcall *v76)(__int64, int *, int *); // rdi
  wchar_t *v77; // rax
  const char *v78; // r9
  __int64 v79; // r11
  __int64 v80; // rax
  int v81; // edi
  volatile signed __int32 *v82; // rbx
  volatile signed __int32 *v83; // rbx
  UsoScheduler *v84; // rax
  UsoScheduler *v85; // rbx
  __int64 v86; // rax
  __int128 v87; // rtt
  __int64 *v88; // rax
  __int64 v89; // rbx
  _QWORD *v90; // rdi
  __int128 v91; // xmm1
  __int64 (__fastcall ***v92)(_QWORD, GUID *, UsoScheduler **); // rcx
  int v93; // eax
  int v94; // eax
  const char *v95; // r9
  __int64 *v96; // rax
  _QWORD *v97; // rax
  char v98; // di
  volatile signed __int32 *v99; // rbx
  volatile signed __int32 *v100; // rbx
  __int64 *v101; // rax
  __int64 v102; // rbx
  __int64 v103; // rax
  __int64 v104; // rax
  volatile signed __int32 *v105; // rbx
  volatile signed __int32 *v106; // rbx
  __int64 *v107; // rax
  _QWORD *v108; // rax
  __int64 v109; // rdx
  __int64 *v110; // rax
  __int64 v111; // rax
  __int64 v112; // rdi
  __int64 (__fastcall *v113)(__int64, __int128 *, __int128 *); // rbx
  unsigned int v114; // edi
  __int64 v115; // rdx
  __int64 *v116; // rax
  __int64 v117; // rdx
  UsoScheduler *v118; // rbx
  UsoScheduler *v119; // rbx
  __int64 (__fastcall ***v120)(_QWORD, GUID *, UsoScheduler **); // rcx
  int v121; // eax
  int v122; // eax
  __int64 v123; // rbx
  __int64 (__fastcall *v124)(__int64, __int64); // rbx
  __int64 v125; // rax
  __int64 v126; // r11
  int v127; // eax
  __int64 *v128; // rax
  __int64 v129; // rax
  __int64 v130; // rbx
  void (__fastcall *v131)(__int64, __int128 *, int *, __int128 *, __int128 *); // r14
  __int128 v132; // xmm6
  _OWORD *v133; // rax
  __int64 *v134; // rax
  _QWORD *v135; // rax
  __int64 *v136; // rax
  __int64 (__fastcall *v137)(__int64, __int128 *, __int128 *); // rbx
  int *v138; // rax
  const char *v139; // r9
  __int64 v140; // r11
  __int64 v141; // rax
  __int64 v142; // rdx
  volatile signed __int32 *v143; // rbx
  volatile signed __int32 *v144; // rbx
  __int64 *v145; // rax
  UsoScheduler *v146; // rbx
  UsoScheduler *v147; // rbx
  int v148; // eax
  _QWORD *v149; // rax
  int v150; // eax
  const char *v151; // r9
  _QWORD *v152; // rax
  int v153; // eax
  const char *v154; // r9
  _QWORD *v155; // rax
  int v156; // eax
  __int64 *v157; // rax
  __int64 v158; // r10
  __int64 v159; // rax
  __int64 v160; // rax
  volatile signed __int32 *v161; // rbx
  volatile signed __int32 *v162; // rbx
  int v163; // edi
  int v164; // edi
  int v165; // edi
  int v166; // edi
  int v167; // edi
  int v168; // edi
  int v169; // edi
  __int64 v170; // rdx
  RulesEngine *v171; // rcx
  __int64 *v172; // rax
  __int64 v173; // rdx
  UsoScheduler *v174; // rbx
  UsoScheduler *v175; // rbx
  _QWORD *UpdateManager; // rax
  int v177; // eax
  __int64 *System; // rax
  __int64 v179; // rbx
  __int64 traits_2_unsigned_short; // rax
  const char *v181; // r9
  __int64 v182; // r11
  __int64 v183; // rax
  __int64 v184; // rax
  volatile signed __int32 *v185; // rbx
  const char *v186; // r9
  unsigned int v187; // eax
  int v188; // [rsp+20h] [rbp-148h]
  int v189; // [rsp+20h] [rbp-148h]
  _QWORD v190[2]; // [rsp+30h] [rbp-138h] BYREF
  int v191[4]; // [rsp+40h] [rbp-128h] BYREF
  UsoScheduler *v192[2]; // [rsp+50h] [rbp-118h] BYREF
  __int128 v193; // [rsp+60h] [rbp-108h] BYREF
  __int128 v194; // [rsp+70h] [rbp-F8h] BYREF
  int v195[4]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v196[16]; // [rsp+90h] [rbp-D8h] BYREF
  __int128 v197; // [rsp+A0h] [rbp-C8h] BYREF
  __int128 v198; // [rsp+B0h] [rbp-B8h] BYREF
  __int128 v199; // [rsp+C0h] [rbp-A8h] BYREF
  __int128 v200; // [rsp+D0h] [rbp-98h] BYREF
  __int64 v201; // [rsp+E0h] [rbp-88h]
  __int64 v202; // [rsp+E8h] [rbp-80h]
  char v203; // [rsp+F0h] [rbp-78h]
  __int128 v204; // [rsp+F8h] [rbp-70h] BYREF
  __int64 v205; // [rsp+108h] [rbp-60h]
  __int64 v206; // [rsp+110h] [rbp-58h]
  int v207; // [rsp+118h] [rbp-50h] BYREF
  UsoScheduler *v208[2]; // [rsp+120h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v2 = 1;
  v196[1] = 1;
  v3 = s_runOperationInfo;
  v4 = mtx_do_lock(s_runOperationInfo);
  try
  {
    if ( v4 )
      std::_Throw_Cpp_error(5);
    v6 = *(_DWORD *)(v3 + 76);
    if ( v6 == 0x7FFFFFFF )
    {
      *(_DWORD *)(v3 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v7 = s_runOperationInfo;
    if ( !*(_QWORD *)(s_runOperationInfo + 120) )
    {
      v8 = v6 - 1;
      *(_DWORD *)(v3 + 76) = v8;
      if ( !v8 )
      {
        *(_DWORD *)(v3 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 16));
      }
      wil::details::lambda_call__RulesEngine::RunNextOperation_::_3_::_lambda_1___::_lambda_call__RulesEngine::RunNextOperation_::_3_::_lambda_1___(
        v196,
        v5);
      return;
    }
    v10 = *(_QWORD *)(s_runOperationInfo + 112);
    v11 = (*(_QWORD *)(s_runOperationInfo + 104) - 1LL) & (v10 >> 2);
    v12 = v10 & 3;
    v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(s_runOperationInfo + 96) + 8 * v11) + 4 * v12);
    v14 = -1;
    v15 = (*(_QWORD *)(s_runOperationInfo + 120))-- == 1;
    v16 = 0;
    if ( !v15 )
      v16 = v10 + 1;
    *(_QWORD *)(v7 + 112) = v16;
    v15 = (*(_DWORD *)(v3 + 76))-- == 1;
    if ( v15 )
    {
      *(_DWORD *)(v3 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 16));
    }
    if ( v13 > 10 )
    {
      v163 = v13 - 11;
      if ( !v163 )
      {
        RulesEngine::HandleConnectedStandbySignal((RulesEngine *)v12);
        goto LABEL_227;
      }
      v164 = v163 - 1;
      if ( !v164 )
      {
        RulesEngine::HandleUnlockScreenSignal((RulesEngine *)v12);
        goto LABEL_227;
      }
      v165 = v164 - 1;
      if ( !v165 )
      {
        RulesEngine::SendSuspendSignal((RulesEngine *)v12);
        goto LABEL_227;
      }
      v166 = v165 - 1;
      if ( !v166 )
      {
        RulesEngine::SendResumeSignal((RulesEngine *)v12);
        goto LABEL_227;
      }
      v167 = v166 - 1;
      if ( v167 )
      {
        v168 = v167 - 1;
        if ( v168 )
        {
          v169 = v168 - 1;
          if ( !v169 )
          {
            UpdateManager = (_QWORD *)anonymous_namespace_::GetUpdateManager(
                                        v192,
                                        L"RulesEngine - CFRTermination",
                                        L"ConfigProvider");
            v177 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(*(_QWORD *)*UpdateManager + 72LL))(
                     *UpdateManager,
                     1,
                     0,
                     1);
            if ( v177 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x319,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                (const char *)(unsigned int)v177,
                1);
            v63 = v192[0];
            goto LABEL_210;
          }
          if ( v169 == 1 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
            {
              v187 = wil::verify_hresult(2149884179LL);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x330,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                (const char *)v187,
                v188);
            }
            if ( !*((_QWORD *)this + 14) )
            {
              LOBYTE(v190[0]) = 1;
              LODWORD(v194) = 12;
              v172 = (__int64 *)std::make_unique_UsoScheduler_wchar_t_const_____19__std::chrono::duration_int_std::ratio_3600_1____bool__RulesEngine::RunNextOperation_::_67_::_lambda_5__0_(
                                  v192,
                                  v170,
                                  &v194,
                                  v190);
              v173 = *v172;
              *v172 = 0;
              v174 = (UsoScheduler *)*((_QWORD *)this + 14);
              *((_QWORD *)this + 14) = v173;
              if ( v174 )
              {
                UsoScheduler::~UsoScheduler(v174);
                operator delete(v174, (const struct std::nothrow_t *)0x128);
              }
              v175 = v192[0];
              if ( v192[0] )
              {
                UsoScheduler::~UsoScheduler(v192[0]);
                operator delete(v175, (const struct std::nothrow_t *)0x128);
              }
            }
            RulesEngine::CleanupUOProviders(v171);
            goto LABEL_227;
          }
          goto LABEL_242;
        }
        *(_QWORD *)v191 = L"RulesOperation: AAD Registration Change signaled";
        *(_QWORD *)&v191[2] = 48;
        v193 = *(_OWORD *)v191;
        SystemInterface::Log<>(&v193);
        RulesEngine::HandleAADRegistrationChangeSignal(this);
LABEL_227:
        wil::details::lambda_call__RulesEngine::RunNextOperation_::_3_::_lambda_1___::_lambda_call__RulesEngine::RunNextOperation_::_3_::_lambda_1___(
          v196,
          v39);
        return;
      }
      System = SystemInterface::Service::GetSystem((__int64 *)&v199);
      v179 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*System + 32LL))(*System, &v197);
      v208[0] = 0;
      GetSystemTimePreciseAsFileTime(v208);
      v192[0] = (UsoScheduler *)(((unsigned __int64)HIDWORD(v208[0]) << 32) - 116444736000000000LL + LODWORD(v208[0]));
      traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                  L"LastUserWakeTime",
                                  word_1800FABAA,
                                  0);
      if ( traits_2_unsigned_short == v182
        || (v183 = (traits_2_unsigned_short - (__int64)L"LastUserWakeTime") >> 1, v183 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v181);
      }
      *(_QWORD *)v191 = L"LastUserWakeTime";
      *(_QWORD *)&v191[2] = v183;
      v200 = 0;
      v201 = 0;
      v202 = 7;
      LOWORD(v200) = 0;
      v208[0] = (UsoScheduler *)&v200;
      v208[1] = 0;
      *(_QWORD *)&v194 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v184 = -1;
      do
        ++v184;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v184] );
      *((_QWORD *)&v194 + 1) = v184;
      v193 = *(_OWORD *)v191;
      *(_OWORD *)v195 = *(_OWORD *)v208;
      v198 = v194;
      SystemInterface::Registry::SetSystemTime(v179, &v198, (__int128 *)v195, &v193, v192);
      std::wstring::~wstring(&v200);
      v185 = (volatile signed __int32 *)*((_QWORD *)&v197 + 1);
      if ( *((_QWORD *)&v197 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v185)(v185);
          if ( !_InterlockedDecrement(v185 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v185 + 8LL))(v185);
        }
      }
    }
    else
    {
      if ( v13 != 10 )
      {
        v17 = v13 - 1;
        if ( !v17 )
        {
          try
          {
            *(_QWORD *)v191 = L"RulesOperation: Starting CrmScan";
            *(_QWORD *)&v191[2] = 32;
            v193 = *(_OWORD *)v191;
            SystemInterface::Log<>(&v193);
            v152 = (_QWORD *)anonymous_namespace_::GetUpdateManager(v192, L"UsoCrmScan", &S1);
            v153 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v152 + 72LL))(*v152, 0, 0, 0);
            if ( v153 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x205,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                (const char *)(unsigned int)v153,
                0);
            if ( v192[0] )
              (*(void (__fastcall **)(UsoScheduler *))(*(_QWORD *)v192[0] + 16LL))(v192[0]);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x207,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
              v154);
            goto LABEL_227;
          }
          goto LABEL_227;
        }
        v18 = v17 - 1;
        if ( !v18 )
        {
          try
          {
            *(_QWORD *)v191 = L"RulesOperation: Starting NetworkConnectedScan";
            *(_QWORD *)&v191[2] = 45;
            v193 = *(_OWORD *)v191;
            SystemInterface::Log<>(&v193);
            v149 = (_QWORD *)anonymous_namespace_::GetUpdateManager(v192, L"NetworkConnectedScan", &S1);
            v150 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v149 + 72LL))(*v149, 0, 0, 0);
            if ( v150 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x210,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                (const char *)(unsigned int)v150,
                0);
            if ( v192[0] )
              (*(void (__fastcall **)(UsoScheduler *))(*(_QWORD *)v192[0] + 16LL))(v192[0]);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x212,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
              v151);
            goto LABEL_227;
          }
          goto LABEL_227;
        }
        v19 = v18 - 1;
        if ( !v19 )
        {
          *(_QWORD *)v191 = L"RulesOperation: Signaling Active hours start.";
          *(_QWORD *)&v191[2] = 45;
          v193 = *(_OWORD *)v191;
          SystemInterface::Log<>(&v193);
          v148 = RtlPublishWnfStateData(WNF_USO_ACTIVEHOURS_STARTED, 0, 0, 0) | 0x10000000;
          if ( v148 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x35A,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\Resource.h",
              (const char *)(unsigned int)v148,
              0);
          anonymous_namespace_::StopWorkIfRunning(retaddr);
          goto LABEL_227;
        }
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( !v21 )
          {
            *(_QWORD *)v191 = L"RulesOperation: Setting a timer for 2 hours post DEP OOBE Complete";
            *(_QWORD *)&v191[2] = 66;
            v193 = *(_OWORD *)v191;
            SystemInterface::Log<>(&v193);
            if ( (unsigned __int8)anonymous_namespace_::IsFirstRunConfigurationNeeded() )
            {
              v136 = SystemInterface::Service::GetSystem((__int64 *)&v198);
              v137 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*v136 + 40LL))(
                                                                                                *v136,
                                                                                                v195)
                                                                               + 56LL);
              LODWORD(v194) = 120;
              v138 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"DepOobeCompleteSchedulerTimeInMinutes",
                              &dword_1800FA78C,
                              0);
              if ( v138 == &dword_1800FA78C
                || (v141 = ((char *)v138 - (char *)L"DepOobeCompleteSchedulerTimeInMinutes") >> 1, v141 == -1) )
              {
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                  v139);
              }
              *(_QWORD *)v191 = L"DepOobeCompleteSchedulerTimeInMinutes";
              *(_QWORD *)&v191[2] = v141;
              v193 = *(_OWORD *)v191;
              v207 = v137(v140, &v193, &v194);
              v143 = *(volatile signed __int32 **)&v195[2];
              if ( *(_QWORD *)&v195[2] )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v195[2] + 8LL)) )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v143)(v143);
                  if ( !_InterlockedDecrement(v143 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v143 + 8LL))(v143);
                }
              }
              v144 = (volatile signed __int32 *)*((_QWORD *)&v198 + 1);
              if ( *((_QWORD *)&v198 + 1) )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v198 + 1) + 8LL)) )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v144)(v144);
                  if ( !_InterlockedDecrement(v144 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v144 + 8LL))(v144);
                }
              }
              LOBYTE(v190[0]) = 0;
              v145 = (__int64 *)std::make_unique_UsoScheduler_wchar_t_const_____25__std::chrono::duration_int_std::ratio_60_1______bool__RulesEngine::RunNextOperation_::_39_::_lambda_3__0_(
                                  v192,
                                  v142,
                                  &v207,
                                  v190);
              v39 = *v145;
              *v145 = 0;
              v146 = (UsoScheduler *)*((_QWORD *)this + 11);
              *((_QWORD *)this + 11) = v39;
              if ( v146 )
              {
                UsoScheduler::~UsoScheduler(v146);
                operator delete(v146, (const struct std::nothrow_t *)0x128);
              }
              v147 = v192[0];
              if ( v192[0] )
              {
                UsoScheduler::~UsoScheduler(v192[0]);
                operator delete(v147, (const struct std::nothrow_t *)0x128);
              }
            }
            goto LABEL_227;
          }
          v22 = v21 - 1;
          if ( !v22 )
          {
            *(_QWORD *)v191 = L"RulesOperation: Attempting to run one-time configuration tasks based on DEP OOBE Complete signal";
            *(_QWORD *)&v191[2] = 96;
            v193 = *(_OWORD *)v191;
            SystemInterface::Log<>(&v193);
            if ( !(unsigned __int8)anonymous_namespace_::IsFirstRunConfigurationNeeded() )
              goto LABEL_227;
            v96 = SystemInterface::Service::GetSystem((__int64 *)v195);
            v97 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v96 + 72LL))(*v96, &v193);
            v98 = *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v97 + 288LL))(*v97, &v204) + 8);
            v99 = (volatile signed __int32 *)*((_QWORD *)&v193 + 1);
            if ( *((_QWORD *)&v193 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v193 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
                if ( !_InterlockedDecrement(v99 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
              }
            }
            v100 = *(volatile signed __int32 **)&v195[2];
            if ( *(_QWORD *)&v195[2] )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v195[2] + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v100)(v100);
                if ( !_InterlockedDecrement(v100 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v100 + 8LL))(v100);
              }
            }
            if ( !v98 )
            {
              *(_QWORD *)v191 = L"Setting the USO cached OobeCompleteTimestamp";
              *(_QWORD *)&v191[2] = 44;
              v193 = *(_OWORD *)v191;
              SystemInterface::Log<>(&v193);
              v101 = SystemInterface::Service::GetSystem((__int64 *)&v199);
              v102 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v101 + 32LL))(*v101, &v197);
              v208[0] = 0;
              GetSystemTimePreciseAsFileTime(v208);
              v208[0] = (UsoScheduler *)(((unsigned __int64)HIDWORD(v208[0]) << 32)
                                       - 116444736000000000LL
                                       + LODWORD(v208[0]));
              v103 = -1;
              do
                ++v103;
              while ( SystemInterface::Registry::OOBE_TIMESTAMP[v103] );
              *(_QWORD *)v191 = SystemInterface::Registry::OOBE_TIMESTAMP;
              *(_QWORD *)&v191[2] = v103;
              v200 = 0;
              v201 = 0;
              v202 = 7;
              LOWORD(v200) = 0;
              v192[0] = (UsoScheduler *)&v200;
              v192[1] = 0;
              *(_QWORD *)&v194 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v104 = -1;
              do
                ++v104;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v104] );
              *((_QWORD *)&v194 + 1) = v104;
              v193 = *(_OWORD *)v191;
              *(_OWORD *)v195 = *(_OWORD *)v192;
              v198 = v194;
              SystemInterface::Registry::SetSystemTime(v102, &v198, (__int128 *)v195, &v193, v208);
              std::wstring::~wstring(&v200);
              v105 = (volatile signed __int32 *)*((_QWORD *)&v197 + 1);
              if ( *((_QWORD *)&v197 + 1) )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL)) )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v105)(v105);
                  if ( !_InterlockedDecrement(v105 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v105 + 8LL))(v105);
                }
              }
              v106 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
              if ( *((_QWORD *)&v199 + 1) )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v199 + 1) + 8LL)) )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v106)(v106);
                  if ( !_InterlockedDecrement(v106 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v106 + 8LL))(v106);
                }
              }
            }
            if ( !(unsigned __int8)anonymous_namespace_::IsScanBeforeInitialLogonNeeded() )
              goto LABEL_227;
            v107 = SystemInterface::Service::GetSystem((__int64 *)v195);
            v108 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v107 + 40LL))(*v107, &v193);
            LOBYTE(v109) = 1;
            (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v108 + 8LL))(*v108, v109);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v193);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v195);
            v110 = SystemInterface::Service::GetSystem((__int64 *)&v198);
            v111 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)*v110 + 40LL))(*v110, v195);
            v112 = *(_QWORD *)v111;
            v113 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v111 + 56LL);
            LODWORD(v194) = 1440;
            v193 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                &v204,
                                L"ScanBeforeInitialLogonDelayInMinutes");
            LODWORD(v112) = v113(v112, &v193, &v194);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v195);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v198);
            v114 = v112 + 1;
            LODWORD(v194) = v114;
            LOBYTE(v190[0]) = 0;
            v116 = (__int64 *)std::make_unique_UsoScheduler_wchar_t_const_____32__std::chrono::duration_int_std::ratio_60_1______bool__RulesEngine::RunNextOperation_::_48_::_lambda_4__0_(
                                v192,
                                v115,
                                &v194,
                                v190);
            v117 = *v116;
            *v116 = 0;
            v118 = (UsoScheduler *)*((_QWORD *)this + 13);
            *((_QWORD *)this + 13) = v117;
            if ( v118 )
            {
              UsoScheduler::~UsoScheduler(v118);
              operator delete(v118, (const struct std::nothrow_t *)0x128);
            }
            v119 = v192[0];
            if ( v192[0] )
            {
              UsoScheduler::~UsoScheduler(v192[0]);
              operator delete(v119, (const struct std::nothrow_t *)0x128);
            }
            v207 = 0;
            v208[0] = 0;
            v120 = *(__int64 (__fastcall ****)(_QWORD, GUID *, UsoScheduler **))anonymous_namespace_::GetUpdateManager(
                                                                                  v192,
                                                                                  L"RulesEngine - ScanBeforeLogonSetup",
                                                                                  &S1);
            v208[0] = 0;
            v121 = (**v120)(v120, &GUID_bf6ff983_c70b_49c5_8ac8_e4d895205f89, v208);
            if ( v121 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1C96,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
                (const char *)(unsigned int)v121,
                v188);
            if ( v192[0] )
              (*(void (__fastcall **)(UsoScheduler *))(*(_QWORD *)v192[0] + 16LL))(v192[0]);
            v122 = (*(__int64 (__fastcall **)(UsoScheduler *, int *))(*(_QWORD *)v208[0] + 304LL))(v208[0], &v207);
            if ( v122 >= 0 )
            {
              v123 = v207;
              *(_QWORD *)&v194 = *(_QWORD *)std::chrono::system_clock::now(&v194) + 864000000000LL * v123;
              v124 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v208[0] + 312LL);
              v125 = Windows::Time::to_filetime(&v194);
              v127 = v124(v126, v125);
              if ( v127 < 0 )
              {
                wil::details::in1diag3::Log_IfFailedWithExpected(
                  retaddr,
                  (void *)0x2C7,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                  (const char *)(unsigned int)v127,
                  1,
                  73,
                  v190[0]);
              }
              else
              {
                v128 = SystemInterface::Service::GetSystem((__int64 *)&v199);
                v129 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v128 + 32LL))(*v128, &v197);
                v130 = *(_QWORD *)v129;
                v131 = *(void (__fastcall **)(__int64, __int128 *, int *, __int128 *, __int128 *))(**(_QWORD **)v129
                                                                                                 + 64LL);
                LODWORD(v200) = 1;
                v203 = 0;
                v132 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                    &v204,
                                    L"ScanBeforeInitialLogonBlockFeatureUpdates");
                v133 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v194);
                *(_QWORD *)v191 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
                do
                  ++v14;
                while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v14] );
                *(_QWORD *)&v191[2] = v14;
                v193 = v132;
                *(_OWORD *)v195 = *v133;
                v198 = *(_OWORD *)v191;
                v131(v130, &v198, v195, &v193, &v200);
                if ( v203 != -1 && v203 && v203 != 1 )
                  std::wstring::~wstring(&v200);
                std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v197);
                std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v199);
              }
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2B5,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                (const char *)(unsigned int)v122,
                v188);
            }
            v134 = SystemInterface::Service::GetSystem((__int64 *)v195);
            v135 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v134 + 104LL))(*v134, &v193);
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v135 + 232LL))(*v135, v114);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v193);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v195);
            goto LABEL_64;
          }
          v23 = v22 - 1;
          if ( !v23 )
          {
            try
            {
              *(_QWORD *)v191 = L"RulesOperation: Performing a post-OOBE Expedited Apps Scan";
              *(_QWORD *)&v191[2] = 58;
              v193 = *(_OWORD *)v191;
              SystemInterface::Log<>(&v193);
              v92 = *(__int64 (__fastcall ****)(_QWORD, GUID *, UsoScheduler **))anonymous_namespace_::GetUpdateManager(
                                                                                   &v194,
                                                                                   L"OobeCompleteAppsScan",
                                                                                   &S1);
              v208[0] = 0;
              v93 = (**v92)(v92, &GUID_bf6ff983_c70b_49c5_8ac8_e4d895205f89, v208);
              if ( v93 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1C96,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wi"
                                "l\\result_macros.h",
                  (const char *)(unsigned int)v93,
                  v188);
              v94 = (*(__int64 (__fastcall **)(UsoScheduler *))(*(_QWORD *)v208[0] + 288LL))(v208[0]);
              if ( v94 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2D6,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                  (const char *)(unsigned int)v94,
                  v188);
              if ( v208[0] )
                (*(void (__fastcall **)(UsoScheduler *))(*(_QWORD *)v208[0] + 16LL))(v208[0]);
              if ( (_QWORD)v194 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v194 + 16LL))(v194);
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x2D8,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                v95);
              goto LABEL_227;
            }
            goto LABEL_227;
          }
          v24 = v23 - 1;
          if ( !v24 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveRulesEngineDowntimeEval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RemoveRulesEngineDowntimeEval>::GetImpl'::`2'::impl) )
            {
              *(_QWORD *)v191 = L"RulesOperation: Reevaluate Reboot Downtime";
              *(_QWORD *)&v191[2] = 42;
              v193 = *(_OWORD *)v191;
              SystemInterface::Log<>(&v193);
              RulesEngine::HandleRebootDowntimeSchedule(this);
            }
            goto LABEL_227;
          }
          if ( v24 == 1 )
          {
            v192[0] = (UsoScheduler *)L"RulesOperation: Attempting a database backup";
            v192[1] = (UsoScheduler *)44;
            *(_OWORD *)v191 = *(_OWORD *)v192;
            SystemInterface::Log<>(v191);
            if ( !*((_QWORD *)this + 12) )
            {
              v25 = SystemInterface::Service::GetSystem((__int64 *)&v194);
              v26 = *(__int64 (__fastcall **)(__int64, int *, int *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, UsoScheduler **))(*(_QWORD *)*v25 + 40LL))(
                                                                                     *v25,
                                                                                     v208)
                                                                    + 56LL);
              v207 = 7;
              v27 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                 L"DatabaseBackupCheckIntervalHours",
                                 word_1800FA612,
                                 0);
              if ( v27 == word_1800FA612
                || (v30 = ((char *)v27 - (char *)L"DatabaseBackupCheckIntervalHours") >> 1, v30 == -1) )
              {
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                  v28);
              }
              v192[0] = (UsoScheduler *)L"DatabaseBackupCheckIntervalHours";
              v192[1] = (UsoScheduler *)v30;
              *(_OWORD *)v191 = *(_OWORD *)v192;
              v32 = v26(v29, v191, &v207);
              v33 = (volatile signed __int32 *)v208[1];
              if ( v208[1] )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v208[1] + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
                  if ( !_InterlockedDecrement(v33 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
                }
              }
              v34 = (volatile signed __int32 *)*((_QWORD *)&v194 + 1);
              if ( *((_QWORD *)&v194 + 1) )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v194 + 1) + 8LL)) )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
                  if ( !_InterlockedDecrement(v34 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
                }
              }
              LOBYTE(v190[0]) = 1;
              v207 = v32;
              v35 = (__int64 *)std::make_unique_UsoScheduler_wchar_t_const_____15__std::chrono::duration_int_std::ratio_3600_1____bool__RulesEngine::RunNextOperation_::_16_::_lambda_2__0_(
                                 v208,
                                 v31,
                                 &v207,
                                 v190);
              v36 = *v35;
              *v35 = 0;
              v37 = (UsoScheduler *)*((_QWORD *)this + 12);
              *((_QWORD *)this + 12) = v36;
              if ( v37 )
              {
                UsoScheduler::~UsoScheduler(v37);
                operator delete(v37, (const struct std::nothrow_t *)0x128);
              }
              v38 = v208[0];
              if ( v208[0] )
              {
                UsoScheduler::~UsoScheduler(v208[0]);
                operator delete(v38, (const struct std::nothrow_t *)0x128);
              }
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048>::GetImpl'::`2'::impl) )
            {
              v64 = SystemInterface::Service::GetSystem((__int64 *)&v194);
              v65 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v64 + 32LL))(*v64, &v199);
              v66 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                      L"LastSuccessfulDatabaseBackup",
                      word_1800FA672,
                      0);
              if ( v66 == v68 || (v69 = (v66 - (__int64)L"LastSuccessfulDatabaseBackup") >> 1, v69 == -1) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                  v67);
              *(_QWORD *)v191 = L"LastSuccessfulDatabaseBackup";
              *(_QWORD *)&v191[2] = v69;
              v204 = 0;
              v205 = 0;
              v206 = 7;
              LOWORD(v204) = 0;
              v192[0] = (UsoScheduler *)&v204;
              v192[1] = 0;
              v208[0] = (UsoScheduler *)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v70 = -1;
              do
                ++v70;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v70] );
              v208[1] = (UsoScheduler *)v70;
              *(_OWORD *)v195 = *(_OWORD *)v191;
              v198 = *(_OWORD *)v192;
              v197 = *(_OWORD *)v208;
              SystemInterface::Registry::TryGetSystemTime(
                v65,
                (unsigned int)v192,
                (unsigned int)&v197,
                (unsigned int)&v198,
                (__int64)v195);
              std::wstring::~wstring(&v204);
              v71 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
              if ( *((_QWORD *)&v199 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v199 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
                  if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
                }
              }
              v72 = (volatile signed __int32 *)*((_QWORD *)&v194 + 1);
              if ( *((_QWORD *)&v194 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v194 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
                  if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
                }
              }
              v73 = SystemInterface::Service::GetSystem((__int64 *)&v197);
              v74 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v73 + 40LL))(*v73, &v198);
              v75 = *(_QWORD *)v74;
              v76 = *(__int64 (__fastcall **)(__int64, int *, int *))(**(_QWORD **)v74 + 56LL);
              v207 = 24;
              v77 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                 L"DatabaseBackupIntervalHours",
                                 L"RulesOperation: Setting a timer for 2 hours post DEP OOBE Complete",
                                 0);
              if ( v77 == L"RulesOperation: Setting a timer for 2 hours post DEP OOBE Complete"
                || (v80 = ((__int64)v77 - v79) >> 1, v80 == -1) )
              {
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                  v78);
              }
              *(_QWORD *)v191 = v79;
              *(_QWORD *)&v191[2] = v80;
              *(_OWORD *)v195 = *(_OWORD *)v191;
              v81 = v76(v75, v195, &v207);
              v82 = (volatile signed __int32 *)*((_QWORD *)&v198 + 1);
              if ( *((_QWORD *)&v198 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v198 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
                  if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
                }
              }
              v83 = (volatile signed __int32 *)*((_QWORD *)&v197 + 1);
              if ( *((_QWORD *)&v197 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
                  if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
                }
              }
              if ( LOBYTE(v192[1]) )
              {
                v208[0] = 0;
                GetSystemTimePreciseAsFileTime(v208);
                v84 = (UsoScheduler *)(LODWORD(v208[0])
                                     + ((unsigned __int64)HIDWORD(v208[0]) << 32)
                                     - 116444736000000000LL);
                v85 = v192[0];
                if ( v192[0] == v84 )
                  goto LABEL_92;
                if ( (__int64)v192[0] < (__int64)v84 )
                  v2 = -1;
                if ( v2 <= 0 )
                {
LABEL_92:
                  v87 = (__int64)(*(_QWORD *)std::chrono::system_clock::now(v192) - (_QWORD)v85);
                  v86 = v87 / 36000000000LL;
                  v39 = v87 % 36000000000LL;
                  if ( (_DWORD)v86 == v81 || (int)v86 < v81 )
                    goto LABEL_227;
                }
              }
              v208[0] = 0;
              CoreWorker = GetCoreWorker(&GUID_af2ba583_e24f_43f1_b92b_fc8125f93d16, (void **)v208);
              v57 = retaddr;
              if ( CoreWorker >= 0 )
              {
                CoreWorker = (*(__int64 (__fastcall **)(UsoScheduler *))(*(_QWORD *)v208[0] + 64LL))(v208[0]);
                v57 = retaddr;
                if ( CoreWorker >= 0 )
                {
                  v88 = SystemInterface::Service::GetSystem((__int64 *)&v193);
                  v89 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v88 + 32LL))(
                                     *v88,
                                     &v199);
                  v90 = (_QWORD *)std::chrono::system_clock::now(v192);
                  v91 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                     &v204,
                                     L"LastSuccessfulDatabaseBackup");
                  v200 = 0;
                  v201 = 0;
                  v202 = 7;
                  LOWORD(v200) = 0;
                  *(_QWORD *)v191 = &v200;
                  *(_QWORD *)&v191[2] = 0;
                  *(_QWORD *)&v194 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
                  do
                    ++v14;
                  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v14] );
                  *((_QWORD *)&v194 + 1) = v14;
                  *(_OWORD *)v195 = v91;
                  v198 = *(_OWORD *)v191;
                  v197 = v194;
                  SystemInterface::Registry::SetSystemTime(v89, &v197, &v198, (__int128 *)v195, v90);
                  std::wstring::~wstring(&v200);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v199);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v193);
                  goto LABEL_64;
                }
                v58 = 584;
              }
              else
              {
                v58 = 583;
              }
            }
            else
            {
              if ( IsCoreWorkerRunning() )
                goto LABEL_227;
              v40 = SystemInterface::Service::GetSystem((__int64 *)&v197);
              v41 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v40 + 32LL))(*v40, &v199);
              v42 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                      L"LastSuccessfulDatabaseBackup",
                      word_1800FA672,
                      0);
              if ( v42 == v44 || (v45 = (v42 - (__int64)L"LastSuccessfulDatabaseBackup") >> 1, v45 == -1) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                  v43);
              v192[0] = (UsoScheduler *)L"LastSuccessfulDatabaseBackup";
              v192[1] = (UsoScheduler *)v45;
              v204 = 0;
              v205 = 0;
              v206 = 7;
              LOWORD(v204) = 0;
              v208[0] = (UsoScheduler *)&v204;
              v208[1] = 0;
              *(_QWORD *)&v194 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v46 = -1;
              do
                ++v46;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v46] );
              *((_QWORD *)&v194 + 1) = v46;
              *(_OWORD *)v191 = *(_OWORD *)v192;
              *(_OWORD *)v192 = *(_OWORD *)v208;
              SystemInterface::Registry::TryGetSystemTime(
                v41,
                (unsigned int)v208,
                (unsigned int)&v194,
                (unsigned int)v192,
                (__int64)v191);
              std::wstring::~wstring(&v204);
              v47 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
              if ( *((_QWORD *)&v199 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v199 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
                  if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
                }
              }
              v48 = (volatile signed __int32 *)*((_QWORD *)&v197 + 1);
              if ( *((_QWORD *)&v197 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
                  if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
                }
              }
              v49 = SystemInterface::Service::GetSystem((__int64 *)v191);
              v50 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v49 + 40LL))(*v49, &v199);
              v51 = *(_QWORD *)v50;
              v52 = *(int (__fastcall **)(__int64, __int128 *, int *))(**(_QWORD **)v50 + 56LL);
              v207 = 24;
              v197 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                  &v193,
                                  L"DatabaseBackupIntervalHours");
              v53 = v52(v51, &v197, &v207);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v199);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v191);
              if ( LOBYTE(v208[1]) )
              {
                if ( !(unsigned __int8)Time::IsFuture(v208) )
                {
                  v54 = (_QWORD *)std::chrono::system_clock::now(v192);
                  v55 = *v54 - (unsigned __int64)v208[0];
                  if ( v55 == 36000000000LL * v53 || v55 < 36000000000LL * v53 )
                    goto LABEL_227;
                }
              }
              v208[0] = 0;
              CoreWorker = GetCoreWorker(&GUID_af2ba583_e24f_43f1_b92b_fc8125f93d16, (void **)v208);
              v57 = retaddr;
              if ( CoreWorker >= 0 )
              {
                CoreWorker = (*(__int64 (__fastcall **)(UsoScheduler *))(*(_QWORD *)v208[0] + 64LL))(v208[0]);
                v57 = retaddr;
                if ( CoreWorker >= 0 )
                {
                  v59 = SystemInterface::Service::GetSystem((__int64 *)v195);
                  v60 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v59 + 32LL))(
                                     *v59,
                                     &v198);
                  v61 = (_QWORD *)std::chrono::system_clock::now(v192);
                  v62 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                     &v193,
                                     L"LastSuccessfulDatabaseBackup");
                  v204 = 0;
                  v205 = 0;
                  v206 = 7;
                  LOWORD(v204) = 0;
                  *(_QWORD *)&v194 = &v204;
                  *((_QWORD *)&v194 + 1) = 0;
                  *(_QWORD *)v191 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
                  do
                    ++v14;
                  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v14] );
                  *(_QWORD *)&v191[2] = v14;
                  v197 = v62;
                  v199 = v194;
                  SystemInterface::Registry::SetSystemTime(v60, (__int128 *)v191, &v199, &v197, v61);
                  std::wstring::~wstring(&v204);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v198);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v195);
                  goto LABEL_64;
                }
                v58 = 611;
              }
              else
              {
                v58 = 610;
              }
            }
            wil::details::in1diag3::_Log_Hr(
              v57,
              (void *)v58,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
              (const char *)(unsigned int)CoreWorker,
              v189);
LABEL_64:
            v63 = v208[0];
LABEL_210:
            if ( v63 )
              (*(void (__fastcall **)(UsoScheduler *))(*(_QWORD *)v63 + 16LL))(v63);
            goto LABEL_227;
          }
LABEL_242:
          v186 = (const char *)(unsigned int)wil::verify_hresult(2149884179LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x335,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
            v186,
            v188);
        }
        *(_QWORD *)v191 = L"RulesOperation: Performing a Settings refresh";
        *(_QWORD *)&v191[2] = 45;
        v193 = *(_OWORD *)v191;
        SystemInterface::Log<>(&v193);
        RulesEngine::HandleSettingsRefresh(this);
        goto LABEL_227;
      }
      *(_QWORD *)v191 = L"RulesOperation: Starting Scan before Initial Logon";
      *(_QWORD *)&v191[2] = 50;
      v193 = *(_OWORD *)v191;
      SystemInterface::Log<>(&v193);
      v155 = (_QWORD *)anonymous_namespace_::GetUpdateManager(v192, L"ScanBeforeInitialLogon", &S1);
      v156 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v155 + 72LL))(*v155, 0, 0, 1);
      if ( v156 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EC,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
          (const char *)(unsigned int)v156,
          0);
      if ( v192[0] )
        (*(void (__fastcall **)(UsoScheduler *))(*(_QWORD *)v192[0] + 16LL))(v192[0]);
      v157 = SystemInterface::Service::GetSystem((__int64 *)&v199);
      v158 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v157 + 32LL))(*v157, &v197);
      v159 = -1;
      do
        ++v159;
      while ( SystemInterface::Registry::SCAN_BEFORE_INITIAL_LOGON_COMPLETED[v159] );
      *(_QWORD *)v191 = SystemInterface::Registry::SCAN_BEFORE_INITIAL_LOGON_COMPLETED;
      *(_QWORD *)&v191[2] = v159;
      v200 = 0;
      v201 = 0;
      v202 = 7;
      LOWORD(v200) = 0;
      v192[0] = (UsoScheduler *)&v200;
      v192[1] = 0;
      v208[0] = (UsoScheduler *)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v160 = -1;
      do
        ++v160;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v160] );
      v208[1] = (UsoScheduler *)v160;
      v193 = *(_OWORD *)v191;
      *(_OWORD *)v195 = *(_OWORD *)v192;
      v198 = *(_OWORD *)v208;
      SystemInterface::Registry::SetSystemBool(v158, &v198, (__int128 *)v195, &v193, 1u);
      std::wstring::~wstring(&v200);
      v161 = (volatile signed __int32 *)*((_QWORD *)&v197 + 1);
      if ( *((_QWORD *)&v197 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v161)(v161);
          if ( !_InterlockedDecrement(v161 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v161 + 8LL))(v161);
        }
      }
    }
    v162 = (volatile signed __int32 *)*((_QWORD *)&v199 + 1);
    if ( *((_QWORD *)&v199 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v199 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v162)(v162);
        if ( !_InterlockedDecrement(v162 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v162 + 8LL))(v162);
      }
    }
    goto LABEL_227;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x338,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x180014650  mov     rax, rsp
0x180014653  mov     [rax+10h], rbx
0x180014657  mov     [rax+18h], rsi
0x18001465b  mov     [rax+20h], rdi
0x18001465f  push    r13
0x180014661  push    r14
0x180014663  push    r15
0x180014665  sub     rsp, 150h
0x18001466c  movaps  xmmword ptr [rax-28h], xmm6
0x180014670  mov     rax, cs:__security_cookie
0x180014677  xor     rax, rsp
0x18001467a  mov     [rsp+168h+var_38], rax
0x180014682  mov     r14, rcx
0x180014685  xor     r13d, r13d
0x180014688  lea     r15d, [r13+1]
0x18001468c  mov     [rsp+168h+var_D7], r15b
0x180014694  mov     rbx, cs:?s_runOperationInfo@@3V?$shared_ptr@URunOperationInfo@@@std@@A; std::shared_ptr<RunOperationInfo> s_runOperationInfo
0x18001469b  mov     rcx, rbx
0x18001469e  call    mtx_do_lock
0x1800146a3  test    eax, eax
0x1800146a5  jnz     loc_18001633C
0x1800146ab  mov     eax, [rbx+4Ch]
0x1800146ae  cmp     eax, 7FFFFFFFh
0x1800146b3  jz      loc_180016345
0x1800146b9  mov     r8, cs:?s_runOperationInfo@@3V?$shared_ptr@URunOperationInfo@@@std@@A; std::shared_ptr<RunOperationInfo> s_runOperationInfo
0x1800146c0  cmp     [r8+78h], r13
0x1800146c4  jnz     short loc_1800146F2
0x1800146c6  sub     eax, 1
0x1800146c9  mov     [rbx+4Ch], eax
0x1800146cc  jnz     short loc_1800146E0
0x1800146ce  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800146d5  lea     rcx, [rbx+10h]; SRWLock
0x1800146d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800146df  nop
0x1800146e0  lea     rcx, [rsp+168h+var_D8]
0x1800146e8  call    wil__details__lambda_call__RulesEngine__RunNextOperation____3____lambda_1______lambda_call__RulesEngine__RunNextOperation____3____lambda_1___
0x1800146ed  jmp     loc_180016309
0x1800146f2  mov     r10, [r8+70h]
0x1800146f6  mov     rdx, r10
0x1800146f9  shr     rdx, 2
0x1800146fd  mov     rax, [r8+68h]
0x180014701  sub     rax, r15
0x180014704  and     rdx, rax
0x180014707  mov     rax, [r8+60h]
0x18001470b  mov     rcx, r10
0x18001470e  and     ecx, 3
0x180014711  mov     rax, [rax+rdx*8]
0x180014715  mov     edi, [rax+rcx*4]
0x180014718  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001471c  add     [r8+78h], rsi
0x180014720  mov     rax, r13
0x180014723  jz      short loc_180014729
0x180014725  lea     rax, [r10+1]
0x180014729  mov     [r8+70h], rax
0x18001472d  add     [rbx+4Ch], esi
0x180014730  jnz     short loc_18001473F
0x180014732  mov     [rbx+48h], esi
0x180014735  lea     rcx, [rbx+10h]; SRWLock
0x180014739  call    cs:__imp_ReleaseSRWLockExclusive
0x18001473f  cmp     edi, 0Ah
0x180014742  jg      loc_180015FC2
0x180014748  jz      loc_180015DAA
0x18001474e  sub     edi, 1
0x180014751  jz      loc_180015D1A
0x180014757  sub     edi, 1
0x18001475a  jz      loc_180015C8F
0x180014760  sub     edi, 1
0x180014763  jz      loc_180015C2E
0x180014769  sub     edi, 1
0x18001476c  jz      loc_180015BFA
0x180014772  sub     edi, 1
0x180014775  jz      loc_180015A39
0x18001477b  sub     edi, 1
0x18001477e  jz      loc_180015364
0x180014784  sub     edi, 1
0x180014787  jz      loc_18001528F
0x18001478d  sub     edi, 1
0x180014790  jz      loc_180015244
0x180014796  cmp     edi, 1
0x180014799  jnz     loc_18001646A
0x18001479f  lea     rax, aRulesoperation_8; "RulesOperation: Attempting a database b"...
0x1800147a6  mov     [rsp+168h+var_118], rax
0x1800147ab  mov     [rsp+168h+var_118+8], 2Ch ; ','
0x1800147b4  movaps  xmm0, xmmword ptr [rsp+168h+var_118]
0x1800147b9  movdqa  xmmword ptr [rsp+168h+var_128], xmm0
0x1800147bf  lea     rcx, [rsp+168h+var_128]
0x1800147c4  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800147c9  cmp     [r14+60h], r13
0x1800147cd  jnz     loc_180014960
0x1800147d3  lea     rcx, [rsp+168h+var_F8]
0x1800147d8  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800147dd  nop
0x1800147de  mov     rcx, [rax]
0x1800147e1  mov     rax, [rcx]
0x1800147e4  lea     rdx, [rsp+168h+var_48]
0x1800147ec  mov     rax, [rax+28h]
0x1800147f0  call    _guard_dispatch_icall
0x1800147f5  nop
0x1800147f6  mov     r11, [rax]
0x1800147f9  mov     rax, [r11]
0x1800147fc  mov     rbx, [rax+38h]
0x180014800  mov     [rsp+168h+var_50], 7
0x18001480b  xor     r8d, r8d
0x18001480e  lea     rdi, word_1800FA612
0x180014815  mov     rdx, rdi
0x180014818  lea     rcx, aDatabasebackup; "DatabaseBackupCheckIntervalHours"
0x18001481f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180014824  cmp     rax, rdi
0x180014827  jz      loc_180016355
0x18001482d  lea     rcx, aDatabasebackup; "DatabaseBackupCheckIntervalHours"
0x180014834  sub     rax, rcx
0x180014837  sar     rax, 1
0x18001483a  cmp     rax, rsi
0x18001483d  jz      loc_180016355
0x180014843  mov     [rsp+168h+var_118], rcx
0x180014848  mov     [rsp+168h+var_118+8], rax
0x18001484d  movaps  xmm0, xmmword ptr [rsp+168h+var_118]
0x180014852  movdqa  xmmword ptr [rsp+168h+var_128], xmm0
0x180014858  lea     r8, [rsp+168h+var_50]
0x180014860  lea     rdx, [rsp+168h+var_128]
0x180014865  mov     rcx, r11
0x180014868  mov     rax, rbx
0x18001486b  call    _guard_dispatch_icall
0x180014870  mov     edi, eax
0x180014872  mov     rbx, [rsp+168h+var_48+8]
0x18001487a  test    rbx, rbx
0x18001487d  jz      short loc_1800148B3
0x18001487f  mov     ecx, esi
0x180014881  lock xadd [rbx+8], ecx
0x180014886  add     ecx, esi
0x180014888  jnz     short loc_1800148B3
0x18001488a  mov     rax, [rbx]
0x18001488d  mov     rcx, rbx
0x180014890  mov     rax, [rax]
0x180014893  call    _guard_dispatch_icall
0x180014898  mov     eax, esi
0x18001489a  lock xadd [rbx+0Ch], eax
0x18001489f  add     eax, esi
0x1800148a1  jnz     short loc_1800148B3
0x1800148a3  mov     rax, [rbx]
0x1800148a6  mov     rcx, rbx
0x1800148a9  mov     rax, [rax+8]
0x1800148ad  call    _guard_dispatch_icall
0x1800148b2  nop
0x1800148b3  mov     rbx, qword ptr [rsp+168h+var_F8+8]
0x1800148b8  test    rbx, rbx
0x1800148bb  jz      short loc_1800148F0
0x1800148bd  mov     eax, esi
0x1800148bf  lock xadd [rbx+8], eax
0x1800148c4  add     eax, esi
0x1800148c6  jnz     short loc_1800148F0
0x1800148c8  mov     rax, [rbx]
0x1800148cb  mov     rcx, rbx
0x1800148ce  mov     rax, [rax]
0x1800148d1  call    _guard_dispatch_icall
0x1800148d6  mov     eax, esi
0x1800148d8  lock xadd [rbx+0Ch], eax
0x1800148dd  add     eax, esi
0x1800148df  jnz     short loc_1800148F0
0x1800148e1  mov     rax, [rbx]
0x1800148e4  mov     rcx, rbx
0x1800148e7  mov     rax, [rax+8]
0x1800148eb  call    _guard_dispatch_icall
0x1800148f0  mov     [rsp+168h+var_138], r15b
0x1800148f5  mov     [rsp+168h+var_50], edi
0x1800148fc  lea     r9, [rsp+168h+var_138]
0x180014901  lea     r8, [rsp+168h+var_50]
0x180014909  lea     rcx, [rsp+168h+var_48]
0x180014911  call    std__make_unique_UsoScheduler_wchar_t_const_____15__std__chrono__duration_int_std__ratio_3600_1____bool__RulesEngine__RunNextOperation____16____lambda_2__0_
0x180014916  mov     rcx, [rax]
0x180014919  mov     [rax], r13
0x18001491c  mov     rbx, [r14+60h]
0x180014920  mov     [r14+60h], rcx
0x180014924  test    rbx, rbx
0x180014927  jz      short loc_18001493E
0x180014929  mov     rcx, rbx; this
0x18001492c  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180014931  mov     edx, 128h; struct std::nothrow_t *
0x180014936  mov     rcx, rbx; void *
0x180014939  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001493e  mov     rbx, [rsp+168h+var_48]
0x180014946  test    rbx, rbx
0x180014949  jz      short loc_180014960
0x18001494b  mov     rcx, rbx; this
0x18001494e  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180014953  mov     edx, 128h; struct std::nothrow_t *
0x180014958  mov     rcx, rbx; void *
0x18001495b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014960  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048>::GetImpl(void)'::`2'::impl
0x180014967  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UsoDatabaseBackup_49669048>::__private_IsEnabled(void)
0x18001496c  test    al, al
0x18001496e  jnz     loc_180014D78
0x180014974  call    ?IsCoreWorkerRunning@@YA_NXZ; IsCoreWorkerRunning(void)
0x180014979  test    al, al
0x18001497b  jnz     loc_1800162FB
0x180014981  lea     rcx, [rsp+168h+var_C8]
0x180014989  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18001498e  nop
0x18001498f  mov     rcx, [rax]
0x180014992  mov     rax, [rcx]
0x180014995  lea     rdx, [rsp+168h+var_A8]
0x18001499d  mov     rax, [rax+20h]
0x1800149a1  call    _guard_dispatch_icall
0x1800149a6  nop
0x1800149a7  mov     rbx, [rax]
0x1800149aa  xor     r8d, r8d
0x1800149ad  lea     r11, word_1800FA672
0x1800149b4  mov     rdx, r11
0x1800149b7  lea     r14, aLastsuccessful; "LastSuccessfulDatabaseBackup"
0x1800149be  mov     rcx, r14
0x1800149c1  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800149c6  cmp     rax, r11
0x1800149c9  jz      loc_18001636F
0x1800149cf  sub     rax, r14
0x1800149d2  sar     rax, 1
0x1800149d5  cmp     rax, rsi
0x1800149d8  jz      loc_18001636F
0x1800149de  mov     [rsp+168h+var_118], r14
0x1800149e3  mov     [rsp+168h+var_118+8], rax
0x1800149e8  xorps   xmm0, xmm0
0x1800149eb  movups  [rsp+168h+var_70], xmm0
0x1800149f3  mov     [rsp+168h+var_60], r13
0x1800149fb  mov     [rsp+168h+var_58], 7
0x180014a07  mov     word ptr [rsp+168h+var_70], r13w
0x180014a10  lea     rax, [rsp+168h+var_70]
0x180014a18  mov     [rsp+168h+var_48], rax
0x180014a20  mov     [rsp+168h+var_48+8], r13
0x180014a28  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180014a2f  mov     qword ptr [rsp+168h+var_F8], rcx
0x180014a34  mov     rax, rsi
0x180014a37  inc     rax
0x180014a3a  cmp     [rcx+rax*2], r13w
0x180014a3f  jnz     short loc_180014A37
0x180014a41  mov     qword ptr [rsp+168h+var_F8+8], rax
0x180014a46  movups  xmm0, xmmword ptr [rsp+168h+var_118]
0x180014a4b  movdqu  xmmword ptr [rsp+168h+var_128], xmm0
0x180014a51  movups  xmm1, xmmword ptr [rsp+168h+var_48]
0x180014a59  movdqu  xmmword ptr [rsp+168h+var_118], xmm1
0x180014a5f  movaps  xmm0, [rsp+168h+var_F8]
0x180014a64  movdqa  [rsp+168h+var_F8], xmm0
0x180014a6a  lea     rax, [rsp+168h+var_128]
0x180014a6f  mov     qword ptr [rsp+168h+var_148], rax; int
0x180014a74  lea     r9, [rsp+168h+var_118]
0x180014a79  lea     r8, [rsp+168h+var_F8]
0x180014a7e  lea     rdx, [rsp+168h+var_48]
0x180014a86  mov     rcx, rbx
0x180014a89  call    ?TryGetSystemTime@Registry@SystemInterface@@QEAA?AV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@V?$basic_zstring_view@_W@wil@@00@Z; SystemInterface::Registry::TryGetSystemTime(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180014a8e  nop
0x180014a8f  lea     rcx, [rsp+168h+var_70]; void *
0x180014a97  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014a9c  nop
0x180014a9d  mov     rbx, qword ptr [rsp+168h+var_A8+8]
0x180014aa5  test    rbx, rbx
0x180014aa8  jz      short loc_180014ADE
0x180014aaa  mov     eax, esi
0x180014aac  lock xadd [rbx+8], eax
0x180014ab1  add     eax, esi
0x180014ab3  jnz     short loc_180014ADE
0x180014ab5  mov     rax, [rbx]
0x180014ab8  mov     rcx, rbx
0x180014abb  mov     rax, [rax]
0x180014abe  call    _guard_dispatch_icall
0x180014ac3  mov     eax, esi
0x180014ac5  lock xadd [rbx+0Ch], eax
0x180014aca  add     eax, esi
0x180014acc  jnz     short loc_180014ADE
0x180014ace  mov     rax, [rbx]
0x180014ad1  mov     rcx, rbx
0x180014ad4  mov     rax, [rax+8]
0x180014ad8  call    _guard_dispatch_icall
0x180014add  nop
0x180014ade  mov     rbx, qword ptr [rsp+168h+var_C8+8]
0x180014ae6  test    rbx, rbx
0x180014ae9  jz      short loc_180014B1E
0x180014aeb  mov     eax, esi
0x180014aed  lock xadd [rbx+8], eax
0x180014af2  add     eax, esi
0x180014af4  jnz     short loc_180014B1E
0x180014af6  mov     rax, [rbx]
0x180014af9  mov     rcx, rbx
0x180014afc  mov     rax, [rax]
0x180014aff  call    _guard_dispatch_icall
0x180014b04  mov     eax, esi
0x180014b06  lock xadd [rbx+0Ch], eax
0x180014b0b  add     eax, esi
0x180014b0d  jnz     short loc_180014B1E
0x180014b0f  mov     rax, [rbx]
0x180014b12  mov     rcx, rbx
0x180014b15  mov     rax, [rax+8]
0x180014b19  call    _guard_dispatch_icall
0x180014b1e  lea     rcx, [rsp+168h+var_128]
0x180014b23  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180014b28  nop
0x180014b29  mov     rcx, [rax]
0x180014b2c  mov     rax, [rcx]
0x180014b2f  lea     rdx, [rsp+168h+var_A8]
0x180014b37  mov     rax, [rax+28h]
0x180014b3b  call    _guard_dispatch_icall
0x180014b40  nop
0x180014b41  mov     rdi, [rax]
  ... truncated ...
```
