# CExplorerFrame::CreateFrameWindow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<IETHREADPARAM *,void (*)(IETHREADPARAM *),&SHDestroyIETHREADPARAM(IETHREADPARAM *),wistd::integral_constant<unsigned __int64,0>,IETHREADPARAM *,IETHREADPARAM *,0,std::nullptr_t>>> &)

- ea: `0x180191640`
- end: `0x180191d5c`
- name: `?CreateFrameWindow@CExplorerFrame@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUIETHREADPARAM@@P6AXPEAU1@@Z$1?SHDestroyIETHREADPARAM@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1820`
- prototype: `__int64 __fastcall(CExplorerFrame *this)`
- caller_count: `1`
- callee_count: `46`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180094a28`

## callees

- `0x1800218ac`
- `0x180021d88`
- `0x18002e488`
- `0x18002e4e0`
- `0x18002f35c`
- `0x180036ab8`
- `0x180039440`
- `0x180039c48`
- `0x1800471dc`
- `0x180049260`
- `0x180050aa8`
- `0x180071e30`
- `0x1800724a4`
- `0x18008f508`
- `0x1800c8234`
- `0x1800de5cc`
- `0x1800e37d0`
- `0x1800e8b9c`
- `0x1800ebd14`
- `0x1801016ac`
- `0x180104100`
- `0x180105c90`
- `0x180107b64`
- `0x1801084c4`
- `0x1801084e0`
- `0x180110694`
- `0x180116378`
- `0x180116bc4`
- `0x180116c64`
- `0x1801177a8`
- `0x18011abb4`
- `0x180122914`
- `0x18012fda4`
- `0x180130458`
- `0x18013f7d0`
- `0x180147388`
- `0x18018df40`
- `0x18018e67c`
- `0x18018f9e0`
- `0x1801900f4`
- `0x1801913d4`
- `0x180191640`
- `0x18019bb94`
- `0x18019bc0c`
- `0x180208584`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThreadRef` at `0x180191b63`
- `SHCORE!SHCreateThreadRef` at `0x180191b63`
- `SHCORE!SHSetThreadRef` at `0x180191b70`
- `SHCORE!SHSetThreadRef` at `0x180191b70`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x180191806`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x180191806`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180191a2e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180191a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180191952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801918e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801918e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180191978`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180191a42`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180191a42`
- `USER32!CreateWindowExW` at `0x180191afe`
- `USER32!CreateWindowExW` at `0x180191afe`
- `USER32!RegisterPowerSettingNotification` at `0x180191bae`
- `USER32!RegisterPowerSettingNotification` at `0x180191bae`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CExplorerFrame::CreateFrameWindow(CExplorerFrame *this, struct IETHREADPARAM **a2)
{
  bool v4; // al
  _QWORD *v5; // rbx
  wil::details::in1diag3 *v6; // rcx
  _QWORD *v7; // rax
  struct IETHREADPARAM **v8; // rsi
  bool v9; // bl
  CExplorerFrame *v10; // rcx
  __int64 v11; // r14
  char *v12; // rcx
  int (__fastcall ***v13)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **); // r15
  int (__fastcall *v14)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **); // rbx
  HSTRING v15; // rdx
  PCWSTR StringRawBuffer; // rax
  int v17; // eax
  int v18; // ebx
  LANGID UserDefaultUILanguage; // ax
  int v20; // ebx
  HINSTANCE hInstance; // r12
  int v22; // r15d
  __int64 v23; // rdx
  HWND Window; // r15
  __int64 v25; // rdx
  int *v26; // r8
  const char *v27; // r9
  int v28; // eax
  __int64 result; // rax
  int X; // [rsp+20h] [rbp-1E8h]
  UINT32 length[2]; // [rsp+68h] [rbp-1A0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v32; // [rsp+70h] [rbp-198h] BYREF
  int nHeight; // [rsp+78h] [rbp-190h] BYREF
  int nWidth; // [rsp+7Ch] [rbp-18Ch] BYREF
  int Y; // [rsp+80h] [rbp-188h] BYREF
  int v36; // [rsp+84h] [rbp-184h] BYREF
  __int64 v37; // [rsp+88h] [rbp-180h] BYREF
  int v38; // [rsp+94h] [rbp-174h]
  HSTRING string; // [rsp+98h] [rbp-170h]
  _QWORD v40[2]; // [rsp+A0h] [rbp-168h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-158h] BYREF
  HSTRING v42; // [rsp+C8h] [rbp-140h]
  WCHAR Buffer[128]; // [rsp+D0h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v4 = IsControlPanelProcess();
  try
  {
    if ( !v4 )
    {
      v5 = (_QWORD *)((char *)this + 920);
      if ( !(unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerSearchSuccessTest,_tip_FileExplorerSearchSuccessTest>>::operator bool((char *)this + 920) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60906013>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60906013>::GetImpl'::`2'::impl) )
        {
          if ( *v5 && (unsigned __int8)tip2::details::shared_data<0,0,1>::has_ever_started(*v5 + 8LL) )
            wil::details::in1diag3::FailFastImmediate_Unexpected(v6);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::ensure_data((char *)this + 920)
                   + 41LL) = 2;
        }
        if ( *v5 && (unsigned __int8)tip2::details::shared_data<0,0,1>::has_ever_started(*v5 + 8LL) )
          wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>,wil::err_returncode_policy>::reset((char *)this + 920);
        v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::ensure_data((char *)this + 920);
        tip2::details::shared_data<0,0,0>::start(*v7 + 8LL, v40);
        if ( !CachedExplorerExtensionState::IsTabsAvailable() )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::operator->(
                                  (char *)this + 920,
                                  &v37)
                   + 273LL) = 0;
          tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>(&v37);
          tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerUptimeTest,_tip_FileExplorerUptimeTest>>::complete((char *)this + 920);
          wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>,wil::err_returncode_policy>::reset((char *)this + 920);
        }
      }
    }
    v8 = (struct IETHREADPARAM **)((char *)this + 720);
    if ( *((struct IETHREADPARAM **)this + 90) != *a2 && v8 != a2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<IETHREADPARAM *,void (*)(IETHREADPARAM *),&void SHDestroyIETHREADPARAM(IETHREADPARAM *),wistd::integral_constant<unsigned __int64,0>,IETHREADPARAM *,IETHREADPARAM *,0,std::nullptr_t>>::reset((char *)this + 720);
      *a2 = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60906013>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60906013>::GetImpl'::`2'::impl) )
    {
      v9 = (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 35) + 32LL))((char *)this + 280) != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::operator->(
                              (char *)this + 920,
                              &v37)
               + 276LL) = v9;
      tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>(&v37);
    }
    TelemetryCorrelationVectorServiceProvider::MakeSeed(v40);
    v11 = v40[0];
    if ( v40[0] )
    {
      length[0] = 0;
      v12 = (char *)this + 152;
      if ( !this )
        v12 = 0;
      IUnknown_ProfferService(
        v12,
        &GUID_2e228ba3_ea25_4378_97b6_d574faeba356,
        (v40[0] + 40LL) & -(__int64)(v40[0] != 0),
        length);
    }
    CExplorerFrame::_RegisterFrameClass(v10);
    v36 = 10;
    Y = 10;
    nWidth = 800;
    nHeight = 600;
    v13 = (int (__fastcall ***)(_QWORD, GUID *, struct Windows::Foundation::Collections::IPropertySet **))*((_QWORD *)*v8 + 28);
    if ( v13 )
    {
      v32 = 0;
      v14 = **v13;
      Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v32);
      if ( v14(v13, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v32) >= 0 && v32 )
      {
        Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v37,
          v32);
        v15 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &off_1802295C8)
                         + 24);
        Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v37,
          v15);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61168173>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61168173>::GetImpl'::`2'::impl) )
        {
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v42 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"LaunchExplorerWindowRequestGuid",
            0x20u,
            0x1Fu);
          if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
                      (Windows::Internal::ShellHelpers::PropertySetHelper *)&v37,
                      v42) >= 0 )
          {
            length[0] = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(string, length);
            std::string::assign<unsigned short const *,0>(
              (char *)this + 1184,
              StringRawBuffer,
              &StringRawBuffer[length[0]]);
          }
          WindowsDeleteString(string);
        }
        Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v37);
      }
      Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v32);
    }
    CExplorerFrame::ComputeInitialWindowLocation(
      this,
      *((struct _ITEMIDLIST_ABSOLUTE **)*v8 + 5),
      &v36,
      &Y,
      &nWidth,
      &nHeight);
    Buffer[0] = 0;
    LoadStringW(g_hinst, 0x7009u, Buffer, 128);
    v17 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
    if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
    {
      v18 = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
      if ( UserDefaultUILanguage )
        v18 = IsBiDiLocale(UserDefaultUILanguage);
      _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v18 != 0);
      v17 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
    }
    v20 = 0;
    if ( v17 == 1 )
      v20 = 0x400000;
    hInstance = g_hinst;
    if ( *v8 )
      v22 = *((_DWORD *)*v8 + 52);
    else
      v22 = 0;
    if ( g_hActCtx != (HANDLE)-3LL )
      DelayLoadCC();
    Window = CreateWindowExW(
               v22 | (unsigned int)v20,
               L"CabinetWClass",
               Buffer,
               0xCF0000u,
               v36,
               Y,
               nWidth,
               nHeight,
               0,
               0,
               hInstance,
               this);
    if ( Window )
    {
      LOBYTE(v23) = 119;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::__private_IsEnabledPreCheck(
        `wil::Feature<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::GetImpl'::`2'::impl,
        v23);
      wil::ThreadErrorContext::ThreadErrorContext((wil::ThreadErrorContext *)&v37);
      LOBYTE(v25) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash>::GetImpl'::`2'::impl,
        v25);
      if ( v37 )
        *(_DWORD *)(v37 + 16) = v38;
      if ( SHCreateThreadRef((LONG *)this + 75, (IUnknown **)this + 38) >= 0 )
        SHSetThreadRef(*((IUnknown **)this + 38));
      ResolveInitialBrowserLocation(*((HWND *)this + 1), *v8, v26);
      if ( CanShowTabs() )
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 20) + 40LL))((char *)this + 160, 0xFFFFFFFFLL);
      *((_QWORD *)this + 67) = RegisterPowerSettingNotification(Window, &GUID_SESSION_DISPLAY_STATUS, 0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51876866>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51876866>::GetImpl'::`2'::impl) )
      {
        v28 = CExplorerFrame::SubscribeToUserActivityRequest(this);
        if ( v28 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x73C,
            (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
            (const char *)(unsigned int)v28,
            X);
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
      }
      if ( v11 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithGITSite,IServiceProvider,ITelemetryCorrelationVector,Microsoft::WRL::FtmBase>::Release(v11);
      result = 0;
    }
    else
    {
      tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_TabTearOutTest,_tip_TabTearOutTest>>>(&v32);
      if ( v32 )
      {
        if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)v32 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_TabTearOutTest,_tip_TabTearOutTest>>::operator->(
                                  &v32,
                                  v40)
                   + 275LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_TabTearOutTest,_tip_TabTearOutTest>>::~test_data_control<tip2::details::merged_data<_tip_TabTearOutTest,_tip_TabTearOutTest>>(v40);
          if ( v32 )
            tip2::details::shared_data<1,0,0>::complete_without_lock((char *)v32 + 8);
        }
      }
      wil::com_ptr_t<tip2::details::merged_data<_tip_TabTearOutTest,_tip_TabTearOutTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_TabTearOutTest,_tip_TabTearOutTest>,wil::err_returncode_policy>(&v32);
      if ( v11 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithGITSite,IServiceProvider,ITelemetryCorrelationVector,Microsoft::WRL::FtmBase>::Release(v11);
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x759,
                           (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x180191640  mov     [rsp+arg_10], rbx
0x180191645  mov     [rsp+arg_18], rsi
0x18019164a  push    rdi
0x18019164b  push    r12
0x18019164d  push    r13
0x18019164f  push    r14
0x180191651  push    r15
0x180191653  sub     rsp, 1E0h
0x18019165a  mov     rax, cs:__security_cookie
0x180191661  xor     rax, rsp
0x180191664  mov     [rsp+208h+var_38], rax
0x18019166c  mov     r14, rdx
0x18019166f  mov     rdi, rcx
0x180191672  call    ?IsControlPanelProcess@@YA_NXZ; IsControlPanelProcess(void)
0x180191677  xor     r13d, r13d
0x18019167a  test    al, al
0x18019167c  jnz     loc_18019174A
0x180191682  lea     rbx, [rdi+398h]
0x180191689  mov     rcx, rbx
0x18019168c  call    ??B?$tip_test@V?$merged_data@U_tip_FileExplorerSearchSuccessTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerSearchSuccessTest,_tip_FileExplorerSearchSuccessTest>>::operator bool(void)
0x180191691  test    al, al
0x180191693  jnz     loc_18019174A
0x180191699  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60906013@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60906013@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60906013> `wil::Feature<__WilFeatureTraits_Feature_60906013>::GetImpl(void)'::`2'::impl
0x1801916a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60906013@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60906013>::__private_IsEnabled(void)
0x1801916a5  test    al, al
0x1801916a7  jz      short loc_1801916D1
0x1801916a9  mov     rcx, [rbx]
0x1801916ac  test    rcx, rcx
0x1801916af  jz      short loc_1801916C2
0x1801916b1  add     rcx, 8
0x1801916b5  call    ?has_ever_started@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::has_ever_started(void)
0x1801916ba  test    al, al
0x1801916bc  jnz     loc_180191D55
0x1801916c2  mov     rcx, rbx
0x1801916c5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::ensure_data(void)
0x1801916ca  mov     rcx, [rax]
0x1801916cd  mov     byte ptr [rcx+29h], 2
0x1801916d1  mov     rcx, [rbx]
0x1801916d4  test    rcx, rcx
0x1801916d7  jz      short loc_1801916EE
0x1801916d9  add     rcx, 8
0x1801916dd  call    ?has_ever_started@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::has_ever_started(void)
0x1801916e2  test    al, al
0x1801916e4  jz      short loc_1801916EE
0x1801916e6  mov     rcx, rbx
0x1801916e9  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>,wil::err_returncode_policy>::reset(void)
0x1801916ee  mov     rcx, rbx
0x1801916f1  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::ensure_data(void)
0x1801916f6  mov     rcx, [rax]
0x1801916f9  add     rcx, 8
0x1801916fd  lea     rdx, [rsp+208h+var_168]
0x180191705  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18019170a  call    ?IsTabsAvailable@CachedExplorerExtensionState@@SA_NXZ; CachedExplorerExtensionState::IsTabsAvailable(void)
0x18019170f  test    al, al
0x180191711  jnz     short loc_18019174A
0x180191713  lea     rdx, [rsp+208h+var_180]
0x18019171b  mov     rcx, rbx
0x18019171e  call    ??C?$tip_test@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::operator->(void)
0x180191723  mov     rcx, [rax]
0x180191726  mov     [rcx+111h], r13b
0x18019172d  lea     rcx, [rsp+208h+var_180]
0x180191735  call    ??1?$test_data_control@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>(void)
0x18019173a  mov     rcx, rbx
0x18019173d  call    ?complete@?$tip_test@V?$merged_data@U_tip_FileExplorerUptimeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerUptimeTest,_tip_FileExplorerUptimeTest>>::complete(void)
0x180191742  mov     rcx, rbx
0x180191745  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>,wil::err_returncode_policy>::reset(void)
0x18019174a  mov     rdx, [r14]
0x18019174d  lea     rsi, [rdi+2D0h]
0x180191754  cmp     [rsi], rdx
0x180191757  jz      short loc_180191769
0x180191759  cmp     rsi, r14
0x18019175c  jz      short loc_180191769
0x18019175e  mov     rcx, rsi
0x180191761  call    ?reset@?$unique_storage@U?$resource_policy@PEAUIETHREADPARAM@@P6AXPEAU1@@Z$1?SHDestroyIETHREADPARAM@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUIETHREADPARAM@@@Z; wil::details::unique_storage<wil::details::resource_policy<IETHREADPARAM *,void (*)(IETHREADPARAM *),&SHDestroyIETHREADPARAM(IETHREADPARAM *),wistd::integral_constant<unsigned __int64,0>,IETHREADPARAM *,IETHREADPARAM *,0,std::nullptr_t>>::reset(IETHREADPARAM *)
0x180191766  mov     [r14], r13
0x180191769  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60906013@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60906013@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60906013> `wil::Feature<__WilFeatureTraits_Feature_60906013>::GetImpl(void)'::`2'::impl
0x180191770  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60906013@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60906013>::__private_IsEnabled(void)
0x180191775  test    al, al
0x180191777  jz      short loc_1801917BB
0x180191779  lea     rcx, [rdi+118h]
0x180191780  mov     rax, [rcx]
0x180191783  mov     rax, [rax+20h]
0x180191787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019178c  test    eax, eax
0x18019178e  setnz   bl
0x180191791  lea     rcx, [rdi+398h]
0x180191798  lea     rdx, [rsp+208h+var_180]
0x1801917a0  call    ??C?$tip_test@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::operator->(void)
0x1801917a5  mov     rcx, [rax]
0x1801917a8  mov     [rcx+114h], bl
0x1801917ae  lea     rcx, [rsp+208h+var_180]
0x1801917b6  call    ??1?$test_data_control@V?$merged_data@U_tip_FileExplorerFirstTabLaunch@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerFirstTabLaunch,_tip_FileExplorerFirstTabLaunch>>(void)
0x1801917bb  lea     rcx, [rsp+208h+var_168]
0x1801917c3  call    ?MakeSeed@TelemetryCorrelationVectorServiceProvider@@SA?AV?$ComPtr@VTelemetryCorrelationVectorServiceProvider@@@WRL@Microsoft@@XZ; TelemetryCorrelationVectorServiceProvider::MakeSeed(void)
0x1801917c8  nop
0x1801917c9  mov     r14, [rsp+208h+var_168]
0x1801917d1  test    r14, r14
0x1801917d4  jz      short loc_18019180C
0x1801917d6  mov     [rsp+208h+length], r13d
0x1801917db  mov     rax, r14
0x1801917de  lea     rcx, [r14+28h]
0x1801917e2  neg     rax
0x1801917e5  sbb     r8, r8
0x1801917e8  and     r8, rcx
0x1801917eb  test    rdi, rdi
0x1801917ee  lea     rcx, [rdi+98h]
0x1801917f5  jnz     short loc_1801917FA
0x1801917f7  mov     rcx, r13
0x1801917fa  lea     r9, [rsp+208h+length]
0x1801917ff  lea     rdx, _GUID_2e228ba3_ea25_4378_97b6_d574faeba356
0x180191806  call    cs:__imp_IUnknown_ProfferService
0x18019180c  call    ?_RegisterFrameClass@CExplorerFrame@@AEAAXXZ; CExplorerFrame::_RegisterFrameClass(void)
0x180191811  mov     [rsp+208h+var_1A8], r13b
0x180191816  mov     eax, 0Ah
0x18019181b  mov     [rsp+208h+var_184], eax
0x180191822  mov     [rsp+208h+var_188], eax
0x180191829  mov     [rsp+208h+var_18C], 320h
0x180191831  mov     [rsp+208h+var_190], 258h
0x180191839  mov     rax, [rsi]
0x18019183c  mov     r15, [rax+0E0h]
0x180191843  test    r15, r15
0x180191846  jz      loc_1801919D8
0x18019184c  mov     [rsp+208h+var_198], r13
0x180191851  mov     rax, [r15]
0x180191854  mov     rbx, [rax]
0x180191857  lea     rcx, [rsp+208h+var_198]
0x18019185c  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180191861  lea     r8, [rsp+208h+var_198]
0x180191866  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18019186d  mov     rcx, r15
0x180191870  mov     rax, rbx
0x180191873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191878  test    eax, eax
0x18019187a  js      loc_18019198D
0x180191880  mov     rdx, [rsp+208h+var_198]; struct Windows::Foundation::Collections::IPropertySet *
0x180191885  test    rdx, rdx
0x180191888  jz      loc_18019198D
0x18019188e  lea     rcx, [rsp+208h+var_180]; this
0x180191896  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x18019189b  nop
0x18019189c  lea     rdx, off_1802295C8; "IsTabTearOutInProgress"
0x1801918a3  lea     rcx, [rsp+208h+hstringHeader]
0x1801918ab  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801918b0  nop
0x1801918b1  lea     r9, [rsp+208h+var_1A8]
0x1801918b6  mov     rdx, [rax+18h]
0x1801918ba  lea     rcx, [rsp+208h+var_180]
0x1801918c2  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x1801918c7  nop
0x1801918c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61168173@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61168173@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61168173> `wil::Feature<__WilFeatureTraits_Feature_61168173>::GetImpl(void)'::`2'::impl
0x1801918cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61168173@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61168173>::__private_IsEnabled(void)
0x1801918d4  test    al, al
0x1801918d6  jz      loc_18019197F
0x1801918dc  mov     [rsp+208h+string], r13
0x1801918e4  xor     ecx, ecx; string
0x1801918e6  call    cs:__imp_WindowsDeleteString
0x1801918ec  mov     [rsp+208h+string], r13
0x1801918f4  mov     [rsp+208h+var_140], r13
0x1801918fc  mov     r9d, 1Fh; unsigned int
0x180191902  lea     r8d, [r9+1]; unsigned int
0x180191906  lea     rdx, sourceString; "LaunchExplorerWindowRequestGuid"
0x18019190d  lea     rcx, [rsp+208h+hstringHeader]; hstringHeader
0x180191915  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18019191a  nop
0x18019191b  lea     r9, [rsp+208h+string]
0x180191923  mov     rdx, [rsp+208h+var_140]; HSTRING
0x18019192b  lea     rcx, [rsp+208h+var_180]; this
0x180191933  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180191938  nop
0x180191939  shr     eax, 1Fh
0x18019193c  xor     al, 1
0x18019193e  jz      short loc_180191970
0x180191940  mov     [rsp+208h+length], r13d
0x180191945  lea     rdx, [rsp+208h+length]; length
0x18019194a  mov     rcx, [rsp+208h+string]; string
0x180191952  call    cs:__imp_WindowsGetStringRawBuffer
0x180191958  mov     ecx, [rsp+208h+length]
0x18019195c  lea     r8, [rax+rcx*2]
0x180191960  lea     rcx, [rdi+4A0h]
0x180191967  mov     rdx, rax
0x18019196a  call    ??$assign@PEBG$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBG0@Z; std::string::assign<ushort const *,0>(ushort const * const,ushort const * const)
0x18019196f  nop
0x180191970  mov     rcx, [rsp+208h+string]; string
0x180191978  call    cs:__imp_WindowsDeleteString
0x18019197e  nop
0x18019197f  lea     rcx, [rsp+208h+var_180]
0x180191987  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x18019198c  nop
0x18019198d  lea     rcx, [rsp+208h+var_198]
0x180191992  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180191997  cmp     [rsp+208h+var_1A8], r13b
0x18019199c  jz      short loc_1801919D8
0x18019199e  mov     rdx, [rsi]; struct IETHREADPARAM *
0x1801919a1  cmp     [rdx+0D8h], r13
0x1801919a8  jz      short loc_1801919D8
0x1801919aa  lea     rax, [rsp+208h+var_18C]
0x1801919af  mov     qword ptr [rsp+208h+Y], rax; int *
0x1801919b4  lea     rax, [rsp+208h+var_190]
0x1801919b9  mov     qword ptr [rsp+208h+X], rax; int *
0x1801919be  lea     r9, [rsp+208h+var_188]; int *
0x1801919c6  lea     r8, [rsp+208h+var_184]; int *
0x1801919ce  mov     rcx, rdi; this
0x1801919d1  call    ?ComputeTargetWindowPlacement@CExplorerFrame@@AEAAXPEAUIETHREADPARAM@@PEAH111@Z; CExplorerFrame::ComputeTargetWindowPlacement(IETHREADPARAM *,int *,int *,int *,int *)
0x1801919d6  jmp     short loc_180191A0B
0x1801919d8  mov     rdx, [rsi]
0x1801919db  lea     rax, [rsp+208h+var_190]
0x1801919e0  mov     qword ptr [rsp+208h+Y], rax; int *
0x1801919e5  lea     rax, [rsp+208h+var_18C]
0x1801919ea  mov     qword ptr [rsp+208h+X], rax; int *
0x1801919ef  lea     r9, [rsp+208h+var_188]; int *
0x1801919f7  lea     r8, [rsp+208h+var_184]; int *
0x1801919ff  mov     rdx, [rdx+28h]; struct _ITEMIDLIST_ABSOLUTE *
0x180191a03  mov     rcx, rdi; this
0x180191a06  call    ?ComputeInitialWindowLocation@CExplorerFrame@@AEAAXPEAU_ITEMIDLIST_ABSOLUTE@@PEAH111@Z; CExplorerFrame::ComputeInitialWindowLocation(_ITEMIDLIST_ABSOLUTE *,int *,int *,int *,int *)
0x180191a0b  mov     [rsp+208h+Buffer], r13w
0x180191a14  mov     r9d, 80h; cchBufferMax
0x180191a1a  lea     r8, [rsp+208h+Buffer]; lpBuffer
0x180191a22  mov     edx, 7009h; uID
0x180191a27  mov     rcx, cs:g_hinst; hInstance
0x180191a2e  call    cs:__imp_LoadStringW
0x180191a34  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180191a3a  cmp     eax, 0FFFFFFFFh
0x180191a3d  jnz     short loc_180191A72
0x180191a3f  mov     ebx, r13d
0x180191a42  call    cs:__imp_GetUserDefaultUILanguage
0x180191a48  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x180191a4f  test    ax, ax
0x180191a52  jz      short loc_180191A5E
0x180191a54  movzx   ecx, ax; unsigned int
0x180191a57  call    ?IsBiDiLocale@@YAHK@Z; IsBiDiLocale(ulong)
0x180191a5c  mov     ebx, eax
0x180191a5e  mov     ecx, r13d
0x180191a61  test    ebx, ebx
0x180191a63  setnz   cl
0x180191a66  xchg    ecx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180191a6c  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180191a72  mov     ebx, r13d
0x180191a75  mov     ecx, 400000h
0x180191a7a  cmp     eax, 1
0x180191a7d  cmovz   ebx, ecx
0x180191a80  mov     r12, cs:g_hinst
0x180191a87  mov     rax, [rsi]
0x180191a8a  test    rax, rax
0x180191a8d  jz      short loc_180191A98
0x180191a8f  mov     r15d, [rax+0D0h]
0x180191a96  jmp     short loc_180191A9B
0x180191a98  mov     r15d, r13d
0x180191a9b  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x180191aa3  jz      short loc_180191AAA
0x180191aa5  call    DelayLoadCC
0x180191aaa  or      ebx, r15d
0x180191aad  mov     [rsp+208h+lpParam], rdi; lpParam
0x180191ab2  mov     [rsp+208h+hInstance], r12; hInstance
0x180191ab7  mov     [rsp+208h+hMenu], r13; hMenu
0x180191abc  mov     [rsp+208h+hWndParent], r13; hWndParent
0x180191ac1  mov     eax, [rsp+208h+var_190]
0x180191ac5  mov     [rsp+208h+nHeight], eax; nHeight
0x180191ac9  mov     eax, [rsp+208h+var_18C]
0x180191acd  mov     [rsp+208h+nWidth], eax; nWidth
0x180191ad1  mov     eax, [rsp+208h+var_188]
0x180191ad8  mov     [rsp+208h+Y], eax; Y
0x180191adc  mov     eax, [rsp+208h+var_184]
0x180191ae3  mov     [rsp+208h+X], eax; int
0x180191ae7  mov     r9d, 0CF0000h; dwStyle
0x180191aed  lea     r8, [rsp+208h+Buffer]; lpWindowName
0x180191af5  lea     rdx, aCabinetwclass; "CabinetWClass"
0x180191afc  mov     ecx, ebx; dwExStyle
0x180191afe  call    cs:__imp_CreateWindowExW
0x180191b04  mov     r15, rax
0x180191b07  test    rax, rax
0x180191b0a  jz      loc_180191CA8
0x180191b10  mov     dl, 77h ; 'w'
0x180191b12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme> `wil::Feature<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::GetImpl(void)'::`2'::impl
0x180191b19  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180191b1e  lea     rcx, [rsp+208h+var_180]; this
0x180191b26  call    ??0ThreadErrorContext@wil@@QEAA@XZ; wil::ThreadErrorContext::ThreadErrorContext(void)
0x180191b2b  nop
0x180191b2c  mov     dl, 1
0x180191b2e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash>::GetImpl(void)'::`2'::impl
0x180191b35  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorerItemViewFlash>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180191b3a  nop
0x180191b3b  mov     rcx, [rsp+208h+var_180]
0x180191b43  test    rcx, rcx
0x180191b46  jz      short loc_180191B52
0x180191b48  mov     eax, [rsp+208h+var_174]
0x180191b4f  mov     [rcx+10h], eax
0x180191b52  lea     rbx, [rdi+130h]
0x180191b59  lea     rcx, [rdi+12Ch]; pcRef
0x180191b60  mov     rdx, rbx; ppunk
0x180191b63  call    cs:__imp_SHCreateThreadRef
0x180191b69  test    eax, eax
0x180191b6b  js      short loc_180191B76
0x180191b6d  mov     rcx, [rbx]; punk
0x180191b70  call    cs:__imp_SHSetThreadRef
0x180191b76  mov     rdx, [rsi]; struct IETHREADPARAM *
0x180191b79  mov     rcx, [rdi+8]; HWND
0x180191b7d  call    ?ResolveInitialBrowserLocation@@YAJPEAUHWND__@@PEAUIETHREADPARAM@@PEAH@Z; ResolveInitialBrowserLocation(HWND__ *,IETHREADPARAM *,int *)
0x180191b82  call    ?CanShowTabs@@YA_NXZ; CanShowTabs(void)
0x180191b87  test    al, al
0x180191b89  jz      short loc_180191BA1
  ... truncated ...
```
