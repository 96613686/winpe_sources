# SrumCache<BatteryDrainRow>::Query(unsigned __int64,unsigned __int64,bool,std::vector<BatteryDrainRow,std::allocator<BatteryDrainRow>> &)

- ea: `0x18003942c`
- end: `0x1800396bb`
- name: `?Query@?$SrumCache@UBatteryDrainRow@@@@QEAAK_K0_NAEAV?$vector@UBatteryDrainRow@@V?$allocator@UBatteryDrainRow@@@std@@@std@@@Z`
- size: `655`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18003995c`
- `0x180039fec`
- `0x18003a55c`
- `0x18003aa90`

## callees

- `0x18000a13c`
- `0x18001e360`
- `0x180022c0c`
- `0x180037d3c`
- `0x180038cdc`
- `0x180038fd0`
- `0x18003942c`
- `0x18003af28`
- `0x18003b65c`
- `0x18003b6f4`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180039459`
- `msvcp_win!_Xtime_get_ticks` at `0x180039638`
- `msvcp_win!_Xtime_get_ticks` at `0x180039459`
- `msvcp_win!_Xtime_get_ticks` at `0x180039638`

## string_xrefs

- `0x1800394c3`: `onecoreuap\shell\coresettinghandlers\batteryusage\lib\SrumCache.h`
- `0x180039534`: `onecoreuap\shell\coresettinghandlers\batteryusage\lib\SrumCache.h`

## pseudocode

```c
__int64 __fastcall SrumCache<BatteryDrainRow>::Query(_QWORD *a1, __int64 a2, __int64 a3, char a4, __int64 a5)
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
  v14 = SrumCache<BatteryDrainRow>::QuerySrumData(a1, v7, v13, &v38);
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
        v18 = SrumCache<BatteryDrainRow>::QuerySrumData(a1, v17, v6, &v38);
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
      SrumCache<BatteryDrainRow>::Evict(a1, v22, v23, &v38);
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
          SrumCache<BatteryDrainRow>::Evict(a1, v26, v25, &v38);
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
  std::transform<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,BatteryDrainRow>>>>,std::back_insert_iterator<std::vector<BatteryDrainRow>>,_lambda_b6c155258daca20797b1c812b997df34_>(
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
0x18003942c  mov     [rsp-38h+arg_18], rbx
0x180039431  mov     [rsp-38h+arg_10], r8
0x180039436  mov     [rsp-38h+arg_8], rdx
0x18003943b  push    rbp
0x18003943c  push    rsi
0x18003943d  push    rdi
0x18003943e  push    r12
0x180039440  push    r13
0x180039442  push    r14
0x180039444  push    r15
0x180039446  mov     rbp, rsp
0x180039449  sub     rsp, 70h
0x18003944d  mov     r13b, r9b
0x180039450  mov     rdi, r8
0x180039453  mov     r14, rdx
0x180039456  mov     rsi, rcx
0x180039459  call    cs:__imp__Xtime_get_ticks
0x18003945f  mov     rcx, [rsi+20h]
0x180039463  lea     rbx, [rsi+28h]
0x180039467  xor     r12d, r12d
0x18003946a  mov     [rbp+var_20], rax
0x18003946e  mov     [rbp+arg_0], 0
0x180039476  mov     [rbp+var_28], r12
0x18003947a  test    rcx, rcx
0x18003947d  jnz     short loc_180039484
0x18003947f  cmp     [rbx], r12
0x180039482  jz      short loc_18003949A
0x180039484  cmp     r14, rcx
0x180039487  jnb     short loc_1800394EA
0x180039489  test    rcx, rcx
0x18003948c  jz      short loc_18003949A
0x18003948e  cmp     rcx, rdi
0x180039491  mov     r8, rdi
0x180039494  cmovb   r8, rcx
0x180039498  jmp     short loc_18003949D
0x18003949a  mov     r8, rdi
0x18003949d  lea     r9, [rbp+arg_0]
0x1800394a1  mov     rdx, r14
0x1800394a4  mov     rcx, rsi
0x1800394a7  call    ?QuerySrumData@?$SrumCache@UBatteryDrainRow@@@@AEAAK_K0PEA_K@Z; SrumCache<BatteryDrainRow>::QuerySrumData(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800394ac  mov     ebx, eax
0x1800394ae  test    eax, eax
0x1800394b0  jle     short loc_1800394BB
0x1800394b2  movzx   ebx, ax
0x1800394b5  or      ebx, 80070000h
0x1800394bb  test    ebx, ebx
0x1800394bd  jns     short loc_1800394DE
0x1800394bf  mov     rcx, [rbp+38h]; this
0x1800394c3  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x1800394ca  mov     r9d, ebx; char *
0x1800394cd  mov     edx, 1Eh; void *
0x1800394d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800394d7  mov     eax, ebx
0x1800394d9  jmp     loc_1800396A3
0x1800394de  mov     r12, [rbp+arg_0]
0x1800394e2  lea     rbx, [rsi+28h]
0x1800394e6  mov     [rbp+var_28], r12
0x1800394ea  cmp     qword ptr [rsi+20h], 0
0x1800394ef  jz      short loc_180039558
0x1800394f1  lea     rbx, [rsi+28h]
0x1800394f5  cmp     qword ptr [rbx], 0
0x1800394f9  jz      short loc_180039558
0x1800394fb  cmp     rdi, [rbx]
0x1800394fe  jbe     short loc_180039558
0x180039500  cmp     [rbx], r14
0x180039503  lea     r9, [rbp+arg_0]
0x180039507  mov     rdx, r14
0x18003950a  mov     r8, rdi
0x18003950d  cmova   rdx, [rbx]
0x180039511  mov     rcx, rsi
0x180039514  call    ?QuerySrumData@?$SrumCache@UBatteryDrainRow@@@@AEAAK_K0PEA_K@Z; SrumCache<BatteryDrainRow>::QuerySrumData(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180039519  mov     r15d, eax
0x18003951c  test    eax, eax
0x18003951e  jle     short loc_18003952B
0x180039520  movzx   r15d, ax
0x180039524  or      r15d, 80070000h
0x18003952b  test    r15d, r15d
0x18003952e  jns     short loc_180039550
0x180039530  mov     rcx, [rbp+38h]; this
0x180039534  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x18003953b  mov     r9d, r15d; char *
0x18003953e  mov     edx, 24h ; '$'; void *
0x180039543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039548  mov     eax, r15d
0x18003954b  jmp     loc_1800396A3
0x180039550  add     r12, [rbp+arg_0]
0x180039554  mov     [rbp+var_28], r12
0x180039558  xor     r15d, r15d
0x18003955b  mov     [rbp+arg_0], 0
0x180039563  mov     [rbp+var_30], r15
0x180039567  test    r13b, r13b
0x18003956a  jnz     short loc_180039594
0x18003956c  mov     rax, [rsi+20h]
0x180039570  test    rax, rax
0x180039573  jnz     short loc_18003957A
0x180039575  cmp     [rbx], r15
0x180039578  jz      short loc_180039594
0x18003957a  cmp     rdi, rax
0x18003957d  jb      short loc_180039594
0x18003957f  cmp     r14, [rbx]
0x180039582  ja      short loc_180039594
0x180039584  cmp     rax, r14
0x180039587  cmovb   r14, rax
0x18003958b  cmp     [rbx], rdi
0x18003958e  cmova   rdi, [rbx]
0x180039592  jmp     short loc_1800395F9
0x180039594  mov     rdx, [rsi+20h]
0x180039598  test    rdx, rdx
0x18003959b  jz      short loc_1800395C5
0x18003959d  cmp     [rbx], r15
0x1800395a0  jz      short loc_1800395C5
0x1800395a2  cmp     rdx, r14
0x1800395a5  jnb     short loc_1800395C5
0x1800395a7  cmp     [rbx], r14
0x1800395aa  lea     r9, [rbp+arg_0]
0x1800395ae  mov     r8, r14
0x1800395b1  mov     rcx, rsi
0x1800395b4  cmovb   r8, [rbx]
0x1800395b8  call    ?Evict@?$SrumCache@UBatteryDrainRow@@@@AEAAX_K0PEA_K@Z; SrumCache<BatteryDrainRow>::Evict(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800395bd  mov     r15, [rbp+arg_0]
0x1800395c1  mov     [rbp+var_30], r15
0x1800395c5  mov     rax, [rsi+20h]
0x1800395c9  test    rax, rax
0x1800395cc  jz      short loc_1800395F9
0x1800395ce  mov     r8, [rbx]
0x1800395d1  test    r8, r8
0x1800395d4  jz      short loc_1800395F9
0x1800395d6  cmp     r8, rdi
0x1800395d9  jbe     short loc_1800395F9
0x1800395db  cmp     rax, rdi
0x1800395de  lea     r9, [rbp+arg_0]
0x1800395e2  mov     rdx, rdi
0x1800395e5  mov     rcx, rsi
0x1800395e8  cmova   rdx, rax
0x1800395ec  call    ?Evict@?$SrumCache@UBatteryDrainRow@@@@AEAAX_K0PEA_K@Z; SrumCache<BatteryDrainRow>::Evict(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800395f1  add     r15, [rbp+arg_0]
0x1800395f5  mov     [rbp+var_30], r15
0x1800395f9  lea     r8, [rbp+arg_10]
0x1800395fd  mov     [rbx], rdi
0x180039600  lea     rdx, [rbp+arg_0]
0x180039604  mov     [rsi+20h], r14
0x180039608  lea     rcx, [rsi+38h]
0x18003960c  call    ?upper_bound@?$_Tree@V?$_Tmap_traits@_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@5@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,1>>::upper_bound(unsigned __int64 const &)
0x180039611  lea     r8, [rbp+arg_8]
0x180039615  lea     rdx, [rbp+var_18]
0x180039619  lea     rcx, [rsi+38h]
0x18003961d  mov     r11, [rax]
0x180039620  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@_KUEnergyEstimationRow@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,EnergyEstimationRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,EnergyEstimationRow>>,1>>::lower_bound(unsigned __int64 const &)
0x180039625  mov     r9, [rbp+arg_20]
0x180039629  lea     rcx, [rbp+var_10]
0x18003962d  mov     r8, r11
0x180039630  mov     rdx, [rax]
0x180039633  call    ??$transform@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUBatteryDrainRow@@@std@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@UBatteryDrainRow@@V?$allocator@UBatteryDrainRow@@@std@@@std@@@2@V_lambda_b6c155258daca20797b1c812b997df34_@@@std@@YA?AV?$back_insert_iterator@V?$vector@UBatteryDrainRow@@V?$allocator@UBatteryDrainRow@@@std@@@std@@@0@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUBatteryDrainRow@@@std@@@std@@@std@@@0@0V10@V_lambda_b6c155258daca20797b1c812b997df34_@@@Z; std::transform<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,BatteryDrainRow>>>>,std::back_insert_iterator<std::vector<BatteryDrainRow>>,_lambda_b6c155258daca20797b1c812b997df34_>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,BatteryDrainRow>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,BatteryDrainRow>>>>,std::back_insert_iterator<std::vector<BatteryDrainRow>>,_lambda_b6c155258daca20797b1c812b997df34_)
0x180039638  call    cs:__imp__Xtime_get_ticks
0x18003963e  sub     rax, [rbp+var_20]
0x180039642  lea     rdx, [rbp+arg_0]
0x180039646  lea     rcx, [rbp+var_20]
0x18003964a  mov     [rbp+arg_0], rax
0x18003964e  call    ??$?0_JU?$ratio@$00$0JIJGIA@@std@@$0A@@?$duration@NU?$ratio@$00$00@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@@Z; std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x180039653  mov     r9, [rsi+40h]
0x180039657  mov     rcx, rsi
0x18003965a  movsd   xmm1, [rbp+var_20]
0x18003965f  movsd   [rbp+var_20], xmm1
0x180039664  mov     [rbp+arg_0], r9
0x180039668  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003966d  mov     [rbp+var_18], rax
0x180039671  lea     r9, [rbp+arg_10]
0x180039675  lea     rax, [rbp+var_30]
0x180039679  mov     [rsp+70h+var_40], rax
0x18003967e  lea     r8, [rbp+arg_8]
0x180039682  lea     rax, [rbp+var_28]
0x180039686  mov     [rsp+70h+var_48], rax
0x18003968b  lea     rdx, [rbp+var_20]
0x18003968f  lea     rax, [rbp+arg_0]
0x180039693  lea     rcx, [rbp+var_18]
0x180039697  mov     [rsp+70h+var_50], rax
0x18003969c  call    ??$SrumCacheQueryStats@PEBGNAEA_KAEA_K_KAEA_KAEA_K@UsageGraphTelemetry@@SAX$$QEAPEBG$$QEANAEA_K2$$QEA_K22@Z; UsageGraphTelemetry::SrumCacheQueryStats<ushort const *,double,unsigned __int64 &,unsigned __int64 &,unsigned __int64,unsigned __int64 &,unsigned __int64 &>(ushort const * &&,double &&,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &&,unsigned __int64 &,unsigned __int64 &)
0x1800396a1  xor     eax, eax
0x1800396a3  mov     rbx, [rsp+70h+arg_18]
0x1800396ab  add     rsp, 70h
0x1800396af  pop     r15
0x1800396b1  pop     r14
0x1800396b3  pop     r13
0x1800396b5  pop     r12
0x1800396b7  pop     rdi
0x1800396b8  pop     rsi
0x1800396b9  pop     rbp
0x1800396ba  retn
```
