# SystemSettings::StorageSenseHandlers::CStoragePolicySettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x1800812d0`
- end: `0x1800815c5`
- name: `?SetValue@?$CStoragePolicySettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000171c`
- `0x1800023e4`
- `0x180006e50`
- `0x180016ef4`
- `0x18001fc0c`
- `0x18001fe08`
- `0x180023928`
- `0x1800286c0`
- `0x18007c7dc`
- `0x180080c00`
- `0x1800812d0`
- `0x180081840`
- `0x1800b4240`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180081352`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008146a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180081352`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008146a`
- `ext-ms-win-storage-sense-l1-2-3!SilentCleanupTaskSetEnabledState` at `0x18008140a`
- `ext-ms-win-storage-sense-l1-2-3!SilentCleanupTaskSetEnabledState` at `0x18008140a`
- `ext-ms-win-storage-sense-l1-2-0!SetStoragePolicySettings` at `0x180081429`
- `ext-ms-win-storage-sense-l1-2-0!SetStoragePolicySettings` at `0x180081429`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStoragePolicySettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(
        SystemSettings::DataModel::CSettingBase *this,
        __int64 *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // esi
  unsigned int v6; // edi
  __int64 v7; // rax
  int IsCleanMgrPresent; // edi
  int *v9; // rax
  bool *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  bool v13; // bl
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  int v18; // r9d
  int lpData; // [rsp+20h] [rbp-59h]
  unsigned __int8 v21; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v22[3]; // [rsp+41h] [rbp-38h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-35h] BYREF
  int v24; // [rsp+48h] [rbp-31h] BYREF
  int v25; // [rsp+4Ch] [rbp-2Dh] BYREF
  int *v26; // [rsp+50h] [rbp-29h] BYREF
  int Data; // [rsp+58h] [rbp-21h] BYREF
  int v28; // [rsp+5Ch] [rbp-1Dh] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp+7h] BYREF

  v4 = *((_QWORD *)this + 11);
  v5 = *(_DWORD *)(v4 + 24);
  v6 = *(_DWORD *)(v4 + 28);
  v21 = 0;
  v23 = 0;
  std::wstring::wstring(v30);
  Data = 1;
  RegSetKeyValueW(
    HKEY_CURRENT_USER,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
    L"StoragePoliciesChanged",
    4u,
    &Data,
    4u);
  v7 = *a2;
  if ( ((v5 - 3) & 0xFFFFFFFD) == 0 )
  {
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v7 + 96))(a2, &v23);
    LOBYTE(lpData) = 0;
    IsCleanMgrPresent = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)this + 272LL))(
                          this,
                          v5,
                          v6,
                          v23,
                          lpData);
    if ( IsCleanMgrPresent < 0 )
      goto LABEL_22;
    v13 = v23 != 0;
    goto LABEL_21;
  }
  if ( v5 == 10 )
  {
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v7 + 96))(a2, &v23);
    LOBYTE(lpData) = 1;
    IsCleanMgrPresent = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, __int64, _QWORD, _QWORD, int))(*(_QWORD *)this + 272LL))(
                          this,
                          10,
                          v6,
                          v23,
                          lpData);
    if ( IsCleanMgrPresent < 0 )
      goto LABEL_22;
    v24 = 2;
    v9 = &v24;
    goto LABEL_17;
  }
  IsCleanMgrPresent = (*(__int64 (__fastcall **)(__int64 *, unsigned __int8 *))(v7 + 144))(a2, &v21);
  if ( IsCleanMgrPresent < 0 )
    goto LABEL_22;
  if ( v5 == 6 )
  {
LABEL_18:
    v13 = v21 != 0;
LABEL_21:
    v14 = std::wstring::wstring(v29, v30, v11);
    LOBYTE(v15) = v13;
    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring>::SetIsItemChecked(
      v16,
      v14,
      v15);
    goto LABEL_22;
  }
  if ( v5 != 2
    || (v22[0] = 0,
        IsCleanMgrPresent = SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsCleanMgrPresent(
                              (SystemSettings::StorageSenseHandlers::ExecutionHelpers *)v22,
                              v10),
        IsCleanMgrPresent >= 0)
    && (!v22[0]
     || (v21 ? (v12 = 0xFFFFFFFFLL) : (v12 = 0),
         IsCleanMgrPresent = SilentCleanupTaskSetEnabledState(v12),
         IsCleanMgrPresent >= 0)) )
  {
    IsCleanMgrPresent = SetStoragePolicySettings(v5, 0, v21 != 0);
    if ( IsCleanMgrPresent >= 0 )
    {
      if ( !v5 )
      {
        v24 = 1;
        RegSetKeyValueW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
          L"StoragePoliciesNotified",
          4u,
          &v24,
          4u);
        v25 = 3;
        v9 = &v25;
LABEL_17:
        v26 = v9;
        SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(
          &SystemSettings::StorageSenseHandlers::g_policySingleton,
          &v26);
        goto LABEL_22;
      }
      goto LABEL_18;
    }
  }
LABEL_22:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl'::`2'::impl) )
  {
    v25 = 4;
    v26 = &v25;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(
      &SystemSettings::StorageSenseHandlers::g_policySingleton,
      &v26);
  }
  else
  {
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1801068F0);
  }
  v17 = SettingsHandlersStorageSenseLogging::Provider();
  if ( *(_DWORD *)v17 && (unsigned __int8)tlgKeywordOn(v17, 0x400000000000LL) )
  {
    v25 = IsCleanMgrPresent;
    v24 = v23;
    v28 = v21;
    LODWORD(v26) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)&unk_180152786,
      0,
      v18,
      (__int64)&v26,
      (__int64)&v28,
      (__int64)&v24,
      (__int64)&v25);
  }
  std::wstring::_Tidy_deallocate(v30);
  return (unsigned int)IsCleanMgrPresent;
}

```

## disassembly

```asm
0x1800812d0  mov     [rsp-8+arg_10], rbx
0x1800812d5  push    rbp
0x1800812d6  push    rsi
0x1800812d7  push    rdi
0x1800812d8  push    r12
0x1800812da  push    r14
0x1800812dc  lea     rbp, [rsp-37h]
0x1800812e1  sub     rsp, 0B0h
0x1800812e8  mov     rax, cs:__security_cookie
0x1800812ef  xor     rax, rsp
0x1800812f2  mov     [rbp+57h+var_30], rax
0x1800812f6  mov     rbx, rdx
0x1800812f9  mov     r14, rcx
0x1800812fc  mov     rdx, [rcx+58h]
0x180081300  mov     esi, [rdx+18h]
0x180081303  mov     edi, [rdx+1Ch]
0x180081306  mov     [rbp+57h+var_90], 0
0x18008130a  mov     [rbp+57h+var_8C], 0
0x180081311  mov     rdx, [rdx+20h]
0x180081315  lea     rcx, [rbp+57h+var_50]
0x180081319  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008131e  nop
0x18008131f  mov     [rbp+57h+Data], 1
0x180081326  mov     r12d, 4
0x18008132c  mov     [rsp+0D0h+cbData], r12d; cbData
0x180081331  lea     rax, [rbp+57h+Data]
0x180081335  mov     [rsp+0D0h+lpData], rax; lpData
0x18008133a  mov     r9d, r12d; dwType
0x18008133d  lea     r8, ValueName; "StoragePoliciesChanged"
0x180081344  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008134b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180081352  call    cs:__imp_RegSetKeyValueW
0x180081358  lea     eax, [rsi-3]
0x18008135b  test    eax, 0FFFFFFFDh
0x180081360  mov     rax, [rbx]
0x180081363  mov     rcx, rbx
0x180081366  jz      loc_18008149A
0x18008136c  cmp     esi, 0Ah
0x18008136f  jnz     short loc_1800813B8
0x180081371  lea     rdx, [rbp+57h+var_8C]
0x180081375  mov     rax, [rax+60h]
0x180081379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008137e  mov     rax, [r14]
0x180081381  mov     byte ptr [rsp+0D0h+lpData], 1
0x180081386  mov     r9d, [rbp+57h+var_8C]
0x18008138a  mov     r8d, edi
0x18008138d  mov     edx, esi
0x18008138f  mov     rcx, r14
0x180081392  mov     rax, [rax+110h]
0x180081399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008139e  mov     edi, eax
0x1800813a0  test    eax, eax
0x1800813a2  js      loc_1800814EC
0x1800813a8  mov     [rbp+57h+var_88], 2
0x1800813af  lea     rax, [rbp+57h+var_88]
0x1800813b3  jmp     loc_18008147B
0x1800813b8  lea     rdx, [rbp+57h+var_90]
0x1800813bc  mov     rax, [rax+90h]
0x1800813c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800813c8  mov     edi, eax
0x1800813ca  test    eax, eax
0x1800813cc  js      loc_1800814EC
0x1800813d2  cmp     esi, 6
0x1800813d5  jz      loc_180081491
0x1800813db  cmp     esi, 2
0x1800813de  jnz     short loc_18008141A
0x1800813e0  mov     [rbp+57h+var_8F], 0
0x1800813e4  lea     rcx, [rbp+57h+var_8F]; this
0x1800813e8  call    ?IsCleanMgrPresent@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEA_N@Z; SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsCleanMgrPresent(bool *)
0x1800813ed  mov     edi, eax
0x1800813ef  test    eax, eax
0x1800813f1  js      loc_1800814EC
0x1800813f7  cmp     [rbp+57h+var_8F], 0
0x1800813fb  jz      short loc_18008141A
0x1800813fd  cmp     [rbp+57h+var_90], 0
0x180081401  jnz     short loc_180081407
0x180081403  xor     ecx, ecx
0x180081405  jmp     short loc_18008140A
0x180081407  or      ecx, 0FFFFFFFFh
0x18008140a  call    cs:__imp_SilentCleanupTaskSetEnabledState
0x180081410  test    eax, eax
0x180081412  mov     edi, eax
0x180081414  js      loc_1800814EC
0x18008141a  xor     r8d, r8d
0x18008141d  cmp     [rbp+57h+var_90], r8b
0x180081421  setnz   r8b
0x180081425  xor     edx, edx
0x180081427  mov     ecx, esi
0x180081429  call    cs:__imp_SetStoragePolicySettings
0x18008142f  mov     edi, eax
0x180081431  test    eax, eax
0x180081433  js      loc_1800814EC
0x180081439  test    esi, esi
0x18008143b  jnz     short loc_180081491
0x18008143d  mov     [rbp+57h+var_88], 1
0x180081444  mov     [rsp+0D0h+cbData], r12d; cbData
0x180081449  lea     rax, [rbp+57h+var_88]
0x18008144d  mov     [rsp+0D0h+lpData], rax; lpData
0x180081452  mov     r9d, r12d; dwType
0x180081455  lea     r8, aStoragepolicie_0; "StoragePoliciesNotified"
0x18008145c  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180081463  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008146a  call    cs:__imp_RegSetKeyValueW
0x180081470  mov     [rbp+57h+var_84], 3
0x180081477  lea     rax, [rbp+57h+var_84]
0x18008147b  mov     [rbp+57h+var_80], rax
0x18008147f  lea     rdx, [rbp+57h+var_80]
0x180081483  lea     rcx, ?g_policySingleton@StorageSenseHandlers@SystemSettings@@3V?$CListOperationSingleton@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SingletonHelpers@12@A; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring> SystemSettings::StorageSenseHandlers::g_policySingleton
0x18008148a  call    ??$_Notify@V_lambda_85500d1d50c263a6fc3da139d6425a19_@@@?$CSingletonHelper@W4VolumeUpdateNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_85500d1d50c263a6fc3da139d6425a19_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(_lambda_85500d1d50c263a6fc3da139d6425a19_ const &)
0x18008148f  jmp     short loc_1800814EC
0x180081491  cmp     [rbp+57h+var_90], 0
0x180081495  setnz   bl
0x180081498  jmp     short loc_1800814D4
0x18008149a  lea     rdx, [rbp+57h+var_8C]
0x18008149e  mov     rax, [rax+60h]
0x1800814a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800814a7  mov     rax, [r14]
0x1800814aa  mov     byte ptr [rsp+0D0h+lpData], 0
0x1800814af  mov     r9d, [rbp+57h+var_8C]
0x1800814b3  mov     r8d, edi
0x1800814b6  mov     edx, esi
0x1800814b8  mov     rcx, r14
0x1800814bb  mov     rax, [rax+110h]
0x1800814c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800814c7  mov     edi, eax
0x1800814c9  test    eax, eax
0x1800814cb  js      short loc_1800814EC
0x1800814cd  cmp     [rbp+57h+var_8C], 0
0x1800814d1  setnbe  bl
0x1800814d4  lea     rdx, [rbp+57h+var_50]
0x1800814d8  lea     rcx, [rbp+57h+var_70]
0x1800814dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800814e1  mov     r8b, bl
0x1800814e4  mov     rdx, rax
0x1800814e7  call    ?SetIsItemChecked@?$CListOperationSingleton@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring>::SetIsItemChecked(std::wstring,bool)
0x1800814ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix> `wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl(void)'::`2'::impl
0x1800814f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(void)
0x1800814f8  test    al, al
0x1800814fa  jz      short loc_18008151A
0x1800814fc  mov     [rbp+57h+var_84], r12d
0x180081500  lea     rax, [rbp+57h+var_84]
0x180081504  mov     [rbp+57h+var_80], rax
0x180081508  lea     rdx, [rbp+57h+var_80]
0x18008150c  lea     rcx, ?g_policySingleton@StorageSenseHandlers@SystemSettings@@3V?$CListOperationSingleton@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SingletonHelpers@12@A; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring> SystemSettings::StorageSenseHandlers::g_policySingleton
0x180081513  call    ??$_Notify@V_lambda_85500d1d50c263a6fc3da139d6425a19_@@@?$CSingletonHelper@W4VolumeUpdateNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_85500d1d50c263a6fc3da139d6425a19_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(_lambda_85500d1d50c263a6fc3da139d6425a19_ const &)
0x180081518  jmp     short loc_180081529
0x18008151a  lea     rdx, stru_1801068F0; unsigned __int16 *
0x180081521  mov     rcx, r14; this
0x180081524  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180081529  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18008152e  mov     r9, rax
0x180081531  mov     ecx, [rax]
0x180081533  test    ecx, ecx
0x180081535  jz      short loc_180081597
0x180081537  mov     rdx, 400000000000h
0x180081541  mov     rcx, rax
0x180081544  call    _tlgKeywordOn
0x180081549  test    al, al
0x18008154b  jz      short loc_180081597
0x18008154d  mov     [rbp+57h+var_84], edi
0x180081550  mov     ecx, [rbp+57h+var_8C]
0x180081553  mov     [rbp+57h+var_88], ecx
0x180081556  movzx   eax, [rbp+57h+var_90]
0x18008155a  mov     [rbp+57h+var_74], eax
0x18008155d  mov     dword ptr [rbp+57h+var_80], esi
0x180081560  lea     rax, [rbp+57h+var_84]
0x180081564  mov     [rsp+0D0h+var_98], rax
0x180081569  lea     rax, [rbp+57h+var_88]
0x18008156d  mov     [rsp+0D0h+var_A0], rax
0x180081572  lea     rax, [rbp+57h+var_74]
0x180081576  mov     qword ptr [rsp+0D0h+cbData], rax
0x18008157b  lea     rax, [rbp+57h+var_80]
0x18008157f  mov     [rsp+0D0h+lpData], rax
0x180081584  xor     r8d, r8d
0x180081587  lea     rdx, unk_180152786
0x18008158e  mov     rcx, r9
0x180081591  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180081596  nop
0x180081597  lea     rcx, [rbp+57h+var_50]
0x18008159b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800815a0  mov     eax, edi
0x1800815a2  mov     rcx, [rbp+57h+var_30]
0x1800815a6  xor     rcx, rsp; StackCookie
0x1800815a9  call    __security_check_cookie
0x1800815ae  mov     rbx, [rsp+0D0h+arg_10]
0x1800815b6  add     rsp, 0B0h
0x1800815bd  pop     r14
0x1800815bf  pop     r12
0x1800815c1  pop     rdi
0x1800815c2  pop     rsi
0x1800815c3  pop     rbp
0x1800815c4  retn
```
