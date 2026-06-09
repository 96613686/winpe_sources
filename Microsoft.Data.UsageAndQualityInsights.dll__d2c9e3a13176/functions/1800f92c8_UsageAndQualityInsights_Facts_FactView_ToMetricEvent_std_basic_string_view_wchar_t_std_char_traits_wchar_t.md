# UsageAndQualityInsights::Facts::FactView::ToMetricEvent(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800f92c8`
- end: `0x1800f9deb`
- name: `?ToMetricEvent@FactView@Facts@UsageAndQualityInsights@@QEBA?AUMetricEvent@Utilities@3@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `2851`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025220`

## callees

- `0x180002fd0`
- `0x1800033d0`
- `0x1800038b8`
- `0x180003fac`
- `0x180005e7c`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180010908`
- `0x180012054`
- `0x180012dd4`
- `0x180012f84`
- `0x18001386c`
- `0x180013ff8`
- `0x180014618`
- `0x1800163f8`
- `0x180016680`
- `0x180016698`
- `0x180019458`
- `0x180019794`
- `0x180019b64`
- `0x18001a380`
- `0x18001a3e8`
- `0x18001a8f4`
- `0x18001a9b0`
- `0x1800233bc`
- `0x180024678`
- `0x1800247e4`
- `0x1800266d0`
- `0x180026820`
- `0x18002733c`
- `0x180027ba4`
- `0x1800349f0`
- `0x180034f1c`
- `0x180036e34`
- `0x1800f63b0`
- `0x1800f65ec`
- `0x1800f6f54`
- `0x1800f7268`
- `0x1800f7444`
- `0x1800f92c8`
- `0x1800fa1e0`
- `0x1800fd380`
- `0x1800fd834`
- `0x1800fdd88`
- `0x1800fe830`
- `0x1800ff804`
- `0x1800ff850`
- `0x1800ff89c`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800f951f`
- `msvcp_win!_Xtime_get_ticks` at `0x1800f951f`

## string_xrefs

- `0x1800f9dc7`: `onecore\base\usageandqualityinsights\service\lib\factstore\factview.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall UsageAndQualityInsights::Facts::FactView::ToMetricEvent(__int64 *a1, __int64 a2, __int64 a3)
{
  _WORD **v6; // rsi
  _WORD **v7; // rdi
  _WORD *v8; // rbx
  __int64 v9; // r8
  _WORD *v10; // rbx
  __int64 v11; // r8
  _WORD *v12; // rbx
  __int64 v13; // r8
  _WORD **v14; // rcx
  _WORD *v15; // rbx
  _OWORD *v16; // rcx
  __m128i si128; // xmm7
  __int64 ticks; // r14
  __int64 v19; // rsi
  _QWORD *v20; // rax
  __int64 v21; // r13
  __int64 v22; // r15
  unsigned __int64 v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rdi
  _QWORD *v26; // rcx
  _QWORD *v27; // rbx
  _QWORD *v28; // rbx
  _QWORD *v29; // rax
  __int64 *v30; // rbx
  __int64 *v31; // r13
  const wchar_t *v32; // rcx
  unsigned __int64 v33; // r8
  __int64 v34; // rcx
  unsigned __int64 v35; // r15
  unsigned __int64 v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r13
  __int64 v41; // rax
  std::_Format_arg_index *v42; // rdi
  __int64 v43; // r15
  __int64 v44; // rdi
  __int64 v45; // rcx
  __int64 v46; // rdi
  _QWORD *v47; // r15
  __int64 **v48; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 MetricName; // rax
  unsigned __int64 v52; // rcx
  double v53; // xmm0_8
  _QWORD *v54; // rdi
  _QWORD *k; // rbx
  __int64 v56; // rax
  __int64 v57; // rax
  unsigned int v59; // eax
  const char *v60; // [rsp+30h] [rbp-D8h]
  __int64 v61; // [rsp+40h] [rbp-C8h]
  int v62; // [rsp+48h] [rbp-C0h]
  __int64 v63; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v64; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v65[2]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v66[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v67; // [rsp+88h] [rbp-80h]
  __int128 v68; // [rsp+90h] [rbp-78h] BYREF
  char v69; // [rsp+A0h] [rbp-68h]
  __int128 v70; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-50h]
  int v72; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD *v73; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 v74; // [rsp+D8h] [rbp-30h]
  __int64 v75; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v76; // [rsp+E8h] [rbp-20h]
  __int64 v77; // [rsp+F8h] [rbp-10h]
  __int64 v78; // [rsp+100h] [rbp-8h]
  __int128 *v79; // [rsp+108h] [rbp+0h] BYREF
  _QWORD *v80; // [rsp+110h] [rbp+8h]
  __int64 v81; // [rsp+118h] [rbp+10h] BYREF
  __int64 v82; // [rsp+120h] [rbp+18h]
  __int64 v83; // [rsp+128h] [rbp+20h]
  __int128 *v84; // [rsp+130h] [rbp+28h]
  __int64 v85; // [rsp+138h] [rbp+30h]
  char v86[8]; // [rsp+148h] [rbp+40h] BYREF
  char v87[16]; // [rsp+150h] [rbp+48h] BYREF
  char v88[16]; // [rsp+160h] [rbp+58h] BYREF
  __int128 v89; // [rsp+170h] [rbp+68h] BYREF
  __m128i v90; // [rsp+180h] [rbp+78h]
  __int64 v91; // [rsp+190h] [rbp+88h]
  __int64 v92; // [rsp+198h] [rbp+90h]
  char *Src[5]; // [rsp+1A0h] [rbp+98h] BYREF
  _OWORD v94[4]; // [rsp+1C8h] [rbp+C0h] BYREF
  char v95; // [rsp+208h] [rbp+100h]
  char v96; // [rsp+230h] [rbp+128h]
  char v97; // [rsp+250h] [rbp+148h]
  unsigned __int64 v98; // [rsp+258h] [rbp+150h]
  char v99; // [rsp+260h] [rbp+158h]
  int v100; // [rsp+261h] [rbp+159h]
  __int16 v101; // [rsp+265h] [rbp+15Dh]
  char v102; // [rsp+267h] [rbp+15Fh]
  double Sum; // [rsp+268h] [rbp+160h]
  char v104; // [rsp+270h] [rbp+168h]
  int v105; // [rsp+271h] [rbp+169h]
  __int16 v106; // [rsp+275h] [rbp+16Dh]
  char v107; // [rsp+277h] [rbp+16Fh]
  char v108; // [rsp+280h] [rbp+178h]
  double Min; // [rsp+288h] [rbp+180h]
  char v110; // [rsp+290h] [rbp+188h]
  int v111; // [rsp+291h] [rbp+189h]
  __int16 v112; // [rsp+295h] [rbp+18Dh]
  char v113; // [rsp+297h] [rbp+18Fh]
  double Max; // [rsp+298h] [rbp+190h]
  char v115; // [rsp+2A0h] [rbp+198h]
  int v116; // [rsp+2A1h] [rbp+199h]
  __int16 v117; // [rsp+2A5h] [rbp+19Dh]
  char v118; // [rsp+2A7h] [rbp+19Fh]
  __int64 v119; // [rsp+2A8h] [rbp+1A0h]
  char v120; // [rsp+2B0h] [rbp+1A8h]
  int v121; // [rsp+2B1h] [rbp+1A9h]
  __int16 v122; // [rsp+2B5h] [rbp+1ADh]
  char v123; // [rsp+2B7h] [rbp+1AFh]
  __int64 v124; // [rsp+2B8h] [rbp+1B0h]
  char v125; // [rsp+2C0h] [rbp+1B8h]
  int v126; // [rsp+2C1h] [rbp+1B9h]
  __int16 v127; // [rsp+2C5h] [rbp+1BDh]
  char v128; // [rsp+2C7h] [rbp+1BFh]
  __int64 v129; // [rsp+2C8h] [rbp+1C0h]
  char v130; // [rsp+2D0h] [rbp+1C8h]
  int v131; // [rsp+2D1h] [rbp+1C9h]
  __int16 v132; // [rsp+2D5h] [rbp+1CDh]
  char v133; // [rsp+2D7h] [rbp+1CFh]
  char v134; // [rsp+2F0h] [rbp+1E8h]
  char v135; // [rsp+310h] [rbp+208h]
  wil::details::in1diag3 *retaddr; // [rsp+380h] [rbp+278h]

  v85 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  v6 = (_WORD **)(a2 + 32);
  *(_OWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  *(_QWORD *)(a2 + 56) = 7;
  *(_WORD *)(a2 + 32) = 0;
  *(_OWORD *)(a2 + 64) = 0;
  *(_QWORD *)(a2 + 80) = 0;
  *(_QWORD *)(a2 + 88) = 7;
  *(_WORD *)(a2 + 64) = 0;
  v7 = (_WORD **)(a2 + 96);
  *(_OWORD *)(a2 + 96) = 0;
  *(_QWORD *)(a2 + 112) = 0;
  *(_QWORD *)(a2 + 120) = 7;
  *(_WORD *)(a2 + 96) = 0;
  *(_OWORD *)(a2 + 128) = 0;
  *(_QWORD *)(a2 + 144) = 0;
  *(_QWORD *)(a2 + 152) = 7;
  *(_WORD *)(a2 + 128) = 0;
  *(_BYTE *)(a2 + 192) = 0;
  *(_BYTE *)(a2 + 232) = 0;
  *(_QWORD *)(a2 + 240) = 0;
  *(_QWORD *)(a2 + 248) = 0;
  *(_QWORD *)(a2 + 256) = 0;
  v62 = 1;
  if ( *(_QWORD *)(a2 + 24) < 3u )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      a2,
      3,
      a3,
      L"4.0");
  }
  else
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v8 = (_WORD *)a2;
    else
      v8 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 16) = 3;
    memmove_0(v8, L"4.0", 6u);
    v8[3] = 0;
  }
  if ( *(_QWORD *)(a2 + 56) < 0x17u )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      a2 + 32,
      23,
      v9,
      L"UsageAndQualityInsights");
  }
  else
  {
    v10 = *v6;
    *(_QWORD *)(a2 + 48) = 23;
    memmove_0(v10, L"UsageAndQualityInsights", 0x2Eu);
    v10[23] = 0;
  }
  if ( *(_QWORD *)(a2 + 120) < 0xAu )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      a2 + 96,
      10,
      v11,
      L"MetricData");
  }
  else
  {
    v12 = *v7;
    *(_QWORD *)(a2 + 112) = 10;
    memmove_0(v12, L"MetricData", 0x14u);
    v12[10] = 0;
  }
  v14 = (_WORD **)(a2 + 128);
  if ( *(_QWORD *)(a2 + 152) < 3u )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v14,
      3,
      v13,
      L"1.0");
  }
  else
  {
    if ( *(_QWORD *)(a2 + 152) <= 7u )
      v15 = (_WORD *)(a2 + 128);
    else
      v15 = *v14;
    *(_QWORD *)(a2 + 144) = 3;
    memmove_0(v15, L"1.0", 6u);
    v15[3] = 0;
  }
  v89 = 0;
  v90 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v89, *(const void **)a3, *(_QWORD *)(a3 + 8));
  v16 = (_OWORD *)(a2 + 160);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( *(_BYTE *)(a2 + 192) )
  {
    std::wstring::operator=(v16, &v89);
  }
  else
  {
    *v16 = v89;
    *(__m128i *)(a2 + 176) = v90;
    v90 = si128;
    LOWORD(v89) = 0;
    *(_BYTE *)(a2 + 192) = 1;
  }
  std::wstring::~wstring((char **)&v89);
  ticks = _Xtime_get_ticks();
  v19 = 0;
  v74 = 0;
  v20 = operator new(0x58u);
  *v20 = v20;
  v20[1] = v20;
  v73 = v20;
  v75 = 0;
  v76 = 0;
  v77 = 7;
  v78 = 8;
  v72 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v75,
    16,
    v20);
  v21 = *a1;
  v66[0] = v21;
  v22 = a1[1];
  v67 = v22;
  if ( v21 != v22 )
  {
    while ( 1 )
    {
      v64 = *(_QWORD *)v21;
      std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v65);
      v89 = 0;
      v90 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v89, L"system::metricName", 0x12u);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        v65,
        &v81,
        &v89);
      std::wstring::~wstring((char **)&v89);
      if ( v81 == v65[0] )
      {
        v23 = v64;
      }
      else
      {
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase_unchecked(v65);
        v23 = UsageAndQualityInsights::Facts::FactKey::Rehash((UsageAndQualityInsights::Facts::FactKey *)&v64);
        v64 = v23;
      }
      v24 = 2 * (v23 & v77);
      v25 = *(_QWORD **)(v75 + 16 * (v23 & v77) + 8);
      v26 = v73;
      if ( v25 == v73 )
      {
        v25 = 0;
      }
      else
      {
        v27 = *(_QWORD **)(v75 + 8 * v24);
        while ( !(unsigned __int8)UsageAndQualityInsights::Facts::FactKey::operator==(&v64, v25 + 2) )
        {
          if ( v25 == v27 )
          {
            v25 = 0;
            break;
          }
          v25 = (_QWORD *)v25[1];
        }
        v26 = v73;
      }
      v28 = v26;
      if ( v25 )
        v28 = v25;
      if ( v28 == v26 )
        break;
LABEL_77:
      if ( *(_QWORD *)(v21 + 168) < ticks )
        ticks = *(_QWORD *)(v21 + 168);
      if ( v19 < *(_QWORD *)(v21 + 176) )
        v19 = *(_QWORD *)(v21 + 176);
      v94[0] = 0;
      v94[1] = si128;
      LOWORD(v94[0]) = 0;
      v95 = 0;
      v96 = 0;
      v97 = 0;
      v99 = 0;
      v104 = 0;
      v108 = 0;
      v110 = 0;
      v115 = 0;
      v120 = 0;
      v125 = 0;
      v130 = 0;
      v134 = 0;
      v135 = 0;
      MetricName = UsageAndQualityInsights::Facts::FactKey::GetMetricName(v21, &v89);
      std::wstring::operator=(v94, MetricName);
      std::wstring::~wstring((char **)&v89);
      if ( *(_BYTE *)(v21 + 24) )
      {
        v59 = wil::verify_hresult<long>(2147500033LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factview.cpp",
          (const char *)v59,
          (int)"Discrete metrics are not supported",
          v60);
      }
      v52 = 0;
      v53 = *(double *)(v21 + 32);
      if ( v53 >= 9.223372036854776e18 )
      {
        v53 = v53 - 9.223372036854776e18;
        if ( v53 < 9.223372036854776e18 )
          v52 = 0x8000000000000000uLL;
      }
      v98 = v52 + (unsigned int)(int)v53;
      v99 = 1;
      v100 = *(_DWORD *)((char *)&v61 + 1);
      v101 = *(_WORD *)((char *)&v61 + 5);
      v102 = HIBYTE(v61);
      Sum = UsageAndQualityInsights::Facts::FactMetric::GetSum((UsageAndQualityInsights::Facts::FactMetric *)(v21 + 24));
      v104 = 1;
      v105 = *(_DWORD *)((char *)&v61 + 1);
      v106 = *(_WORD *)((char *)&v61 + 5);
      v107 = HIBYTE(v61);
      Min = UsageAndQualityInsights::Facts::FactMetric::GetMin((UsageAndQualityInsights::Facts::FactMetric *)(v21 + 24));
      v110 = 1;
      v111 = *(_DWORD *)((char *)&v61 + 1);
      v112 = *(_WORD *)((char *)&v61 + 5);
      v113 = HIBYTE(v61);
      Max = UsageAndQualityInsights::Facts::FactMetric::GetMax((UsageAndQualityInsights::Facts::FactMetric *)(v21 + 24));
      v115 = 1;
      v116 = *(_DWORD *)((char *)&v61 + 1);
      v117 = *(_WORD *)((char *)&v61 + 5);
      v118 = HIBYTE(v61);
      v119 = *(_QWORD *)(v21 + 56);
      v120 = 1;
      v121 = *(_DWORD *)((char *)&v61 + 1);
      v122 = *(_WORD *)((char *)&v61 + 5);
      v123 = HIBYTE(v61);
      v124 = *(_QWORD *)(v21 + 48);
      v125 = 1;
      v126 = *(_DWORD *)((char *)&v61 + 1);
      v127 = *(_WORD *)((char *)&v61 + 5);
      v128 = HIBYTE(v61);
      v129 = *(_QWORD *)(v21 + 40);
      v130 = 1;
      v131 = *(_DWORD *)((char *)&v61 + 1);
      v132 = *(_WORD *)((char *)&v61 + 5);
      v133 = HIBYTE(v61);
      if ( v28[9] == v28[10] )
      {
        std::vector<UsageAndQualityInsights::Utilities::Datapoint>::_Emplace_reallocate<UsageAndQualityInsights::Utilities::Datapoint const &>(
          v28 + 8,
          v28[9],
          v94);
      }
      else
      {
        UsageAndQualityInsights::Utilities::Datapoint::Datapoint(
          (UsageAndQualityInsights::Utilities::Datapoint *)v28[9],
          (const struct UsageAndQualityInsights::Utilities::Datapoint *)v94);
        v28[9] += 336LL;
      }
      UsageAndQualityInsights::Utilities::Datapoint::~Datapoint((UsageAndQualityInsights::Utilities::Datapoint *)v94);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v65);
      v21 += 184;
      v66[0] = v21;
      if ( v21 == v22 )
        goto LABEL_89;
    }
    v69 = 0;
    v70 = 0;
    v71 = 0;
    v68 = 0;
    v29 = operator new(0x60u);
    *v29 = v29;
    v29[1] = v29;
    v29[2] = v29;
    *((_WORD *)v29 + 12) = 257;
    *(_QWORD *)&v68 = v29;
    v69 = 1;
    v30 = *(__int64 **)v65[0];
    while ( 1 )
    {
      if ( *((_BYTE *)v30 + 25) )
      {
        std::_Hash<std::_Umap_traits<UsageAndQualityInsights::Facts::FactKey,UsageAndQualityInsights::Utilities::MetricData,std::_Uhash_compare<UsageAndQualityInsights::Facts::FactKey,std::hash<UsageAndQualityInsights::Facts::FactKey>,std::equal_to<UsageAndQualityInsights::Facts::FactKey>>,std::allocator<std::pair<UsageAndQualityInsights::Facts::FactKey const,UsageAndQualityInsights::Utilities::MetricData>>,0>>::emplace<UsageAndQualityInsights::Facts::FactKey &,UsageAndQualityInsights::Utilities::MetricData>(
          (__int64)&v72,
          (__int64)v88,
          (__int64 *)&v64,
          (__int64)&v68);
        v28 = *(_QWORD **)std::_Hash<std::_Umap_traits<UsageAndQualityInsights::Facts::FactKey,UsageAndQualityInsights::Utilities::MetricData,std::_Uhash_compare<UsageAndQualityInsights::Facts::FactKey,std::hash<UsageAndQualityInsights::Facts::FactKey>,std::equal_to<UsageAndQualityInsights::Facts::FactKey>>,std::allocator<std::pair<UsageAndQualityInsights::Facts::FactKey const,UsageAndQualityInsights::Utilities::MetricData>>,0>>::find(
                            &v72,
                            v86,
                            &v64);
        std::vector<UsageAndQualityInsights::Utilities::Datapoint>::_Tidy(&v70);
        if ( v69 )
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v68);
        v22 = v67;
        v21 = v66[0];
        goto LABEL_77;
      }
      v31 = v30 + 4;
      v32 = (unsigned __int64)v30[7] <= 7 ? (const wchar_t *)(v30 + 4) : (const wchar_t *)*v31;
      if ( (unsigned __int64)v30[6] >= 0xA && !wmemcmp(v32, L"enriched::", 0xAu) )
        break;
      std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
        (__int64)&v68,
        &v89,
        (__int64)(v30 + 4));
      v44 = v90.m128i_i64[0];
      if ( std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::FactDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>>,0>>::_Lower_bound_duplicate<std::wstring>(
             v45,
             v90.m128i_i64[0],
             (__int64)(v30 + 4)) )
      {
        std::wstring::operator=(v44 + 64, v30 + 8);
      }
      else
      {
        if ( *((_QWORD *)&v68 + 1) == 0x2AAAAAAAAAAAAAALL )
          std::_Throw_tree_length_error();
        v46 = v68;
        v79 = &v68;
        v80 = 0;
        v47 = operator new(0x60u);
        v80 = v47;
        v66[1] = v47 + 4;
        std::wstring::wstring((__int64)(v47 + 4), (__int64)(v30 + 4));
        std::wstring::wstring((__int64)(v47 + 8), (__int64)(v30 + 8));
        *v47 = v46;
        v47[1] = v46;
        v47[2] = v46;
        *((_WORD *)v47 + 12) = 0;
        v80 = 0;
        std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>((__int64)&v79);
        *(_OWORD *)&v66[1] = v89;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(
          &v68,
          &v66[1],
          v47);
      }
LABEL_65:
      v48 = (__int64 **)v30[2];
      if ( *((_BYTE *)v48 + 25) )
      {
        for ( i = (__int64 *)v30[1]; !*((_BYTE *)i + 25) && v30 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v30 = i;
        v30 = i;
      }
      else
      {
        v30 = (__int64 *)v30[2];
        for ( j = *v48; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v30 = j;
      }
    }
    if ( (unsigned __int64)v30[7] <= 7 )
      v34 = (__int64)(v30 + 4);
    else
      v34 = *v31;
    v63 = v34;
    v35 = v30[6];
    if ( v35 < 2 || v35 - 2 < v33 )
    {
      v38 = -1;
    }
    else
    {
      v36 = v34 + 2 * v35;
      v37 = _std_search_2(v34 + 20, v36, L"::", 2);
      v34 = v63;
      if ( v37 == v36 )
      {
        v39 = 1;
LABEL_54:
        v40 = -1;
        if ( v35 - v39 != -1 )
          v40 = v35 - v39;
        v66[1] = v34 + 2 * v39;
        v41 = 10;
        if ( v35 < 0xA )
          v41 = v35;
        v82 = v41;
        v42 = (std::_Format_arg_index *)&v89;
        v43 = 2;
        do
        {
          std::_Format_arg_index::_Format_arg_index(v42);
          v42 = (std::_Format_arg_index *)((char *)v42 + 8);
          --v43;
        }
        while ( v43 );
        v90.m128i_i64[0] = v63;
        v90.m128i_i64[1] = v82;
        *(_QWORD *)&v89 = 0xC000000000000000uLL;
        v91 = v66[1];
        v92 = v40;
        *((_QWORD *)&v89 + 1) = 0xC000000000000010uLL;
        v83 = 2;
        v84 = &v89;
        v61 = 4;
        std::vformat<0>(Src);
        v62 |= 6u;
        std::map<std::wstring,std::wstring>::insert_or_assign<std::wstring const &>(&v68, v87, Src, v30 + 8);
        std::wstring::~wstring(Src);
        goto LABEL_65;
      }
      v38 = (v37 - v63) >> 1;
    }
    v39 = v38 + 2;
    if ( v35 < v38 + 2 )
      std::wstring_view::_Xran(v34);
    goto LABEL_54;
  }
LABEL_89:
  v66[1] = v74;
  if ( v74 > 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a2 + 256) - *(_QWORD *)(a2 + 240)) >> 4) )
  {
    if ( v74 > 0x555555555555555LL )
      std::vector<std::pair<std::string_view,std::string_view>>::_Xlength(v74, 0xAAAAAAAAAAAAAAABuLL);
    std::vector<UsageAndQualityInsights::Utilities::MetricData>::_Reallocate<0>(a2 + 240, &v66[1]);
  }
  v54 = v73;
  for ( k = (_QWORD *)*v73; k != v54; k = (_QWORD *)*k )
  {
    if ( *(_QWORD *)(a2 + 248) == *(_QWORD *)(a2 + 256) )
    {
      std::vector<UsageAndQualityInsights::Utilities::MetricData>::_Emplace_reallocate<UsageAndQualityInsights::Utilities::MetricData const>(
        a2 + 240,
        *(_QWORD *)(a2 + 248),
        k + 5);
    }
    else
    {
      UsageAndQualityInsights::Utilities::MetricData::MetricData(
        *(UsageAndQualityInsights::Utilities::MetricData **)(a2 + 248),
        (const struct UsageAndQualityInsights::Utilities::MetricData *)(k + 5));
      *(_QWORD *)(a2 + 248) += 48LL;
    }
  }
  v56 = UsageAndQualityInsights::Utilities::TimePointToIso8601((wchar_t *)Src);
  std::wstring::operator=(a2 + 64, v56);
  std::wstring::~wstring(Src);
  v57 = UsageAndQualityInsights::Utilities::TimePointToIso8601((wchar_t *)Src);
  std::optional<std::wstring>::operator=<std::wstring,0>(a2 + 200, v57);
  std::wstring::~wstring(Src);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>(&v75);
  std::list<std::pair<UsageAndQualityInsights::Facts::FactKey const,UsageAndQualityInsights::Utilities::MetricData>>::~list<std::pair<UsageAndQualityInsights::Facts::FactKey const,UsageAndQualityInsights::Utilities::MetricData>>(&v73);
  return a2;
}

```

## disassembly

```asm
0x1800f92c8  mov     rax, rsp
0x1800f92cb  mov     [rax+20h], rbx
0x1800f92cf  push    rbp
0x1800f92d0  push    rsi
0x1800f92d1  push    rdi
0x1800f92d2  push    r12
0x1800f92d4  push    r13
0x1800f92d6  push    r14
0x1800f92d8  push    r15
0x1800f92da  lea     rbp, [rax-278h]
0x1800f92e1  sub     rsp, 340h
0x1800f92e8  movaps  xmmword ptr [rax-48h], xmm6
0x1800f92ec  movaps  xmmword ptr [rax-58h], xmm7
0x1800f92f0  mov     rax, cs:__security_cookie
0x1800f92f7  xor     rax, rsp
0x1800f92fa  mov     [rbp+270h+var_60], rax
0x1800f9301  mov     r14, r8
0x1800f9304  mov     r12, rdx
0x1800f9307  mov     r15, rcx
0x1800f930a  mov     [rbp+270h+var_240], rdx
0x1800f930e  xor     r13d, r13d
0x1800f9311  mov     dword ptr [rsp+370h+var_330], r13d
0x1800f9316  xorps   xmm0, xmm0
0x1800f9319  movups  xmmword ptr [rdx], xmm0
0x1800f931c  mov     [rdx+10h], r13
0x1800f9320  lea     edx, [r13+7]
0x1800f9324  mov     [r12+18h], rdx
0x1800f9329  mov     [r12], r13w
0x1800f932e  lea     rsi, [r12+20h]
0x1800f9333  movups  xmmword ptr [rsi], xmm0
0x1800f9336  mov     [rsi+10h], r13
0x1800f933a  mov     [rsi+18h], rdx
0x1800f933e  mov     [rsi], r13w
0x1800f9342  movups  xmmword ptr [r12+40h], xmm0
0x1800f9348  mov     [r12+50h], r13
0x1800f934d  mov     [r12+58h], rdx
0x1800f9352  mov     [r12+40h], r13w
0x1800f9358  lea     rdi, [r12+60h]
0x1800f935d  movups  xmmword ptr [rdi], xmm0
0x1800f9360  mov     [rdi+10h], r13
0x1800f9364  mov     [rdi+18h], rdx
0x1800f9368  mov     [rdi], r13w
0x1800f936c  movups  xmmword ptr [rdi+20h], xmm0
0x1800f9370  mov     [rdi+30h], r13
0x1800f9374  mov     [rdi+38h], rdx
0x1800f9378  mov     [rdi+20h], r13w
0x1800f937d  mov     [rdi+60h], r13b
0x1800f9381  mov     [rdi+88h], r13b
0x1800f9388  mov     [rdi+90h], r13
0x1800f938f  mov     [rdi+98h], r13
0x1800f9396  mov     [rdi+0A0h], r13
0x1800f939d  mov     dword ptr [rsp+370h+var_330], 1
0x1800f93a5  lea     eax, [rdx-4]
0x1800f93a8  cmp     [r12+18h], rax
0x1800f93ad  jb      short loc_1800F93E0
0x1800f93af  cmp     [r12+18h], rdx
0x1800f93b4  jbe     short loc_1800F93BC
0x1800f93b6  mov     rbx, [r12]
0x1800f93ba  jmp     short loc_1800F93BF
0x1800f93bc  mov     rbx, r12
0x1800f93bf  mov     [r12+10h], rax
0x1800f93c4  mov     r8d, 6; Size
0x1800f93ca  lea     rdx, a40; "4.0"
0x1800f93d1  mov     rcx, rbx; void *
0x1800f93d4  call    memmove_0
0x1800f93d9  mov     [rbx+6], r13w
0x1800f93de  jmp     short loc_1800F93F2
0x1800f93e0  lea     r9, a40; "4.0"
0x1800f93e7  mov     rdx, rax
0x1800f93ea  mov     rcx, r12
0x1800f93ed  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800f93f2  mov     edx, 17h
0x1800f93f7  cmp     [rsi+18h], rdx
0x1800f93fb  jb      short loc_1800F941E
0x1800f93fd  mov     rbx, [rsi]
0x1800f9400  mov     [rsi+10h], rdx
0x1800f9404  lea     r8d, [rdx+17h]; Size
0x1800f9408  lea     rdx, aUsageandqualit_3; "UsageAndQualityInsights"
0x1800f940f  mov     rcx, rbx; void *
0x1800f9412  call    memmove_0
0x1800f9417  mov     [rbx+2Eh], r13w
0x1800f941c  jmp     short loc_1800F942D
0x1800f941e  lea     r9, aUsageandqualit_3; "UsageAndQualityInsights"
0x1800f9425  mov     rcx, rsi
0x1800f9428  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800f942d  mov     eax, 0Ah
0x1800f9432  cmp     [rdi+18h], rax
0x1800f9436  jb      short loc_1800F9459
0x1800f9438  mov     rbx, [rdi]
0x1800f943b  mov     [rdi+10h], rax
0x1800f943f  lea     r8d, [rax+0Ah]; Size
0x1800f9443  lea     rdx, aMetricdata; "MetricData"
0x1800f944a  mov     rcx, rbx; void *
0x1800f944d  call    memmove_0
0x1800f9452  mov     [rbx+14h], r13w
0x1800f9457  jmp     short loc_1800F946B
0x1800f9459  lea     r9, aMetricdata; "MetricData"
0x1800f9460  mov     rdx, rax
0x1800f9463  mov     rcx, rdi
0x1800f9466  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800f946b  lea     rcx, [r12+80h]
0x1800f9473  mov     edx, 3
0x1800f9478  cmp     [rcx+18h], rdx
0x1800f947c  jb      short loc_1800F94AD
0x1800f947e  cmp     qword ptr [rcx+18h], 7
0x1800f9483  jbe     short loc_1800F948A
0x1800f9485  mov     rbx, [rcx]
0x1800f9488  jmp     short loc_1800F948D
0x1800f948a  mov     rbx, rcx
0x1800f948d  mov     [rcx+10h], rdx
0x1800f9491  mov     r8d, 6; Size
0x1800f9497  lea     rdx, a10; "1.0"
0x1800f949e  mov     rcx, rbx; void *
0x1800f94a1  call    memmove_0
0x1800f94a6  mov     [rbx+6], r13w
0x1800f94ab  jmp     short loc_1800F94B9
0x1800f94ad  lea     r9, a10; "1.0"
0x1800f94b4  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800f94b9  xorps   xmm0, xmm0
0x1800f94bc  movups  [rbp+270h+var_208], xmm0
0x1800f94c0  xorps   xmm1, xmm1
0x1800f94c3  movdqu  [rbp+270h+var_1F8], xmm1
0x1800f94c8  mov     r8, [r14+8]
0x1800f94cc  mov     rdx, [r14]
0x1800f94cf  lea     rcx, [rbp+270h+var_208]
0x1800f94d3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f94d8  lea     rcx, [r12+0A0h]
0x1800f94e0  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x1800f94e8  cmp     [rcx+20h], r13b
0x1800f94ec  jz      short loc_1800F94F9
0x1800f94ee  lea     rdx, [rbp+270h+var_208]
0x1800f94f2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f94f7  jmp     short loc_1800F9516
0x1800f94f9  movups  xmm0, [rbp+270h+var_208]
0x1800f94fd  movups  xmmword ptr [rcx], xmm0
0x1800f9500  movups  xmm1, [rbp+270h+var_1F8]
0x1800f9504  movups  xmmword ptr [rcx+10h], xmm1
0x1800f9508  movdqu  [rbp+270h+var_1F8], xmm7
0x1800f950d  mov     word ptr [rbp+270h+var_208], r13w
0x1800f9512  mov     byte ptr [rcx+20h], 1
0x1800f9516  lea     rcx, [rbp+270h+var_208]; void *
0x1800f951a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f951f  call    cs:__imp__Xtime_get_ticks
0x1800f9525  mov     r14, rax
0x1800f9528  mov     rsi, r13
0x1800f952b  mov     [rbp+270h+var_2B0], r13d
0x1800f952f  mov     [rbp+270h+var_2A8], r13
0x1800f9533  mov     [rbp+270h+var_2A0], r13
0x1800f9537  mov     ecx, 58h ; 'X'; Size
0x1800f953c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9541  mov     [rax], rax
0x1800f9544  mov     [rax+8], rax
0x1800f9548  mov     [rbp+270h+var_2A8], rax
0x1800f954c  mov     [rbp+270h+var_298], r13
0x1800f9550  xorps   xmm0, xmm0
0x1800f9553  movdqa  [rbp+270h+var_290], xmm0
0x1800f9558  mov     [rbp+270h+var_280], 7
0x1800f9560  mov     [rbp+270h+var_278], 8
0x1800f9568  mov     [rbp+270h+var_2B0], 3F800000h
0x1800f956f  mov     r8, rax
0x1800f9572  mov     edx, 10h
0x1800f9577  lea     rcx, [rbp+270h+var_298]
0x1800f957b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800f9580  nop
0x1800f9581  mov     r13, [r15]
0x1800f9584  mov     qword ptr [rsp+370h+var_308], r13
0x1800f9589  mov     r15, [r15+8]
0x1800f958d  mov     [rbp+270h+var_2F0], r15
0x1800f9591  cmp     r13, r15
0x1800f9594  jz      loc_1800F9C7F
0x1800f959a  movsd   xmm6, cs:__real@43e0000000000000
0x1800f95a2  mov     rax, [r13+0]
0x1800f95a6  mov     [rsp+370h+var_320], rax
0x1800f95ab  lea     rdx, [r13+8]
0x1800f95af  lea     rcx, [rsp+370h+var_318]
0x1800f95b4  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(std::map<std::wstring,std::wstring> const &)
0x1800f95b9  nop
0x1800f95ba  xorps   xmm0, xmm0
0x1800f95bd  movups  [rbp+270h+var_208], xmm0
0x1800f95c1  xorps   xmm1, xmm1
0x1800f95c4  movdqu  [rbp+270h+var_1F8], xmm1
0x1800f95c9  mov     r8d, 12h
0x1800f95cf  lea     rdx, aSystemMetricna; "system::metricName"
0x1800f95d6  lea     rcx, [rbp+270h+var_208]
0x1800f95da  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800f95df  lea     r8, [rbp+270h+var_208]
0x1800f95e3  lea     rdx, [rbp+270h+var_260]
0x1800f95e7  lea     rcx, [rsp+370h+var_318]
0x1800f95ec  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800f95f1  lea     rcx, [rbp+270h+var_208]; void *
0x1800f95f5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f95fa  mov     rdx, [rbp+270h+var_260]
0x1800f95fe  cmp     rdx, [rsp+370h+var_318]
0x1800f9603  jz      short loc_1800F9623
0x1800f9605  lea     rcx, [rsp+370h+var_318]
0x1800f960a  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>)
0x1800f960f  lea     rcx, [rsp+370h+var_320]; this
0x1800f9614  call    ?Rehash@FactKey@Facts@UsageAndQualityInsights@@AEBA_KXZ; UsageAndQualityInsights::Facts::FactKey::Rehash(void)
0x1800f9619  mov     rcx, rax
0x1800f961c  mov     [rsp+370h+var_320], rax
0x1800f9621  jmp     short loc_1800F9628
0x1800f9623  mov     rcx, [rsp+370h+var_320]
0x1800f9628  mov     rax, [rbp+270h+var_280]
0x1800f962c  and     rax, rcx
0x1800f962f  add     rax, rax
0x1800f9632  mov     rdx, [rbp+270h+var_298]
0x1800f9636  mov     rdi, [rdx+rax*8+8]
0x1800f963b  mov     rcx, [rbp+270h+var_2A8]
0x1800f963f  cmp     rdi, rcx
0x1800f9642  jnz     short loc_1800F964A
0x1800f9644  xor     edx, edx
0x1800f9646  mov     edi, edx
0x1800f9648  jmp     short loc_1800F9674
0x1800f964a  mov     rbx, [rdx+rax*8]
0x1800f964e  lea     rdx, [rdi+10h]
0x1800f9652  lea     rcx, [rsp+370h+var_320]
0x1800f9657  call    ??8FactKey@Facts@UsageAndQualityInsights@@QEBA_NAEBV012@@Z; UsageAndQualityInsights::Facts::FactKey::operator==(UsageAndQualityInsights::Facts::FactKey const &)
0x1800f965c  xor     edx, edx
0x1800f965e  test    al, al
0x1800f9660  jnz     short loc_1800F9670
0x1800f9662  cmp     rdi, rbx
0x1800f9665  jz      short loc_1800F966D
0x1800f9667  mov     rdi, [rdi+8]
0x1800f966b  jmp     short loc_1800F964E
0x1800f966d  mov     rdi, rdx
0x1800f9670  mov     rcx, [rbp+270h+var_2A8]
0x1800f9674  mov     rbx, rcx
0x1800f9677  test    rdi, rdi
0x1800f967a  cmovnz  rbx, rdi
0x1800f967e  cmp     rbx, rcx
0x1800f9681  jnz     loc_1800F99D1
0x1800f9687  mov     [rbp+270h+var_2D8], dl
0x1800f968a  xorps   xmm0, xmm0
0x1800f968d  movdqu  [rbp+270h+var_2D0], xmm0
0x1800f9692  mov     [rbp+270h+var_2C0], rdx
0x1800f9696  movdqu  [rbp+270h+var_2E8], xmm0
0x1800f969b  mov     ecx, 60h ; '`'; Size
0x1800f96a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f96a5  mov     [rax], rax
0x1800f96a8  mov     [rax+8], rax
0x1800f96ac  mov     [rax+10h], rax
0x1800f96b0  mov     word ptr [rax+18h], 101h
0x1800f96b6  mov     qword ptr [rbp+270h+var_2E8], rax
0x1800f96ba  mov     [rbp+270h+var_2D8], 1
0x1800f96be  mov     rbx, [rsp+370h+var_318]
0x1800f96c3  mov     rbx, [rbx]
0x1800f96c6  xor     edi, edi
0x1800f96c8  cmp     [rbx+19h], dil
0x1800f96cc  jnz     loc_1800F9982
0x1800f96d2  lea     r13, [rbx+20h]
0x1800f96d6  cmp     qword ptr [rbx+38h], 7
0x1800f96db  jbe     short loc_1800F96E3
0x1800f96dd  mov     rcx, [r13+0]
0x1800f96e1  jmp     short loc_1800F96E6
0x1800f96e3  mov     rcx, r13; S1
0x1800f96e6  cmp     qword ptr [rbx+30h], 0Ah
0x1800f96eb  jb      loc_1800F986E
0x1800f96f1  mov     r8d, 0Ah; N
0x1800f96f7  lea     rdx, aEnriched; "enriched::"
0x1800f96fe  call    wmemcmp
0x1800f9703  test    eax, eax
0x1800f9705  jnz     loc_1800F986E
0x1800f970b  cmp     qword ptr [r13+18h], 7
0x1800f9710  jbe     short loc_1800F9718
0x1800f9712  mov     rcx, [r13+0]
0x1800f9716  jmp     short loc_1800F971B
0x1800f9718  mov     rcx, r13
0x1800f971b  mov     [rsp+370h+var_328], rcx
0x1800f9720  mov     r15, [r13+10h]
0x1800f9724  cmp     r15, 2
0x1800f9728  jb      short loc_1800F9769
0x1800f972a  lea     rax, [r15-2]
0x1800f972e  cmp     rax, r8
0x1800f9731  jb      short loc_1800F9769
0x1800f9733  lea     rdi, [rcx+r15*2]
0x1800f9737  add     rcx, 14h
0x1800f973b  mov     r9d, 2
0x1800f9741  lea     r8, asc_18014281C; "::"
0x1800f9748  mov     rdx, rdi
0x1800f974b  call    __std_search_2
0x1800f9750  mov     rcx, [rsp+370h+var_328]
0x1800f9755  cmp     rax, rdi
0x1800f9758  jz      short loc_1800F9762
0x1800f975a  sub     rax, rcx
0x1800f975d  sar     rax, 1
0x1800f9760  jmp     short loc_1800F976D
0x1800f9762  mov     edx, 1
0x1800f9767  jmp     short loc_1800F977A
0x1800f9769  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f976d  lea     rdx, [rax+2]
0x1800f9771  cmp     r15, rdx
0x1800f9774  jb      loc_1800F9DDF
0x1800f977a  mov     rax, r15
0x1800f977d  sub     rax, rdx
0x1800f9780  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800f9784  cmp     rax, r13
0x1800f9787  cmovb   r13, rax
0x1800f978b  lea     rax, [rcx+rdx*2]
0x1800f978f  mov     qword ptr [rsp+370h+var_308+8], rax
0x1800f9794  mov     eax, 0Ah
  ... truncated ...
```
