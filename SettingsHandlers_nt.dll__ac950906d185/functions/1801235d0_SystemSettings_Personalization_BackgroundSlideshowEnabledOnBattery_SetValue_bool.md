# SystemSettings::Personalization::BackgroundSlideshowEnabledOnBattery::SetValue(bool)

- ea: `0x1801235d0`
- end: `0x180123771`
- name: `?SetValue@BackgroundSlideshowEnabledOnBattery@Personalization@SystemSettings@@UEAAJ_N@Z`
- size: `417`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::BackgroundSlideshowEnabledOnBattery *__hidden this, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18001e6c4`
- `0x1800504dc`
- `0x180116b10`
- `0x1801235d0`
- `0x1801992e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801236fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801236fc`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x1801236c4`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x1801236c4`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x1801236ec`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x1801236ec`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1801236a4`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1801236da`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1801236a4`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1801236da`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1801235f5`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1801235f5`
- `POWRPROF!PowerReadACValueIndex` at `0x18012365b`
- `POWRPROF!PowerReadACValueIndex` at `0x18012365b`
- `POWRPROF!PowerReadDCValueIndex` at `0x180123632`
- `POWRPROF!PowerReadDCValueIndex` at `0x180123632`

## pseudocode

```c
__int64 __fastcall SystemSettings::Personalization::BackgroundSlideshowEnabledOnBattery::SetValue(
        SystemSettings::Personalization::BackgroundSlideshowEnabledOnBattery *this,
        char a2)
{
  GUID *v4; // rdx
  struct SystemSettings::DataModel::ISettingItemTelemetry *v5; // r8
  __int128 v7; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v8[16]; // [rsp+40h] [rbp-10h] BYREF
  DWORD AcValueIndex; // [rsp+80h] [rbp+30h] BYREF
  char v10; // [rsp+88h] [rbp+38h] BYREF
  DWORD *DcValueIndex; // [rsp+90h] [rbp+40h] BYREF
  GUID *ActivePolicyGuid; // [rsp+98h] [rbp+48h] BYREF

  v10 = a2;
  ActivePolicyGuid = 0;
  if ( !PowerGetActiveScheme(0, &ActivePolicyGuid) )
  {
    AcValueIndex = 0;
    LODWORD(DcValueIndex) = 0;
    if ( PowerReadDCValueIndex(
           0,
           ActivePolicyGuid,
           &SubGroupOfPowerSettingsGuid,
           &PowerSettingGuid,
           (LPDWORD)&DcValueIndex)
      || PowerReadACValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, &AcValueIndex) )
    {
      goto LABEL_12;
    }
    if ( AcValueIndex && (_DWORD)DcValueIndex )
    {
      v4 = ActivePolicyGuid;
      if ( a2 )
      {
        PowerWriteDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 0);
        PowerWriteACValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 0);
        goto LABEL_11;
      }
    }
    else
    {
      v4 = ActivePolicyGuid;
      if ( a2 )
      {
        PowerWriteDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 0);
LABEL_11:
        PowerSetActiveScheme(0, ActivePolicyGuid);
LABEL_12:
        LocalFree(ActivePolicyGuid);
        goto LABEL_13;
      }
    }
    PowerWriteDCValueIndex(0, v4, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 1u);
    goto LABEL_11;
  }
LABEL_13:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    AcValueIndex = 9;
    DcValueIndex = &AcValueIndex;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::EThemeOperation>::_Notify<_lambda_dc161c2385f253b892df8be3f78e6a7d_>(
      &SystemSettings::Personalization::g_BackgroundSingleton,
      &DcValueIndex);
  }
  v7 = (__int128)*SystemSettings::Personalization::GetPageSessionId(
                    (SystemSettings::Personalization *)v8,
                    (struct _GUID *)(((unsigned __int64)this + 16) & -(__int64)(this != 0)),
                    v5);
  ThemeSettingsTelemetry::SlideshowEnableOnBatteryChanged<_GUID,bool &>(&v7, &v10);
  return 0;
}

```

## disassembly

```asm
0x1801235d0  mov     [rsp-28h+arg_8], dl
0x1801235d4  push    rbp
0x1801235d5  push    rbx
0x1801235d6  push    rdi
0x1801235d7  push    r14
0x1801235d9  push    r15
0x1801235db  mov     rbp, rsp
0x1801235de  sub     rsp, 50h
0x1801235e2  mov     bl, dl
0x1801235e4  mov     [rbp+ActivePolicyGuid], 0
0x1801235ec  mov     rdi, rcx
0x1801235ef  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x1801235f3  xor     ecx, ecx; UserRootPowerKey
0x1801235f5  call    cs:__imp_PowerGetActiveScheme
0x1801235fc  nop     dword ptr [rax+rax+00h]
0x180123601  test    eax, eax
0x180123603  jnz     loc_180123708
0x180123609  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18012360d  lea     r14, PowerSettingGuid
0x180123614  mov     [rbp+AcValueIndex], eax
0x180123617  lea     r15, SubGroupOfPowerSettingsGuid
0x18012361e  mov     dword ptr [rbp+arg_10], eax
0x180123621  mov     r9, r14; PowerSettingGuid
0x180123624  lea     rax, [rbp+arg_10]
0x180123628  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x18012362b  xor     ecx, ecx; RootPowerKey
0x18012362d  mov     [rsp+50h+DcValueIndex], rax; DcValueIndex
0x180123632  call    cs:__imp_PowerReadDCValueIndex
0x180123639  nop     dword ptr [rax+rax+00h]
0x18012363e  test    eax, eax
0x180123640  jnz     loc_1801236F8
0x180123646  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18012364a  lea     rax, [rbp+AcValueIndex]
0x18012364e  mov     r9, r14; PowerSettingGuid
0x180123651  mov     [rsp+50h+DcValueIndex], rax; AcValueIndex
0x180123656  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x180123659  xor     ecx, ecx; RootPowerKey
0x18012365b  call    cs:__imp_PowerReadACValueIndex
0x180123662  nop     dword ptr [rax+rax+00h]
0x180123667  test    eax, eax
0x180123669  jnz     loc_1801236F8
0x18012366f  cmp     [rbp+AcValueIndex], eax
0x180123672  jnz     short loc_18012368A
0x180123674  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x180123678  xor     ecx, ecx; RootPowerKey
0x18012367a  mov     r9, r14; PowerSettingGuid
0x18012367d  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x180123680  test    bl, bl
0x180123682  jz      short loc_1801236D2
0x180123684  mov     dword ptr [rsp+50h+DcValueIndex], ecx
0x180123688  jmp     short loc_1801236DA
0x18012368a  cmp     dword ptr [rbp+arg_10], 0
0x18012368e  jz      short loc_180123674
0x180123690  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x180123694  xor     ecx, ecx; RootPowerKey
0x180123696  mov     r9, r14; PowerSettingGuid
0x180123699  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x18012369c  test    bl, bl
0x18012369e  jz      short loc_1801236D2
0x1801236a0  mov     dword ptr [rsp+50h+DcValueIndex], ecx; DcValueIndex
0x1801236a4  call    cs:__imp_PowerWriteDCValueIndex
0x1801236ab  nop     dword ptr [rax+rax+00h]
0x1801236b0  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x1801236b4  mov     r9, r14; PowerSettingGuid
0x1801236b7  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x1801236ba  mov     dword ptr [rsp+50h+DcValueIndex], 0; AcValueIndex
0x1801236c2  xor     ecx, ecx; RootPowerKey
0x1801236c4  call    cs:__imp_PowerWriteACValueIndex
0x1801236cb  nop     dword ptr [rax+rax+00h]
0x1801236d0  jmp     short loc_1801236E6
0x1801236d2  mov     dword ptr [rsp+50h+DcValueIndex], 1; DcValueIndex
0x1801236da  call    cs:__imp_PowerWriteDCValueIndex
0x1801236e1  nop     dword ptr [rax+rax+00h]
0x1801236e6  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x1801236ea  xor     ecx, ecx; UserRootPowerKey
0x1801236ec  call    cs:__imp_PowerSetActiveScheme
0x1801236f3  nop     dword ptr [rax+rax+00h]
0x1801236f8  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x1801236fc  call    cs:__imp_LocalFree
0x180123703  nop     dword ptr [rax+rax+00h]
0x180123708  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x18012370f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180123714  test    al, al
0x180123716  jz      short loc_180123737
0x180123718  lea     rax, [rbp+AcValueIndex]
0x18012371c  mov     [rbp+AcValueIndex], 9
0x180123723  lea     rdx, [rbp+arg_10]
0x180123727  mov     [rbp+arg_10], rax
0x18012372b  lea     rcx, ?g_BackgroundSingleton@Personalization@SystemSettings@@3VCBackgroundSingleton@12@A; SystemSettings::Personalization::CBackgroundSingleton SystemSettings::Personalization::g_BackgroundSingleton
0x180123732  call    ??$_Notify@V_lambda_dc161c2385f253b892df8be3f78e6a7d_@@@?$CSingletonHelper@W4EThemeOperation@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_dc161c2385f253b892df8be3f78e6a7d_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::EThemeOperation>::_Notify<_lambda_dc161c2385f253b892df8be3f78e6a7d_>(_lambda_dc161c2385f253b892df8be3f78e6a7d_ const &)
0x180123737  lea     rax, [rdi+10h]
0x18012373b  neg     rdi
0x18012373e  lea     rcx, [rbp+var_10]; this
0x180123742  sbb     rdx, rdx
0x180123745  and     rdx, rax; retstr
0x180123748  call    ?GetPageSessionId@Personalization@SystemSettings@@YA?AU_GUID@@PEAUISettingItemTelemetry@DataModel@2@@Z; SystemSettings::Personalization::GetPageSessionId(SystemSettings::DataModel::ISettingItemTelemetry *)
0x18012374d  lea     rdx, [rbp+arg_8]
0x180123751  lea     rcx, [rbp+var_20]
0x180123755  movups  xmm0, xmmword ptr [rax]
0x180123758  movdqu  [rbp+var_20], xmm0
0x18012375d  call    ??$SlideshowEnableOnBatteryChanged@U_GUID@@AEA_N@ThemeSettingsTelemetry@@SAX$$QEAU_GUID@@AEA_N@Z; ThemeSettingsTelemetry::SlideshowEnableOnBatteryChanged<_GUID,bool &>(_GUID &&,bool &)
0x180123762  xor     eax, eax
0x180123764  add     rsp, 50h
0x180123768  pop     r15
0x18012376a  pop     r14
0x18012376c  pop     rdi
0x18012376d  pop     rbx
0x18012376e  pop     rbp
0x18012376f  retn
```
