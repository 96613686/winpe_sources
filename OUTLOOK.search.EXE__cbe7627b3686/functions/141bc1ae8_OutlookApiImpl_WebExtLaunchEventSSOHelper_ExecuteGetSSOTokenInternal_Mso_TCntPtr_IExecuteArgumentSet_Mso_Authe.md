# OutlookApiImpl::WebExtLaunchEventSSOHelper::ExecuteGetSSOTokenInternal(Mso::TCntPtr<IExecuteArgumentSet> &,Mso::Authentication::IOfficeIdentity *,_MAPIUID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x141bc1ae8`
- end: `0x141bc2bd1`
- name: `?ExecuteGetSSOTokenInternal@WebExtLaunchEventSSOHelper@OutlookApiImpl@@AEAAJAEAV?$TCntPtr@UIExecuteArgumentSet@@@Mso@@PEAUIOfficeIdentity@Authentication@4@AEBU_MAPIUID@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `4329`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140bda1c4`

## callees

- `0x14001dd7c`
- `0x1400204a0`
- `0x1400211a0`
- `0x1400215d0`
- `0x1400255e8`
- `0x14003f764`
- `0x14005e5c8`
- `0x14007131c`
- `0x1400729b4`
- `0x14007a108`
- `0x1400a6c5c`
- `0x140103fac`
- `0x140189340`
- `0x14019b174`
- `0x1401b3ff4`
- `0x140388500`
- `0x1405049f0`
- `0x1406708f0`
- `0x1407e9990`
- `0x1407eafb0`
- `0x1407eceb0`
- `0x14081178c`
- `0x1408121d4`
- `0x1408126bc`
- `0x14082dc24`
- `0x14082de78`
- `0x1409b1d90`
- `0x1409c47c4`
- `0x141bc1ae8`
- `0x141bc2be0`

## import_xrefs

- `osf99!OsfTokenHelperForOutlook_ShouldThrottlePrompt` at `0x141bc25f7`
- `osf99!OsfTokenHelperForOutlook_ShouldThrottlePrompt` at `0x141bc25f7`
- `osf99!OsfTokenHelper_ValidateResourceUrl` at `0x141bc2899`
- `osf99!OsfTokenHelper_ValidateResourceUrl` at `0x141bc2899`
- `osf99!OsfTokenHelper_GetUserIdentity` at `0x141bc294e`
- `osf99!OsfTokenHelper_GetUserIdentity` at `0x141bc294e`
- `osf99!OsfTokenHelper_GetAuthToken` at `0x141bc29e8`
- `osf99!OsfTokenHelper_GetAuthToken` at `0x141bc29e8`
- `osfshared!?LogOsfRuntimeEvent@Osf@@YAXPEB_WW4Severity@Logging@Mso@@K0ZZ` at `0x141bc2ab7`
- `osfshared!?LogOsfRuntimeEvent@Osf@@YAXPEB_WW4Severity@Logging@Mso@@K0ZZ` at `0x141bc2ab7`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1d82`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1df1`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1e8c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1f3c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1fe8`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2098`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2181`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2a49`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1d82`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1df1`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1e8c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1f3c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc1fe8`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2098`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2181`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bc2a49`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1ba8`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1bb6`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1bc4`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1bd2`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1be0`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1ba8`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1bb6`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1bc4`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1bd2`
- `OLEAUT32!__imp_VariantInit` at `0x141bc1be0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x141bc1d06`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x141bc1d06`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x141bc1cf0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x141bc1cf0`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x141bc1d2c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x141bc1d2c`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc21f7`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2232`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2575`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc21f7`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2232`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x141bc2575`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141bc2ad5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141bc2ad5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2290`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc22b2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc22d2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc22f2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2442`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc24cc`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc24ec`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc26c5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2744`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2807`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2a7e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2290`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc22b2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc22d2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc22f2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2442`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc24cc`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc24ec`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc26c5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2744`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2807`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bc2a7e`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1e4f`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1eff`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1fab`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc2057`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc2140`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1e4f`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1eff`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc1fab`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc2057`
- `Mso20Win32Client!__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141bc2140`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc24ae`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc254e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc24ae`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141bc254e`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1ec9`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1f79`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc2025`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1ec9`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc1f79`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x141bc2025`
- `Mso20Win32Client!__imp_?CreateJsonDom@Json@Mso@@YA?AV?$TCntPtr@UIJsonDom@Json@Mso@@@2@PEB_W@Z` at `0x141bc1d66`
- `Mso20Win32Client!__imp_?CreateJsonDom@Json@Mso@@YA?AV?$TCntPtr@UIJsonDom@Json@Mso@@@2@PEB_W@Z` at `0x141bc1d66`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc20dd`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc21c8`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc20dd`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x141bc21c8`

## string_xrefs

- `0x141bc1c4e`: `ExecuteGetSSOTokenInternal`
- `0x141bc1f86`: `forMSGraphAccess`
- `0x141bc22db`: `ForGraphAccess`
- `0x141bc2813`: `ServiceApplicationId not defined.`

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
  __int64 v53; // r15
  struct Mso::Telemetry::IDataFieldCollection *v54; // rbx
  __int64 PrivacyCompliantId; // rax
  __int64 v56; // rcx
  unsigned int v57; // edi
  struct Mso::Telemetry::IDataFieldCollection *v58; // rax
  struct Mso::Telemetry::IDataFieldCollection *v59; // rax
  bool v60; // bl
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  struct Mso::Telemetry::IDataFieldCollection *v68; // rax
  const char *v69; // rdx
  const char *v70; // r8
  struct Mso::Telemetry::IDataFieldCollection *v71; // rax
  __int64 v72; // rax
  bool v73; // al
  __int64 v74; // rax
  struct Mso::Telemetry::IDataFieldCollection *v75; // rax
  __int64 v76; // rax
  __int64 v77; // rbx
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // r8
  int v81; // eax
  const char *v82; // rdx
  const char *v83; // r8
  __int64 v84; // rax
  int UserIdentity; // eax
  const char *v86; // rdx
  const char *v87; // r8
  __int64 v88; // rbx
  __int128 *v89; // rdi
  __int64 v90; // rax
  __int64 v91; // rax
  const char *v92; // rdx
  __int64 v93; // rax
  unsigned int v94; // edi
  struct Mso::Telemetry::IDataFieldCollection *v95; // rax
  __int64 v96; // rcx
  struct IWebExtHost *v97; // rcx
  __int64 v98; // rcx
  _BYTE *v100; // [rsp+20h] [rbp-248h]
  bool v101; // [rsp+28h] [rbp-240h]
  const char *v102; // [rsp+38h] [rbp-230h]
  unsigned int v103; // [rsp+40h] [rbp-228h]
  bool v104; // [rsp+60h] [rbp-208h]
  bool v105; // [rsp+61h] [rbp-207h]
  int v106[2]; // [rsp+68h] [rbp-200h] BYREF
  _QWORD *v107; // [rsp+70h] [rbp-1F8h]
  char v108; // [rsp+78h] [rbp-1F0h]
  char v109[8]; // [rsp+80h] [rbp-1E8h] BYREF
  unsigned int v110; // [rsp+88h] [rbp-1E0h]
  _BYTE v111[16]; // [rsp+90h] [rbp-1D8h] BYREF
  int v112; // [rsp+A0h] [rbp-1C8h]
  __int64 v113; // [rsp+A8h] [rbp-1C0h] BYREF
  LONG plUbound; // [rsp+B0h] [rbp-1B8h] BYREF
  struct IWebExtHost *v115; // [rsp+B8h] [rbp-1B0h] BYREF
  __int64 v116; // [rsp+C0h] [rbp-1A8h] BYREF
  LONG plLbound; // [rsp+C8h] [rbp-1A0h] BYREF
  LONG rgIndices; // [rsp+CCh] [rbp-19Ch] BYREF
  __int64 v119; // [rsp+D0h] [rbp-198h] BYREF
  __int64 v120; // [rsp+D8h] [rbp-190h]
  __int64 v121; // [rsp+E0h] [rbp-188h]
  _QWORD *v122; // [rsp+E8h] [rbp-180h]
  _BYTE v123[16]; // [rsp+F0h] [rbp-178h] BYREF
  __int128 v124; // [rsp+100h] [rbp-168h] BYREF
  VARIANTARG pv; // [rsp+110h] [rbp-158h] BYREF
  _QWORD v126[2]; // [rsp+128h] [rbp-140h] BYREF
  char v127[8]; // [rsp+138h] [rbp-130h] BYREF
  VARIANTARG v128; // [rsp+140h] [rbp-128h] BYREF
  VARIANTARG v129; // [rsp+158h] [rbp-110h] BYREF
  VARIANTARG pvarg; // [rsp+170h] [rbp-F8h] BYREF
  VARIANTARG v131; // [rsp+188h] [rbp-E0h] BYREF
  _QWORD v132[3]; // [rsp+1A0h] [rbp-C8h] BYREF
  unsigned __int64 v133; // [rsp+1B8h] [rbp-B0h]
  _BYTE v134[32]; // [rsp+1C0h] [rbp-A8h] BYREF
  __int128 v135; // [rsp+1E0h] [rbp-88h] BYREF
  __int64 v136; // [rsp+1F0h] [rbp-78h]
  unsigned __int64 v137; // [rsp+1F8h] [rbp-70h]
  _OWORD v138[2]; // [rsp+200h] [rbp-68h] BYREF

  v120 = a4;
  v107 = a2;
  v122 = a2;
  v121 = a5;
  v116 = a3;
  plLbound = -1;
  plUbound = -1;
  rgIndices = 0;
  v108 = 0;
  LOBYTE(v5) = 0;
  v112 = v5;
  v8 = 0;
  v104 = 0;
  v9 = 0;
  v105 = 0;
  v135 = 0;
  v136 = 0;
  v137 = 7;
  LOWORD(v135) = 0;
  v110 = 0;
  VariantInit(&v131);
  VariantInit(&pvarg);
  VariantInit(&v129);
  VariantInit(&v128);
  VariantInit(&pv);
  v138[0] = 0;
  v138[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v138[0]) = 0;
  v119 = 0;
  v115 = 0;
  v113 = 0;
  v124 = 0;
  v10 = (const struct Mso::Telemetry::EventFlags *)Mso::Telemetry::EventFlags::EventFlags(v127, 1, 2);
  v126[0] = &off_141E28D10;
  v126[1] = "ExecuteGetSSOTokenInternal";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v111,
    (const struct Mso::Telemetry::EventName *)v126,
    v10);
  v11 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 80LL))(v11, 5001);
  if ( !v116 )
  {
    v12 = 559285337;
LABEL_3:
    SolutionSummary = -2147467259;
    v14 = 2147500037LL;
LABEL_136:
    EtwTraceErrorTag(v14, v12);
    goto LABEL_137;
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
    goto LABEL_135;
  }
  Element = SafeArrayGetElement(v17, &rgIndices, &pv);
  SolutionSummary = Element;
  if ( Element < 0 )
  {
    v12 = 559285335;
LABEL_11:
    v14 = (unsigned int)Element;
    goto LABEL_136;
  }
  if ( pv.vt != 8 )
  {
    v12 = 559285334;
LABEL_135:
    v14 = 2147942487LL;
    SolutionSummary = -2147024809;
    goto LABEL_136;
  }
  Mso::Json::CreateJsonDom(v106, pv.llVal);
  if ( !*(_QWORD *)v106 )
  {
    SolutionSummary = -2147024809;
    EtwTraceErrorTag(2147942487LL, 559285333);
    v20 = *(_QWORD *)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
    }
    v21 = v107;
    goto LABEL_138;
  }
  v22 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(v106);
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 16LL))(v22, v109);
  if ( !Mso::Json::value::is_object((Mso::Json::value *)v109) )
  {
    SolutionSummary = -2147024809;
    EtwTraceErrorTag(2147942487LL, 559285332);
    std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
    v23 = *(_QWORD *)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    }
    v21 = v107;
    goto LABEL_138;
  }
  std::wstring::wstring(v132);
  v24 = (Mso::Json::value *)Mso::Json::value::operator[](v109, v132);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v132);
  if ( !Mso::Json::value::is_null(v24) )
  {
    if ( !Mso::Json::value::is_boolean(v24) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285331);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
      v25 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      }
      v21 = v107;
      goto LABEL_138;
    }
    LOBYTE(v5) = Mso::Json::value::as_bool(v24);
    v112 = v5;
  }
  std::wstring::wstring(v132);
  v26 = (Mso::Json::value *)Mso::Json::value::operator[](v109, v132);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v132);
  if ( !Mso::Json::value::is_null(v26) )
  {
    if ( !Mso::Json::value::is_boolean(v26) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285330);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
      v27 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      }
      v21 = v107;
      goto LABEL_138;
    }
    v9 = Mso::Json::value::as_bool(v26);
    v105 = v9;
  }
  std::wstring::wstring(v132);
  v28 = (Mso::Json::value *)Mso::Json::value::operator[](v109, v132);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v132);
  if ( !Mso::Json::value::is_null(v28) )
  {
    if ( !Mso::Json::value::is_boolean(v28) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285329);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
      v29 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      }
      v21 = v107;
      goto LABEL_138;
    }
    v8 = Mso::Json::value::as_bool(v28);
    v104 = v8;
  }
  std::wstring::wstring(v132);
  v30 = (Mso::Json::value *)Mso::Json::value::operator[](v109, v132);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v132);
  if ( !Mso::Json::value::is_null(v30) )
  {
    if ( !Mso::Json::value::is_string(v30) )
    {
      SolutionSummary = -2147024809;
      EtwTraceErrorTag(2147942487LL, 559285328);
      std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
      v31 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      }
      v21 = v107;
      goto LABEL_138;
    }
    v32 = Mso::Json::value::as_string(v30, v134);
    std::wstring::operator=(&v135, v32);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v134);
    if ( v136 )
    {
      v108 = 1;
      v9 = 0;
      v105 = 0;
    }
  }
  std::wstring::wstring(v134);
  v33 = (Mso::Json::value *)Mso::Json::value::operator[](v109, v134);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v134);
  if ( Mso::Json::value::is_null(v33) )
  {
LABEL_62:
    std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
    v39 = *(_QWORD *)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    }
    v40 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    LOBYTE(v41) = v108;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v40, "AuthChallengeDefined", v41);
    v42 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    LOBYTE(v43) = v5;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v42, "AllowInteractiveConsent", v43);
    v44 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    LOBYTE(v45) = v8;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v44, "ForGraphAccess", v45);
    v46 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    LOBYTE(v47) = v9;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v46, "AllowSignInPrompt", v47);
    Element = HrGetWebExtHost(&v115, 0, 0);
    SolutionSummary = Element;
    if ( Element < 0 )
    {
      v12 = 559285324;
      goto LABEL_11;
    }
    if ( !v115 )
    {
      v12 = 559285323;
      goto LABEL_3;
    }
    v48 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v115);
    v49 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v48 + 480LL))(v48, v123, *(_QWORD *)a1);
    std::shared_ptr<MeetingAttendeeGridDpiDetails>::operator=(&v124, v49);
    std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(v123);
    v50 = v124;
    if ( !(_QWORD)v124 )
    {
      v12 = 559285322;
      goto LABEL_3;
    }
    v51 = v120;
    v52 = HexizeEmsmdbUID(v132, v120);
    v53 = v50 + 56;
    std::wstring::wstring(v134);
    SolutionSummary = HrWebExtGetSolutionSummary(v134, v52, &v113, 0x1FFF);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v134);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v132);
    if ( SolutionSummary < 0 )
    {
      v12 = 559285321;
      v14 = (unsigned int)SolutionSummary;
      goto LABEL_136;
    }
    if ( !v113 )
    {
      v12 = 559285320;
      goto LABEL_3;
    }
    v54 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    std::wstring::wstring(v134);
    PrivacyCompliantId = WebExt::GetPrivacyCompliantId(v134, v51);
    Mso::Telemetry::IDataFieldCollection::Add(v54, "SolutionId", PrivacyCompliantId, 4);
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v134);
    v56 = v113;
    if ( !v113 )
      CrashWithRecovery(0x1E3C3840u, 0);
    v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 80LL))(v56);
    v58 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v58, "StoreType", v57);
    v59 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v59, "AccountTypeFilter", v110);
    Element = OutlookApiImpl::WebExtLaunchEventSSOHelper::InitializeAppProperties(a1, &v113);
    SolutionSummary = Element;
    if ( Element < 0 )
    {
      v12 = 559285319;
      goto LABEL_11;
    }
    if ( v57 == 3 )
    {
      v60 = v104;
      if ( !v104 )
        goto LABEL_92;
      v61 = v113;
      if ( !v113 )
        CrashWithRecovery(0x1E3C3840u, 0);
      v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 560LL))(v61);
      if ( (unsigned int)MsoFWzEqual(v62, L"User", 1) )
      {
        v63 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 80LL))(v63, 13012);
        v12 = 559285318;
        goto LABEL_3;
      }
    }
    else
    {
      if ( v57 - 1 <= 1 )
      {
        v12 = 559285317;
        goto LABEL_3;
      }
      if ( !v57 || v57 == 7 )
      {
        if ( v104 )
        {
          v66 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 80LL))(v66, 13012);
          v12 = 559285316;
          goto LABEL_3;
        }
LABEL_92:
        if ( v105 || (_BYTE)v5 )
        {
          if ( *(_BYTE *)(a1 + 120) )
          {
            v64 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 88);
            if ( (unsigned __int8)OsfTokenHelperForOutlook_ShouldThrottlePrompt(v64) )
            {
              v65 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 80LL))(v65, 13013);
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
          if ( (!v57 || v57 == 7) && !*(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 168) + 16) )
          {
            v71 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
            Mso::Telemetry::IDataFieldCollection::Add(v71, "Error", L"Missing asset ID for OMEX add-in", 4);
            std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v53);
            v72 = std::wstring::wstring(v134);
            std::_Optional_construct_base<std::wstring>::_Assign<std::wstring>(a1 + 168, v72);
            std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v134);
          }
          v73 = !*(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 168) + 16)
             && !*(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 48) + 16);
          if ( v57 == 12 )
            v73 = 1;
          if ( !v73 || *(_QWORD *)(std::_Optional_construct_base<std::wstring>::operator*(a1 + 88) + 16) )
          {
            v76 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 88);
            v77 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v76);
            v78 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 8);
            std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v78);
            v79 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121);
            v101 = 0;
            v100 = v111;
            v81 = OsfTokenHelper_ValidateResourceUrl(*a2, v79, v80, v77);
            v106[0] = v81;
            if ( v81 < 0 )
            {
              HandleCORgError_Impl(0, v82, v83, 0, (bool)v111, 0, 0, v102, 0x21560421u, v81, v106);
              goto LABEL_106;
            }
            if ( v105 || v116 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v116 + 296LL))(v116) )
            {
              LOBYTE(v82) = v105;
              UserIdentity = OsfTokenHelper_GetUserIdentity(*a2, v82, v110, v111);
              v106[0] = UserIdentity;
              if ( UserIdentity >= 0 )
              {
                v88 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v53);
                v89 = &v135;
                if ( v137 > 7 )
                  v89 = (__int128 *)v135;
                v90 = std::_Optional_construct_base<std::wstring>::operator*(a1 + 8);
                v91 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v90);
                v100 = (_BYTE *)v88;
                SolutionSummary = OsfTokenHelper_GetAuthToken(*a2, v116, v91, v89);
                v106[0] = SolutionSummary;
                if ( SolutionSummary >= 0 )
                  goto LABEL_137;
                HandleCORgError_Impl(
                  0,
                  v92,
                  v19,
                  0,
                  (bool)v100,
                  (bool)v111,
                  0,
                  (const char *)&v119,
                  0x2156041Eu,
                  SolutionSummary,
                  v106);
              }
              else
              {
                HandleCORgError_Impl(0, v86, v87, 0, (bool)&v116, 0, 0, v102, 0x2156041Fu, UserIdentity, v106);
              }
              goto LABEL_106;
            }
            v84 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 80LL))(v84, 13001);
            v103 = 559285280;
          }
          else
          {
            v74 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v74 + 80LL))(v74, 13000);
            v75 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
            Mso::Telemetry::IDataFieldCollection::Add(v75, "Error", L"ServiceApplicationId not defined.", 4);
            v103 = 559285282;
          }
        }
        else
        {
          v67 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 80LL))(v67, 13000);
          v68 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
          Mso::Telemetry::IDataFieldCollection::Add(v68, "Error", L"AppResource not defined.", 4);
          v103 = 559285313;
        }
        v106[0] = -2147467259;
        HandleCORgError_Impl(0, v69, v70, 0, (bool)v100, v101, 0, v102, v103, -2147467259, v106);
LABEL_106:
        SolutionSummary = v106[0];
LABEL_137:
        v21 = v107;
        goto LABEL_138;
      }
      v60 = v104;
    }
    if ( v60 )
    {
      v5 = (unsigned __int8)v5;
      if ( v57 == 10 )
        v5 = 0;
      v112 = v5;
    }
    goto LABEL_92;
  }
  if ( Mso::Json::value::is_string(v33) )
  {
    Mso::Json::value::as_string(v33, v132);
    v35 = v132;
    if ( v133 > 7 )
      v35 = (_QWORD *)v132[0];
    if ( (unsigned int)MsoFWzEqual(v35, L"msa", 1) )
    {
      v110 = 2;
    }
    else
    {
      v36 = v132;
      if ( v133 > 7 )
        v36 = (_QWORD *)v132[0];
      v37 = MsoFWzEqual(v36, L"aad", 1);
      v38 = v110;
      if ( v37 )
        v38 = 1;
      v110 = v38;
    }
    std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v132);
    goto LABEL_62;
  }
  SolutionSummary = -2147024809;
  EtwTraceErrorTag(2147942487LL, 559285327);
  std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(v109);
  v34 = *(_QWORD *)v106;
  if ( *(_QWORD *)v106 )
  {
    *(_QWORD *)v106 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
  }
  v21 = v107;
LABEL_138:
  if ( *v21 )
  {
    v93 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(a2);
    v94 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 88LL))(v93);
    v95 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v111);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v95, "OsfOmError", v94);
    if ( v94 )
    {
      LODWORD(v100) = v94;
      Osf::LogOsfRuntimeEvent(L"WebApplicationInfo", 15, 505992770, L"SSO failed with \"%d\" error code.", v100);
    }
  }
  Mso::Telemetry::SetActivityResultHr(
    (Mso::Telemetry *)v111,
    (struct Mso::Telemetry::Activity *)(unsigned int)SolutionSummary,
    (int)v19);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v111);
  std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v124);
  v96 = v113;
  if ( v113 )
  {
    v113 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  }
  v97 = v115;
  if ( v115 )
  {
    v115 = 0;
    (*(void (__fastcall **)(struct IWebExtHost *))(*(_QWORD *)v97 + 16LL))(v97);
  }
  v98 = v119;
  if ( v119 )
  {
    v119 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
  }
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v138);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&pv);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&v128);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&v129);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&pvarg);
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&v131);
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&v135);
  return (unsigned int)SolutionSummary;
}

```

## disassembly

```asm
0x141bc1ae8  mov     r11, rsp
0x141bc1aeb  push    rbx
0x141bc1aec  push    rsi
0x141bc1aed  push    rdi
0x141bc1aee  push    r12
0x141bc1af0  push    r13
0x141bc1af2  push    r14
0x141bc1af4  push    r15
0x141bc1af6  sub     rsp, 230h
0x141bc1afd  mov     rax, cs:__security_cookie
0x141bc1b04  xor     rax, rsp
0x141bc1b07  mov     [rsp+268h+var_48], rax
0x141bc1b0f  mov     [rsp+268h+var_190], r9
0x141bc1b17  mov     [rsp+268h+var_1F8], rdx
0x141bc1b1c  mov     r14, rcx
0x141bc1b1f  mov     [rsp+268h+var_180], rdx
0x141bc1b27  mov     rbx, [rsp+268h+arg_20]
0x141bc1b2f  mov     [rsp+268h+var_188], rbx
0x141bc1b37  mov     r12, rdx
0x141bc1b3a  mov     [r11-1A8h], r8
0x141bc1b41  or      eax, 0FFFFFFFFh
0x141bc1b44  mov     [rsp+268h+plLbound], eax
0x141bc1b4b  mov     [rsp+268h+plUbound], eax
0x141bc1b52  xor     esi, esi
0x141bc1b54  mov     [rsp+268h+rgIndices], esi
0x141bc1b5b  mov     [rsp+268h+var_1F0], sil
0x141bc1b60  mov     r13b, sil
0x141bc1b63  mov     [rsp+268h+var_1C8], r13d
0x141bc1b6b  mov     dil, sil
0x141bc1b6e  mov     [rsp+268h+var_208], sil
0x141bc1b73  mov     r15b, sil
0x141bc1b76  mov     [rsp+268h+var_207], sil
0x141bc1b7b  xorps   xmm0, xmm0
0x141bc1b7e  movups  [rsp+268h+var_88], xmm0
0x141bc1b86  mov     [r11-78h], rsi
0x141bc1b8a  mov     qword ptr [r11-70h], 7
0x141bc1b92  mov     word ptr [rsp+268h+var_88], si
0x141bc1b9a  mov     [rsp+268h+var_1E0], esi
0x141bc1ba1  lea     rcx, [r11-0E0h]; pvarg
0x141bc1ba8  call    cs:__imp_VariantInit
0x141bc1bae  lea     rcx, [rsp+268h+pvarg]; pvarg
0x141bc1bb6  call    cs:__imp_VariantInit
0x141bc1bbc  lea     rcx, [rsp+268h+var_110]; pvarg
0x141bc1bc4  call    cs:__imp_VariantInit
0x141bc1bca  lea     rcx, [rsp+268h+var_128]; pvarg
0x141bc1bd2  call    cs:__imp_VariantInit
0x141bc1bd8  lea     rcx, [rsp+268h+pv]; pvarg
0x141bc1be0  call    cs:__imp_VariantInit
0x141bc1be6  xorps   xmm0, xmm0
0x141bc1be9  movups  [rsp+268h+var_68], xmm0
0x141bc1bf1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x141bc1bf9  movdqu  [rsp+268h+var_58], xmm1
0x141bc1c02  mov     word ptr [rsp+268h+var_68], si
0x141bc1c0a  mov     [rsp+268h+var_198], rsi
0x141bc1c12  mov     [rsp+268h+var_1B0], rsi
0x141bc1c1a  mov     [rsp+268h+var_1C0], rsi
0x141bc1c22  movdqu  [rsp+268h+var_168], xmm0
0x141bc1c2b  lea     edx, [rsi+1]
0x141bc1c2e  lea     r8d, [rsi+2]
0x141bc1c32  lea     rcx, [rsp+268h+var_130]
0x141bc1c3a  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4SamplingPolicy@12@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::SamplingPolicy,Mso::Telemetry::DataCategories)
0x141bc1c3f  lea     rcx, off_141E28D10
0x141bc1c46  mov     [rsp+268h+var_140], rcx
0x141bc1c4e  lea     rcx, aExecutegetssot; "ExecuteGetSSOTokenInternal"
0x141bc1c55  mov     [rsp+268h+var_138], rcx
0x141bc1c5d  mov     r8, rax; struct Mso::Telemetry::EventFlags *
0x141bc1c60  lea     rdx, [rsp+268h+var_140]; struct Mso::Telemetry::EventName *
0x141bc1c68  lea     rcx, [rsp+268h+var_1D8]; this
0x141bc1c70  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x141bc1c75  mov     rcx, r12
0x141bc1c78  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x141bc1c7d  mov     rcx, rax
0x141bc1c80  mov     rax, [rax]
0x141bc1c83  mov     edx, 1389h
0x141bc1c88  mov     rax, [rax+50h]
0x141bc1c8c  call    cs:__guard_dispatch_icall_fptr
0x141bc1c92  cmp     [rsp+268h+var_1A8], rsi
0x141bc1c9a  jnz     short loc_141BC1CB0
0x141bc1c9c  mov     edx, 21560459h
0x141bc1ca1  mov     ebx, 80004005h
0x141bc1ca6  mov     ecx, 80004005h
0x141bc1cab  jmp     loc_141BC2A49
0x141bc1cb0  cmp     [rbx+10h], rsi
0x141bc1cb4  jnz     short loc_141BC1CBD
0x141bc1cb6  mov     edx, 21560458h
0x141bc1cbb  jmp     short loc_141BC1CA1
0x141bc1cbd  mov     rcx, r12
0x141bc1cc0  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x141bc1cc5  mov     rcx, rax
0x141bc1cc8  mov     rax, [rax]
0x141bc1ccb  mov     rax, [rax+80h]
0x141bc1cd2  call    cs:__guard_dispatch_icall_fptr
0x141bc1cd8  mov     rbx, rax
0x141bc1cdb  test    rax, rax
0x141bc1cde  jz      short loc_141BC1D0C
0x141bc1ce0  lea     r8, [rsp+268h+plLbound]; plLbound
0x141bc1ce8  mov     edx, 1; nDim
0x141bc1ced  mov     rcx, rax; psa
0x141bc1cf0  call    cs:__imp_SafeArrayGetLBound
0x141bc1cf6  lea     r8, [rsp+268h+plUbound]; plUbound
0x141bc1cfe  mov     edx, 1; nDim
0x141bc1d03  mov     rcx, rbx; psa
0x141bc1d06  call    cs:__imp_SafeArrayGetUBound
0x141bc1d0c  cmp     [rsp+268h+plUbound], esi
0x141bc1d13  jnz     loc_141BC2A3A
0x141bc1d19  lea     r8, [rsp+268h+pv]; pv
0x141bc1d21  lea     rdx, [rsp+268h+rgIndices]; rgIndices
0x141bc1d29  mov     rcx, rbx; psa
0x141bc1d2c  call    cs:__imp_SafeArrayGetElement
0x141bc1d32  mov     ebx, eax
0x141bc1d34  test    eax, eax
0x141bc1d36  jns     short loc_141BC1D44
0x141bc1d38  mov     edx, 21560457h
0x141bc1d3d  mov     ecx, eax
0x141bc1d3f  jmp     loc_141BC2A49
0x141bc1d44  cmp     word ptr [rsp+268h+pv], 8
0x141bc1d4d  jz      short loc_141BC1D59
0x141bc1d4f  mov     edx, 21560456h
0x141bc1d54  jmp     loc_141BC2A3F
0x141bc1d59  mov     rdx, qword ptr [rsp+268h+pv+8]
0x141bc1d61  lea     rcx, [rsp+268h+var_200]
0x141bc1d66  call    cs:__imp_?CreateJsonDom@Json@Mso@@YA?AV?$TCntPtr@UIJsonDom@Json@Mso@@@2@PEB_W@Z; Mso::Json::CreateJsonDom(wchar_t const *)
0x141bc1d6c  cmp     qword ptr [rsp+268h+var_200], rsi
0x141bc1d71  jnz     short loc_141BC1DAF
0x141bc1d73  mov     ebx, 80070057h
0x141bc1d78  mov     edx, 21560455h
0x141bc1d7d  mov     ecx, 80070057h
0x141bc1d82  call    cs:__imp_EtwTraceErrorTag
0x141bc1d88  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1d8d  test    rcx, rcx
0x141bc1d90  jz      short loc_141BC1DA5
0x141bc1d92  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1d97  mov     rax, [rcx]
0x141bc1d9a  mov     rax, [rax+8]
0x141bc1d9e  call    cs:__guard_dispatch_icall_fptr
0x141bc1da4  nop
0x141bc1da5  mov     rax, [rsp+268h+var_1F8]
0x141bc1daa  jmp     loc_141BC2A54
0x141bc1daf  lea     rcx, [rsp+268h+var_200]
0x141bc1db4  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x141bc1db9  mov     rcx, rax
0x141bc1dbc  mov     rax, [rax]
0x141bc1dbf  lea     rdx, [rsp+268h+var_1E8]
0x141bc1dc7  mov     rax, [rax+10h]
0x141bc1dcb  call    cs:__guard_dispatch_icall_fptr
0x141bc1dd1  lea     rcx, [rsp+268h+var_1E8]; this
0x141bc1dd9  call    ?is_object@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_object(void)
0x141bc1dde  test    al, al
0x141bc1de0  jnz     short loc_141BC1E2B
0x141bc1de2  mov     ebx, 80070057h
0x141bc1de7  mov     edx, 21560454h
0x141bc1dec  mov     ecx, 80070057h
0x141bc1df1  call    cs:__imp_EtwTraceErrorTag
0x141bc1df7  lea     rcx, [rsp+268h+var_1E8]
0x141bc1dff  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1e04  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1e09  test    rcx, rcx
0x141bc1e0c  jz      short loc_141BC1E21
0x141bc1e0e  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1e13  mov     rax, [rcx]
0x141bc1e16  mov     rax, [rax+8]
0x141bc1e1a  call    cs:__guard_dispatch_icall_fptr
0x141bc1e20  nop
0x141bc1e21  mov     rax, [rsp+268h+var_1F8]
0x141bc1e26  jmp     loc_141BC2A54
0x141bc1e2b  lea     rdx, aAllowconsentpr; "allowConsentPrompt"
0x141bc1e32  lea     rcx, [rsp+268h+var_C8]
0x141bc1e3a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1e3f  lea     rdx, [rsp+268h+var_C8]
0x141bc1e47  lea     rcx, [rsp+268h+var_1E8]
0x141bc1e4f  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1e55  mov     rbx, rax
0x141bc1e58  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1e60  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1e65  mov     rcx, rbx; this
0x141bc1e68  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1e6d  test    al, al
0x141bc1e6f  jnz     short loc_141BC1EDA
0x141bc1e71  mov     rcx, rbx; this
0x141bc1e74  call    ?is_boolean@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_boolean(void)
0x141bc1e79  test    al, al
0x141bc1e7b  jnz     short loc_141BC1EC6
0x141bc1e7d  mov     ebx, 80070057h
0x141bc1e82  mov     edx, 21560453h
0x141bc1e87  mov     ecx, 80070057h
0x141bc1e8c  call    cs:__imp_EtwTraceErrorTag
0x141bc1e92  lea     rcx, [rsp+268h+var_1E8]
0x141bc1e9a  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1e9f  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1ea4  test    rcx, rcx
0x141bc1ea7  jz      short loc_141BC1EBC
0x141bc1ea9  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1eae  mov     rax, [rcx]
0x141bc1eb1  mov     rax, [rax+8]
0x141bc1eb5  call    cs:__guard_dispatch_icall_fptr
0x141bc1ebb  nop
0x141bc1ebc  mov     rax, [rsp+268h+var_1F8]
0x141bc1ec1  jmp     loc_141BC2A54
0x141bc1ec6  mov     rcx, rbx
0x141bc1ec9  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x141bc1ecf  mov     r13b, al
0x141bc1ed2  mov     [rsp+268h+var_1C8], r13d
0x141bc1eda  lea     rdx, aAllowsigninpro_0; "allowSignInPrompt"
0x141bc1ee1  lea     rcx, [rsp+268h+var_C8]
0x141bc1ee9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1eee  nop
0x141bc1eef  lea     rdx, [rsp+268h+var_C8]
0x141bc1ef7  lea     rcx, [rsp+268h+var_1E8]
0x141bc1eff  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1f05  mov     rbx, rax
0x141bc1f08  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1f10  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1f15  mov     rcx, rbx; this
0x141bc1f18  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1f1d  test    al, al
0x141bc1f1f  jnz     short loc_141BC1F86
0x141bc1f21  mov     rcx, rbx; this
0x141bc1f24  call    ?is_boolean@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_boolean(void)
0x141bc1f29  test    al, al
0x141bc1f2b  jnz     short loc_141BC1F76
0x141bc1f2d  mov     ebx, 80070057h
0x141bc1f32  mov     edx, 21560452h
0x141bc1f37  mov     ecx, 80070057h
0x141bc1f3c  call    cs:__imp_EtwTraceErrorTag
0x141bc1f42  lea     rcx, [rsp+268h+var_1E8]
0x141bc1f4a  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1f4f  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc1f54  test    rcx, rcx
0x141bc1f57  jz      short loc_141BC1F6C
0x141bc1f59  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc1f5e  mov     rax, [rcx]
0x141bc1f61  mov     rax, [rax+8]
0x141bc1f65  call    cs:__guard_dispatch_icall_fptr
0x141bc1f6b  nop
0x141bc1f6c  mov     rax, [rsp+268h+var_1F8]
0x141bc1f71  jmp     loc_141BC2A54
0x141bc1f76  mov     rcx, rbx
0x141bc1f79  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x141bc1f7f  mov     r15b, al
0x141bc1f82  mov     [rsp+268h+var_207], al
0x141bc1f86  lea     rdx, aFormsgraphacce; "forMSGraphAccess"
0x141bc1f8d  lea     rcx, [rsp+268h+var_C8]
0x141bc1f95  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc1f9a  nop
0x141bc1f9b  lea     rdx, [rsp+268h+var_C8]
0x141bc1fa3  lea     rcx, [rsp+268h+var_1E8]
0x141bc1fab  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc1fb1  mov     rbx, rax
0x141bc1fb4  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc1fbc  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc1fc1  mov     rcx, rbx; this
0x141bc1fc4  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc1fc9  test    al, al
0x141bc1fcb  jnz     short loc_141BC2032
0x141bc1fcd  mov     rcx, rbx; this
0x141bc1fd0  call    ?is_boolean@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_boolean(void)
0x141bc1fd5  test    al, al
0x141bc1fd7  jnz     short loc_141BC2022
0x141bc1fd9  mov     ebx, 80070057h
0x141bc1fde  mov     edx, 21560451h
0x141bc1fe3  mov     ecx, 80070057h
0x141bc1fe8  call    cs:__imp_EtwTraceErrorTag
0x141bc1fee  lea     rcx, [rsp+268h+var_1E8]
0x141bc1ff6  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x141bc1ffb  mov     rcx, qword ptr [rsp+268h+var_200]
0x141bc2000  test    rcx, rcx
0x141bc2003  jz      short loc_141BC2018
0x141bc2005  mov     qword ptr [rsp+268h+var_200], rsi
0x141bc200a  mov     rax, [rcx]
0x141bc200d  mov     rax, [rax+8]
0x141bc2011  call    cs:__guard_dispatch_icall_fptr
0x141bc2017  nop
0x141bc2018  mov     rax, [rsp+268h+var_1F8]
0x141bc201d  jmp     loc_141BC2A54
0x141bc2022  mov     rcx, rbx
0x141bc2025  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x141bc202b  mov     dil, al
0x141bc202e  mov     [rsp+268h+var_208], al
0x141bc2032  lea     rdx, aAuthchallenge_1; "authChallenge"
0x141bc2039  lea     rcx, [rsp+268h+var_C8]
0x141bc2041  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x141bc2046  nop
0x141bc2047  lea     rdx, [rsp+268h+var_C8]
0x141bc204f  lea     rcx, [rsp+268h+var_1E8]
0x141bc2057  call    cs:__imp_??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x141bc205d  mov     rbx, rax
0x141bc2060  lea     rcx, [rsp+268h+var_C8]; void *
0x141bc2068  call    ??1?$basic_string@_WUcase_insensitive_wchar_traits@@V?$allocator@_W@std@@@std@@QEAA@XZ; std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(void)
0x141bc206d  mov     rcx, rbx; this
0x141bc2070  call    ?is_null@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_null(void)
0x141bc2075  test    al, al
0x141bc2077  jnz     loc_141BC2117
0x141bc207d  mov     rcx, rbx; this
0x141bc2080  call    ?is_string@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::is_string(void)
0x141bc2085  test    al, al
0x141bc2087  jnz     short loc_141BC20D2
0x141bc2089  mov     ebx, 80070057h
0x141bc208e  mov     edx, 21560450h
0x141bc2093  mov     ecx, 80070057h
0x141bc2098  call    cs:__imp_EtwTraceErrorTag
  ... truncated ...
```
