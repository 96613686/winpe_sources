# _lambda_536eb1c8974d2b35d088cee14bcb25f5_::operator()

- ea: `0x18003f4f4`
- end: `0x18003fa2b`
- name: `_lambda_536eb1c8974d2b35d088cee14bcb25f5_::operator()`
- size: `1335`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040970`

## callees

- `0x1800030e0`
- `0x180005ecc`
- `0x180006ec8`
- `0x180010ea8`
- `0x180011418`
- `0x1800115d8`
- `0x1800134b8`
- `0x180018954`
- `0x18001899c`
- `0x180019fcc`
- `0x18001a378`
- `0x18001dd44`
- `0x18003103c`
- `0x18003105c`
- `0x1800338d4`
- `0x1800390a0`
- `0x18003b394`
- `0x18003b440`
- `0x18003d518`
- `0x18003ddb0`
- `0x18003e308`
- `0x18003e8fc`
- `0x18003ec18`
- `0x18003ec5c`
- `0x18003edd0`
- `0x18003ee08`
- `0x18003f1a8`
- `0x18003f4f4`
- `0x180041004`
- `0x180041054`
- `0x1800411ec`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18003f7be`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18003f7be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x18003f911`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x18003f911`

## string_xrefs

- `0x18003f588`: `Hits SYNC_PEN_SETTINGS Task Handler`
- `0x18003f695`: `shellcommon\shell\settingshandlers\pen\lib\cdstopensettingtaskhandler.cpp`
- `0x18003f6ab`: `shellcommon\shell\settingshandlers\pen\lib\cdstopensettingtaskhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall lambda_536eb1c8974d2b35d088cee14bcb25f5_::operator()(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 HandwritingViewRegKeySDDLForCurrentContext; // rax
  const char *v5; // r9
  __int64 v6; // rbx
  __int64 v7; // r8
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rdx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rbx
  const unsigned __int16 *v15; // rax
  HKEY v16; // rcx
  int v17; // eax
  char v18; // r14
  __int64 v19; // rbx
  unsigned int v20; // eax
  void *v21; // rdx
  unsigned int v22; // r8d
  unsigned int v23; // r14d
  __int64 v24; // rbx
  const unsigned __int16 *v25; // rax
  HKEY v26; // rcx
  int v27; // eax
  char v28; // r14
  __int64 v29; // rbx
  const unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // rdx
  HKEY v32; // rcx
  int v33; // eax
  BOOL v34; // eax
  const char *v35; // r9
  wil::details::in1diag3 *v36; // rcx
  __int64 v37; // rbx
  const char *v38; // r9
  __int64 result; // rax
  int pvData; // [rsp+20h] [rbp-178h]
  int pvDataa; // [rsp+20h] [rbp-178h]
  unsigned int pvDatab; // [rsp+20h] [rbp-178h]
  int pvDatac; // [rsp+20h] [rbp-178h]
  int pvDatad; // [rsp+20h] [rbp-178h]
  unsigned int v45[2]; // [rsp+40h] [rbp-158h] BYREF
  __int64 v46; // [rsp+48h] [rbp-150h] BYREF
  __int64 v47; // [rsp+50h] [rbp-148h] BYREF
  char v48; // [rsp+58h] [rbp-140h]
  _BYTE v49[56]; // [rsp+60h] [rbp-138h] BYREF
  __int64 v50; // [rsp+98h] [rbp-100h]
  _BYTE v51[40]; // [rsp+A0h] [rbp-F8h] BYREF
  _OWORD v52[2]; // [rsp+C8h] [rbp-D0h] BYREF
  char v53; // [rsp+F0h] [rbp-A8h] BYREF
  char v54; // [rsp+F1h] [rbp-A7h]
  char v55; // [rsp+F4h] [rbp-A4h]
  unsigned int v56; // [rsp+F8h] [rbp-A0h]
  char v57; // [rsp+100h] [rbp-98h]
  _BYTE v58[32]; // [rsp+108h] [rbp-90h] BYREF
  char v59; // [rsp+128h] [rbp-70h]
  unsigned int v60; // [rsp+12Ch] [rbp-6Ch]
  char v61; // [rsp+130h] [rbp-68h]
  char v62; // [rsp+131h] [rbp-67h]
  _BYTE v63[32]; // [rsp+160h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[13]>();
  wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(
    v45,
    a1);
  v2 = *(_QWORD *)v45;
  *(_QWORD *)v45 = 0;
  v47 = v2;
  v48 = 1;
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v45);
  try
  {
    wil::cloud_store::cloud_store(v51);
    v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                            v3,
                            *(_QWORD *)(a1 + 24),
                            L"SYNC_PEN_SETTINGS",
                            17) )
    {
      PenSettingsTelemetry::CloudPenSettingsTask<unsigned short const (&)[36]>(L"Hits SYNC_PEN_SETTINGS Task Handler");
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>>(v49);
      try
      {
        v52[0] = 0;
        v52[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v52[0]) = 0;
        HandwritingViewRegKeySDDLForCurrentContext = Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContext(v63);
        std::wstring::operator=(v52, HandwritingViewRegKeySDDLForCurrentContext);
        std::wstring::_Tidy_deallocate(v63);
      }
      catch ( ... )
      {
        v45[0] = wil::details::in1diag3::Return_CaughtException(
                   retaddr,
                   (void *)0x99,
                   (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
                   v5);
        std::wstring::_Tidy_deallocate(v52);
        tip2::test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(v49);
        wil::cloud_store::~cloud_store((wil::cloud_store *)v51);
        wil::details::lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2___::_lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2___(&v47);
        return v45[0];
      }
      wil::cloud_store::load<Windows::Data::Input::InkAndPen::InkPlatformSettings>(v51, &v53);
      if ( v57 )
      {
        v6 = v50;
        *(_QWORD *)v45 = v50;
        if ( v50 )
          _InterlockedIncrement((volatile signed __int32 *)(v50 + 320));
        tip2::details::shared_data<0,0,0>::begin_update(v6 + 8);
        std::wstring::operator=(v6 + 280, v58);
        tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(v45);
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
        v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
        v12 = SHRegSetStringWithSSDL(v10, v9, v11, v8, v9);
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
            (const char *)(unsigned int)v12,
            pvData);
      }
      if ( v55 )
      {
        v13 = v56;
        v14 = v50;
        *(_QWORD *)v45 = v50;
        if ( v50 )
          _InterlockedIncrement((volatile signed __int32 *)(v50 + 320));
        tip2::details::shared_data<0,0,0>::begin_update(v14 + 8);
        *(_DWORD *)(v14 + 276) = v13;
        tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(v45);
        v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
        v17 = SHRegSetDWORDWithSSDL(
                v16,
                L"Software\\Microsoft\\TabletTip\\EmbeddedInkControl",
                L"HandwritingFontSize",
                v15,
                v13);
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
            (const char *)(unsigned int)v17,
            pvDataa);
      }
      if ( v53 )
      {
        v18 = v54;
        v19 = v50;
        v46 = v50;
        if ( v50 )
          _InterlockedIncrement((volatile signed __int32 *)(v50 + 320));
        tip2::details::shared_data<0,0,0>::begin_update(v19 + 8);
        *(_BYTE *)(v19 + 272) = v18;
        tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(&v46);
        v45[0] = v54 != 0;
        v20 = SHSetValueW(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\PenWorkspace",
                L"PenWorkspaceAppLaunchOnPenDetachEnabled",
                4u,
                v45,
                4u);
        if ( v20 )
          wil::details::in1diag3::_Log_Win32(retaddr, v21, v22, (const char *)v20, pvDatab);
      }
      if ( v59 )
      {
        v23 = v60;
        v24 = v50;
        v46 = v50;
        if ( v50 )
          _InterlockedIncrement((volatile signed __int32 *)(v50 + 320));
        tip2::details::shared_data<0,0,0>::begin_update(v24 + 8);
        *(_DWORD *)(v24 + 312) = v23;
        tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(&v46);
        v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
        v27 = SHRegSetDWORDWithSSDL(
                v26,
                L"Software\\Microsoft\\TabletTip\\1.7",
                L"EnableDesktopModePenAutoInvoke",
                v25,
                v23);
        if ( v27 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
            (const char *)(unsigned int)v27,
            pvDatac);
      }
      if ( v61 )
      {
        v28 = v62;
        v29 = v50;
        v46 = v50;
        if ( v50 )
          _InterlockedIncrement((volatile signed __int32 *)(v50 + 320));
        tip2::details::shared_data<0,0,0>::begin_update(v29 + 8);
        *(_BYTE *)(v29 + 316) = v28;
        tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(&v46);
        v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
        v33 = SHRegSetBOOLWithSSDL(v32, v31, L"EnableInkingWithTouch", v30, (int)v31);
        if ( v33 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
            (const char *)(unsigned int)v33,
            pvDatad);
      }
      if ( v59 || v61 )
      {
        v34 = SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"touch keyboard");
        v36 = retaddr;
        if ( !v34 )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x99,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
            v35);
        v45[0] = 1;
        wil::wnf_publish<unsigned long>(v36, v45);
      }
      v37 = v50;
      wil::EnterCriticalSection(&v46, v50 + 200);
      *(_DWORD *)(v37 + 72) |= 0x300u;
      if ( *(_QWORD *)(v37 + 248) )
        tip2::details::shared_data<0,0,0>::complete_helper(v37 + 8, 2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v46);
      wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::~cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(&v53);
      std::wstring::_Tidy_deallocate(v52);
      tip2::test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(v49);
    }
    wil::cloud_store::~cloud_store((wil::cloud_store *)v51);
    wil::details::lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2___::_lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2___(&v47);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x99,
                           (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\cdstopensettingtaskhandler.cpp",
                           v38);
  }
  return result;
}

```

## disassembly

```asm
0x18003f4f4  mov     [rsp+arg_8], rbx
0x18003f4f9  mov     [rsp+arg_10], rdi
0x18003f4fe  push    r14
0x18003f500  sub     rsp, 190h
0x18003f507  mov     rax, cs:__security_cookie
0x18003f50e  xor     rax, rsp
0x18003f511  mov     [rsp+198h+var_18], rax
0x18003f519  mov     rbx, rcx
0x18003f51c  call    ??$CloudPenSettingsTask@AEAY0N@$$CBG@PenSettingsTelemetry@@SAXAEAY0N@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[13]>(ushort const (&)[13])
0x18003f521  mov     rdx, rbx
0x18003f524  lea     rcx, [rsp+198h+var_158]
0x18003f529  call    ??0?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy> const &)
0x18003f52e  mov     rax, qword ptr [rsp+198h+var_158]
0x18003f533  mov     qword ptr [rsp+198h+var_158], 0
0x18003f53c  mov     [rsp+198h+var_148], rax
0x18003f541  mov     [rsp+198h+var_140], 1
0x18003f546  lea     rcx, [rsp+198h+var_158]
0x18003f54b  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18003f550  lea     rcx, [rsp+198h+var_F8]
0x18003f558  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x18003f55d  nop
0x18003f55e  lea     rcx, [rbx+8]
0x18003f562  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f567  mov     rcx, rax
0x18003f56a  mov     r9d, 11h
0x18003f570  lea     r8, aSyncPenSetting; "SYNC_PEN_SETTINGS"
0x18003f577  mov     rdx, [rbx+18h]
0x18003f57b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003f580  test    al, al
0x18003f582  jz      loc_18003F9E4
0x18003f588  lea     rcx, aHitsSyncPenSet; "Hits SYNC_PEN_SETTINGS Task Handler"
0x18003f58f  call    ??$CloudPenSettingsTask@AEAY0CE@$$CBG@PenSettingsTelemetry@@SAXAEAY0CE@$$CBG@Z; PenSettingsTelemetry::CloudPenSettingsTask<ushort const (&)[36]>(ushort const (&)[36])
0x18003f594  lea     rcx, [rsp+198h+var_138]
0x18003f599  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003f59e  nop
0x18003f59f  xorps   xmm0, xmm0
0x18003f5a2  movups  [rsp+198h+var_D0], xmm0
0x18003f5aa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003f5b2  movdqu  [rsp+198h+var_C0], xmm1
0x18003f5bb  xor     eax, eax
0x18003f5bd  mov     word ptr [rsp+198h+var_D0], ax
0x18003f5c5  lea     rcx, [rsp+198h+var_38]
0x18003f5cd  call    Helpers__PenAndInkSettingsInternal__GetHandwritingViewRegKeySDDLForCurrentContext
0x18003f5d2  mov     rdx, rax
0x18003f5d5  lea     rcx, [rsp+198h+var_D0]
0x18003f5dd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003f5e2  lea     rcx, [rsp+198h+var_38]
0x18003f5ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f5ef  nop
0x18003f5f0  lea     rdx, [rsp+198h+var_A8]
0x18003f5f8  lea     rcx, [rsp+198h+var_F8]
0x18003f600  call    ??$load@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Input::InkAndPen::InkPlatformSettings>(wil::cloud_store_load_options,char const *)
0x18003f605  nop
0x18003f606  cmp     [rsp+198h+var_98], 0
0x18003f60e  jz      loc_18003F6AB
0x18003f614  lea     rdi, [rsp+198h+var_90]
0x18003f61c  mov     rbx, [rsp+198h+var_100]
0x18003f624  mov     qword ptr [rsp+198h+var_158], rbx
0x18003f629  test    rbx, rbx
0x18003f62c  jz      short loc_18003F635
0x18003f62e  lock inc dword ptr [rbx+140h]
0x18003f635  lea     rcx, [rbx+8]
0x18003f639  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18003f63e  nop
0x18003f63f  lea     rcx, [rbx+118h]
0x18003f646  mov     rdx, rdi
0x18003f649  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003f64e  nop
0x18003f64f  lea     rcx, [rsp+198h+var_158]
0x18003f654  call    ??1?$test_data_control@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f659  lea     r8, [rsp+198h+var_90]
0x18003f661  lea     rcx, [rsp+198h+var_D0]
0x18003f669  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f66e  mov     rdx, rax
0x18003f671  mov     rcx, r8
0x18003f674  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f679  mov     r9, rax; unsigned __int16 *
0x18003f67c  mov     [rsp+198h+pvData], rdx; int
0x18003f681  call    ?SHRegSetStringWithSSDL@@YAJPEAUHKEY__@@PEBG111@Z; SHRegSetStringWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003f686  mov     rcx, [rsp+198h]; this
0x18003f68e  test    eax, eax
0x18003f690  jns     short loc_18003F6AB
0x18003f692  mov     r9d, eax; char *
0x18003f695  lea     rdi, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\p"...
0x18003f69c  mov     r8, rdi; unsigned int
0x18003f69f  mov     edx, 99h; void *
0x18003f6a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f6a9  jmp     short loc_18003F6B2
0x18003f6ab  lea     rdi, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\p"...
0x18003f6b2  cmp     [rsp+198h+var_A4], 0
0x18003f6ba  jz      short loc_18003F73B
0x18003f6bc  mov     r14d, [rsp+198h+var_A0]
0x18003f6c4  mov     rbx, [rsp+198h+var_100]
0x18003f6cc  mov     qword ptr [rsp+198h+var_158], rbx
0x18003f6d1  test    rbx, rbx
0x18003f6d4  jz      short loc_18003F6DD
0x18003f6d6  lock inc dword ptr [rbx+140h]
0x18003f6dd  lea     rcx, [rbx+8]
0x18003f6e1  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18003f6e6  mov     [rbx+114h], r14d
0x18003f6ed  lea     rcx, [rsp+198h+var_158]
0x18003f6f2  call    ??1?$test_data_control@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f6f7  lea     rcx, [rsp+198h+var_D0]
0x18003f6ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f704  mov     r9, rax; unsigned __int16 *
0x18003f707  mov     dword ptr [rsp+198h+pvData], r14d; int
0x18003f70c  lea     r8, aHandwritingfon; "HandwritingFontSize"
0x18003f713  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\TabletTip\\Embedde"...
0x18003f71a  call    ?SHRegSetDWORDWithSSDL@@YAJPEAUHKEY__@@PEBG11K@Z; SHRegSetDWORDWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18003f71f  mov     rcx, [rsp+198h]; this
0x18003f727  test    eax, eax
0x18003f729  jns     short loc_18003F73B
0x18003f72b  mov     r9d, eax; char *
0x18003f72e  mov     r8, rdi; unsigned int
0x18003f731  mov     edx, 99h; void *
0x18003f736  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f73b  cmp     [rsp+198h+var_A8], 0
0x18003f743  jz      loc_18003F7D8
0x18003f749  mov     r14b, [rsp+198h+var_A7]
0x18003f751  mov     rbx, [rsp+198h+var_100]
0x18003f759  mov     [rsp+198h+var_150], rbx
0x18003f75e  test    rbx, rbx
0x18003f761  jz      short loc_18003F76A
0x18003f763  lock inc dword ptr [rbx+140h]
0x18003f76a  lea     rcx, [rbx+8]
0x18003f76e  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18003f773  mov     [rbx+110h], r14b
0x18003f77a  lea     rcx, [rsp+198h+var_150]
0x18003f77f  call    ??1?$test_data_control@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f784  xor     eax, eax
0x18003f786  cmp     [rsp+198h+var_A7], al
0x18003f78d  setnz   al
0x18003f790  mov     [rsp+198h+var_158], eax
0x18003f794  mov     r9d, 4; dwType
0x18003f79a  mov     [rsp+198h+cbData], r9d; cbData
0x18003f79f  lea     rax, [rsp+198h+var_158]
0x18003f7a4  mov     [rsp+198h+pvData], rax; unsigned int
0x18003f7a9  lea     r8, aPenworkspaceap; "PenWorkspaceAppLaunchOnPenDetachEnabled"
0x18003f7b0  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003f7b7  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18003f7be  call    cs:__imp_SHSetValueW
0x18003f7c4  mov     rcx, [rsp+198h]; this
0x18003f7cc  test    eax, eax
0x18003f7ce  jz      short loc_18003F7D8
0x18003f7d0  mov     r9d, eax; char *
0x18003f7d3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003f7d8  cmp     [rsp+198h+var_70], 0
0x18003f7e0  jz      short loc_18003F861
0x18003f7e2  mov     r14d, [rsp+198h+var_6C]
0x18003f7ea  mov     rbx, [rsp+198h+var_100]
0x18003f7f2  mov     [rsp+198h+var_150], rbx
0x18003f7f7  test    rbx, rbx
0x18003f7fa  jz      short loc_18003F803
0x18003f7fc  lock inc dword ptr [rbx+140h]
0x18003f803  lea     rcx, [rbx+8]
0x18003f807  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18003f80c  mov     [rbx+138h], r14d
0x18003f813  lea     rcx, [rsp+198h+var_150]
0x18003f818  call    ??1?$test_data_control@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f81d  lea     rcx, [rsp+198h+var_D0]
0x18003f825  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f82a  mov     r9, rax; unsigned __int16 *
0x18003f82d  mov     dword ptr [rsp+198h+pvData], r14d; int
0x18003f832  lea     r8, aEnabledesktopm; "EnableDesktopModePenAutoInvoke"
0x18003f839  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\TabletTip\\1.7"
0x18003f840  call    ?SHRegSetDWORDWithSSDL@@YAJPEAUHKEY__@@PEBG11K@Z; SHRegSetDWORDWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18003f845  mov     rcx, [rsp+198h]; this
0x18003f84d  test    eax, eax
0x18003f84f  jns     short loc_18003F861
0x18003f851  mov     r9d, eax; char *
0x18003f854  mov     r8, rdi; unsigned int
0x18003f857  mov     edx, 99h; void *
0x18003f85c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f861  cmp     [rsp+198h+var_68], 0
0x18003f869  jz      short loc_18003F8EA
0x18003f86b  mov     r14b, [rsp+198h+var_67]
0x18003f873  mov     rbx, [rsp+198h+var_100]
0x18003f87b  mov     [rsp+198h+var_150], rbx
0x18003f880  test    rbx, rbx
0x18003f883  jz      short loc_18003F88C
0x18003f885  lock inc dword ptr [rbx+140h]
0x18003f88c  lea     rcx, [rbx+8]
0x18003f890  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18003f895  mov     [rbx+13Ch], r14b
0x18003f89c  lea     rcx, [rsp+198h+var_150]
0x18003f8a1  call    ??1?$test_data_control@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_data_control<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f8a6  movzx   edx, [rsp+198h+var_67]
0x18003f8ae  lea     rcx, [rsp+198h+var_D0]
0x18003f8b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003f8bb  mov     r9, rax; unsigned __int16 *
0x18003f8be  mov     dword ptr [rsp+198h+pvData], edx; int
0x18003f8c2  lea     r8, aEnableinkingwi; "EnableInkingWithTouch"
0x18003f8c9  call    ?SHRegSetBOOLWithSSDL@@YAJPEAUHKEY__@@PEBG11H@Z; SHRegSetBOOLWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,int)
0x18003f8ce  mov     rcx, [rsp+198h]; this
0x18003f8d6  test    eax, eax
0x18003f8d8  jns     short loc_18003F8EA
0x18003f8da  mov     r9d, eax; char *
0x18003f8dd  mov     r8, rdi; unsigned int
0x18003f8e0  mov     edx, 99h; void *
0x18003f8e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f8ea  cmp     [rsp+198h+var_70], 0
0x18003f8f2  jnz     short loc_18003F8FE
0x18003f8f4  cmp     [rsp+198h+var_68], 0
0x18003f8fc  jz      short loc_18003F942
0x18003f8fe  lea     r9, lParam; "touch keyboard"
0x18003f905  xor     r8d, r8d; wParam
0x18003f908  lea     edx, [r8+1Ah]; Msg
0x18003f90c  mov     ecx, 0FFFFh; hWnd
0x18003f911  call    cs:__imp_SendNotifyMessageW
0x18003f917  mov     rcx, [rsp+198h]; this
0x18003f91f  test    eax, eax
0x18003f921  jnz     short loc_18003F930
0x18003f923  mov     r8, rdi; unsigned int
0x18003f926  mov     edx, 99h; void *
0x18003f92b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003f930  mov     [rsp+198h+var_158], 1
0x18003f938  lea     rdx, [rsp+198h+var_158]
0x18003f93d  call    ??$wnf_publish@K@wil@@YAXAEBU_WNF_STATE_NAME@@AEBK@Z; wil::wnf_publish<ulong>(_WNF_STATE_NAME const &,ulong const &)
0x18003f942  mov     rbx, [rsp+198h+var_100]
0x18003f94a  lea     rdx, [rbx+0C8h]
0x18003f951  lea     rcx, [rsp+198h+var_150]
0x18003f956  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003f95b  or      dword ptr [rbx+48h], 300h
0x18003f962  cmp     qword ptr [rbx+0F8h], 0
0x18003f96a  jz      short loc_18003F97A
0x18003f96c  mov     edx, 2
0x18003f971  lea     rcx, [rbx+8]
0x18003f975  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003f97a  lea     rcx, [rsp+198h+var_150]
0x18003f97f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003f984  nop
0x18003f985  lea     rcx, [rsp+198h+var_A8]
0x18003f98d  call    ??1?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::~cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(void)
0x18003f992  nop
0x18003f993  lea     rcx, [rsp+198h+var_D0]
0x18003f99b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f9a0  nop
0x18003f9a1  lea     rcx, [rsp+198h+var_138]
0x18003f9a6  call    ??1?$test_watcher@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f9ab  jmp     short loc_18003F9E4
0x18003f9ad  lea     rcx, [rsp+198h+var_D0]
0x18003f9b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f9ba  nop
0x18003f9bb  lea     rcx, [rsp+198h+var_138]
0x18003f9c0  call    ??1?$test_watcher@V?$merged_data@U_tip_RoamedPenAndInkSettingsUpdatesLocalTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>::~test_watcher<tip2::details::merged_data<_tip_RoamedPenAndInkSettingsUpdatesLocalTest,_tip_RoamedPenAndInkSettingsUpdatesLocalTest>>(void)
0x18003f9c5  nop
0x18003f9c6  lea     rcx, [rsp+198h+var_F8]; this
0x18003f9ce  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18003f9d3  nop
0x18003f9d4  lea     rcx, [rsp+198h+var_148]
0x18003f9d9  call    wil__details__lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2______lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2___
0x18003f9de  mov     eax, [rsp+198h+var_158]
0x18003f9e2  jmp     short loc_18003FA05
0x18003f9e4  lea     rcx, [rsp+198h+var_F8]; this
0x18003f9ec  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18003f9f1  nop
0x18003f9f2  lea     rcx, [rsp+198h+var_148]
0x18003f9f7  call    wil__details__lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2______lambda_call__lambda_07510db1f1eeb9b6226e747ed92e08e2___
0x18003f9fc  nop
0x18003f9fd  xor     eax, eax
0x18003f9ff  jmp     short loc_18003FA05
0x18003fa01  mov     eax, [rsp+198h+var_158]
0x18003fa05  mov     rcx, [rsp+198h+var_18]
0x18003fa0d  xor     rcx, rsp; StackCookie
0x18003fa10  call    __security_check_cookie
0x18003fa15  lea     r11, [rsp+198h+var_8]
0x18003fa1d  mov     rbx, [r11+18h]
0x18003fa21  mov     rdi, [r11+20h]
0x18003fa25  mov     rsp, r11
0x18003fa28  pop     r14
0x18003fa2a  retn
```
