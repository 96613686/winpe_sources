# InkPenBackupRestoreHandler::OnRestore(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800ec890`
- end: `0x1800ecd9e`
- name: `?OnRestore@InkPenBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `1294`
- prototype: `void __high(const struct _GUID *, const char *, struct wil::cloud_store)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18001cf84`
- `0x18001d0a8`
- `0x18001faa8`
- `0x18002236c`
- `0x1800284d0`
- `0x180036a3c`
- `0x180096af4`
- `0x1800977e8`
- `0x1800a0f70`
- `0x1800e8b80`
- `0x1800e8c28`
- `0x1800e8d70`
- `0x1800e8e18`
- `0x1800e8ec0`
- `0x1800e8f68`
- `0x1800e91b0`
- `0x1800e923c`
- `0x1800ea5c8`
- `0x1800eab40`
- `0x1800eb794`
- `0x1800eb7d8`
- `0x1800eb8b8`
- `0x1800eb904`
- `0x1800ebc7c`
- `0x1800ec890`
- `0x1800ecf64`
- `0x1800ed1d0`
- `0x1800ed288`
- `0x1800edda4`
- `0x1800edffc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800eccb2`
- `KERNEL32!GetLastError` at `0x1800eccb2`
- `USER32!SystemParametersInfoW` at `0x1800ecc59`
- `USER32!SystemParametersInfoW` at `0x1800ecc59`

## string_xrefs

- `0x1800ecd17`: `Local Settings Restore Completed`
- `0x1800ecd3a`: `Restore Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall InkPenBackupRestoreHandler::OnRestore(__int64 a1, __int64 a2, __int64 a3, wil::cloud_store *a4)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r10
  __int64 v11; // r11
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rbx
  signed int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbx
  signed int LastError; // eax
  wil::details::in1diag3 *v27; // rcx
  __int64 v28; // rcx
  int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v31; // [rsp+88h] [rbp-78h] BYREF
  char v32; // [rsp+90h] [rbp-70h]
  wil::cloud_store *v33; // [rsp+98h] [rbp-68h]
  _BYTE v34[56]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+D8h] [rbp-28h]
  _BYTE v36[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+100h] [rbp+0h] BYREF
  __int64 v38; // [rsp+108h] [rbp+8h] BYREF
  __int64 v39; // [rsp+110h] [rbp+10h] BYREF
  __int64 v40; // [rsp+118h] [rbp+18h] BYREF
  __int64 v41; // [rsp+120h] [rbp+20h] BYREF
  __int64 v42; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int8 v43; // [rsp+130h] [rbp+30h]
  unsigned __int8 v44; // [rsp+131h] [rbp+31h]
  _BYTE v45[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v46[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v47[32]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v48[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v49[32]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v50[18]; // [rsp+1D8h] [rbp+D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v33 = a4;
  v30 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::start_and_watch_errors(
    &v30,
    v34);
  wil::com_ptr_t<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>,wil::err_returncode_policy>(&v30);
  v31 = v34;
  v32 = 1;
  CloudRestoreLauncherTelemetry::InkPenActivity::StartActivity(
    (CloudRestoreLauncherTelemetry::InkPenActivity *)(a1 + 344),
    L"Restore Started");
  wil::cloud_store::load<Windows::Data::Input::Devices::PenPerDevice>(a4, &v37, 9);
  if ( (unsigned __int8)ValidateAndLogRestoreCloudDataLoad<Windows::Data::Input::Devices::PenPerDevice>(&v37) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      McTemplateU0xxxxxxxxzzzzzz_EventWriteTransfer(
        v44,
        (unsigned int)RestoreAssociatedInkPenSettingCloudFile,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v7,
        v8,
        v9,
        v10,
        v11,
        v6);
    }
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<unsigned short const (&)[8],unsigned short const (&)[22]>();
    v12 = v35;
    v30 = v35;
    if ( v35 )
      _InterlockedIncrement((volatile signed __int32 *)(v35 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v12 + 8);
    *(_BYTE *)(v12 + 272) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(&v30);
    std::wstring::wstring(
      v36,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\SingleClickBelowLock");
    InkPenBackupRestoreHandler::SetClickActions(
      v13,
      (unsigned int *)&v37,
      (unsigned int *)&v38,
      (__int64)v45,
      (__int64)v48,
      (__int64)v36);
    std::wstring::_Tidy_deallocate(v36);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v14, InkPenSettingStatus, L"Single-Click", L"Done");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[33],unsigned short const (&)[8]>(
      v14,
      L"SetClickActions for single-click");
    std::wstring::wstring(
      v36,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\DoubleClickBelowLock");
    InkPenBackupRestoreHandler::SetClickActions(
      v15,
      (unsigned int *)&v39,
      (unsigned int *)&v40,
      (__int64)v46,
      (__int64)v49,
      (__int64)v36);
    std::wstring::_Tidy_deallocate(v36);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v16, InkPenSettingStatus, L"Double-Click", L"Done");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[33],unsigned short const (&)[8]>(
      v16,
      L"SetClickActions for double-click");
    std::wstring::wstring(
      v36,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\LongPressBelowLock");
    InkPenBackupRestoreHandler::SetClickActions(
      v17,
      (unsigned int *)&v41,
      (unsigned int *)&v42,
      (__int64)v47,
      (__int64)v50,
      (__int64)v36);
    std::wstring::_Tidy_deallocate(v36);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v18, InkPenSettingStatus, L"Long-Press", L"Done");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[31],unsigned short const (&)[8]>();
    v19 = v35;
    v30 = v35;
    if ( v35 )
      _InterlockedIncrement((volatile signed __int32 *)(v35 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v19 + 8);
    *(_BYTE *)(v19 + 273) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(&v30);
    v20 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\PenWorkspace",
            L"PenWorkspaceAppLaunchOnPenDetachEnabled",
            v43);
    if ( v20 )
    {
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\inkpenbackuprestorehandler.cpp",
        (const char *)(unsigned int)v20,
        v29);
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v23,
          InkPenSettingStatus,
          L"PenWorkspaceAppLaunchOnPenDetachEnabled",
          L"Failed");
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[58],unsigned short const (&)[7]>(v23);
    }
    else
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(v21, InkPenSettingStatus, L"PenWorkspaceAppLaunchOnPenDetachEnabled", L"Done");
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[58],unsigned short const (&)[8]>();
      v22 = v35;
      v30 = v35;
      if ( v35 )
        _InterlockedIncrement((volatile signed __int32 *)(v35 + 280));
      tip2::details::shared_data<0,0,0>::begin_update(v22 + 8);
      *(_BYTE *)(v22 + 274) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(&v30);
    }
    if ( SystemParametersInfoW(0x1053u, 0, (PVOID)(v44 == 0), 3u) )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(v24, InkPenSettingStatus, L"PenEnablePenButtonOverride", L"Done");
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[52],unsigned short const (&)[8]>();
      v25 = v35;
      v30 = v35;
      if ( v35 )
        _InterlockedIncrement((volatile signed __int32 *)(v35 + 280));
      tip2::details::shared_data<0,0,0>::begin_update(v25 + 8);
      *(_BYTE *)(v25 + 275) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(&v30);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v27 = retaddr;
      if ( LastError < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\inkpenbackuprestorehandler.cpp",
          (const char *)(unsigned int)LastError,
          v29);
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(v27, InkPenSettingStatus, L"PenEnablePenButtonOverride", L"Failed");
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[52],unsigned short const (&)[7]>(v27);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[33],unsigned short const (&)[8]>(
        v28,
        L"Local Settings Restore Completed");
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
  {
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<unsigned short const (&)[8],unsigned short const (&)[35]>();
  }
  CloudRestoreLauncherTelemetry::InkPenActivity::Stop(
    (CloudRestoreLauncherTelemetry::InkPenActivity *)(a1 + 344),
    L"Restore Completed");
  wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>::~cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>((Windows::Data::Input::Devices::PenPerDevice *)&v37);
  v32 = 0;
  lambda_7f0b270afd843a4cbdbbb8ef45377fac_::operator()(&v31);
  tip2::test_watcher<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_watcher<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(v34);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x1800ec890  mov     [rsp-8+arg_8], rbx
0x1800ec895  push    rbp
0x1800ec896  push    rsi
0x1800ec897  push    rdi
0x1800ec898  push    r12
0x1800ec89a  push    r13
0x1800ec89c  lea     rbp, [rsp-130h]
0x1800ec8a4  sub     rsp, 230h
0x1800ec8ab  mov     rax, cs:__security_cookie
0x1800ec8b2  xor     rax, rsp
0x1800ec8b5  mov     [rbp+150h+var_30], rax
0x1800ec8bc  mov     rdi, r9
0x1800ec8bf  mov     rsi, rcx
0x1800ec8c2  mov     [rbp+150h+var_1B8], r9
0x1800ec8c6  mov     [rbp+150h+var_1D0], 0
0x1800ec8ce  lea     rdx, [rbp+150h+var_1B0]
0x1800ec8d2  lea     rcx, [rbp+150h+var_1D0]
0x1800ec8d6  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::start_and_watch_errors(void)
0x1800ec8db  lea     rcx, [rbp+150h+var_1D0]
0x1800ec8df  call    ??1?$com_ptr_t@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>,wil::err_returncode_policy>(void)
0x1800ec8e4  nop
0x1800ec8e5  lea     rax, [rbp+150h+var_1B0]
0x1800ec8e9  mov     [rbp+150h+var_1C8], rax
0x1800ec8ed  mov     [rbp+150h+var_1C0], 1
0x1800ec8f1  lea     rdx, aRestoreStarted_0; "Restore Started"
0x1800ec8f8  lea     rcx, [rsi+158h]; this
0x1800ec8ff  call    ?StartActivity@InkPenActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::StartActivity(ushort const *)
0x1800ec904  mov     r8d, 9
0x1800ec90a  lea     rdx, [rbp+150h+var_150]
0x1800ec90e  mov     rcx, rdi
0x1800ec911  call    ??$load@UPenPerDevice@Devices@Input@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UPenPerDevice@Devices@Input@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Input::Devices::PenPerDevice>(wil::cloud_store_load_options,char const *)
0x1800ec916  nop
0x1800ec917  lea     rcx, [rbp+150h+var_150]
0x1800ec91b  call    ??$ValidateAndLogRestoreCloudDataLoad@UPenPerDevice@Devices@Input@Data@Windows@@@@YA_NAEBV?$cloud_store_data@UPenPerDevice@Devices@Input@Data@Windows@@@wil@@@Z; ValidateAndLogRestoreCloudDataLoad<Windows::Data::Input::Devices::PenPerDevice>(wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice> const &)
0x1800ec920  test    al, al
0x1800ec922  jz      loc_1800ECD25
0x1800ec928  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec92f  jz      loc_1800EC9EB
0x1800ec935  lea     rcx, [rbp+150h+var_78]
0x1800ec93c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec941  mov     rbx, rax
0x1800ec944  lea     rcx, [rbp+150h+var_98]
0x1800ec94b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec950  mov     r11, rax
0x1800ec953  lea     rcx, [rbp+150h+var_B8]
0x1800ec95a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec95f  mov     r10, rax
0x1800ec962  lea     rcx, [rbp+150h+var_D8]
0x1800ec966  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec96b  mov     r9, rax
0x1800ec96e  lea     rcx, [rbp+150h+var_F8]
0x1800ec972  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec977  mov     r8, rax
0x1800ec97a  lea     rcx, [rbp+150h+var_118]
0x1800ec97e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec983  movzx   ecx, [rbp+150h+var_11F]
0x1800ec987  movzx   edx, [rbp+150h+var_120]
0x1800ec98b  mov     [rsp+250h+var_1D8], rbx
0x1800ec990  mov     [rsp+250h+var_1E0], r11
0x1800ec995  mov     [rsp+250h+var_1E8], r10
0x1800ec99a  mov     [rsp+250h+var_1F0], r9
0x1800ec99f  mov     [rsp+250h+var_1F8], r8
0x1800ec9a4  mov     [rsp+250h+var_200], rax
0x1800ec9a9  mov     [rsp+250h+var_208], rcx
0x1800ec9ae  mov     [rsp+250h+var_210], rdx
0x1800ec9b3  mov     rax, [rbp+150h+var_128]
0x1800ec9b7  mov     [rsp+250h+var_218], rax
0x1800ec9bc  mov     rax, [rbp+150h+var_130]
0x1800ec9c0  mov     [rsp+250h+var_220], rax
0x1800ec9c5  mov     rax, [rbp+150h+var_138]
0x1800ec9c9  mov     [rsp+250h+var_228], rax
0x1800ec9ce  mov     rax, [rbp+150h+var_140]
0x1800ec9d2  mov     qword ptr [rsp+250h+var_230], rax
0x1800ec9d7  mov     r9, [rbp+150h+var_148]
0x1800ec9db  mov     r8, [rbp+150h+var_150]
0x1800ec9df  lea     rdx, RestoreAssociatedInkPenSettingCloudFile
0x1800ec9e6  call    McTemplateU0xxxxxxxxzzzzzz_EventWriteTransfer
0x1800ec9eb  call    ??$InkPen_BondSchemaActivity@AEAY07$$CBGAEAY0BG@$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY07$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<ushort const (&)[8],ushort const (&)[22]>(ushort const (&)[8],ushort const (&)[22])
0x1800ec9f0  mov     rbx, [rbp+150h+var_178]
0x1800ec9f4  mov     [rbp+150h+var_1D0], rbx
0x1800ec9f8  test    rbx, rbx
0x1800ec9fb  jz      short loc_1800ECA04
0x1800ec9fd  lock inc dword ptr [rbx+118h]
0x1800eca04  lea     rcx, [rbx+8]
0x1800eca08  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800eca0d  mov     byte ptr [rbx+110h], 1
0x1800eca14  lea     rcx, [rbp+150h+var_1D0]
0x1800eca18  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(void)
0x1800eca1d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800eca24  lea     rcx, [rbp+150h+var_170]
0x1800eca28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800eca2d  nop
0x1800eca2e  lea     rax, [rbp+150h+var_170]
0x1800eca32  mov     [rsp+250h+var_228], rax
0x1800eca37  lea     rax, [rbp+150h+var_B8]
0x1800eca3e  mov     qword ptr [rsp+250h+var_230], rax
0x1800eca43  lea     r9, [rbp+150h+var_118]
0x1800eca47  lea     r8, [rbp+150h+var_148]
0x1800eca4b  lea     rdx, [rbp+150h+var_150]
0x1800eca4f  call    ?SetClickActions@InkPenBackupRestoreHandler@@AEAAXAEB_K0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; InkPenBackupRestoreHandler::SetClickActions(unsigned __int64 const &,unsigned __int64 const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800eca54  nop
0x1800eca55  lea     rcx, [rbp+150h+var_170]
0x1800eca59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800eca5e  lea     r13, aDone; "Done"
0x1800eca65  lea     r12, InkPenSettingStatus
0x1800eca6c  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800eca73  jz      short loc_1800ECA87
0x1800eca75  mov     r9, r13
0x1800eca78  lea     r8, aSingleClick; "Single-Click"
0x1800eca7f  mov     rdx, r12
0x1800eca82  call    McTemplateU0zz_EventWriteTransfer
0x1800eca87  lea     rdx, aSetclickaction_1; "SetClickActions for single-click"
0x1800eca8e  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[33],ushort const (&)[8])
0x1800eca93  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800eca9a  lea     rcx, [rbp+150h+var_170]
0x1800eca9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ecaa3  nop
0x1800ecaa4  lea     rax, [rbp+150h+var_170]
0x1800ecaa8  mov     [rsp+250h+var_228], rax
0x1800ecaad  lea     rax, [rbp+150h+var_98]
0x1800ecab4  mov     qword ptr [rsp+250h+var_230], rax
0x1800ecab9  lea     r9, [rbp+150h+var_F8]
0x1800ecabd  lea     r8, [rbp+150h+var_138]
0x1800ecac1  lea     rdx, [rbp+150h+var_140]
0x1800ecac5  call    ?SetClickActions@InkPenBackupRestoreHandler@@AEAAXAEB_K0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; InkPenBackupRestoreHandler::SetClickActions(unsigned __int64 const &,unsigned __int64 const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800ecaca  nop
0x1800ecacb  lea     rcx, [rbp+150h+var_170]
0x1800ecacf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ecad4  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ecadb  jz      short loc_1800ECAEF
0x1800ecadd  mov     r9, r13
0x1800ecae0  lea     r8, aDoubleClick; "Double-Click"
0x1800ecae7  mov     rdx, r12
0x1800ecaea  call    McTemplateU0zz_EventWriteTransfer
0x1800ecaef  lea     rdx, aSetclickaction; "SetClickActions for double-click"
0x1800ecaf6  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[33],ushort const (&)[8])
0x1800ecafb  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ecb02  lea     rcx, [rbp+150h+var_170]
0x1800ecb06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ecb0b  nop
0x1800ecb0c  lea     rax, [rbp+150h+var_170]
0x1800ecb10  mov     [rsp+250h+var_228], rax
0x1800ecb15  lea     rax, [rbp+150h+var_78]
0x1800ecb1c  mov     qword ptr [rsp+250h+var_230], rax; int
0x1800ecb21  lea     r9, [rbp+150h+var_D8]
0x1800ecb25  lea     r8, [rbp+150h+var_128]
0x1800ecb29  lea     rdx, [rbp+150h+var_130]
0x1800ecb2d  call    ?SetClickActions@InkPenBackupRestoreHandler@@AEAAXAEB_K0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; InkPenBackupRestoreHandler::SetClickActions(unsigned __int64 const &,unsigned __int64 const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800ecb32  nop
0x1800ecb33  lea     rcx, [rbp+150h+var_170]
0x1800ecb37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ecb3c  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ecb43  jz      short loc_1800ECB57
0x1800ecb45  mov     r9, r13
0x1800ecb48  lea     r8, aLongPress; "Long-Press"
0x1800ecb4f  mov     rdx, r12
0x1800ecb52  call    McTemplateU0zz_EventWriteTransfer
0x1800ecb57  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0BP@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0BP@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[31],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[31],ushort const (&)[8])
0x1800ecb5c  mov     rbx, [rbp+150h+var_178]
0x1800ecb60  mov     [rbp+150h+var_1D0], rbx
0x1800ecb64  test    rbx, rbx
0x1800ecb67  jz      short loc_1800ECB70
0x1800ecb69  lock inc dword ptr [rbx+118h]
0x1800ecb70  lea     rcx, [rbx+8]
0x1800ecb74  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ecb79  mov     byte ptr [rbx+111h], 1
0x1800ecb80  lea     rcx, [rbp+150h+var_1D0]
0x1800ecb84  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(void)
0x1800ecb89  movzx   r9d, [rbp+150h+var_120]; unsigned int
0x1800ecb8e  lea     rbx, aPenworkspaceap_1; "PenWorkspaceAppLaunchOnPenDetachEnabled"
0x1800ecb95  mov     r8, rbx; unsigned __int16 *
0x1800ecb98  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ecb9f  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800ecba6  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800ecbab  test    eax, eax
0x1800ecbad  jnz     short loc_1800ECBFA
0x1800ecbaf  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ecbb6  jz      short loc_1800ECBC6
0x1800ecbb8  mov     r9, r13
0x1800ecbbb  mov     r8, rbx
0x1800ecbbe  mov     rdx, r12
0x1800ecbc1  call    McTemplateU0zz_EventWriteTransfer
0x1800ecbc6  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0DK@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0DK@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[58],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[58],ushort const (&)[8])
0x1800ecbcb  mov     rbx, [rbp+150h+var_178]
0x1800ecbcf  mov     [rbp+150h+var_1D0], rbx
0x1800ecbd3  test    rbx, rbx
0x1800ecbd6  jz      short loc_1800ECBDF
0x1800ecbd8  lock inc dword ptr [rbx+118h]
0x1800ecbdf  lea     rcx, [rbx+8]
0x1800ecbe3  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ecbe8  mov     byte ptr [rbx+112h], 1
0x1800ecbef  lea     rcx, [rbp+150h+var_1D0]
0x1800ecbf3  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(void)
0x1800ecbf8  jmp     short loc_1800ECC43
0x1800ecbfa  jle     short loc_1800ECC04
0x1800ecbfc  movzx   eax, ax
0x1800ecbff  or      eax, 80070000h
0x1800ecc04  mov     rcx, [rbp+158h]; this
0x1800ecc0b  test    eax, eax
0x1800ecc0d  jns     short loc_1800ECC23
0x1800ecc0f  mov     r9d, eax; char *
0x1800ecc12  lea     r8, aPcshellShellCl_29; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ecc19  mov     edx, 103h; void *
0x1800ecc1e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ecc23  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ecc2a  jz      short loc_1800ECC3E
0x1800ecc2c  lea     r9, aFailed; "Failed"
0x1800ecc33  mov     r8, rbx
0x1800ecc36  mov     rdx, r12
0x1800ecc39  call    McTemplateU0zz_EventWriteTransfer
0x1800ecc3e  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0DK@$$CBGAEAY06$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0DK@$$CBGAEAY06$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[58],ushort const (&)[7]>(ushort const (&)[12],ushort const (&)[58],ushort const (&)[7])
0x1800ecc43  xor     r8d, r8d
0x1800ecc46  cmp     [rbp+150h+var_11F], r8b
0x1800ecc4a  setz    r8b; pvParam
0x1800ecc4e  xor     edx, edx; uiParam
0x1800ecc50  mov     ecx, 1053h; uiAction
0x1800ecc55  lea     r9d, [rdx+3]; fWinIni
0x1800ecc59  call    cs:__imp_SystemParametersInfoW
0x1800ecc5f  test    eax, eax
0x1800ecc61  jz      short loc_1800ECCB2
0x1800ecc63  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ecc6a  jz      short loc_1800ECC7E
0x1800ecc6c  mov     r9, r13
0x1800ecc6f  lea     r8, aPenenablepenbu_2; "PenEnablePenButtonOverride"
0x1800ecc76  mov     rdx, r12
0x1800ecc79  call    McTemplateU0zz_EventWriteTransfer
0x1800ecc7e  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0DE@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0DE@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[52],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[52],ushort const (&)[8])
0x1800ecc83  mov     rbx, [rbp+150h+var_178]
0x1800ecc87  mov     [rbp+150h+var_1D0], rbx
0x1800ecc8b  test    rbx, rbx
0x1800ecc8e  jz      short loc_1800ECC97
0x1800ecc90  lock inc dword ptr [rbx+118h]
0x1800ecc97  lea     rcx, [rbx+8]
0x1800ecc9b  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ecca0  mov     byte ptr [rbx+113h], 1
0x1800ecca7  lea     rcx, [rbp+150h+var_1D0]
0x1800eccab  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(void)
0x1800eccb0  jmp     short loc_1800ECD07
0x1800eccb2  call    cs:__imp_GetLastError
0x1800eccb8  test    eax, eax
0x1800eccba  jle     short loc_1800ECCC4
0x1800eccbc  movzx   eax, ax
0x1800eccbf  or      eax, 80070000h
0x1800eccc4  mov     rcx, [rbp+158h]; this
0x1800ecccb  test    eax, eax
0x1800ecccd  jns     short loc_1800ECCE3
0x1800ecccf  mov     r9d, eax; char *
0x1800eccd2  lea     r8, aPcshellShellCl_29; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800eccd9  mov     edx, 117h; void *
0x1800eccde  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ecce3  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800eccea  jz      short loc_1800ECD02
0x1800eccec  lea     r9, aFailed; "Failed"
0x1800eccf3  lea     r8, aPenenablepenbu_2; "PenEnablePenButtonOverride"
0x1800eccfa  mov     rdx, r12
0x1800eccfd  call    McTemplateU0zz_EventWriteTransfer
0x1800ecd02  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0DE@$$CBGAEAY06$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0DE@$$CBGAEAY06$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[52],ushort const (&)[7]>(ushort const (&)[12],ushort const (&)[52],ushort const (&)[7])
0x1800ecd07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800ecd0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800ecd13  test    al, al
0x1800ecd15  jz      short loc_1800ECD3A
0x1800ecd17  lea     rdx, aLocalSettingsR; "Local Settings Restore Completed"
0x1800ecd1e  call    ??$InkPen_ApiActivity@AEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[12],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[33],ushort const (&)[8])
0x1800ecd23  jmp     short loc_1800ECD3A
0x1800ecd25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800ecd2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800ecd31  test    al, al
0x1800ecd33  jz      short loc_1800ECD3A
0x1800ecd35  call    ??$InkPen_BondSchemaActivity@AEAY07$$CBGAEAY0CD@$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY07$$CBGAEAY0CD@$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<ushort const (&)[8],ushort const (&)[35]>(ushort const (&)[8],ushort const (&)[35])
0x1800ecd3a  lea     rdx, aRestoreComplet; "Restore Completed"
0x1800ecd41  lea     rcx, [rsi+158h]; this
0x1800ecd48  call    ?Stop@InkPenActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::Stop(ushort const *)
0x1800ecd4d  nop
0x1800ecd4e  lea     rcx, [rbp+150h+var_150]; this
0x1800ecd52  call    ??1?$cloud_store_data@UPenPerDevice@Devices@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>::~cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>(void)
0x1800ecd57  nop
0x1800ecd58  mov     [rbp+150h+var_1C0], 0
0x1800ecd5c  lea     rcx, [rbp+150h+var_1C8]
0x1800ecd60  call    _lambda_7f0b270afd843a4cbdbbb8ef45377fac___operator__
0x1800ecd65  nop
0x1800ecd66  lea     rcx, [rbp+150h+var_1B0]
0x1800ecd6a  call    ??1?$test_watcher@V?$merged_data@U_tip_InkPenRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>::~test_watcher<tip2::details::merged_data<_tip_InkPenRestoreTipTest,_tip_InkPenRestoreTipTest>>(void)
0x1800ecd6f  nop
0x1800ecd70  mov     rcx, rdi; this
0x1800ecd73  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800ecd78  mov     rcx, [rbp+150h+var_30]
0x1800ecd7f  xor     rcx, rsp; StackCookie
0x1800ecd82  call    __security_check_cookie
0x1800ecd87  mov     rbx, [rsp+250h+arg_8]
0x1800ecd8f  add     rsp, 230h
0x1800ecd96  pop     r13
0x1800ecd98  pop     r12
0x1800ecd9a  pop     rdi
0x1800ecd9b  pop     rsi
0x1800ecd9c  pop     rbp
0x1800ecd9d  retn
```
