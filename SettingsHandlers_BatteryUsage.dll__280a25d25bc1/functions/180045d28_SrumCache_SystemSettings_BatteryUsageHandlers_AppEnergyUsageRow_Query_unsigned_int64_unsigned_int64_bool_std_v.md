# SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::Query(unsigned __int64,unsigned __int64,bool,std::vector<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow,std::allocator<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>> &)

- ea: `0x180045d28`
- end: `0x180045fb7`
- name: `?Query@?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@QEAAK_K0_NAEAV?$vector@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@V?$allocator@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@Z`
- size: `655`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18003f910`
- `0x18003fa2c`

## callees

- `0x18000a13c`
- `0x18001e360`
- `0x180022c0c`
- `0x180037d3c`
- `0x18003b65c`
- `0x18003b6f4`
- `0x18003d888`
- `0x18003f11c`
- `0x180045d28`
- `0x180046060`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180045d55`
- `msvcp_win!_Xtime_get_ticks` at `0x180045f34`
- `msvcp_win!_Xtime_get_ticks` at `0x180045d55`
- `msvcp_win!_Xtime_get_ticks` at `0x180045f34`

## string_xrefs

- `0x180045dbf`: `onecoreuap\shell\coresettinghandlers\batteryusage\lib\SrumCache.h`
- `0x180045e30`: `onecoreuap\shell\coresettinghandlers\batteryusage\lib\SrumCache.h`

## pseudocode

```c
__int64 __fastcall SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::Query(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5)
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
  v14 = SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::QuerySrumData(a1, v7, v13, &v38);
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
        v18 = SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::QuerySrumData(a1, v17, v6, &v38);
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
      SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::Evict(a1, v22, v23, &v38);
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
          SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::Evict(a1, v26, v25, &v38);
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
  std::transform<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>>>,std::back_insert_iterator<std::vector<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,_lambda_1e66152caec4462226a90d223302e186_>(
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
0x180045d28  mov     [rsp-38h+arg_18], rbx
0x180045d2d  mov     [rsp-38h+arg_10], r8
0x180045d32  mov     [rsp-38h+arg_8], rdx
0x180045d37  push    rbp
0x180045d38  push    rsi
0x180045d39  push    rdi
0x180045d3a  push    r12
0x180045d3c  push    r13
0x180045d3e  push    r14
0x180045d40  push    r15
0x180045d42  mov     rbp, rsp
0x180045d45  sub     rsp, 70h
0x180045d49  mov     r13b, r9b
0x180045d4c  mov     rdi, r8
0x180045d4f  mov     r14, rdx
0x180045d52  mov     rsi, rcx
0x180045d55  call    cs:__imp__Xtime_get_ticks
0x180045d5b  mov     rcx, [rsi+20h]
0x180045d5f  lea     rbx, [rsi+28h]
0x180045d63  xor     r12d, r12d
0x180045d66  mov     [rbp+var_20], rax
0x180045d6a  mov     [rbp+arg_0], 0
0x180045d72  mov     [rbp+var_28], r12
0x180045d76  test    rcx, rcx
0x180045d79  jnz     short loc_180045D80
0x180045d7b  cmp     [rbx], r12
0x180045d7e  jz      short loc_180045D96
0x180045d80  cmp     r14, rcx
0x180045d83  jnb     short loc_180045DE6
0x180045d85  test    rcx, rcx
0x180045d88  jz      short loc_180045D96
0x180045d8a  cmp     rcx, rdi
0x180045d8d  mov     r8, rdi
0x180045d90  cmovb   r8, rcx
0x180045d94  jmp     short loc_180045D99
0x180045d96  mov     r8, rdi
0x180045d99  lea     r9, [rbp+arg_0]
0x180045d9d  mov     rdx, r14
0x180045da0  mov     rcx, rsi
0x180045da3  call    ?QuerySrumData@?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@AEAAK_K0PEA_K@Z; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::QuerySrumData(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180045da8  mov     ebx, eax
0x180045daa  test    eax, eax
0x180045dac  jle     short loc_180045DB7
0x180045dae  movzx   ebx, ax
0x180045db1  or      ebx, 80070000h
0x180045db7  test    ebx, ebx
0x180045db9  jns     short loc_180045DDA
0x180045dbb  mov     rcx, [rbp+38h]; this
0x180045dbf  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x180045dc6  mov     r9d, ebx; char *
0x180045dc9  mov     edx, 1Eh; void *
0x180045dce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045dd3  mov     eax, ebx
0x180045dd5  jmp     loc_180045F9F
0x180045dda  mov     r12, [rbp+arg_0]
0x180045dde  lea     rbx, [rsi+28h]
0x180045de2  mov     [rbp+var_28], r12
0x180045de6  cmp     qword ptr [rsi+20h], 0
0x180045deb  jz      short loc_180045E54
0x180045ded  lea     rbx, [rsi+28h]
0x180045df1  cmp     qword ptr [rbx], 0
0x180045df5  jz      short loc_180045E54
0x180045df7  cmp     rdi, [rbx]
0x180045dfa  jbe     short loc_180045E54
0x180045dfc  cmp     [rbx], r14
0x180045dff  lea     r9, [rbp+arg_0]
0x180045e03  mov     rdx, r14
0x180045e06  mov     r8, rdi
0x180045e09  cmova   rdx, [rbx]
0x180045e0d  mov     rcx, rsi
0x180045e10  call    ?QuerySrumData@?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@AEAAK_K0PEA_K@Z; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::QuerySrumData(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180045e15  mov     r15d, eax
0x180045e18  test    eax, eax
0x180045e1a  jle     short loc_180045E27
0x180045e1c  movzx   r15d, ax
0x180045e20  or      r15d, 80070000h
0x180045e27  test    r15d, r15d
0x180045e2a  jns     short loc_180045E4C
0x180045e2c  mov     rcx, [rbp+38h]; this
0x180045e30  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x180045e37  mov     r9d, r15d; char *
0x180045e3a  mov     edx, 24h ; '$'; void *
0x180045e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045e44  mov     eax, r15d
0x180045e47  jmp     loc_180045F9F
0x180045e4c  add     r12, [rbp+arg_0]
0x180045e50  mov     [rbp+var_28], r12
0x180045e54  xor     r15d, r15d
0x180045e57  mov     [rbp+arg_0], 0
0x180045e5f  mov     [rbp+var_30], r15
0x180045e63  test    r13b, r13b
0x180045e66  jnz     short loc_180045E90
0x180045e68  mov     rax, [rsi+20h]
0x180045e6c  test    rax, rax
0x180045e6f  jnz     short loc_180045E76
0x180045e71  cmp     [rbx], r15
0x180045e74  jz      short loc_180045E90
0x180045e76  cmp     rdi, rax
0x180045e79  jb      short loc_180045E90
0x180045e7b  cmp     r14, [rbx]
0x180045e7e  ja      short loc_180045E90
0x180045e80  cmp     rax, r14
0x180045e83  cmovb   r14, rax
0x180045e87  cmp     [rbx], rdi
0x180045e8a  cmova   rdi, [rbx]
0x180045e8e  jmp     short loc_180045EF5
0x180045e90  mov     rdx, [rsi+20h]
0x180045e94  test    rdx, rdx
0x180045e97  jz      short loc_180045EC1
0x180045e99  cmp     [rbx], r15
0x180045e9c  jz      short loc_180045EC1
0x180045e9e  cmp     rdx, r14
0x180045ea1  jnb     short loc_180045EC1
0x180045ea3  cmp     [rbx], r14
0x180045ea6  lea     r9, [rbp+arg_0]
0x180045eaa  mov     r8, r14
0x180045ead  mov     rcx, rsi
0x180045eb0  cmovb   r8, [rbx]
0x180045eb4  call    ?Evict@?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@AEAAX_K0PEA_K@Z; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::Evict(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180045eb9  mov     r15, [rbp+arg_0]
0x180045ebd  mov     [rbp+var_30], r15
0x180045ec1  mov     rax, [rsi+20h]
0x180045ec5  test    rax, rax
0x180045ec8  jz      short loc_180045EF5
0x180045eca  mov     r8, [rbx]
0x180045ecd  test    r8, r8
0x180045ed0  jz      short loc_180045EF5
0x180045ed2  cmp     r8, rdi
0x180045ed5  jbe     short loc_180045EF5
0x180045ed7  cmp     rax, rdi
0x180045eda  lea     r9, [rbp+arg_0]
0x180045ede  mov     rdx, rdi
0x180045ee1  mov     rcx, rsi
0x180045ee4  cmova   rdx, rax
0x180045ee8  call    ?Evict@?$SrumCache@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@@AEAAX_K0PEA_K@Z; SrumCache<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>::Evict(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180045eed  add     r15, [rbp+arg_0]
0x180045ef1  mov     [rbp+var_30], r15
0x180045ef5  lea     r8, [rbp+arg_10]
0x180045ef9  mov     [rbx], rdi
0x180045efc  lea     rdx, [rbp+arg_0]
0x180045f00  mov     [rsi+20h], r14
0x180045f04  lea     rcx, [rsi+38h]
0x180045f08  call    ?upper_bound@?$_Tree@V?$_Tmap_traits@_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@5@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,1>>::upper_bound(unsigned __int64 const &)
0x180045f0d  lea     r8, [rbp+arg_8]
0x180045f11  lea     rdx, [rbp+var_18]
0x180045f15  lea     rcx, [rsi+38h]
0x180045f19  mov     r11, [rax]
0x180045f1c  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@_KUEnergyEstimationRow@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUEnergyEstimationRow@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,EnergyEstimationRow,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,EnergyEstimationRow>>,1>>::lower_bound(unsigned __int64 const &)
0x180045f21  mov     r9, [rbp+arg_20]
0x180045f25  lea     rcx, [rbp+var_10]
0x180045f29  mov     r8, r11
0x180045f2c  mov     rdx, [rax]
0x180045f2f  call    ??$transform@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@V?$allocator@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@2@V_lambda_1e66152caec4462226a90d223302e186_@@@std@@YA?AV?$back_insert_iterator@V?$vector@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@V?$allocator@UAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@0@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUAppEnergyUsageRow@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@std@@@0@0V10@V_lambda_1e66152caec4462226a90d223302e186_@@@Z; std::transform<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>>>,std::back_insert_iterator<std::vector<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,_lambda_1e66152caec4462226a90d223302e186_>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>>>,std::back_insert_iterator<std::vector<SystemSettings::BatteryUsageHandlers::AppEnergyUsageRow>>,_lambda_1e66152caec4462226a90d223302e186_)
0x180045f34  call    cs:__imp__Xtime_get_ticks
0x180045f3a  sub     rax, [rbp+var_20]
0x180045f3e  lea     rdx, [rbp+arg_0]
0x180045f42  lea     rcx, [rbp+var_20]
0x180045f46  mov     [rbp+arg_0], rax
0x180045f4a  call    ??$?0_JU?$ratio@$00$0JIJGIA@@std@@$0A@@?$duration@NU?$ratio@$00$00@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@@Z; std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x180045f4f  mov     r9, [rsi+40h]
0x180045f53  mov     rcx, rsi
0x180045f56  movsd   xmm1, [rbp+var_20]
0x180045f5b  movsd   [rbp+var_20], xmm1
0x180045f60  mov     [rbp+arg_0], r9
0x180045f64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045f69  mov     [rbp+var_18], rax
0x180045f6d  lea     r9, [rbp+arg_10]
0x180045f71  lea     rax, [rbp+var_30]
0x180045f75  mov     [rsp+70h+var_40], rax
0x180045f7a  lea     r8, [rbp+arg_8]
0x180045f7e  lea     rax, [rbp+var_28]
0x180045f82  mov     [rsp+70h+var_48], rax
0x180045f87  lea     rdx, [rbp+var_20]
0x180045f8b  lea     rax, [rbp+arg_0]
0x180045f8f  lea     rcx, [rbp+var_18]
0x180045f93  mov     [rsp+70h+var_50], rax
0x180045f98  call    ??$SrumCacheQueryStats@PEBGNAEA_KAEA_K_KAEA_KAEA_K@UsageGraphTelemetry@@SAX$$QEAPEBG$$QEANAEA_K2$$QEA_K22@Z; UsageGraphTelemetry::SrumCacheQueryStats<ushort const *,double,unsigned __int64 &,unsigned __int64 &,unsigned __int64,unsigned __int64 &,unsigned __int64 &>(ushort const * &&,double &&,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &&,unsigned __int64 &,unsigned __int64 &)
0x180045f9d  xor     eax, eax
0x180045f9f  mov     rbx, [rsp+70h+arg_18]
0x180045fa7  add     rsp, 70h
0x180045fab  pop     r15
0x180045fad  pop     r14
0x180045faf  pop     r13
0x180045fb1  pop     r12
0x180045fb3  pop     rdi
0x180045fb4  pop     rsi
0x180045fb5  pop     rbp
0x180045fb6  retn
```
