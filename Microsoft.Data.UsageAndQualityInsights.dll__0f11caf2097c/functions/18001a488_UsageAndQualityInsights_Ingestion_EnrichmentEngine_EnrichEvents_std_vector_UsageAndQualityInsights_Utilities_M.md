# UsageAndQualityInsights::Ingestion::EnrichmentEngine::EnrichEvents(std::vector<UsageAndQualityInsights::Utilities::MetricEvent,std::allocator<UsageAndQualityInsights::Utilities::MetricEvent>> &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields,std::allocator<UsageAndQualityInsights::Configuration::EnrichedFields>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields,std::allocator<UsageAndQualityInsights::Configuration::EnrichedFields>>>>> const &)

- ea: `0x18001a488`
- end: `0x18001a8ee`
- name: `?EnrichEvents@EnrichmentEngine@Ingestion@UsageAndQualityInsights@@SAXAEAV?$vector@UMetricEvent@Utilities@UsageAndQualityInsights@@V?$allocator@UMetricEvent@Utilities@UsageAndQualityInsights@@@std@@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@UEnrichedFields@Configuration@UsageAndQualityInsights@@V?$allocator@UEnrichedFields@Configuration@UsageAndQualityInsights@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@UEnrichedFields@Configuration@UsageAndQualityInsights@@V?$allocator@UEnrichedFields@Configuration@UsageAndQualityInsights@@@std@@@2@@std@@@2@@5@@Z`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x180015930`

## callees

- `0x1800033d0`
- `0x1800038b8`
- `0x180005e7c`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180012054`
- `0x180012dd4`
- `0x1800163f8`
- `0x180016680`
- `0x180019458`
- `0x18001a488`
- `0x18001a8f4`
- `0x18001a9b0`
- `0x1800228b0`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001a8b2`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001a8b2`

## string_xrefs

- `0x18001a8dc`: `onecore\base\usageandqualityinsights\service\lib\ingestion\enrichmentengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UsageAndQualityInsights::Ingestion::EnrichmentEngine::EnrichEvents(__int64 *a1, __int64 *a2)
{
  __int64 *v2; // r12
  int v3; // r13d
  __int64 v4; // r15
  bool i; // zf
  __int64 SourceEventFromMetricEvent; // rdi
  __int64 v7; // rbx
  const wchar_t *v8; // rdx
  size_t v9; // r14
  size_t v10; // rsi
  size_t v11; // r8
  int v12; // eax
  char v13; // al
  __int64 ***v14; // rax
  __int64 *v15; // rbx
  _QWORD *v16; // r15
  __int64 *v17; // rax
  __int64 v18; // r14
  const wchar_t *v19; // rdx
  size_t v20; // rdi
  size_t v21; // rsi
  const wchar_t *v22; // rcx
  size_t v23; // r8
  int v24; // eax
  char v25; // al
  __int64 v26; // rax
  __int128 v27; // xmm6
  __int64 v28; // rdx
  const wchar_t *v29; // rdx
  size_t v30; // rsi
  size_t v31; // rdi
  const wchar_t *v32; // rcx
  size_t v33; // r8
  int v34; // eax
  char v35; // al
  __int64 v36; // rsi
  _QWORD *v37; // r14
  __int64 **v38; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  unsigned int v41; // eax
  const char *v42; // [rsp+30h] [rbp-B1h]
  __int64 v43; // [rsp+38h] [rbp-A9h]
  _QWORD v44[3]; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v45; // [rsp+58h] [rbp-89h]
  __int64 v46; // [rsp+68h] [rbp-79h] BYREF
  __int64 v47; // [rsp+70h] [rbp-71h] BYREF
  _QWORD *v48; // [rsp+78h] [rbp-69h]
  __int64 ***v49; // [rsp+80h] [rbp-61h]
  __int64 *v50; // [rsp+88h] [rbp-59h]
  __int64 v51; // [rsp+90h] [rbp-51h]
  _QWORD *v52; // [rsp+98h] [rbp-49h]
  _QWORD *v53; // [rsp+A0h] [rbp-41h]
  wchar_t *S1[2]; // [rsp+A8h] [rbp-39h] BYREF
  size_t v55; // [rsp+B8h] [rbp-29h]
  unsigned __int64 v56; // [rsp+C0h] [rbp-21h]
  _BYTE v57[32]; // [rsp+C8h] [rbp-19h] BYREF
  char v58; // [rsp+E8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]

  v2 = a2;
  v50 = a2;
  v3 = 0;
  v4 = *a1;
  v51 = a1[1];
  for ( i = v4 == v51; ; i = v4 == v51 )
  {
    v43 = v4;
    if ( i )
      break;
    SourceEventFromMetricEvent = UsageAndQualityInsights::Utilities::GetSourceEventFromMetricEvent(v57, v4);
    std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
      v2,
      &v44[1],
      SourceEventFromMetricEvent);
    v7 = v45;
    if ( *(_BYTE *)(v45 + 25) )
      goto LABEL_17;
    v8 = (const wchar_t *)(v45 + 32);
    v9 = *(_QWORD *)(v45 + 48);
    if ( *(_QWORD *)(v45 + 56) > 7u )
      v8 = *(const wchar_t **)v8;
    v10 = *(_QWORD *)(SourceEventFromMetricEvent + 16);
    if ( *(_QWORD *)(SourceEventFromMetricEvent + 24) > 7u )
      SourceEventFromMetricEvent = *(_QWORD *)SourceEventFromMetricEvent;
    v11 = v10;
    if ( v9 < v10 )
      v11 = *(_QWORD *)(v45 + 48);
    v12 = wmemcmp((const wchar_t *)SourceEventFromMetricEvent, v8, v11);
    if ( v12 )
    {
      if ( v12 < 0 )
        goto LABEL_13;
    }
    else
    {
      if ( v10 < v9 )
      {
LABEL_13:
        v13 = -1;
        goto LABEL_16;
      }
      if ( v10 <= v9 )
        goto LABEL_18;
    }
    v13 = 1;
LABEL_16:
    if ( v13 < 0 )
LABEL_17:
      v7 = *v2;
LABEL_18:
    std::wstring::~wstring(v57);
    if ( v7 != *v2 )
    {
      v14 = *(__int64 ****)(v7 + 64);
      v44[0] = v14;
      v49 = *(__int64 ****)(v7 + 72);
      if ( v14 != v49 )
      {
        while ( 1 )
        {
          v15 = **v14;
          while ( !*((_BYTE *)v15 + 25) )
          {
            v16 = *(_QWORD **)(v4 + 240);
            v48 = *(_QWORD **)(v43 + 248);
            if ( v16 != v48 )
            {
              v17 = v15 + 9;
              while ( 1 )
              {
                std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                  v16,
                  &v46,
                  v17);
                if ( v46 == *v16 )
                {
                  v58 = 0;
                  goto LABEL_45;
                }
                if ( *((_DWORD *)v15 + 16) )
                {
                  v41 = wil::verify_hresult<long>(2147942487LL);
                  wil::details::in1diag3::Throw_HrMsg(
                    retaddr,
                    (void *)0x4D,
                    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\ingestion\\enrichmentengine.cpp",
                    (const char *)v41,
                    (int)"Unsupported enrichment type",
                    v42);
                }
                std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                  v15 + 13,
                  &v47,
                  v46 + 64);
                if ( v47 != v15[13] )
                {
                  std::wstring::wstring(v57, v47 + 64);
                  v58 = 1;
                  goto LABEL_45;
                }
                *(_OWORD *)S1 = 0;
                v55 = 0;
                v56 = 0;
                std::wstring::_Construct<1,wchar_t const *>(S1, L"__default__", 11);
                std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
                  v15 + 13,
                  &v44[1],
                  S1);
                v18 = v45;
                if ( *(_BYTE *)(v45 + 25) )
                  goto LABEL_82;
                v19 = (const wchar_t *)(v45 + 32);
                v20 = *(_QWORD *)(v45 + 48);
                if ( *(_QWORD *)(v45 + 56) > 7u )
                  v19 = *(const wchar_t **)v19;
                v21 = v55;
                v22 = (const wchar_t *)S1;
                if ( v56 > 7 )
                  v22 = S1[0];
                v23 = v55;
                if ( v20 < v55 )
                  v23 = *(_QWORD *)(v45 + 48);
                v24 = wmemcmp(v22, v19, v23);
                if ( v24 )
                  break;
                if ( v21 < v20 )
                  goto LABEL_40;
                if ( v21 > v20 )
                  goto LABEL_42;
LABEL_44:
                std::wstring::wstring(v57, v18 + 64);
                v58 = 1;
                std::wstring::~wstring(S1);
LABEL_45:
                if ( !v58 )
                  goto LABEL_64;
                v26 = std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
                        v16,
                        &v44[1],
                        v15 + 4);
                v27 = *(_OWORD *)v26;
                v28 = *(_QWORD *)(v26 + 16);
                if ( *(_BYTE *)(v28 + 25) )
                  goto LABEL_62;
                v29 = (const wchar_t *)(v28 + 32);
                v30 = *((_QWORD *)v29 + 2);
                if ( *((_QWORD *)v29 + 3) > 7u )
                  v29 = *(const wchar_t **)v29;
                v31 = v15[6];
                if ( (unsigned __int64)v15[7] <= 7 )
                  v32 = (const wchar_t *)(v15 + 4);
                else
                  v32 = (const wchar_t *)v15[4];
                v33 = v15[6];
                if ( v30 < v31 )
                  v33 = v30;
                v34 = wmemcmp(v32, v29, v33);
                if ( v34 )
                {
                  if ( v34 < 0 )
                    goto LABEL_58;
                }
                else
                {
                  if ( v31 < v30 )
                  {
LABEL_58:
                    v35 = -1;
                    goto LABEL_61;
                  }
                  if ( v31 <= v30 )
                    goto LABEL_64;
                }
                v35 = 1;
LABEL_61:
                if ( v35 < 0 )
                {
LABEL_62:
                  if ( v16[1] == 0x2AAAAAAAAAAAAAALL )
                    goto LABEL_83;
                  v36 = *v16;
                  v52 = v16;
                  v53 = 0;
                  v37 = operator new(0x60u);
                  v53 = v37;
                  v44[1] = v37 + 4;
                  std::wstring::wstring(v37 + 4, v15 + 4);
                  std::wstring::wstring(v37 + 8, v57);
                  *v37 = v36;
                  v37[1] = v36;
                  v37[2] = v36;
                  *((_WORD *)v37 + 12) = 0;
                  v53 = 0;
                  *(_OWORD *)&v44[1] = v27;
                  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(
                    v16,
                    &v44[1],
                    v37);
                }
LABEL_64:
                v3 |= 1u;
                if ( v58 )
                  std::wstring::~wstring(v57);
                v16 += 6;
                v17 = v15 + 9;
                if ( v16 == v48 )
                  goto LABEL_67;
              }
              if ( v24 >= 0 )
LABEL_42:
                v25 = 1;
              else
LABEL_40:
                v25 = -1;
              if ( v25 < 0 )
              {
LABEL_82:
                std::_Xout_of_range("invalid map<K, T> key");
LABEL_83:
                std::_Throw_tree_length_error();
              }
              goto LABEL_44;
            }
LABEL_67:
            v38 = (__int64 **)v15[2];
            if ( *((_BYTE *)v38 + 25) )
            {
              for ( j = (__int64 *)v15[1]; !*((_BYTE *)j + 25) && v15 == (__int64 *)j[2]; j = (__int64 *)j[1] )
                v15 = j;
              v15 = j;
            }
            else
            {
              v15 = (__int64 *)v15[2];
              for ( k = *v38; !*((_BYTE *)k + 25); k = (__int64 *)*k )
                v15 = k;
            }
            v4 = v43;
          }
          v14 = (__int64 ***)(v44[0] + 16LL);
          v44[0] = v14;
          if ( v14 == v49 )
          {
            v2 = v50;
            break;
          }
        }
      }
    }
    v4 += 264;
  }
}

```

## disassembly

```asm
0x18001a488  mov     rax, rsp
0x18001a48b  mov     [rax+18h], rbx
0x18001a48f  push    rbp
0x18001a490  push    rsi
0x18001a491  push    rdi
0x18001a492  push    r12
0x18001a494  push    r13
0x18001a496  push    r14
0x18001a498  push    r15
0x18001a49a  lea     rbp, [rax-5Fh]
0x18001a49e  sub     rsp, 100h
0x18001a4a5  movaps  xmmword ptr [rax-48h], xmm6
0x18001a4a9  mov     rax, cs:__security_cookie
0x18001a4b0  xor     rax, rsp
0x18001a4b3  mov     [rbp+57h+var_48], rax
0x18001a4b7  mov     r12, rdx
0x18001a4ba  mov     [rbp+57h+var_B0], rdx
0x18001a4be  xor     r13d, r13d
0x18001a4c1  mov     dword ptr [rsp+130h+var_100], r13d
0x18001a4c6  mov     r15, [rcx]
0x18001a4c9  mov     rax, [rcx+8]
0x18001a4cd  mov     [rbp+57h+var_A8], rax
0x18001a4d1  cmp     r15, rax
0x18001a4d4  jmp     loc_18001A874
0x18001a4d9  mov     rdx, r15
0x18001a4dc  lea     rcx, [rbp+57h+var_70]
0x18001a4e0  call    ?GetSourceEventFromMetricEvent@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUMetricEvent@12@@Z; UsageAndQualityInsights::Utilities::GetSourceEventFromMetricEvent(UsageAndQualityInsights::Utilities::MetricEvent const &)
0x18001a4e5  mov     rdi, rax
0x18001a4e8  mov     r8, rax
0x18001a4eb  lea     rdx, [rsp+130h+var_F8+8]
0x18001a4f0  mov     rcx, r12
0x18001a4f3  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001a4f8  mov     rbx, [rsp+130h+var_E0]
0x18001a4fd  cmp     byte ptr [rbx+19h], 0
0x18001a501  jnz     short loc_18001A54E
0x18001a503  lea     rdx, [rbx+20h]
0x18001a507  mov     r14, [rdx+10h]
0x18001a50b  cmp     qword ptr [rdx+18h], 7
0x18001a510  jbe     short loc_18001A515
0x18001a512  mov     rdx, [rdx]; S2
0x18001a515  mov     rsi, [rdi+10h]
0x18001a519  cmp     qword ptr [rdi+18h], 7
0x18001a51e  jbe     short loc_18001A523
0x18001a520  mov     rdi, [rdi]
0x18001a523  mov     r8, rsi
0x18001a526  cmp     r14, rsi
0x18001a529  cmovb   r8, r14; N
0x18001a52d  mov     rcx, rdi; S1
0x18001a530  call    wmemcmp
0x18001a535  test    eax, eax
0x18001a537  jz      short loc_18001A53D
0x18001a539  jns     short loc_18001A548
0x18001a53b  jmp     short loc_18001A542
0x18001a53d  cmp     rsi, r14
0x18001a540  jnb     short loc_18001A546
0x18001a542  mov     al, 0FFh
0x18001a544  jmp     short loc_18001A54A
0x18001a546  jbe     short loc_18001A552
0x18001a548  mov     al, 1
0x18001a54a  test    al, al
0x18001a54c  jns     short loc_18001A552
0x18001a54e  mov     rbx, [r12]
0x18001a552  lea     rcx, [rbp+57h+var_70]; void *
0x18001a556  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a55b  cmp     rbx, [r12]
0x18001a55f  jz      loc_18001A869
0x18001a565  mov     rax, [rbx+40h]
0x18001a569  mov     qword ptr [rsp+130h+var_F8], rax
0x18001a56e  mov     rcx, [rbx+48h]
0x18001a572  mov     [rbp+57h+var_B8], rcx
0x18001a576  cmp     rax, rcx
0x18001a579  jz      loc_18001A869
0x18001a57f  mov     rbx, [rax]
0x18001a582  mov     rbx, [rbx]
0x18001a585  cmp     byte ptr [rbx+19h], 0
0x18001a589  jnz     loc_18001A84D
0x18001a58f  lea     r12, [rbx+20h]
0x18001a593  mov     r15, [r15+0F0h]
0x18001a59a  mov     rax, [rsp+130h+var_100]
0x18001a59f  mov     rax, [rax+0F8h]
0x18001a5a6  mov     [rbp+57h+var_C0], rax
0x18001a5aa  cmp     r15, rax
0x18001a5ad  jz      loc_18001A800
0x18001a5b3  lea     rax, [r12+28h]
0x18001a5b8  mov     r8, rax
0x18001a5bb  lea     rdx, [rbp+57h+var_D0]
0x18001a5bf  mov     rcx, r15
0x18001a5c2  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001a5c7  mov     r8, [rbp+57h+var_D0]
0x18001a5cb  cmp     r8, [r15]
0x18001a5ce  jnz     short loc_18001A5D9
0x18001a5d0  mov     [rbp+57h+var_50], 0
0x18001a5d4  jmp     loc_18001A6D3
0x18001a5d9  cmp     dword ptr [r12+20h], 0
0x18001a5df  jnz     loc_18001A8BF
0x18001a5e5  lea     rdi, [r12+48h]
0x18001a5ea  add     r8, 40h ; '@'
0x18001a5ee  lea     rdx, [rbp+57h+var_C8]
0x18001a5f2  mov     rcx, rdi
0x18001a5f5  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001a5fa  mov     rdx, [rbp+57h+var_C8]
0x18001a5fe  cmp     rdx, [rdi]
0x18001a601  jz      short loc_18001A619
0x18001a603  add     rdx, 40h ; '@'
0x18001a607  lea     rcx, [rbp+57h+var_70]
0x18001a60b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a610  mov     [rbp+57h+var_50], 1
0x18001a614  jmp     loc_18001A6D3
0x18001a619  xorps   xmm0, xmm0
0x18001a61c  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18001a620  mov     [rbp+57h+var_80], 0
0x18001a628  mov     [rbp+57h+var_78], 0
0x18001a630  mov     r8d, 0Bh
0x18001a636  lea     rdx, aDefault; "__default__"
0x18001a63d  lea     rcx, [rbp+57h+S1]
0x18001a641  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001a646  nop
0x18001a647  lea     r8, [rbp+57h+S1]
0x18001a64b  lea     rdx, [rsp+130h+var_F8+8]
0x18001a650  mov     rcx, rdi
0x18001a653  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001a658  mov     r14, [rsp+130h+var_E0]
0x18001a65d  cmp     byte ptr [r14+19h], 0
0x18001a662  jnz     loc_18001A8AB
0x18001a668  lea     rdx, [r14+20h]
0x18001a66c  mov     rdi, [rdx+10h]
0x18001a670  cmp     qword ptr [rdx+18h], 7
0x18001a675  jbe     short loc_18001A67A
0x18001a677  mov     rdx, [rdx]; S2
0x18001a67a  mov     rsi, [rbp+57h+var_80]
0x18001a67e  lea     rcx, [rbp+57h+S1]
0x18001a682  cmp     [rbp+57h+var_78], 7
0x18001a687  cmova   rcx, [rbp+57h+S1]; S1
0x18001a68c  mov     r8, rsi
0x18001a68f  cmp     rdi, rsi
0x18001a692  cmovb   r8, rdi; N
0x18001a696  call    wmemcmp
0x18001a69b  test    eax, eax
0x18001a69d  jz      short loc_18001A6A3
0x18001a69f  jns     short loc_18001A6AE
0x18001a6a1  jmp     short loc_18001A6A8
0x18001a6a3  cmp     rsi, rdi
0x18001a6a6  jnb     short loc_18001A6AC
0x18001a6a8  mov     al, 0FFh
0x18001a6aa  jmp     short loc_18001A6B0
0x18001a6ac  jbe     short loc_18001A6B8
0x18001a6ae  mov     al, 1
0x18001a6b0  test    al, al
0x18001a6b2  js      loc_18001A8AB
0x18001a6b8  lea     rdx, [r14+40h]
0x18001a6bc  lea     rcx, [rbp+57h+var_70]
0x18001a6c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a6c5  mov     [rbp+57h+var_50], 1
0x18001a6c9  lea     rcx, [rbp+57h+S1]; void *
0x18001a6cd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a6d2  nop
0x18001a6d3  cmp     [rbp+57h+var_50], 0
0x18001a6d7  jz      loc_18001A7DA
0x18001a6dd  mov     r8, r12
0x18001a6e0  lea     rdx, [rsp+130h+var_F8+8]
0x18001a6e5  mov     rcx, r15
0x18001a6e8  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001a6ed  movups  xmm6, xmmword ptr [rax]
0x18001a6f0  mov     rdx, [rax+10h]
0x18001a6f4  cmp     byte ptr [rdx+19h], 0
0x18001a6f8  jnz     short loc_18001A752
0x18001a6fa  add     rdx, 20h ; ' '
0x18001a6fe  mov     rsi, [rdx+10h]
0x18001a702  cmp     qword ptr [rdx+18h], 7
0x18001a707  jbe     short loc_18001A70C
0x18001a709  mov     rdx, [rdx]; S2
0x18001a70c  mov     rdi, [r12+10h]
0x18001a711  cmp     qword ptr [r12+18h], 7
0x18001a717  jbe     short loc_18001A71F
0x18001a719  mov     rcx, [r12]
0x18001a71d  jmp     short loc_18001A722
0x18001a71f  mov     rcx, r12; S1
0x18001a722  mov     r8, rdi
0x18001a725  cmp     rsi, rdi
0x18001a728  cmovb   r8, rsi; N
0x18001a72c  call    wmemcmp
0x18001a731  test    eax, eax
0x18001a733  jz      short loc_18001A739
0x18001a735  jns     short loc_18001A748
0x18001a737  jmp     short loc_18001A73E
0x18001a739  cmp     rdi, rsi
0x18001a73c  jnb     short loc_18001A742
0x18001a73e  mov     al, 0FFh
0x18001a740  jmp     short loc_18001A74A
0x18001a742  jbe     loc_18001A7DA
0x18001a748  mov     al, 1
0x18001a74a  test    al, al
0x18001a74c  jns     loc_18001A7DA
0x18001a752  mov     rax, 2AAAAAAAAAAAAAAh
0x18001a75c  cmp     [r15+8], rax
0x18001a760  jz      loc_18001A8B9
0x18001a766  mov     rsi, [r15]
0x18001a769  mov     [rbp+57h+var_A0], r15
0x18001a76d  mov     [rbp+57h+var_98], 0
0x18001a775  mov     ecx, 60h ; '`'; Size
0x18001a77a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a77f  mov     r14, rax
0x18001a782  mov     [rbp+57h+var_98], rax
0x18001a786  lea     rdi, [rax+20h]
0x18001a78a  mov     qword ptr [rsp+130h+var_F8+8], rdi
0x18001a78f  mov     rdx, r12
0x18001a792  mov     rcx, rdi
0x18001a795  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a79a  nop
0x18001a79b  lea     rcx, [rdi+20h]
0x18001a79f  lea     rdx, [rbp+57h+var_70]
0x18001a7a3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a7a8  nop
0x18001a7a9  mov     [r14], rsi
0x18001a7ac  mov     [r14+8], rsi
0x18001a7b0  mov     [r14+10h], rsi
0x18001a7b4  mov     word ptr [r14+18h], 0
0x18001a7bb  mov     [rbp+57h+var_98], 0
0x18001a7c3  movdqu  xmmword ptr [rsp+130h+var_F8+8], xmm6
0x18001a7c9  mov     r8, r14
0x18001a7cc  lea     rdx, [rsp+130h+var_F8+8]
0x18001a7d1  mov     rcx, r15
0x18001a7d4  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>,void *> * const)
0x18001a7d9  nop
0x18001a7da  or      r13d, 1
0x18001a7de  cmp     [rbp+57h+var_50], 0
0x18001a7e2  jz      short loc_18001A7ED
0x18001a7e4  lea     rcx, [rbp+57h+var_70]; void *
0x18001a7e8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a7ed  add     r15, 30h ; '0'
0x18001a7f1  cmp     r15, [rbp+57h+var_C0]
0x18001a7f5  lea     rax, [r12+28h]
0x18001a7fa  jnz     loc_18001A5B8
0x18001a800  mov     rcx, [rbx+10h]
0x18001a804  cmp     byte ptr [rcx+19h], 0
0x18001a808  jz      short loc_18001A830
0x18001a80a  mov     rax, [rbx+8]
0x18001a80e  jmp     short loc_18001A81D
0x18001a810  cmp     rbx, [rax+10h]
0x18001a814  jnz     short loc_18001A823
0x18001a816  mov     rbx, rax
0x18001a819  mov     rax, [rax+8]
0x18001a81d  cmp     byte ptr [rax+19h], 0
0x18001a821  jz      short loc_18001A810
0x18001a823  mov     rbx, rax
0x18001a826  mov     r15, [rsp+130h+var_100]
0x18001a82b  jmp     loc_18001A585
0x18001a830  mov     rbx, rcx
0x18001a833  mov     rcx, [rcx]
0x18001a836  cmp     byte ptr [rcx+19h], 0
0x18001a83a  jnz     short loc_18001A826
0x18001a83c  mov     rbx, rcx
0x18001a83f  mov     rax, [rcx]
0x18001a842  mov     rcx, rax
0x18001a845  cmp     byte ptr [rax+19h], 0
0x18001a849  jz      short loc_18001A83C
0x18001a84b  jmp     short loc_18001A826
0x18001a84d  mov     rax, qword ptr [rsp+130h+var_F8]
0x18001a852  add     rax, 10h
0x18001a856  mov     qword ptr [rsp+130h+var_F8], rax
0x18001a85b  cmp     rax, [rbp+57h+var_B8]
0x18001a85f  jnz     loc_18001A57F
0x18001a865  mov     r12, [rbp+57h+var_B0]
0x18001a869  add     r15, 108h
0x18001a870  cmp     r15, [rbp+57h+var_A8]
0x18001a874  mov     [rsp+130h+var_100], r15
0x18001a879  jnz     loc_18001A4D9
0x18001a87f  mov     rcx, [rbp+57h+var_48]
0x18001a883  xor     rcx, rsp; StackCookie
0x18001a886  call    __security_check_cookie
0x18001a88b  lea     r11, [rsp+130h+var_30]
0x18001a893  mov     rbx, [r11+50h]
0x18001a897  movaps  xmm6, xmmword ptr [r11-10h]
0x18001a89c  mov     rsp, r11
0x18001a89f  pop     r15
0x18001a8a1  pop     r14
0x18001a8a3  pop     r13
0x18001a8a5  pop     r12
0x18001a8a7  pop     rdi
0x18001a8a8  pop     rsi
0x18001a8a9  pop     rbp
0x18001a8aa  retn
0x18001a8ab  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18001a8b2  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001a8b8  nop
0x18001a8b9  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x18001a8bf  mov     ecx, 80070057h
0x18001a8c4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001a8c9  mov     r9d, eax; char *
0x18001a8cc  mov     rcx, [rbp+5Fh]; this
0x18001a8d0  lea     rax, aUnsupportedEnr; "Unsupported enrichment type"
0x18001a8d7  mov     qword ptr [rsp+130h+var_110], rax; int
0x18001a8dc  lea     r8, aOnecoreBaseUsa; "onecore\\base\\usageandqualityinsights"...
0x18001a8e3  mov     edx, 4Dh ; 'M'; void *
0x18001a8e8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
