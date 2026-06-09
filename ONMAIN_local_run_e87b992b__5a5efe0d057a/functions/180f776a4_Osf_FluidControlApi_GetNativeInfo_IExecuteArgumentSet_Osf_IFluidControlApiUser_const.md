# Osf::FluidControlApi::GetNativeInfo(IExecuteArgumentSet *,Osf::IFluidControlApiUser const *)

- ea: `0x180f776a4`
- end: `0x180f78a97`
- name: `?GetNativeInfo@FluidControlApi@Osf@@CAXPEAUIExecuteArgumentSet@@PEBUIFluidControlApiUser@2@@Z`
- size: `5107`
- prototype: `void __fastcall(struct IExecuteArgumentSet *, const struct Osf::IFluidControlApiUser *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1808e4714`

## callees

- `0x18002d954`
- `0x18002e214`
- `0x18002e308`
- `0x18006eaec`
- `0x180094190`
- `0x180094440`
- `0x18009456c`
- `0x180164b00`
- `0x18019b8ac`
- `0x1802e2190`
- `0x1802e5170`
- `0x1802e5190`
- `0x180389390`
- `0x1803ac6f8`
- `0x1804cf3dc`
- `0x1804cfa30`
- `0x18059e664`
- `0x1806c2130`
- `0x1807e7004`
- `0x18080cab0`
- `0x1809134f8`
- `0x180f76b14`
- `0x180f776a4`
- `0x180f78bc0`
- `0x180f79260`
- `0x180f79350`
- `0x180f7a474`
- `0x180f7a900`

## import_xrefs

- `Mso30Win32Client!__imp_?CreateConfigUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@VMsoReserveTag@@W4URL@ConfigURL@12@@Z` at `0x180f77964`
- `Mso30Win32Client!__imp_?CreateConfigUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@VMsoReserveTag@@W4URL@ConfigURL@12@@Z` at `0x180f77964`
- `Mso30Win32Client!__imp_?IsOneAuthEnabled@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x180f787e5`
- `Mso30Win32Client!__imp_?IsOneAuthEnabled@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x180f787e5`
- `Mso20Win32Client!__imp_?GetChannel@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f7784c`
- `Mso20Win32Client!__imp_?GetChannel@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f7784c`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f788cc`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f788cc`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f7846b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f784eb`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f786a6`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f78798`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f7846b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f784eb`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f786a6`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f78798`
- `Mso20Win32Client!__imp_?GetAudienceGroup@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f777c9`
- `Mso20Win32Client!__imp_?GetAudienceGroup@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ` at `0x180f777c9`
- `Mso20Win32Client!__imp_?CreateJsonWriter@Json@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@2@XZ` at `0x180f776e9`
- `Mso20Win32Client!__imp_?CreateJsonWriter@Json@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@2@XZ` at `0x180f776e9`

## string_xrefs

- `0x180f77d9e`: `isReadOnly`
- `0x180f780f0`: `linkUrl`
- `0x180f77b21`: `Invalid json for OEP.FluidHost.FluidSettingOverrides`
- `0x180f77de2`: `loopComponentPropertiesAreEnabled`
- `0x180f77d5a`: `linkProblemState`
- `0x180f77e68`: `createParams`
- `0x180f782cf`: `manifestData`
- `0x180f7839a`: `safeLinkWrappedUrl`
- `0x180f78803`: `useTokenCache`
- `0x180f78098`: `linkText`

## pseudocode

```c
void __fastcall Osf::FluidControlApi::GetNativeInfo(
        struct IExecuteArgumentSet *a1,
        const struct Osf::IFluidControlApiUser *a2,
        int a3)
{
  __int64 v5; // rdi
  char v6; // r15
  char v7; // bl
  char v8; // r12
  const struct Osf::LoopInfo *v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // r8
  char *v12; // r8
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  void (__fastcall *v17)(__int64, _QWORD *); // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // r8
  char *v20; // r8
  _QWORD *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r8
  void (__fastcall *v25)(__int64, _QWORD *); // rax
  _QWORD *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // r8
  void (__fastcall *v38)(__int64, struct tagVARIANT *); // rax
  struct tagVARIANT *v39; // rdx
  __int64 v40; // rax
  int v41; // r9d
  __int64 v42; // rax
  _QWORD *v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // r8
  void (__fastcall *v49)(__int64, _QWORD *); // rax
  _QWORD *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // r8
  void (__fastcall *v54)(__int64, _QWORD *); // rax
  _QWORD *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  bool IsOptionalConnectedExperiencesEnabled; // bl
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rax
  bool v82; // bl
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rbx
  void (__fastcall *v86)(__int64, _QWORD *); // rdi
  _QWORD *v87; // rax
  bool v88; // bl
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rbx
  void (__fastcall *v92)(__int64, _QWORD *); // rdi
  _QWORD *v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // r8
  void (__fastcall *v103)(__int64, _QWORD *); // rax
  _QWORD *v104; // rdx
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // r8
  void (__fastcall *v108)(__int64, _QWORD *); // rax
  _QWORD *v109; // rdx
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // r8
  void (__fastcall *v113)(__int64, _QWORD *); // rax
  _QWORD *v114; // rdx
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // r8
  void (__fastcall *v118)(__int64, _QWORD *); // rax
  _QWORD *v119; // rdx
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // r8
  void (__fastcall *v123)(__int64, _QWORD *); // rax
  _QWORD *v124; // rdx
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // r8
  void (__fastcall *v128)(__int64, _QWORD *); // rax
  _QWORD *v129; // rdx
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // r8
  void (__fastcall *v133)(__int64, _QWORD *); // rax
  _QWORD *v134; // rdx
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // r8
  void (__fastcall *v138)(__int64, _QWORD *); // rax
  _QWORD *v139; // rdx
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // r8
  void (__fastcall *v143)(__int64, _QWORD *); // rax
  _QWORD *v144; // rdx
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rbx
  __int64 v148; // rax
  char v149; // al
  bool v150; // cl
  char v151; // bl
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rdx
  bool v155; // al
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 *v158; // rbx
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 **v161; // rax
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // rax
  __int64 v167; // rdi
  void (__fastcall *v168)(__int64, _QWORD); // rbx
  int TelemetryBatchDuration; // eax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rdx
  bool v173; // al
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rdx
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rdx
  Mso::Authentication::IdentityFlights *v183; // rcx
  bool v184; // al
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rdx
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // rdx
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rdi
  void (__fastcall *v194)(__int64, struct tagVARIANT *); // rbx
  __int64 v195; // rax
  struct tagVARIANT *v196; // rdx
  bool v197; // al
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rbx
  void (__fastcall *v201)(__int64, _QWORD *); // rdi
  _QWORD *v202; // rax
  __int64 v203; // rax
  __int64 v204; // rax
  int v205; // edx
  const wchar_t *v206; // r8
  __int64 v207; // rcx
  __int64 v208; // [rsp+30h] [rbp-D0h] BYREF
  char v209; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v210; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v211; // [rsp+48h] [rbp-B8h] BYREF
  struct tagVARIANT v212; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v213; // [rsp+68h] [rbp-98h]
  _QWORD v214[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v215; // [rsp+88h] [rbp-78h]
  _QWORD v216[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v217; // [rsp+A8h] [rbp-58h]
  wchar_t *v218[2]; // [rsp+B0h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-40h]
  _QWORD v220[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v221[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v222[4]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v223[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v224[4]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v225[4]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v226[4]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v227[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v228[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v229[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v230[4]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v231[4]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v232[4]; // [rsp+250h] [rbp+150h] BYREF
  char v233; // [rsp+270h] [rbp+170h]
  _BYTE v234[42]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v235[6]; // [rsp+2AAh] [rbp+1AAh] BYREF

  Osf::CSafeArrayWriter::CSafeArrayWriter((Osf::CSafeArrayWriter *)&v210, (int)a2, a3);
  Mso::Json::CreateJsonWriter(&v208);
  *(_OWORD *)v218 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v218[0]) = 0;
  v5 = (*(int (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 136LL))(a2);
  v6 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 144LL))(a2);
  (*(void (__fastcall **)(const struct Osf::IFluidControlApiUser *, _QWORD *))(*(_QWORD *)a2 + 128LL))(a2, v223);
  v7 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 192LL))(a2);
  v8 = (**(__int64 (__fastcall ***)(const struct Osf::IFluidControlApiUser *))a2)(a2);
  (*(void (__fastcall **)(const struct Osf::IFluidControlApiUser *, _QWORD *))(*(_QWORD *)a2 + 8LL))(a2, v222);
  v9 = (const struct Osf::LoopInfo *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 152LL))(a2);
  Osf::LoopInfo::LoopInfo((Osf::LoopInfo *)v224, v9);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  Mso::AudienceApi::GetAudienceGroup(v216);
  v11 = v216;
  if ( v217 > 0xF )
    v11 = (_QWORD *)v216[0];
  v12 = (char *)v11 + v216[2];
  v13 = v216;
  if ( v217 > 0xF )
    v13 = (_QWORD *)v216[0];
  std::wstring::wstring(v221, v13, v12);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v14 + 48LL))(v14, L"audienceGroup");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  v16 = v15;
  v17 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v15 + 56LL);
  v18 = v221;
  if ( v221[3] > 7u )
    v18 = (_QWORD *)v221[0];
  v17(v16, v18);
  Mso::AudienceApi::GetChannel(v214);
  v19 = v214;
  if ( v215 > 0xF )
    v19 = (_QWORD *)v214[0];
  v20 = (char *)v19 + v214[2];
  v21 = v214;
  if ( v215 > 0xF )
    v21 = (_QWORD *)v214[0];
  std::wstring::wstring(v220, v21, v20);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v22 + 48LL))(v22, L"channel");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  v24 = v23;
  v25 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v23 + 56LL);
  v26 = v220;
  if ( v220[3] > 7u )
    v26 = (_QWORD *)v220[0];
  v25(v24, v26);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v27 + 48LL))(v27, L"enableRightToLeftSplashScreen");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v29) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 64LL))(v28, v29);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v30 + 48LL))(v30, L"enableShowLoopGlowBorderEvent");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v32) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 64LL))(v31, v32);
  Mso::OfficeWebServiceApi::CreateConfigUrlBuilder(&v211, 504673955, 358);
  if ( v211 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v211);
    v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 160LL))(v33);
    std::wstring::wstring(&v212, v34);
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v35 + 48LL))(v35, L"graphEndpoint");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v37 = v36;
    v38 = *(void (__fastcall **)(__int64, struct tagVARIANT *))(*(_QWORD *)v36 + 56LL);
    v39 = &v212;
    if ( v213 > 7 )
      v39 = *(struct tagVARIANT **)&v212.vt;
    v38(v37, v39);
    std::wstring::~wstring(&v212);
  }
  if ( dword_1815BAC20 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_1815BAC20);
    if ( dword_1815BAC20 == -1 )
    {
      std::wstring::wstring(v234, &WindowName);
      *(_QWORD *)&v212.vt = "FluidHost.FluidSettingOverrides";
      v209 = 52;
      Mso::AB::Optimized::Setting<std::wstring>::Setting<std::wstring>(
        (unsigned int)qword_1815BAC30,
        (unsigned int)&v209,
        (unsigned int)&v212,
        (unsigned int)v234,
        0);
      std::wstring::~wstring(v234);
      atexit(sub_1808B8AC0);
      Init_thread_footer(&dword_1815BAC20);
    }
  }
  if ( *(_QWORD *)(Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(qword_1815BAC30) + 16) )
  {
    v40 = Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(qword_1815BAC30);
    if ( *(_QWORD *)(v40 + 24) > 7u )
      v40 = *(_QWORD *)v40;
    if ( Osf::FluidControlApi::IsValidJson((const wchar_t *)v40) )
    {
      Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
      (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v42 + 48LL))(v42, L"fluidSettingOverrides");
      v43 = (_QWORD *)Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(qword_1815BAC30);
      if ( v43[3] > 7u )
        v43 = (_QWORD *)*v43;
      Osf::FluidControlApi::WriteJson(&v208, v43);
    }
    else
    {
      *(_QWORD *)&v212.vt = "Invalid json for OEP.FluidHost.FluidSettingOverrides";
      Mso::Diagnostics::SendDiagnosticTrace<>(512340195, 2489, 10, v41, (__int64)&v212);
    }
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v44 + 48LL))(v44, L"host");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v45 + 56LL))(v45, L"fluidControlApi");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v46 + 48LL))(v46, L"hydrateId");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  v48 = v47;
  v49 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v47 + 56LL);
  v50 = v223;
  if ( v223[3] > 7u )
    v50 = (_QWORD *)v223[0];
  v49(v48, v50);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v51 + 48LL))(v51, L"hydrateScenarioEntryPoint");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  v53 = v52;
  v54 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v52 + 56LL);
  v55 = v222;
  if ( v222[3] > 7u )
    v55 = (_QWORD *)v222[0];
  v54(v53, v55);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v56 + 48LL))(v56, L"isCardChannelProviderEnabled");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v58) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 64LL))(v57, v58);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v59 + 48LL))(v59, L"isDarkBackground");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v61) = v7;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 64LL))(v60, v61);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v62 + 48LL))(v62, L"isInEditableDocument");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v64) = v8;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 64LL))(v63, v64);
  IsOptionalConnectedExperiencesEnabled = Osf::FluidControlApi::IsOptionalConnectedExperiencesEnabled();
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v66 + 48LL))(
    v66,
    L"isOptionalConnectedExperiencesEnabled");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v68) = IsOptionalConnectedExperiencesEnabled;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 64LL))(v67, v68);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v69 + 48LL))(v69, L"linkProblemState");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 72LL))(v70, v5);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v71 + 48LL))(v71, L"isReadOnly");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v73) = v6;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 64LL))(v72, v73);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v74 + 48LL))(v74, L"loopComponentPropertiesAreEnabled");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v76) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v75 + 64LL))(v75, v76);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v77 + 48LL))(v77, L"useLoopContentWidthEnabled");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v79) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 64LL))(v78, v79);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v80 + 48LL))(v80, L"createParams");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  v82 = *(_QWORD *)((*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 112LL))(
                      a2,
                      v234)
                  + 16) != 0;
  std::wstring::~wstring(v234);
  if ( v82 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v83 + 48LL))(v83, L"loopFileName");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v85 = v84;
    v86 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v84 + 56LL);
    v87 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 112LL))(
                      a2,
                      v234);
    if ( v87[3] > 7u )
      v87 = (_QWORD *)*v87;
    v86(v85, v87);
    std::wstring::~wstring(v234);
  }
  v88 = *(_QWORD *)((*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 120LL))(
                      a2,
                      v234)
                  + 16) != 0;
  std::wstring::~wstring(v234);
  if ( v88 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v89 + 48LL))(v89, L"loopFolderName");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v91 = v90;
    v92 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v90 + 56LL);
    v93 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 120LL))(
                      a2,
                      v234);
    if ( v93[3] > 7u )
      v93 = (_QWORD *)*v93;
    v92(v91, v93);
    std::wstring::~wstring(v234);
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 24LL))(v94);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v95 + 48LL))(v95, L"loopInfo");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v97 + 48LL))(v97, L"isFluidLoop");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v99) = v233;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v98 + 64LL))(v98, v99);
  if ( v224[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v100 + 48LL))(v100, L"linkText");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v102 = v101;
    v103 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v101 + 56LL);
    v104 = v224;
    if ( v224[3] > 7u )
      v104 = (_QWORD *)v224[0];
    v103(v102, v104);
  }
  if ( v225[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v105 + 48LL))(v105, L"linkUrl");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v107 = v106;
    v108 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v106 + 56LL);
    v109 = v225;
    if ( v225[3] > 7u )
      v109 = (_QWORD *)v225[0];
    v108(v107, v109);
  }
  if ( v226[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v110 + 48LL))(v110, L"loopData");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v112 = v111;
    v113 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v111 + 56LL);
    v114 = v226;
    if ( v226[3] > 7u )
      v114 = (_QWORD *)v226[0];
    v113(v112, v114);
  }
  if ( v227[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v115 + 48LL))(v115, L"loopIconUrl");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v117 = v116;
    v118 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v116 + 56LL);
    v119 = v227;
    if ( v227[3] > 7u )
      v119 = (_QWORD *)v227[0];
    v118(v117, v119);
  }
  if ( v228[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v120 + 48LL))(v120, L"loopName");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v122 = v121;
    v123 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v121 + 56LL);
    v124 = v228;
    if ( v228[3] > 7u )
      v124 = (_QWORD *)v228[0];
    v123(v122, v124);
  }
  if ( v229[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v125 + 48LL))(v125, L"loopTitle");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v127 = v126;
    v128 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v126 + 56LL);
    v129 = v229;
    if ( v229[3] > 7u )
      v129 = (_QWORD *)v229[0];
    v128(v127, v129);
  }
  if ( v230[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v130 + 48LL))(v130, L"manifestData");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v132 = v131;
    v133 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v131 + 56LL);
    v134 = v230;
    if ( v230[3] > 7u )
      v134 = (_QWORD *)v230[0];
    v133(v132, v134);
  }
  if ( v231[2] )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v135 + 48LL))(v135, L"registrationId");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v137 = v136;
    v138 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v136 + 56LL);
    v139 = v231;
    if ( v231[3] > 7u )
      v139 = (_QWORD *)v231[0];
    v138(v137, v139);
  }
  if ( v232[2] && !v233 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v140 + 48LL))(v140, L"safeLinkWrappedUrl");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v142 = v141;
    v143 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v141 + 56LL);
    v144 = v232;
    if ( v232[3] > 7u )
      v144 = (_QWORD *)v232[0];
    v143(v142, v144);
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v145 + 24LL))(v145);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v146 + 48LL))(v146, L"scenarioStartTime");
  v147 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 160LL))(a2);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v148 + 80LL))(v148, v147);
  v149 = byte_18154C6E8;
  if ( byte_18154C6E8 < 0 )
  {
    v150 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C6E8);
    v149 = byte_18154C6E8;
  }
  else
  {
    v150 = byte_18154C6E8 != 0;
  }
  if ( v150 )
  {
    v151 = (*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *))(*(_QWORD *)a2 + 216LL))(a2);
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v152 + 48LL))(v152, L"showTeachingCallout");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    LOBYTE(v154) = v151;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v153 + 64LL))(v153, v154);
    v149 = byte_18154C6E8;
  }
  if ( v149 < 0 )
    v155 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C6E8);
  else
    v155 = v149 != 0;
  if ( v155 )
  {
    GetTeachingCalloutColors(&v212);
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v156 + 48LL))(v156, L"teachingCalloutColors");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
    v158 = **(__int64 ***)&v212.vt;
    while ( !*((_BYTE *)v158 + 25) )
    {
      Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v159 + 48LL))(v159, v158[4]);
      Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v160 + 72LL))(v160, *((unsigned int *)v158 + 10));
      v161 = (__int64 **)v158[2];
      if ( *((_BYTE *)v161 + 25) )
      {
        for ( i = (__int64 *)v158[1]; !*((_BYTE *)i + 25) && v158 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v158 = i;
        v158 = i;
      }
      else
      {
        v158 = (__int64 *)v158[2];
        for ( j = *v161; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v158 = j;
      }
    }
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v164 + 24LL))(v164);
    std::_Tree<std::_Tset_traits<Jot::CGraphDiffOperation *,std::less<Jot::CGraphDiffOperation *>,std::allocator<Jot::CGraphDiffOperation *>,0>>::~_Tree<std::_Tset_traits<Jot::CGraphDiffOperation *,std::less<Jot::CGraphDiffOperation *>,std::allocator<Jot::CGraphDiffOperation *>,0>>(&v212);
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v165 + 48LL))(v165, L"telemetryBatchDurationMs");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  v167 = v166;
  v168 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v166 + 72LL);
  TelemetryBatchDuration = Osf::FluidControlApi::GetTelemetryBatchDuration();
  v168(v167, TelemetryBatchDuration);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v170 + 48LL))(v170, L"useDevicePixelRatio");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v172) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v171 + 64LL))(v171, v172);
  if ( byte_18154C7C8 < 0 )
    v173 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C7C8);
  else
    v173 = byte_18154C7C8 != 0;
  if ( v173 || !v233 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v174 + 48LL))(v174, L"useGenericLoader");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    LOBYTE(v176) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v175 + 64LL))(v175, v176);
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v177 + 48LL))(v177, L"useLoopBrand");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v179) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v178 + 64LL))(v178, v179);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v180 + 48LL))(v180, L"useNewAnimatedSplashScreen");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  LOBYTE(v182) = 1;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v181 + 64LL))(v181, v182);
  if ( byte_18154C7D8 < 0 )
    v184 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18154C7D8);
  else
    v184 = byte_18154C7D8 != 0;
  if ( v184 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v185 + 48LL))(v185, L"consoleLogEnabled");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    LOBYTE(v187) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v186 + 64LL))(v186, v187);
  }
  if ( Mso::Authentication::IdentityFlights::IsOneAuthEnabled(v183) )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v188 + 48LL))(v188, L"useTokenCache");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    LOBYTE(v190) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v189 + 64LL))(v189, v190);
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v191 + 48LL))(v191, L"version");
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  v193 = v192;
  v194 = *(void (__fastcall **)(__int64, struct tagVARIANT *))(*(_QWORD *)v192 + 56LL);
  v195 = std::_UIntegral_to_buff<wchar_t,unsigned long>(v235, 33);
  std::wstring::wstring(&v212, v195, v235);
  v196 = &v212;
  if ( v213 > 7 )
    v196 = *(struct tagVARIANT **)&v212.vt;
  v194(v193, v196);
  std::wstring::~wstring(&v212);
  if ( byte_18154C7B8 < 0 )
    v197 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18154C7B8);
  else
    v197 = byte_18154C7B8 != 0;
  if ( v197 )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v198 + 48LL))(v198, L"invokeBotResponse");
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
    v200 = v199;
    v201 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v199 + 56LL);
    v202 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Osf::IFluidControlApiUser *, _BYTE *))(*(_QWORD *)a2 + 328LL))(
                       a2,
                       v234);
    if ( v202[3] > 7u )
      v202 = (_QWORD *)*v202;
    v201(v200, v202);
    std::wstring::~wstring(v234);
  }
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v203 + 24LL))(v203);
  Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v208);
  (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v204 + 120LL))(v204, v218);
  v212.vt = 3;
  v212.lVal = 0;
  Osf::CSafeArrayWriter::SetElementAtIndex((Osf::CSafeArrayWriter *)&v210, 0, &v212);
  v206 = (const wchar_t *)v218;
  if ( si128.m128i_i64[1] > 7uLL )
    v206 = v218[0];
  Osf::CSafeArrayWriter::SetStringAtIndex((Osf::CSafeArrayWriter *)&v210, v205, v206);
  (*(void (__fastcall **)(struct IExecuteArgumentSet *, __int64))(*(_QWORD *)a1 + 136LL))(a1, v210);
  (*(void (__fastcall **)(struct IExecuteArgumentSet *, _QWORD))(*(_QWORD *)a1 + 80LL))(a1, 0);
  (*(void (__fastcall **)(struct IExecuteArgumentSet *))(*(_QWORD *)a1 + 24LL))(a1);
  Mso::TCntPtr<RequestIt::RequestThrottledError>::~TCntPtr<RequestIt::RequestThrottledError>(&v211);
  std::wstring::~wstring(v220);
  std::string::~string(v214);
  std::wstring::~wstring(v221);
  std::string::~string(v216);
  Osf::LoopInfo::~LoopInfo((Osf::LoopInfo *)v224);
  std::wstring::~wstring(v222);
  std::wstring::~wstring(v223);
  std::wstring::~wstring(v218);
  v207 = v208;
  if ( v208 )
  {
    v208 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v207 + 8LL))(v207);
  }
}

```

## disassembly

```asm
0x180f776a4  mov     [rsp-8+arg_10], rbx
0x180f776a9  push    rbp
0x180f776aa  push    rsi
0x180f776ab  push    rdi
0x180f776ac  push    r12
0x180f776ae  push    r13
0x180f776b0  push    r14
0x180f776b2  push    r15
0x180f776b4  lea     rbp, [rsp-1C0h]
0x180f776bc  sub     rsp, 2C0h
0x180f776c3  mov     rax, cs:__security_cookie
0x180f776ca  xor     rax, rsp
0x180f776cd  mov     [rbp+1F0h+var_40], rax
0x180f776d4  mov     rsi, rdx
0x180f776d7  mov     r14, rcx
0x180f776da  lea     rcx, [rsp+2F0h+var_2B0]; this
0x180f776df  call    ??0CSafeArrayWriter@Osf@@QEAA@JJ@Z; Osf::CSafeArrayWriter::CSafeArrayWriter(long,long)
0x180f776e4  lea     rcx, [rsp+2F0h+var_2C0]
0x180f776e9  call    cs:__imp_?CreateJsonWriter@Json@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@2@XZ; Mso::Json::CreateJsonWriter(void)
0x180f776ef  xorps   xmm0, xmm0
0x180f776f2  movups  xmmword ptr [rbp+1F0h+var_240], xmm0
0x180f776f6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180f776fe  movdqu  [rbp+1F0h+var_230], xmm1
0x180f77703  xor     r13d, r13d
0x180f77706  mov     word ptr [rbp+1F0h+var_240], r13w
0x180f7770b  mov     rax, [rsi]
0x180f7770e  mov     rcx, rsi
0x180f77711  mov     rax, [rax+88h]
0x180f77718  call    cs:__guard_dispatch_icall_fptr
0x180f7771e  movsxd  rdi, eax
0x180f77721  mov     rcx, [rsi]
0x180f77724  mov     rax, [rcx+90h]
0x180f7772b  mov     rcx, rsi
0x180f7772e  call    cs:__guard_dispatch_icall_fptr
0x180f77734  mov     r15b, al
0x180f77737  mov     rcx, [rsi]
0x180f7773a  mov     rax, [rcx+80h]
0x180f77741  lea     rdx, [rbp+1F0h+var_1C0]
0x180f77745  mov     rcx, rsi
0x180f77748  call    cs:__guard_dispatch_icall_fptr
0x180f7774e  mov     rcx, [rsi]
0x180f77751  mov     rax, [rcx+0C0h]
0x180f77758  mov     rcx, rsi
0x180f7775b  call    cs:__guard_dispatch_icall_fptr
0x180f77761  mov     bl, al
0x180f77763  mov     rcx, [rsi]
0x180f77766  mov     rax, [rcx]
0x180f77769  mov     rcx, rsi
0x180f7776c  call    cs:__guard_dispatch_icall_fptr
0x180f77772  mov     r12b, al
0x180f77775  mov     rcx, [rsi]
0x180f77778  mov     rax, [rcx+8]
0x180f7777c  lea     rdx, [rbp+1F0h+var_1E0]
0x180f77780  mov     rcx, rsi
0x180f77783  call    cs:__guard_dispatch_icall_fptr
0x180f77789  mov     rcx, [rsi]
0x180f7778c  mov     rax, [rcx+98h]
0x180f77793  mov     rcx, rsi
0x180f77796  call    cs:__guard_dispatch_icall_fptr
0x180f7779c  mov     rdx, rax; struct Osf::LoopInfo *
0x180f7779f  lea     rcx, [rbp+1F0h+var_1A0]; this
0x180f777a3  call    ??0LoopInfo@Osf@@QEAA@AEBU01@@Z; Osf::LoopInfo::LoopInfo(Osf::LoopInfo const &)
0x180f777a8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f777ad  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f777b2  mov     rdx, rax
0x180f777b5  mov     rcx, [rax]
0x180f777b8  mov     rax, [rcx+10h]
0x180f777bc  mov     rcx, rdx
0x180f777bf  call    cs:__guard_dispatch_icall_fptr
0x180f777c5  lea     rcx, [rbp+1F0h+var_260]
0x180f777c9  call    cs:__imp_?GetAudienceGroup@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Mso::AudienceApi::GetAudienceGroup(void)
0x180f777cf  lea     r8, [rbp+1F0h+var_260]
0x180f777d3  cmp     [rbp+1F0h+var_248], 0Fh
0x180f777d8  cmova   r8, [rbp+1F0h+var_260]
0x180f777dd  add     r8, [rbp+1F0h+var_250]
0x180f777e1  lea     rdx, [rbp+1F0h+var_260]
0x180f777e5  cmp     [rbp+1F0h+var_248], 0Fh
0x180f777ea  cmova   rdx, [rbp+1F0h+var_260]
0x180f777ef  lea     rcx, [rbp+1F0h+var_200]
0x180f777f3  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<wchar_t> const &)
0x180f777f8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f777fd  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77802  mov     r8, rax
0x180f77805  mov     rcx, [rax]
0x180f77808  mov     rax, [rcx+30h]
0x180f7780c  lea     rdx, aAudiencegroup; "audienceGroup"
0x180f77813  mov     rcx, r8
0x180f77816  call    cs:__guard_dispatch_icall_fptr
0x180f7781c  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77821  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77826  mov     r8, rax
0x180f77829  mov     rcx, [rax]
0x180f7782c  mov     rax, [rcx+38h]
0x180f77830  lea     rdx, [rbp+1F0h+var_200]
0x180f77834  cmp     [rbp+1F0h+var_1E8], 7
0x180f77839  cmova   rdx, [rbp+1F0h+var_200]
0x180f7783e  mov     rcx, r8
0x180f77841  call    cs:__guard_dispatch_icall_fptr
0x180f77847  lea     rcx, [rsp+2F0h+var_280]
0x180f7784c  call    cs:__imp_?GetChannel@AudienceApi@Mso@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Mso::AudienceApi::GetChannel(void)
0x180f77852  lea     r8, [rsp+2F0h+var_280]
0x180f77857  cmp     [rbp+1F0h+var_268], 0Fh
0x180f7785c  cmova   r8, [rsp+2F0h+var_280]
0x180f77862  add     r8, [rbp+1F0h+var_270]
0x180f77866  lea     rdx, [rsp+2F0h+var_280]
0x180f7786b  cmp     [rbp+1F0h+var_268], 0Fh
0x180f77870  cmova   rdx, [rsp+2F0h+var_280]
0x180f77876  lea     rcx, [rbp+1F0h+var_220]
0x180f7787a  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<wchar_t> const &)
0x180f7787f  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77884  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77889  mov     r8, rax
0x180f7788c  mov     rcx, [rax]
0x180f7788f  mov     rax, [rcx+30h]
0x180f77893  lea     rdx, aChannel; "channel"
0x180f7789a  mov     rcx, r8
0x180f7789d  call    cs:__guard_dispatch_icall_fptr
0x180f778a3  lea     rcx, [rsp+2F0h+var_2C0]
0x180f778a8  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f778ad  mov     r8, rax
0x180f778b0  mov     rcx, [rax]
0x180f778b3  mov     rax, [rcx+38h]
0x180f778b7  lea     rdx, [rbp+1F0h+var_220]
0x180f778bb  cmp     [rbp+1F0h+var_208], 7
0x180f778c0  cmova   rdx, [rbp+1F0h+var_220]
0x180f778c5  mov     rcx, r8
0x180f778c8  call    cs:__guard_dispatch_icall_fptr
0x180f778ce  lea     rcx, [rsp+2F0h+var_2C0]
0x180f778d3  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f778d8  mov     r8, rax
0x180f778db  mov     rcx, [rax]
0x180f778de  mov     rax, [rcx+30h]
0x180f778e2  lea     rdx, aEnablerighttol; "enableRightToLeftSplashScreen"
0x180f778e9  mov     rcx, r8
0x180f778ec  call    cs:__guard_dispatch_icall_fptr
0x180f778f2  lea     rcx, [rsp+2F0h+var_2C0]
0x180f778f7  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f778fc  mov     r8, rax
0x180f778ff  mov     rcx, [rax]
0x180f77902  mov     rax, [rcx+40h]
0x180f77906  mov     dl, 1
0x180f77908  mov     rcx, r8
0x180f7790b  call    cs:__guard_dispatch_icall_fptr
0x180f77911  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77916  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f7791b  mov     r8, rax
0x180f7791e  mov     rcx, [rax]
0x180f77921  mov     rax, [rcx+30h]
0x180f77925  lea     rdx, aEnableshowloop; "enableShowLoopGlowBorderEvent"
0x180f7792c  mov     rcx, r8
0x180f7792f  call    cs:__guard_dispatch_icall_fptr
0x180f77935  lea     rcx, [rsp+2F0h+var_2C0]
0x180f7793a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f7793f  mov     r8, rax
0x180f77942  mov     rcx, [rax]
0x180f77945  mov     rax, [rcx+40h]
0x180f77949  mov     dl, 1
0x180f7794b  mov     rcx, r8
0x180f7794e  call    cs:__guard_dispatch_icall_fptr
0x180f77954  mov     edx, 1E14B6A3h
0x180f77959  mov     r8d, 166h
0x180f7795f  lea     rcx, [rsp+2F0h+var_2A8]
0x180f77964  call    cs:__imp_?CreateConfigUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@VMsoReserveTag@@W4URL@ConfigURL@12@@Z; Mso::OfficeWebServiceApi::CreateConfigUrlBuilder(MsoReserveTag,Mso::OfficeWebServiceApi::ConfigURL::URL)
0x180f7796a  cmp     [rsp+2F0h+var_2A8], r13
0x180f7796f  jz      loc_180F779FE
0x180f77975  lea     rcx, [rsp+2F0h+var_2A8]
0x180f7797a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f7797f  mov     rdx, rax
0x180f77982  mov     rcx, [rax]
0x180f77985  mov     rax, [rcx+0A0h]
0x180f7798c  mov     rcx, rdx
0x180f7798f  call    cs:__guard_dispatch_icall_fptr
0x180f77995  mov     rdx, rax
0x180f77998  lea     rcx, [rsp+2F0h+var_2A0]
0x180f7799d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180f779a2  lea     rcx, [rsp+2F0h+var_2C0]
0x180f779a7  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f779ac  mov     r8, rax
0x180f779af  mov     rcx, [rax]
0x180f779b2  mov     rax, [rcx+30h]
0x180f779b6  lea     rdx, aGraphendpoint; "graphEndpoint"
0x180f779bd  mov     rcx, r8
0x180f779c0  call    cs:__guard_dispatch_icall_fptr
0x180f779c6  lea     rcx, [rsp+2F0h+var_2C0]
0x180f779cb  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f779d0  mov     r8, rax
0x180f779d3  mov     rcx, [rax]
0x180f779d6  mov     rax, [rcx+38h]
0x180f779da  lea     rdx, [rsp+2F0h+var_2A0]
0x180f779df  cmp     [rsp+2F0h+var_288], 7
0x180f779e5  cmova   rdx, qword ptr [rsp+2F0h+var_2A0]
0x180f779eb  mov     rcx, r8
0x180f779ee  call    cs:__guard_dispatch_icall_fptr
0x180f779f4  lea     rcx, [rsp+2F0h+var_2A0]; void *
0x180f779f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180f779fe  mov     ecx, cs:_tls_index
0x180f77a04  mov     rax, gs:58h
0x180f77a0d  mov     edx, 10h
0x180f77a12  mov     rax, [rax+rcx*8]
0x180f77a16  mov     eax, [rdx+rax]
0x180f77a19  cmp     cs:dword_1815BAC20, eax
0x180f77a1f  jle     short loc_180F77AA0
0x180f77a21  lea     rcx, dword_1815BAC20
0x180f77a28  call    _Init_thread_header
0x180f77a2d  cmp     cs:dword_1815BAC20, 0FFFFFFFFh
0x180f77a34  jnz     short loc_180F77AA0
0x180f77a36  lea     rdx, WindowName
0x180f77a3d  lea     rcx, [rbp+1F0h+var_70]
0x180f77a44  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180f77a49  lea     rax, aFluidhostFluid; "FluidHost.FluidSettingOverrides"
0x180f77a50  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180f77a55  mov     [rsp+2F0h+var_2B8], 34h ; '4'
0x180f77a5a  mov     [rsp+2F0h+var_2D0], r13
0x180f77a5f  lea     r9, [rbp+1F0h+var_70]
0x180f77a66  lea     r8, [rsp+2F0h+var_2A0]
0x180f77a6b  lea     rdx, [rsp+2F0h+var_2B8]
0x180f77a70  lea     rcx, qword_1815BAC30
0x180f77a77  call    ??0?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEAA@AEBW4TeamEnum@23@AEBV?$StringLiteral@D@StringLiterals@3@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A?BU?$pair@PEBU?$pair@VScopeEnum@AB@Mso@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBU12@@8@X_E@Z; Mso::AB::Optimized::Setting<std::wstring>::Setting<std::wstring>(Mso::AB::TeamEnum const &,Mso::StringLiterals::StringLiteral<char> const &,std::wstring &&,std::pair<std::pair<Mso::AB::ScopeEnum,std::wstring> const *,std::pair<Mso::AB::ScopeEnum,std::wstring> const *> const (*)(void),...)
0x180f77a7c  lea     rcx, [rbp+1F0h+var_70]; void *
0x180f77a83  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180f77a88  lea     rcx, sub_1808B8AC0; void (__cdecl *)()
0x180f77a8f  call    atexit
0x180f77a94  lea     rcx, dword_1815BAC20
0x180f77a9b  call    _Init_thread_footer
0x180f77aa0  lea     rcx, qword_1815BAC30
0x180f77aa7  call    ??B?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(void)
0x180f77aac  cmp     [rax+10h], r13
0x180f77ab0  jz      loc_180F77B4C
0x180f77ab6  lea     rcx, qword_1815BAC30
0x180f77abd  call    ??B?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(void)
0x180f77ac2  cmp     qword ptr [rax+18h], 7
0x180f77ac7  jbe     short loc_180F77ACC
0x180f77ac9  mov     rax, [rax]
0x180f77acc  mov     rcx, rax; wchar_t *
0x180f77acf  call    ?IsValidJson@FluidControlApi@Osf@@CA_NPEB_W@Z; Osf::FluidControlApi::IsValidJson(wchar_t const *)
0x180f77ad4  test    al, al
0x180f77ad6  jz      short loc_180F77B21
0x180f77ad8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77add  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77ae2  mov     r8, rax
0x180f77ae5  mov     rcx, [rax]
0x180f77ae8  mov     rax, [rcx+30h]
0x180f77aec  lea     rdx, aFluidsettingov; "fluidSettingOverrides"
0x180f77af3  mov     rcx, r8
0x180f77af6  call    cs:__guard_dispatch_icall_fptr
0x180f77afc  lea     rcx, qword_1815BAC30
0x180f77b03  call    ??B?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Optimized@AB@Mso@@QEGBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::AB::Optimized::Setting<std::wstring>::operator std::wstring const &(void)
0x180f77b08  cmp     qword ptr [rax+18h], 7
0x180f77b0d  jbe     short loc_180F77B12
0x180f77b0f  mov     rax, [rax]
0x180f77b12  mov     rdx, rax
0x180f77b15  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b1a  call    ?WriteJson@FluidControlApi@Osf@@CAXAEBV?$TCntPtr@UIJsonWriter@Json@Mso@@@Mso@@PEB_W@Z; Osf::FluidControlApi::WriteJson(Mso::TCntPtr<Mso::Json::IJsonWriter> const &,wchar_t const *)
0x180f77b1f  jmp     short loc_180F77B4C
0x180f77b21  lea     rax, aInvalidJsonFor; "Invalid json for OEP.FluidHost.FluidSet"...
0x180f77b28  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180f77b2d  lea     rax, [rsp+2F0h+var_2A0]
0x180f77b32  mov     [rsp+2F0h+var_2D0], rax
0x180f77b37  mov     edx, 9B9h
0x180f77b3c  mov     ecx, 1E89B0E3h
0x180f77b41  mov     r8d, 0Ah
0x180f77b47  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180f77b4c  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b51  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77b56  mov     r8, rax
0x180f77b59  mov     rcx, [rax]
0x180f77b5c  mov     rax, [rcx+30h]
0x180f77b60  lea     rdx, aHost; "host"
0x180f77b67  mov     rcx, r8
0x180f77b6a  call    cs:__guard_dispatch_icall_fptr
0x180f77b70  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b75  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77b7a  mov     r8, rax
0x180f77b7d  mov     rcx, [rax]
0x180f77b80  mov     rax, [rcx+38h]
0x180f77b84  lea     rdx, aFluidcontrolap; "fluidControlApi"
0x180f77b8b  mov     rcx, r8
0x180f77b8e  call    cs:__guard_dispatch_icall_fptr
0x180f77b94  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77b99  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77b9e  mov     r8, rax
0x180f77ba1  mov     rcx, [rax]
0x180f77ba4  mov     rax, [rcx+30h]
0x180f77ba8  lea     rdx, aHydrateid_0; "hydrateId"
0x180f77baf  mov     rcx, r8
0x180f77bb2  call    cs:__guard_dispatch_icall_fptr
0x180f77bb8  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77bbd  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77bc2  mov     r8, rax
0x180f77bc5  mov     rcx, [rax]
0x180f77bc8  mov     rax, [rcx+38h]
0x180f77bcc  lea     rdx, [rbp+1F0h+var_1C0]
0x180f77bd0  cmp     [rbp+1F0h+var_1A8], 7
0x180f77bd5  cmova   rdx, [rbp+1F0h+var_1C0]
0x180f77bda  mov     rcx, r8
0x180f77bdd  call    cs:__guard_dispatch_icall_fptr
0x180f77be3  lea     rcx, [rsp+2F0h+var_2C0]
0x180f77be8  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f77bed  mov     r8, rax
0x180f77bf0  mov     rcx, [rax]
  ... truncated ...
```
