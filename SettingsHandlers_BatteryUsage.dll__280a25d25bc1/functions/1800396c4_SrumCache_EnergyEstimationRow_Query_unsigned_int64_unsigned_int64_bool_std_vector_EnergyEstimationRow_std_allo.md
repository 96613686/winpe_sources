# SrumCache<EnergyEstimationRow>::Query(unsigned __int64,unsigned __int64,bool,std::vector<EnergyEstimationRow,std::allocator<EnergyEstimationRow>> &)

- ea: `0x1800396c4`
- end: `0x180039953`
- name: `?Query@?$SrumCache@UEnergyEstimationRow@@@@QEAAK_K0_NAEAV?$vector@UEnergyEstimationRow@@V?$allocator@UEnergyEstimationRow@@@std@@@std@@@Z`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800390c0`

## callees

- `0x18000a13c`
- `0x18001e360`
- `0x180022c0c`
- `0x180037d3c`
- `0x180038d7c`
- `0x180039048`
- `0x1800396c4`
- `0x18003b080`
- `0x18003b65c`
- `0x18003b6f4`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800396f1`
- `msvcp_win!_Xtime_get_ticks` at `0x1800398d0`
- `msvcp_win!_Xtime_get_ticks` at `0x1800396f1`
- `msvcp_win!_Xtime_get_ticks` at `0x1800398d0`

## string_xrefs

- `0x18003975b`: `onecoreuap\shell\coresettinghandlers\batteryusage\lib\SrumCache.h`
- `0x1800397cc`: `onecoreuap\shell\coresettinghandlers\batteryusage\lib\SrumCache.h`

## pseudocode

```c
__int64 __fastcall SrumCache<EnergyEstimationRow>::Query(_QWORD *a1, __int64 a2, __int64 a3, char a4, __int64 a5)
{
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r14
  __int64 ticks; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 *v11; // rbx
  __int64 v12; // r12
  unsigned __int64 v13; // r8
  int v14; // eax
  unsigned int v15; // ebx
  unsigned __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // r15d
  __int64 v20; // r15
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // r11
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // [rsp+20h] [rbp-50h]
  __int64 v32; // [rsp+40h] [rbp-30h] BYREF
  __int64 v33; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+50h] [rbp-20h] BYREF
  __int64 v35; // [rsp+58h] [rbp-18h] BYREF
  char v36[16]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v38; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v39; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v40; // [rsp+C0h] [rbp+50h] BYREF

  v40 = a3;
  v39 = a2;
  v6 = a3;
  v7 = a2;
  ticks = _Xtime_get_ticks();
  v10 = a1[4];
  v11 = a1 + 5;
  v12 = 0;
  v34 = ticks;
  v38 = 0;
  v33 = 0;
  if ( !v10 && !*v11 )
    goto LABEL_8;
  if ( v7 >= v10 )
    goto LABEL_14;
  if ( v10 )
  {
    v13 = v6;
    if ( v10 < v6 )
      v13 = v10;
  }
  else
  {
LABEL_8:
    v13 = v6;
  }
  v14 = SrumCache<EnergyEstimationRow>::QuerySrumData(a1, v7, v13, &v38);
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
  if ( (v15 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\SrumCache.h",
      (const char *)v15,
      v31);
    return v15;
  }
  v12 = v38;
  v11 = a1 + 5;
  v33 = v38;
LABEL_14:
  if ( a1[4] )
  {
    v11 = a1 + 5;
    if ( a1[5] )
    {
      if ( v6 > *v11 )
      {
        v17 = v7;
        if ( *v11 > v7 )
          v17 = *v11;
        v18 = SrumCache<EnergyEstimationRow>::QuerySrumData(a1, v17, v6, &v38);
        v19 = v18;
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        if ( (v19 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\SrumCache.h",
            (const char *)v19,
            v31);
          return v19;
        }
        v33 = v38 + v12;
      }
    }
  }
  v20 = 0;
  v38 = 0;
  v32 = 0;
  if ( !a4 && ((v21 = a1[4]) != 0 || *v11) && v6 >= v21 && v7 <= *v11 )
  {
    if ( v21 < v7 )
      v7 = a1[4];
    if ( *v11 > v6 )
      v6 = *v11;
  }
  else
  {
    v22 = a1[4];
    if ( v22 && *v11 && v22 < v7 )
    {
      v23 = v7;
      if ( *v11 < v7 )
        v23 = *v11;
      SrumCache<EnergyEstimationRow>::Evict(a1, v22, v23, &v38);
      v20 = v38;
      v32 = v38;
    }
    v24 = a1[4];
    if ( v24 )
    {
      v25 = *v11;
      if ( *v11 )
      {
        if ( v25 > v6 )
        {
          v26 = v6;
          if ( v24 > v6 )
            v26 = a1[4];
          SrumCache<EnergyEstimationRow>::Evict(a1, v26, v25, &v38);
          v32 = v38 + v20;
        }
      }
    }
  }
  *v11 = v6;
  a1[4] = v7;
  std::_Tree<std::_Tmap_traits<unsigned __int64,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,1>>::upper_bound(
    a1 + 7,
    &v38,
    &v40);
  v27 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned __int64,EnergyEstimationRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,EnergyEstimationRow>>,1>>::lower_bound(
                    a1 + 7,
                    &v35,
                    &v39);
  std::transform<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,EnergyEstimationRow>>>>,std::back_insert_iterator<std::vector<EnergyEstimationRow>>,_lambda_94dea711e5b3750c7dd36827bebc0f75_>(
    v36,
    *v27,
    v28,
    a5);
  v38 = _Xtime_get_ticks() - v34;
  std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(&v34, &v38);
  v38 = a1[8];
  v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v29, v30);
  UsageGraphTelemetry::SrumCacheQueryStats<unsigned short const *,double,unsigned __int64 &,unsigned __int64 &,unsigned __int64,unsigned __int64 &,unsigned __int64 &>(
    &v35,
    &v34,
    &v39,
    &v40,
    &v38,
    &v33,
    &v32);
  return 0;
}

```

## disassembly

```asm
0x1800396c4  mov     [rsp-38h+arg_18], rbx
0x1800396c9  mov     [rsp-38h+arg_10], r8
0x1800396ce  mov     [rsp-38h+arg_8], rdx
0x1800396d3  push    rbp
0x1800396d4  push    rsi
0x1800396d5  push    rdi
0x1800396d6  push    r12
0x1800396d8  push    r13
0x1800396da  push    r14
0x1800396dc  push    r15
0x1800396de  mov     rbp, rsp
0x1800396e1  sub     rsp, 70h
0x1800396e5  mov     r13b, r9b
0x1800396e8  mov     rdi, r8
0x1800396eb  mov     r14, rdx
0x1800396ee  mov     rsi, rcx
0x1800396f1  call    cs:__imp__Xtime_get_ticks
0x1800396f7  mov     rcx, [rsi+20h]
0x1800396fb  lea     rbx, [rsi+28h]
0x1800396ff  xor     r12d, r12d
0x180039702  mov     [rbp+var_20], rax
0x180039706  mov     [rbp+arg_0], 0
0x18003970e  mov     [rbp+var_28], r12
0x180039712  test    rcx, rcx
0x180039715  jnz     short loc_18003971C
0x180039717  cmp     [rbx], r12
0x18003971a  jz      short loc_180039732
0x18003971c  cmp     r14, rcx
0x18003971f  jnb     short loc_180039782
0x180039721  test    rcx, rcx
0x180039724  jz      short loc_180039732
0x180039726  cmp     rcx, rdi
0x180039729  mov     r8, rdi
0x18003972c  cmovb   r8, rcx
0x180039730  jmp     short loc_180039735
0x180039732  mov     r8, rdi
0x180039735  lea     r9, [rbp+arg_0]
0x180039739  mov     rdx, r14
0x18003973c  mov     rcx, rsi
0x18003973f  call    ?QuerySrumData@?$SrumCache@UEnergyEstimationRow@@@@AEAAK_K0PEA_K@Z; SrumCache<EnergyEstimationRow>::QuerySrumData(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180039744  mov     ebx, eax
0x180039746  test    eax, eax
0x180039748  jle     short loc_180039753
0x18003974a  movzx   ebx, ax
0x18003974d  or      ebx, 80070000h
0x180039753  test    ebx, ebx
0x180039755  jns     short loc_180039776
0x180039757  mov     rcx, [rbp+38h]; this
0x18003975b  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x180039762  mov     r9d, ebx; char *
0x180039765  mov     edx, 1Eh; void *
0x18003976a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003976f  mov     eax, ebx
0x180039771  jmp     loc_18003993B
0x180039776  mov     r12, [rbp+arg_0]
0x18003977a  lea     rbx, [rsi+28h]
0x18003977e  mov     [rbp+var_28], r12
0x180039782  cmp     qword ptr [rsi+20h], 0
0x180039787  jz      short loc_1800397F0
0x180039789  lea     rbx, [rsi+28h]
0x18003978d  cmp     qword ptr [rbx], 0
0x180039791  jz      short loc_1800397F0
0x180039793  cmp     rdi, [rbx]
0x180039796  jbe     short loc_1800397F0
0x180039798  cmp     [rbx], r14
0x18003979b  lea     r9, [rbp+arg_0]
0x18003979f  mov     rdx, r14
0x1800397a2  mov     r8, rdi
0x1800397a5  cmova   rdx, [rbx]
0x1800397a9  mov     rcx, rsi
0x1800397ac  call    ?QuerySrumData@?$SrumCache@UEnergyEstimationRow@@@@AEAAK_K0PEA_K@Z; SrumCache<EnergyEstimationRow>::QuerySrumData(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800397b1  mov     r15d, eax
0x1800397b4  test    eax, eax
0x1800397b6  jle     short loc_1800397C3
0x1800397b8  movzx   r15d, ax
0x1800397bc  or      r15d, 80070000h
0x1800397c3  test    r15d, r15d
0x1800397c6  jns     short loc_1800397E8
0x1800397c8  mov     rcx, [rbp+38h]; this
0x1800397cc  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x1800397d3  mov     r9d, r15d; char *
0x1800397d6  mov     edx, 24h ; '$'; void *
0x1800397db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800397e0  mov     eax, r15d
0x1800397e3  jmp     loc_18003993B
0x1800397e8  add     r12, [rbp+arg_0]
0x1800397ec  mov     [rbp+var_28], r12
0x1800397f0  xor     r15d, r15d
0x1800397f3  mov     [rbp+arg_0], 0
0x1800397fb  mov     [rbp+var_30], r15
0x1800397ff  test    r13b, r13b
0x180039802  jnz     short loc_18003982C
0x180039804  mov     rax, [rsi+20h]
0x180039808  test    rax, rax
0x18003980b  jnz     short loc_180039812
0x18003980d  cmp     [rbx], r15
0x180039810  jz      short loc_18003982C
0x180039812  cmp     rdi, rax
0x180039815  jb      short loc_18003982C
0x180039817  cmp     r14, [rbx]
0x18003981a  ja      short loc_18003982C
0x18003981c  cmp     rax, r14
0x18003981f  cmovb   r14, rax
0x180039823  cmp     [rbx], rdi
0x180039826  cmova   rdi, [rbx]
0x18003982a  jmp     short loc_180039891
0x18003982c  mov     rdx, [rsi+20h]
0x180039830  test    rdx, rdx
0x180039833  jz      short loc_18003985D
0x180039835  cmp     [rbx], r15
0x180039838  jz      short loc_18003985D
0x18003983a  cmp     rdx, r14
0x18003983d  jnb     short loc_18003985D
0x18003983f  cmp     [rbx], r14
0x180039842  lea     r9, [rbp+arg_0]
0x180039846  mov     r8, r14
0x180039849  mov     rcx, rsi
0x18003984c  cmovb   r8, [rbx]
0x180039850  call    ?Evict@?$SrumCache@UEnergyEstimationRow@@@@AEAAX_K0PEA_K@Z; SrumCache<EnergyEstimationRow>::Evict(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180039855  mov     r15, [rbp+arg_0]
0x180039859  mov     [rbp+var_30], r15
0x18003985d  mov     rax, [rsi+20h]
0x180039861  test    rax, rax
0x180039864  jz      short loc_180039891
0x180039866  mov     r8, [rbx]
0x180039869  test    r8, r8
0x18003986c  jz      short loc_180039891
0x18003986e  cmp     r8, rdi
0x180039871  jbe     short loc_180039891
0x180039873  cmp     rax, rdi
0x180039876  lea     r9, [rbp+arg_0]
0x18003987a  mov     rdx, rdi
0x18003987d  mov     rcx, rsi
0x180039880  cmova   rdx, rax
0x180039884  call    ?Evict@?$SrumCache@UEnergyEstimationRow@@@@AEAAX_K0PEA_K@Z; SrumCache<EnergyEstimationRow>::Evict(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180039889  add     r15, [rbp+arg_0]
0x18003988d  mov     [rbp+var_30], r15
0x180039891  lea     r8, [rbp+arg_10]
0x180039895  mov     [rbx], rdi
0x180039898  lea     rdx, [rbp+arg_0]
0x18003989c  mov     [rsi+20h], r14
0x1800398a0  lea     rcx, [rsi+38h]
0x1800398a4  call    ?upper_bound@?$_Tree@V?$_Tmap_traits@_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@5@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,1>>::upper_bound(unsigned __int64 const &)
0x1800398a9  lea     r8, [rbp+arg_8]
0x1800398ad  lea     rdx, [rbp+var_18]
0x1800398b1  lea     rcx, [rsi+38h]
0x1800398b5  mov     r11, [rax]
0x1800398b8  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@_KUEnergyEstimationRow@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,EnergyEstimationRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,EnergyEstimationRow>>,1>>::lower_bound(unsigned __int64 const &)
0x1800398bd  mov     r9, [rbp+arg_20]
0x1800398c1  lea     rcx, [rbp+var_10]
0x1800398c5  mov     r8, r11
0x1800398c8  mov     rdx, [rax]
0x1800398cb  call    ??$transform@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@UEnergyEstimationRow@@V?$allocator@UEnergyEstimationRow@@@std@@@std@@@2@V_lambda_94dea711e5b3750c7dd36827bebc0f75_@@@std@@YA?AV?$back_insert_iterator@V?$vector@UEnergyEstimationRow@@V?$allocator@UEnergyEstimationRow@@@std@@@std@@@0@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@std@@@std@@@0@0V10@V_lambda_94dea711e5b3750c7dd36827bebc0f75_@@@Z; std::transform<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,EnergyEstimationRow>>>>,std::back_insert_iterator<std::vector<EnergyEstimationRow>>,_lambda_94dea711e5b3750c7dd36827bebc0f75_>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,EnergyEstimationRow>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,EnergyEstimationRow>>>>,std::back_insert_iterator<std::vector<EnergyEstimationRow>>,_lambda_94dea711e5b3750c7dd36827bebc0f75_)
0x1800398d0  call    cs:__imp__Xtime_get_ticks
0x1800398d6  sub     rax, [rbp+var_20]
0x1800398da  lea     rdx, [rbp+arg_0]
0x1800398de  lea     rcx, [rbp+var_20]
0x1800398e2  mov     [rbp+arg_0], rax
0x1800398e6  call    ??$?0_JU?$ratio@$00$0JIJGIA@@std@@$0A@@?$duration@NU?$ratio@$00$00@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@@Z; std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x1800398eb  mov     r9, [rsi+40h]
0x1800398ef  mov     rcx, rsi
0x1800398f2  movsd   xmm1, [rbp+var_20]
0x1800398f7  movsd   [rbp+var_20], xmm1
0x1800398fc  mov     [rbp+arg_0], r9
0x180039900  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039905  mov     [rbp+var_18], rax
0x180039909  lea     r9, [rbp+arg_10]
0x18003990d  lea     rax, [rbp+var_30]
0x180039911  mov     [rsp+70h+var_40], rax
0x180039916  lea     r8, [rbp+arg_8]
0x18003991a  lea     rax, [rbp+var_28]
0x18003991e  mov     [rsp+70h+var_48], rax
0x180039923  lea     rdx, [rbp+var_20]
0x180039927  lea     rax, [rbp+arg_0]
0x18003992b  lea     rcx, [rbp+var_18]
0x18003992f  mov     [rsp+70h+var_50], rax
0x180039934  call    ??$SrumCacheQueryStats@PEBGNAEA_KAEA_K_KAEA_KAEA_K@UsageGraphTelemetry@@SAX$$QEAPEBG$$QEANAEA_K2$$QEA_K22@Z; UsageGraphTelemetry::SrumCacheQueryStats<ushort const *,double,unsigned __int64 &,unsigned __int64 &,unsigned __int64,unsigned __int64 &,unsigned __int64 &>(ushort const * &&,double &&,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &&,unsigned __int64 &,unsigned __int64 &)
0x180039939  xor     eax, eax
0x18003993b  mov     rbx, [rsp+70h+arg_18]
0x180039943  add     rsp, 70h
0x180039947  pop     r15
0x180039949  pop     r14
0x18003994b  pop     r13
0x18003994d  pop     r12
0x18003994f  pop     rdi
0x180039950  pop     rsi
0x180039951  pop     rbp
0x180039952  retn
```
