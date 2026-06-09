# WaasMedic::CInPlaceUpgrade::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x180050120`
- end: `0x180050686`
- name: `?IsActionApplicable2@CInPlaceUpgrade@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `1382`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x1800179c4`
- `0x18001cae0`
- `0x18002543c`
- `0x180028a74`
- `0x180030890`
- `0x1800309a0`
- `0x180030f54`
- `0x180050120`
- `0x18005718c`
- `0x1800576a4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800505e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800505e0`
- `OLEAUT32!__imp_VariantInit` at `0x180050325`
- `OLEAUT32!__imp_VariantInit` at `0x18005048a`
- `OLEAUT32!__imp_VariantInit` at `0x180050325`
- `OLEAUT32!__imp_VariantInit` at `0x18005048a`
- `OLEAUT32!__imp_VariantClear` at `0x1800504db`
- `OLEAUT32!__imp_VariantClear` at `0x180050639`
- `OLEAUT32!__imp_VariantClear` at `0x180050646`
- `OLEAUT32!__imp_VariantClear` at `0x180050655`
- `OLEAUT32!__imp_VariantClear` at `0x180050660`
- `OLEAUT32!__imp_VariantClear` at `0x1800504db`
- `OLEAUT32!__imp_VariantClear` at `0x180050639`
- `OLEAUT32!__imp_VariantClear` at `0x180050646`
- `OLEAUT32!__imp_VariantClear` at `0x180050655`
- `OLEAUT32!__imp_VariantClear` at `0x180050660`

## string_xrefs

- `0x18005019f`: `Plugin is applicable due to manual remediation.`
- `0x180050337`: `PluginRunCount`
- `0x18005027a`: `ManualCorruptionRepairPlugin`
- `0x18005033e`: `ManualCorruptionRepairPlugin`
- `0x1800503c6`: `ManualCorruptionRepairPlugin`
- `0x1800504a8`: `ManualCorruptionRepairPlugin`
- `0x18005020c`: `Plugin not applicable. Reason code: %d`
- `0x1800502f8`: `SYSTEM\WaaS\Plugin`
- `0x18005046d`: `MCR has not yet run to completion.`
- `0x180050165`: `onecore\enduser\waasmedic\lib\plugins\inplaceupgradeplugin.cpp`
- `0x180050414`: `onecore\enduser\waasmedic\lib\plugins\inplaceupgradeplugin.cpp`
- `0x1800504ca`: `onecore\enduser\waasmedic\lib\plugins\inplaceupgradeplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaasMedic::CInPlaceUpgrade::IsActionApplicable2(__int64 a1, int a2, __int64 a3, _DWORD *a4)
{
  int IsActionApplicable2; // ebx
  __int64 v8; // rdx
  const char *v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _BYTE *, _BYTE *, _BYTE *); // rbx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  unsigned int v18; // r15d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int128 *, __int128 *, unsigned int *); // rbx
  char v21; // bl
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  __int64 (__fastcall ***v25)(_QWORD, __int128 *, __int128 *, _DWORD *); // rbx
  __int64 (__fastcall *v26)(_QWORD, __int128 *, __int128 *, _DWORD *); // r15
  __int64 v27; // rdx
  __int64 v28; // r8
  bool v29; // bl
  int v30; // [rsp+20h] [rbp-B9h]
  unsigned int v31; // [rsp+20h] [rbp-B9h]
  bool v32; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v33; // [rsp+34h] [rbp-A5h] BYREF
  struct _FILETIME v34; // [rsp+38h] [rbp-A1h] BYREF
  _BYTE v35[4]; // [rsp+40h] [rbp-99h] BYREF
  int v36; // [rsp+44h] [rbp-95h]
  char v37; // [rsp+48h] [rbp-91h]
  unsigned int v38; // [rsp+50h] [rbp-89h] BYREF
  int v39; // [rsp+54h] [rbp-85h]
  char v40; // [rsp+58h] [rbp-81h]
  _DWORD v41[2]; // [rsp+60h] [rbp-79h] BYREF
  char v42; // [rsp+68h] [rbp-71h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v44[32]; // [rsp+78h] [rbp-61h] BYREF
  _BYTE pvarg[32]; // [rsp+98h] [rbp-41h] BYREF
  __int128 v46; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v47; // [rsp+C8h] [rbp-11h]
  __int128 v48; // [rsp+D8h] [rbp-1h] BYREF
  __int128 v49; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  if ( !a4 )
  {
    IsActionApplicable2 = -2147467261;
    v8 = 52;
    goto LABEL_3;
  }
  IsActionApplicable2 = WaasMedic::CRemediationPluginBase::IsActionApplicable2();
  if ( IsActionApplicable2 < 0 )
  {
    v8 = 54;
    goto LABEL_3;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
    && *a4 == 16 )
  {
    LogLevelW(4u, L"Plugin is applicable due to manual remediation.");
    return 0;
  }
  if ( !a2 )
  {
    v33 = 0;
    IsActionApplicable2 = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(&v33);
    if ( IsActionApplicable2 < 0 )
    {
      v8 = 71;
      goto LABEL_3;
    }
    if ( v33 == 1 )
    {
      v10 = (const char *)(a1 + 120);
      if ( *(_QWORD *)(a1 + 144) > 0xFu )
        v10 = *(const char **)v10;
      IsActionApplicable2 = WaasMedic::IpuHelper::SetAllowInPlaceUpgradeRegKeyValueAndReportTelemetry(v10, 1u, 0);
      if ( IsActionApplicable2 < 0 )
      {
        v8 = 74;
        goto LABEL_3;
      }
    }
  }
  if ( *a4 )
  {
    LogLevelW(4u, L"Plugin not applicable. Reason code: %d");
    return 0;
  }
  v37 = 0;
  v35[0] = 0;
  v36 = 2;
  v11 = *(_QWORD *)(a1 + 104);
  v12 = *(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *, _BYTE *))(*(_QWORD *)v11 + 24LL);
  memset(v44, 0, sizeof(v44));
  std::wstring::_Construct<1,unsigned short const *>(v44, L"ENABLED", 7);
  memset(pvarg, 0, sizeof(pvarg));
  std::wstring::_Construct<1,unsigned short const *>(pvarg, L"ManualCorruptionRepairPlugin", 28);
  IsActionApplicable2 = v12(v11, pvarg, v44, v35);
  std::wstring::~wstring(pvarg);
  std::wstring::~wstring(v44);
  if ( IsActionApplicable2 < 0 )
  {
    v8 = 86;
    goto LABEL_3;
  }
  if ( v36 == 2 )
  {
    IsActionApplicable2 = -2147467259;
    v8 = 87;
    goto LABEL_3;
  }
  if ( v35[0] )
  {
    v33 = 0;
    v14 = WaasMedic::RegQueryDwordValue(v13, L"SYSTEM\\WaaS\\Plugin", L"EscalatetoInPlaceUpgrade", &v33);
    IsActionApplicable2 = v14;
    if ( v14 != -2147024894 && v14 )
    {
      if ( v14 >= 0 )
        return (unsigned int)IsActionApplicable2;
      v8 = 94;
LABEL_3:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\inplaceupgradeplugin.cpp",
        (const char *)(unsigned int)IsActionApplicable2,
        v30);
      return (unsigned int)IsActionApplicable2;
    }
    VariantInit((VARIANTARG *)pvarg);
    v15 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _BYTE *))(**(_QWORD **)(a1 + 96) + 16LL))(
            *(_QWORD *)(a1 + 96),
            L"ManualCorruptionRepairPlugin",
            L"PluginRunCount",
            pvarg);
    IsActionApplicable2 = v15;
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 98;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\inplaceupgradeplugin.cpp",
        (const char *)v16,
        v30);
LABEL_58:
      VariantClear((VARIANTARG *)pvarg);
      return (unsigned int)IsActionApplicable2;
    }
    v18 = 0;
    if ( *(_WORD *)pvarg == 19 )
      v18 = *(_DWORD *)&pvarg[8];
    v40 = 0;
    v38 = 0;
    v39 = 2;
    v19 = *(_QWORD *)(a1 + 104);
    v20 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, unsigned int *))(*(_QWORD *)v19 + 8LL);
    v48 = 0;
    v49 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v48, L"ACTIONLIMIT", 11);
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v46, L"ManualCorruptionRepairPlugin", 28);
    IsActionApplicable2 = v20(v19, &v46, &v48, &v38);
    std::wstring::~wstring(&v46);
    std::wstring::~wstring(&v48);
    if ( IsActionApplicable2 < 0 )
    {
      v17 = 105;
LABEL_35:
      v16 = (unsigned int)IsActionApplicable2;
      goto LABEL_36;
    }
    if ( v39 == 2 )
    {
      IsActionApplicable2 = -2147467259;
      v17 = 106;
      goto LABEL_35;
    }
    if ( v18 >= v38 || (v21 = 0, v33) )
      v21 = 1;
    v31 = v33;
    LogLevelW(4u, L"MCR run count: %d, MCR limit: %d, In-place Upgrade escalation flag: %d.", v18);
    if ( !v21 )
    {
      LogLevelW(4u, L"MCR has not yet run to completion.");
      *a4 = 12;
LABEL_57:
      IsActionApplicable2 = 0;
      goto LABEL_58;
    }
    VariantInit((VARIANTARG *)v44);
    v34 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const char *, _BYTE *))(**(_QWORD **)(a1 + 96) + 16LL))(
            *(_QWORD *)(a1 + 96),
            L"ManualCorruptionRepairPlugin",
            L"LastRemediationRunTime",
            v44);
    IsActionApplicable2 = v22;
    if ( v22 < 0 )
    {
      v23 = 121;
LABEL_46:
      v24 = (unsigned int)v22;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\inplaceupgradeplugin.cpp",
        (const char *)v24,
        v31);
      VariantClear((VARIANTARG *)v44);
      goto LABEL_58;
    }
    if ( *(_WORD *)v44 == 8 )
    {
      v22 = WaasMedic::TimeHelper::StringToFileTime(*(const unsigned __int16 **)&v44[8], &v34);
      IsActionApplicable2 = v22;
      if ( v22 < 0 )
      {
        v23 = 124;
        goto LABEL_46;
      }
      v42 = 0;
      v41[0] = *(_DWORD *)(a1 + 156);
      v41[1] = 2;
      v25 = *(__int64 (__fastcall ****)(_QWORD, __int128 *, __int128 *, _DWORD *))(a1 + 104);
      v26 = **v25;
      v46 = 0;
      v47 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v46, L"InPlaceUpgradeWaitAfterMCRInDays", 32);
      v27 = *(_QWORD *)(a1 + 112);
      v48 = 0;
      v49 = 0;
      v28 = -1;
      do
        ++v28;
      while ( *(_WORD *)(v27 + 2 * v28) );
      std::wstring::_Construct<1,unsigned short const *>(&v48, v27, v28);
      IsActionApplicable2 = v26(v25, &v48, &v46, v41);
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v46);
      if ( IsActionApplicable2 < 0 )
      {
        v24 = (unsigned int)IsActionApplicable2;
        v23 = 127;
        goto LABEL_47;
      }
      WaasMedic::TimeHelper::AddDelayToFileTime(&v34, 864000000000LL * v41[0], 1);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v32 = 0;
      WaasMedic::TimeHelper::TimeDiff(&v34, &SystemTimeAsFileTime, &v32);
      v29 = v32;
      LogLevelW(4u, L"MCR last ran %s. Number of days: %d have expired (bool): %d.", *(_QWORD *)&v44[8], v41[0], v32);
      if ( !v29 )
      {
        LogLevelW(4u, L"Escalation from MCR->IPU has not yet expired.");
        *a4 = 12;
        VariantClear((VARIANTARG *)v44);
        goto LABEL_57;
      }
    }
    VariantClear((VARIANTARG *)v44);
    VariantClear((VARIANTARG *)pvarg);
  }
  return 0;
}

```

## disassembly

```asm
0x180050120  push    rbp
0x180050122  push    rbx
0x180050123  push    rsi
0x180050124  push    rdi
0x180050125  push    r12
0x180050127  push    r14
0x180050129  push    r15
0x18005012b  lea     rbp, [rsp-27h]
0x180050130  sub     rsp, 100h
0x180050137  mov     rax, cs:__security_cookie
0x18005013e  xor     rax, rsp
0x180050141  mov     [rbp+57h+var_38], rax
0x180050145  mov     rsi, r9
0x180050148  mov     edi, edx
0x18005014a  mov     r14, rcx
0x18005014d  xor     r12d, r12d
0x180050150  test    r9, r9
0x180050153  jnz     short loc_180050178
0x180050155  mov     ebx, 80004003h
0x18005015a  lea     edx, [r9+34h]; void *
0x18005015e  mov     rcx, [rbp+5Fh]; this
0x180050162  mov     r9d, ebx; char *
0x180050165  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18005016c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050171  mov     eax, ebx
0x180050173  jmp     loc_180050668
0x180050178  call    ?IsActionApplicable2@CRemediationPluginBase@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)
0x18005017d  mov     ebx, eax
0x18005017f  test    eax, eax
0x180050181  jns     short loc_18005018A
0x180050183  mov     edx, 36h ; '6'
0x180050188  jmp     short loc_18005015E
0x18005018a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x180050191  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x180050196  test    al, al
0x180050198  jz      short loc_1800501B5
0x18005019a  cmp     dword ptr [rsi], 10h
0x18005019d  jnz     short loc_1800501B5
0x18005019f  lea     rdx, aPluginIsApplic; "Plugin is applicable due to manual reme"...
0x1800501a6  mov     ecx, 4; unsigned __int8
0x1800501ab  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800501b0  jmp     loc_180050666
0x1800501b5  test    edi, edi
0x1800501b7  jnz     short loc_180050204
0x1800501b9  mov     [rsp+130h+var_FC], r12d
0x1800501be  lea     rcx, [rsp+130h+var_FC]; unsigned int *
0x1800501c3  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x1800501c8  mov     ebx, eax
0x1800501ca  test    eax, eax
0x1800501cc  jns     short loc_1800501D3
0x1800501ce  lea     edx, [rdi+47h]
0x1800501d1  jmp     short loc_18005015E
0x1800501d3  cmp     [rsp+130h+var_FC], 1
0x1800501d8  jnz     short loc_180050204
0x1800501da  lea     rcx, [r14+78h]
0x1800501de  cmp     qword ptr [rcx+18h], 0Fh
0x1800501e3  jbe     short loc_1800501E8
0x1800501e5  mov     rcx, [rcx]; char *
0x1800501e8  xor     r8d, r8d; unsigned int
0x1800501eb  lea     edx, [r8+1]; unsigned int
0x1800501ef  call    ?SetAllowInPlaceUpgradeRegKeyValueAndReportTelemetry@IpuHelper@WaasMedic@@SAJPEBDKK@Z; WaasMedic::IpuHelper::SetAllowInPlaceUpgradeRegKeyValueAndReportTelemetry(char const *,ulong,ulong)
0x1800501f4  mov     ebx, eax
0x1800501f6  test    eax, eax
0x1800501f8  jns     short loc_180050204
0x1800501fa  mov     edx, 4Ah ; 'J'
0x1800501ff  jmp     loc_18005015E
0x180050204  mov     r8d, [rsi]
0x180050207  test    r8d, r8d
0x18005020a  jz      short loc_180050222
0x18005020c  lea     rdx, aPluginNotAppli; "Plugin not applicable. Reason code: %d"
0x180050213  mov     ecx, 4; unsigned __int8
0x180050218  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005021d  jmp     loc_180050666
0x180050222  mov     [rsp+130h+var_E8], r12b
0x180050227  mov     [rsp+130h+var_F0], r12b
0x18005022c  mov     [rsp+130h+var_EC], 2
0x180050234  mov     rdi, [r14+68h]
0x180050238  mov     rax, [rdi]
0x18005023b  mov     rbx, [rax+18h]
0x18005023f  xorps   xmm0, xmm0
0x180050242  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180050246  xorps   xmm1, xmm1
0x180050249  movdqu  xmmword ptr [rbp+57h+var_B8+10h], xmm1
0x18005024e  mov     r8d, 7
0x180050254  lea     rdx, aEnabled_0; "ENABLED"
0x18005025b  lea     rcx, [rbp+57h+var_B8]
0x18005025f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180050264  nop
0x180050265  xorps   xmm0, xmm0
0x180050268  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18005026c  xorps   xmm1, xmm1
0x18005026f  movdqu  xmmword ptr [rbp+57h+pvarg+10h], xmm1
0x180050274  mov     r8d, 1Ch
0x18005027a  lea     rdx, aManualcorrupti; "ManualCorruptionRepairPlugin"
0x180050281  lea     rcx, [rbp+57h+pvarg]
0x180050285  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005028a  nop
0x18005028b  lea     r9, [rsp+130h+var_F0]
0x180050290  lea     r8, [rbp+57h+var_B8]
0x180050294  lea     rdx, [rbp+57h+pvarg]
0x180050298  mov     rcx, rdi
0x18005029b  mov     rax, rbx
0x18005029e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502a3  mov     ebx, eax
0x1800502a5  lea     rcx, [rbp+57h+pvarg]; void *
0x1800502a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800502ae  nop
0x1800502af  lea     rcx, [rbp+57h+var_B8]; void *
0x1800502b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800502b8  test    ebx, ebx
0x1800502ba  jns     short loc_1800502C6
0x1800502bc  mov     edx, 56h ; 'V'
0x1800502c1  jmp     loc_18005015E
0x1800502c6  cmp     [rsp+130h+var_EC], 2
0x1800502cb  jnz     short loc_1800502DC
0x1800502cd  mov     ebx, 80004005h
0x1800502d2  mov     edx, 57h ; 'W'
0x1800502d7  jmp     loc_18005015E
0x1800502dc  cmp     [rsp+130h+var_F0], r12b
0x1800502e1  jz      loc_180050666
0x1800502e7  mov     [rsp+130h+var_FC], r12d
0x1800502ec  lea     r9, [rsp+130h+var_FC]
0x1800502f1  lea     r8, aEscalatetoinpl; "EscalatetoInPlaceUpgrade"
0x1800502f8  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x1800502ff  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAKW4RegistryHiveType@1@@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *,WaasMedic::RegistryHiveType)
0x180050304  mov     ebx, eax
0x180050306  cmp     eax, 80070002h
0x18005030b  jz      short loc_180050321
0x18005030d  test    eax, eax
0x18005030f  jz      short loc_180050321
0x180050311  jns     loc_180050171
0x180050317  mov     edx, 5Eh ; '^'
0x18005031c  jmp     loc_18005015E
0x180050321  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180050325  call    cs:__imp_VariantInit
0x18005032b  nop
0x18005032c  mov     rcx, [r14+60h]
0x180050330  mov     rax, [rcx]
0x180050333  lea     r9, [rbp+57h+pvarg]
0x180050337  lea     r8, aPluginruncount; "PluginRunCount"
0x18005033e  lea     rdx, aManualcorrupti; "ManualCorruptionRepairPlugin"
0x180050345  mov     rax, [rax+10h]
0x180050349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005034e  mov     ebx, eax
0x180050350  test    eax, eax
0x180050352  jns     short loc_180050361
0x180050354  mov     r9d, eax
0x180050357  mov     edx, 62h ; 'b'
0x18005035c  jmp     loc_180050410
0x180050361  mov     r15d, r12d
0x180050364  cmp     word ptr [rbp+57h+pvarg], 13h
0x180050369  cmovz   r15d, dword ptr [rbp+57h+pvarg+8]
0x18005036e  mov     [rsp+130h+var_D8], r12b
0x180050373  mov     [rsp+130h+var_E0], r12d
0x180050378  mov     [rsp+130h+var_DC], 2
0x180050380  mov     rdi, [r14+68h]
0x180050384  mov     rax, [rdi]
0x180050387  mov     rbx, [rax+8]
0x18005038b  xorps   xmm0, xmm0
0x18005038e  movups  [rbp+57h+var_58], xmm0
0x180050392  xorps   xmm1, xmm1
0x180050395  movdqu  [rbp+57h+var_48], xmm1
0x18005039a  mov     r8d, 0Bh
0x1800503a0  lea     rdx, aActionlimit; "ACTIONLIMIT"
0x1800503a7  lea     rcx, [rbp+57h+var_58]
0x1800503ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800503b0  nop
0x1800503b1  xorps   xmm0, xmm0
0x1800503b4  movups  [rbp+57h+var_78], xmm0
0x1800503b8  xorps   xmm1, xmm1
0x1800503bb  movdqu  [rbp+57h+var_68], xmm1
0x1800503c0  mov     r8d, 1Ch
0x1800503c6  lea     rdx, aManualcorrupti; "ManualCorruptionRepairPlugin"
0x1800503cd  lea     rcx, [rbp+57h+var_78]
0x1800503d1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800503d6  nop
0x1800503d7  lea     r9, [rsp+130h+var_E0]
0x1800503dc  lea     r8, [rbp+57h+var_58]
0x1800503e0  lea     rdx, [rbp+57h+var_78]
0x1800503e4  mov     rcx, rdi
0x1800503e7  mov     rax, rbx
0x1800503ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503ef  mov     ebx, eax
0x1800503f1  lea     rcx, [rbp+57h+var_78]; void *
0x1800503f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800503fa  nop
0x1800503fb  lea     rcx, [rbp+57h+var_58]; void *
0x1800503ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050404  test    ebx, ebx
0x180050406  jns     short loc_180050425
0x180050408  mov     edx, 69h ; 'i'; void *
0x18005040d  mov     r9d, ebx; char *
0x180050410  mov     rcx, [rbp+5Fh]; this
0x180050414  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18005041b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050420  jmp     loc_180050642
0x180050425  cmp     [rsp+130h+var_DC], 2
0x18005042a  jnz     short loc_180050438
0x18005042c  mov     ebx, 80004005h
0x180050431  mov     edx, 6Ah ; 'j'
0x180050436  jmp     short loc_18005040D
0x180050438  mov     eax, [rsp+130h+var_FC]
0x18005043c  mov     r9d, [rsp+130h+var_E0]
0x180050441  cmp     r15d, r9d
0x180050444  jnb     short loc_18005044D
0x180050446  test    eax, eax
0x180050448  mov     bl, r12b
0x18005044b  jz      short loc_18005044F
0x18005044d  mov     bl, 1
0x18005044f  mov     [rsp+130h+var_110], eax; int
0x180050453  mov     r8d, r15d
0x180050456  lea     rdx, aMcrRunCountDMc; "MCR run count: %d, MCR limit: %d, In-pl"...
0x18005045d  mov     edi, 4
0x180050462  mov     ecx, edi; unsigned __int8
0x180050464  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180050469  test    bl, bl
0x18005046b  jnz     short loc_180050486
0x18005046d  lea     rdx, aMcrHasNotYetRu; "MCR has not yet run to completion."
0x180050474  mov     ecx, edi; unsigned __int8
0x180050476  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005047b  mov     dword ptr [rsi], 0Ch
0x180050481  jmp     loc_18005063F
0x180050486  lea     rcx, [rbp+57h+var_B8]; pvarg
0x18005048a  call    cs:__imp_VariantInit
0x180050490  nop
0x180050491  mov     qword ptr [rsp+130h+var_F8.dwLowDateTime], r12
0x180050496  mov     rcx, [r14+60h]
0x18005049a  mov     rax, [rcx]
0x18005049d  lea     r9, [rbp+57h+var_B8]
0x1800504a1  lea     r8, aLastremediatio; "LastRemediationRunTime"
0x1800504a8  lea     rdx, aManualcorrupti; "ManualCorruptionRepairPlugin"
0x1800504af  mov     rax, [rax+10h]
0x1800504b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504b8  mov     ebx, eax
0x1800504ba  test    eax, eax
0x1800504bc  jns     short loc_1800504E6
0x1800504be  mov     edx, 79h ; 'y'; void *
0x1800504c3  mov     r9d, eax; char *
0x1800504c6  mov     rcx, [rbp+5Fh]; this
0x1800504ca  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800504d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800504d6  nop
0x1800504d7  lea     rcx, [rbp+57h+var_B8]; pvarg
0x1800504db  call    cs:__imp_VariantClear
0x1800504e1  jmp     loc_180050642
0x1800504e6  cmp     word ptr [rbp+57h+var_B8], 8
0x1800504eb  jnz     loc_180050651
0x1800504f1  lea     rdx, [rsp+130h+var_F8]; struct _FILETIME *
0x1800504f6  mov     rcx, qword ptr [rbp+57h+var_B8+8]; unsigned __int16 *
0x1800504fa  call    ?StringToFileTime@TimeHelper@WaasMedic@@SAJPEBGPEAU_FILETIME@@@Z; WaasMedic::TimeHelper::StringToFileTime(ushort const *,_FILETIME *)
0x1800504ff  mov     ebx, eax
0x180050501  test    eax, eax
0x180050503  jns     short loc_18005050C
0x180050505  mov     edx, 7Ch ; '|'
0x18005050a  jmp     short loc_1800504C3
0x18005050c  mov     [rbp+57h+var_C8], r12b
0x180050510  mov     eax, [r14+9Ch]
0x180050517  mov     [rbp+57h+var_D0], eax
0x18005051a  mov     [rbp+57h+var_CC], 2
0x180050521  mov     rbx, [r14+68h]
0x180050525  mov     rax, [rbx]
0x180050528  mov     r15, [rax]
0x18005052b  xorps   xmm0, xmm0
0x18005052e  movups  [rbp+57h+var_78], xmm0
0x180050532  xorps   xmm1, xmm1
0x180050535  movdqu  [rbp+57h+var_68], xmm1
0x18005053a  mov     r8d, 20h ; ' '
0x180050540  lea     rdx, aInplaceupgrade_1; "InPlaceUpgradeWaitAfterMCRInDays"
0x180050547  lea     rcx, [rbp+57h+var_78]
0x18005054b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180050550  nop
0x180050551  mov     rdx, [r14+70h]
0x180050555  xorps   xmm0, xmm0
0x180050558  movups  [rbp+57h+var_58], xmm0
0x18005055c  xorps   xmm1, xmm1
0x18005055f  movdqu  [rbp+57h+var_48], xmm1
0x180050564  or      r8, 0FFFFFFFFFFFFFFFFh
0x180050568  inc     r8
0x18005056b  cmp     [rdx+r8*2], r12w
0x180050570  jnz     short loc_180050568
0x180050572  lea     rcx, [rbp+57h+var_58]
0x180050576  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005057b  nop
0x18005057c  lea     r9, [rbp+57h+var_D0]
0x180050580  lea     r8, [rbp+57h+var_78]
0x180050584  lea     rdx, [rbp+57h+var_58]
0x180050588  mov     rcx, rbx
0x18005058b  mov     rax, r15
0x18005058e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050593  mov     ebx, eax
0x180050595  lea     rcx, [rbp+57h+var_58]; void *
0x180050599  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005059e  nop
0x18005059f  lea     rcx, [rbp+57h+var_78]; void *
0x1800505a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800505a8  test    ebx, ebx
0x1800505aa  jns     short loc_1800505B9
0x1800505ac  mov     r9d, ebx
0x1800505af  mov     edx, 7Fh
0x1800505b4  jmp     loc_1800504C6
  ... truncated ...
```
