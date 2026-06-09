# UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetMaxExpirationDateBySourceAndEvent(void)

- ea: `0x1800eaecc`
- end: `0x1800eb406`
- name: `?GetMaxExpirationDateBySourceAndEvent@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@QEBA?AV?$array@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@$01@std@@XZ`
- size: `1338`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f4eb4`

## callees

- `0x1800033d0`
- `0x180003870`
- `0x1800038b8`
- `0x180005104`
- `0x180005e7c`
- `0x18000eee0`
- `0x180012054`
- `0x180012dd4`
- `0x1800163f8`
- `0x180016680`
- `0x180016a6c`
- `0x180019458`
- `0x18001a8f4`
- `0x18003bdac`
- `0x1800432a0`
- `0x1800eacc4`
- `0x1800eaecc`
- `0x180100b74`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800eb168`
- `msvcp_win!_Xtime_get_ticks` at `0x1800eb168`

## string_xrefs

- `0x1800eb3bf`: `onecore\base\usageandqualityinsights\service\lib\configuration\compileduqiconfig.cpp`
- `0x1800eb3ee`: `onecore\base\usageandqualityinsights\service\lib\configuration\compileduqiconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char *__fastcall UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetMaxExpirationDateBySourceAndEvent(
        __int64 *a1,
        char *a2)
{
  char *v2; // rbx
  __int64 *v3; // r12
  __int64 i; // r15
  _QWORD *v5; // rax
  char *v6; // rdi
  _QWORD *v7; // rsi
  __int64 *v8; // r14
  __int64 *v9; // rbx
  _QWORD *v10; // rcx
  __int64 v11; // rdi
  __int64 *v12; // rbx
  __int64 v13; // r14
  const wchar_t *v14; // rdx
  size_t v15; // rsi
  size_t v16; // r15
  const wchar_t *v17; // rcx
  size_t v18; // r8
  int v19; // eax
  __int64 v20; // rcx
  char v21; // al
  __int64 v22; // rsi
  wchar_t *v23; // r13
  __int64 v24; // rcx
  char *v25; // r14
  __int64 v26; // r15
  const wchar_t *v27; // rdx
  unsigned __int64 v28; // r14
  unsigned __int64 v29; // rsi
  const wchar_t *v30; // rcx
  size_t v31; // r8
  int v32; // eax
  char v33; // al
  int v34; // esi
  __int64 ticks; // r12
  char v36; // al
  __int64 v37; // r12
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int128 v42; // xmm6
  __int64 v43; // rdx
  const wchar_t *v44; // rdx
  size_t v45; // r14
  size_t v46; // rsi
  const wchar_t *v47; // rcx
  size_t v48; // r8
  int v49; // eax
  char v50; // al
  __int64 v51; // r14
  _QWORD *v52; // r15
  __int64 **v53; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  unsigned int v57; // eax
  unsigned int v58; // eax
  const char *v59; // [rsp+30h] [rbp-D8h]
  char *v60; // [rsp+38h] [rbp-D0h]
  _QWORD *v61; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v62; // [rsp+48h] [rbp-C0h]
  __int64 v63; // [rsp+50h] [rbp-B8h]
  char *v64; // [rsp+58h] [rbp-B0h]
  __int128 v65; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+78h] [rbp-90h]
  wchar_t *v67; // [rsp+88h] [rbp-80h]
  __int64 v68; // [rsp+90h] [rbp-78h]
  __int64 *v69; // [rsp+98h] [rbp-70h]
  char *v70; // [rsp+A0h] [rbp-68h]
  _QWORD *v71; // [rsp+A8h] [rbp-60h]
  wchar_t *v72; // [rsp+B0h] [rbp-58h] BYREF
  wchar_t *v73; // [rsp+B8h] [rbp-50h]
  char *v74; // [rsp+C8h] [rbp-40h]
  wchar_t *S1[2]; // [rsp+D0h] [rbp-38h] BYREF
  size_t v76; // [rsp+E0h] [rbp-28h]
  unsigned __int64 v77; // [rsp+E8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v2 = a2;
  v64 = a2;
  v3 = a1;
  v69 = a1;
  v74 = a2;
  `eh vector constructor iterator'(
    a2,
    0x10u,
    2u,
    std::map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>,
    std::map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>);
  LODWORD(v63) = 1;
  for ( i = 0; i != 2; ++i )
  {
    v61 = 0;
    v62 = 0;
    v5 = operator new(0x48u);
    *v5 = v5;
    v5[1] = v5;
    v5[2] = v5;
    *((_WORD *)v5 + 12) = 257;
    v61 = v5;
    v6 = &v2[16 * i];
    if ( v6 != (char *)&v61 )
    {
      v7 = *(_QWORD **)v6;
      v8 = *(__int64 **)(*(_QWORD *)v6 + 8LL);
      if ( !*((_BYTE *)v8 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>,void *>>>(
            v6,
            v6,
            v8[2]);
          v9 = v8;
          v8 = (__int64 *)*v8;
          std::wstring::~wstring(v9 + 4);
          operator delete(v9, 0x48u);
        }
        while ( !*((_BYTE *)v8 + 25) );
        v2 = v64;
      }
      v7[1] = v7;
      *v7 = v7;
      v7[2] = v7;
      v10 = *(_QWORD **)v6;
      *(_QWORD *)v6 = v61;
      v61 = v10;
      *((_QWORD *)v6 + 1) = v62;
      v62 = 0;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>,0>>(&v61);
  }
  v11 = *v3;
LABEL_9:
  if ( v11 != v3[1] )
  {
    v12 = **(__int64 ***)(v11 + 56);
    while ( 1 )
    {
      if ( v12 == *(__int64 **)(v11 + 56) )
      {
        v11 += 72;
        v3 = v69;
        goto LABEL_9;
      }
      std::wstring::wstring(S1, v12 + 8);
      std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
        v11 + 40,
        &v65,
        S1);
      v13 = v66;
      if ( *(_BYTE *)(v66 + 25) )
        goto LABEL_95;
      v14 = (const wchar_t *)(v66 + 32);
      v15 = *(_QWORD *)(v66 + 48);
      if ( *(_QWORD *)(v66 + 56) > 7u )
        v14 = *(const wchar_t **)v14;
      v16 = v76;
      v17 = (const wchar_t *)S1;
      if ( v77 > 7 )
        v17 = S1[0];
      v18 = v76;
      if ( v15 < v76 )
        v18 = *(_QWORD *)(v66 + 48);
      v19 = wmemcmp(v17, v14, v18);
      if ( v19 )
      {
        if ( v19 < 0 )
          goto LABEL_23;
      }
      else
      {
        if ( v16 < v15 )
        {
LABEL_23:
          v21 = -1;
          goto LABEL_26;
        }
        if ( v16 <= v15 )
          goto LABEL_27;
      }
      v21 = 1;
LABEL_26:
      if ( v21 < 0 )
        goto LABEL_95;
LABEL_27:
      if ( v13 == *(_QWORD *)(v11 + 40) )
      {
LABEL_95:
        v57 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\compileduqiconfig.cpp",
          (const char *)v57,
          (int)"Missing fact definition for source fact",
          v59);
      }
      v22 = *(int *)(v13 + 64);
      UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetEventName(v20, &v72);
      v23 = v72;
      v67 = v73;
      if ( v72 != v73 )
      {
        v24 = 16 * v22;
        v68 = 16 * v22;
        while ( 2 )
        {
          v25 = &v64[v24];
          v60 = &v64[v24];
          std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
            &v64[v24],
            &v65,
            v23);
          v26 = v66;
          if ( *(_BYTE *)(v66 + 25) )
            goto LABEL_48;
          v27 = (const wchar_t *)(v66 + 32);
          v28 = *(_QWORD *)(v66 + 48);
          if ( *(_QWORD *)(v66 + 56) > 7u )
            v27 = *(const wchar_t **)v27;
          v29 = *((_QWORD *)v23 + 2);
          if ( *((_QWORD *)v23 + 3) <= 7u )
            v30 = v23;
          else
            v30 = *(const wchar_t **)v23;
          v31 = *((_QWORD *)v23 + 2);
          if ( v28 < v29 )
            v31 = *(_QWORD *)(v66 + 48);
          v32 = wmemcmp(v30, v27, v31);
          if ( v32 )
          {
            if ( v32 < 0 )
            {
LABEL_42:
              v33 = -1;
              goto LABEL_45;
            }
          }
          else
          {
            if ( v29 < v28 )
              goto LABEL_42;
            if ( v29 <= v28 )
              goto LABEL_46;
          }
          v33 = 1;
LABEL_45:
          if ( v33 >= 0 )
          {
LABEL_46:
            v25 = v60;
            goto LABEL_49;
          }
          v25 = v60;
LABEL_48:
          v26 = *(_QWORD *)v25;
LABEL_49:
          v34 = *((_DWORD *)v12 + 38);
          ticks = _Xtime_get_ticks();
          *(_QWORD *)&v65 = ticks;
          v36 = StringToAggregationWindowType((wchar_t *)v12 + 60);
          switch ( v36 )
          {
            case 0:
              v39 = v34 + 24;
              v40 = 36000000000LL;
              goto LABEL_58;
            case 1:
              v38 = v34 + 1;
LABEL_55:
              v39 = v38;
              v40 = 864000000000LL;
LABEL_58:
              v37 = ticks - v40 * v39;
              goto LABEL_59;
            case 2:
              v38 = 7 * v34 + 1;
              goto LABEL_55;
          }
          if ( v36 != 3 )
          {
            v58 = wil::verify_hresult<long>(2147942487LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x15B,
              (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\compileduqiconfig.cpp",
              (const char *)v58,
              (int)"Invalid aggregation window type",
              v59);
          }
          v37 = ticks - 540000000LL * (48699 * v34 + 1600);
LABEL_59:
          if ( v26 != *(_QWORD *)v25 )
          {
            if ( v37 == *(_QWORD *)(v26 + 64) || v37 >= *(_QWORD *)(v26 + 64) )
              v37 = *(_QWORD *)(v26 + 64);
            *(_QWORD *)(v26 + 64) = v37;
            goto LABEL_83;
          }
          v41 = std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
                  v25,
                  &v65,
                  v23);
          v42 = *(_OWORD *)v41;
          v43 = *(_QWORD *)(v41 + 16);
          if ( *(_BYTE *)(v43 + 25) )
            goto LABEL_77;
          v44 = (const wchar_t *)(v43 + 32);
          v45 = *((_QWORD *)v44 + 2);
          if ( *((_QWORD *)v44 + 3) > 7u )
            v44 = *(const wchar_t **)v44;
          v46 = *((_QWORD *)v23 + 2);
          if ( *((_QWORD *)v23 + 3) <= 7u )
            v47 = v23;
          else
            v47 = *(const wchar_t **)v23;
          v48 = *((_QWORD *)v23 + 2);
          if ( v45 < v46 )
            v48 = v45;
          v49 = wmemcmp(v47, v44, v48);
          if ( v49 )
          {
            if ( v49 < 0 )
              goto LABEL_72;
          }
          else
          {
            if ( v46 < v45 )
            {
LABEL_72:
              v50 = -1;
              goto LABEL_75;
            }
            if ( v46 <= v45 )
              goto LABEL_83;
          }
          v50 = 1;
LABEL_75:
          if ( v50 < 0 )
          {
            v25 = v60;
LABEL_77:
            if ( *((_QWORD *)v25 + 1) == 0x38E38E38E38E38ELL )
              std::_Throw_tree_length_error();
            v51 = *(_QWORD *)v25;
            v70 = v60;
            v71 = 0;
            v52 = operator new(0x48u);
            v71 = v52;
            std::wstring::wstring(v52 + 4, v23);
            v52[8] = v37;
            *v52 = v51;
            v52[1] = v51;
            v52[2] = v51;
            *((_WORD *)v52 + 12) = 0;
            v71 = 0;
            v65 = v42;
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(
              v60,
              &v65,
              v52);
          }
LABEL_83:
          v23 += 16;
          v24 = v68;
          if ( v23 == v67 )
            break;
          continue;
        }
      }
      std::vector<std::wstring>::_Tidy(&v72);
      std::wstring::~wstring(S1);
      v53 = (__int64 **)v12[2];
      if ( *((_BYTE *)v53 + 25) )
      {
        for ( j = (__int64 *)v12[1]; !*((_BYTE *)j + 25) && v12 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v12 = j;
        v12 = j;
      }
      else
      {
        v12 = (__int64 *)v12[2];
        for ( k = *v53; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v12 = k;
      }
    }
  }
  return v64;
}

```

## disassembly

```asm
0x1800eaecc  mov     rax, rsp
0x1800eaecf  push    rbp
0x1800eaed0  push    rbx
0x1800eaed1  push    rsi
0x1800eaed2  push    rdi
0x1800eaed3  push    r12
0x1800eaed5  push    r13
0x1800eaed7  push    r14
0x1800eaed9  push    r15
0x1800eaedb  lea     rbp, [rax-48h]
0x1800eaedf  sub     rsp, 108h
0x1800eaee6  movaps  xmmword ptr [rax-58h], xmm6
0x1800eaeea  mov     rax, cs:__security_cookie
0x1800eaef1  xor     rax, rsp
0x1800eaef4  mov     qword ptr [rbp+40h+var_58], rax
0x1800eaef8  mov     rbx, rdx
0x1800eaefb  mov     [rsp+140h+var_F0], rdx
0x1800eaf00  mov     r12, rcx
0x1800eaf03  mov     [rbp+40h+var_B0], rcx
0x1800eaf07  mov     [rbp+40h+var_80], rdx
0x1800eaf0b  xor     r13d, r13d
0x1800eaf0e  mov     dword ptr [rsp+140h+var_F8], r13d
0x1800eaf13  lea     rax, ??1?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800eaf1a  mov     [rsp+20h], rax; void (*)(void *)
0x1800eaf1f  lea     r9, ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x1800eaf26  lea     edx, [r13+10h]; unsigned __int64
0x1800eaf2a  lea     r8d, [r13+2]; unsigned __int64
0x1800eaf2e  mov     rcx, rbx; void *
0x1800eaf31  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800eaf36  mov     dword ptr [rsp+140h+var_F8], 1
0x1800eaf3e  mov     r15d, r13d
0x1800eaf41  mov     [rsp+140h+var_108], r13
0x1800eaf46  mov     [rsp+140h+var_100], r13
0x1800eaf4b  mov     ecx, 48h ; 'H'; Size
0x1800eaf50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eaf55  mov     [rax], rax
0x1800eaf58  mov     [rax+8], rax
0x1800eaf5c  mov     [rax+10h], rax
0x1800eaf60  mov     word ptr [rax+18h], 101h
0x1800eaf66  mov     [rsp+140h+var_108], rax
0x1800eaf6b  mov     rdi, r15
0x1800eaf6e  shl     rdi, 4
0x1800eaf72  add     rdi, rbx
0x1800eaf75  lea     rax, [rsp+140h+var_108]
0x1800eaf7a  cmp     rdi, rax
0x1800eaf7d  jz      short loc_1800EAFEB
0x1800eaf7f  mov     rsi, [rdi]
0x1800eaf82  mov     r14, [rsi+8]
0x1800eaf86  cmp     [r14+19h], r13b
0x1800eaf8a  jnz     short loc_1800EAFC2
0x1800eaf8c  mov     r8, [r14+10h]
0x1800eaf90  mov     rdx, rdi
0x1800eaf93  mov     rcx, rdi
0x1800eaf96  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>,void *> *)
0x1800eaf9b  mov     rbx, r14
0x1800eaf9e  mov     r14, [r14]
0x1800eafa1  lea     rcx, [rbx+20h]; void *
0x1800eafa5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eafaa  mov     edx, 48h ; 'H'; unsigned __int64
0x1800eafaf  mov     rcx, rbx; void *
0x1800eafb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800eafb7  cmp     [r14+19h], r13b
0x1800eafbb  jz      short loc_1800EAF8C
0x1800eafbd  mov     rbx, [rsp+140h+var_F0]
0x1800eafc2  mov     [rsi+8], rsi
0x1800eafc6  mov     [rsi], rsi
0x1800eafc9  mov     [rsi+10h], rsi
0x1800eafcd  mov     rcx, [rdi]
0x1800eafd0  mov     rax, [rsp+140h+var_108]
0x1800eafd5  mov     [rdi], rax
0x1800eafd8  mov     [rsp+140h+var_108], rcx
0x1800eafdd  mov     rax, [rsp+140h+var_100]
0x1800eafe2  mov     [rdi+8], rax
0x1800eafe6  mov     [rsp+140h+var_100], r13
0x1800eafeb  lea     rcx, [rsp+140h+var_108]
0x1800eaff0  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>,0>>(void)
0x1800eaff5  inc     r15
0x1800eaff8  cmp     r15, 2
0x1800eaffc  jnz     loc_1800EAF41
0x1800eb002  mov     rdi, [r12]
0x1800eb006  cmp     rdi, [r12+8]
0x1800eb00b  jz      loc_1800EB375
0x1800eb011  mov     rbx, [rdi+38h]
0x1800eb015  mov     rbx, [rbx]
0x1800eb018  cmp     rbx, [rdi+38h]
0x1800eb01c  jz      loc_1800EB368
0x1800eb022  lea     rdx, [rbx+40h]
0x1800eb026  lea     rcx, [rbp+40h+S1]
0x1800eb02a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800eb02f  nop
0x1800eb030  lea     r8, [rbp+40h+S1]
0x1800eb034  lea     rdx, [rsp+140h+var_E8+8]
0x1800eb039  lea     rcx, [rdi+28h]
0x1800eb03d  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800eb042  mov     r14, [rsp+140h+var_D0]
0x1800eb047  cmp     [r14+19h], r13b
0x1800eb04b  jnz     loc_1800EB3A2
0x1800eb051  lea     rdx, [r14+20h]
0x1800eb055  mov     rsi, [rdx+10h]
0x1800eb059  cmp     qword ptr [rdx+18h], 7
0x1800eb05e  jbe     short loc_1800EB063
0x1800eb060  mov     rdx, [rdx]; S2
0x1800eb063  mov     r15, [rbp+40h+var_68]
0x1800eb067  lea     rcx, [rbp+40h+S1]
0x1800eb06b  cmp     [rbp+40h+var_60], 7
0x1800eb070  cmova   rcx, [rbp+40h+S1]; S1
0x1800eb075  mov     r8, r15
0x1800eb078  cmp     rsi, r15
0x1800eb07b  cmovb   r8, rsi; N
0x1800eb07f  call    wmemcmp
0x1800eb084  test    eax, eax
0x1800eb086  jz      short loc_1800EB08C
0x1800eb088  jns     short loc_1800EB097
0x1800eb08a  jmp     short loc_1800EB091
0x1800eb08c  cmp     r15, rsi
0x1800eb08f  jnb     short loc_1800EB095
0x1800eb091  mov     al, 0FFh
0x1800eb093  jmp     short loc_1800EB099
0x1800eb095  jbe     short loc_1800EB0A1
0x1800eb097  mov     al, 1
0x1800eb099  test    al, al
0x1800eb09b  js      loc_1800EB3A2
0x1800eb0a1  cmp     r14, [rdi+28h]
0x1800eb0a5  jz      loc_1800EB3A2
0x1800eb0ab  lea     r8, [r14+40h]
0x1800eb0af  movsxd  rsi, dword ptr [r8]
0x1800eb0b2  lea     rdx, [rbp+40h+var_98]
0x1800eb0b6  call    ?GetEventName@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@AEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBUFactDefinition@23@@Z; UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetEventName(UsageAndQualityInsights::Configuration::FactDefinition const &)
0x1800eb0bb  nop
0x1800eb0bc  mov     r13, [rbp+40h+var_98]
0x1800eb0c0  mov     rax, [rbp+40h+var_90]
0x1800eb0c4  mov     [rbp+40h+var_C0], rax
0x1800eb0c8  cmp     r13, rax
0x1800eb0cb  jz      loc_1800EB303
0x1800eb0d1  mov     rcx, rsi
0x1800eb0d4  shl     rcx, 4
0x1800eb0d8  mov     [rbp+40h+var_B8], rcx
0x1800eb0dc  mov     r14, [rsp+140h+var_F0]
0x1800eb0e1  add     r14, rcx
0x1800eb0e4  mov     [rsp+140h+var_110], r14
0x1800eb0e9  mov     r8, r13
0x1800eb0ec  lea     rdx, [rsp+140h+var_E8+8]
0x1800eb0f1  mov     rcx, r14
0x1800eb0f4  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800eb0f9  mov     r15, [rsp+140h+var_D0]
0x1800eb0fe  cmp     byte ptr [r15+19h], 0
0x1800eb103  jnz     short loc_1800EB15F
0x1800eb105  lea     rdx, [r15+20h]
0x1800eb109  mov     r14, [rdx+10h]
0x1800eb10d  cmp     qword ptr [rdx+18h], 7
0x1800eb112  jbe     short loc_1800EB117
0x1800eb114  mov     rdx, [rdx]; S2
0x1800eb117  mov     rsi, [r13+10h]
0x1800eb11b  cmp     qword ptr [r13+18h], 7
0x1800eb120  jbe     short loc_1800EB128
0x1800eb122  mov     rcx, [r13+0]
0x1800eb126  jmp     short loc_1800EB12B
0x1800eb128  mov     rcx, r13; S1
0x1800eb12b  mov     r8, rsi
0x1800eb12e  cmp     r14, rsi
0x1800eb131  cmovb   r8, r14; N
0x1800eb135  call    wmemcmp
0x1800eb13a  test    eax, eax
0x1800eb13c  jz      short loc_1800EB142
0x1800eb13e  jns     short loc_1800EB14D
0x1800eb140  jmp     short loc_1800EB147
0x1800eb142  cmp     rsi, r14
0x1800eb145  jnb     short loc_1800EB14B
0x1800eb147  mov     al, 0FFh
0x1800eb149  jmp     short loc_1800EB14F
0x1800eb14b  jbe     short loc_1800EB153
0x1800eb14d  mov     al, 1
0x1800eb14f  test    al, al
0x1800eb151  js      short loc_1800EB15A
0x1800eb153  mov     r14, [rsp+140h+var_110]
0x1800eb158  jmp     short loc_1800EB162
0x1800eb15a  mov     r14, [rsp+140h+var_110]
0x1800eb15f  mov     r15, [r14]
0x1800eb162  mov     esi, [rbx+98h]
0x1800eb168  call    cs:__imp__Xtime_get_ticks
0x1800eb16e  mov     r12, rax
0x1800eb171  mov     qword ptr [rsp+140h+var_E8+8], rax
0x1800eb176  lea     rcx, [rbx+78h]; S1
0x1800eb17a  call    ?StringToAggregationWindowType@@YA?AW4AggregationWindowType@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; StringToAggregationWindowType(std::wstring const &)
0x1800eb17f  movzx   ecx, al
0x1800eb182  test    al, al
0x1800eb184  jz      short loc_1800EB1CC
0x1800eb186  sub     ecx, 1
0x1800eb189  jz      short loc_1800EB1C7
0x1800eb18b  sub     ecx, 1
0x1800eb18e  jz      short loc_1800EB1B3
0x1800eb190  cmp     ecx, 1
0x1800eb193  jnz     loc_1800EB3D1
0x1800eb199  imul    eax, esi, 0BE3Bh
0x1800eb19f  add     eax, 640h
0x1800eb1a4  movsxd  rcx, eax
0x1800eb1a7  imul    rax, rcx, 202FBF00h
0x1800eb1ae  sub     r12, rax
0x1800eb1b1  jmp     short loc_1800EB1E3
0x1800eb1b3  imul    eax, esi, 7
0x1800eb1b6  inc     eax
0x1800eb1b8  movsxd  rcx, eax
0x1800eb1bb  mov     rax, 0C92A69C000h
0x1800eb1c5  jmp     short loc_1800EB1DC
0x1800eb1c7  lea     eax, [rsi+1]
0x1800eb1ca  jmp     short loc_1800EB1B8
0x1800eb1cc  lea     eax, [rsi+18h]
0x1800eb1cf  movsxd  rcx, eax
0x1800eb1d2  mov     rax, 861C46800h
0x1800eb1dc  imul    rcx, rax
0x1800eb1e0  sub     r12, rcx
0x1800eb1e3  cmp     r15, [r14]
0x1800eb1e6  jnz     loc_1800EB2E1
0x1800eb1ec  mov     r8, r13
0x1800eb1ef  lea     rdx, [rsp+140h+var_E8+8]
0x1800eb1f4  mov     rcx, r14
0x1800eb1f7  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800eb1fc  movups  xmm6, xmmword ptr [rax]
0x1800eb1ff  mov     rdx, [rax+10h]
0x1800eb203  cmp     byte ptr [rdx+19h], 0
0x1800eb207  jnz     short loc_1800EB264
0x1800eb209  add     rdx, 20h ; ' '
0x1800eb20d  mov     r14, [rdx+10h]
0x1800eb211  cmp     qword ptr [rdx+18h], 7
0x1800eb216  jbe     short loc_1800EB21B
0x1800eb218  mov     rdx, [rdx]; S2
0x1800eb21b  mov     rsi, [r13+10h]
0x1800eb21f  cmp     qword ptr [r13+18h], 7
0x1800eb224  jbe     short loc_1800EB22C
0x1800eb226  mov     rcx, [r13+0]
0x1800eb22a  jmp     short loc_1800EB22F
0x1800eb22c  mov     rcx, r13; S1
0x1800eb22f  mov     r8, rsi
0x1800eb232  cmp     r14, rsi
0x1800eb235  cmovb   r8, r14; N
0x1800eb239  call    wmemcmp
0x1800eb23e  test    eax, eax
0x1800eb240  jz      short loc_1800EB246
0x1800eb242  jns     short loc_1800EB255
0x1800eb244  jmp     short loc_1800EB24B
0x1800eb246  cmp     rsi, r14
0x1800eb249  jnb     short loc_1800EB24F
0x1800eb24b  mov     al, 0FFh
0x1800eb24d  jmp     short loc_1800EB257
0x1800eb24f  jbe     loc_1800EB2F1
0x1800eb255  mov     al, 1
0x1800eb257  test    al, al
0x1800eb259  jns     loc_1800EB2F1
0x1800eb25f  mov     r14, [rsp+140h+var_110]
0x1800eb264  mov     rax, 38E38E38E38E38Eh
0x1800eb26e  cmp     [r14+8], rax
0x1800eb272  jz      loc_1800EB400
0x1800eb278  mov     r14, [r14]
0x1800eb27b  mov     rax, [rsp+140h+var_110]
0x1800eb280  mov     [rbp+40h+var_A8], rax
0x1800eb284  mov     [rbp+40h+var_A0], 0
0x1800eb28c  mov     ecx, 48h ; 'H'; Size
0x1800eb291  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eb296  mov     r15, rax
0x1800eb299  mov     [rbp+40h+var_A0], rax
0x1800eb29d  mov     rdx, r13
0x1800eb2a0  lea     rcx, [rax+20h]
0x1800eb2a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800eb2a9  mov     [r15+40h], r12
0x1800eb2ad  mov     [r15], r14
0x1800eb2b0  mov     [r15+8], r14
0x1800eb2b4  mov     [r15+10h], r14
0x1800eb2b8  mov     word ptr [r15+18h], 0
0x1800eb2bf  mov     [rbp+40h+var_A0], 0
0x1800eb2c7  movdqu  [rsp+140h+var_E8+8], xmm6
0x1800eb2cd  mov     r8, r15
0x1800eb2d0  lea     rdx, [rsp+140h+var_E8+8]
0x1800eb2d5  mov     rcx, [rsp+140h+var_110]
0x1800eb2da  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>,void *> * const)
0x1800eb2df  jmp     short loc_1800EB2F1
0x1800eb2e1  cmp     r12, [r15+40h]
0x1800eb2e5  jz      short loc_1800EB2E9
0x1800eb2e7  jl      short loc_1800EB2ED
0x1800eb2e9  mov     r12, [r15+40h]
0x1800eb2ed  mov     [r15+40h], r12
0x1800eb2f1  add     r13, 20h ; ' '
0x1800eb2f5  cmp     r13, [rbp+40h+var_C0]
0x1800eb2f9  mov     rcx, [rbp+40h+var_B8]
0x1800eb2fd  jnz     loc_1800EB0DC
0x1800eb303  lea     rcx, [rbp+40h+var_98]
0x1800eb307  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800eb30c  nop
0x1800eb30d  lea     rcx, [rbp+40h+S1]; void *
0x1800eb311  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb316  mov     rcx, [rbx+10h]
0x1800eb31a  xor     r13d, r13d
0x1800eb31d  cmp     [rcx+19h], r13b
0x1800eb321  jz      short loc_1800EB344
0x1800eb323  mov     rax, [rbx+8]
0x1800eb327  jmp     short loc_1800EB336
0x1800eb329  cmp     rbx, [rax+10h]
0x1800eb32d  jnz     short loc_1800EB33C
0x1800eb32f  mov     rbx, rax
0x1800eb332  mov     rax, [rax+8]
0x1800eb336  cmp     [rax+19h], r13b
  ... truncated ...
```
