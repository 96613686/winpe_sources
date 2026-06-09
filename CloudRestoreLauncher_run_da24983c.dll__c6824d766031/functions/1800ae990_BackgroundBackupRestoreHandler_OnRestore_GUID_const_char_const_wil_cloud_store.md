# BackgroundBackupRestoreHandler::OnRestore(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800ae990`
- end: `0x1800aec63`
- name: `?OnRestore@BackgroundBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `723`
- prototype: `void __high(const struct _GUID *, const char *, struct wil::cloud_store)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18001cf84`
- `0x18001cfa4`
- `0x1800284d0`
- `0x180036a3c`
- `0x1800462bc`
- `0x18008cedc`
- `0x180095d1c`
- `0x180096af4`
- `0x1800977e8`
- `0x18009fadc`
- `0x18009fdc8`
- `0x1800a0524`
- `0x1800a0604`
- `0x1800a0628`
- `0x1800a07c8`
- `0x1800a07f0`
- `0x1800a0f70`
- `0x1800a1250`
- `0x1800a1308`
- `0x1800a1d38`
- `0x1800a48f4`
- `0x1800a50c4`
- `0x1800a52ac`
- `0x1800a5338`
- `0x1800ae990`
- `0x1800af354`
- `0x1800b08e4`
- `0x1800b13c8`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800aeba7`
- `USER32!SystemParametersInfoW` at `0x1800aeba7`

## string_xrefs

- `0x1800aebed`: `Restore Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall BackgroundBackupRestoreHandler::OnRestore(__int64 a1, __int64 a2, __int64 a3, wil::cloud_store *a4)
{
  CloudRestoreLauncherTelemetry::BackgroundActivity *v6; // r14
  HKEY v7; // rcx
  int v8; // eax
  HKEY v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // r9d
  int v14; // eax
  BackgroundBackupRestoreHandler *v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  const char *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h]
  _BYTE v20[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  char v22; // [rsp+40h] [rbp-C0h]
  wil::cloud_store *v23; // [rsp+48h] [rbp-B8h]
  _BYTE v24[64]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v25[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[48]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[64]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v23 = a4;
  v6 = (CloudRestoreLauncherTelemetry::BackgroundActivity *)(a1 + 360);
  CloudRestoreLauncherTelemetry::BackgroundActivity::StartActivity(
    (CloudRestoreLauncherTelemetry::BackgroundActivity *)(a1 + 360),
    L"Restore Started");
  tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::start_and_watch_errors(
    a1 + 16,
    v24);
  v21 = a1;
  v22 = 1;
  v8 = SHRegSetBOOL(v7, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers", L"WallpaperRestored", 0);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v8,
      v19);
  wil::cloud_store::load<Windows::Data::Background::DesktopWallpaper>(a4, v25, 9);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(
                          a1 + 16,
                          v20)
           + 273LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(v20);
  if ( (unsigned __int8)ValidateAndLogRestoreCloudDataLoad<Windows::Data::Background::DesktopWallpaper>(v25) )
  {
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<unsigned short const (&)[8],unsigned short const (&)[22]>();
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      McTemplateU0zzz_EventWriteTransfer(v12, (unsigned int)&RestoreAssociatedCloudFile, v10, v13, v11);
    }
    if ( v25[0] == 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoChangingWallpaper>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_NoChangingWallpaper>::GetImpl'::`2'::impl)
        && BackgroundBackupRestoreHandler::isChangingWallpaperRestricted(v15) )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v16,
            &InformationMessage,
            L"Background Restore",
            L"Policy Prevents Wallpaper Change");
        CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[23],unsigned short const (&)[33],unsigned short const (&)[8]>();
      }
      else
      {
        v17 = SHRegSetDWORD(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
                L"BackgroundType",
                0);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
            (const char *)(unsigned int)v17,
            v19);
        BackgroundBackupRestoreHandler::SetImage(retaddr, v25);
      }
    }
    else
    {
      v14 = SHRegSetBOOL(v9, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"WallpaperSetFromTheme", 0);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2F6,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
          (const char *)(unsigned int)v14,
          v19);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[33],unsigned short const (&)[8]>();
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(
                            a1 + 16,
                            v20)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(v20);
    if ( !SystemParametersInfoW(0x14u, 0, 0, 0) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x304,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
        v18);
  }
  else
  {
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<unsigned short const (&)[8],unsigned short const (&)[35]>();
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(
                            a1 + 16,
                            v20)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(v20);
  }
  CloudRestoreLauncherTelemetry::BackgroundActivity::Stop(v6, L"Restore Completed");
  wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper>::~cloud_store_data<Windows::Data::Background::DesktopWallpaper>((Windows::Data::Background::DesktopWallpaper *)v25);
  v22 = 0;
  _lambda_7684c1eab8583df9349b09dfd1db4e36_::operator()(&v21);
  tip2::test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(v24);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x1800ae990  mov     [rsp-8+arg_8], rbx
0x1800ae995  mov     [rsp-8+arg_10], rsi
0x1800ae99a  push    rbp
0x1800ae99b  push    rdi
0x1800ae99c  push    r14
0x1800ae99e  lea     rbp, [rsp-40h]
0x1800ae9a3  sub     rsp, 140h
0x1800ae9aa  mov     rax, cs:__security_cookie
0x1800ae9b1  xor     rax, rsp
0x1800ae9b4  mov     [rbp+50h+var_20], rax
0x1800ae9b8  mov     rsi, r9
0x1800ae9bb  mov     rbx, rcx
0x1800ae9be  mov     [rsp+150h+var_108], r9
0x1800ae9c3  lea     r14, [rcx+168h]
0x1800ae9ca  lea     rdx, aRestoreStarted_0; "Restore Started"
0x1800ae9d1  mov     rcx, r14; this
0x1800ae9d4  call    ?StartActivity@BackgroundActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::StartActivity(ushort const *)
0x1800ae9d9  lea     rdi, [rbx+10h]
0x1800ae9dd  lea     rdx, [rsp+150h+var_100]
0x1800ae9e2  mov     rcx, rdi
0x1800ae9e5  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::start_and_watch_errors(void)
0x1800ae9ea  nop
0x1800ae9eb  mov     [rsp+150h+var_118], rbx
0x1800ae9f0  mov     [rsp+150h+var_110], 1
0x1800ae9f5  xor     r9d, r9d; int
0x1800ae9f8  lea     r8, aWallpaperresto; "WallpaperRestored"
0x1800ae9ff  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aea06  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800aea0b  mov     rcx, [rbp+58h]; this
0x1800aea0f  test    eax, eax
0x1800aea11  jns     short loc_1800AEA27
0x1800aea13  mov     r9d, eax; char *
0x1800aea16  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aea1d  mov     edx, 2D2h; void *
0x1800aea22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aea27  mov     r8d, 9
0x1800aea2d  lea     rdx, [rbp+50h+var_C0]
0x1800aea31  mov     rcx, rsi
0x1800aea34  call    ??$load@UDesktopWallpaper@Background@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Background::DesktopWallpaper>(wil::cloud_store_load_options,char const *)
0x1800aea39  nop
0x1800aea3a  lea     rdx, [rsp+150h+var_120]
0x1800aea3f  mov     rcx, rdi
0x1800aea42  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(void)
0x1800aea47  mov     rcx, [rax]
0x1800aea4a  mov     byte ptr [rcx+111h], 1
0x1800aea51  lea     rcx, [rsp+150h+var_120]
0x1800aea56  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800aea5b  lea     rcx, [rbp+50h+var_C0]
0x1800aea5f  call    ??$ValidateAndLogRestoreCloudDataLoad@UDesktopWallpaper@Background@Data@Windows@@@@YA_NAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; ValidateAndLogRestoreCloudDataLoad<Windows::Data::Background::DesktopWallpaper>(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)
0x1800aea64  test    al, al
0x1800aea66  jz      loc_1800AEBC7
0x1800aea6c  call    ??$Background_BondSchemaActivity@AEAY07$$CBGAEAY0BG@$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY07$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<ushort const (&)[8],ushort const (&)[22]>(ushort const (&)[8],ushort const (&)[22])
0x1800aea71  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800aea78  jz      short loc_1800AEAAF
0x1800aea7a  lea     rcx, [rbp+50h+var_60]
0x1800aea7e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aea83  mov     rdx, rax
0x1800aea86  lea     rcx, [rbp+50h+var_90]
0x1800aea8a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aea8f  mov     r9, rax
0x1800aea92  lea     rcx, [rbp+50h+var_B0]
0x1800aea96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aea9b  mov     r8, rax
0x1800aea9e  mov     qword ptr [rsp+150h+var_130], rdx; int
0x1800aeaa3  lea     rdx, RestoreAssociatedCloudFile
0x1800aeaaa  call    McTemplateU0zzz_EventWriteTransfer
0x1800aeaaf  cmp     [rbp+50h+var_C0], 1
0x1800aeab3  jz      short loc_1800AEAED
0x1800aeab5  xor     r9d, r9d; int
0x1800aeab8  lea     r8, aWallpapersetfr; "WallpaperSetFromTheme"
0x1800aeabf  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aeac6  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800aeacb  mov     rcx, [rbp+58h]; this
0x1800aeacf  test    eax, eax
0x1800aead1  jns     loc_1800AEB62
0x1800aead7  mov     r9d, eax; char *
0x1800aeada  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aeae1  mov     edx, 2F6h; void *
0x1800aeae6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aeaeb  jmp     short loc_1800AEB62
0x1800aeaed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NoChangingWallpaper@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NoChangingWallpaper@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoChangingWallpaper> `wil::Feature<__WilFeatureTraits_Feature_NoChangingWallpaper>::GetImpl(void)'::`2'::impl
0x1800aeaf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NoChangingWallpaper@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoChangingWallpaper>::__private_IsEnabled(void)
0x1800aeaf9  test    al, al
0x1800aeafb  jz      short loc_1800AEB30
0x1800aeafd  call    ?isChangingWallpaperRestricted@BackgroundBackupRestoreHandler@@AEAA_NXZ; BackgroundBackupRestoreHandler::isChangingWallpaperRestricted(void)
0x1800aeb02  test    al, al
0x1800aeb04  jz      short loc_1800AEB30
0x1800aeb06  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800aeb0d  jz      short loc_1800AEB29
0x1800aeb0f  lea     r9, aPolicyPrevents; "Policy Prevents Wallpaper Change"
0x1800aeb16  lea     r8, aBackgroundRest_0; "Background Restore"
0x1800aeb1d  lea     rdx, InformationMessage
0x1800aeb24  call    McTemplateU0zz_EventWriteTransfer
0x1800aeb29  call    ??$Background_ApiActivity@AEAY0BH@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BH@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[23],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[23],ushort const (&)[33],ushort const (&)[8])
0x1800aeb2e  jmp     short loc_1800AEB62
0x1800aeb30  xor     r9d, r9d; unsigned int
0x1800aeb33  lea     r8, aBackgroundtype; "BackgroundType"
0x1800aeb3a  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aeb41  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800aeb48  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800aeb4d  mov     rcx, [rbp+58h]; this
0x1800aeb51  test    eax, eax
0x1800aeb53  js      loc_1800AEC4E
0x1800aeb59  lea     rdx, [rbp+50h+var_C0]
0x1800aeb5d  call    ?SetImage@BackgroundBackupRestoreHandler@@AEAAXAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; BackgroundBackupRestoreHandler::SetImage(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)
0x1800aeb62  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800aeb69  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800aeb6e  test    al, al
0x1800aeb70  jz      short loc_1800AEB77
0x1800aeb72  call    ??$Background_ApiActivity@AEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[12],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[33],ushort const (&)[8])
0x1800aeb77  lea     rdx, [rsp+150h+var_120]
0x1800aeb7c  mov     rcx, rdi
0x1800aeb7f  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(void)
0x1800aeb84  mov     rcx, [rax]
0x1800aeb87  mov     byte ptr [rcx+110h], 1
0x1800aeb8e  lea     rcx, [rsp+150h+var_120]
0x1800aeb93  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800aeb98  mov     rbx, [rbp+58h]
0x1800aeb9c  xor     r9d, r9d; fWinIni
0x1800aeb9f  xor     r8d, r8d; pvParam
0x1800aeba2  xor     edx, edx; uiParam
0x1800aeba4  lea     ecx, [rdx+14h]; uiAction
0x1800aeba7  call    cs:__imp_SystemParametersInfoW
0x1800aebad  test    eax, eax
0x1800aebaf  jnz     short loc_1800AEBED
0x1800aebb1  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aebb8  mov     edx, 304h; void *
0x1800aebbd  mov     rcx, rbx; this
0x1800aebc0  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800aebc5  jmp     short loc_1800AEBED
0x1800aebc7  call    ??$Background_BondSchemaActivity@AEAY07$$CBGAEAY0CD@$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY07$$CBGAEAY0CD@$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<ushort const (&)[8],ushort const (&)[35]>(ushort const (&)[8],ushort const (&)[35])
0x1800aebcc  lea     rdx, [rsp+150h+var_120]
0x1800aebd1  mov     rcx, rdi
0x1800aebd4  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(void)
0x1800aebd9  mov     rdx, [rax]
0x1800aebdc  mov     byte ptr [rdx+110h], 1
0x1800aebe3  lea     rcx, [rsp+150h+var_120]
0x1800aebe8  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800aebed  lea     rdx, aRestoreComplet; "Restore Completed"
0x1800aebf4  mov     rcx, r14; this
0x1800aebf7  call    ?Stop@BackgroundActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Stop(ushort const *)
0x1800aebfc  nop
0x1800aebfd  lea     rcx, [rbp+50h+var_C0]; this
0x1800aec01  call    ??1?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper>::~cloud_store_data<Windows::Data::Background::DesktopWallpaper>(void)
0x1800aec06  nop
0x1800aec07  mov     [rsp+150h+var_110], 0
0x1800aec0c  lea     rcx, [rsp+150h+var_118]
0x1800aec11  call    ??R_lambda_7684c1eab8583df9349b09dfd1db4e36_@@QEBA@XZ; _lambda_7684c1eab8583df9349b09dfd1db4e36_::operator()(void)
0x1800aec16  nop
0x1800aec17  lea     rcx, [rsp+150h+var_100]
0x1800aec1c  call    ??1?$test_watcher@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800aec21  nop
0x1800aec22  mov     rcx, rsi; this
0x1800aec25  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800aec2a  mov     rcx, [rbp+50h+var_20]
0x1800aec2e  xor     rcx, rsp; StackCookie
0x1800aec31  call    __security_check_cookie
0x1800aec36  lea     r11, [rsp+150h+var_10]
0x1800aec3e  mov     rbx, [r11+28h]
0x1800aec42  mov     rsi, [r11+30h]
0x1800aec46  mov     rsp, r11
0x1800aec49  pop     r14
0x1800aec4b  pop     rdi
0x1800aec4c  pop     rbp
0x1800aec4d  retn
0x1800aec4e  mov     r9d, eax; char *
0x1800aec51  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aec58  mov     edx, 1C6h; void *
0x1800aec5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
