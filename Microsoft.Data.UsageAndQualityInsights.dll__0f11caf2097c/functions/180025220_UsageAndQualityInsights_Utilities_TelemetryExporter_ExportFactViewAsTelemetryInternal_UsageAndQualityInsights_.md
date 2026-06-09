# UsageAndQualityInsights::Utilities::TelemetryExporter::ExportFactViewAsTelemetryInternal(UsageAndQualityInsights::Facts::FactView const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,UsageAndQualityInsights::Utilities::TelemetryLevel,unsigned __int64,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x180025220`
- end: `0x180026188`
- name: `?ExportFactViewAsTelemetryInternal@TelemetryExporter@Utilities@UsageAndQualityInsights@@CAXAEBUFactView@Facts@3@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4TelemetryLevel@23@_KV?$basic_string_view@_WU?$char_traits@_W@std@@@7@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@7@@Z`
- size: `3944`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, service_task`

## callers

- `0x18002515c`

## callees

- `0x1800033d0`
- `0x1800038b8`
- `0x180005e7c`
- `0x1800108c8`
- `0x180010908`
- `0x180012dd4`
- `0x1800148b8`
- `0x180016648`
- `0x18001a8f4`
- `0x18001a92c`
- `0x180020650`
- `0x180022de4`
- `0x1800239a8`
- `0x180023a60`
- `0x180023b18`
- `0x180023b34`
- `0x180023fec`
- `0x1800241c0`
- `0x1800247e4`
- `0x18002492c`
- `0x180024c20`
- `0x180024c48`
- `0x180024c74`
- `0x180024d0c`
- `0x180024e88`
- `0x180025220`
- `0x180026190`
- `0x1800262cc`
- `0x1800266e8`
- `0x1800266fc`
- `0x180026710`
- `0x1800f92c8`
- `0x180108010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800257a6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800257a6`

## string_xrefs

- `0x1800256f7`: `onecore\base\usageandqualityinsights\service\lib\utilities\telemetryexporter.cpp`
- `0x18002616a`: `onecore\base\usageandqualityinsights\service\lib\utilities\telemetryexporter.cpp`
- `0x18002564d`: `PartAReplace_Time`
- `0x1800256e1`: `Invalid overwrite dimensions array size`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall UsageAndQualityInsights::Utilities::TelemetryExporter::ExportFactViewAsTelemetryInternal(
        __int64 *a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        __int128 *a5,
        __int64 *a6)
{
  _QWORD *v6; // rbx
  __int64 v8; // rcx
  _BYTE *v9; // rdx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdi
  UsageAndQualityInsights::Utilities::MetricData *v12; // rbx
  void *v13; // rax
  struct UsageAndQualityInsights::Utilities::MetricData *v14; // rsi
  struct UsageAndQualityInsights::Utilities::MetricData *v15; // rdi
  __int128 *v16; // rcx
  _BYTE *v17; // rdx
  __int128 *v18; // rcx
  _BYTE *v19; // rdx
  unsigned __int64 v20; // rbx
  __int64 i; // rcx
  __int64 (__fastcall ***v22)(); // rcx
  __int128 *v23; // rcx
  _BYTE *v24; // rdx
  double v25; // xmm0_8
  __int64 j; // rax
  __int128 *v27; // rcx
  _BYTE *v28; // rdx
  _QWORD *v29; // r8
  __int64 v30; // rax
  __int128 *v31; // rbx
  _QWORD *v32; // rsi
  _QWORD *v33; // r8
  __int64 v34; // rax
  __int128 *v35; // rdi
  _QWORD *v36; // r8
  __int64 v37; // rax
  __int64 *v38; // rbx
  _QWORD *v39; // rdx
  __int64 **v40; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rdx
  struct UsageAndQualityInsights::Utilities::MetricData *v46; // rsi
  struct UsageAndQualityInsights::Utilities::MetricData *v47; // r12
  __int64 v48; // r13
  __int64 *v49; // rbx
  _QWORD *v50; // rax
  _QWORD *v51; // r8
  __int64 v52; // rax
  __int64 **v53; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  __int64 *v56; // rdi
  __int64 *v57; // r15
  __int64 *v58; // r8
  __int64 v59; // rax
  _QWORD *v60; // r14
  _QWORD *v61; // r8
  __int64 v62; // rax
  _QWORD *v63; // r8
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // r14
  __int64 jj; // rbx
  __int64 v76; // rax
  unsigned __int16 v77; // ax
  __int64 Provider; // rax
  unsigned int v80; // eax
  int v81; // [rsp+20h] [rbp-E0h]
  const char *v82; // [rsp+28h] [rbp-D8h]
  char *v83; // [rsp+30h] [rbp-D0h] BYREF
  UsageAndQualityInsights::Utilities::MetricData *v84; // [rsp+38h] [rbp-C8h] BYREF
  UsageAndQualityInsights::Utilities::MetricData *v85; // [rsp+40h] [rbp-C0h]
  __int128 *v86; // [rsp+48h] [rbp-B8h]
  _BYTE v87[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v88; // [rsp+5Ah] [rbp-A6h]
  char v89; // [rsp+5Bh] [rbp-A5h]
  char v90; // [rsp+5Ch] [rbp-A4h]
  char v91; // [rsp+5Dh] [rbp-A3h]
  char v92; // [rsp+5Eh] [rbp-A2h]
  char v93; // [rsp+5Fh] [rbp-A1h]
  char v94; // [rsp+60h] [rbp-A0h]
  char v95; // [rsp+61h] [rbp-9Fh]
  char v96; // [rsp+62h] [rbp-9Eh]
  char v97; // [rsp+63h] [rbp-9Dh]
  char v98; // [rsp+64h] [rbp-9Ch]
  char v99; // [rsp+65h] [rbp-9Bh]
  char v100; // [rsp+66h] [rbp-9Ah]
  __int64 **v101; // [rsp+68h] [rbp-98h]
  double v102; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v103; // [rsp+80h] [rbp-80h]
  __int128 v104; // [rsp+90h] [rbp-70h] BYREF
  __int64 v105; // [rsp+A0h] [rbp-60h]
  __int64 v106; // [rsp+B0h] [rbp-50h] BYREF
  int v107; // [rsp+B8h] [rbp-48h]
  __int64 v108; // [rsp+C0h] [rbp-40h]
  __int64 v109; // [rsp+C8h] [rbp-38h]
  char v110; // [rsp+D0h] [rbp-30h]
  _QWORD v111[3]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v112[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v113; // [rsp+100h] [rbp+0h]
  _BYTE v114[32]; // [rsp+110h] [rbp+10h] BYREF
  char v115[32]; // [rsp+130h] [rbp+30h] BYREF
  char v116[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v117[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v118[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v119[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v120; // [rsp+1D0h] [rbp+D0h]
  _BYTE v121[32]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v122; // [rsp+1F8h] [rbp+F8h]
  __int128 v123; // [rsp+200h] [rbp+100h] BYREF
  char *v124; // [rsp+210h] [rbp+110h]
  __int128 *v125; // [rsp+220h] [rbp+120h] BYREF
  unsigned int v126; // [rsp+228h] [rbp+128h]
  __int64 *v127; // [rsp+230h] [rbp+130h]
  int *v128; // [rsp+238h] [rbp+138h]
  __int128 v129; // [rsp+240h] [rbp+140h] BYREF
  _BYTE *v130; // [rsp+250h] [rbp+150h]
  __int64 v131; // [rsp+258h] [rbp+158h] BYREF
  __int128 v132; // [rsp+260h] [rbp+160h]
  int v133; // [rsp+270h] [rbp+170h]
  int v134; // [rsp+274h] [rbp+174h]
  __int64 v135; // [rsp+278h] [rbp+178h]
  __int128 v136; // [rsp+280h] [rbp+180h]
  int v137; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v138[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v139[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v140[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v141[32]; // [rsp+300h] [rbp+200h] BYREF
  _QWORD v142[4]; // [rsp+320h] [rbp+220h] BYREF
  _QWORD v143[4]; // [rsp+340h] [rbp+240h] BYREF
  char v144; // [rsp+360h] [rbp+260h]
  _QWORD v145[4]; // [rsp+368h] [rbp+268h] BYREF
  char v146; // [rsp+388h] [rbp+288h]
  struct UsageAndQualityInsights::Utilities::MetricData *v147; // [rsp+390h] [rbp+290h]
  struct UsageAndQualityInsights::Utilities::MetricData *v148; // [rsp+398h] [rbp+298h]
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v103 = a3;
  v6 = a2;
  v111[0] = a4;
  if ( a3 )
  {
    if ( a3 - 1 > 1 )
    {
      v80 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\utilities\\telemetryexporter.cpp",
        (const char *)v80,
        (int)"Unsupported telemetry level",
        v82);
    }
    v8 = 0x800000000000LL;
  }
  else
  {
    v8 = 0x400000000000LL;
  }
  if ( a2[3] > 7u )
    v6 = (_QWORD *)*a2;
  v125 = &v129;
  v126 = 0;
  v127 = &v131;
  v128 = &v137;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 184549376;
  v134 = 4;
  v135 = v8;
  v136 = 0;
  v137 = 0;
  *(_QWORD *)&v104 = &v129;
  DWORD2(v104) = 0;
  LOBYTE(v83) = 0;
  std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v129, 0, &v83);
  LOBYTE(v83) = 0;
  if ( *((_BYTE **)&v129 + 1) == v130 )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v129, *((_QWORD *)&v129 + 1), &v83);
    v9 = (_BYTE *)*((_QWORD *)&v129 + 1);
  }
  else
  {
    **((_BYTE **)&v129 + 1) = 0;
    v9 = (_BYTE *)++*((_QWORD *)&v129 + 1);
  }
  LOBYTE(v83) = 0;
  if ( v9 == v130 )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v129, v9, &v83);
  }
  else
  {
    *v9 = 0;
    ++*((_QWORD *)&v129 + 1);
  }
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v104, v6);
  v104 = *a5;
  UsageAndQualityInsights::Facts::FactView::ToMetricEvent(a1, v138, &v104);
  v102 = COERCE_DOUBLE(v114);
  std::wstring::wstring(v114, v138);
  std::wstring::wstring(v115, v139);
  std::wstring::wstring(v116, v140);
  v111[1] = v117;
  std::wstring::wstring(v117, v141);
  v111[2] = v118;
  std::wstring::wstring(v118, v142);
  *(_QWORD *)&v104 = v119;
  v120 = 0;
  if ( v144 )
  {
    std::wstring::wstring(v119, v143);
    v120 = 1;
  }
  *(_QWORD *)&v104 = v121;
  v122 = 0;
  if ( v146 )
  {
    std::wstring::wstring(v121, v145);
    v122 = 1;
  }
  v123 = 0;
  v124 = 0;
  v10 = 0xAAAAAAAAAAAAAAABuLL * ((v148 - v147) >> 4);
  if ( v10 )
  {
    if ( v10 > 0x555555555555555LL )
      std::vector<std::pair<std::string_view,std::string_view>>::_Xlength();
    v11 = 16 * ((v148 - v147) >> 4);
    if ( v11 )
    {
      if ( v11 < 0x1000 )
      {
        v12 = (UsageAndQualityInsights::Utilities::MetricData *)operator new(16 * ((v148 - v147) >> 4));
      }
      else
      {
        if ( v11 + 39 < v11 )
          __scrt_throw_std_bad_array_new_length();
        v13 = operator new(v11 + 39);
        if ( !v13 )
          __fastfail(5u);
        v12 = (UsageAndQualityInsights::Utilities::MetricData *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v12 - 1) = v13;
      }
    }
    else
    {
      v12 = 0;
    }
    *(_QWORD *)&v123 = v12;
    *((_QWORD *)&v123 + 1) = v12;
    v124 = (char *)v12 + v11;
    *(_QWORD *)&v104 = &v123;
    v14 = v148;
    v15 = v147;
    v84 = v12;
    v85 = v12;
    v86 = &v123;
    while ( v15 != v14 )
    {
      UsageAndQualityInsights::Utilities::MetricData::MetricData(v12, v15);
      v12 = (UsageAndQualityInsights::Utilities::MetricData *)((char *)v12 + 48);
      v85 = v12;
      v15 = (struct UsageAndQualityInsights::Utilities::MetricData *)((char *)v15 + 48);
    }
    *((_QWORD *)&v123 + 1) = v12;
  }
  UsageAndQualityInsights::Utilities::CalculateSchemaDescriptor(v87, v114);
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v125, L"PartA_PrivTags");
  LOBYTE(v83) = 10;
  v16 = v125;
  v17 = (_BYTE *)*((_QWORD *)v125 + 1);
  if ( v17 == *((_BYTE **)v125 + 2) )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(v125, v17, &v83);
  }
  else
  {
    *v17 = 10;
    ++*((_QWORD *)v16 + 1);
  }
  if ( v126 )
    ++*(_BYTE *)(v126 + *(_QWORD *)v125);
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v127, v127[1], v111, 8);
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v125, L"PartAReplace_Time");
  LOBYTE(v83) = 17;
  v18 = v125;
  v19 = (_BYTE *)*((_QWORD *)v125 + 1);
  if ( v19 == *((_BYTE **)v125 + 2) )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(v125, v19, &v83);
  }
  else
  {
    *v19 = 17;
    ++*((_QWORD *)v18 + 1);
  }
  if ( v126 )
    ++*(_BYTE *)(v126 + *(_QWORD *)v125);
  v102 = COERCE_DOUBLE(UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(v140));
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v127, v127[1], &v102, 8);
  LOBYTE(v81) = a6[1] - *a6 != 96;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xCE,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\utilities\\telemetryexporter.cpp",
    (const char *)0x80070057LL,
    v81,
    (bool)"Invalid overwrite dimensions array size",
    v83);
  v20 = 0;
  for ( i = *a6; v20 < (a6[1] - *a6) >> 5; i = *a6 )
  {
    if ( *(_QWORD *)(i + 32 * v20 + 16) )
    {
      v22 = (&off_180158858)[8 * v20];
      if ( !v22 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      ((void (__fastcall *)(__int64 (__fastcall ***)(), __int128 **))(*v22)[2])(v22, &v125);
    }
    ++v20;
  }
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v125, L"pipeline_cardinality");
  LOBYTE(v83) = 12;
  v23 = v125;
  v24 = (_BYTE *)*((_QWORD *)v125 + 1);
  if ( v24 == *((_BYTE **)v125 + 2) )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(v125, v24, &v83);
  }
  else
  {
    *v24 = 12;
    ++*((_QWORD *)v23 + 1);
  }
  if ( v126 )
    ++*(_BYTE *)(v126 + *(_QWORD *)v125);
  v25 = 0.0;
  for ( j = *a1; j != a1[1]; j += 184 )
    v25 = v25 + *(double *)(j + 32);
  v102 = v25;
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v127, v127[1], &v102, 8);
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v125, L"baseType");
  LOBYTE(v83) = 1;
  v27 = v125;
  v28 = (_BYTE *)*((_QWORD *)v125 + 1);
  if ( v28 == *((_BYTE **)v125 + 2) )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(v125, v28, &v83);
  }
  else
  {
    *v28 = 1;
    ++*((_QWORD *)v27 + 1);
  }
  if ( v126 )
    ++*(_BYTE *)(v126 + *(_QWORD *)v125);
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v127, v127[1], L"MetricStream", 26);
  tld::EventBuilder<std::vector<unsigned char>>::AddStruct<wchar_t>(&v125, &v84, L"baseData");
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"baseVer");
  tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 1);
  v29 = v142;
  if ( v142[3] > 7u )
    v29 = (_QWORD *)v142[0];
  v30 = -1;
  do
    ++v30;
  while ( *((_WORD *)v29 + v30) );
  v31 = v86;
  v32 = (_QWORD *)v86 + 1;
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
    v86,
    *((_QWORD *)v86 + 1),
    v29,
    (unsigned int)(2 * v30 + 2));
  if ( v87[1] )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"startTimeExclusive");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 1);
    v33 = v145;
    if ( v145[3] > 7u )
      v33 = (_QWORD *)v145[0];
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
      v31,
      *v32,
      v33,
      (unsigned int)(2 * v34 + 2));
  }
  v35 = v31;
  if ( v87[0] )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"metricVer");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 1);
    if ( v143[3] <= 7u )
    {
      v35 = v31;
      v36 = v143;
    }
    else
    {
      v36 = (_QWORD *)v143[0];
    }
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
      v35,
      *v32,
      v36,
      (unsigned int)(2 * v37 + 2));
  }
  tld::EventBuilder<std::vector<unsigned char>>::AddStructArray<wchar_t>(&v84, &v104, L"metrics");
  LOWORD(v83) = -21845 * ((v148 - v147) >> 4);
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v105, *(_QWORD *)(v105 + 8), &v83, 2);
  tld::EventBuilder<std::vector<unsigned char>>::AddStruct<wchar_t>(&v104, v112, L"attributes");
  v38 = *v101;
  while ( !*((_BYTE *)v38 + 25) )
  {
    v39 = v38 + 4;
    if ( (unsigned __int64)v38[7] > 7 )
      v39 = (_QWORD *)*v39;
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(v112, v39);
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(v112, 0, 1);
    v40 = (__int64 **)v38[2];
    if ( *((_BYTE *)v40 + 25) )
    {
      for ( k = (__int64 *)v38[1]; !*((_BYTE *)k + 25) && v38 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v38 = k;
      v38 = k;
    }
    else
    {
      v38 = (__int64 *)v38[2];
      for ( m = *v40; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v38 = m;
    }
  }
  tld::EventBuilder<std::vector<unsigned char>>::AddStructArray<wchar_t>(&v104, &v84, L"datapoints");
  tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"name");
  tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 1);
  if ( v88 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"description");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 1);
  }
  if ( v89 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"unit");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 1);
  }
  if ( v95 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"explicitBounds");
    LOBYTE(v43) = 64;
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, v43, 12);
  }
  if ( v92 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"count");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 10);
  }
  if ( v91 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"sum");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 12);
  }
  if ( v90 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"value");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 12);
  }
  if ( v93 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"min");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 12);
  }
  if ( v94 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"max");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 12);
  }
  if ( v98 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"minuteMask");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 10);
  }
  if ( v99 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"hourMask");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 10);
  }
  if ( v100 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"dayMask");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, 0, 10);
  }
  v110 = 0;
  if ( v96 )
  {
    v44 = tld::EventBuilder<std::vector<unsigned char>>::AddStructArray<wchar_t>(&v84, &v104, L"quantileValues");
    v106 = *(_QWORD *)v44;
    v107 = *(_DWORD *)(v44 + 8);
    v108 = *(_QWORD *)(v44 + 16);
    v109 = *(_QWORD *)(v44 + 24);
    v110 = 1;
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v106, L"quantile");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v106, 0, 12);
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v106, L"value");
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v106, 0, 12);
  }
  if ( v97 )
  {
    tld::detail::MetadataBuilderBase<std::vector<unsigned char>>::AddString(&v84, L"bucketCounts");
    LOBYTE(v45) = 64;
    tld::EventMetadataBuilder<std::vector<unsigned char>>::AddFieldInfo(&v84, v45, 10);
  }
  v46 = v147;
  v47 = v148;
  if ( v147 != v148 )
  {
    v48 = v113;
    do
    {
      v49 = *v101;
      while ( !*((_BYTE *)v49 + 25) )
      {
        v50 = (_QWORD *)std::map<std::wstring,std::wstring>::at(v46, v49 + 4);
        v51 = v50;
        if ( v50[3] > 7u )
          v51 = (_QWORD *)*v50;
        v52 = -1;
        do
          ++v52;
        while ( *((_WORD *)v51 + v52) );
        std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
          v48,
          *(_QWORD *)(v48 + 8),
          v51,
          (unsigned int)(2 * v52 + 2));
        v53 = (__int64 **)v49[2];
        if ( *((_BYTE *)v53 + 25) )
        {
          for ( n = (__int64 *)v49[1]; !*((_BYTE *)n + 25) && v49 == (__int64 *)n[2]; n = (__int64 *)n[1] )
            v49 = n;
          v49 = n;
        }
        else
        {
          v49 = (__int64 *)v49[2];
          for ( ii = *v53; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
            v49 = ii;
        }
      }
      LOWORD(v83) = -12483 * ((__int64)(*((_QWORD *)v46 + 4) - *((_QWORD *)v46 + 3)) >> 4);
      std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v86, *((_QWORD *)v86 + 1), &v83, 2);
      v56 = (__int64 *)*((_QWORD *)v46 + 3);
      v57 = (__int64 *)*((_QWORD *)v46 + 4);
      while ( v56 != v57 )
      {
        if ( (unsigned __int64)v56[3] <= 7 )
          v58 = v56;
        else
          v58 = (__int64 *)*v56;
        v59 = -1;
        do
          ++v59;
        while ( *((_WORD *)v58 + v59) );
        v60 = (_QWORD *)v86 + 1;
        std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
          v86,
          *((_QWORD *)v86 + 1),
          v58,
          (unsigned int)(2 * v59 + 2));
        if ( v88 )
        {
          v61 = v56 + 4;
          if ( !*((_BYTE *)v56 + 64) )
            goto LABEL_181;
          if ( (unsigned __int64)v56[7] > 7 )
            v61 = (_QWORD *)*v61;
          v62 = -1;
          do
            ++v62;
          while ( *((_WORD *)v61 + v62) );
          std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
            v86,
            *v60,
            v61,
            (unsigned int)(2 * v62 + 2));
        }
        if ( v89 )
        {
          v63 = v56 + 9;
          if ( !*((_BYTE *)v56 + 104) )
LABEL_181:
            std::_Throw_bad_optional_access();
          if ( (unsigned __int64)v56[12] > 7 )
            v63 = (_QWORD *)*v63;
          v64 = -1;
          do
            ++v64;
          while ( *((_WORD *)v63 + v64) );
          std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
            v86,
            *v60,
            v63,
            (unsigned int)(2 * v64 + 2));
        }
        if ( v95 )
        {
          LOWORD(v83) = (__int64)(unsigned int)(*((_DWORD *)v56 + 30) - *((_DWORD *)v56 + 28)) >> 3;
          std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(v86, *v60, &v83, 2);
          std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(
            v86,
            *v60,
            v56[14],
            8LL * (unsigned __int16)((v56[15] - v56[14]) >> 3));
        }
        if ( v92 )
        {
          v65 = std::optional<double>::value(v56 + 18);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v65);
        }
        if ( v91 )
        {
          v66 = std::optional<double>::value(v56 + 20);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v66);
        }
        if ( v90 )
        {
          v67 = std::optional<double>::value(v56 + 22);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v67);
        }
        if ( v93 )
        {
          v68 = std::optional<double>::value(v56 + 24);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v68);
        }
        if ( v94 )
        {
          v69 = std::optional<double>::value(v56 + 26);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v69);
        }
        if ( v98 )
        {
          v70 = std::optional<double>::value(v56 + 28);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v70);
        }
        if ( v99 )
        {
          v71 = std::optional<double>::value(v56 + 30);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v71);
        }
        if ( v100 )
        {
          v72 = std::optional<double>::value(v56 + 32);
          tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v84, v72);
        }
        if ( v96 )
        {
          v73 = std::vector<UsageAndQualityInsights::Utilities::QuantileValue>::size(v56 + 34);
          tld::EventBuilder<std::vector<unsigned char>>::AddArrayCount(&v106, v73);
          v74 = v56[35];
          for ( jj = v56[34]; jj != v74; jj += 16 )
          {
            tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v106, jj);
            tld::EventBuilder<std::vector<unsigned char>>::AddValue<unsigned __int64>(&v106, jj + 8);
          }
        }
        if ( v97 )
        {
          v76 = std::vector<unsigned __int64>::size(v56 + 38);
          tld::EventBuilder<std::vector<unsigned char>>::AddArrayCount(&v84, v76);
          v77 = std::vector<unsigned __int64>::size(v56 + 38);
          tld::EventBuilder<std::vector<unsigned char>>::AddValues<unsigned __int64>(&v84, v56[38], v77);
        }
        v56 += 42;
      }
      v46 = (struct UsageAndQualityInsights::Utilities::MetricData *)((char *)v46 + 48);
    }
    while ( v46 != v47 );
  }
  Provider = UsageAndQualityInsights::Utilities::TelemetryExporter::GetProvider(v103);
  tld::Event<std::vector<unsigned char>>::Write((__int64)&v125, Provider);
  UsageAndQualityInsights::Utilities::SchemaDescriptor::~SchemaDescriptor((UsageAndQualityInsights::Utilities::SchemaDescriptor *)v87);
  UsageAndQualityInsights::Utilities::MetricEvent::~MetricEvent((UsageAndQualityInsights::Utilities::MetricEvent *)v138);
  return tld::Event<std::vector<unsigned char>>::~Event<std::vector<unsigned char>>(&v125);
}

```

## disassembly

```asm
0x180025220  push    rbp
0x180025222  push    rbx
0x180025223  push    rsi
0x180025224  push    rdi
0x180025225  push    r12
0x180025227  push    r13
0x180025229  push    r14
0x18002522b  push    r15
0x18002522d  lea     rbp, [rsp-2C8h]
0x180025235  sub     rsp, 3C8h
0x18002523c  mov     rax, cs:__security_cookie
0x180025243  xor     rax, rsp
0x180025246  mov     [rbp+300h+var_50], rax
0x18002524d  mov     [rbp+300h+var_380], r8d
0x180025251  mov     rbx, rdx
0x180025254  mov     r15, rcx
0x180025257  mov     [rbp+300h+var_328], r9
0x18002525b  mov     rdi, [rbp+300h+arg_20]
0x180025262  mov     r14, [rbp+300h+arg_28]
0x180025269  mov     ecx, r8d
0x18002526c  xor     r12d, r12d
0x18002526f  test    r8d, r8d
0x180025272  jz      short loc_18002528E
0x180025274  sub     ecx, 1
0x180025277  jz      short loc_180025282
0x180025279  cmp     ecx, 1
0x18002527c  jnz     loc_18002614A
0x180025282  mov     rcx, 800000000000h
0x18002528c  jmp     short loc_180025298
0x18002528e  mov     rcx, 400000000000h
0x180025298  cmp     qword ptr [rdx+18h], 7
0x18002529d  jbe     short loc_1800252A2
0x18002529f  mov     rbx, [rdx]
0x1800252a2  lea     rax, [rbp+300h+var_1C0]
0x1800252a9  mov     [rbp+300h+var_1E0], rax
0x1800252b0  mov     [rbp+300h+var_1D8], r12d
0x1800252b7  lea     rax, [rbp+300h+var_1A8]
0x1800252be  mov     [rbp+300h+var_1D0], rax
0x1800252c5  lea     rax, [rbp+300h+var_170]
0x1800252cc  mov     [rbp+300h+var_1C8], rax
0x1800252d3  xorps   xmm0, xmm0
0x1800252d6  movdqa  [rbp+300h+var_1C0], xmm0
0x1800252de  mov     [rbp+300h+var_1B0], r12
0x1800252e5  mov     [rbp+300h+var_1A8], r12
0x1800252ec  movdqa  [rbp+300h+var_1A0], xmm0
0x1800252f4  mov     [rbp+300h+var_190], 0B000000h
0x1800252fe  mov     [rbp+300h+var_18C], 4
0x180025308  mov     [rbp+300h+var_188], rcx
0x18002530f  movdqa  [rbp+300h+var_180], xmm0
0x180025317  mov     [rbp+300h+var_170], r12d
0x18002531e  lea     rax, [rbp+300h+var_1C0]
0x180025325  mov     qword ptr [rbp+300h+var_370], rax
0x180025329  mov     dword ptr [rbp+300h+var_370+8], r12d
0x18002532d  mov     byte ptr [rsp+400h+var_3D0], r12b
0x180025332  lea     r8, [rsp+400h+var_3D0]
0x180025337  xor     edx, edx
0x180025339  lea     rcx, [rbp+300h+var_1C0]
0x180025340  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x180025345  mov     byte ptr [rsp+400h+var_3D0], r12b
0x18002534a  mov     rdx, qword ptr [rbp+300h+var_1C0+8]
0x180025351  mov     r13d, 1
0x180025357  cmp     rdx, [rbp+300h+var_1B0]
0x18002535e  jz      short loc_180025376
0x180025360  mov     [rdx], r12b
0x180025363  mov     rdx, qword ptr [rbp+300h+var_1C0+8]
0x18002536a  add     rdx, r13
0x18002536d  mov     qword ptr [rbp+300h+var_1C0+8], rdx
0x180025374  jmp     short loc_18002538E
0x180025376  lea     r8, [rsp+400h+var_3D0]
0x18002537b  lea     rcx, [rbp+300h+var_1C0]
0x180025382  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x180025387  mov     rdx, qword ptr [rbp+300h+var_1C0+8]
0x18002538e  mov     byte ptr [rsp+400h+var_3D0], r12b
0x180025393  cmp     rdx, [rbp+300h+var_1B0]
0x18002539a  jz      short loc_1800253A8
0x18002539c  mov     [rdx], r12b
0x18002539f  add     qword ptr [rbp+300h+var_1C0+8], r13
0x1800253a6  jmp     short loc_1800253B9
0x1800253a8  lea     r8, [rsp+400h+var_3D0]
0x1800253ad  lea     rcx, [rbp+300h+var_1C0]
0x1800253b4  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x1800253b9  mov     rdx, rbx
0x1800253bc  lea     rcx, [rbp+300h+var_370]
0x1800253c0  call    ?AddString@?$MetadataBuilderBase@V?$vector@EV?$allocator@E@std@@@std@@@detail@tld@@IEAAXPEB_W@Z; tld::detail::MetadataBuilderBase<std::vector<uchar>>::AddString(wchar_t const *)
0x1800253c5  nop
0x1800253c6  movaps  xmm0, xmmword ptr [rdi]
0x1800253c9  movdqa  [rbp+300h+var_370], xmm0
0x1800253ce  lea     r8, [rbp+300h+var_370]
0x1800253d2  lea     rdx, [rbp+300h+var_160]
0x1800253d9  mov     rcx, r15
0x1800253dc  call    ?ToMetricEvent@FactView@Facts@UsageAndQualityInsights@@QEBA?AUMetricEvent@Utilities@3@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; UsageAndQualityInsights::Facts::FactView::ToMetricEvent(std::wstring_view)
0x1800253e1  nop
0x1800253e2  lea     rax, [rbp+300h+var_2F0]
0x1800253e6  mov     [rsp+400h+var_388], rax
0x1800253eb  lea     rdx, [rbp+300h+var_160]
0x1800253f2  lea     rcx, [rbp+300h+var_2F0]
0x1800253f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800253fb  nop
0x1800253fc  lea     rdx, [rbp+300h+var_140]
0x180025403  lea     rcx, [rbp+300h+var_2D0]
0x180025407  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002540c  nop
0x18002540d  lea     rdx, [rbp+300h+var_120]
0x180025414  lea     rcx, [rbp+300h+var_2B0]
0x180025418  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002541d  nop
0x18002541e  lea     rax, [rbp+300h+var_290]
0x180025422  mov     [rbp+300h+var_320], rax
0x180025426  lea     rdx, [rbp+300h+var_100]
0x18002542d  lea     rcx, [rbp+300h+var_290]
0x180025431  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025436  nop
0x180025437  lea     rax, [rbp+300h+var_270]
0x18002543e  mov     [rbp+300h+var_318], rax
0x180025442  lea     rdx, [rbp+300h+var_E0]
0x180025449  lea     rcx, [rbp+300h+var_270]
0x180025450  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025455  nop
0x180025456  lea     rax, [rbp+300h+var_250]
0x18002545d  mov     qword ptr [rbp+300h+var_370], rax
0x180025461  mov     [rbp+300h+var_230], r12b
0x180025468  cmp     [rbp+300h+var_A0], r12b
0x18002546f  jz      short loc_18002548B
0x180025471  lea     rdx, [rbp+300h+var_C0]
0x180025478  lea     rcx, [rbp+300h+var_250]
0x18002547f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025484  mov     [rbp+300h+var_230], r13b
0x18002548b  lea     rax, [rbp+300h+var_228]
0x180025492  mov     qword ptr [rbp+300h+var_370], rax
0x180025496  mov     [rbp+300h+var_208], r12b
0x18002549d  cmp     [rbp+300h+var_78], r12b
0x1800254a4  jz      short loc_1800254C0
0x1800254a6  lea     rdx, [rbp+300h+var_98]
0x1800254ad  lea     rcx, [rbp+300h+var_228]
0x1800254b4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800254b9  mov     [rbp+300h+var_208], r13b
0x1800254c0  xorps   xmm0, xmm0
0x1800254c3  movdqu  [rbp+300h+var_200], xmm0
0x1800254cb  mov     [rbp+300h+var_1F0], r12
0x1800254d2  mov     rax, [rbp+300h+var_68]
0x1800254d9  sub     rax, [rbp+300h+var_70]
0x1800254e0  sar     rax, 4
0x1800254e4  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800254ee  imul    rax, rcx
0x1800254f2  test    rax, rax
0x1800254f5  jz      loc_1800255CC
0x1800254fb  mov     rcx, 555555555555555h
0x180025505  cmp     rax, rcx
0x180025508  ja      loc_18002617C
0x18002550e  lea     rdi, [rax+rax*2]
0x180025512  shl     rdi, 4
0x180025516  test    rdi, rdi
0x180025519  jnz     short loc_180025520
0x18002551b  mov     rbx, r12
0x18002551e  jmp     short loc_18002555E
0x180025520  cmp     rdi, 1000h
0x180025527  jb      short loc_180025553
0x180025529  lea     rcx, [rdi+27h]; Size
0x18002552d  cmp     rcx, rdi
0x180025530  jbe     loc_180026182
0x180025536  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002553b  test    rax, rax
0x18002553e  jnz     short loc_180025545
0x180025540  lea     ecx, [rax+5]
0x180025543  int     29h; Win8: RtlFailFast(ecx)
0x180025545  lea     rbx, [rax+27h]
0x180025549  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18002554d  mov     [rbx-8], rax
0x180025551  jmp     short loc_18002555E
0x180025553  mov     rcx, rdi; Size
0x180025556  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002555b  mov     rbx, rax
0x18002555e  mov     qword ptr [rbp+300h+var_200], rbx
0x180025565  mov     qword ptr [rbp+300h+var_200+8], rbx
0x18002556c  lea     rcx, [rbx+rdi]
0x180025570  mov     [rbp+300h+var_1F0], rcx
0x180025577  lea     rax, [rbp+300h+var_200]
0x18002557e  mov     qword ptr [rbp+300h+var_370], rax
0x180025582  mov     rsi, [rbp+300h+var_68]
0x180025589  mov     rdi, [rbp+300h+var_70]
0x180025590  mov     [rsp+400h+var_3C8], rbx
0x180025595  mov     [rsp+400h+var_3C0], rbx
0x18002559a  lea     rax, [rbp+300h+var_200]
0x1800255a1  mov     [rsp+400h+var_3B8], rax
0x1800255a6  jmp     short loc_1800255C0
0x1800255a8  mov     rdx, rdi; struct UsageAndQualityInsights::Utilities::MetricData *
0x1800255ab  mov     rcx, rbx; this
0x1800255ae  call    ??0MetricData@Utilities@UsageAndQualityInsights@@QEAA@AEBU012@@Z; UsageAndQualityInsights::Utilities::MetricData::MetricData(UsageAndQualityInsights::Utilities::MetricData const &)
0x1800255b3  add     rbx, 30h ; '0'
0x1800255b7  mov     [rsp+400h+var_3C0], rbx
0x1800255bc  add     rdi, 30h ; '0'
0x1800255c0  cmp     rdi, rsi
0x1800255c3  jnz     short loc_1800255A8
0x1800255c5  mov     qword ptr [rbp+300h+var_200+8], rbx
0x1800255cc  lea     rdx, [rbp+300h+var_2F0]
0x1800255d0  lea     rcx, [rsp+400h+var_3A8]
0x1800255d5  call    ?CalculateSchemaDescriptor@Utilities@UsageAndQualityInsights@@YA?AUSchemaDescriptor@12@UMetricEvent@12@@Z; UsageAndQualityInsights::Utilities::CalculateSchemaDescriptor(UsageAndQualityInsights::Utilities::MetricEvent)
0x1800255da  nop
0x1800255db  lea     rdx, aPartaPrivtags; "PartA_PrivTags"
0x1800255e2  lea     rcx, [rbp+300h+var_1E0]
0x1800255e9  call    ?AddString@?$MetadataBuilderBase@V?$vector@EV?$allocator@E@std@@@std@@@detail@tld@@IEAAXPEB_W@Z; tld::detail::MetadataBuilderBase<std::vector<uchar>>::AddString(wchar_t const *)
0x1800255ee  mov     byte ptr [rsp+400h+var_3D0], 0Ah
0x1800255f3  mov     rcx, [rbp+300h+var_1E0]
0x1800255fa  mov     rdx, [rcx+8]
0x1800255fe  cmp     rdx, [rcx+10h]
0x180025602  jz      short loc_18002560D
0x180025604  mov     byte ptr [rdx], 0Ah
0x180025607  add     [rcx+8], r13
0x18002560b  jmp     short loc_180025617
0x18002560d  lea     r8, [rsp+400h+var_3D0]
0x180025612  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x180025617  mov     ecx, [rbp+300h+var_1D8]
0x18002561d  test    ecx, ecx
0x18002561f  jz      short loc_180025631
0x180025621  mov     rax, [rbp+300h+var_1E0]
0x180025628  mov     edx, ecx
0x18002562a  mov     rcx, [rax]
0x18002562d  add     [rdx+rcx], r13b
0x180025631  mov     rcx, [rbp+300h+var_1D0]
0x180025638  mov     edi, 8
0x18002563d  mov     r9d, edi
0x180025640  lea     r8, [rbp+300h+var_328]
0x180025644  mov     rdx, [rcx+8]
0x180025648  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x18002564d  lea     rdx, aPartareplaceTi; "PartAReplace_Time"
0x180025654  lea     rcx, [rbp+300h+var_1E0]
0x18002565b  call    ?AddString@?$MetadataBuilderBase@V?$vector@EV?$allocator@E@std@@@std@@@detail@tld@@IEAAXPEB_W@Z; tld::detail::MetadataBuilderBase<std::vector<uchar>>::AddString(wchar_t const *)
0x180025660  mov     byte ptr [rsp+400h+var_3D0], 11h; char *
0x180025665  mov     rcx, [rbp+300h+var_1E0]
0x18002566c  mov     rdx, [rcx+8]
0x180025670  cmp     rdx, [rcx+10h]
0x180025674  jz      short loc_18002567F
0x180025676  mov     byte ptr [rdx], 11h
0x180025679  add     [rcx+8], r13
0x18002567d  jmp     short loc_180025689
0x18002567f  lea     r8, [rsp+400h+var_3D0]
0x180025684  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x180025689  mov     ecx, [rbp+300h+var_1D8]
0x18002568f  test    ecx, ecx
0x180025691  jz      short loc_1800256A3
0x180025693  mov     rax, [rbp+300h+var_1E0]
0x18002569a  mov     edx, ecx
0x18002569c  mov     rcx, [rax]
0x18002569f  add     [rdx+rcx], r13b
0x1800256a3  lea     rcx, [rbp+300h+var_120]
0x1800256aa  call    ?PreciseUtc8601ToFileTime@Utilities@UsageAndQualityInsights@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(std::wstring const &)
0x1800256af  mov     [rsp+400h+var_388], rax
0x1800256b4  mov     rcx, [rbp+300h+var_1D0]
0x1800256bb  mov     r9, rdi
0x1800256be  lea     r8, [rsp+400h+var_388]
0x1800256c3  mov     rdx, [rcx+8]
0x1800256c7  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x1800256cc  mov     rax, [r14+8]
0x1800256d0  sub     rax, [r14]
0x1800256d3  cmp     rax, 60h ; '`'
0x1800256d7  setnz   al
0x1800256da  mov     rcx, [rbp+308h]; this
0x1800256e1  lea     rdx, aInvalidOverwri; "Invalid overwrite dimensions array size"
0x1800256e8  mov     qword ptr [rsp+400h+var_3D8], rdx; bool
0x1800256ed  mov     byte ptr [rsp+400h+var_3E0], al; int
0x1800256f1  mov     r9d, 80070057h; char *
0x1800256f7  lea     r8, aOnecoreBaseUsa_4; "onecore\\base\\usageandqualityinsights"...
0x1800256fe  mov     edx, 0CEh; void *
0x180025703  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180025708  mov     rbx, r12
0x18002570b  mov     rcx, [r14]
0x18002570e  mov     rax, [r14+8]
0x180025712  sub     rax, rcx
0x180025715  sar     rax, 5
0x180025719  test    rax, rax
0x18002571c  jz      short loc_18002576E
0x18002571e  mov     r8, rbx
0x180025721  shl     r8, 5
0x180025725  add     r8, rcx
0x180025728  cmp     [r8+10h], r12
0x18002572c  jz      short loc_180025758
0x18002572e  mov     rax, rbx
0x180025731  shl     rax, 6
0x180025735  lea     rcx, off_180158858
0x18002573c  mov     rcx, [rax+rcx]
0x180025740  test    rcx, rcx
0x180025743  jz      short loc_1800257A6
0x180025745  mov     rax, [rcx]
0x180025748  lea     rdx, [rbp+300h+var_1E0]
0x18002574f  mov     rax, [rax+10h]
0x180025753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025758  add     rbx, r13
0x18002575b  mov     rcx, [r14]
0x18002575e  mov     rax, [r14+8]
0x180025762  sub     rax, rcx
0x180025765  sar     rax, 5
0x180025769  cmp     rbx, rax
0x18002576c  jb      short loc_18002571E
0x18002576e  lea     rdx, aPipelineCardin; "pipeline_cardinality"
0x180025775  lea     rcx, [rbp+300h+var_1E0]
0x18002577c  call    ?AddString@?$MetadataBuilderBase@V?$vector@EV?$allocator@E@std@@@std@@@detail@tld@@IEAAXPEB_W@Z; tld::detail::MetadataBuilderBase<std::vector<uchar>>::AddString(wchar_t const *)
0x180025781  mov     r14d, 0Ch
0x180025787  mov     byte ptr [rsp+400h+var_3D0], r14b
0x18002578c  mov     rcx, [rbp+300h+var_1E0]
0x180025793  mov     rdx, [rcx+8]
  ... truncated ...
```
