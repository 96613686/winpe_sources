# SystemSettings::StorageSenseHandlers::CStoragePolicySettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180080fd0`
- end: `0x1800812c5`
- name: `?SetValue@?$CStoragePolicySettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
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
- `0x180080fd0`
- `0x180081840`
- `0x1800b4240`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180081052`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008116a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180081052`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008116a`
- `ext-ms-win-storage-sense-l1-2-3!SilentCleanupTaskSetEnabledState` at `0x18008110a`
- `ext-ms-win-storage-sense-l1-2-3!SilentCleanupTaskSetEnabledState` at `0x18008110a`
- `ext-ms-win-storage-sense-l1-2-0!SetStoragePolicySettings` at `0x180081129`
- `ext-ms-win-storage-sense-l1-2-0!SetStoragePolicySettings` at `0x180081129`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStoragePolicySettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(
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
  __int64 v11; // rcx
  bool v12; // bl
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  const struct _tlgProvider_t *v16; // rax
  int v17; // r9d
  int lpData; // [rsp+20h] [rbp-59h]
  unsigned __int8 v20; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v21[3]; // [rsp+41h] [rbp-38h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-35h] BYREF
  int v23; // [rsp+48h] [rbp-31h] BYREF
  int v24; // [rsp+4Ch] [rbp-2Dh] BYREF
  int *v25; // [rsp+50h] [rbp-29h] BYREF
  int Data; // [rsp+58h] [rbp-21h] BYREF
  int v27; // [rsp+5Ch] [rbp-1Dh] BYREF
  _BYTE v28[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v29[32]; // [rsp+80h] [rbp+7h] BYREF

  v4 = *((_QWORD *)this + 11);
  v5 = *(_DWORD *)(v4 + 24);
  v6 = *(_DWORD *)(v4 + 28);
  v20 = 0;
  v22 = 0;
  std::wstring::wstring(v29);
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
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v7 + 96))(a2, &v22);
    LOBYTE(lpData) = 0;
    IsCleanMgrPresent = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)this + 272LL))(
                          this,
                          v5,
                          v6,
                          v22,
                          lpData);
    if ( IsCleanMgrPresent < 0 )
      goto LABEL_22;
    v12 = v22 != 0;
    goto LABEL_21;
  }
  if ( v5 == 10 )
  {
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v7 + 96))(a2, &v22);
    LOBYTE(lpData) = 1;
    IsCleanMgrPresent = (*(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, __int64, _QWORD, _QWORD, int))(*(_QWORD *)this + 272LL))(
                          this,
                          10,
                          v6,
                          v22,
                          lpData);
    if ( IsCleanMgrPresent < 0 )
      goto LABEL_22;
    v23 = 2;
    v9 = &v23;
    goto LABEL_17;
  }
  IsCleanMgrPresent = (*(__int64 (__fastcall **)(__int64 *, unsigned __int8 *))(v7 + 144))(a2, &v20);
  if ( IsCleanMgrPresent < 0 )
    goto LABEL_22;
  if ( v5 == 6 )
  {
LABEL_18:
    v12 = v20 != 0;
LABEL_21:
    v13 = std::wstring::wstring(v28, v29);
    LOBYTE(v14) = v12;
    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring>::SetIsItemChecked(
      v15,
      v13,
      v14);
    goto LABEL_22;
  }
  if ( v5 != 2
    || (v21[0] = 0,
        IsCleanMgrPresent = SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsCleanMgrPresent(
                              (SystemSettings::StorageSenseHandlers::ExecutionHelpers *)v21,
                              v10),
        IsCleanMgrPresent >= 0)
    && (!v21[0]
     || (v20 ? (v11 = 0xFFFFFFFFLL) : (v11 = 0),
         IsCleanMgrPresent = SilentCleanupTaskSetEnabledState(v11),
         IsCleanMgrPresent >= 0)) )
  {
    IsCleanMgrPresent = SetStoragePolicySettings(v5, 0, v20 != 0);
    if ( IsCleanMgrPresent >= 0 )
    {
      if ( !v5 )
      {
        v23 = 1;
        RegSetKeyValueW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\StoragePolicy",
          L"StoragePoliciesNotified",
          4u,
          &v23,
          4u);
        v24 = 3;
        v9 = &v24;
LABEL_17:
        v25 = v9;
        SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(
          &SystemSettings::StorageSenseHandlers::g_policySingleton,
          &v25);
        goto LABEL_22;
      }
      goto LABEL_18;
    }
  }
LABEL_22:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl'::`2'::impl) )
  {
    v24 = 4;
    v25 = &v24;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(
      &SystemSettings::StorageSenseHandlers::g_policySingleton,
      &v25);
  }
  else
  {
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1801068F0);
  }
  v16 = SettingsHandlersStorageSenseLogging::Provider();
  if ( *(_DWORD *)v16 && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL) )
  {
    v24 = IsCleanMgrPresent;
    v23 = v22;
    v27 = v20;
    LODWORD(v25) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&unk_180152930,
      0,
      v17,
      (__int64)&v25,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)&v24);
  }
  std::wstring::_Tidy_deallocate(v29);
  return (unsigned int)IsCleanMgrPresent;
}

```

## disassembly

```asm
0x180080fd0  mov     [rsp-8+arg_10], rbx
0x180080fd5  push    rbp
0x180080fd6  push    rsi
0x180080fd7  push    rdi
0x180080fd8  push    r12
0x180080fda  push    r14
0x180080fdc  lea     rbp, [rsp-37h]
0x180080fe1  sub     rsp, 0B0h
0x180080fe8  mov     rax, cs:__security_cookie
0x180080fef  xor     rax, rsp
0x180080ff2  mov     [rbp+57h+var_30], rax
0x180080ff6  mov     rbx, rdx
0x180080ff9  mov     r14, rcx
0x180080ffc  mov     rdx, [rcx+58h]
0x180081000  mov     esi, [rdx+18h]
0x180081003  mov     edi, [rdx+1Ch]
0x180081006  mov     [rbp+57h+var_90], 0
0x18008100a  mov     [rbp+57h+var_8C], 0
0x180081011  mov     rdx, [rdx+20h]
0x180081015  lea     rcx, [rbp+57h+var_50]
0x180081019  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008101e  nop
0x18008101f  mov     [rbp+57h+Data], 1
0x180081026  mov     r12d, 4
0x18008102c  mov     [rsp+0D0h+cbData], r12d; cbData
0x180081031  lea     rax, [rbp+57h+Data]
0x180081035  mov     [rsp+0D0h+lpData], rax; lpData
0x18008103a  mov     r9d, r12d; dwType
0x18008103d  lea     r8, ValueName; "StoragePoliciesChanged"
0x180081044  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008104b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180081052  call    cs:__imp_RegSetKeyValueW
0x180081058  lea     eax, [rsi-3]
0x18008105b  test    eax, 0FFFFFFFDh
0x180081060  mov     rax, [rbx]
0x180081063  mov     rcx, rbx
0x180081066  jz      loc_18008119A
0x18008106c  cmp     esi, 0Ah
0x18008106f  jnz     short loc_1800810B8
0x180081071  lea     rdx, [rbp+57h+var_8C]
0x180081075  mov     rax, [rax+60h]
0x180081079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008107e  mov     rax, [r14]
0x180081081  mov     byte ptr [rsp+0D0h+lpData], 1
0x180081086  mov     r9d, [rbp+57h+var_8C]
0x18008108a  mov     r8d, edi
0x18008108d  mov     edx, esi
0x18008108f  mov     rcx, r14
0x180081092  mov     rax, [rax+110h]
0x180081099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008109e  mov     edi, eax
0x1800810a0  test    eax, eax
0x1800810a2  js      loc_1800811EC
0x1800810a8  mov     [rbp+57h+var_88], 2
0x1800810af  lea     rax, [rbp+57h+var_88]
0x1800810b3  jmp     loc_18008117B
0x1800810b8  lea     rdx, [rbp+57h+var_90]
0x1800810bc  mov     rax, [rax+90h]
0x1800810c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800810c8  mov     edi, eax
0x1800810ca  test    eax, eax
0x1800810cc  js      loc_1800811EC
0x1800810d2  cmp     esi, 6
0x1800810d5  jz      loc_180081191
0x1800810db  cmp     esi, 2
0x1800810de  jnz     short loc_18008111A
0x1800810e0  mov     [rbp+57h+var_8F], 0
0x1800810e4  lea     rcx, [rbp+57h+var_8F]; this
0x1800810e8  call    ?IsCleanMgrPresent@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEA_N@Z; SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsCleanMgrPresent(bool *)
0x1800810ed  mov     edi, eax
0x1800810ef  test    eax, eax
0x1800810f1  js      loc_1800811EC
0x1800810f7  cmp     [rbp+57h+var_8F], 0
0x1800810fb  jz      short loc_18008111A
0x1800810fd  cmp     [rbp+57h+var_90], 0
0x180081101  jnz     short loc_180081107
0x180081103  xor     ecx, ecx
0x180081105  jmp     short loc_18008110A
0x180081107  or      ecx, 0FFFFFFFFh
0x18008110a  call    cs:__imp_SilentCleanupTaskSetEnabledState
0x180081110  test    eax, eax
0x180081112  mov     edi, eax
0x180081114  js      loc_1800811EC
0x18008111a  xor     r8d, r8d
0x18008111d  cmp     [rbp+57h+var_90], r8b
0x180081121  setnz   r8b
0x180081125  xor     edx, edx
0x180081127  mov     ecx, esi
0x180081129  call    cs:__imp_SetStoragePolicySettings
0x18008112f  mov     edi, eax
0x180081131  test    eax, eax
0x180081133  js      loc_1800811EC
0x180081139  test    esi, esi
0x18008113b  jnz     short loc_180081191
0x18008113d  mov     [rbp+57h+var_88], 1
0x180081144  mov     [rsp+0D0h+cbData], r12d; cbData
0x180081149  lea     rax, [rbp+57h+var_88]
0x18008114d  mov     [rsp+0D0h+lpData], rax; lpData
0x180081152  mov     r9d, r12d; dwType
0x180081155  lea     r8, aStoragepolicie_0; "StoragePoliciesNotified"
0x18008115c  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180081163  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008116a  call    cs:__imp_RegSetKeyValueW
0x180081170  mov     [rbp+57h+var_84], 3
0x180081177  lea     rax, [rbp+57h+var_84]
0x18008117b  mov     [rbp+57h+var_80], rax
0x18008117f  lea     rdx, [rbp+57h+var_80]
0x180081183  lea     rcx, ?g_policySingleton@StorageSenseHandlers@SystemSettings@@3V?$CListOperationSingleton@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SingletonHelpers@12@A; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring> SystemSettings::StorageSenseHandlers::g_policySingleton
0x18008118a  call    ??$_Notify@V_lambda_85500d1d50c263a6fc3da139d6425a19_@@@?$CSingletonHelper@W4VolumeUpdateNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_85500d1d50c263a6fc3da139d6425a19_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(_lambda_85500d1d50c263a6fc3da139d6425a19_ const &)
0x18008118f  jmp     short loc_1800811EC
0x180081191  cmp     [rbp+57h+var_90], 0
0x180081195  setnz   bl
0x180081198  jmp     short loc_1800811D4
0x18008119a  lea     rdx, [rbp+57h+var_8C]
0x18008119e  mov     rax, [rax+60h]
0x1800811a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800811a7  mov     rax, [r14]
0x1800811aa  mov     byte ptr [rsp+0D0h+lpData], 0
0x1800811af  mov     r9d, [rbp+57h+var_8C]
0x1800811b3  mov     r8d, edi
0x1800811b6  mov     edx, esi
0x1800811b8  mov     rcx, r14
0x1800811bb  mov     rax, [rax+110h]
0x1800811c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800811c7  mov     edi, eax
0x1800811c9  test    eax, eax
0x1800811cb  js      short loc_1800811EC
0x1800811cd  cmp     [rbp+57h+var_8C], 0
0x1800811d1  setnbe  bl
0x1800811d4  lea     rdx, [rbp+57h+var_50]
0x1800811d8  lea     rcx, [rbp+57h+var_70]
0x1800811dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800811e1  mov     r8b, bl
0x1800811e4  mov     rdx, rax
0x1800811e7  call    ?SetIsItemChecked@?$CListOperationSingleton@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring>::SetIsItemChecked(std::wstring,bool)
0x1800811ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix> `wil::Feature<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::GetImpl(void)'::`2'::impl
0x1800811f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandsUxNotRefreshingCorefix>::__private_IsEnabled(void)
0x1800811f8  test    al, al
0x1800811fa  jz      short loc_18008121A
0x1800811fc  mov     [rbp+57h+var_84], r12d
0x180081200  lea     rax, [rbp+57h+var_84]
0x180081204  mov     [rbp+57h+var_80], rax
0x180081208  lea     rdx, [rbp+57h+var_80]
0x18008120c  lea     rcx, ?g_policySingleton@StorageSenseHandlers@SystemSettings@@3V?$CListOperationSingleton@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SingletonHelpers@12@A; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<std::wstring> SystemSettings::StorageSenseHandlers::g_policySingleton
0x180081213  call    ??$_Notify@V_lambda_85500d1d50c263a6fc3da139d6425a19_@@@?$CSingletonHelper@W4VolumeUpdateNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_85500d1d50c263a6fc3da139d6425a19_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::_Notify<_lambda_85500d1d50c263a6fc3da139d6425a19_>(_lambda_85500d1d50c263a6fc3da139d6425a19_ const &)
0x180081218  jmp     short loc_180081229
0x18008121a  lea     rdx, stru_1801068F0; unsigned __int16 *
0x180081221  mov     rcx, r14; this
0x180081224  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180081229  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18008122e  mov     r9, rax
0x180081231  mov     ecx, [rax]
0x180081233  test    ecx, ecx
0x180081235  jz      short loc_180081297
0x180081237  mov     rdx, 400000000000h
0x180081241  mov     rcx, rax
0x180081244  call    _tlgKeywordOn
0x180081249  test    al, al
0x18008124b  jz      short loc_180081297
0x18008124d  mov     [rbp+57h+var_84], edi
0x180081250  mov     ecx, [rbp+57h+var_8C]
0x180081253  mov     [rbp+57h+var_88], ecx
0x180081256  movzx   eax, [rbp+57h+var_90]
0x18008125a  mov     [rbp+57h+var_74], eax
0x18008125d  mov     dword ptr [rbp+57h+var_80], esi
0x180081260  lea     rax, [rbp+57h+var_84]
0x180081264  mov     [rsp+0D0h+var_98], rax
0x180081269  lea     rax, [rbp+57h+var_88]
0x18008126d  mov     [rsp+0D0h+var_A0], rax
0x180081272  lea     rax, [rbp+57h+var_74]
0x180081276  mov     qword ptr [rsp+0D0h+cbData], rax
0x18008127b  lea     rax, [rbp+57h+var_80]
0x18008127f  mov     [rsp+0D0h+lpData], rax
0x180081284  xor     r8d, r8d
0x180081287  lea     rdx, unk_180152930
0x18008128e  mov     rcx, r9
0x180081291  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180081296  nop
0x180081297  lea     rcx, [rbp+57h+var_50]
0x18008129b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800812a0  mov     eax, edi
0x1800812a2  mov     rcx, [rbp+57h+var_30]
0x1800812a6  xor     rcx, rsp; StackCookie
0x1800812a9  call    __security_check_cookie
0x1800812ae  mov     rbx, [rsp+0D0h+arg_10]
0x1800812b6  add     rsp, 0B0h
0x1800812bd  pop     r14
0x1800812bf  pop     r12
0x1800812c1  pop     rdi
0x1800812c2  pop     rsi
0x1800812c3  pop     rbp
0x1800812c4  retn
```
