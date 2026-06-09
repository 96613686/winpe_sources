# OutlookApiImpl::WebExtLaunchEventSSOHelper::ExecuteGetSSOTokenInternal(Mso::TCntPtr<IExecuteArgumentSet> &,Mso::Authentication::IOfficeIdentity *,_MAPIUID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x141bc1a28`
- end: `0x141bc2b11`
- name: `?ExecuteGetSSOTokenInternal@WebExtLaunchEventSSOHelper@OutlookApiImpl@@AEAAJAEAV?$TCntPtr@UIExecuteArgumentSet@@@Mso@@PEAUIOfficeIdentity@Authentication@4@AEBU_MAPIUID@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `4329`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140bda104`

## callees

- `0x14001dd7c`
- `0x1400204a0`
- `0x1400211a0`
- `0x1400215d0`
- `0x1400255e8`
- `0x14003f764`
- `0x14005e608`
- `0x1400712cc`
- `0x140072964`
- `0x14007a108`
- `0x1400a6c6c`
- `0x140103f1c`
- `0x1401892c0`
- `0x14019b154`
- `0x1401b3fd4`
- `0x140387bf0`
- `0x140503f00`
- `0x14067af14`
- `0x1407e99f0`
- `0x1407eb010`
- `0x1407ecf10`
- `0x1408117ac`
- `0x1408121f4`
- `0x1408126dc`
- `0x14082dc84`
- `0x14082ded8`
- `0x1409b1c40`
- `0x1409c4674`
- `0x141bc1a28`
- `0x141bc2b20`

## import_xrefs

- `osf99!OsfTokenHelperForOutlook_ShouldThrottlePrompt` at `0x141bc2537`
- `osf99!OsfTokenHelperForOutlook_ShouldThrottlePrompt` at `0x141bc2537`
- `osf99!OsfTokenHelper_ValidateResourceUrl` at `0x141bc27d9`
- `osf99!OsfTokenHelper_ValidateResourceUrl` at `0x141bc27d9`
- `osf99!OsfTokenHelper_GetUserIdentity` at `0x141bc288e`
- `osf99!OsfTokenHelper_GetUserIdentity` at `0x141bc288e`
- `osf99!OsfTokenHelper_GetAuthToken` at `0x141bc2928`
- `osf99!OsfTokenHelper_GetAuthToken` at `0x141bc2928`
- `osfshared!?LogOsfRuntimeEvent@Osf@@YAXPEB_WW4Severity@Logging@Mso@@K0ZZ` at `0x141bc29f7`
- `osfshared!?LogOsfRuntimeEvent@Osf@@YAXPEB_WW4Severity@Logging@Mso@@K0ZZ` at `0x141bc29f7`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1cc2`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1d31`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1dcc`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1e7c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1f28`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1fd8`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc20c1`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2989`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1cc2`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1d31`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1dcc`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1e7c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1f28`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1fd8`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc20c1`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2989`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1ae8`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1af6`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1b04`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1b12`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1b20`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1ae8`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1af6`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1b04`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1b12`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1b20`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x141bc1c46`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x141bc1c46`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x141bc1c30`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x141bc1c30`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x141bc1c6c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x141bc1c6c`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2137`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2172`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc24b5`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2137`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2172`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc24b5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141bc2a15`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141bc2a15`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc21d0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc21f2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2212`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2232`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2382`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc240c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc242c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2605`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2684`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2747`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc29be`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc21d0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc21f2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2212`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2232`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2382`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc240c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc242c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2605`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2684`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2747`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc29be`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1d8f`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1e3f`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1eeb`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1f97`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc2080`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1d8f`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1e3f`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1eeb`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1f97`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc2080`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc23ee`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc248e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc23ee`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc248e`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1e09`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1eb9`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1f65`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1e09`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1eb9`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1f65`
- `Mso20Win32Client!__imp_?CreateJsonDom@Json@Mso@@YA?AV?$TCntPtr@UIJsonDom@Json@Mso@@@2@PEB_W@Z` at `0x141bc1ca6`
- `Mso20Win32Client!__imp_?CreateJsonDom@Json@Mso@@YA?AV?$TCntPtr@UIJsonDom@Json@Mso@@@2@PEB_W@Z` at `0x141bc1ca6`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc201d`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc2108`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc201d`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc2108`

## string_xrefs

- `0x141bc1b8e`: `ExecuteGetSSOTokenInternal`
- `0x141bc1ec6`: `forMSGraphAccess`
- `0x141bc221b`: `ForGraphAccess`
- `0x141bc2753`: `ServiceApplicationId not defined.`

## pseudocode

```c
__int64 __fastcall OutlookApiImpl::WebExtLaunchEventSSOHelper::ExecuteGetSSOTokenInternal(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v5; // r13d
  bool v8; // di
  bool v9; // r15
  const struct Mso::Telemetry::EventFlags *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  int SolutionSummary; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  SAFEARRAY *v16; // rax
  SAFEARRAY *v17; // rbx
  HRESULT Element; // eax
  const char *v19; // r8
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  Mso::Json::value *v24; // rbx
  __int64 v25; // rcx
  Mso::Json::value *v26; // rbx
  __int64 v27; // rcx
  Mso::Json::value *v28; // rbx
  __int64 v29; // rcx
  Mso::Json::value *v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // rax
  Mso::Json::value *v33; // rbx
  __int64 v34; // rcx
  _QWORD *v35; // rcx
  _QWORD *v36; // rcx
  int v37; // eax
  int v38; // ebx
  __int64 v39; // rcx
  struct Mso::Telemetry::IDataFieldCollection *v40; // rax
  __int64 v41; // r8
  struct Mso::Telemetry::IDataFieldCollection *v42; // rax
  __int64 v43; // r8
  struct Mso::Telemetry::IDataFieldCollection *v44; // rax
  __int64 v45; // r8
  struct Mso::Telemetry::IDataFieldCollection *v46; // rax
  __int64 v47; // r8
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r15
  __int64 v51; // rdi
  __int64 v52; // rbx
  _QWORD *v53; // r15
  _QWORD *v54; // rdx
  struct Mso::Telemetry::IDataFieldCollection *v55; // rbx
  _QWORD *v56; // rdx
  __int64 PrivacyCompliantId; // rax
  __int64 v58; // rcx
  unsigned int v59; // edi
  struct Mso::Telemetry::IDataFieldCollection *v60; // rax
  struct Mso::Telemetry::IDataFieldCollection *v61; // rax
  bool v62; // bl
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  struct Mso::Telemetry::IDataFieldCollection *v70; // rax
  const char *v71; // rdx
  const char *v72; // r8
  struct Mso::Telemetry::IDataFieldCollection *v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  bool v76; // al
  __int64 v77; // rax
  struct Mso::Telemetry::IDataFieldCollection *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rbx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // r8
  int v84; // eax
  const char *v85; // rdx
  const char *v86; // r8
  __int64 v87; // rax
  int UserIdentity; // eax
  const char *v89; // rdx
  const char *v90; // r8
  __int64 v91; // rbx
  __int128 *v92; // rdi
  __int64 v93; // rax
  __int64 v94; // rax
  const char *v95; // rdx
  __int64 v96; // rax
  unsigned int v97; // edi
  struct Mso::Telemetry::IDataFieldCollection *v98; // rax
  __int64 v99; // rcx
  struct IWebExtHost *v100; // rcx
  __int64 v101; // rcx
  _BYTE *v103; // [rsp+20h] [rbp-248h]
  bool v104; // [rsp+28h] [rbp-240h]
  const char *v105; // [rsp+38h] [rbp-230h]
  unsigned int v106; // [rsp+40h] [rbp-228h]
  bool v107; // [rsp+60h] [rbp-208h]
  bool v108; // [rsp+61h] [rbp-207h]
  int v109[2]; // [rsp+68h] [rbp-200h] BYREF
  _QWORD *v110; // [rsp+70h] [rbp-1F8h]
  char v111; // [rsp+78h] [rbp-1F0h]
  char v112[8]; // [rsp+80h] [rbp-1E8h] BYREF
  unsigned int v113; // [rsp+88h] [rbp-1E0h]
  _BYTE v114[16]; // [rsp+90h] [rbp-1D8h] BYREF
  int v115; // [rsp+A0h] [rbp-1C8h]
  __int64 v116; // [rsp+A8h] [rbp-1C0h] BYREF
  LONG plUbound; // [rsp+B0h] [rbp-1B8h] BYREF
  struct IWebExtHost *v118; // [rsp+B8h] [rbp-1B0h] BYREF
  __int64 v119; // [rsp+C0h] [rbp-1A8h] BYREF
  LONG plLbound; // [rsp+C8h] [rbp-1A0h] BYREF
  LONG rgIndices; // [rsp+CCh] [rbp-19Ch] BYREF
  __int64 v122; // [rsp+D0h] [rbp-198h] BYREF
  __int64 v123; // [rsp+D8h] [rbp-190h]
  __int64 v124; // [rsp+E0h] [rbp-188h]
  _QWORD *v125; // [rsp+E8h] [rbp-180h]
  _BYTE v126[16]; // [rsp+F0h] [rbp-178h] BYREF
  __int128 v127; // [rsp+100h] [rbp-168h] BYREF
  VARIANTARG pv; // [rsp+110h] [rbp-158h] BYREF
  _QWORD v129[2]; // [rsp+128h] [rbp-140h] BYREF
  char v130[8]; // [rsp+138h] [rbp-130h] BYREF
  VARIANTARG v131; // [rsp+140h] [rbp-128h] BYREF
  VARIANTARG v132; // [rsp+158h] [rbp-110h] BYREF
  VARIANTARG pvarg; // [rsp+170h] [rbp-F8h] BYREF
  VARIANTARG v134; // [rsp+188h] [rbp-E0h] BYREF
  _QWORD v135[3]; // [rsp+1A0h] [rbp-C8h] BYREF
  unsigned __int64 v136; // [rsp+1B8h] [rbp-B0h]
  _BYTE v137[32]; // [rsp+1C0h] [rbp-A8h] BYREF
  __int128 v138; // [rsp+1E0h] [rbp-88h] BYREF
  __int64 v139; // [rsp+1F0h] [rbp-78h]
  unsigned __int64 v140; // [rsp+1F8h] [rbp-70h]
  _OWORD v141[2]; // [rsp+200h] [rbp-68h] BYREF

  v123 = a4;
  v110 = a2;
  v125 = a2;
  v124 = a5;
  v119 = a3;
  plLbound = -1;
  plUbound = -1;
  rgIndices = 0;
  v111 = 0;
  LOBYTE(v5) = 0;
  v115 = v5;
  v8 = 0;
  v107 = 0;
  v9 = 0;
  v108 = 0;
  v138 = 0;
  v139 = 0;
  v140 = 7;
  LOWORD(v138) = 0;
  v113 = 0;
  VariantInit(&v134);
  VariantInit(&pvarg);
  VariantInit(&v132);
  VariantInit(&v131);
  VariantInit(&pv);
  v141[0] = 0;
  v141[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v141[0]) = 0;
  v122 = 0;
  v118 = 0;
  v116 = 0;
  v127 = 0;
  v10 = (const struct Mso::Telemetry::EventFlags *)Mso::Telemetry::EventFlags::EventFlags(v130, 1, 2);
  v129[0] = &off_141E28D00;
  v129[1] = "ExecuteGetSSOTokenInternal";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v114,
    (const struct Mso::Telemetry::EventName *)v129,
    v10);
  v11 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 80LL))(v11, 5001);
  if ( !v119 )
  {
    v12 = 559285337;
LABEL_3:
    SolutionSummary = -2147467259;
    v14 = 2147500037LL;
LABEL_140:
    EtwTraceErrorTag(v14, v12);
    goto LABEL_141;
  }
  if ( !*(_QWORD *)(a5 + 16) )
  {
    v12 = 559285336;
    goto LABEL_3;
  }
  v15 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
  v16 = (SAFEARRAY *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 128LL))(v15);
  v17 = v16;
  if ( v16 )
  {
    SafeArrayGetLBound(v16, 1u, &plLbound);
    SafeArrayGetUBound(v17, 1u, &plUbound);
  }
  if ( plUbound )
  {
    v12 = 559285325;
    goto LABEL_139;
  }
  Element = SafeArrayGetElement(v17, &rgIndices, &pv);
  SolutionSummary = Element;
  if ( Element < 0 )
  {
    v12 = 559285335;
LABEL_11:
    v14 = (unsigned int)Element;
    goto LABEL_140;
  }
  if ( pv.vt != 8 )
  {
    v12 = 559285334;
LABEL_139:
    v14 = 2147942487LL;
    SolutionSummary = -2147024809;
    goto LABEL_140;
  }
  Mso::Json::CreateJsonDom(v109, pv.llVal);
  if ( !*(_QWORD *)v109 )
  {
    SolutionSummary = -2147024809;
    EtwTraceErrorTag(2147942487LL, 559285333);
    v20 = *(_QWORD *)v109;
    if ( *(_QWORD *)v109 )
    {
      *(_QWORD *)v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
    }
    v21 = v110;
    goto LABEL_142;
  }
  v22 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(v109);
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 16LL))(v22, v112);
  if ( !Mso::Json::value::is_object((Mso::Json::value *)v112) )
  {
    SolutionSummary = -2147024809;
    EtwTraceErrorTag(2147942487LL, 559285332);
    std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
    v23 = *(_QWORD *)v109;
    if ( *(_QWORD *)v109 )
    {
      *(_QWORD *)v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    }
    v21 = v110;
    goto LABEL_142;
  }
  std::wstring::wstring(v135, L"allowConsentPrompt");
  v24 = (Mso::Json::value *)Mso::Json::value::operator[](v112, v135);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v135);
  if ( !Mso::Json::value::is_null(v24) )
  {
    if ( !Mso::Json::value::is_boolean(v24) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285331);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
      v25 = *(_QWORD *)v109;
      if ( *(_QWORD *)v109 )
      {
        *(_QWORD *)v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      }
      v21 = v110;
      goto LABEL_142;
    }
    LOBYTE(v5) = Mso::Json::value::as_bool(v24);
    v115 = v5;
  }
  std::wstring::wstring(v135, L"allowSignInPrompt");
  v26 = (Mso::Json::value *)Mso::Json::value::operator[](v112, v135);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v135);
  if ( !Mso::Json::value::is_null(v26) )
  {
    if ( !Mso::Json::value::is_boolean(v26) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285330);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
      v27 = *(_QWORD *)v109;
      if ( *(_QWORD *)v109 )
      {
        *(_QWORD *)v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      }
      v21 = v110;
      goto LABEL_142;
    }
    v9 = Mso::Json::value::as_bool(v26);
    v108 = v9;
  }
  std::wstring::wstring(v135, L"forMSGraphAccess");
  v28 = (Mso::Json::value *)Mso::Json::value::operator[](v112, v135);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v135);
  if ( !Mso::Json::value::is_null(v28) )
  {
    if ( !Mso::Json::value::is_boolean(v28) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285329);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
      v29 = *(_QWORD *)v109;
      if ( *(_QWORD *)v109 )
      {
        *(_QWORD *)v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      }
      v21 = v110;
      goto LABEL_142;
    }
    v8 = Mso::Json::value::as_bool(v28);
    v107 = v8;
  }
  std::wstring::wstring(v135, L"authChallenge");
  v30 = (Mso::Json::value *)Mso::Json::value::operator[](v112, v135);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v135);
  if ( !Mso::Json::value::is_null(v30) )
  {
    if ( !Mso::Json::value::is_string(v30) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285328);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
      v31 = *(_QWORD *)v109;
      if ( *(_QWORD *)v109 )
      {
        *(_QWORD *)v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      }
      v21 = v110;
      goto LABEL_142;
    }
    v32 = Mso::Json::value::as_string(v30, v137);
    std::wstring::operator=(&v138, v32);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v137);
    if ( v139 )
    {
      v111 = 1;
      v9 = 0;
      v108 = 0;
    }
  }
  std::wstring::wstring(v137, L"accountTypeFilter");
  v33 = (Mso::Json::value *)Mso::Json::value::operator[](v112, v137);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v137);
  if ( Mso::Json::value::is_null(v33) )
  {
LABEL_62:
    std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
    v39 = *(_QWORD *)v109;
    if ( *(_QWORD *)v109 )
    {
      *(_QWORD *)v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    }
    v40 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    LOBYTE(v41) = v111;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v40, "AuthChallengeDefined", v41);
    v42 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    LOBYTE(v43) = v5;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v42, "AllowInteractiveConsent", v43);
    v44 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    LOBYTE(v45) = v8;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v44, "ForGraphAccess", v45);
    v46 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    LOBYTE(v47) = v9;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v46, "AllowSignInPrompt", v47);
    Element = HrGetWebExtHost(&v118, 0, 0);
    SolutionSummary = Element;
    if ( Element < 0 )
    {
      v12 = 559285324;
      goto LABEL_11;
    }
    if ( !v118 )
    {
      v12 = 559285323;
      goto LABEL_3;
    }
    v48 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v118);
    v49 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v48 + 480LL))(v48, v126, *(_QWORD *)a1);
    std::shared_ptr<MeetingAttendeeGridDpiDetails>::operator=(&v127, v49);
    std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(v126);
    v50 = v127;
    if ( !(_QWORD)v127 )
    {
      v12 = 559285322;
      goto LABEL_3;
    }
    v51 = v123;
    v52 = HexizeEmsmdbUID(v135, v123);
    v53 = (_QWORD *)(v50 + 56);
    v54 = v53;
    if ( v53[3] > 7u )
      v54 = (_QWORD *)*v53;
    std::wstring::wstring(v137, v54);
    SolutionSummary = HrWebExtGetSolutionSummary(v137, v52, &v116, 0x1FFF);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v137);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v135);
    if ( SolutionSummary < 0 )
    {
      v12 = 559285321;
      v14 = (unsigned int)SolutionSummary;
      goto LABEL_140;
    }
    if ( !v116 )
    {
      v12 = 559285320;
      goto LABEL_3;
    }
    v55 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    v56 = v53;
    if ( v53[3] > 7u )
      v56 = (_QWORD *)*v53;
    std::wstring::wstring(v137, v56);
    PrivacyCompliantId = WebExt::GetPrivacyCompliantId(v137, v51);
    Mso::Telemetry::IDataFieldCollection::Add(v55, "SolutionId", PrivacyCompliantId, 4);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v137);
    v58 = v116;
    if ( !v116 )
      CrashWithRecovery(0x1E3C3840u, 0);
    v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v58 + 80LL))(v58);
    v60 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v60, "StoreType", v59);
    v61 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v61, "AccountTypeFilter", v113);
    Element = OutlookApiImpl::WebExtLaunchEventSSOHelper::InitializeAppProperties(a1, &v116);
    SolutionSummary = Element;
    if ( Element < 0 )
    {
      v12 = 559285319;
      goto LABEL_11;
    }
    if ( v59 == 3 )
    {
      v62 = v107;
      if ( !v107 )
        goto LABEL_96;
      v63 = v116;
      if ( !v116 )
        CrashWithRecovery(0x1E3C3840u, 0);
      v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 560LL))(v63);
      if ( (unsigned int)MsoFWzEqual(v64, L"User", 1) )
      {
        v65 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 80LL))(v65, 13012);
        v12 = 559285318;
        goto LABEL_3;
      }
    }
    else
    {
      if ( v59 - 1 <= 1 )
      {
        v12 = 559285317;
        goto LABEL_3;
      }
      if ( !v59 || v59 == 7 )
      {
        if ( v107 )
        {
          v68 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 80LL))(v68, 13012);
          v12 = 559285316;
          goto LABEL_3;
        }
LABEL_96:
        if ( v108 || (_BYTE)v5 )
        {
          if ( *(_BYTE *)(a1 + 120) )
          {
            v66 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 88);
            if ( (unsigned __int8)OsfTokenHelperForOutlook_ShouldThrottlePrompt(v66) )
            {
              v67 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 80LL))(v67, 13013);
              v12 = 559285315;
              goto LABEL_3;
            }
          }
        }
        if ( !*(_BYTE *)(a1 + 40) || !*(_BYTE *)(a1 + 80) || !*(_BYTE *)(a1 + 120) || !*(_BYTE *)(a1 + 160) )
        {
          v12 = 559285314;
          goto LABEL_3;
        }
        if ( *(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 8) + 16) )
        {
          if ( (!v59 || v59 == 7) && !*(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 168) + 16) )
          {
            v73 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
            Mso::Telemetry::IDataFieldCollection::Add(v73, "Error", L"Missing asset ID for OMEX add-in", 4);
            v74 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v53);
            v75 = std::wstring::wstring(v137, v74);
            std::_Optional_construct_base<std::wstring>::_Assign<std::wstring>(a1 + 168, v75);
            std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v137);
          }
          v76 = !*(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 168) + 16)
             && !*(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 48) + 16);
          if ( v59 == 12 )
            v76 = 1;
          if ( !v76 || *(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 88) + 16) )
          {
            v79 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 88);
            v80 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v79);
            v81 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 8);
            std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v81);
            v82 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v124);
            v104 = 0;
            v103 = v114;
            v84 = OsfTokenHelper_ValidateResourceUrl(*a2, v82, v83, v80);
            v109[0] = v84;
            if ( v84 < 0 )
            {
              HandleCORgError_Impl(0, v85, v86, 0, (bool)v114, 0, 0, v105, 0x21560421u, v84, v109);
              goto LABEL_110;
            }
            if ( v108 || v119 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v119 + 296LL))(v119) )
            {
              LOBYTE(v85) = v108;
              UserIdentity = OsfTokenHelper_GetUserIdentity(*a2, v85, v113, v114);
              v109[0] = UserIdentity;
              if ( UserIdentity >= 0 )
              {
                v91 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v53);
                v92 = &v138;
                if ( v140 > 7 )
                  v92 = (__int128 *)v138;
                v93 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 8);
                v94 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v93);
                v103 = (_BYTE *)v91;
                SolutionSummary = OsfTokenHelper_GetAuthToken(*a2, v119, v94, v92);
                v109[0] = SolutionSummary;
                if ( SolutionSummary >= 0 )
                  goto LABEL_141;
                HandleCORgError_Impl(
                  0,
                  v95,
                  v19,
                  0,
                  (bool)v103,
                  (bool)v114,
                  0,
                  (const char *)&v122,
                  0x2156041Eu,
                  SolutionSummary,
                  v109);
              }
              else
              {
                HandleCORgError_Impl(0, v89, v90, 0, (bool)&v119, 0, 0, v105, 0x2156041Fu, UserIdentity, v109);
              }
              goto LABEL_110;
            }
            v87 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 80LL))(v87, 13001);
            v106 = 559285280;
          }
          else
          {
            v77 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 80LL))(v77, 13000);
            v78 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
            Mso::Telemetry::IDataFieldCollection::Add(v78, "Error", L"ServiceApplicationId not defined.", 4);
            v106 = 559285282;
          }
        }
        else
        {
          v69 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 80LL))(v69, 13000);
          v70 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
          Mso::Telemetry::IDataFieldCollection::Add(v70, "Error", L"AppResource not defined.", 4);
          v106 = 559285313;
        }
        v109[0] = -2147467259;
        HandleCORgError_Impl(0, v71, v72, 0, (bool)v103, v104, 0, v105, v106, -2147467259, v109);
LABEL_110:
        SolutionSummary = v109[0];
LABEL_141:
        v21 = v110;
        goto LABEL_142;
      }
      v62 = v107;
    }
    if ( v62 )
    {
      v5 = (unsigned __int8)v5;
      if ( v59 == 10 )
        v5 = 0;
      v115 = v5;
    }
    goto LABEL_96;
  }
  if ( Mso::Json::value::is_string(v33) )
  {
    Mso::Json::value::as_string(v33, v135);
    v35 = v135;
    if ( v136 > 7 )
      v35 = (_QWORD *)v135[0];
    if ( (unsigned int)MsoFWzEqual(v35, L"msa", 1) )
    {
      v113 = 2;
    }
    else
    {
      v36 = v135;
      if ( v136 > 7 )
        v36 = (_QWORD *)v135[0];
      v37 = MsoFWzEqual(v36, L"aad", 1);
      v38 = v113;
      if ( v37 )
        v38 = 1;
      v113 = v38;
    }
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v135);
    goto LABEL_62;
  }
  SolutionSummary = -2147024809;
  EtwTraceErrorTag(2147942487LL, 559285327);
  std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v112);
  v34 = *(_QWORD *)v109;
  if ( *(_QWORD *)v109 )
  {
    *(_QWORD *)v109 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
  }
  v21 = v110;
LABEL_142:
  if ( *v21 )
  {
    v96 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
    v97 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 88LL))(v96);
    v98 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v114);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v98, "OsfOmError", v97);
    if ( v97 )
    {
      LODWORD(v103) = v97;
      Osf::LogOsfRuntimeEvent(L"WebApplicationInfo", 15, 505992770, L"SSO failed with \"%d\" error code.", v103);
    }
  }
  Mso::Telemetry::SetActivityResultHr(
    (Mso::Telemetry *)v114,
    (struct Mso::Telemetry::Activity *)(unsigned int)SolutionSummary,
    (int)v19);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v114);
  std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v127);
  v99 = v116;
  if ( v116 )
  {
    v116 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
  }
  v100 = v118;
  if ( v118 )
  {
    v118 = 0;
    (*(void (__fastcall **)(struct IWebExtHost *))(*(_QWORD *)v100 + 16LL))(v100);
  }
  v101 = v122;
  if ( v122 )
  {
    v122 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
  }
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v141);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&pv);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&v131);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&v132);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&pvarg);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&v134);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&v138);
  return (unsigned int)SolutionSummary;
}

```

## disassembly

```asm
0x141bc1a28  mov     r11, rsp
0x141bc1a2b  push    rbx
0x141bc1a2c  push    rsi
0x141bc1a2d  push    rdi
0x141bc1a2e  push    r12
0x141bc1a30  push    r13
0x141bc1a32  push    r14
0x141bc1a34  push    r15
0x141bc1a36  sub     rsp, 230h
0x141bc1a3d  mov     rax, cs:__security_cookie
0x141bc1a44  xor     rax, rsp
0x141bc1a47  mov     [rsp+268h+var_48], rax
0x141bc1a4f  mov     [rsp+268h+var_190], r9
0x141bc1a57  mov     [rsp+268h+var_1F8], rdx
0x141bc1a5c  mov     r14, rcx
0x141bc1a5f  mov     [rsp+268h+var_180], rdx
0x141bc1a67  mov     rbx, [rsp+268h+arg_20]
0x141bc1a6f  mov     [rsp+268h+var_188], rbx
0x141bc1a77  mov     r12, rdx
0x141bc1a7a  mov     [r11-1A8h], r8
0x141bc1a81  or      eax, 0FFFFFFFFh
0x141bc1a84  mov     [rsp+268h+plLbound], eax
0x141bc1a8b  mov     [rsp+268h+plUbound], eax
0x141bc1a92  xor     esi, esi
0x141bc1a94  mov     [rsp+268h+rgIndices], esi
0x141bc1a9b  mov     [rsp+268h+var_1F0], sil
0x141bc1aa0  mov     r13b, sil
0x141bc1aa3  mov     [rsp+268h+var_1C8], r13d
0x141bc1aab  mov     dil, sil
0x141bc1aae  mov     [rsp+268h+var_208], sil
0x141bc1ab3  mov     r15b, sil
0x141bc1ab6  mov     [rsp+268h+var_207], sil
0x141bc1abb  xorps   xmm0, xmm0
0x141bc1abe  movups  [rsp+268h+var_88], xmm0
0x141bc1ac6  mov     [r11-78h], rsi
0x141bc1aca  mov     qword ptr [r11-70h], 7
0x141bc1ad2  mov     word ptr [rsp+268h+var_88], si
0x141bc1ada  mov     [rsp+268h+var_1E0], esi
0x141bc1ae1  lea     rcx, [r11-0E0h]; pvarg
0x141bc1ae8  call    cs:__imp_VariantInit
0x141bc1aee  lea     rcx, [rsp+268h+pvarg]; pvarg
0x141bc1af6  call    cs:__imp_VariantInit
0x141bc1afc  lea     rcx, [rsp+268h+var_110]; pvarg
0x141bc1b04  call    cs:__imp_VariantInit
0x141bc1b0a  lea     rcx, [rsp+268h+var_128]; pvarg
0x141bc1b12  call    cs:__imp_VariantInit
0x141bc1b18  lea     rcx, [rsp+268h+pv]; pvarg
0x141bc1b20  call    cs:__imp_VariantInit
0x141bc1b26  xorps   xmm0, xmm0
0x141bc1b29  movups  [rsp+268h+var_68], xmm0
0x141bc1b31  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x141bc1b39  movdqu  [rsp+268h+var_58], xmm1
0x141bc1b42  mov     word ptr [rsp+268h+var_68], si
0x141bc1b4a  mov     [rsp+268h+var_198], rsi
0x141bc1b52  mov     [rsp+268h+var_1B0], rsi
0x141bc1b5a  mov     [rsp+268h+var_1C0], rsi
0x141bc1b62  movdqu  [rsp+268h+var_168], xmm0
0x141bc1b6b  lea     edx, [rsi+1]
0x141bc1b6e  lea     r8d, [rsi+2]
0x141bc1b72  lea     rcx, [rsp+268h+var_130]
0x141bc1b7a  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4SamplingPolicy@12@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::SamplingPolicy,Mso::Telemetry::DataCategories)
0x141bc1b7f  lea     rcx, off_141E28D00
0x141bc1b86  mov     [rsp+268h+var_140], rcx
0x141bc1b8e  lea     rcx, aExecutegetssot; "ExecuteGetSSOTokenInternal"
0x141bc1b95  mov     [rsp+268h+var_138], rcx
0x141bc1b9d  mov     r8, rax; struct Mso::Telemetry::EventFlags *
0x141bc1ba0  lea     rdx, [rsp+268h+var_140]; struct Mso::Telemetry::EventName *
0x141bc1ba8  lea     rcx, [rsp+268h+var_1D8]; this
0x141bc1bb0  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x141bc1bb5  mov     rcx, r12
0x141bc1bb8  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x141bc1bbd  mov     rcx, rax
0x141bc1bc0  mov     rax, [rax]
0x141bc1bc3  mov     edx, 1389h
0x141bc1bc8  mov     rax, [rax+50h]
0x141bc1bcc  call    cs:__guard_dispatch_icall_fptr
0x141bc1bd2  cmp     [rsp+268h+var_1A8], rsi
0x141bc1bda  jnz     short loc_141BC1BF0
0x141bc1bdc  mov     edx, 21560459h
0x141bc1be1  mov     ebx, 80004005h
0x141bc1be6  mov     ecx, 80004005h
0x141bc1beb  jmp     loc_141BC2989
0x141bc1bf0  cmp     [rbx+10h], rsi
0x141bc1bf4  jnz     short loc_141BC1BFD
0x141bc1bf6  mov     edx, 21560458h
0x141bc1bfb  jmp     short loc_141BC1BE1
0x141bc1bfd  mov     rcx, r12
0x141bc1c00  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x141bc1c05  mov     rcx, rax
0x141bc1c08  mov     rax, [rax]
0x141bc1c0b  mov     rax, [rax+80h]
0x141bc1c12  call    cs:__guard_dispatch_icall_fptr
0x141bc1c18  mov     rbx, rax
0x141bc1c1b  test    rax, rax
0x141bc1c1e  jz      short loc_141BC1C4C
0x141bc1c20  lea     r8, [rsp+268h+plLbound]; plLbound
0x141bc1c28  mov     edx, 1; nDim
0x141bc1c2d  mov     rcx, rax; psa
0x141bc1c30  call    cs:__imp_SafeArrayGetLBound
0x141bc1c36  lea     r8, [rsp+268h+plUbound]; plUbound
0x141bc1c3e  mov     edx, 1; nDim
0x141bc1c43  mov     rcx, rbx; psa
0x141bc1c46  call    cs:__imp_SafeArrayGetUBound
0x141bc1c4c  cmp     [rsp+268h+plUbound], esi
0x141bc1c53  jnz     loc_141BC297A
0x141bc1c59  lea     r8, [rsp+268h+pv]; pv
0x141bc1c61  lea     rdx, [rsp+268h+rgIndices]; rgIndices
0x141bc1c69  mov     rcx, rbx; psa
0x141bc1c6c  call    cs:__imp_SafeArrayGetElement
0x141bc1c72  mov     ebx, eax
0x141bc1c74  test    eax, eax
0x141bc1c76  jns     short loc_141BC1C84
0x141bc1c78  mov     edx, 21560457h
0x141bc1c7d  mov     ecx, eax
0x141bc1c7f  jmp     loc_141BC2989
0x141bc1c84  cmp     word ptr [rsp+268h+pv], 8
0x141bc1c8d  jz      short loc_141BC1C99
0x141bc1c8f  mov     edx, 21560456h
0x141bc1c94  jmp     loc_141BC297F
0x141bc1c99  mov     rdx, qword ptr [rsp+268h+pv+8]
0x141bc1ca1  lea     rcx, [rsp+268h+var_200]
0x141bc1ca6  call    cs:__imp_?CreateJsonDom@Json@Mso@@YA?AV?$TCntPtr@UIJsonDom@Json@Mso@@@2@PEB_W@Z; Mso::Json::CreateJsonDom(wchar_t const *)
0x141bc1cac  cmp     qword ptr [rsp+268h+var_200], rsi
0x141bc1cb1  jnz     short loc_141BC1CEF
0x141bc1cb3  mov     ebx, 80070057h
0x141bc1cb8  mov     edx, 21560455h
0x141bc1cbd  mov     ecx, 80070057h
0x141bc1cc2  call    cs:__imp_EtwTraceErrorTag
0x141bc1cc8  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1ccd  test    rcx, rcx
0x141bc1cd0  jz      short loc_141BC1CE5
0x141bc1cd2  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1cd7  mov     rax, [rcx]
0x141bc1cda  mov     rax, [rax+8]
0x141bc1cde  call    cs:__guard_dispatch_icall_fptr
0x141bc1ce4  nop
0x141bc1ce5  mov     rax, [rsp+268h+var_1F8]
0x141bc1cea  jmp     loc_141BC2994
0x141bc1cef  lea     rcx, [rsp+268h+var_200]
0x141bc1cf4  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x141bc1cf9  mov     rcx, rax
0x141bc1cfc  mov     rax, [rax]
0x141bc1cff  lea     rdx, [rsp+268h+var_1E8]
0x141bc1d07  mov     rax, [rax+10h]
0x141bc1d0b  call    cs:__guard_dispatch_icall_fptr
0x141bc1d11  lea     rcx, [rsp+268h+var_1E8]; this
0x141bc1d19  call    ?is_object@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_object(void)
0x141bc1d1e  test    al, al
0x141bc1d20  jnz     short loc_141BC1D6B
0x141bc1d22  mov     ebx, 80070057h
0x141bc1d27  mov     edx, 21560454h
0x141bc1d2c  mov     ecx, 80070057h
0x141bc1d31  call    cs:__imp_EtwTraceErrorTag
0x141bc1d37  lea     rcx, [rsp+268h+var_1E8]
0x141bc1d3f  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1d44  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1d49  test    rcx, rcx
0x141bc1d4c  jz      short loc_141BC1D61
0x141bc1d4e  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1d53  mov     rax, [rcx]
0x141bc1d56  mov     rax, [rax+8]
0x141bc1d5a  call    cs:__guard_dispatch_icall_fptr
0x141bc1d60  nop
0x141bc1d61  mov     rax, [rsp+268h+var_1F8]
0x141bc1d66  jmp     loc_141BC2994
0x141bc1d6b  lea     rdx, aAllowconsentpr; "allowConsentPrompt"
0x141bc1d72  lea     rcx, [rsp+268h+var_C8]
0x141bc1d7a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1d7f  lea     rdx, [rsp+268h+var_C8]
0x141bc1d87  lea     rcx, [rsp+268h+var_1E8]
0x141bc1d8f  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1d95  mov     rbx, rax
0x141bc1d98  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1da0  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1da5  mov     rcx, rbx; this
0x141bc1da8  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1dad  test    al, al
0x141bc1daf  jnz     short loc_141BC1E1A
0x141bc1db1  mov     rcx, rbx; this
0x141bc1db4  call    ?is_boolean@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_boolean(void)
0x141bc1db9  test    al, al
0x141bc1dbb  jnz     short loc_141BC1E06
0x141bc1dbd  mov     ebx, 80070057h
0x141bc1dc2  mov     edx, 21560453h
0x141bc1dc7  mov     ecx, 80070057h
0x141bc1dcc  call    cs:__imp_EtwTraceErrorTag
0x141bc1dd2  lea     rcx, [rsp+268h+var_1E8]
0x141bc1dda  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1ddf  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1de4  test    rcx, rcx
0x141bc1de7  jz      short loc_141BC1DFC
0x141bc1de9  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1dee  mov     rax, [rcx]
0x141bc1df1  mov     rax, [rax+8]
0x141bc1df5  call    cs:__guard_dispatch_icall_fptr
0x141bc1dfb  nop
0x141bc1dfc  mov     rax, [rsp+268h+var_1F8]
0x141bc1e01  jmp     loc_141BC2994
0x141bc1e06  mov     rcx, rbx
0x141bc1e09  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x141bc1e0f  mov     r13b, al
0x141bc1e12  mov     [rsp+268h+var_1C8], r13d
0x141bc1e1a  lea     rdx, aAllowsigninpro_0; "allowSignInPrompt"
0x141bc1e21  lea     rcx, [rsp+268h+var_C8]
0x141bc1e29  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1e2e  nop
0x141bc1e2f  lea     rdx, [rsp+268h+var_C8]
0x141bc1e37  lea     rcx, [rsp+268h+var_1E8]
0x141bc1e3f  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1e45  mov     rbx, rax
0x141bc1e48  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1e50  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1e55  mov     rcx, rbx; this
0x141bc1e58  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1e5d  test    al, al
0x141bc1e5f  jnz     short loc_141BC1EC6
0x141bc1e61  mov     rcx, rbx; this
0x141bc1e64  call    ?is_boolean@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_boolean(void)
0x141bc1e69  test    al, al
0x141bc1e6b  jnz     short loc_141BC1EB6
0x141bc1e6d  mov     ebx, 80070057h
0x141bc1e72  mov     edx, 21560452h
0x141bc1e77  mov     ecx, 80070057h
0x141bc1e7c  call    cs:__imp_EtwTraceErrorTag
0x141bc1e82  lea     rcx, [rsp+268h+var_1E8]
0x141bc1e8a  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1e8f  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1e94  test    rcx, rcx
0x141bc1e97  jz      short loc_141BC1EAC
0x141bc1e99  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1e9e  mov     rax, [rcx]
0x141bc1ea1  mov     rax, [rax+8]
0x141bc1ea5  call    cs:__guard_dispatch_icall_fptr
0x141bc1eab  nop
0x141bc1eac  mov     rax, [rsp+268h+var_1F8]
0x141bc1eb1  jmp     loc_141BC2994
0x141bc1eb6  mov     rcx, rbx
0x141bc1eb9  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x141bc1ebf  mov     r15b, al
0x141bc1ec2  mov     [rsp+268h+var_207], al
0x141bc1ec6  lea     rdx, aFormsgraphacce; "forMSGraphAccess"
0x141bc1ecd  lea     rcx, [rsp+268h+var_C8]
0x141bc1ed5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1eda  nop
0x141bc1edb  lea     rdx, [rsp+268h+var_C8]
0x141bc1ee3  lea     rcx, [rsp+268h+var_1E8]
0x141bc1eeb  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1ef1  mov     rbx, rax
0x141bc1ef4  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1efc  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1f01  mov     rcx, rbx; this
0x141bc1f04  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1f09  test    al, al
0x141bc1f0b  jnz     short loc_141BC1F72
0x141bc1f0d  mov     rcx, rbx; this
0x141bc1f10  call    ?is_boolean@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_boolean(void)
0x141bc1f15  test    al, al
0x141bc1f17  jnz     short loc_141BC1F62
0x141bc1f19  mov     ebx, 80070057h
0x141bc1f1e  mov     edx, 21560451h
0x141bc1f23  mov     ecx, 80070057h
0x141bc1f28  call    cs:__imp_EtwTraceErrorTag
0x141bc1f2e  lea     rcx, [rsp+268h+var_1E8]
0x141bc1f36  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1f3b  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1f40  test    rcx, rcx
0x141bc1f43  jz      short loc_141BC1F58
0x141bc1f45  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1f4a  mov     rax, [rcx]
0x141bc1f4d  mov     rax, [rax+8]
0x141bc1f51  call    cs:__guard_dispatch_icall_fptr
0x141bc1f57  nop
0x141bc1f58  mov     rax, [rsp+268h+var_1F8]
0x141bc1f5d  jmp     loc_141BC2994
0x141bc1f62  mov     rcx, rbx
0x141bc1f65  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x141bc1f6b  mov     dil, al
0x141bc1f6e  mov     [rsp+268h+var_208], al
0x141bc1f72  lea     rdx, aAuthchallenge_1; "authChallenge"
0x141bc1f79  lea     rcx, [rsp+268h+var_C8]
0x141bc1f81  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1f86  nop
0x141bc1f87  lea     rdx, [rsp+268h+var_C8]
0x141bc1f8f  lea     rcx, [rsp+268h+var_1E8]
0x141bc1f97  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1f9d  mov     rbx, rax
0x141bc1fa0  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1fa8  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1fad  mov     rcx, rbx; this
0x141bc1fb0  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1fb5  test    al, al
0x141bc1fb7  jnz     loc_141BC2057
0x141bc1fbd  mov     rcx, rbx; this
0x141bc1fc0  call    ?is_string@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_string(void)
0x141bc1fc5  test    al, al
0x141bc1fc7  jnz     short loc_141BC2012
0x141bc1fc9  mov     ebx, 80070057h
0x141bc1fce  mov     edx, 21560450h
0x141bc1fd3  mov     ecx, 80070057h
0x141bc1fd8  call    cs:__imp_EtwTraceErrorTag
  ... truncated ...
```
