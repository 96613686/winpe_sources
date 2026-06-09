# SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::DoGenericAsyncWork(void)

- ea: `0x18003d200`
- end: `0x18003d39d`
- name: `?DoGenericAsyncWork@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@UEAAXXZ`
- size: `413`
- prototype: `void __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012c58`
- `0x180017998`
- `0x18002570c`
- `0x18002c634`
- `0x180031828`
- `0x18003d200`
- `0x18003e8b4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d36f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d36f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d33b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d33b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d218`

## string_xrefs

- `0x18003d334`: `SettingsHandlers_OneCore_PowerAndSleep.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::DoGenericAsyncWork(
        SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *this)
{
  int v2; // ecx
  __int64 v3; // r8
  GUID *v4; // rdx
  GUID *v5; // rdx
  HMODULE v6; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v9; // [rsp+40h] [rbp+20h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+48h] [rbp+28h] BYREF
  unsigned int *v11; // [rsp+50h] [rbp+30h] BYREF

  EnterCriticalSection(&SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection);
  v10 = &SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection;
  if ( *((_DWORD *)this + 90) == 1 )
  {
    if ( *((_DWORD *)this + 89) != 100 )
    {
      v2 = *((_DWORD *)this + 89) - 200;
      if ( *((_DWORD *)this + 89) != 200 )
        goto LABEL_5;
      v4 = &GUID_POWER_MODE_PERFORMANCE;
      goto LABEL_9;
    }
    v5 = &GUID_POWER_MODE_NONE;
LABEL_16:
    SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(this, v5);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl'::`2'::impl) )
    {
      v9 = 100;
      goto LABEL_18;
    }
    goto LABEL_19;
  }
  if ( *((_DWORD *)this + 90) != 2 )
    goto LABEL_19;
  if ( *((_DWORD *)this + 89) == 100 )
  {
    v5 = &GUID_POWER_MODE_BEST_EFFICIENCY;
    goto LABEL_16;
  }
  v2 = *((_DWORD *)this + 89) - 200;
  if ( *((_DWORD *)this + 89) != 200 )
  {
LABEL_5:
    if ( v2 == 100 )
    {
      SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(
        this,
        &GUID_POWER_MODE_BEST_PERFORMANCE);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl'::`2'::impl) )
      {
        v9 = 300;
LABEL_18:
        v11 = (unsigned int *)&v9;
        SystemSettings::DataModel::CSingletonHelper<int>::_Notify<_lambda_e398eed577395da8d81f0cd0fd7d36b5_>(
          (__int64)&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverPowerOverlaySingleton,
          &v11,
          v3);
        goto LABEL_19;
      }
    }
    goto LABEL_19;
  }
  v4 = &GUID_POWER_MODE_NONE;
LABEL_9:
  SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(this, v4);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl'::`2'::impl) )
  {
    v9 = 200;
    goto LABEL_18;
  }
LABEL_19:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v10);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180057650);
  v6 = SystemSettings::DataModel::g_handlerModule;
  if ( SystemSettings::DataModel::g_handlerModule
    || (Library = LoadLibraryExW(L"SettingsHandlers_OneCore_PowerAndSleep.dll", 0, 0x800u),
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          &SystemSettings::DataModel::g_handlerModule,
          Library),
        (v6 = SystemSettings::DataModel::g_handlerModule) != 0) )
  {
    ProcAddress = (FARPROC)SystemSettings::DataModel::g_NotifyPowerAndSleep;
    if ( SystemSettings::DataModel::g_NotifyPowerAndSleep
      || (ProcAddress = GetProcAddress(v6, "NotifyPowerAndSleep"),
          (SystemSettings::DataModel::g_NotifyPowerAndSleep = (void (__high *)(enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent))ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(1);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v10);
}

```

## disassembly

```asm
0x18003d200  push    rbp
0x18003d202  push    rbx
0x18003d203  push    rdi
0x18003d204  mov     rbp, rsp
0x18003d207  sub     rsp, 20h
0x18003d20b  mov     rbx, rcx
0x18003d20e  lea     rdi, ?_SliderPositionCritSection@BatterySaverOneCoreDataModel@SystemSettings@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection
0x18003d215  mov     rcx, rdi; lpCriticalSection
0x18003d218  call    cs:__imp_EnterCriticalSection
0x18003d21e  mov     [rbp+arg_8], rdi
0x18003d222  mov     ecx, [rbx+168h]
0x18003d228  sub     ecx, 1
0x18003d22b  jz      loc_18003D2B2
0x18003d231  cmp     ecx, 1
0x18003d234  jnz     loc_18003D308
0x18003d23a  mov     ecx, [rbx+164h]
0x18003d240  mov     edi, 64h ; 'd'
0x18003d245  sub     ecx, edi
0x18003d247  jz      short loc_18003D2A9
0x18003d249  sub     ecx, edi
0x18003d24b  jz      short loc_18003D281
0x18003d24d  cmp     ecx, edi
0x18003d24f  jnz     loc_18003D308
0x18003d255  lea     rdx, GUID_POWER_MODE_BEST_PERFORMANCE; struct _GUID *
0x18003d25c  mov     rcx, rbx; this
0x18003d25f  call    ?_SetUserConfiguredPowerMode@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBU_GUID@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(_GUID const *)
0x18003d264  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix> `wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl(void)'::`2'::impl
0x18003d26b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(void)
0x18003d270  test    al, al
0x18003d272  jz      loc_18003D308
0x18003d278  mov     [rbp+arg_0], 12Ch
0x18003d27f  jmp     short loc_18003D2F0
0x18003d281  lea     rdx, GUID_POWER_MODE_NONE; struct _GUID *
0x18003d288  mov     rcx, rbx; this
0x18003d28b  call    ?_SetUserConfiguredPowerMode@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBU_GUID@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(_GUID const *)
0x18003d290  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix> `wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl(void)'::`2'::impl
0x18003d297  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(void)
0x18003d29c  test    al, al
0x18003d29e  jz      short loc_18003D308
0x18003d2a0  mov     [rbp+arg_0], 0C8h
0x18003d2a7  jmp     short loc_18003D2F0
0x18003d2a9  lea     rdx, GUID_POWER_MODE_BEST_EFFICIENCY
0x18003d2b0  jmp     short loc_18003D2D5
0x18003d2b2  mov     ecx, [rbx+164h]
0x18003d2b8  mov     edi, 64h ; 'd'
0x18003d2bd  sub     ecx, edi
0x18003d2bf  jz      short loc_18003D2CE
0x18003d2c1  sub     ecx, edi
0x18003d2c3  jnz     short loc_18003D24D
0x18003d2c5  lea     rdx, GUID_POWER_MODE_PERFORMANCE
0x18003d2cc  jmp     short loc_18003D288
0x18003d2ce  lea     rdx, GUID_POWER_MODE_NONE; struct _GUID *
0x18003d2d5  mov     rcx, rbx; this
0x18003d2d8  call    ?_SetUserConfiguredPowerMode@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBU_GUID@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_SetUserConfiguredPowerMode(_GUID const *)
0x18003d2dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix> `wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl(void)'::`2'::impl
0x18003d2e4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(void)
0x18003d2e9  test    al, al
0x18003d2eb  jz      short loc_18003D308
0x18003d2ed  mov     [rbp+arg_0], edi
0x18003d2f0  lea     rax, [rbp+arg_0]
0x18003d2f4  mov     [rbp+arg_10], rax
0x18003d2f8  lea     rdx, [rbp+arg_10]
0x18003d2fc  lea     rcx, ?g_CBatterySaverPowerOverlaySingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverPowerOverlaySingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverPowerOverlaySingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverPowerOverlaySingleton
0x18003d303  call    ??$_Notify@V_lambda_e398eed577395da8d81f0cd0fd7d36b5_@@@?$CSingletonHelper@H@DataModel@SystemSettings@@AEAAXAEBV_lambda_e398eed577395da8d81f0cd0fd7d36b5_@@@Z; SystemSettings::DataModel::CSingletonHelper<int>::_Notify<_lambda_e398eed577395da8d81f0cd0fd7d36b5_>(_lambda_e398eed577395da8d81f0cd0fd7d36b5_ const &)
0x18003d308  lea     rcx, [rbp+arg_8]; this
0x18003d30c  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003d311  lea     rdx, stru_180057650; unsigned __int16 *
0x18003d318  mov     rcx, rbx; this
0x18003d31b  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18003d320  mov     rcx, cs:?g_handlerModule@DataModel@SystemSettings@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> SystemSettings::DataModel::g_handlerModule
0x18003d327  test    rcx, rcx
0x18003d32a  jnz     short loc_18003D35C
0x18003d32c  xor     edx, edx; hFile
0x18003d32e  mov     r8d, 800h; dwFlags
0x18003d334  lea     rcx, aSettingshandle_0; "SettingsHandlers_OneCore_PowerAndSleep."...
0x18003d33b  call    cs:__imp_LoadLibraryExW
0x18003d341  mov     rdx, rax
0x18003d344  lea     rcx, ?g_handlerModule@DataModel@SystemSettings@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> SystemSettings::DataModel::g_handlerModule
0x18003d34b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18003d350  mov     rcx, cs:?g_handlerModule@DataModel@SystemSettings@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18003d357  test    rcx, rcx
0x18003d35a  jz      short loc_18003D38C
0x18003d35c  mov     rax, cs:?g_NotifyPowerAndSleep@DataModel@SystemSettings@@3P6AXW4DisplayTimeoutAndSleepEvent@12@@ZEA; void (*SystemSettings::DataModel::g_NotifyPowerAndSleep)(SystemSettings::DataModel::DisplayTimeoutAndSleepEvent)
0x18003d363  test    rax, rax
0x18003d366  jnz     short loc_18003D381
0x18003d368  lea     rdx, aNotifypowerand; "NotifyPowerAndSleep"
0x18003d36f  call    cs:__imp_GetProcAddress
0x18003d375  mov     cs:?g_NotifyPowerAndSleep@DataModel@SystemSettings@@3P6AXW4DisplayTimeoutAndSleepEvent@12@@ZEA, rax; void (*SystemSettings::DataModel::g_NotifyPowerAndSleep)(SystemSettings::DataModel::DisplayTimeoutAndSleepEvent)
0x18003d37c  test    rax, rax
0x18003d37f  jz      short loc_18003D38C
0x18003d381  mov     ecx, 1
0x18003d386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d38b  nop
0x18003d38c  lea     rcx, [rbp+arg_8]; this
0x18003d390  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003d395  add     rsp, 20h
0x18003d399  pop     rdi
0x18003d39a  pop     rbx
0x18003d39b  pop     rbp
0x18003d39c  retn
```
