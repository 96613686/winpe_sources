# DesktopSettingBackupRestoreHandler::OnRestore(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800fec70`
- end: `0x1800ff0f6`
- name: `?OnRestore@DesktopSettingBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `1158`
- prototype: `void __high(const struct _GUID *, const char *, struct wil::cloud_store)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000d688`
- `0x18000ed08`
- `0x180015a58`
- `0x18001ac54`
- `0x1800225d4`
- `0x180022ef0`
- `0x180024084`
- `0x1800284d0`
- `0x180036a3c`
- `0x180096af4`
- `0x1800a0f70`
- `0x1800fe568`
- `0x1800fe8e8`
- `0x1800fe920`
- `0x1800fe948`
- `0x1800fe9dc`
- `0x1800fec70`
- `0x1800ff1c8`
- `0x1800ff290`
- `0x1800ff778`
- `0x1800ff964`

## import_xrefs

- `SHCORE!SHRegGetValueW` at `0x1800fee38`
- `SHCORE!SHRegGetValueW` at `0x1800fef89`
- `SHCORE!SHRegGetValueW` at `0x1800fee38`
- `SHCORE!SHRegGetValueW` at `0x1800fef89`
- `SHCORE!__imp_SHRegSetValue` at `0x1800ff0b4`
- `SHCORE!__imp_SHRegSetValue` at `0x1800ff0b4`
- `USER32!SendMessageW` at `0x1800feff1`
- `USER32!SendMessageW` at `0x1800feff1`
- `USER32!GetShellWindow` at `0x1800fefdd`
- `USER32!GetShellWindow` at `0x1800fefdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DesktopSettingBackupRestoreHandler::OnRestore(__int64 a1, __int64 a2, __int64 a3, wil::cloud_store *a4)
{
  const unsigned __int16 *v6; // rdx
  __int64 *v7; // rdi
  __int64 v8; // rcx
  void **v9; // rax
  __int64 v10; // rax
  int DWORD; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // ebx
  LSTATUS ValueW; // eax
  LSTATUS v16; // ebx
  int v17; // eax
  int v18; // ebx
  int v19; // eax
  int v20; // ebx
  DWORD v21; // ebx
  void *pvData; // r15
  LSTATUS v23; // eax
  LSTATUS v24; // ebx
  HWND ShellWindow; // rax
  const unsigned __int16 *v26; // rdx
  LSTATUS v27; // eax
  int v28; // ebx
  int pdwType; // [rsp+28h] [rbp-59h]
  int pdwTypea; // [rsp+28h] [rbp-59h]
  int pdwTypeb; // [rsp+28h] [rbp-59h]
  int pdwTypec; // [rsp+28h] [rbp-59h]
  _BYTE v33[8]; // [rsp+48h] [rbp-39h] BYREF
  DWORD dwType; // [rsp+50h] [rbp-31h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-2Dh] BYREF
  unsigned int v36; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v37[3]; // [rsp+60h] [rbp-21h] BYREF
  void **v38; // [rsp+78h] [rbp-9h] BYREF
  _BYTE v39[48]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v40; // [rsp+B0h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  DWORD cbData; // [rsp+E8h] [rbp+67h] BYREF
  wil::cloud_store *v43; // [rsp+100h] [rbp+7Fh]

  v43 = a4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::DesktopSettingsActivity::StartActivity(
      (CloudRestoreLauncherTelemetry::DesktopSettingsActivity *)(a1 + 16),
      v6);
  v7 = (__int64 *)(a1 + 8);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v8 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>,wil::err_returncode_policy>::reset(a1 + 8);
  v9 = tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::ensure_data((void **)(a1 + 8));
  tip2::details::shared_data<0,0,0>::start((char *)*v9 + 8, v37);
  v38 = &tip2::test_watcher<tip2::details::merged_data<_tip_NightlightRestoreTipTest,_tip_NightlightRestoreTipTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v39,
    (struct wil::details::IFailureCallback *)&v38,
    0,
    1);
  v10 = *v7;
  v40 = v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 280));
  v35 = 0;
  DWORD = SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop",
            L"IconSizeMigration",
            &v35);
  v12 = DWORD;
  if ( DWORD < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
      (const char *)(unsigned int)DWORD,
      pdwType);
    if ( v12 != -2147024894 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v17 = SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop", L"IconSize", v35);
  v18 = v17;
  if ( v17 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
      (const char *)(unsigned int)v17,
      pdwType);
  if ( v18 >= 0 )
  {
LABEL_10:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(
                            a1 + 8,
                            v33)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(v33);
    goto LABEL_11;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2B,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
    (const char *)(unsigned int)v18,
    pdwType);
LABEL_11:
  v36 = 0;
  v13 = SHRegGetDWORD(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop",
          L"FFlagsMigration",
          &v36);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
      (const char *)(unsigned int)v13,
      pdwType);
    if ( v14 != -2147024894 )
      goto LABEL_14;
    goto LABEL_13;
  }
  v19 = SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop", L"FFlags", v36);
  v20 = v19;
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
      (const char *)(unsigned int)v19,
      pdwType);
  if ( v20 >= 0 )
  {
LABEL_13:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(
                            a1 + 8,
                            v33)
             + 273LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(v33);
    goto LABEL_14;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
    (const char *)(unsigned int)v20,
    pdwType);
LABEL_14:
  cbData = 0;
  dwType = 3;
  ValueW = SHRegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop",
             L"SortMigration",
             8,
             &dwType,
             0,
             &cbData);
  v16 = ValueW;
  if ( ValueW >= 0 )
  {
    v21 = cbData;
    pvData = operator new[](cbData);
    memset_0(pvData, 0, v21);
    v37[0] = pvData;
    v23 = SHRegGetValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop",
            L"SortMigration",
            8,
            &dwType,
            pvData,
            &cbData);
    v24 = v23;
    if ( v23 >= 0 )
    {
      v27 = SHRegSetValue(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\Shell\\Bags\\1\\Desktop",
              L"Sort",
              8,
              dwType,
              pvData,
              cbData);
      v28 = v27;
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
          (const char *)(unsigned int)v27,
          pdwTypec);
      if ( v28 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
          (const char *)(unsigned int)v28,
          pdwTypec);
        goto LABEL_28;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
        (const char *)(unsigned int)v23,
        pdwTypeb);
      if ( v24 != -2147024894 )
      {
LABEL_28:
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v37);
        goto LABEL_29;
      }
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(
                            a1 + 8,
                            v33)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(v33);
    goto LABEL_28;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x48,
    (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\desktopsettingbackuprestorehandler.cpp",
    (const char *)(unsigned int)ValueW,
    pdwTypea);
  if ( v16 == -2147024894 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(
                            a1 + 8,
                            v33)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(v33);
  }
LABEL_29:
  ShellWindow = GetShellWindow();
  SendMessageW(ShellWindow, 0x462u, 0, 0);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(
                          a1 + 8,
                          v37)
           + 275LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(v37);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::DesktopSettingsActivity::DesktopSettings_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[33],unsigned short const (&)[8]>();
  if ( *v7 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(*v7 + 8);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::DesktopSettingsActivity::Stop(
      (CloudRestoreLauncherTelemetry::DesktopSettingsActivity *)(a1 + 16),
      v26);
  tip2::test_watcher<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_watcher<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(&v38);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x1800fec70  mov     rax, rsp
0x1800fec73  mov     [rax+10h], rbx
0x1800fec77  mov     [rax+18h], rsi
0x1800fec7b  mov     [rax+20h], r9
0x1800fec7f  push    rbp
0x1800fec80  push    rdi
0x1800fec81  push    r12
0x1800fec83  push    r14
0x1800fec85  push    r15
0x1800fec87  lea     rbp, [rax-5Fh]
0x1800fec8b  sub     rsp, 0B0h
0x1800fec92  mov     r12, r9
0x1800fec95  mov     r14, rcx
0x1800fec98  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800fec9f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800feca4  test    al, al
0x1800feca6  jz      short loc_1800FECB1
0x1800feca8  lea     rcx, [r14+10h]; this
0x1800fecac  call    ?StartActivity@DesktopSettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::DesktopSettingsActivity::StartActivity(ushort const *)
0x1800fecb1  lea     rdi, [r14+8]
0x1800fecb5  mov     rcx, [rdi]
0x1800fecb8  test    rcx, rcx
0x1800fecbb  jz      short loc_1800FECD2
0x1800fecbd  add     rcx, 8
0x1800fecc1  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x1800fecc6  test    al, al
0x1800fecc8  jz      short loc_1800FECD2
0x1800fecca  mov     rcx, rdi
0x1800feccd  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>,wil::err_returncode_policy>::reset(void)
0x1800fecd2  mov     rcx, rdi
0x1800fecd5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::ensure_data(void)
0x1800fecda  mov     rcx, [rax]
0x1800fecdd  add     rcx, 8
0x1800fece1  lea     rdx, [rbp+57h+var_78]
0x1800fece5  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800fecea  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_NightlightRestoreTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_NightlightRestoreTipTest,_tip_NightlightRestoreTipTest>>::`vftable'
0x1800fecf1  mov     [rbp+57h+var_60], rax
0x1800fecf5  mov     r9b, 1; bool
0x1800fecf8  xor     r8d, r8d; struct wil::CallContextInfo *
0x1800fecfb  lea     rdx, [rbp+57h+var_60]; struct wil::details::IFailureCallback *
0x1800fecff  lea     rcx, [rbp+57h+var_58]; this
0x1800fed03  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800fed08  mov     rax, [rdi]
0x1800fed0b  mov     [rbp+57h+var_28], rax
0x1800fed0f  test    rax, rax
0x1800fed12  jz      short loc_1800FED1B
0x1800fed14  lock inc dword ptr [rax+118h]
0x1800fed1b  mov     [rbp+57h+var_84], 0
0x1800fed22  lea     r9, [rbp+57h+var_84]; unsigned int *
0x1800fed26  lea     r8, aIconsizemigrat; "IconSizeMigration"
0x1800fed2d  lea     r15, pszSubKey; "Software\\Microsoft\\Windows\\Shell\\Ba"...
0x1800fed34  mov     rdx, r15; unsigned __int16 *
0x1800fed37  mov     rsi, 0FFFFFFFF80000001h
0x1800fed3e  mov     rcx, rsi; HKEY
0x1800fed41  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800fed46  mov     ebx, eax
0x1800fed48  mov     rcx, [rbp+5Fh]; this
0x1800fed4c  test    eax, eax
0x1800fed4e  jns     loc_1800FEE8C
0x1800fed54  mov     r9d, eax; char *
0x1800fed57  lea     rsi, aPcshellShellCl_34; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800fed5e  mov     r8, rsi; unsigned int
0x1800fed61  mov     edx, 28h ; '('; void *
0x1800fed66  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fed6b  cmp     ebx, 80070002h
0x1800fed71  jnz     short loc_1800FED92
0x1800fed73  lea     rdx, [rbp+57h+var_90]
0x1800fed77  mov     rcx, rdi
0x1800fed7a  call    ??C?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(void)
0x1800fed7f  mov     rcx, [rax]
0x1800fed82  mov     byte ptr [rcx+110h], 1
0x1800fed89  lea     rcx, [rbp+57h+var_90]
0x1800fed8d  call    ??1?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(void)
0x1800fed92  mov     [rbp+57h+var_80], 0
0x1800fed99  lea     r9, [rbp+57h+var_80]; unsigned int *
0x1800fed9d  lea     r8, aFflagsmigratio; "FFlagsMigration"
0x1800feda4  mov     rdx, r15; unsigned __int16 *
0x1800feda7  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800fedae  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800fedb3  mov     ebx, eax
0x1800fedb5  mov     rcx, [rbp+5Fh]; this
0x1800fedb9  test    eax, eax
0x1800fedbb  jns     loc_1800FEEE4
0x1800fedc1  mov     r9d, eax; char *
0x1800fedc4  mov     r8, rsi; unsigned int
0x1800fedc7  mov     edx, 37h ; '7'; void *
0x1800fedcc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fedd1  cmp     ebx, 80070002h
0x1800fedd7  jnz     short loc_1800FEDF8
0x1800fedd9  lea     rdx, [rbp+57h+var_90]
0x1800feddd  mov     rcx, rdi
0x1800fede0  call    ??C?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(void)
0x1800fede5  mov     rcx, [rax]
0x1800fede8  mov     byte ptr [rcx+111h], 1
0x1800fedef  lea     rcx, [rbp+57h+var_90]
0x1800fedf3  call    ??1?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(void)
0x1800fedf8  mov     [rbp+57h+cbData], 0
0x1800fedff  mov     [rbp+57h+dwType], 3
0x1800fee06  lea     rax, [rbp+57h+cbData]
0x1800fee0a  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800fee0f  mov     [rsp+0D0h+pvData], 0; pvData
0x1800fee18  lea     rax, [rbp+57h+dwType]
0x1800fee1c  mov     [rsp+0D0h+pdwType], rax; int
0x1800fee21  mov     r9d, 8; srrfFlags
0x1800fee27  lea     r8, pszValue; "SortMigration"
0x1800fee2e  mov     rdx, r15; pszSubKey
0x1800fee31  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800fee38  call    cs:__imp_SHRegGetValueW
0x1800fee3e  mov     ebx, eax
0x1800fee40  mov     rcx, [rbp+5Fh]; this
0x1800fee44  test    eax, eax
0x1800fee46  jns     loc_1800FEF39
0x1800fee4c  mov     r9d, eax; char *
0x1800fee4f  mov     r8, rsi; unsigned int
0x1800fee52  mov     edx, 48h ; 'H'; void *
0x1800fee57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fee5c  cmp     ebx, 80070002h
0x1800fee62  jnz     loc_1800FEFDD
0x1800fee68  lea     rdx, [rbp+57h+var_90]
0x1800fee6c  mov     rcx, rdi
0x1800fee6f  call    ??C?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(void)
0x1800fee74  mov     rcx, [rax]
0x1800fee77  mov     byte ptr [rcx+112h], 1
0x1800fee7e  lea     rcx, [rbp+57h+var_90]
0x1800fee82  call    ??1?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(void)
0x1800fee87  jmp     loc_1800FEFDD
0x1800fee8c  mov     r9d, [rbp+57h+var_84]; unsigned int
0x1800fee90  lea     r8, aIconsize; "IconSize"
0x1800fee97  mov     rdx, r15; unsigned __int16 *
0x1800fee9a  mov     rcx, rsi; HKEY
0x1800fee9d  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800feea2  mov     ebx, eax
0x1800feea4  mov     rcx, [rbp+5Fh]; this
0x1800feea8  lea     rsi, aPcshellShellCl_34; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800feeaf  test    eax, eax
0x1800feeb1  jns     short loc_1800FEEC3
0x1800feeb3  mov     r9d, eax; char *
0x1800feeb6  mov     r8, rsi; unsigned int
0x1800feeb9  mov     edx, 2Ah ; '*'; void *
0x1800feebe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800feec3  mov     rcx, [rbp+5Fh]; this
0x1800feec7  test    ebx, ebx
0x1800feec9  jns     loc_1800FED73
0x1800feecf  mov     r9d, ebx; char *
0x1800feed2  mov     r8, rsi; unsigned int
0x1800feed5  mov     edx, 2Bh ; '+'; void *
0x1800feeda  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800feedf  jmp     loc_1800FED92
0x1800feee4  mov     r9d, [rbp+57h+var_80]; unsigned int
0x1800feee8  lea     r8, aFflags; "FFlags"
0x1800feeef  mov     rdx, r15; unsigned __int16 *
0x1800feef2  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800feef9  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800feefe  mov     ebx, eax
0x1800fef00  mov     rcx, [rbp+5Fh]; this
0x1800fef04  test    eax, eax
0x1800fef06  jns     short loc_1800FEF18
0x1800fef08  mov     r9d, eax; char *
0x1800fef0b  mov     r8, rsi; unsigned int
0x1800fef0e  mov     edx, 39h ; '9'; void *
0x1800fef13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fef18  mov     rcx, [rbp+5Fh]; this
0x1800fef1c  test    ebx, ebx
0x1800fef1e  jns     loc_1800FEDD9
0x1800fef24  mov     r9d, ebx; char *
0x1800fef27  mov     r8, rsi; unsigned int
0x1800fef2a  mov     edx, 3Ah ; ':'; void *
0x1800fef2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fef34  jmp     loc_1800FEDF8
0x1800fef39  mov     ebx, [rbp+57h+cbData]
0x1800fef3c  mov     ecx, ebx; unsigned __int64
0x1800fef3e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800fef43  mov     r15, rax
0x1800fef46  mov     r8d, ebx; Size
0x1800fef49  xor     edx, edx; Val
0x1800fef4b  mov     rcx, rax; void *
0x1800fef4e  call    memset_0
0x1800fef53  mov     [rbp+57h+var_78], r15
0x1800fef57  lea     rax, [rbp+57h+cbData]
0x1800fef5b  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800fef60  mov     [rsp+0D0h+pvData], r15; pvData
0x1800fef65  lea     rax, [rbp+57h+dwType]
0x1800fef69  mov     [rsp+0D0h+pdwType], rax; int
0x1800fef6e  mov     r9d, 8; srrfFlags
0x1800fef74  lea     r8, pszValue; "SortMigration"
0x1800fef7b  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\Shell\\Ba"...
0x1800fef82  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800fef89  call    cs:__imp_SHRegGetValueW
0x1800fef8f  mov     ebx, eax
0x1800fef91  mov     rcx, [rbp+5Fh]; this
0x1800fef95  test    eax, eax
0x1800fef97  jns     loc_1800FF084
0x1800fef9d  mov     r9d, eax; char *
0x1800fefa0  mov     r8, rsi; unsigned int
0x1800fefa3  mov     edx, 4Ch ; 'L'; void *
0x1800fefa8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fefad  cmp     ebx, 80070002h
0x1800fefb3  jnz     short loc_1800FEFD4
0x1800fefb5  lea     rdx, [rbp+57h+var_90]
0x1800fefb9  mov     rcx, rdi
0x1800fefbc  call    ??C?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(void)
0x1800fefc1  mov     rcx, [rax]
0x1800fefc4  mov     byte ptr [rcx+112h], 1
0x1800fefcb  lea     rcx, [rbp+57h+var_90]
0x1800fefcf  call    ??1?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(void)
0x1800fefd4  lea     rcx, [rbp+57h+var_78]
0x1800fefd8  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800fefdd  call    cs:__imp_GetShellWindow
0x1800fefe3  mov     rcx, rax; hWnd
0x1800fefe6  xor     r9d, r9d; lParam
0x1800fefe9  xor     r8d, r8d; wParam
0x1800fefec  mov     edx, 462h; Msg
0x1800feff1  call    cs:__imp_SendMessageW
0x1800feff7  lea     rdx, [rbp+57h+var_78]
0x1800feffb  mov     rcx, rdi
0x1800feffe  call    ??C?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::operator->(void)
0x1800ff003  mov     rcx, [rax]
0x1800ff006  mov     byte ptr [rcx+113h], 1
0x1800ff00d  lea     rcx, [rbp+57h+var_78]
0x1800ff011  call    ??1?$test_data_control@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(void)
0x1800ff016  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800ff01d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800ff022  test    al, al
0x1800ff024  jz      short loc_1800FF02B
0x1800ff026  call    ??$DesktopSettings_ApiActivity@AEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@DesktopSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::DesktopSettingsActivity::DesktopSettings_ApiActivity<ushort const (&)[12],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[33],ushort const (&)[8])
0x1800ff02b  mov     rcx, [rdi]
0x1800ff02e  test    rcx, rcx
0x1800ff031  jz      short loc_1800FF03C
0x1800ff033  add     rcx, 8
0x1800ff037  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1800ff03c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800ff043  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800ff048  test    al, al
0x1800ff04a  jz      short loc_1800FF056
0x1800ff04c  lea     rcx, [r14+10h]; this
0x1800ff050  call    ?Stop@DesktopSettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::DesktopSettingsActivity::Stop(ushort const *)
0x1800ff055  nop
0x1800ff056  lea     rcx, [rbp+57h+var_60]
0x1800ff05a  call    ??1?$test_watcher@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::~test_watcher<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>(void)
0x1800ff05f  nop
0x1800ff060  mov     rcx, r12; this
0x1800ff063  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800ff068  lea     r11, [rsp+0D0h+var_20]
0x1800ff070  mov     rbx, [r11+38h]
0x1800ff074  mov     rsi, [r11+40h]
0x1800ff078  mov     rsp, r11
0x1800ff07b  pop     r15
0x1800ff07d  pop     r14
0x1800ff07f  pop     r12
0x1800ff081  pop     rdi
0x1800ff082  pop     rbp
0x1800ff083  retn
0x1800ff084  mov     eax, [rbp+57h+cbData]
0x1800ff087  mov     r8d, [rbp+57h+dwType]
0x1800ff08b  mov     dword ptr [rsp+0D0h+pcbData], eax; cbData
0x1800ff08f  mov     [rsp+0D0h+pvData], r15; pvData
0x1800ff094  mov     dword ptr [rsp+0D0h+pdwType], r8d; int
0x1800ff099  mov     r9d, 8; srrfFlags
0x1800ff09f  lea     r8, aSort; "Sort"
0x1800ff0a6  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\Shell\\Ba"...
0x1800ff0ad  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800ff0b4  call    cs:__imp_SHRegSetValue
0x1800ff0ba  mov     ebx, eax
0x1800ff0bc  mov     rcx, [rbp+5Fh]; this
0x1800ff0c0  test    eax, eax
0x1800ff0c2  jns     short loc_1800FF0D4
0x1800ff0c4  mov     r9d, eax; char *
0x1800ff0c7  mov     r8, rsi; unsigned int
0x1800ff0ca  mov     edx, 4Eh ; 'N'; void *
0x1800ff0cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff0d4  mov     rcx, [rbp+5Fh]; this
0x1800ff0d8  test    ebx, ebx
0x1800ff0da  jns     loc_1800FEFB5
0x1800ff0e0  mov     r9d, ebx; char *
0x1800ff0e3  mov     r8, rsi; unsigned int
0x1800ff0e6  mov     edx, 4Fh ; 'O'; void *
0x1800ff0eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff0f0  jmp     loc_1800FEFD4
```
