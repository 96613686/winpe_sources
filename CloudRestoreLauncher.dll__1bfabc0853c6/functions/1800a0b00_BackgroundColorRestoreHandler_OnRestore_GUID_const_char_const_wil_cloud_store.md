# BackgroundColorRestoreHandler::OnRestore(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800a0b00`
- end: `0x1800a0d99`
- name: `?OnRestore@BackgroundColorRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `665`
- prototype: `void __high(const struct _GUID *, const char *, struct wil::cloud_store)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18001cfa4`
- `0x180036a3c`
- `0x18008cedc`
- `0x180096af4`
- `0x18009cbec`
- `0x18009e898`
- `0x18009e940`
- `0x18009e9cc`
- `0x18009ea58`
- `0x18009eae4`
- `0x18009fadc`
- `0x18009fdc8`
- `0x1800a0524`
- `0x1800a0604`
- `0x1800a0628`
- `0x1800a07c8`
- `0x1800a07f0`
- `0x1800a0b00`
- `0x1800a0e20`
- `0x1800a0f70`
- `0x1800a0fac`
- `0x1800a10c0`
- `0x1800a1250`
- `0x1800a1308`
- `0x1800a1d38`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800a0c4a`
- `USER32!SystemParametersInfoW` at `0x1800a0c4a`

## string_xrefs

- `0x1800a0d0e`: `Restore Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall BackgroundColorRestoreHandler::OnRestore(__int64 a1, __int64 a2, __int64 a3, wil::cloud_store *a4)
{
  char IsEnabled; // al
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rdx
  const wchar_t *v9; // rcx
  const wchar_t *v10; // rdx
  const wchar_t *v11; // rcx
  __int64 v12; // r8
  const char *v13; // r9
  int v14; // eax
  HKEY v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  const wchar_t *v18; // rcx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  char v21; // [rsp+30h] [rbp-D0h]
  wil::cloud_store *v22; // [rsp+38h] [rbp-C8h]
  _BYTE v23[64]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v24[40]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v22 = a4;
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackgroundRestoreHandler>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BackgroundRestoreHandler>::GetImpl'::`2'::impl,
    a2,
    a3);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl);
  v7 = L"Restore Started - Background Color";
  if ( !IsEnabled )
    v7 = L"Restore Started";
  CloudRestoreLauncherTelemetry::BackgroundActivity::StartActivity(
    (CloudRestoreLauncherTelemetry::BackgroundActivity *)(a1 + 360),
    v7);
  tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::start_and_watch_errors(
    a1 + 16,
    v23);
  v20 = a1;
  v21 = 1;
  wil::cloud_store::load<Windows::Data::Background::DesktopWallpaper>(a4, v24, 9);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(
                          a1 + 16,
                          &v19)
           + 273LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(&v19);
  if ( (unsigned __int8)ValidateAndLogRestoreCloudDataLoad<Windows::Data::Background::DesktopWallpaper>(v24) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<unsigned short const (&)[25],unsigned short const (&)[22]>(
        v9,
        v8);
    else
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<unsigned short const (&)[8],unsigned short const (&)[43]>(
        v9,
        v8);
    if ( v24[0] )
    {
      if ( v24[0] == 1 )
        BackgroundColorRestoreHandler::SetPosition(1, v24);
    }
    else
    {
      v14 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
              L"BackgroundType",
              1u);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
          (const char *)(unsigned int)v14,
          v19);
      BackgroundColorRestoreHandler::SetSolidColor(retaddr, v24);
      v16 = SHRegSetString(v15, L"Control Panel\\Desktop", L"Wallpaper", &word_1801382A0);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
          (const char *)(unsigned int)v16,
          v19);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[29],unsigned short const (&)[33],unsigned short const (&)[8]>(
        v11,
        v10,
        v12);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(
                            a1 + 16,
                            &v19)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(&v19);
    if ( !SystemParametersInfoW(0x14u, 0, 0, 0) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xA2,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
        v13);
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<unsigned short const (&)[25],unsigned short const (&)[35]>(
        v18,
        v17);
    else
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<unsigned short const (&)[8],unsigned short const (&)[56]>(
        v18,
        v17);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(
                            a1 + 16,
                            &v19)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(&v19);
  }
  CloudRestoreLauncherTelemetry::BackgroundActivity::Stop(
    (CloudRestoreLauncherTelemetry::BackgroundActivity *)(a1 + 360),
    L"Restore Completed");
  wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper>::~cloud_store_data<Windows::Data::Background::DesktopWallpaper>((Windows::Data::Background::DesktopWallpaper *)v24);
  v21 = 0;
  _lambda_7684c1eab8583df9349b09dfd1db4e36_::operator()(&v20);
  tip2::test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(v23);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x1800a0b00  mov     [rsp-8+arg_8], rbx
0x1800a0b05  mov     [rsp-8+arg_10], rsi
0x1800a0b0a  push    rbp
0x1800a0b0b  push    rdi
0x1800a0b0c  push    r14
0x1800a0b0e  lea     rbp, [rsp-30h]
0x1800a0b13  sub     rsp, 130h
0x1800a0b1a  mov     rax, cs:__security_cookie
0x1800a0b21  xor     rax, rsp
0x1800a0b24  mov     [rbp+40h+var_20], rax
0x1800a0b28  mov     rsi, r9
0x1800a0b2b  mov     rbx, rcx
0x1800a0b2e  mov     [rsp+140h+var_108], r9
0x1800a0b33  mov     r8b, 3
0x1800a0b36  mov     dl, 1
0x1800a0b38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackgroundRestoreHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackgroundRestoreHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackgroundRestoreHandler> `wil::Feature<__WilFeatureTraits_Feature_BackgroundRestoreHandler>::GetImpl(void)'::`2'::impl
0x1800a0b3f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BackgroundRestoreHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackgroundRestoreHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800a0b44  lea     r14, [rbx+168h]
0x1800a0b4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800a0b52  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800a0b57  lea     rcx, aRestoreStarted_0; "Restore Started"
0x1800a0b5e  lea     rdx, aRestoreStarted; "Restore Started - Background Color"
0x1800a0b65  test    al, al
0x1800a0b67  cmovz   rdx, rcx; unsigned __int16 *
0x1800a0b6b  mov     rcx, r14; this
0x1800a0b6e  call    ?StartActivity@BackgroundActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::StartActivity(ushort const *)
0x1800a0b73  lea     rdi, [rbx+10h]
0x1800a0b77  lea     rdx, [rsp+140h+var_100]
0x1800a0b7c  mov     rcx, rdi
0x1800a0b7f  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::start_and_watch_errors(void)
0x1800a0b84  nop
0x1800a0b85  mov     [rsp+140h+var_118], rbx
0x1800a0b8a  mov     [rsp+140h+var_110], 1
0x1800a0b8f  mov     r8d, 9
0x1800a0b95  lea     rdx, [rbp+40h+var_C0]
0x1800a0b99  mov     rcx, rsi
0x1800a0b9c  call    ??$load@UDesktopWallpaper@Background@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Background::DesktopWallpaper>(wil::cloud_store_load_options,char const *)
0x1800a0ba1  nop
0x1800a0ba2  lea     rdx, [rsp+140h+var_120]
0x1800a0ba7  mov     rcx, rdi
0x1800a0baa  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(void)
0x1800a0baf  mov     rcx, [rax]
0x1800a0bb2  mov     byte ptr [rcx+111h], 1
0x1800a0bb9  lea     rcx, [rsp+140h+var_120]
0x1800a0bbe  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800a0bc3  lea     rcx, [rbp+40h+var_C0]
0x1800a0bc7  call    ??$ValidateAndLogRestoreCloudDataLoad@UDesktopWallpaper@Background@Data@Windows@@@@YA_NAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; ValidateAndLogRestoreCloudDataLoad<Windows::Data::Background::DesktopWallpaper>(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)
0x1800a0bcc  test    al, al
0x1800a0bce  jz      loc_1800A0CD1
0x1800a0bd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800a0bdb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800a0be0  test    al, al
0x1800a0be2  jz      short loc_1800A0BEB
0x1800a0be4  call    ??$Background_BondSchemaActivity@AEAY0BJ@$$CBGAEAY0BG@$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BJ@$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<ushort const (&)[25],ushort const (&)[22]>(ushort const (&)[25],ushort const (&)[22])
0x1800a0be9  jmp     short loc_1800A0BF0
0x1800a0beb  call    ??$Background_BondSchemaActivity@AEAY07$$CBGAEAY0CL@$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY07$$CBGAEAY0CL@$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<ushort const (&)[8],ushort const (&)[43]>(ushort const (&)[8],ushort const (&)[43])
0x1800a0bf0  mov     ecx, [rbp+40h+var_C0]
0x1800a0bf3  test    ecx, ecx
0x1800a0bf5  jz      short loc_1800A0C71
0x1800a0bf7  cmp     ecx, 1
0x1800a0bfa  jnz     short loc_1800A0C05
0x1800a0bfc  lea     rdx, [rbp+40h+var_C0]
0x1800a0c00  call    ?SetPosition@BackgroundColorRestoreHandler@@AEAAXAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; BackgroundColorRestoreHandler::SetPosition(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)
0x1800a0c05  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800a0c0c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800a0c11  test    al, al
0x1800a0c13  jz      short loc_1800A0C1A
0x1800a0c15  call    ??$Background_ApiActivity@AEAY0BN@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BN@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[29],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[29],ushort const (&)[33],ushort const (&)[8])
0x1800a0c1a  lea     rdx, [rsp+140h+var_120]
0x1800a0c1f  mov     rcx, rdi
0x1800a0c22  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(void)
0x1800a0c27  mov     rcx, [rax]
0x1800a0c2a  mov     byte ptr [rcx+110h], 1
0x1800a0c31  lea     rcx, [rsp+140h+var_120]
0x1800a0c36  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800a0c3b  mov     rbx, [rbp+48h]
0x1800a0c3f  xor     r9d, r9d; fWinIni
0x1800a0c42  xor     r8d, r8d; pvParam
0x1800a0c45  xor     edx, edx; uiParam
0x1800a0c47  lea     ecx, [rdx+14h]; uiAction
0x1800a0c4a  call    cs:__imp_SystemParametersInfoW
0x1800a0c50  test    eax, eax
0x1800a0c52  jnz     loc_1800A0D0E
0x1800a0c58  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a0c5f  mov     edx, 0A2h; void *
0x1800a0c64  mov     rcx, rbx; this
0x1800a0c67  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800a0c6c  jmp     loc_1800A0D0E
0x1800a0c71  mov     r9d, 1; unsigned int
0x1800a0c77  lea     r8, aBackgroundtype; "BackgroundType"
0x1800a0c7e  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a0c85  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800a0c8c  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a0c91  mov     rcx, [rbp+48h]; this
0x1800a0c95  test    eax, eax
0x1800a0c97  js      loc_1800A0D6F
0x1800a0c9d  lea     rdx, [rbp+40h+var_C0]
0x1800a0ca1  call    ?SetSolidColor@BackgroundColorRestoreHandler@@AEAAXAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; BackgroundColorRestoreHandler::SetSolidColor(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)
0x1800a0ca6  lea     r9, word_1801382A0; unsigned __int16 *
0x1800a0cad  lea     r8, aWallpaper; "Wallpaper"
0x1800a0cb4  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x1800a0cbb  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800a0cc0  mov     rcx, [rbp+48h]; this
0x1800a0cc4  test    eax, eax
0x1800a0cc6  js      loc_1800A0D84
0x1800a0ccc  jmp     loc_1800A0C05
0x1800a0cd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800a0cd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800a0cdd  test    al, al
0x1800a0cdf  jz      short loc_1800A0CE8
0x1800a0ce1  call    ??$Background_BondSchemaActivity@AEAY0BJ@$$CBGAEAY0CD@$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BJ@$$CBGAEAY0CD@$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<ushort const (&)[25],ushort const (&)[35]>(ushort const (&)[25],ushort const (&)[35])
0x1800a0ce6  jmp     short loc_1800A0CED
0x1800a0ce8  call    ??$Background_BondSchemaActivity@AEAY07$$CBGAEAY0DI@$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY07$$CBGAEAY0DI@$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_BondSchemaActivity<ushort const (&)[8],ushort const (&)[56]>(ushort const (&)[8],ushort const (&)[56])
0x1800a0ced  lea     rdx, [rsp+140h+var_120]
0x1800a0cf2  mov     rcx, rdi
0x1800a0cf5  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::operator->(void)
0x1800a0cfa  mov     rdx, [rax]
0x1800a0cfd  mov     byte ptr [rdx+110h], 1
0x1800a0d04  lea     rcx, [rsp+140h+var_120]
0x1800a0d09  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800a0d0e  lea     rdx, aRestoreComplet; "Restore Completed"
0x1800a0d15  mov     rcx, r14; this
0x1800a0d18  call    ?Stop@BackgroundActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Stop(ushort const *)
0x1800a0d1d  nop
0x1800a0d1e  lea     rcx, [rbp+40h+var_C0]; this
0x1800a0d22  call    ??1?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper>::~cloud_store_data<Windows::Data::Background::DesktopWallpaper>(void)
0x1800a0d27  nop
0x1800a0d28  mov     [rsp+140h+var_110], 0
0x1800a0d2d  lea     rcx, [rsp+140h+var_118]
0x1800a0d32  call    ??R_lambda_7684c1eab8583df9349b09dfd1db4e36_@@QEBA@XZ; _lambda_7684c1eab8583df9349b09dfd1db4e36_::operator()(void)
0x1800a0d37  nop
0x1800a0d38  lea     rcx, [rsp+140h+var_100]
0x1800a0d3d  call    ??1?$test_watcher@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::~test_watcher<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>(void)
0x1800a0d42  nop
0x1800a0d43  mov     rcx, rsi; this
0x1800a0d46  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800a0d4b  mov     rcx, [rbp+40h+var_20]
0x1800a0d4f  xor     rcx, rsp; StackCookie
0x1800a0d52  call    __security_check_cookie
0x1800a0d57  lea     r11, [rsp+140h+var_10]
0x1800a0d5f  mov     rbx, [r11+28h]
0x1800a0d63  mov     rsi, [r11+30h]
0x1800a0d67  mov     rsp, r11
0x1800a0d6a  pop     r14
0x1800a0d6c  pop     rdi
0x1800a0d6d  pop     rbp
0x1800a0d6e  retn
0x1800a0d6f  mov     r9d, eax; char *
0x1800a0d72  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a0d79  mov     edx, 2Dh ; '-'; void *
0x1800a0d7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a0d84  mov     r9d, eax; char *
0x1800a0d87  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a0d8e  mov     edx, 91h; void *
0x1800a0d93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
