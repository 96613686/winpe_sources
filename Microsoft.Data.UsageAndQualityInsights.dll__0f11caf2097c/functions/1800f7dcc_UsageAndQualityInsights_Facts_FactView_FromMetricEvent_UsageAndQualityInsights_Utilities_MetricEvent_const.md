# UsageAndQualityInsights::Facts::FactView::FromMetricEvent(UsageAndQualityInsights::Utilities::MetricEvent const &)

- ea: `0x1800f7dcc`
- end: `0x1800f8ec8`
- name: `?FromMetricEvent@FactView@Facts@UsageAndQualityInsights@@SA?AU123@AEBUMetricEvent@Utilities@3@@Z`
- size: `4348`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180015930`

## callees

- `0x1800033d0`
- `0x180003870`
- `0x1800038b8`
- `0x180003f40`
- `0x180003f58`
- `0x180003f70`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180011d6c`
- `0x180012f84`
- `0x18001386c`
- `0x1800145bc`
- `0x180014810`
- `0x180016648`
- `0x180016d2c`
- `0x180019458`
- `0x180019b64`
- `0x180020650`
- `0x1800228b0`
- `0x180022de4`
- `0x180023334`
- `0x1800233bc`
- `0x1800236c0`
- `0x180027ba4`
- `0x180027d8c`
- `0x180041ec8`
- `0x180041f88`
- `0x1800e905c`
- `0x1800ed390`
- `0x1800f715c`
- `0x1800f7748`
- `0x1800f7924`
- `0x1800f7dcc`
- `0x1800fa250`
- `0x1800fd7b0`
- `0x1800fdd88`
- `0x180100300`
- `0x180100eb4`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800f8e5f`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800f8e5f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800f8e51`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800f8e51`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x1800f83f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoll` at `0x1800f83f0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f83c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f83c8`

## string_xrefs

- `0x1800f87cf`: `overwrite::PartA_Ext_App_UserId`
- `0x1800f876b`: `system::userSid`
- `0x1800f8a39`: `onecore\base\usageandqualityinsights\service\lib\factstore\factview.cpp`
- `0x1800f8a71`: `onecore\base\usageandqualityinsights\service\lib\factstore\factview.cpp`
- `0x1800f8aa9`: `onecore\base\usageandqualityinsights\service\lib\factstore\factview.cpp`
- `0x1800f8ae1`: `onecore\base\usageandqualityinsights\service\lib\factstore\factview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
UsageAndQualityInsights::Facts::FactView *__fastcall UsageAndQualityInsights::Facts::FactView::FromMetricEvent(
        UsageAndQualityInsights::Facts::FactView *a1,
        __int64 a2)
{
  _QWORD *v4; // rdx
  unsigned __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // r8
  int v8; // r13d
  const wchar_t *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 **v13; // r12
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 SourceEventFromMetricEvent; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 *v26; // rbx
  __int64 v27; // rax
  __int64 **v28; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v31; // r13
  __int64 v32; // rbx
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  _DWORD *v37; // rax
  _DWORD *v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rdi
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdi
  __int64 v53; // rax
  __int64 *v54; // rdi
  __int64 *v55; // r13
  const wchar_t *v56; // rcx
  __int64 *v57; // rdi
  __int64 *v58; // rsi
  const wchar_t *v59; // rcx
  __int64 v60; // rax
  _QWORD *v61; // rax
  unsigned __int64 v62; // rcx
  __int64 v63; // rdx
  double v64; // xmm7_8
  __int64 v65; // rcx
  double v66; // xmm9_8
  double v67; // xmm8_8
  double v68; // xmm0_8
  _QWORD *v69; // rax
  double v70; // xmm8_8
  double v71; // xmm6_8
  double v72; // xmm10_8
  double v73; // xmm0_8
  __int64 *HourTimeBin; // rax
  int v75; // edx
  int v76; // r8d
  int v77; // r9d
  __int64 v78; // rcx
  double v79; // xmm0_8
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rbx
  __int64 v83; // rax
  void *v84; // rcx
  _QWORD *v85; // rbx
  void *v86; // rcx
  int v88; // [rsp+28h] [rbp-E0h]
  int v89; // [rsp+28h] [rbp-E0h]
  int v90; // [rsp+28h] [rbp-E0h]
  int v91; // [rsp+28h] [rbp-E0h]
  char *v92; // [rsp+38h] [rbp-D0h]
  char *v93; // [rsp+38h] [rbp-D0h]
  char *v94; // [rsp+38h] [rbp-D0h]
  char *v95; // [rsp+38h] [rbp-D0h]
  int v96; // [rsp+48h] [rbp-C0h]
  _QWORD v97[2]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v98; // [rsp+60h] [rbp-A8h]
  int v99; // [rsp+64h] [rbp-A4h] BYREF
  wchar_t *v100; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v101; // [rsp+70h] [rbp-98h]
  wchar_t *EndPtr; // [rsp+78h] [rbp-90h] BYREF
  __int64 v103; // [rsp+80h] [rbp-88h]
  __int64 v104; // [rsp+88h] [rbp-80h]
  double v105; // [rsp+90h] [rbp-78h] BYREF
  __int64 v106; // [rsp+98h] [rbp-70h] BYREF
  __int64 v107; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v108; // [rsp+A8h] [rbp-60h] BYREF
  __int64 **v109; // [rsp+B0h] [rbp-58h]
  UsageAndQualityInsights::Facts::FactView *v110; // [rsp+B8h] [rbp-50h]
  _BYTE v111[8]; // [rsp+C0h] [rbp-48h] BYREF
  int *v112; // [rsp+C8h] [rbp-40h]
  _BYTE v113[8]; // [rsp+D0h] [rbp-38h] BYREF
  char v114; // [rsp+D8h] [rbp-30h] BYREF
  double v115; // [rsp+E0h] [rbp-28h]
  __int64 v116; // [rsp+E8h] [rbp-20h]
  __int64 v117; // [rsp+F0h] [rbp-18h]
  __int64 v118; // [rsp+F8h] [rbp-10h]
  _BYTE v119[80]; // [rsp+100h] [rbp-8h] BYREF
  void *v120[2]; // [rsp+150h] [rbp+48h] BYREF
  char v121; // [rsp+160h] [rbp+58h]
  _BYTE v122[16]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v123[96]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v124[192]; // [rsp+1D8h] [rbp+D0h] BYREF
  wchar_t *S1[2]; // [rsp+298h] [rbp+190h] BYREF
  unsigned __int64 v126; // [rsp+2A8h] [rbp+1A0h]
  unsigned __int64 v127; // [rsp+2B0h] [rbp+1A8h]
  wchar_t v128[8]; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v129; // [rsp+2C8h] [rbp+1C0h]
  __int64 v130; // [rsp+2D0h] [rbp+1C8h]
  int v131; // [rsp+2D8h] [rbp+1D0h] BYREF
  char v132; // [rsp+2DCh] [rbp+1D4h]
  int v133; // [rsp+2E0h] [rbp+1D8h]
  double X; // [rsp+2E8h] [rbp+1E0h]
  double v135; // [rsp+2F0h] [rbp+1E8h]
  _QWORD v136[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  __int128 v137; // [rsp+308h] [rbp+200h] BYREF
  __int64 v138; // [rsp+318h] [rbp+210h]
  __int64 v139; // [rsp+320h] [rbp+218h]
  wil::details::in1diag3 *retaddr; // [rsp+3E0h] [rbp+2D8h]

  v110 = a1;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  v4 = (_QWORD *)(a2 + 32);
  *(_OWORD *)S1 = 0;
  v126 = 0;
  v127 = 0;
  v5 = v4[2];
  if ( v5 < 0x18 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v6 = v5 - 24;
  v7 = -1;
  if ( v6 != -1 )
    v7 = v6;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  std::wstring::_Construct<1,wchar_t const *>(S1, v4 + 6, v7);
  v8 = 3;
  v96 = 3;
  v9 = (const wchar_t *)S1;
  if ( v127 > 7 )
    v9 = S1[0];
  LOBYTE(v10) = v126 >= 0x34 && wmemcmp(v9, L"Microsoft.Windows.Health.TestInProduction.TestResult", 0x34u) == 0;
  std::wstring::~wstring(S1);
  v10 = (unsigned __int8)v10;
  v98 = (unsigned __int8)v10;
  v11 = *(_QWORD *)(a2 + 240);
  v12 = 0;
  while ( v11 != *(_QWORD *)(a2 + 248) )
  {
    v12 += 0xCF3CF3CF3CF3CF3DuLL * ((__int64)(*(_QWORD *)(v11 + 32) - *(_QWORD *)(v11 + 24)) >> 4);
    v11 += 48;
  }
  std::vector<UsageAndQualityInsights::Facts::FactRecord>::reserve(a1, v12);
  v13 = *(__int64 ***)(a2 + 240);
  v109 = *(__int64 ***)(a2 + 248);
  if ( v13 != v109 )
  {
    while ( 1 )
    {
      v14 = UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(a2 + 64);
      UsageAndQualityInsights::Utilities::TimePointFromFileTime(&v106, v14);
      v97[0] = 0;
      v97[1] = 0;
      v15 = operator new(0x60u);
      *v15 = v15;
      v15[1] = v15;
      v15[2] = v15;
      *((_WORD *)v15 + 12) = 257;
      v97[0] = v15;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
      {
        v16 = UsageAndQualityInsights::Configuration::FactSourceTypeToString(v128, v10);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::factSource", 18);
        v17 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        std::wstring::operator=(v17, v16);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v128);
        SourceEventFromMetricEvent = UsageAndQualityInsights::Utilities::GetSourceEventFromMetricEvent(v128, a2);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::factName", 16);
        v19 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        std::wstring::operator=(v19, SourceEventFromMetricEvent);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v128);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::factTime", 16);
        v20 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        std::wstring::operator=(v20, a2 + 64);
        std::wstring::~wstring(S1);
        v21 = UsageAndQualityInsights::Utilities::TimePointToIso8601(v128);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::hourTimeBin", 19);
        v22 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        std::wstring::operator=(v22, v21);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v128);
        v23 = UsageAndQualityInsights::Utilities::TimePointToIso8601(v128);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::dayTimeBin", 18);
        v24 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        std::wstring::operator=(v24, v23);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v128);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"hourly", 6);
        v8 |= 4u;
        v96 = v8;
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::window_type", 19);
        v25 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        std::wstring::operator=(v25, v128);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v128);
      }
      if ( *((_BYTE *)v13 + 16) )
      {
        v26 = (__int64 *)**v13;
        while ( !*((_BYTE *)v26 + 25) )
        {
          v27 = std::map<std::wstring,std::wstring>::operator[](v97);
          std::wstring::operator=(v27, v26 + 8);
          v28 = (__int64 **)v26[2];
          if ( *((_BYTE *)v28 + 25) )
          {
            for ( i = (__int64 *)v26[1]; !*((_BYTE *)i + 25) && v26 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v26 = i;
            v26 = i;
          }
          else
          {
            v26 = (__int64 *)v26[2];
            for ( j = *v28; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v26 = j;
          }
        }
      }
      v103 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
      {
        v137 = 0;
        v138 = 0;
        v139 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v137, L"system::hourTimeBin", 19);
        v33 = std::map<std::wstring,std::wstring>::operator[](v97, &v137);
        v37 = (_DWORD *)_o__errno(v35, v34, v36);
        v38 = v37;
        if ( *(_QWORD *)(v33 + 24) > 7u )
          v33 = *(_QWORD *)v33;
        EndPtr = 0;
        *v37 = 0;
        v39 = wcstoll((const wchar_t *)v33, &EndPtr, 10);
        if ( (wchar_t *)v33 == EndPtr )
        {
          std::_Xinvalid_argument("invalid stoll argument");
          return a1;
        }
        if ( *v38 == 34 )
        {
          std::_Xout_of_range("stoll argument out of range");
          __debugbreak();
        }
        v40 = *(_QWORD *)UsageAndQualityInsights::Utilities::TimePointFromFileTime(v111, v39);
        std::wstring::~wstring(&v137);
        v41 = UsageAndQualityInsights::Utilities::TimePointToIso8601((wchar_t *)S1);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"system::hourTimeBin", 19);
        v42 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v42, v41);
        std::wstring::~wstring(v128);
        std::wstring::~wstring(S1);
        v43 = UsageAndQualityInsights::Utilities::TimePointToIso8601((wchar_t *)S1);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"system::dayTimeBin", 18);
        v44 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v44, v43);
        std::wstring::~wstring(v128);
        std::wstring::~wstring(S1);
        v45 = UsageAndQualityInsights::Configuration::FactSourceTypeToString(S1, v98);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"system::factSource", 18);
        v46 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v46, v45);
        std::wstring::~wstring(v128);
        std::wstring::~wstring(S1);
        v47 = UsageAndQualityInsights::Utilities::GetSourceEventFromMetricEvent(S1, a2);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"system::factName", 16);
        v48 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v48, v47);
        std::wstring::~wstring(v128);
        std::wstring::~wstring(S1);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"system::factTime", 16);
        v49 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v49, a2 + 64);
        std::wstring::~wstring(v128);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"hourly", 6);
        v96 = v8 | 8;
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"system::window_type", 19);
        v50 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v50, S1);
        std::wstring::~wstring(v128);
        std::wstring::~wstring(S1);
        *(_OWORD *)S1 = 0;
        v126 = 0;
        v127 = 0;
        std::wstring::_Construct<1,wchar_t const *>(S1, L"system::userSid", 15);
        v51 = std::map<std::wstring,std::wstring>::operator[](v97, S1);
        v52 = std::operator+<wchar_t>(&v131, L"s:", v51);
        *(_OWORD *)v128 = 0;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,wchar_t const *>(v128, L"overwrite::PartA_Ext_App_UserId", 31);
        v53 = std::map<std::wstring,std::wstring>::operator[](v97, v128);
        std::wstring::operator=(v53, v52);
        std::wstring::~wstring(v128);
        std::wstring::~wstring(&v131);
        std::wstring::~wstring(S1);
        v54 = v13[3];
        v55 = v13[4];
        while ( v54 != v55 )
        {
          if ( (unsigned __int64)v54[3] <= 7 )
            v56 = (const wchar_t *)v54;
          else
            v56 = (const wchar_t *)*v54;
          if ( v54[2] == 12 && !wmemcmp(v56, L"__MinuteMask", 0xCu) )
          {
            if ( !*((_BYTE *)v54 + 232) )
              std::_Throw_bad_optional_access();
            v103 = v54[28];
          }
          v54 += 42;
        }
        v31 = 1LL << (v40 / 36000000000LL % 24);
        v32 = 1LL << (v40 / 864000000000LL % 63);
      }
      else
      {
        v31 = 0;
        v32 = 0;
      }
      v104 = v32;
      v57 = v13[3];
      v58 = v13[4];
      while ( v57 != v58 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl)
          || ((unsigned __int64)v57[3] <= 7 ? (v59 = (const wchar_t *)v57) : (v59 = (const wchar_t *)*v57),
              (unsigned __int64)v57[2] < 2 || wmemcmp(v59, L"__", 2u)) )
        {
          std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(&v100, v97);
          *(_OWORD *)v128 = 0;
          v129 = 0;
          v130 = 0;
          std::wstring::_Construct<1,wchar_t const *>(v128, L"system::metricName", 18);
          v60 = std::map<std::wstring,std::wstring>::operator[](&v100, v128);
          std::wstring::operator=(v60, v57);
          std::wstring::~wstring(v128);
          S1[1] = 0;
          v126 = 0;
          v61 = operator new(0x60u);
          *v61 = v61;
          v61[1] = v61;
          v61[2] = v61;
          *((_WORD *)v61 + 12) = 257;
          S1[1] = v100;
          v100 = (wchar_t *)v61;
          v62 = v126;
          v126 = v101;
          v101 = v62;
          S1[0] = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::Rehash((UsageAndQualityInsights::Facts::FactKey *)S1);
          LOBYTE(v88) = *((_BYTE *)v57 + 168) == 0;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xEF,
            (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factview.cpp",
            (const char *)0x80070057LL,
            v88,
            (bool)"Sum must be present in metric datapoint",
            v92);
          LOBYTE(v89) = *((_BYTE *)v57 + 200) == 0;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xF0,
            (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factview.cpp",
            (const char *)0x80070057LL,
            v89,
            (bool)"Min must be present in metric datapoint",
            v93);
          LOBYTE(v90) = *((_BYTE *)v57 + 216) == 0;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xF1,
            (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factview.cpp",
            (const char *)0x80070057LL,
            v90,
            (bool)"Max must be present in metric datapoint",
            v94);
          LOBYTE(v91) = *((_BYTE *)v57 + 152) == 0;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factview.cpp",
            (const char *)0x80070057LL,
            v91,
            (bool)"Count must be present in metric datapoint",
            v95);
          v63 = v57[18];
          if ( v63 < 0 )
          {
            v65 = v57[18] & 1 | ((unsigned __int64)v63 >> 1);
            v64 = (double)(int)v65 + (double)(int)v65;
          }
          else
          {
            v64 = (double)(int)v63;
          }
          if ( v63 )
            v66 = *((double *)v57 + 20) / v64;
          else
            v66 = 0.0;
          v112 = &v131;
          v67 = *((double *)v57 + 20);
          v131 = 160;
          v132 = 2;
          v133 = 20;
          v68 = pow(2.0, -20.0);
          X = pow(2.0, v68);
          v135 = 0.0;
          v136[0] = 0;
          v136[1] = 0;
          v69 = operator new(0x30u);
          *v69 = v69;
          v69[1] = v69;
          v69[2] = v69;
          *((_WORD *)v69 + 12) = 257;
          v136[0] = v69;
          if ( v64 > 0.0 )
          {
            v70 = v67 / v64;
            v105 = v70;
            v71 = o_log_0(v70);
            v72 = X;
            v73 = o_log_0(X);
            v99 = (int)floor(v71 / v73);
            if ( v70 < 0.0 || v72 < v70 )
              std::_Tree<std::_Tmap_traits<long,double,std::less<long>,std::allocator<std::pair<long const,double>>,0>>::emplace<long const &,double const &>(
                v136,
                v122,
                &v99,
                &v105);
            else
              v135 = v135 + v64;
            if ( v131 )
              --v131;
            else
              UsageAndQualityInsights::Facts::ExponentialHistogram::Rescale(
                (UsageAndQualityInsights::Facts::ExponentialHistogram *)&v131,
                v133 - 1);
          }
          HourTimeBin = (__int64 *)UsageAndQualityInsights::Facts::FactKey::GetHourTimeBin(S1, v113);
          UsageAndQualityInsights::Facts::ContinuousMetricFields::ContinuousMetricFields(
            (unsigned int)v123,
            v75,
            v76,
            v77,
            COERCE__INT64(v66 * v66),
            *(__int64 *)&v66,
            *HourTimeBin,
            (__int64)&v131);
          v114 = 0;
          v78 = v57[18];
          if ( v78 < 0 )
          {
            v80 = v57[18] & 1 | ((unsigned __int64)v78 >> 1);
            v79 = (double)(int)v80 + (double)(int)v80;
          }
          else
          {
            v79 = (double)(int)v78;
          }
          v115 = v79;
          v116 = v32;
          v117 = v31;
          v118 = v103;
          UsageAndQualityInsights::Facts::ContinuousMetricFields::ContinuousMetricFields(v119, v123);
          v121 = 1;
          v81 = UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(a2 + 64);
          UsageAndQualityInsights::Utilities::TimePointFromFileTime(&v107, v81);
          if ( !*(_BYTE *)(a2 + 232) )
            std::_Throw_bad_optional_access();
          v82 = v107;
          v83 = UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(a2 + 200);
          UsageAndQualityInsights::Utilities::TimePointFromFileTime(&v108, v83);
          UsageAndQualityInsights::Facts::FactRecord::FactRecord(
            (unsigned int)v124,
            (unsigned int)S1,
            (unsigned int)&v114,
            v108,
            v82);
          UsageAndQualityInsights::Facts::FactView::AppendFact(
            a1,
            (const struct UsageAndQualityInsights::Facts::FactRecord *)v124);
          UsageAndQualityInsights::Facts::FactRecord::~FactRecord((UsageAndQualityInsights::Facts::FactRecord *)v124);
          if ( v121 )
          {
            v84 = v120[0];
            v85 = (_QWORD *)*((_QWORD *)v120[0] + 1);
            if ( !*((_BYTE *)v85 + 25) )
            {
              do
              {
                std::_Tree_val<std::_Tree_simple_types<std::pair<long const,double>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<long const,double>,void *>>>(
                  v120,
                  v120,
                  v85[2]);
                v86 = v85;
                v85 = (_QWORD *)*v85;
                operator delete(v86, 0x30u);
              }
              while ( !*((_BYTE *)v85 + 25) );
              v84 = v120[0];
            }
            operator delete(v84, 0x30u);
          }
          UsageAndQualityInsights::Facts::ContinuousMetricFields::~ContinuousMetricFields((UsageAndQualityInsights::Facts::ContinuousMetricFields *)v123);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&S1[1]);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v100);
        }
        v57 += 42;
        v32 = v104;
      }
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v97);
      v13 += 6;
      if ( v13 == v109 )
        return a1;
      v8 = v96;
      v10 = v98;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800f7dcc  mov     rax, rsp
0x1800f7dcf  mov     [rax+18h], rbx
0x1800f7dd3  push    rbp
0x1800f7dd4  push    rsi
0x1800f7dd5  push    rdi
0x1800f7dd6  push    r12
0x1800f7dd8  push    r13
0x1800f7dda  push    r14
0x1800f7ddc  push    r15
0x1800f7dde  lea     rbp, [rax-2D8h]
0x1800f7de5  sub     rsp, 3A0h
0x1800f7dec  movaps  xmmword ptr [rax-48h], xmm6
0x1800f7df0  movaps  xmmword ptr [rax-58h], xmm7
0x1800f7df4  movaps  xmmword ptr [rax-68h], xmm8
0x1800f7df9  movaps  xmmword ptr [rax-78h], xmm9
0x1800f7dfe  movaps  xmmword ptr [rax-88h], xmm10
0x1800f7e06  movaps  xmmword ptr [rax-98h], xmm11
0x1800f7e0e  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800f7e16  mov     rax, cs:__security_cookie
0x1800f7e1d  xor     rax, rsp
0x1800f7e20  mov     [rbp+2D0h+var_B0], rax
0x1800f7e27  mov     r15, rdx
0x1800f7e2a  mov     r14, rcx
0x1800f7e2d  mov     [rbp+2D0h+var_320], rcx
0x1800f7e31  xor     esi, esi
0x1800f7e33  mov     dword ptr [rsp+3D0h+var_390], esi
0x1800f7e37  mov     [rcx], rsi
0x1800f7e3a  mov     [rcx+8], rsi
0x1800f7e3e  mov     [rcx+10h], rsi
0x1800f7e42  mov     dword ptr [rsp+3D0h+var_390], 1
0x1800f7e4a  add     rdx, 20h ; ' '
0x1800f7e4e  xorps   xmm0, xmm0
0x1800f7e51  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f7e58  mov     [rbp+2D0h+var_130], rsi
0x1800f7e5f  mov     [rbp+2D0h+var_128], rsi
0x1800f7e66  mov     rax, [rdx+10h]
0x1800f7e6a  cmp     rax, 18h
0x1800f7e6e  jb      loc_1800F8EBC
0x1800f7e74  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800f7e78  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f7e7c  cmp     rax, r8
0x1800f7e7f  cmovb   r8, rax
0x1800f7e83  cmp     qword ptr [rdx+18h], 7
0x1800f7e88  jbe     short loc_1800F7E8D
0x1800f7e8a  mov     rdx, [rdx]
0x1800f7e8d  add     rdx, 30h ; '0'
0x1800f7e91  lea     rcx, [rbp+2D0h+S1]
0x1800f7e98  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f7e9d  mov     r13d, 3
0x1800f7ea3  mov     dword ptr [rsp+3D0h+var_390], r13d
0x1800f7ea8  lea     rcx, [rbp+2D0h+S1]
0x1800f7eaf  cmp     [rbp+2D0h+var_128], 7
0x1800f7eb7  cmova   rcx, [rbp+2D0h+S1]; S1
0x1800f7ebf  lea     r8d, [r13+31h]; N
0x1800f7ec3  cmp     [rbp+2D0h+var_130], r8
0x1800f7eca  jnb     short loc_1800F7ED1
0x1800f7ecc  mov     bl, sil
0x1800f7ecf  jmp     short loc_1800F7EE2
0x1800f7ed1  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.Health.TestInProducti"...
0x1800f7ed8  call    wmemcmp
0x1800f7edd  test    eax, eax
0x1800f7edf  setz    bl
0x1800f7ee2  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f7ee9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f7eee  movzx   ebx, bl
0x1800f7ef1  mov     dword ptr [rsp+3D0h+var_378], ebx
0x1800f7ef5  mov     rax, [r15+0F8h]
0x1800f7efc  mov     r8, [r15+0F0h]
0x1800f7f03  mov     rdx, rsi
0x1800f7f06  jmp     short loc_1800F7F29
0x1800f7f08  mov     rcx, [r8+20h]
0x1800f7f0c  sub     rcx, [r8+18h]
0x1800f7f10  sar     rcx, 4
0x1800f7f14  mov     r9, 0CF3CF3CF3CF3CF3Dh
0x1800f7f1e  imul    rcx, r9
0x1800f7f22  add     rdx, rcx
0x1800f7f25  add     r8, 30h ; '0'
0x1800f7f29  cmp     r8, rax
0x1800f7f2c  jnz     short loc_1800F7F08
0x1800f7f2e  mov     rcx, r14
0x1800f7f31  call    ?reserve@?$vector@UFactRecord@Facts@UsageAndQualityInsights@@V?$allocator@UFactRecord@Facts@UsageAndQualityInsights@@@std@@@std@@QEAAX_K@Z; std::vector<UsageAndQualityInsights::Facts::FactRecord>::reserve(unsigned __int64)
0x1800f7f36  mov     r12, [r15+0F0h]
0x1800f7f3d  mov     rax, [r15+0F8h]
0x1800f7f44  mov     [rbp+2D0h+var_328], rax
0x1800f7f48  cmp     r12, rax
0x1800f7f4b  jz      loc_1800F8E66
0x1800f7f51  xorps   xmm11, xmm11
0x1800f7f55  movsd   xmm12, cs:__real@4000000000000000
0x1800f7f5e  lea     rdi, [r15+40h]
0x1800f7f62  mov     rcx, rdi
0x1800f7f65  call    ?PreciseUtc8601ToFileTime@Utilities@UsageAndQualityInsights@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(std::wstring const &)
0x1800f7f6a  mov     rdx, rax
0x1800f7f6d  lea     rcx, [rbp+2D0h+var_340]
0x1800f7f71  call    ?TimePointFromFileTime@Utilities@UsageAndQualityInsights@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_K@Z; UsageAndQualityInsights::Utilities::TimePointFromFileTime(unsigned __int64)
0x1800f7f76  mov     [rsp+3D0h+var_388], rsi
0x1800f7f7b  mov     qword ptr [rsp+3D0h+var_380], rsi
0x1800f7f80  mov     ecx, 60h ; '`'; Size
0x1800f7f85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f7f8a  mov     [rax], rax
0x1800f7f8d  mov     [rax+8], rax
0x1800f7f91  mov     [rax+10h], rax
0x1800f7f95  mov     word ptr [rax+18h], 101h
0x1800f7f9b  mov     [rsp+3D0h+var_388], rax
0x1800f7fa0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport> `wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl(void)'::`2'::impl
0x1800f7fa7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(void)
0x1800f7fac  test    al, al
0x1800f7fae  jnz     loc_1800F82EC
0x1800f7fb4  mov     edx, ebx
0x1800f7fb6  lea     rcx, [rbp+2D0h+var_120]
0x1800f7fbd  call    ?FactSourceTypeToString@Configuration@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4FactSourceType@12@@Z; UsageAndQualityInsights::Configuration::FactSourceTypeToString(UsageAndQualityInsights::Configuration::FactSourceType)
0x1800f7fc2  mov     rbx, rax
0x1800f7fc5  xorps   xmm0, xmm0
0x1800f7fc8  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f7fcf  mov     [rbp+2D0h+var_130], rsi
0x1800f7fd6  mov     [rbp+2D0h+var_128], rsi
0x1800f7fdd  mov     r8d, 12h
0x1800f7fe3  lea     rdx, aSystemFactsour; "system::factSource"
0x1800f7fea  lea     rcx, [rbp+2D0h+S1]
0x1800f7ff1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f7ff6  nop
0x1800f7ff7  lea     rdx, [rbp+2D0h+S1]
0x1800f7ffe  lea     rcx, [rsp+3D0h+var_388]
0x1800f8003  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800f8008  mov     rcx, rax
0x1800f800b  mov     rdx, rbx
0x1800f800e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f8013  nop
0x1800f8014  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f801b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f8020  nop
0x1800f8021  lea     rcx, [rbp+2D0h+var_120]; void *
0x1800f8028  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f802d  mov     rdx, r15
0x1800f8030  lea     rcx, [rbp+2D0h+var_120]
0x1800f8037  call    ?GetSourceEventFromMetricEvent@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUMetricEvent@12@@Z; UsageAndQualityInsights::Utilities::GetSourceEventFromMetricEvent(UsageAndQualityInsights::Utilities::MetricEvent const &)
0x1800f803c  mov     rbx, rax
0x1800f803f  xorps   xmm0, xmm0
0x1800f8042  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f8049  mov     [rbp+2D0h+var_130], rsi
0x1800f8050  mov     [rbp+2D0h+var_128], rsi
0x1800f8057  mov     r8d, 10h
0x1800f805d  lea     rdx, aSystemFactname; "system::factName"
0x1800f8064  lea     rcx, [rbp+2D0h+S1]
0x1800f806b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f8070  nop
0x1800f8071  lea     rdx, [rbp+2D0h+S1]
0x1800f8078  lea     rcx, [rsp+3D0h+var_388]
0x1800f807d  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800f8082  mov     rcx, rax
0x1800f8085  mov     rdx, rbx
0x1800f8088  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f808d  nop
0x1800f808e  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f8095  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f809a  nop
0x1800f809b  lea     rcx, [rbp+2D0h+var_120]; void *
0x1800f80a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f80a7  xorps   xmm0, xmm0
0x1800f80aa  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f80b1  mov     [rbp+2D0h+var_130], rsi
0x1800f80b8  mov     [rbp+2D0h+var_128], rsi
0x1800f80bf  mov     r8d, 10h
0x1800f80c5  lea     rdx, aSystemFacttime; "system::factTime"
0x1800f80cc  lea     rcx, [rbp+2D0h+S1]
0x1800f80d3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f80d8  nop
0x1800f80d9  lea     rdx, [rbp+2D0h+S1]
0x1800f80e0  lea     rcx, [rsp+3D0h+var_388]
0x1800f80e5  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800f80ea  mov     rcx, rax
0x1800f80ed  mov     rdx, rdi
0x1800f80f0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800f80f5  nop
0x1800f80f6  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f80fd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f8102  mov     rbx, [rbp+2D0h+var_340]
0x1800f8106  mov     rax, rbx
0x1800f8109  cqo
0x1800f810b  mov     r8, 861C46800h
0x1800f8115  idiv    r8
0x1800f8118  movsxd  rcx, eax
0x1800f811b  imul    rcx, r8
0x1800f811f  cmp     rcx, rbx
0x1800f8122  jz      short loc_1800F8128
0x1800f8124  jl      short loc_1800F8128
0x1800f8126  dec     eax
0x1800f8128  movsxd  rdx, eax
0x1800f812b  imul    rdx, r8
0x1800f812f  lea     rcx, [rbp+2D0h+var_120]; wchar_t *
0x1800f8136  call    ?TimePointToIso8601@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; UsageAndQualityInsights::Utilities::TimePointToIso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x1800f813b  mov     rdi, rax
0x1800f813e  xorps   xmm0, xmm0
0x1800f8141  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f8148  mov     [rbp+2D0h+var_130], rsi
0x1800f814f  mov     [rbp+2D0h+var_128], rsi
0x1800f8156  mov     r8d, 13h
0x1800f815c  lea     rdx, aSystemHourtime; "system::hourTimeBin"
0x1800f8163  lea     rcx, [rbp+2D0h+S1]
0x1800f816a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f816f  nop
0x1800f8170  lea     rdx, [rbp+2D0h+S1]
0x1800f8177  lea     rcx, [rsp+3D0h+var_388]
0x1800f817c  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800f8181  mov     rcx, rax
0x1800f8184  mov     rdx, rdi
0x1800f8187  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f818c  nop
0x1800f818d  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f8194  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f8199  nop
0x1800f819a  lea     rcx, [rbp+2D0h+var_120]; void *
0x1800f81a1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f81a6  mov     rax, rbx
0x1800f81a9  cqo
0x1800f81ab  mov     r8, 0C92A69C000h
0x1800f81b5  idiv    r8
0x1800f81b8  movsxd  rcx, eax
0x1800f81bb  imul    rcx, r8
0x1800f81bf  cmp     rcx, rbx
0x1800f81c2  jz      short loc_1800F81C8
0x1800f81c4  jl      short loc_1800F81C8
0x1800f81c6  dec     eax
0x1800f81c8  movsxd  rdx, eax
0x1800f81cb  imul    rdx, r8
0x1800f81cf  lea     rcx, [rbp+2D0h+var_120]; wchar_t *
0x1800f81d6  call    ?TimePointToIso8601@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; UsageAndQualityInsights::Utilities::TimePointToIso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x1800f81db  mov     rbx, rax
0x1800f81de  xorps   xmm0, xmm0
0x1800f81e1  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f81e8  mov     [rbp+2D0h+var_130], rsi
0x1800f81ef  mov     [rbp+2D0h+var_128], rsi
0x1800f81f6  mov     r8d, 12h
0x1800f81fc  lea     rdx, aSystemDaytimeb; "system::dayTimeBin"
0x1800f8203  lea     rcx, [rbp+2D0h+S1]
0x1800f820a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f820f  nop
0x1800f8210  lea     rdx, [rbp+2D0h+S1]
0x1800f8217  lea     rcx, [rsp+3D0h+var_388]
0x1800f821c  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800f8221  mov     rcx, rax
0x1800f8224  mov     rdx, rbx
0x1800f8227  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f822c  nop
0x1800f822d  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f8234  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f8239  nop
0x1800f823a  lea     rcx, [rbp+2D0h+var_120]; void *
0x1800f8241  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f8246  xorps   xmm0, xmm0
0x1800f8249  movups  xmmword ptr [rbp+2D0h+var_120], xmm0
0x1800f8250  mov     [rbp+2D0h+var_110], rsi
0x1800f8257  mov     [rbp+2D0h+var_108], rsi
0x1800f825e  mov     r8d, 6
0x1800f8264  lea     rdx, aHourly; "hourly"
0x1800f826b  lea     rcx, [rbp+2D0h+var_120]
0x1800f8272  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f8277  or      r13d, 4
0x1800f827b  mov     dword ptr [rsp+3D0h+var_390], r13d
0x1800f8280  xorps   xmm0, xmm0
0x1800f8283  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x1800f828a  mov     [rbp+2D0h+var_130], rsi
0x1800f8291  mov     [rbp+2D0h+var_128], rsi
0x1800f8298  mov     r8d, 13h
0x1800f829e  lea     rdx, aSystemWindowTy; "system::window_type"
0x1800f82a5  lea     rcx, [rbp+2D0h+S1]
0x1800f82ac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f82b1  nop
0x1800f82b2  lea     rdx, [rbp+2D0h+S1]
0x1800f82b9  lea     rcx, [rsp+3D0h+var_388]
0x1800f82be  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800f82c3  mov     rcx, rax
0x1800f82c6  lea     rdx, [rbp+2D0h+var_120]
0x1800f82cd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f82d2  nop
0x1800f82d3  lea     rcx, [rbp+2D0h+S1]; void *
0x1800f82da  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f82df  nop
0x1800f82e0  lea     rcx, [rbp+2D0h+var_120]; void *
0x1800f82e7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f82ec  cmp     [r12+10h], sil
0x1800f82f1  jz      short loc_1800F8362
0x1800f82f3  mov     rbx, [r12]
0x1800f82f7  mov     rbx, [rbx]
0x1800f82fa  cmp     [rbx+19h], sil
0x1800f82fe  jnz     short loc_1800F8362
0x1800f8300  lea     rdx, [rbx+20h]
0x1800f8304  lea     rdi, [rdx+20h]
0x1800f8308  lea     rcx, [rsp+3D0h+var_388]
0x1800f830d  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x1800f8312  mov     rcx, rax
0x1800f8315  mov     rdx, rdi
0x1800f8318  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800f831d  mov     rcx, [rbx+10h]
0x1800f8321  cmp     [rcx+19h], sil
0x1800f8325  jz      short loc_1800F8345
0x1800f8327  mov     rax, [rbx+8]
0x1800f832b  jmp     short loc_1800F833A
0x1800f832d  cmp     rbx, [rax+10h]
0x1800f8331  jnz     short loc_1800F8340
0x1800f8333  mov     rbx, rax
  ... truncated ...
```
