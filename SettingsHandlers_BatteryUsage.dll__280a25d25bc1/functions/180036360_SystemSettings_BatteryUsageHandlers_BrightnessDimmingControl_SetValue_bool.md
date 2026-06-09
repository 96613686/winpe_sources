# SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl::SetValue(bool)

- ea: `0x180036360`
- end: `0x18003653e`
- name: `?SetValue@BrightnessDimmingControl@BatteryUsageHandlers@SystemSettings@@UEAAJ_N@Z`
- size: `478`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl *__hidden this, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800228bc`
- `0x18002edf4`
- `0x180034a5c`
- `0x180035c6c`
- `0x180036360`
- `0x180036654`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003648d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003648d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036529`
- `POWRPROF!PowerGetActiveScheme` at `0x1800363a2`
- `POWRPROF!PowerGetActiveScheme` at `0x1800363a2`
- `POWRPROF!PowerWriteDCValueIndex` at `0x180036469`
- `POWRPROF!PowerWriteDCValueIndex` at `0x180036469`
- `POWRPROF!PowerReadACDefaultIndex` at `0x180036429`
- `POWRPROF!PowerReadACDefaultIndex` at `0x180036429`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x1800363ee`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x1800363ee`
- `POWRPROF!PowerSetActiveScheme` at `0x1800364c7`
- `POWRPROF!PowerSetActiveScheme` at `0x1800364c7`
- `POWRPROF!PowerWriteACValueIndex` at `0x1800364b5`
- `POWRPROF!PowerWriteACValueIndex` at `0x1800364b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl::SetValue(
        SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl *this,
        char a2)
{
  signed int ActiveScheme; // ebx
  GUID *v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  DWORD v7; // eax
  signed int active; // eax
  unsigned int v9; // edi
  bool v10; // cc
  GUID *v11; // rcx
  _QWORD *Instance; // rax
  GUID *SchemePersonalityGuid; // [rsp+30h] [rbp-20h] BYREF
  GUID **p_SchemePersonalityGuid; // [rsp+38h] [rbp-18h] BYREF
  GUID *ActivePolicyGuid; // [rsp+40h] [rbp-10h] BYREF
  char v17; // [rsp+48h] [rbp-8h]
  DWORD DcValueIndex; // [rsp+80h] [rbp+30h] BYREF
  DWORD AcDefaultIndex; // [rsp+88h] [rbp+38h] BYREF

  SchemePersonalityGuid = 0;
  DcValueIndex = 0;
  AcDefaultIndex = 0;
  p_SchemePersonalityGuid = &SchemePersonalityGuid;
  ActivePolicyGuid = 0;
  v17 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_SchemePersonalityGuid);
  v4 = SchemePersonalityGuid;
  if ( ActiveScheme )
  {
    if ( ActiveScheme > 0 )
      ActiveScheme = (unsigned __int16)ActiveScheme | 0x80070000;
    goto LABEL_26;
  }
  if ( !SchemePersonalityGuid )
  {
LABEL_26:
    SchemePersonalityGuid = 0;
    if ( v4 )
      LocalFree(v4);
    return (unsigned int)ActiveScheme;
  }
  if ( a2 )
  {
    v5 = PowerReadDCDefaultIndex(
           0,
           SchemePersonalityGuid,
           &GUID_ENERGY_SAVER_SUBGROUP,
           &GUID_ENERGY_SAVER_BRIGHTNESS,
           &DcValueIndex);
    ActiveScheme = v5;
    if ( v5 > 0 )
      ActiveScheme = (unsigned __int16)v5 | 0x80070000;
    if ( ActiveScheme < 0 )
      goto LABEL_7;
    v6 = PowerReadACDefaultIndex(
           0,
           SchemePersonalityGuid,
           &GUID_ENERGY_SAVER_SUBGROUP,
           &GUID_ENERGY_SAVER_BRIGHTNESS,
           &AcDefaultIndex);
    ActiveScheme = v6;
    if ( v6 > 0 )
      ActiveScheme = (unsigned __int16)v6 | 0x80070000;
    if ( ActiveScheme < 0 )
      goto LABEL_7;
    v4 = SchemePersonalityGuid;
    v7 = DcValueIndex;
  }
  else
  {
    ActiveScheme = 0;
    v7 = 100;
    DcValueIndex = 100;
    AcDefaultIndex = 100;
  }
  active = PowerWriteDCValueIndex(0, v4, &GUID_ENERGY_SAVER_SUBGROUP, &GUID_ENERGY_SAVER_BRIGHTNESS, v7);
  v9 = active;
  v10 = active <= 0;
  if ( !active )
  {
    active = PowerWriteACValueIndex(
               0,
               SchemePersonalityGuid,
               &GUID_ENERGY_SAVER_SUBGROUP,
               &GUID_ENERGY_SAVER_BRIGHTNESS,
               AcDefaultIndex);
    v9 = active;
    v10 = active <= 0;
    if ( !active )
    {
      active = PowerSetActiveScheme(0, SchemePersonalityGuid);
      v9 = active;
      v10 = active <= 0;
      if ( !active )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl'::`2'::impl) )
        {
          Instance = (_QWORD *)UnifiedDisplayManagerSingleton::DisplayManagerSingleton::GetInstance(&p_SchemePersonalityGuid);
          SystemSettings::DataModel::CSingletonHelper<unsigned long>::_Notify<_lambda_7529ec996bf893d04f2d467973114278_>(*Instance);
          if ( ActivePolicyGuid )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)ActivePolicyGuid);
        }
LABEL_7:
        v4 = SchemePersonalityGuid;
        goto LABEL_26;
      }
    }
  }
  if ( !v10 )
    v9 = (unsigned __int16)active | 0x80070000;
  v11 = SchemePersonalityGuid;
  SchemePersonalityGuid = 0;
  if ( v11 )
    LocalFree(v11);
  return v9;
}

```

## disassembly

```asm
0x180036360  mov     [rsp-18h+arg_0], rbx
0x180036365  push    rbp
0x180036366  push    rsi
0x180036367  push    rdi
0x180036368  mov     rbp, rsp
0x18003636b  sub     rsp, 50h
0x18003636f  mov     dil, dl
0x180036372  mov     [rbp+SchemePersonalityGuid], 0
0x18003637a  mov     [rbp+DcValueIndex], 0
0x180036381  mov     [rbp+AcDefaultIndex], 0
0x180036388  lea     rax, [rbp+SchemePersonalityGuid]
0x18003638c  mov     [rbp+var_18], rax
0x180036390  mov     [rbp+ActivePolicyGuid], 0
0x180036398  mov     [rbp+var_8], 1
0x18003639c  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x1800363a0  xor     ecx, ecx; UserRootPowerKey
0x1800363a2  call    cs:__imp_PowerGetActiveScheme
0x1800363a8  mov     ebx, eax
0x1800363aa  lea     rcx, [rbp+var_18]
0x1800363ae  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800363b3  mov     rcx, [rbp+SchemePersonalityGuid]; hMem
0x1800363b7  test    ebx, ebx
0x1800363b9  jnz     loc_180036511
0x1800363bf  test    rcx, rcx
0x1800363c2  jz      loc_18003651C
0x1800363c8  mov     esi, 80070000h
0x1800363cd  test    dil, dil
0x1800363d0  jz      short loc_180036447
0x1800363d2  lea     rax, [rbp+DcValueIndex]
0x1800363d6  mov     [rsp+50h+DcDefaultIndex], rax; DcDefaultIndex
0x1800363db  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x1800363e2  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800363e9  mov     rdx, rcx; SchemePersonalityGuid
0x1800363ec  xor     ecx, ecx; RootPowerKey
0x1800363ee  call    cs:__imp_PowerReadDCDefaultIndex
0x1800363f4  mov     ebx, eax
0x1800363f6  test    eax, eax
0x1800363f8  jle     short loc_1800363FF
0x1800363fa  movzx   ebx, ax
0x1800363fd  or      ebx, esi
0x1800363ff  test    ebx, ebx
0x180036401  jns     short loc_18003640C
0x180036403  mov     rcx, [rbp+SchemePersonalityGuid]
0x180036407  jmp     loc_18003651C
0x18003640c  lea     rax, [rbp+AcDefaultIndex]
0x180036410  mov     [rsp+50h+DcDefaultIndex], rax; AcDefaultIndex
0x180036415  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x18003641c  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180036423  mov     rdx, [rbp+SchemePersonalityGuid]; SchemePersonalityGuid
0x180036427  xor     ecx, ecx; RootPowerKey
0x180036429  call    cs:__imp_PowerReadACDefaultIndex
0x18003642f  mov     ebx, eax
0x180036431  test    eax, eax
0x180036433  jle     short loc_18003643A
0x180036435  movzx   ebx, ax
0x180036438  or      ebx, esi
0x18003643a  test    ebx, ebx
0x18003643c  js      short loc_180036403
0x18003643e  mov     rcx, [rbp+SchemePersonalityGuid]
0x180036442  mov     eax, [rbp+DcValueIndex]
0x180036445  jmp     short loc_180036452
0x180036447  xor     ebx, ebx
0x180036449  lea     eax, [rbx+64h]
0x18003644c  mov     [rbp+DcValueIndex], eax
0x18003644f  mov     [rbp+AcDefaultIndex], eax
0x180036452  mov     dword ptr [rsp+50h+DcDefaultIndex], eax; DcValueIndex
0x180036456  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x18003645d  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180036464  mov     rdx, rcx; SchemeGuid
0x180036467  xor     ecx, ecx; RootPowerKey
0x180036469  call    cs:__imp_PowerWriteDCValueIndex
0x18003646f  mov     edi, eax
0x180036471  test    eax, eax
0x180036473  jz      short loc_18003649A
0x180036475  jle     short loc_18003647C
0x180036477  movzx   edi, ax
0x18003647a  or      edi, esi
0x18003647c  mov     rcx, [rbp+SchemePersonalityGuid]; hMem
0x180036480  mov     [rbp+SchemePersonalityGuid], 0
0x180036488  test    rcx, rcx
0x18003648b  jz      short loc_180036493
0x18003648d  call    cs:__imp_LocalFree
0x180036493  mov     eax, edi
0x180036495  jmp     loc_180036531
0x18003649a  mov     eax, [rbp+AcDefaultIndex]
0x18003649d  mov     dword ptr [rsp+50h+DcDefaultIndex], eax; AcValueIndex
0x1800364a1  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x1800364a8  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800364af  mov     rdx, [rbp+SchemePersonalityGuid]; SchemeGuid
0x1800364b3  xor     ecx, ecx; RootPowerKey
0x1800364b5  call    cs:__imp_PowerWriteACValueIndex
0x1800364bb  mov     edi, eax
0x1800364bd  test    eax, eax
0x1800364bf  jnz     short loc_180036475
0x1800364c1  mov     rdx, [rbp+SchemePersonalityGuid]; SchemeGuid
0x1800364c5  xor     ecx, ecx; UserRootPowerKey
0x1800364c7  call    cs:__imp_PowerSetActiveScheme
0x1800364cd  mov     edi, eax
0x1800364cf  test    eax, eax
0x1800364d1  jnz     short loc_180036475
0x1800364d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix> `wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl(void)'::`2'::impl
0x1800364da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(void)
0x1800364df  test    al, al
0x1800364e1  jz      loc_180036403
0x1800364e7  lea     rcx, [rbp+var_18]
0x1800364eb  call    ?GetInstance@DisplayManagerSingleton@UnifiedDisplayManagerSingleton@@SA?AV?$shared_ptr@VDisplayManagerSingleton@UnifiedDisplayManagerSingleton@@@std@@XZ; UnifiedDisplayManagerSingleton::DisplayManagerSingleton::GetInstance(void)
0x1800364f0  nop
0x1800364f1  mov     rcx, [rax]
0x1800364f4  call    ??$_Notify@V_lambda_7529ec996bf893d04f2d467973114278_@@@?$CSingletonHelper@K@DataModel@SystemSettings@@AEAAXAEBV_lambda_7529ec996bf893d04f2d467973114278_@@@Z; SystemSettings::DataModel::CSingletonHelper<ulong>::_Notify<_lambda_7529ec996bf893d04f2d467973114278_>(_lambda_7529ec996bf893d04f2d467973114278_ const &)
0x1800364f9  nop
0x1800364fa  mov     rcx, [rbp+ActivePolicyGuid]; this
0x1800364fe  test    rcx, rcx
0x180036501  jz      loc_180036403
0x180036507  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003650c  jmp     loc_180036403
0x180036511  jle     short loc_18003651C
0x180036513  movzx   ebx, bx
0x180036516  or      ebx, 80070000h
0x18003651c  test    rcx, rcx
0x18003651f  mov     [rbp+SchemePersonalityGuid], 0
0x180036527  jz      short loc_18003652F
0x180036529  call    cs:__imp_LocalFree
0x18003652f  mov     eax, ebx
0x180036531  mov     rbx, [rsp+50h+arg_0]
0x180036536  add     rsp, 50h
0x18003653a  pop     rdi
0x18003653b  pop     rsi
0x18003653c  pop     rbp
0x18003653d  retn
```
