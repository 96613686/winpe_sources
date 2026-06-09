# CUpdateEvaluator::ServiceFeatureAndPackages(ServiceFeatureAndPackagesFlags,FeatureIntentFlags,FeatureIntentFlags,std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &,std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &,CUpdateEvaluator::Feature *,CCompositionDatabase::Feature const *,CCompositionDatabase const *,CActionListCreator *)

- ea: `0x1800d7934`
- end: `0x1800d8bb6`
- name: `?ServiceFeatureAndPackages@CUpdateEvaluator@@AEAAJW4ServiceFeatureAndPackagesFlags@@W4FeatureIntentFlags@@1AEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@2PEAUFeature@1@PEBU6CCompositionDatabase@@PEBV7@PEAVCActionListCreator@@@Z`
- size: `4738`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, struct CCompositionDatabase::Feature *, __int64, __int64)`
- caller_count: `1`
- callee_count: `37`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d8bbc`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000cd74`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18001a2d0`
- `0x18001a810`
- `0x18001b9e4`
- `0x18001ba14`
- `0x18001ba4c`
- `0x18001be70`
- `0x18001c4f0`
- `0x18001c608`
- `0x18001d368`
- `0x180051468`
- `0x180065a7c`
- `0x180067464`
- `0x180081b38`
- `0x1800887a8`
- `0x180088a24`
- `0x18008931c`
- `0x180089758`
- `0x1800a637c`
- `0x1800a7f14`
- `0x1800c763c`
- `0x1800c8794`
- `0x1800caa70`
- `0x1800cadfc`
- `0x1800ce920`
- `0x1800cea18`
- `0x1800cec2c`
- `0x1800d1b14`
- `0x1800d7934`
- `0x1800de728`
- `0x180182d08`
- `0x1801832a4`

## string_xrefs

- `0x1800d7a3c`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800d8a9e`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800d8b2a`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800d8b8e`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800d85f5`: `UpdateOS`
- `0x1800d79ec`: `Invalid flags passed to ServiceFeatureAndPackages. Cannot specify both update and install.`
- `0x1800d7b90`: `Failed adding token updates for feature`
- `0x1800d7aba`: `Failed adding InstallFeature: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800d7a5b`: `Installing feature: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800d7a62`: `Updating installed feature: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800d7e2c`: `Failed to find Overlay package for Feature Update media`
- `0x1800d7d5d`: `Unable to find Overlay package for Feature Update media; assuming media is Overlay compatible`
- `0x1800d7bf3`: `Feature is already scheduled for install: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800d8196`: `  Skipping already installed Package: {0}`
- `0x1800d8180`: `  LCU Package is already installed but reoffer requested; reinstalling: {0}`
- `0x1800d898d`: `CumulativeUpdate feature only supports a single package currently`
- `0x1800d85b8`: `  Installing using express Package: {0}`
- `0x1800d8552`: `  Installing using PSFX: {0}`
- `0x1800d87f7`: `  Installing using canonical Package: {0}`
- `0x1800d874d`: `  Installing using diff with source Package: {0} for Package: {1}`
- `0x1800d86fe`: `  Installing using universal diff with source Package: {0}, baseline Package: {1} for Package: {2}`
- `0x1800d8ae5`: `Failed adding InstallPackage: Package: {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUpdateEvaluator::ServiceFeatureAndPackages(
        CUpdateEvaluator *a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        struct CCompositionDatabase::Feature *a8,
        __int64 a9,
        CActionListCreator *a10)
{
  int v12; // ecx
  char v13; // al
  const wchar_t *const *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rdx
  char *v18; // rdi
  char *v19; // r14
  __int64 *v20; // rsi
  const char *v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // edx
  __int64 v25; // rdx
  struct CCompositionDatabase::Feature *v26; // r15
  int v27; // eax
  __int64 v28; // r12
  __int64 v29; // rdx
  CUpdateEvaluator *v30; // rsi
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  char v38; // r9
  char v39; // bl
  __int64 v40; // rdi
  __int64 v41; // rcx
  __int64 *v42; // rax
  __int64 *v43; // r8
  int v44; // edx
  _QWORD *v45; // rcx
  _QWORD *v46; // r14
  unsigned __int64 v47; // r11
  unsigned __int64 v48; // r8
  unsigned __int64 v49; // r9
  __int64 *v50; // rcx
  __int64 *v51; // r10
  __int64 v52; // rdx
  int v53; // eax
  __int64 v54; // rdx
  char v55; // al
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rsi
  __int64 v59; // r12
  wchar_t *v60; // r15
  struct CCompositionDatabase::Feature **v61; // rdi
  struct CCompositionDatabase::Feature **v62; // r14
  struct CCompositionDatabase::Feature *v63; // rcx
  struct CCompositionDatabase::Feature *v64; // rax
  CUpdateEvaluator *v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rcx
  unsigned int v68; // eax
  int v69; // ecx
  const wchar_t *const *v70; // rdi
  wchar_t *v71; // rax
  struct CUpdateEvaluator::Package *PackageInAnyGroup; // rax
  wchar_t *v73; // r15
  __int64 v74; // r10
  __int64 v75; // rdx
  bool v76; // zf
  unsigned __int64 v77; // rdx
  __int64 i; // rdi
  __int64 v79; // r14
  __int64 v80; // rbx
  __int64 v81; // rsi
  _QWORD *v82; // rbx
  _QWORD *v83; // rdi
  __int128 v84; // rdi
  CUpdateEvaluator *v85; // rbx
  int v86; // eax
  __int64 v87; // rdx
  _BYTE *v88; // rax
  _BYTE *v89; // rcx
  __int64 v90; // rax
  __int64 *v91; // rdi
  __int64 *v92; // rbx
  __int64 v93; // rax
  __int64 v94; // rbx
  char v95; // cl
  __int64 InstalledCBSPackage; // rax
  _QWORD *v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rdx
  int v100; // r8d
  struct CUpdateEvaluator::Package *VersionlessPackageInAnyGroup; // rax
  __int64 v102; // rdx
  __int64 v103; // rdx
  __int64 v104; // rdx
  __int64 v105; // rdx
  __int64 v106; // rdx
  __int64 v107; // rdx
  int *v108; // [rsp+20h] [rbp-E0h]
  __int64 v109; // [rsp+28h] [rbp-D8h]
  char v110; // [rsp+40h] [rbp-C0h] BYREF
  bool v111; // [rsp+41h] [rbp-BFh]
  char v112; // [rsp+42h] [rbp-BEh]
  CUpdateEvaluator *v113; // [rsp+48h] [rbp-B8h]
  char v114; // [rsp+50h] [rbp-B0h]
  char v115; // [rsp+51h] [rbp-AFh]
  int v116; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t *v117; // [rsp+58h] [rbp-A8h] BYREF
  struct CCompositionDatabase::Feature *v118; // [rsp+60h] [rbp-A0h]
  int v119[2]; // [rsp+68h] [rbp-98h] BYREF
  BOOL v120; // [rsp+70h] [rbp-90h]
  __int64 v121; // [rsp+78h] [rbp-88h] BYREF
  int v122; // [rsp+80h] [rbp-80h]
  int v123[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v124; // [rsp+98h] [rbp-68h] BYREF
  CActionListCreator *v125; // [rsp+A0h] [rbp-60h]
  __int64 v126; // [rsp+A8h] [rbp-58h]
  __int64 v127; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v128; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v129; // [rsp+C0h] [rbp-40h]
  __int64 v130; // [rsp+C8h] [rbp-38h]
  __int64 v131; // [rsp+D0h] [rbp-30h]
  __int64 v132; // [rsp+D8h] [rbp-28h]
  int v133; // [rsp+E0h] [rbp-20h] BYREF
  int v134; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v135[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v136; // [rsp+F8h] [rbp-8h]
  int ApplicableFeaturePackageIntent; // [rsp+100h] [rbp+0h] BYREF
  int v138; // [rsp+104h] [rbp+4h] BYREF
  __int128 v139; // [rsp+108h] [rbp+8h] BYREF
  __int64 v140; // [rsp+118h] [rbp+18h]
  __int128 v141; // [rsp+120h] [rbp+20h] BYREF
  __int64 v142; // [rsp+130h] [rbp+30h]
  __int128 v143; // [rsp+138h] [rbp+38h] BYREF
  __int64 v144; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v132 = -2;
  v113 = a1;
  v130 = a5;
  v129 = a6;
  v118 = a8;
  v131 = a9;
  v125 = a10;
  v134 = a2 & 0x20;
  v12 = a2 | 0xC;
  if ( (a2 & 0x20) == 0 )
    v12 = a2;
  v122 = v12;
  v13 = v12 & 1;
  if ( (v12 & 1) != 0 && (v12 & 2) != 0 )
  {
    LODWORD(v14) = -2147024809;
    v134 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Invalid flags passed to ServiceFeatureAndPackages. Cannot specify both update and install.");
      *(_QWORD *)v119 = &v134;
      v108 = v119;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v15,
        3,
        ": {}");
    }
    v16 = 963;
    goto LABEL_8;
  }
  v18 = (char *)a8 + 56;
  v19 = (char *)a8 + 64;
  v20 = (__int64 *)((char *)a8 + 72);
  v21 = "Updating installed feature: Group: {0}, FMID: {1}, Feature: {2}";
  if ( !v13 )
    v21 = "Installing feature: Group: {0}, FMID: {1}, Feature: {2}";
  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v21, (char *)a8 + 72, (char *)a8 + 64, (char *)a8 + 56);
  v116 = 0;
  v22 = CActionListCreator::InstallFeature(v125, a8, (enum CActionListCreator::InstallFeatureDisposition *)&v116);
  LODWORD(v14) = v22;
  if ( v22 < 0 )
  {
    v134 = v22;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed adding InstallFeature: Group: {0}, FMID: {1}, Feature: {2}",
        v20,
        v19,
        v18);
      *(_QWORD *)v119 = &v134;
      v108 = v119;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v23,
        3,
        ": {}");
    }
    v16 = 979;
    goto LABEL_8;
  }
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::emplace<wchar_t * const &>(
    (char *)v113 + 64,
    v123,
    v18);
  if ( a7 )
    v24 = *(_DWORD *)(a7 + 52);
  else
    v24 = 0;
  ApplicableFeaturePackageIntent = GetApplicableFeaturePackageIntent(v118, ~a4 & (a3 | v24));
  if ( *(_DWORD *)v113 )
  {
    v26 = v118;
    v28 = 0;
  }
  else
  {
    v109 = *v20;
    v26 = v118;
    LODWORD(v108) = (_DWORD)v118;
    LOBYTE(v25) = 1;
    v27 = CUpdateEvaluator::DetermineFeatureTokenChanges(v113, v25, a3, a4);
    LODWORD(v14) = v27;
    v28 = 0;
    if ( v27 < 0 )
    {
      v134 = v27;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed adding token updates for feature");
        *(_QWORD *)v119 = &v134;
        v108 = v119;
        LOBYTE(v29) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v29,
          3,
          ": {}");
      }
      v16 = 995;
      goto LABEL_8;
    }
  }
  if ( v116 == 2 )
  {
    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
      "Feature is already scheduled for install: Group: {0}, FMID: {1}, Feature: {2}",
      v20,
      v19,
      v18);
    return 0;
  }
  v30 = v113;
  v31 = *((_DWORD *)v113 + 12);
  if ( v31 == 2 && *((_BYTE *)v113 + 119)
    || !(v111 = *(_DWORD *)v113 != 1)
    && (*((_BYTE *)v26 + 368) == 17
     || *((_BYTE *)v26 + 368) == 21
     || (unsigned int)*((unsigned __int8 *)v26 + 368) - 22 <= 1
     || (v32 = v31 - 1) != 0
     && (v33 = v32 - 1) != 0
     && (v34 = v33 - 12) != 0
     && (v35 = v34 - 1) != 0
     && (v36 = v35 - 4) != 0
     && (v37 = v36 - 3) != 0
     && v37 != 2) )
  {
    v111 = 1;
  }
  v38 = *((_BYTE *)v125 + 77);
  v114 = v38;
  v39 = *((_BYTE *)v125 + 76);
  v115 = v39;
  v40 = 0;
  v126 = 0;
  v41 = *((_QWORD *)v26 + 13);
  if ( v41 && (unsigned __int8)(*((_BYTE *)v26 + 368) - 2) <= 1u )
  {
    v42 = (__int64 *)*((_QWORD *)v26 + 15);
    v43 = &v42[v41];
    if ( v42 == v43 )
      goto LABEL_58;
    while ( 1 )
    {
      v44 = *(_DWORD *)(*v42 + 320);
      if ( v44 == 1 )
      {
        if ( !v38 || !v40 )
        {
          v40 = *v42;
          if ( !v38 )
            goto LABEL_57;
        }
      }
      else if ( v44 == 2 && (v38 || !v40) )
      {
        v40 = *v42;
        if ( v38 )
        {
LABEL_57:
          v126 = v40;
LABEL_58:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowMissingOverlayMedia>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AllowMissingOverlayMedia>::GetImpl'::`2'::impl) )
          {
            if ( *((_DWORD *)v113 + 12) == 2 && v39 && (!v40 || *(_DWORD *)(v40 + 320) != 2) )
              LogAdapter::TraceAtLevelHr<long,>(
                2,
                2148499477LL,
                "Unable to find Overlay package for Feature Update media; assuming media is Overlay compatible");
            break;
          }
          if ( *((_DWORD *)v113 + 12) != 2 || !v39 || v40 && *(_DWORD *)(v40 + 320) == 2 )
            break;
          LODWORD(v14) = -2146467819;
          v138 = -2146467819;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to find Overlay package for Feature Update media");
            *(_QWORD *)v119 = &v138;
            v108 = v119;
            LOBYTE(v54) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v54,
              3,
              ": {}");
          }
          v16 = 1128;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)v14,
            (int)v108);
          return (unsigned int)v14;
        }
      }
      if ( ++v42 == v43 )
        goto LABEL_57;
    }
  }
  v133 = v122 & 4;
  v138 = v122 & 8;
  v122 &= 0x10u;
  v45 = (_QWORD *)*((_QWORD *)v26 + 15);
  *(_QWORD *)v119 = v45;
  *(_QWORD *)v123 = &v45[*((_QWORD *)v26 + 13)];
  if ( v45 == *(_QWORD **)v123 )
    return 0;
  while ( 2 )
  {
    v46 = (_QWORD *)*v45;
    v124 = (_QWORD *)*v45;
    LOBYTE(v120) = 0;
    if ( !*(_DWORD *)v30 )
    {
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = (__int64 *)v46[13];
      v51 = &v50[v46[11]];
      if ( v50 != v51 )
      {
        do
        {
          v52 = *v50;
          v53 = *(_DWORD *)(*v50 + 24);
          if ( v53 )
          {
            if ( ((v53 - 1) & 0xFFFFFFFB) == 0 )
            {
              v48 += *(_QWORD *)(v52 + 32);
              ++v49;
            }
          }
          else
          {
            v47 = *(_QWORD *)(v52 + 32);
          }
          ++v50;
        }
        while ( v50 != v51 );
        v40 = v126;
      }
      LOBYTE(v120) = 0;
      if ( v48 < v47 )
        v120 = v49 < 3;
    }
    v110 = 1;
    if ( (unsigned __int8)(*((_BYTE *)v26 + 368) - 2) > 1u )
    {
      LODWORD(v109) = ApplicableFeaturePackageIntent;
      LODWORD(v14) = CUpdateEvaluator::IsComponentDataBasePackageApplicable(
                       (_DWORD)v30,
                       *(_DWORD *)v30,
                       (_DWORD)v46,
                       v130,
                       v129,
                       v109,
                       (__int64)&v110);
      if ( (int)v14 < 0 )
      {
        v16 = 1165;
        goto LABEL_8;
      }
      v55 = v110;
      goto LABEL_88;
    }
    if ( (unsigned int)(*((_DWORD *)v46 + 80) - 1) <= 1 && v46 != (_QWORD *)v40 )
    {
      v55 = 0;
LABEL_88:
      if ( !v55 )
      {
        LogAdapter::TraceInfo<wchar_t const *>("  Skipping Package: {0} due to applicability filtering", v46 + 1);
        goto LABEL_270;
      }
    }
    v141 = 0;
    v142 = 0;
    v117 = 0;
    LODWORD(v14) = CDeviceInfo::GetNameValuePairValue(
                     *((CDeviceInfo **)v30 + 12),
                     L"EditionVersion",
                     (const wchar_t **)&v117,
                     0);
    if ( (int)v14 < 0 )
    {
      ApplicableFeaturePackageIntent = (int)v14;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get device OS version");
        *(_QWORD *)v123 = &ApplicableFeaturePackageIntent;
        v108 = v123;
        LOBYTE(v107) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v107,
          3,
          ": {}");
      }
      v103 = 1180;
      goto LABEL_291;
    }
    if ( *((_BYTE *)v26 + 368) != 11 )
      goto LABEL_118;
    v58 = *(_QWORD *)(v131 + 40);
    v59 = v58 + 8LL * *(_QWORD *)(v131 + 24);
    if ( v58 == v59 )
      goto LABEL_117;
    v60 = v117;
    do
    {
      v61 = *(struct CCompositionDatabase::Feature ***)(*(_QWORD *)v58 + 48LL);
      v62 = &v61[*(_QWORD *)(*(_QWORD *)v58 + 32LL)];
      if ( v61 != v62 )
      {
        v63 = v118;
        do
        {
          v64 = *v61;
          if ( *v61 == v63 || *((_BYTE *)v64 + 368) != 11 )
            goto LABEL_114;
          if ( *((_QWORD *)v64 + 13) != 1 )
          {
            LODWORD(v14) = -2147418113;
            v133 = -2147418113;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "CumulativeUpdate feature only supports a single package currently");
              *(_QWORD *)v123 = &v133;
              v108 = v123;
              LOBYTE(v102) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v102,
                3,
                ": {}");
            }
            v103 = 1194;
            goto LABEL_291;
          }
          v14 = (const wchar_t *const *)*((_QWORD *)v64 + 15);
          v65 = v113;
          v66 = *((_QWORD *)v113 + 16);
          if ( v66 )
          {
            if ( (int)CompareVersionString(v66, *((_QWORD *)*v14 + 3), v56, v57) <= 0 )
              goto LABEL_109;
            v65 = v113;
          }
          else
          {
            v67 = *((_QWORD *)v113 + 12);
            if ( *(_BYTE *)(v67 + 236) || *(_QWORD *)(v67 + 240) != *(_QWORD *)(v67 + 248) )
              goto LABEL_109;
          }
          if ( !v60
            || (v68 = *((_DWORD *)v65 + 12), v68 <= 0x16) && (v69 = 4505600, _bittest(&v69, v68))
            || (int)CompareVersionString(v60, *((_QWORD *)*v14 + 3), v56, v57) < 0 )
          {
LABEL_109:
            if ( (int)CompareVersionString(v124[2], *((_QWORD *)*v14 + 2), v56, v57) > 0 )
            {
              *((_BYTE *)*v14 + 330) = 1;
              if ( *((_QWORD *)&v141 + 1) == v142 )
              {
                std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
                  &v141,
                  *((_QWORD *)&v141 + 1),
                  v14);
              }
              else
              {
                **((_QWORD **)&v141 + 1) = *v14;
                *((_QWORD *)&v141 + 1) += 8LL;
              }
            }
          }
          v63 = v118;
LABEL_114:
          ++v61;
        }
        while ( v61 != v62 );
      }
      v58 += 8;
    }
    while ( v58 != v59 );
    v46 = v124;
    v26 = v118;
LABEL_117:
    v28 = 0;
    v30 = v113;
LABEL_118:
    if ( *((_DWORD *)v46 + 80) == 5 )
    {
      v14 = (const wchar_t *const *)v46[29];
      v70 = &v14[2 * v46[27]];
      while ( v14 != v70 )
      {
        if ( *(_BYTE *)v14 || *(_DWORD *)v30 || !(unsigned __int8)rtlex::strings_equal_i<wchar_t *,wchar_t [6]>(v14 + 1) )
          *((_DWORD *)v46 + 83) |= 8u;
        v14 += 2;
      }
    }
    if ( *((_DWORD *)v30 + 12) == 1 )
    {
      if ( *((_BYTE *)v26 + 368) != 15 )
        goto LABEL_131;
LABEL_130:
      v71 = DuplicateNullTerminatedString((CUpdateEvaluator *)((char *)v30 + 8), L"WinRE");
      v46[4] = v71;
      if ( !v71 )
      {
        LODWORD(v14) = -2147024882;
        v103 = 1244;
LABEL_291:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v103,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
          (const char *)(unsigned int)v14,
          (int)v108);
        goto LABEL_292;
      }
    }
    else if ( *((_DWORD *)v30 + 12) == 24 )
    {
      goto LABEL_130;
    }
LABEL_131:
    if ( v111 )
    {
      v14 = (const wchar_t *const *)(v46 + 1);
      if ( (unsigned __int8)CDeviceInfo::IsPackageInstalled(*((_QWORD *)v30 + 12), 2, v46[1]) )
      {
        PackageInAnyGroup = CUpdateEvaluator::FindPackageInAnyGroup(v30, *v14);
        if ( PackageInAnyGroup )
          *(_BYTE *)PackageInAnyGroup = 1;
        if ( *((_BYTE *)v26 + 368) == 11 && *((_BYTE *)v30 + 116) )
        {
          LogAdapter::TraceInfo<wchar_t const *>(
            "  LCU Package is already installed but reoffer requested; reinstalling: {0}",
            v46 + 1);
          LOBYTE(v116) = 1;
          goto LABEL_141;
        }
        LogAdapter::TraceInfo<wchar_t const *>("  Skipping already installed Package: {0}", v46 + 1);
LABEL_269:
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v141);
LABEL_270:
        v45 = (_QWORD *)(*(_QWORD *)v119 + 8LL);
        *(_QWORD *)v119 = v45;
        if ( v45 == *(_QWORD **)v123 )
          return 0;
        v40 = v126;
        continue;
      }
    }
    break;
  }
  LOBYTE(v14) = 0;
  v116 = (int)v14;
  if ( *((_BYTE *)v26 + 368) == 11 )
    v116 = (unsigned __int8)CDeviceInfo::IsPackageInstalled(*((_QWORD *)v30 + 12), 2, v46[1]) != 0;
LABEL_141:
  v112 = 0;
  *(_OWORD *)v135 = 0;
  v136 = 0;
  if ( v134 )
  {
LABEL_258:
    LODWORD(v14) = CActionListCreator::InstallPackage(v125, (__int64)v135);
    if ( (int)v14 < 0 )
    {
      v133 = (int)v14;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed adding InstallPackage: Package: {0}",
          v46 + 1);
        *(_QWORD *)v123 = &v133;
        v108 = v123;
        LOBYTE(v106) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v106,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x650,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v14,
        (int)v108);
      goto LABEL_284;
    }
    v100 = *((_DWORD *)v46 + 80);
    if ( v100 != 10
      && *((_DWORD *)v46 + 80) != 11
      && *((_DWORD *)v46 + 80) != 12
      && *((_DWORD *)v46 + 80) != 13
      && (unsigned int)(*((_DWORD *)v46 + 80) - 14) >= 2
      && v100 != 6
      && (unsigned int)(v100 - 17) > 1 )
    {
      VersionlessPackageInAnyGroup = CUpdateEvaluator::FindVersionlessPackageInAnyGroup(
                                       v30,
                                       (const wchar_t *const)v46[1],
                                       v100);
      if ( VersionlessPackageInAnyGroup )
        *((_BYTE *)VersionlessPackageInAnyGroup + 1) = 1;
    }
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(v135);
    goto LABEL_269;
  }
  v143 = 0;
  v144 = 0;
  v73 = 0;
  v117 = 0;
  v121 = 0;
  v127 = 0;
  v139 = 0;
  v140 = 0;
  v74 = v141;
  v75 = (__int64)(*((_QWORD *)&v141 + 1) - v141) >> 3;
  v76 = v46[11] + v75 == 0;
  v77 = v46[11] + v75;
  v128 = (wchar_t *)v77;
  if ( !v76 )
  {
    if ( v77 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<CCompositionDatabase::Feature *>::_Xlength();
    std::vector<FeatureDescriptor *>::_Reallocate<0>(&v139, &v128);
    v74 = v141;
  }
  v110 = 0;
  v128 = 0;
  std::_Sort_unchecked<CCompositionDatabase::Package * *,bool (*)(CCompositionDatabase::Package const *,CCompositionDatabase::Package const *)>(
    v74,
    *((_QWORD *)&v141 + 1),
    (*((_QWORD *)&v141 + 1) - v74) >> 3,
    CmpAscending);
  v79 = *((_QWORD *)&v141 + 1);
  for ( i = v141; i != v79; i += 8 )
  {
    v80 = *(_QWORD *)(*(_QWORD *)i + 104LL);
    v81 = v80 + 8LL * *(_QWORD *)(*(_QWORD *)i + 88LL);
    while ( v80 != v81 )
    {
      if ( *(_BYTE *)(*(_QWORD *)i + 330LL) )
        *(_BYTE *)(*(_QWORD *)v80 + 176LL) = 1;
      if ( *((_QWORD *)&v139 + 1) == v140 )
      {
        std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
          &v139,
          *((_QWORD *)&v139 + 1),
          v80);
      }
      else
      {
        **((_QWORD **)&v139 + 1) = *(_QWORD *)v80;
        *((_QWORD *)&v139 + 1) += 8LL;
      }
      v80 += 8;
    }
  }
  v46 = v124;
  v82 = (_QWORD *)v124[13];
  v83 = &v82[v124[11]];
  while ( v82 != v83 )
  {
    if ( *((_QWORD *)&v139 + 1) == v140 )
    {
      std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
        &v139,
        *((_QWORD *)&v139 + 1),
        v82);
    }
    else
    {
      **((_QWORD **)&v139 + 1) = *v82;
      *((_QWORD *)&v139 + 1) += 8LL;
    }
    ++v82;
  }
  v84 = v139;
  if ( (_QWORD)v139 == *((_QWORD *)&v139 + 1) )
  {
LABEL_202:
    v30 = v113;
    if ( v28 )
    {
      if ( *((_BYTE *)v113 + 118) )
        *(_DWORD *)(v28 + 24) = 0;
      if ( (_QWORD *)v135[1] == v136 )
      {
        std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
          v135,
          v135[1],
          &v127);
      }
      else
      {
        *(_QWORD *)v135[1] = v28;
        v135[1] += 8;
      }
      LogAdapter::TraceInfo<wchar_t const *>("  Installing using PSFX: {0}", v46 + 1);
      v28 = 0;
    }
    else if ( !v138 )
    {
      v91 = (__int64 *)*((_QWORD *)&v143 + 1);
      v92 = (__int64 *)v143;
      if ( (_QWORD)v143 != *((_QWORD *)&v143 + 1) && (v110 || *((_BYTE *)v113 + 120)) )
      {
        do
        {
          v93 = *v92;
          v127 = *v92;
          if ( (_QWORD *)v135[1] == v136 )
          {
            std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
              v135,
              v135[1],
              &v127);
          }
          else
          {
            *(_QWORD *)v135[1] = v93;
            v135[1] += 8;
          }
          ++v92;
        }
        while ( v92 != v91 );
        LogAdapter::TraceInfo<wchar_t const *>("  Installing using express Package: {0}", v46 + 1);
      }
    }
    if ( v135[0] != v135[1] )
      goto LABEL_257;
    if ( *(_QWORD *)(*((_QWORD *)v30 + 12) + 8LL)
      || !v73
      || ComparePossiblyNullStringsCaseInvariant((const wchar_t *)v46[4], L"Data")
      && ComparePossiblyNullStringsCaseInvariant((const wchar_t *)v46[4], L"UpdateOS") )
    {
      v94 = v121;
    }
    else
    {
      v73 = 0;
      v117 = 0;
      v94 = 0;
      v121 = 0;
    }
    if ( !ComparePossiblyNullStringsCaseInvariant((const wchar_t *)v46[4], L"VAIL") )
    {
      v73 = 0;
      v117 = 0;
      v94 = 0;
      v121 = 0;
    }
    if ( !*(_DWORD *)v30 )
    {
      v95 = *((_BYTE *)v118 + 368);
      if ( ((v95 - 5) & 0xF6) == 0 && v95 != 14 )
      {
        InstalledCBSPackage = CDeviceInfo::GetInstalledCBSPackage(*((_QWORD *)v30 + 12), 2, v46[1]);
        if ( !InstalledCBSPackage || (*(_BYTE *)(InstalledCBSPackage + 60) & 8) == 0 )
        {
          v73 = 0;
          v117 = 0;
          v94 = 0;
          v121 = 0;
        }
      }
    }
    if ( v120 )
    {
      if ( !v73 )
        goto LABEL_252;
      if ( v94 )
      {
        if ( (_QWORD *)v135[1] == v136 )
        {
          std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
            v135,
            v135[1],
            &v117);
          v97 = (_QWORD *)v135[1];
        }
        else
        {
          *(_QWORD *)v135[1] = v73;
          v97 = (_QWORD *)(v135[1] + 8);
          v135[1] += 8;
        }
        if ( v97 == v136 )
        {
          std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
            v135,
            v97,
            &v121);
        }
        else
        {
          *v97 = v94;
          v135[1] += 8;
        }
        v117 = v73;
        LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
          "  Installing using universal diff with source Package: {0}, baseline Package: {1} for Package: {2}",
          v73 + 4,
          v94 + 8,
          v46 + 1);
LABEL_257:
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v139);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v143);
        v26 = v118;
        goto LABEL_258;
      }
    }
    if ( v73 && !v94 )
    {
      v117 = v73;
      if ( (_QWORD *)v135[1] == v136 )
      {
        std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
          v135,
          v135[1],
          &v117);
      }
      else
      {
        *(_QWORD *)v135[1] = v73;
        v135[1] += 8;
      }
      LogAdapter::TraceInfo<wchar_t *,wchar_t *>(
        "  Installing using diff with source Package: {0} for Package: {1}",
        v73 + 4,
        v46 + 1);
      goto LABEL_257;
    }
LABEL_252:
    if ( !v128 )
    {
      LODWORD(v14) = -2147418113;
      v133 = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Package {0} has no valid source",
          v46 + 1);
        *(_QWORD *)v123 = &v133;
        v108 = v123;
        LOBYTE(v98) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v98,
          3,
          ": {}");
      }
      v99 = 1542;
      goto LABEL_283;
    }
    v117 = v128;
    if ( (_QWORD *)v135[1] == v136 )
    {
      std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
        v135,
        v135[1],
        &v117);
    }
    else
    {
      *(_QWORD *)v135[1] = v128;
      v135[1] += 8;
    }
    LogAdapter::TraceInfo<wchar_t const *>("  Installing using canonical Package: {0}", v46 + 1);
    goto LABEL_257;
  }
  v85 = v113;
  while ( 1 )
  {
    v86 = *(_DWORD *)(*(_QWORD *)v84 + 24LL);
    if ( !v86 )
    {
      v128 = *(wchar_t **)v84;
      goto LABEL_198;
    }
    if ( v86 == 4 )
    {
      v28 = *(_QWORD *)v84;
      v127 = *(_QWORD *)v84;
      goto LABEL_198;
    }
    if ( v86 == 1 )
      break;
    if ( v86 == 5 )
    {
      v121 = *(_QWORD *)v84;
    }
    else
    {
      if ( v86 != 2 )
      {
        LODWORD(v14) = -2147418113;
        ApplicableFeaturePackageIntent = -2147418113;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          v133 = v86;
          LogAdapter::Logger::LogNumObjects<long>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Unexpected payload type found: {0}",
            &v133);
          *(_QWORD *)v123 = &ApplicableFeaturePackageIntent;
          v108 = v123;
          LOBYTE(v105) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v105,
            3,
            ": {}");
        }
        v99 = 1432;
        goto LABEL_283;
      }
      if ( !v138 )
      {
        if ( *((_DWORD *)v113 + 12) == 2 || *((_DWORD *)v113 + 12) == 22 )
        {
          v88 = (_BYTE *)v46[21];
          v89 = &v88[16 * v46[19]];
          while ( v88 != v89 )
          {
            if ( *((_DWORD *)v46 + 80) != 8 && !*v88 )
            {
              v85 = v113;
              goto LABEL_198;
            }
            v88 += 16;
          }
        }
        if ( *((_BYTE *)v113 + 117) && *((_DWORD *)v113 + 12) == 1 && *((_BYTE *)v118 + 368) == 12 )
        {
          LogAdapter::TraceInfo<>("WinRE Servicing is required. Requesting canonical SSU in this case.");
        }
        else
        {
          v90 = *(_QWORD *)v84;
          if ( *(_QWORD *)(*(_QWORD *)v84 + 40LL) || *(_DWORD *)(v90 + 28) == 1 )
            v110 = 1;
          if ( *((_QWORD *)&v143 + 1) == v144 )
          {
            std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
              &v143,
              *((_QWORD *)&v143 + 1),
              v84);
          }
          else
          {
            **((_QWORD **)&v143 + 1) = v90;
            *((_QWORD *)&v143 + 1) += 8LL;
          }
        }
        goto LABEL_190;
      }
    }
LABEL_198:
    *(_QWORD *)&v84 = v84 + 8;
    if ( (_QWORD)v84 == *((_QWORD *)&v84 + 1) )
      goto LABEL_202;
  }
  if ( !*(_QWORD *)(*(_QWORD *)v84 + 8LL)
    || (!v120 || !(unsigned __int8)CDeviceInfo::IsCBSPackageInstalled(*((_QWORD *)v85 + 12), 1))
    && !(unsigned __int8)CDeviceInfo::IsCBSPackageInstalled(*((_QWORD *)v85 + 12), 0) )
  {
    goto LABEL_198;
  }
  v124 = (_QWORD *)v46[1];
  if ( std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(
         *((_QWORD *)v113 + 12) + 192LL,
         &v124) )
  {
    v112 = 1;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v87) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v87,
        2,
        "Diff cab available for the source {0}, but failed previously to expand for package:{1}",
        *(_QWORD *)v84 + 8LL,
        v46 + 1);
    }
LABEL_190:
    v85 = v113;
    goto LABEL_198;
  }
  v73 = *(wchar_t **)v84;
  v117 = v73;
  if ( !v73 || (_QWORD)v143 == *((_QWORD *)&v143 + 1) )
    goto LABEL_202;
  LODWORD(v14) = -2147418113;
  v133 = -2147418113;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Diff and express packages cannot be mixed");
    *(_QWORD *)v123 = &v133;
    v108 = v123;
    LOBYTE(v104) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v104,
      3,
      ": {}");
  }
  v99 = 1437;
LABEL_283:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v99,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
    (const char *)0x8000FFFFLL,
    (int)v108);
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v139);
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v143);
LABEL_284:
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(v135);
LABEL_292:
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v141);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800d7934  mov     rax, rsp
0x1800d7937  push    rbp
0x1800d7938  push    rsi
0x1800d7939  push    rdi
0x1800d793a  push    r12
0x1800d793c  push    r13
0x1800d793e  push    r14
0x1800d7940  push    r15
0x1800d7942  lea     rbp, [rsp-60h]
0x1800d7947  sub     rsp, 160h
0x1800d794e  mov     [rbp+90h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800d7956  mov     [rax+10h], rbx
0x1800d795a  mov     rax, cs:__security_cookie
0x1800d7961  xor     rax, rsp
0x1800d7964  mov     [rbp+90h+var_40], rax
0x1800d7968  mov     r12d, r9d
0x1800d796b  mov     r13d, r8d
0x1800d796e  mov     [rsp+190h+var_148], rcx
0x1800d7973  mov     rax, [rbp+90h+arg_20]
0x1800d797a  mov     [rbp+90h+var_C8], rax
0x1800d797e  mov     rax, [rbp+90h+arg_28]
0x1800d7985  mov     [rbp+90h+var_D0], rax
0x1800d7989  mov     r15, [rbp+90h+arg_30]
0x1800d7990  mov     rbx, [rbp+90h+arg_38]
0x1800d7997  mov     [rsp+190h+var_130], rbx
0x1800d799c  mov     rax, [rbp+90h+arg_40]
0x1800d79a3  mov     [rbp+90h+var_C0], rax
0x1800d79a7  mov     rax, [rbp+90h+arg_48]
0x1800d79ae  mov     [rbp+90h+var_F0], rax
0x1800d79b2  mov     eax, edx
0x1800d79b4  and     eax, 20h
0x1800d79b7  mov     [rbp+90h+var_AC], eax
0x1800d79ba  mov     ecx, edx
0x1800d79bc  or      ecx, 0Ch
0x1800d79bf  test    eax, eax
0x1800d79c1  cmovz   ecx, edx
0x1800d79c4  mov     [rbp+90h+var_110], ecx
0x1800d79c7  mov     al, cl
0x1800d79c9  mov     edi, 1
0x1800d79ce  and     al, dil
0x1800d79d1  jz      short loc_1800D7A4F
0x1800d79d3  test    cl, 2
0x1800d79d6  jz      short loc_1800D7A4F
0x1800d79d8  mov     ebx, 80070057h
0x1800d79dd  mov     [rbp+90h+var_AC], ebx
0x1800d79e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d79e7  test    rcx, rcx
0x1800d79ea  jz      short loc_1800D7A2D
0x1800d79ec  lea     r9, aInvalidFlagsPa; "Invalid flags passed to ServiceFeatureA"...
0x1800d79f3  lea     r13d, [rdi+2]
0x1800d79f7  mov     r8d, r13d
0x1800d79fa  xor     edx, edx
0x1800d79fc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d7a01  lea     rax, [rbp+90h+var_AC]
0x1800d7a05  mov     qword ptr [rsp+190h+var_128], rax
0x1800d7a0a  lea     rax, [rsp+190h+var_128]
0x1800d7a0f  mov     [rsp+190h+var_170], rax; int
0x1800d7a14  lea     r9, asc_1801CAFB4; ": {}"
0x1800d7a1b  mov     r8d, r13d
0x1800d7a1e  mov     dl, dil
0x1800d7a21  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d7a28  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d7a2d  mov     edx, 3C3h; void *
0x1800d7a32  mov     rcx, [rbp+98h]; this
0x1800d7a39  mov     r9d, ebx; char *
0x1800d7a3c  lea     r8, aOnecoreBaseSer_14; "onecore\\base\\servicing\\arbiter\\cupd"...
0x1800d7a43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7a48  mov     eax, ebx
0x1800d7a4a  jmp     loc_1800D7C01
0x1800d7a4f  lea     rdi, [rbx+38h]
0x1800d7a53  lea     r14, [rbx+40h]
0x1800d7a57  lea     rsi, [rbx+48h]
0x1800d7a5b  lea     rdx, aInstallingFeat; "Installing feature: Group: {0}, FMID: {"...
0x1800d7a62  lea     rcx, aUpdatingInstal; "Updating installed feature: Group: {0},"...
0x1800d7a69  test    al, al
0x1800d7a6b  cmovz   rcx, rdx
0x1800d7a6f  mov     r9, rdi
0x1800d7a72  mov     r8, r14
0x1800d7a75  mov     rdx, rsi
0x1800d7a78  call    ??$TraceInfo@PEA_WPEA_WPEA_W@LogAdapter@@YAXQEBDAEBQEA_W11@Z; LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(char const * const,wchar_t * const &,wchar_t * const &,wchar_t * const &)
0x1800d7a7d  mov     [rsp+190h+var_13C], 0
0x1800d7a85  lea     r8, [rsp+190h+var_13C]; enum CActionListCreator::InstallFeatureDisposition *
0x1800d7a8a  mov     rdx, rbx; struct CCompositionDatabase::Feature *
0x1800d7a8d  mov     rcx, [rbp+90h+var_F0]; this
0x1800d7a91  call    ?InstallFeature@CActionListCreator@@QEAAJQEBUFeature@CCompositionDatabase@@PEAW4InstallFeatureDisposition@1@@Z; CActionListCreator::InstallFeature(CCompositionDatabase::Feature const * const,CActionListCreator::InstallFeatureDisposition *)
0x1800d7a96  mov     ebx, eax
0x1800d7a98  test    eax, eax
0x1800d7a9a  jns     short loc_1800D7B06
0x1800d7a9c  mov     [rbp+90h+var_AC], eax
0x1800d7a9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d7aa6  test    rcx, rcx
0x1800d7aa9  jz      short loc_1800D7AFC
0x1800d7aab  mov     [rsp+190h+var_160], rdi
0x1800d7ab0  mov     [rsp+190h+var_168], r14
0x1800d7ab5  mov     [rsp+190h+var_170], rsi
0x1800d7aba  lea     r9, aFailedAddingIn_5; "Failed adding InstallFeature: Group: {0"...
0x1800d7ac1  mov     r13d, 3
0x1800d7ac7  mov     r8d, r13d
0x1800d7aca  xor     edx, edx
0x1800d7acc  call    ??$LogNumObjects@PEA_WPEA_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W33@Z; LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &,wchar_t * const &)
0x1800d7ad1  lea     rax, [rbp+90h+var_AC]
0x1800d7ad5  mov     qword ptr [rsp+190h+var_128], rax
0x1800d7ada  lea     rax, [rsp+190h+var_128]
0x1800d7adf  mov     [rsp+190h+var_170], rax
0x1800d7ae4  lea     r9, asc_1801CAFB4; ": {}"
0x1800d7aeb  mov     r8d, r13d
0x1800d7aee  mov     dl, 1
0x1800d7af0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d7af7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d7afc  mov     edx, 3D3h
0x1800d7b01  jmp     loc_1800D7A32
0x1800d7b06  mov     rbx, [rsp+190h+var_148]
0x1800d7b0b  lea     rcx, [rbx+40h]
0x1800d7b0f  mov     r8, rdi
0x1800d7b12  lea     rdx, [rbp+90h+var_108]
0x1800d7b16  call    ??$emplace@AEBQEA_W@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBQEA_W@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::emplace<wchar_t * const &>(wchar_t * const &)
0x1800d7b1b  mov     eax, r12d
0x1800d7b1e  not     eax
0x1800d7b20  test    r15, r15
0x1800d7b23  jz      short loc_1800D7B2B
0x1800d7b25  mov     edx, [r15+34h]
0x1800d7b29  jmp     short loc_1800D7B2D
0x1800d7b2b  xor     edx, edx
0x1800d7b2d  or      edx, r13d
0x1800d7b30  and     edx, eax
0x1800d7b32  mov     rcx, [rsp+190h+var_130]
0x1800d7b37  call    GetApplicableFeaturePackageIntent
0x1800d7b3c  mov     [rbp+90h+var_90], eax
0x1800d7b3f  cmp     dword ptr [rbx], 0
0x1800d7b42  jnz     loc_1800D7BDB
0x1800d7b48  mov     rax, [rbp+90h+var_F0]
0x1800d7b4c  mov     [rsp+190h+var_158], rax
0x1800d7b51  mov     [rsp+190h+var_160], r15
0x1800d7b56  mov     rcx, [rsi]
0x1800d7b59  mov     [rsp+190h+var_168], rcx
0x1800d7b5e  mov     r15, [rsp+190h+var_130]
0x1800d7b63  mov     [rsp+190h+var_170], r15
0x1800d7b68  mov     r9d, r12d
0x1800d7b6b  mov     r8d, r13d
0x1800d7b6e  mov     dl, 1
0x1800d7b70  mov     rcx, rbx
0x1800d7b73  call    ?DetermineFeatureTokenChanges@CUpdateEvaluator@@AEAAJ_NW4FeatureIntentFlags@@1PEBUFeature@CCompositionDatabase@@QEB_WPEBU31@PEAVCActionListCreator@@@Z; CUpdateEvaluator::DetermineFeatureTokenChanges(bool,FeatureIntentFlags,FeatureIntentFlags,CCompositionDatabase::Feature const *,wchar_t const * const,CUpdateEvaluator::Feature const *,CActionListCreator *)
0x1800d7b78  mov     ebx, eax
0x1800d7b7a  xor     r12d, r12d
0x1800d7b7d  test    eax, eax
0x1800d7b7f  jns     short loc_1800D7BE3
0x1800d7b81  mov     [rbp+90h+var_AC], eax
0x1800d7b84  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d7b8b  test    rcx, rcx
0x1800d7b8e  jz      short loc_1800D7BD1
0x1800d7b90  lea     r9, aFailedAddingTo; "Failed adding token updates for feature"
0x1800d7b97  lea     r13d, [r12+3]
0x1800d7b9c  mov     r8d, r13d
0x1800d7b9f  xor     edx, edx
0x1800d7ba1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d7ba6  lea     rax, [rbp+90h+var_AC]
0x1800d7baa  mov     qword ptr [rsp+190h+var_128], rax
0x1800d7baf  lea     rax, [rsp+190h+var_128]
0x1800d7bb4  mov     [rsp+190h+var_170], rax
0x1800d7bb9  lea     r9, asc_1801CAFB4; ": {}"
0x1800d7bc0  mov     r8d, r13d
0x1800d7bc3  mov     dl, 1
0x1800d7bc5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d7bcc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d7bd1  mov     edx, 3E3h
0x1800d7bd6  jmp     loc_1800D7A32
0x1800d7bdb  mov     r15, [rsp+190h+var_130]
0x1800d7be0  xor     r12d, r12d
0x1800d7be3  cmp     [rsp+190h+var_13C], 2
0x1800d7be8  jnz     short loc_1800D7C29
0x1800d7bea  mov     r9, rdi
0x1800d7bed  mov     r8, r14
0x1800d7bf0  mov     rdx, rsi
0x1800d7bf3  lea     rcx, aFeatureIsAlrea; "Feature is already scheduled for instal"...
0x1800d7bfa  call    ??$TraceInfo@PEA_WPEA_WPEA_W@LogAdapter@@YAXQEBDAEBQEA_W11@Z; LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(char const * const,wchar_t * const &,wchar_t * const &,wchar_t * const &)
0x1800d7bff  xor     eax, eax
0x1800d7c01  mov     rcx, [rbp+90h+var_40]
0x1800d7c05  xor     rcx, rsp; StackCookie
0x1800d7c08  call    __security_check_cookie
0x1800d7c0d  mov     rbx, [rsp+190h+arg_8]
0x1800d7c15  add     rsp, 160h
0x1800d7c1c  pop     r15
0x1800d7c1e  pop     r14
0x1800d7c20  pop     r13
0x1800d7c22  pop     r12
0x1800d7c24  pop     rdi
0x1800d7c25  pop     rsi
0x1800d7c26  pop     rbp
0x1800d7c27  retn
0x1800d7c29  mov     rsi, [rsp+190h+var_148]
0x1800d7c2e  mov     ecx, [rsi+30h]
0x1800d7c31  mov     r13d, 3
0x1800d7c37  cmp     ecx, 2
0x1800d7c3a  jnz     short loc_1800D7C48
0x1800d7c3c  cmp     [rsi+77h], r12b
0x1800d7c40  jz      short loc_1800D7C48
0x1800d7c42  lea     r14d, [rcx-1]
0x1800d7c46  jmp     short loc_1800D7C9F
0x1800d7c48  mov     r14d, 1
0x1800d7c4e  cmp     [rsi], r14d
0x1800d7c51  setnz   al
0x1800d7c54  mov     [rsp+190h+var_14F], al
0x1800d7c58  jnz     short loc_1800D7C78
0x1800d7c5a  movzx   edx, byte ptr [r15+170h]
0x1800d7c62  sub     edx, 11h
0x1800d7c65  jz      short loc_1800D7C9F
0x1800d7c67  sub     edx, 4
0x1800d7c6a  jz      short loc_1800D7C9F
0x1800d7c6c  sub     edx, r14d
0x1800d7c6f  jz      short loc_1800D7C9F
0x1800d7c71  cmp     edx, r14d
0x1800d7c74  jnz     short loc_1800D7C7C
0x1800d7c76  jmp     short loc_1800D7C9F
0x1800d7c78  test    al, al
0x1800d7c7a  jnz     short loc_1800D7CA4
0x1800d7c7c  sub     ecx, r14d
0x1800d7c7f  jz      short loc_1800D7CA4
0x1800d7c81  sub     ecx, r14d
0x1800d7c84  jz      short loc_1800D7CA4
0x1800d7c86  sub     ecx, 0Ch
0x1800d7c89  jz      short loc_1800D7CA4
0x1800d7c8b  sub     ecx, r14d
0x1800d7c8e  jz      short loc_1800D7CA4
0x1800d7c90  sub     ecx, 4
0x1800d7c93  jz      short loc_1800D7CA4
0x1800d7c95  sub     ecx, r13d
0x1800d7c98  jz      short loc_1800D7CA4
0x1800d7c9a  cmp     ecx, 2
0x1800d7c9d  jz      short loc_1800D7CA4
0x1800d7c9f  mov     [rsp+190h+var_14F], r14b
0x1800d7ca4  mov     rax, [rbp+90h+var_F0]
0x1800d7ca8  mov     r9b, [rax+4Dh]
0x1800d7cac  mov     [rsp+190h+var_140], r9b
0x1800d7cb1  mov     bl, [rax+4Ch]
0x1800d7cb4  mov     [rsp+190h+var_13F], bl
0x1800d7cb8  mov     rdi, r12
0x1800d7cbb  mov     [rbp+90h+var_E8], r12
0x1800d7cbf  mov     rcx, [r15+68h]
0x1800d7cc3  test    rcx, rcx
0x1800d7cc6  jz      loc_1800D7D73
0x1800d7ccc  mov     al, [r15+170h]
0x1800d7cd3  sub     al, 2
0x1800d7cd5  cmp     al, r14b
0x1800d7cd8  ja      loc_1800D7D73
0x1800d7cde  mov     rax, [r15+78h]
0x1800d7ce2  lea     r8, [rax+rcx*8]
0x1800d7ce6  cmp     rax, r8
0x1800d7ce9  jz      short loc_1800D7D31
0x1800d7ceb  mov     rcx, [rax]
0x1800d7cee  mov     edx, [rcx+140h]
0x1800d7cf4  cmp     edx, r14d
0x1800d7cf7  jnz     short loc_1800D7D0D
0x1800d7cf9  test    r9b, r9b
0x1800d7cfc  jz      short loc_1800D7D03
0x1800d7cfe  test    rdi, rdi
0x1800d7d01  jnz     short loc_1800D7D24
0x1800d7d03  mov     rdi, rcx
0x1800d7d06  test    r9b, r9b
0x1800d7d09  jz      short loc_1800D7D2D
0x1800d7d0b  jmp     short loc_1800D7D24
0x1800d7d0d  cmp     edx, 2
0x1800d7d10  jnz     short loc_1800D7D24
0x1800d7d12  test    r9b, r9b
0x1800d7d15  jnz     short loc_1800D7D1C
0x1800d7d17  test    rdi, rdi
0x1800d7d1a  jnz     short loc_1800D7D24
0x1800d7d1c  mov     rdi, rcx
0x1800d7d1f  test    r9b, r9b
0x1800d7d22  jnz     short loc_1800D7D2D
0x1800d7d24  add     rax, 8
0x1800d7d28  cmp     rax, r8
0x1800d7d2b  jnz     short loc_1800D7CEB
0x1800d7d2d  mov     [rbp+90h+var_E8], rdi
0x1800d7d31  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowMissingOverlayMedia@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowMissingOverlayMedia@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowMissingOverlayMedia> `wil::Feature<__WilFeatureTraits_Feature_AllowMissingOverlayMedia>::GetImpl(void)'::`2'::impl
0x1800d7d38  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowMissingOverlayMedia@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowMissingOverlayMedia>::__private_IsEnabled(void)
0x1800d7d3d  test    al, al
0x1800d7d3f  jz      loc_1800D7DF4
0x1800d7d45  cmp     dword ptr [rsi+30h], 2
0x1800d7d49  jnz     short loc_1800D7D73
0x1800d7d4b  test    bl, bl
0x1800d7d4d  jz      short loc_1800D7D73
0x1800d7d4f  test    rdi, rdi
0x1800d7d52  jz      short loc_1800D7D5D
0x1800d7d54  cmp     dword ptr [rdi+140h], 2
0x1800d7d5b  jz      short loc_1800D7D73
0x1800d7d5d  lea     r8, aUnableToFindOv; "Unable to find Overlay package for Feat"...
0x1800d7d64  mov     edx, 800F8015h
0x1800d7d69  mov     ecx, 2
0x1800d7d6e  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800d7d73  mov     eax, [rbp+90h+var_110]
0x1800d7d76  mov     ecx, eax
0x1800d7d78  and     ecx, 4
0x1800d7d7b  mov     [rbp+90h+var_B0], ecx
0x1800d7d7e  mov     ecx, eax
0x1800d7d80  and     ecx, 8
0x1800d7d83  mov     [rbp+90h+var_8C], ecx
0x1800d7d86  and     eax, 10h
0x1800d7d89  mov     [rbp+90h+var_110], eax
0x1800d7d8c  mov     rcx, [r15+78h]
0x1800d7d90  mov     qword ptr [rsp+190h+var_128], rcx
  ... truncated ...
```
