# UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetTelemetryEndpointConfigs(void)

- ea: `0x1800eb40c`
- end: `0x1800ec2a6`
- name: `?GetTelemetryEndpointConfigs@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@QEBA?AV?$vector@UTelemetryEndpointConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UTelemetryEndpointConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@XZ`
- size: `3738`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180015930`
- `0x1800f5a1c`

## callees

- `0x1800033d0`
- `0x1800033f4`
- `0x180005e7c`
- `0x18000d8fc`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180012054`
- `0x18001219c`
- `0x180012dd4`
- `0x18001394c`
- `0x1800149bc`
- `0x180016b2c`
- `0x180016d2c`
- `0x180019458`
- `0x180019b64`
- `0x18001a434`
- `0x18001a8f4`
- `0x180020650`
- `0x180026730`
- `0x180027ba4`
- `0x18003b50c`
- `0x1800e905c`
- `0x1800e9550`
- `0x1800e989c`
- `0x1800e9b44`
- `0x1800e9f38`
- `0x1800ea0d8`
- `0x1800ea540`
- `0x1800eb40c`
- `0x1800ec5e0`
- `0x1800fdc68`
- `0x180100b04`
- `0x180100b74`

## string_xrefs

- `0x1800eba5f`: `overwrite::PartA_Ext_App_ExpId`
- `0x1800eb865`: `overwrite::PartA_Ext_App_UserId`
- `0x1800eb74a`: `overwrite::PartA_Ext_Os_BootId`
- `0x1800eb543`: `onecore\base\usageandqualityinsights\service\lib\configuration\compileduqiconfig.cpp`
- `0x1800ec294`: `onecore\base\usageandqualityinsights\service\lib\configuration\compileduqiconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
_QWORD *__fastcall UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetTelemetryEndpointConfigs(
        __int64 **a1,
        _QWORD *a2)
{
  __int64 *v3; // r14
  __m128i si128; // xmm6
  __int64 *v5; // rbx
  __int64 *v6; // rax
  __int64 *v7; // r15
  _DWORD *v8; // rdi
  _DWORD *v9; // rcx
  __int64 v10; // rdi
  unsigned __int64 v11; // r13
  const wchar_t *v12; // rdx
  unsigned __int64 v13; // rsi
  const wchar_t *v14; // rcx
  size_t v15; // r8
  int v16; // eax
  _WORD *v17; // r9
  unsigned int v18; // r8d
  unsigned __int64 v19; // r8
  _OWORD *v20; // rcx
  wchar_t *v21; // r13
  int v22; // esi
  __m128i *v23; // rdx
  __m128i *v24; // rdx
  __m128i *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // rsi
  __int64 v30; // r13
  __int64 v31; // rdx
  wchar_t **v32; // rsi
  wchar_t *v33; // rdx
  __int64 v34; // r8
  wchar_t **v35; // rsi
  wchar_t *v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r13
  __int64 i; // rsi
  __int64 v43; // r13
  __int64 j; // rsi
  __int64 v45; // rdx
  __int64 *v46; // rax
  __int64 EnrichedDimensionKey; // rax
  _QWORD *v48; // rdi
  _QWORD *v49; // rsi
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  __int64 *v52; // rax
  int v53; // esi
  __int64 v54; // rcx
  unsigned int v55; // edi
  __int64 **v56; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  unsigned int v60; // eax
  int v61; // [rsp+28h] [rbp-E0h]
  const char *v62; // [rsp+30h] [rbp-D8h]
  const char *v63[3]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v64; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v65[3]; // [rsp+58h] [rbp-B0h] BYREF
  _DWORD *v66; // [rsp+70h] [rbp-98h]
  __int64 *v67; // [rsp+78h] [rbp-90h]
  _QWORD v68[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v69[11]; // [rsp+98h] [rbp-70h] BYREF
  char v70[16]; // [rsp+F0h] [rbp-18h] BYREF
  char v71[16]; // [rsp+100h] [rbp-8h] BYREF
  char v72[16]; // [rsp+110h] [rbp+8h] BYREF
  char v73[16]; // [rsp+120h] [rbp+18h] BYREF
  char v74[16]; // [rsp+130h] [rbp+28h] BYREF
  __int64 Src; // [rsp+140h] [rbp+38h] BYREF
  __int64 v76; // [rsp+148h] [rbp+40h] BYREF
  __int64 v77; // [rsp+150h] [rbp+48h]
  __m128i v78; // [rsp+158h] [rbp+50h]
  __int128 v79; // [rsp+168h] [rbp+60h] BYREF
  __int128 v80; // [rsp+178h] [rbp+70h] BYREF
  __int128 v81; // [rsp+188h] [rbp+80h]
  __int128 v82; // [rsp+198h] [rbp+90h] BYREF
  __int64 v83; // [rsp+1A8h] [rbp+A0h]
  char v84; // [rsp+1B0h] [rbp+A8h]
  unsigned int v85; // [rsp+1B4h] [rbp+ACh]
  int v86; // [rsp+1B8h] [rbp+B0h]
  __int128 v87; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v88; // [rsp+1D0h] [rbp+C8h]
  __int64 v89; // [rsp+1D8h] [rbp+D0h]
  __int128 v90; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v91; // [rsp+1F0h] [rbp+E8h]
  __int64 v92; // [rsp+1F8h] [rbp+F0h]
  int v93; // [rsp+200h] [rbp+F8h]
  int v94; // [rsp+204h] [rbp+FCh]
  __int64 v95; // [rsp+208h] [rbp+100h]
  __int128 v96; // [rsp+218h] [rbp+110h] BYREF
  __m128i v97; // [rsp+228h] [rbp+120h]
  _OWORD v98[2]; // [rsp+238h] [rbp+130h] BYREF
  _OWORD v99[2]; // [rsp+258h] [rbp+150h] BYREF
  _OWORD v100[2]; // [rsp+278h] [rbp+170h] BYREF
  _OWORD v101[2]; // [rsp+298h] [rbp+190h] BYREF
  _OWORD v102[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _OWORD v103[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _OWORD v104[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _OWORD v105[2]; // [rsp+318h] [rbp+210h] BYREF
  _OWORD v106[2]; // [rsp+338h] [rbp+230h] BYREF
  _OWORD v107[2]; // [rsp+358h] [rbp+250h] BYREF
  _OWORD v108[2]; // [rsp+378h] [rbp+270h] BYREF
  _OWORD v109[2]; // [rsp+398h] [rbp+290h] BYREF
  _OWORD v110[2]; // [rsp+3B8h] [rbp+2B0h] BYREF
  _OWORD v111[2]; // [rsp+3D8h] [rbp+2D0h] BYREF
  _OWORD v112[2]; // [rsp+3F8h] [rbp+2F0h] BYREF
  _OWORD v113[2]; // [rsp+418h] [rbp+310h] BYREF
  _OWORD v114[2]; // [rsp+438h] [rbp+330h] BYREF
  _OWORD v115[2]; // [rsp+458h] [rbp+350h] BYREF
  _OWORD v116[2]; // [rsp+478h] [rbp+370h] BYREF
  __int128 v117; // [rsp+498h] [rbp+390h] BYREF
  __m128i v118; // [rsp+4A8h] [rbp+3A0h]
  _BYTE v119[6]; // [rsp+4C2h] [rbp+3BAh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+520h] [rbp+418h]

  v69[10] = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  LODWORD(v63[0]) = 1;
  v3 = *a1;
  v67 = a1[1];
  if ( v3 != v67 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v5 = *(__int64 **)v3[7];
      while ( 1 )
      {
        v6 = v3 + 5;
        if ( *((_BYTE *)v5 + 25) )
          break;
        v7 = v5 + 8;
        v8 = (_DWORD *)v5[20];
        v9 = (_DWORD *)v5[21];
        v66 = v9;
        while ( 1 )
        {
          v65[0] = v8;
          if ( v8 == v9 )
            break;
          if ( *v8 )
            goto LABEL_101;
          std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
            v6,
            &v117,
            v7);
          v10 = v118.m128i_i64[0];
          if ( *(_BYTE *)(v118.m128i_i64[0] + 25) )
          {
LABEL_19:
            v10 = v3[5];
            goto LABEL_20;
          }
          v11 = *(_QWORD *)(v118.m128i_i64[0] + 48);
          v12 = (const wchar_t *)(v118.m128i_i64[0] + 32);
          if ( *(_QWORD *)(v118.m128i_i64[0] + 56) > 7u )
            v12 = *(const wchar_t **)v12;
          v13 = v7[2];
          if ( (unsigned __int64)v7[3] <= 7 )
            v14 = (const wchar_t *)v7;
          else
            v14 = (const wchar_t *)*v7;
          v15 = v7[2];
          if ( v11 < v13 )
            v15 = *(_QWORD *)(v118.m128i_i64[0] + 48);
          v16 = wmemcmp(v14, v12, v15);
          if ( v16 )
          {
            if ( v16 < 0 )
              goto LABEL_19;
          }
          else if ( v13 < v11 )
          {
            goto LABEL_19;
          }
LABEL_20:
          LOBYTE(v61) = v10 == v3[5];
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\compileduqiconfig.cpp",
            (const char *)0x80070057LL,
            v61,
            (bool)"Missing fact definition for source fact",
            v63[0]);
          v79 = 0;
          v80 = 0;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          v87 = 0;
          v88 = 0;
          v89 = 7;
          LOWORD(v87) = 0;
          v90 = 0;
          v91 = 0;
          v92 = 7;
          LOWORD(v90) = 0;
          std::wstring::operator=(&v87, v5 + 4);
          v17 = v119;
          v18 = *((_DWORD *)v3 + 8);
          do
          {
            *--v17 = v18 % 0xA + 48;
            v18 /= 0xAu;
          }
          while ( v18 );
          std::wstring::wstring(&Src, v17, v119);
          LODWORD(v63[0]) |= 6u;
          std::wstring::operator=(&v90, &Src);
          std::wstring::~wstring(&Src);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
          {
            memset(v101, 0, sizeof(v101));
            std::wstring::_Construct<1,wchar_t const *>(v101, L"system::partA__app__is1P", 24);
            memset(v102, 0, sizeof(v102));
            std::wstring::_Construct<1,wchar_t const *>(v102, L"overwrite::PartA_Ext_Os_BootId", 30);
            memset(v103, 0, sizeof(v103));
            std::wstring::_Construct<1,wchar_t const *>(v103, L"system::partA__privacy__isRequired", 34);
            memset(v104, 0, sizeof(v104));
            std::wstring::_Construct<1,wchar_t const *>(v104, L"system::partA__utc__shellId", 27);
            memset(v105, 0, sizeof(v105));
            std::wstring::_Construct<1,wchar_t const *>(v105, L"system::partA__metadata__policies", 33);
            memset(v106, 0, sizeof(v106));
            std::wstring::_Construct<1,wchar_t const *>(v106, L"system::partA__os__ver", 22);
            memset(v107, 0, sizeof(v107));
            std::wstring::_Construct<1,wchar_t const *>(v107, L"system::hourTimeBin", 19);
            memset(v108, 0, sizeof(v108));
            std::wstring::_Construct<1,wchar_t const *>(v108, L"overwrite::PartA_Ext_App_UserId", 31);
            memset(v109, 0, sizeof(v109));
            std::wstring::_Construct<1,wchar_t const *>(v109, L"system::optIn", 13);
            memset(v110, 0, sizeof(v110));
            std::wstring::_Construct<1,wchar_t const *>(v110, L"system::poEnabled", 17);
            memset(v111, 0, sizeof(v111));
            std::wstring::_Construct<1,wchar_t const *>(v111, L"system::dayTimeBin", 18);
            memset(v112, 0, sizeof(v112));
            std::wstring::_Construct<1,wchar_t const *>(v112, L"system::factSource", 18);
            memset(v113, 0, sizeof(v113));
            std::wstring::_Construct<1,wchar_t const *>(v113, L"system::factName", 16);
            memset(v114, 0, sizeof(v114));
            std::wstring::_Construct<1,wchar_t const *>(v114, L"system::factTime", 16);
            memset(v115, 0, sizeof(v115));
            std::wstring::_Construct<1,wchar_t const *>(v115, L"system::metricName", 18);
            memset(v116, 0, sizeof(v116));
            std::wstring::_Construct<1,wchar_t const *>(v116, L"system::window_type", 19);
            v69[0] = v101;
            v69[1] = &v117;
            std::vector<std::wstring>::operator=((char *)&v80 + 8, v69);
            v19 = 16;
            v20 = v101;
          }
          else
          {
            memset(v98, 0, sizeof(v98));
            std::wstring::_Construct<1,wchar_t const *>(v98, L"system::factSource", 18);
            memset(v99, 0, sizeof(v99));
            std::wstring::_Construct<1,wchar_t const *>(v99, L"system::metricName", 18);
            memset(v100, 0, sizeof(v100));
            std::wstring::_Construct<1,wchar_t const *>(v100, L"system::window_type", 19);
            v68[0] = v98;
            v68[1] = v101;
            std::vector<std::wstring>::operator=((char *)&v80 + 8, v68);
            v19 = 3;
            v20 = v98;
          }
          `eh vector destructor iterator'(v20, 0x20u, v19, std::wstring::~wstring);
          v21 = (wchar_t *)(v7 + 7);
          v22 = (unsigned __int8)StringToAggregationWindowType((wchar_t *)v7 + 28);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57896588>::GetImpl'::`2'::impl) )
          {
            v96 = 0;
            v97 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v96, L"overwrite::PartA_Ext_App_ExpId", 30);
            v23 = (__m128i *)v81;
            if ( (_QWORD)v81 == *((_QWORD *)&v81 + 1) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)&v80 + 8, v81, &v96);
            }
            else
            {
              *(_OWORD *)v81 = v96;
              v23[1] = v97;
              v97 = si128;
              LOWORD(v96) = 0;
              *(_QWORD *)&v81 = v81 + 32;
            }
            std::wstring::~wstring(&v96);
            v117 = 0;
            v118 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v117, L"system::triggeredFlightIds", 26);
            v24 = (__m128i *)v81;
            if ( (_QWORD)v81 == *((_QWORD *)&v81 + 1) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)&v80 + 8, v81, &v117);
            }
            else
            {
              *(_OWORD *)v81 = v117;
              v24[1] = v118;
              v118 = si128;
              LOWORD(v117) = 0;
              *(_QWORD *)&v81 = v81 + 32;
            }
            std::wstring::~wstring(&v117);
          }
          v117 = 0;
          v118 = 0;
          if ( v22 )
          {
            std::wstring::_Construct<1,wchar_t const *>(&v117, L"system::dayTimeBin", 18);
            v25 = (__m128i *)v81;
            if ( (_QWORD)v81 != *((_QWORD *)&v81 + 1) )
              goto LABEL_37;
          }
          else
          {
            std::wstring::_Construct<1,wchar_t const *>(&v117, L"system::hourTimeBin", 19);
            v25 = (__m128i *)v81;
            if ( (_QWORD)v81 != *((_QWORD *)&v81 + 1) )
            {
LABEL_37:
              *(_OWORD *)v81 = v117;
              v25[1] = v118;
              v118 = si128;
              LOWORD(v117) = 0;
              *(_QWORD *)&v81 = v81 + 32;
              goto LABEL_39;
            }
          }
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)&v80 + 8, v25, &v117);
LABEL_39:
          std::wstring::~wstring(&v117);
          *(_OWORD *)&v65[1] = 0;
          v26 = std::_Allocate<16,std::_Default_allocate_traits>(64);
          *(_QWORD *)v26 = v26;
          *(_QWORD *)(v26 + 8) = v26;
          *(_QWORD *)(v26 + 16) = v26;
          *(_WORD *)(v26 + 24) = 257;
          v65[1] = v26;
          *(_OWORD *)&v63[1] = 0;
          v27 = std::_Allocate<16,std::_Default_allocate_traits>(64);
          *(_QWORD *)v27 = v27;
          *(_QWORD *)(v27 + 8) = v27;
          *(_QWORD *)(v27 + 16) = v27;
          *(_WORD *)(v27 + 24) = 257;
          v63[1] = (const char *)v27;
          v28 = *(_DWORD *)(v10 + 64);
          if ( !v28 )
          {
            Src = 0;
            std::wstring::wstring(&v76, v10 + 72);
            v40 = *((_QWORD *)&v79 + 1);
            if ( *((_QWORD *)&v79 + 1) == (_QWORD)v80 )
            {
              std::vector<UsageAndQualityInsights::Configuration::Fact>::_Emplace_reallocate<UsageAndQualityInsights::Configuration::Fact>(
                &v79,
                *((_QWORD *)&v79 + 1),
                &Src);
            }
            else
            {
              **((_DWORD **)&v79 + 1) = Src;
              *(_QWORD *)(v40 + 8) = v76;
              *(_QWORD *)(v40 + 16) = v77;
              *(__m128i *)(v40 + 24) = v78;
              v78 = si128;
              LOWORD(v76) = 0;
              *((_QWORD *)&v79 + 1) += 40LL;
            }
            std::wstring::~wstring(&v76);
            v41 = *(_QWORD *)(v10 + 168);
            for ( i = *(_QWORD *)(v10 + 160); i != v41; i += 32 )
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                &v65[1],
                v72,
                i);
            v43 = *(_QWORD *)(v10 + 144);
            for ( j = *(_QWORD *)(v10 + 136); j != v43; j += 32 )
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                &v63[1],
                v73,
                j);
LABEL_55:
            v21 = (wchar_t *)(v7 + 7);
            goto LABEL_56;
          }
          if ( v28 == 1 )
          {
            v29 = *(_QWORD *)(v10 + 192);
            v30 = *(_QWORD *)(v10 + 200);
            if ( v29 != v30 )
            {
              do
              {
                Src = 1;
                std::operator+<wchar_t>(&v76, L"Microsoft.Windows.Health.TestInProduction.TestResult", v29);
                v31 = *((_QWORD *)&v79 + 1);
                if ( *((_QWORD *)&v79 + 1) == (_QWORD)v80 )
                {
                  std::vector<UsageAndQualityInsights::Configuration::Fact>::_Emplace_reallocate<UsageAndQualityInsights::Configuration::Fact>(
                    &v79,
                    *((_QWORD *)&v79 + 1),
                    &Src);
                }
                else
                {
                  **((_DWORD **)&v79 + 1) = Src;
                  *(_QWORD *)(v31 + 8) = v76;
                  *(_QWORD *)(v31 + 16) = v77;
                  *(__m128i *)(v31 + 24) = v78;
                  v78 = si128;
                  LOWORD(v76) = 0;
                  *((_QWORD *)&v79 + 1) += 40LL;
                }
                std::wstring::~wstring(&v76);
                v29 += 32;
              }
              while ( v29 != v30 );
              v7 = v5 + 8;
            }
            v32 = off_18010C6E0;
            do
            {
              v33 = *v32;
              v117 = 0;
              v118 = 0;
              v34 = -1;
              do
                ++v34;
              while ( v33[v34] );
              std::wstring::_Construct<1,wchar_t const *>(&v117, v33, v34);
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                &v65[1],
                v70,
                &v117);
              std::wstring::~wstring(&v117);
              ++v32;
            }
            while ( v32 != &off_18010C6F0 );
            v35 = off_18010C690;
            do
            {
              v36 = *v35;
              v117 = 0;
              v118 = 0;
              v37 = -1;
              do
                ++v37;
              while ( v36[v37] );
              std::wstring::_Construct<1,wchar_t const *>(&v117, v36, v37);
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                &v63[1],
                v71,
                &v117);
              std::wstring::~wstring(&v117);
              ++v35;
            }
            while ( v35 != (wchar_t **)&unk_18010C6D8 );
            goto LABEL_55;
          }
LABEL_56:
          if ( *(_BYTE *)(v10 + 240) )
          {
            v38 = **(_QWORD **)(v10 + 224);
            v64 = v38;
            while ( !*(_BYTE *)(v38 + 25) )
            {
              if ( *(_QWORD *)(v38 + 56) <= 7u )
                v39 = v38 + 32;
              else
                v39 = *(_QWORD *)(v38 + 32);
              v45 = *(_QWORD *)(v38 + 48);
              v46 = v3;
              if ( (unsigned __int64)v3[3] > 7 )
                v46 = (__int64 *)*v3;
              v69[2] = v39;
              v69[3] = v45;
              v69[4] = v46;
              v69[5] = v3[2];
              EnrichedDimensionKey = UsageAndQualityInsights::Facts::FactKey::MakeEnrichedDimensionKey(&Src);
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                &v63[1],
                v74,
                EnrichedDimensionKey);
              std::wstring::~wstring(&Src);
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::EnrichedField>>>,std::_Iterator_base0>::operator++(&v64);
              v38 = v64;
            }
          }
          v48 = (_QWORD *)v7[4];
          v49 = (_QWORD *)v7[5];
          while ( v48 != v49 )
          {
            if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::contains(
                                    &v65[1],
                                    v48) )
            {
              if ( *((_QWORD *)&v82 + 1) == v83 )
              {
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v82, *((_QWORD *)&v82 + 1), v48);
              }
              else
              {
                std::wstring::wstring(*((_QWORD *)&v82 + 1), v48);
                *((_QWORD *)&v82 + 1) += 32LL;
              }
            }
            else
            {
              std::wstring::wstring(&v117, v48);
              if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::contains(
                                      &v63[1],
                                      &v117) )
              {
                if ( (_QWORD)v81 == *((_QWORD *)&v81 + 1) )
                {
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>((char *)&v80 + 8, v81, &v117);
                }
                else
                {
                  std::wstring::wstring(v81, &v117);
                  *(_QWORD *)&v81 = v81 + 32;
                }
              }
              else
              {
                if ( v48[3] <= 7u )
                  v50 = v48;
                else
                  v50 = (_QWORD *)*v48;
                v51 = v48[2];
                if ( (unsigned __int64)v3[3] <= 7 )
                  v52 = v3;
                else
                  v52 = (__int64 *)*v3;
                v69[6] = v50;
                v69[7] = v51;
                v69[8] = v52;
                v69[9] = v3[2];
                UsageAndQualityInsights::Facts::FactKey::MakeEnrichedDimensionKey(&Src);
                if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::contains(
                                         &v63[1],
                                         &Src) )
                {
                  v60 = wil::verify_hresult<long>(2147942487LL);
                  wil::details::in1diag3::Throw_HrMsg(
                    retaddr,
                    (void *)0xC4,
                    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\compileduqiconfig.cpp",
                    (const char *)v60,
                    (int)"Field not found in available metrics or dimensions",
                    v62);
                }
                if ( (_QWORD)v81 == *((_QWORD *)&v81 + 1) )
                {
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>((char *)&v80 + 8, v81, &Src);
                }
                else
                {
                  std::wstring::wstring(v81, &Src);
                  *(_QWORD *)&v81 = v81 + 32;
                }
                std::wstring::~wstring(&Src);
              }
              std::wstring::~wstring(&v117);
            }
            v48 += 4;
          }
          v84 = StringToAggregationWindowType(v21);
          v53 = *((_DWORD *)v7 + 22);
          LOBYTE(v54) = v84;
          v55 = AggregationWindowSizeRate(v54);
          v85 = v53 * (v55 / (unsigned int)AggregationWindowSizeRate(0));
          v86 = *((_DWORD *)v7 + 23);
          v93 = v86;
          v8 = (_DWORD *)v65[0];
          v94 = *(_DWORD *)(v65[0] + 4LL);
          v95 = *(_QWORD *)(v65[0] + 16LL);
          if ( a2[1] == a2[2] )
          {
            std::vector<UsageAndQualityInsights::Configuration::TelemetryEndpointConfig>::_Emplace_reallocate<UsageAndQualityInsights::Configuration::TelemetryEndpointConfig>(
              a2,
              a2[1],
              &v79);
          }
          else
          {
            UsageAndQualityInsights::Configuration::TelemetryEndpointConfig::TelemetryEndpointConfig(a2[1], &v79);
            a2[1] += 168LL;
          }
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v63[1]);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v65[1]);
          UsageAndQualityInsights::Configuration::TelemetryEndpointConfig::~TelemetryEndpointConfig((UsageAndQualityInsights::Configuration::TelemetryEndpointConfig *)&v79);
          v6 = v3 + 5;
          v9 = v66;
LABEL_101:
          v8 += 8;
        }
        v56 = (__int64 **)v5[2];
        if ( *((_BYTE *)v56 + 25) )
        {
          for ( k = (__int64 *)v5[1]; !*((_BYTE *)k + 25) && v5 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v5 = k;
          v5 = k;
        }
        else
        {
          v5 = (__int64 *)v5[2];
          for ( m = *v56; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v5 = m;
        }
      }
      v3 += 9;
    }
    while ( v3 != v67 );
  }
  return a2;
}

```

## disassembly

```asm
0x1800eb40c  mov     rax, rsp
0x1800eb40f  mov     [rax+18h], rbx
0x1800eb413  push    rbp
0x1800eb414  push    rsi
0x1800eb415  push    rdi
0x1800eb416  push    r12
0x1800eb418  push    r13
0x1800eb41a  push    r14
0x1800eb41c  push    r15
0x1800eb41e  lea     rbp, [rax-418h]
0x1800eb425  sub     rsp, 4E0h
0x1800eb42c  movaps  xmmword ptr [rax-48h], xmm6
0x1800eb430  mov     rax, cs:__security_cookie
0x1800eb437  xor     rax, rsp
0x1800eb43a  mov     [rbp+410h+var_50], rax
0x1800eb441  mov     r12, rdx
0x1800eb444  mov     [rbp+410h+var_430], rdx
0x1800eb448  xor     esi, esi
0x1800eb44a  mov     dword ptr [rsp+510h+var_4E0], esi
0x1800eb44e  mov     [rdx], rsi
0x1800eb451  mov     [rdx+8], rsi
0x1800eb455  mov     [rdx+10h], rsi
0x1800eb459  mov     dword ptr [rsp+510h+var_4E0], 1
0x1800eb461  mov     r14, [rcx]
0x1800eb464  mov     rcx, [rcx+8]
0x1800eb468  mov     [rsp+510h+var_4A0], rcx
0x1800eb46d  cmp     r14, rcx
0x1800eb470  jz      loc_1800EC242
0x1800eb476  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800eb47e  mov     rbx, [r14+38h]
0x1800eb482  mov     rbx, [rbx]
0x1800eb485  lea     rax, [r14+28h]
0x1800eb489  cmp     [rbx+19h], sil
0x1800eb48d  jnz     loc_1800EC233
0x1800eb493  lea     r15, [rbx+40h]
0x1800eb497  mov     rdi, [r15+60h]
0x1800eb49b  mov     rcx, [r15+68h]
0x1800eb49f  mov     [rsp+510h+var_4A8], rcx
0x1800eb4a4  jmp     loc_1800EC1D6
0x1800eb4a9  cmp     [rdi], esi
0x1800eb4ab  jnz     loc_1800EC1D2
0x1800eb4b1  mov     r8, r15
0x1800eb4b4  lea     rdx, [rbp+410h+var_80]
0x1800eb4bb  mov     rcx, rax
0x1800eb4be  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800eb4c3  mov     rdi, qword ptr [rbp+410h+var_70]
0x1800eb4ca  cmp     [rdi+19h], sil
0x1800eb4ce  jnz     short loc_1800EB51B
0x1800eb4d0  mov     r13, [rdi+30h]
0x1800eb4d4  lea     rdx, [rdi+20h]
0x1800eb4d8  cmp     qword ptr [rdi+38h], 7
0x1800eb4dd  jbe     short loc_1800EB4E2
0x1800eb4df  mov     rdx, [rdx]; S2
0x1800eb4e2  mov     rsi, [r15+10h]
0x1800eb4e6  cmp     qword ptr [r15+18h], 7
0x1800eb4eb  jbe     short loc_1800EB4F2
0x1800eb4ed  mov     rcx, [r15]
0x1800eb4f0  jmp     short loc_1800EB4F5
0x1800eb4f2  mov     rcx, r15; S1
0x1800eb4f5  mov     r8, rsi
0x1800eb4f8  cmp     r13, rsi
0x1800eb4fb  cmovb   r8, r13; N
0x1800eb4ff  call    wmemcmp
0x1800eb504  test    eax, eax
0x1800eb506  jz      short loc_1800EB510
0x1800eb508  xor     esi, esi
0x1800eb50a  test    eax, eax
0x1800eb50c  jns     short loc_1800EB51F
0x1800eb50e  jmp     short loc_1800EB51B
0x1800eb510  cmp     rsi, r13
0x1800eb513  jb      short loc_1800EB519
0x1800eb515  xor     esi, esi
0x1800eb517  jmp     short loc_1800EB51F
0x1800eb519  xor     esi, esi
0x1800eb51b  mov     rdi, [r14+28h]
0x1800eb51f  cmp     rdi, [r14+28h]
0x1800eb523  setz    al
0x1800eb526  mov     rcx, [rbp+418h]; this
0x1800eb52d  lea     rdx, aMissingFactDef; "Missing fact definition for source fact"
0x1800eb534  mov     qword ptr [rsp+510h+var_4E8], rdx; bool
0x1800eb539  mov     byte ptr [rsp+510h+var_4F0], al; int
0x1800eb53d  mov     r9d, 80070057h; char *
0x1800eb543  lea     r8, aOnecoreBaseUsa_19; "onecore\\base\\usageandqualityinsights"...
0x1800eb54a  mov     edx, 48h ; 'H'; void *
0x1800eb54f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800eb554  xorps   xmm0, xmm0
0x1800eb557  movdqa  [rbp+410h+var_3B0], xmm0
0x1800eb55c  xorps   xmm1, xmm1
0x1800eb55f  movdqa  [rbp+410h+var_3A0], xmm1
0x1800eb564  movdqa  [rbp+410h+var_390], xmm0
0x1800eb56c  movdqa  [rbp+410h+var_380], xmm1
0x1800eb574  mov     [rbp+410h+var_370], rsi
0x1800eb57b  movups  [rbp+410h+var_358], xmm0
0x1800eb582  mov     [rbp+410h+var_348], rsi
0x1800eb589  mov     ecx, 7
0x1800eb58e  mov     [rbp+410h+var_340], rcx
0x1800eb595  mov     word ptr [rbp+410h+var_358], si
0x1800eb59c  movups  [rbp+410h+var_338], xmm0
0x1800eb5a3  mov     [rbp+410h+var_328], rsi
0x1800eb5aa  mov     [rbp+410h+var_320], rcx
0x1800eb5b1  mov     word ptr [rbp+410h+var_338], si
0x1800eb5b8  lea     rdx, [rbx+20h]
0x1800eb5bc  lea     rcx, [rbp+410h+var_358]
0x1800eb5c3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800eb5c8  lea     r9, [rbp+410h+var_56]
0x1800eb5cf  mov     r8d, [r14+20h]
0x1800eb5d3  sub     r9, 2
0x1800eb5d7  mov     eax, 0CCCCCCCDh
0x1800eb5dc  mul     r8d
0x1800eb5df  shr     edx, 3
0x1800eb5e2  movzx   eax, dx
0x1800eb5e5  shl     ax, 2
0x1800eb5e9  lea     ecx, [rax+rdx]
0x1800eb5ec  add     cx, cx
0x1800eb5ef  sub     r8w, cx
0x1800eb5f3  add     r8w, 30h ; '0'
0x1800eb5f8  mov     [r9], r8w
0x1800eb5fc  mov     r8d, edx
0x1800eb5ff  test    edx, edx
0x1800eb601  jnz     short loc_1800EB5D3
0x1800eb603  lea     r8, [rbp+410h+var_56]
0x1800eb60a  mov     rdx, r9
0x1800eb60d  lea     rcx, [rbp+410h+Src]
0x1800eb611  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x1800eb616  or      dword ptr [rsp+510h+var_4E0], 6
0x1800eb61b  lea     rdx, [rbp+410h+Src]
0x1800eb61f  lea     rcx, [rbp+410h+var_338]
0x1800eb626  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800eb62b  lea     rcx, [rbp+410h+Src]; void *
0x1800eb62f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb634  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport> `wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl(void)'::`2'::impl
0x1800eb63b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(void)
0x1800eb640  xorps   xmm0, xmm0
0x1800eb643  xorps   xmm1, xmm1
0x1800eb646  test    al, al
0x1800eb648  jnz     loc_1800EB706
0x1800eb64e  movups  [rbp+410h+var_2E0], xmm0
0x1800eb655  movdqa  [rbp+410h+var_2D0], xmm1
0x1800eb65d  mov     esi, 12h
0x1800eb662  mov     r8d, esi
0x1800eb665  lea     rdx, aSystemFactsour; "system::factSource"
0x1800eb66c  lea     rcx, [rbp+410h+var_2E0]
0x1800eb673  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb678  nop
0x1800eb679  xorps   xmm0, xmm0
0x1800eb67c  movups  [rbp+410h+var_2C0], xmm0
0x1800eb683  xorps   xmm1, xmm1
0x1800eb686  movdqa  [rbp+410h+var_2B0], xmm1
0x1800eb68e  mov     r8d, esi
0x1800eb691  lea     rdx, aSystemMetricna; "system::metricName"
0x1800eb698  lea     rcx, [rbp+410h+var_2C0]
0x1800eb69f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb6a4  nop
0x1800eb6a5  xorps   xmm0, xmm0
0x1800eb6a8  movups  [rbp+410h+var_2A0], xmm0
0x1800eb6af  xorps   xmm1, xmm1
0x1800eb6b2  movdqa  [rbp+410h+var_290], xmm1
0x1800eb6ba  lea     r8d, [rsi+1]
0x1800eb6be  lea     rdx, aSystemWindowTy; "system::window_type"
0x1800eb6c5  lea     rcx, [rbp+410h+var_2A0]
0x1800eb6cc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb6d1  nop
0x1800eb6d2  lea     rax, [rbp+410h+var_2E0]
0x1800eb6d9  mov     [rbp+410h+var_490], rax
0x1800eb6dd  lea     rax, [rbp+410h+var_280]
0x1800eb6e4  mov     [rbp+410h+var_488], rax
0x1800eb6e8  lea     rdx, [rbp+410h+var_490]
0x1800eb6ec  lea     rcx, [rbp+410h+var_3A0+8]
0x1800eb6f0  call    ??4?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV01@V?$initializer_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::vector<std::wstring>::operator=(std::initializer_list<std::wstring>)
0x1800eb6f5  nop
0x1800eb6f6  lea     r8d, [rsi-0Fh]
0x1800eb6fa  lea     rcx, [rbp+410h+var_2E0]
0x1800eb701  jmp     loc_1800EBA10
0x1800eb706  movups  [rbp+410h+var_280], xmm0
0x1800eb70d  movdqa  [rbp+410h+var_270], xmm1
0x1800eb715  mov     r8d, 18h
0x1800eb71b  lea     rdx, aSystemPartaApp; "system::partA__app__is1P"
0x1800eb722  lea     rcx, [rbp+410h+var_280]
0x1800eb729  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb72e  nop
0x1800eb72f  xorps   xmm0, xmm0
0x1800eb732  movups  [rbp+410h+var_260], xmm0
0x1800eb739  xorps   xmm1, xmm1
0x1800eb73c  movdqa  [rbp+410h+var_250], xmm1
0x1800eb744  mov     r8d, 1Eh
0x1800eb74a  lea     rdx, aOverwriteParta_1; "overwrite::PartA_Ext_Os_BootId"
0x1800eb751  lea     rcx, [rbp+410h+var_260]
0x1800eb758  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb75d  nop
0x1800eb75e  xorps   xmm0, xmm0
0x1800eb761  movups  [rbp+410h+var_240], xmm0
0x1800eb768  xorps   xmm1, xmm1
0x1800eb76b  movdqa  [rbp+410h+var_230], xmm1
0x1800eb773  mov     r8d, 22h ; '"'
0x1800eb779  lea     rdx, aSystemPartaPri; "system::partA__privacy__isRequired"
0x1800eb780  lea     rcx, [rbp+410h+var_240]
0x1800eb787  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb78c  nop
0x1800eb78d  xorps   xmm0, xmm0
0x1800eb790  movups  [rbp+410h+var_220], xmm0
0x1800eb797  xorps   xmm1, xmm1
0x1800eb79a  movdqa  [rbp+410h+var_210], xmm1
0x1800eb7a2  mov     r8d, 1Bh
0x1800eb7a8  lea     rdx, aSystemPartaUtc; "system::partA__utc__shellId"
0x1800eb7af  lea     rcx, [rbp+410h+var_220]
0x1800eb7b6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb7bb  nop
0x1800eb7bc  xorps   xmm0, xmm0
0x1800eb7bf  movups  [rbp+410h+var_200], xmm0
0x1800eb7c6  xorps   xmm1, xmm1
0x1800eb7c9  movdqa  [rbp+410h+var_1F0], xmm1
0x1800eb7d1  mov     r8d, 21h ; '!'
0x1800eb7d7  lea     rdx, aSystemPartaMet; "system::partA__metadata__policies"
0x1800eb7de  lea     rcx, [rbp+410h+var_200]
0x1800eb7e5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb7ea  nop
0x1800eb7eb  xorps   xmm0, xmm0
0x1800eb7ee  movups  [rbp+410h+var_1E0], xmm0
0x1800eb7f5  xorps   xmm1, xmm1
0x1800eb7f8  movdqa  [rbp+410h+var_1D0], xmm1
0x1800eb800  mov     r8d, 16h
0x1800eb806  lea     rdx, aSystemPartaOsV; "system::partA__os__ver"
0x1800eb80d  lea     rcx, [rbp+410h+var_1E0]
0x1800eb814  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb819  nop
0x1800eb81a  xorps   xmm0, xmm0
0x1800eb81d  movups  [rbp+410h+var_1C0], xmm0
0x1800eb824  xorps   xmm1, xmm1
0x1800eb827  movdqa  [rbp+410h+var_1B0], xmm1
0x1800eb82f  mov     r13d, 13h
0x1800eb835  mov     r8d, r13d
0x1800eb838  lea     rdx, aSystemHourtime; "system::hourTimeBin"
0x1800eb83f  lea     rcx, [rbp+410h+var_1C0]
0x1800eb846  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb84b  nop
0x1800eb84c  xorps   xmm0, xmm0
0x1800eb84f  movups  [rbp+410h+var_1A0], xmm0
0x1800eb856  xorps   xmm1, xmm1
0x1800eb859  movdqa  [rbp+410h+var_190], xmm1
0x1800eb861  lea     r8d, [r13+0Ch]
0x1800eb865  lea     rdx, aOverwriteParta_0; "overwrite::PartA_Ext_App_UserId"
0x1800eb86c  lea     rcx, [rbp+410h+var_1A0]
0x1800eb873  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb878  nop
0x1800eb879  xorps   xmm0, xmm0
0x1800eb87c  movups  [rbp+410h+var_180], xmm0
0x1800eb883  xorps   xmm1, xmm1
0x1800eb886  movdqa  [rbp+410h+var_170], xmm1
0x1800eb88e  lea     r8d, [r13-6]
0x1800eb892  lea     rdx, aSystemOptin; "system::optIn"
0x1800eb899  lea     rcx, [rbp+410h+var_180]
0x1800eb8a0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb8a5  nop
0x1800eb8a6  xorps   xmm0, xmm0
0x1800eb8a9  movups  [rbp+410h+var_160], xmm0
0x1800eb8b0  xorps   xmm1, xmm1
0x1800eb8b3  movdqa  [rbp+410h+var_150], xmm1
0x1800eb8bb  lea     r8d, [r13-2]
0x1800eb8bf  lea     rdx, aSystemPoenable; "system::poEnabled"
0x1800eb8c6  lea     rcx, [rbp+410h+var_160]
0x1800eb8cd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb8d2  nop
0x1800eb8d3  xorps   xmm0, xmm0
0x1800eb8d6  movups  [rbp+410h+var_140], xmm0
0x1800eb8dd  xorps   xmm1, xmm1
0x1800eb8e0  movdqa  [rbp+410h+var_130], xmm1
0x1800eb8e8  lea     esi, [r13-1]
0x1800eb8ec  mov     r8d, esi
0x1800eb8ef  lea     rdx, aSystemDaytimeb; "system::dayTimeBin"
0x1800eb8f6  lea     rcx, [rbp+410h+var_140]
0x1800eb8fd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb902  nop
0x1800eb903  xorps   xmm0, xmm0
0x1800eb906  movups  [rbp+410h+var_120], xmm0
0x1800eb90d  xorps   xmm1, xmm1
0x1800eb910  movdqa  [rbp+410h+var_110], xmm1
0x1800eb918  mov     r8d, esi
0x1800eb91b  lea     rdx, aSystemFactsour; "system::factSource"
0x1800eb922  lea     rcx, [rbp+410h+var_120]
0x1800eb929  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb92e  nop
0x1800eb92f  xorps   xmm0, xmm0
0x1800eb932  movups  [rbp+410h+var_100], xmm0
0x1800eb939  xorps   xmm1, xmm1
0x1800eb93c  movdqa  [rbp+410h+var_F0], xmm1
0x1800eb944  lea     r8d, [r13-3]
0x1800eb948  lea     rdx, aSystemFactname; "system::factName"
0x1800eb94f  lea     rcx, [rbp+410h+var_100]
0x1800eb956  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb95b  nop
0x1800eb95c  xorps   xmm0, xmm0
0x1800eb95f  movups  [rbp+410h+var_E0], xmm0
0x1800eb966  xorps   xmm1, xmm1
0x1800eb969  movdqa  [rbp+410h+var_D0], xmm1
0x1800eb971  lea     r8d, [r13-3]
0x1800eb975  lea     rdx, aSystemFacttime; "system::factTime"
0x1800eb97c  lea     rcx, [rbp+410h+var_E0]
0x1800eb983  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800eb988  nop
0x1800eb989  xorps   xmm0, xmm0
  ... truncated ...
```
