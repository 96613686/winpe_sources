# RestoreDeviceWorker::DoWork(void)

- ea: `0x180030434`
- end: `0x180030d4e`
- name: `?DoWork@RestoreDeviceWorker@@QEAAJXZ`
- size: `2330`
- prototype: `__int64 __fastcall(RestoreDeviceWorker *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x180003450`
- `0x180003ff0`
- `0x18000912c`
- `0x18001109c`
- `0x1800110d0`
- `0x180011170`
- `0x180011210`
- `0x180012f10`
- `0x180015338`
- `0x180015818`
- `0x1800174f0`
- `0x180019794`
- `0x1800205d8`
- `0x18002b108`
- `0x18002f4cc`
- `0x18002f854`
- `0x18002fd30`
- `0x18002fe24`
- `0x18002feb4`
- `0x18002ff34`
- `0x180030014`
- `0x1800301f8`
- `0x180030244`
- `0x1800302a4`
- `0x1800302f8`
- `0x18003034c`
- `0x180030434`
- `0x180030e14`
- `0x1800310f8`
- `0x180031170`
- `0x1800311c4`
- `0x18003125c`
- `0x180031360`
- `0x180031538`
- `0x18003305c`
- `0x180033194`
- `0x180046010`

## string_xrefs

- `0x180030512`: `onecoreuap\enduser\winstore\installservice\lib\restoredeviceworker.cpp`
- `0x180030587`: `onecoreuap\enduser\winstore\installservice\lib\restoredeviceworker.cpp`
- `0x180030602`: `onecoreuap\enduser\winstore\installservice\lib\restoredeviceworker.cpp`
- `0x180030693`: `onecoreuap\enduser\winstore\installservice\lib\restoredeviceworker.cpp`
- `0x1800309b2`: `onecoreuap\enduser\winstore\installservice\lib\restoredeviceworker.cpp`
- `0x180030bf3`: `onecoreuap\enduser\winstore\installservice\lib\restoredeviceworker.cpp`

## pseudocode

```c
__int64 __fastcall RestoreDeviceWorker::DoWork(RestoreDeviceWorker *this)
{
  const char *v1; // rdx
  __int64 v2; // rcx
  const char *v3; // r9
  __int64 result; // rax
  unsigned int v5; // eax
  unsigned int v6; // r14d
  int v7; // r12d
  int v8; // r13d
  unsigned int v9; // r15d
  int v10; // eax
  struct IUnknown *v11; // rdx
  int v12; // r14d
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, void **); // rbx
  void **v15; // rax
  unsigned int v16; // eax
  int v17; // ebx
  struct winrt::impl::hstring_header *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // eax
  CorrelationVector *v21; // rcx
  winrt::impl *v22; // rax
  int v23; // r14d
  struct winrt::impl::hstring_header *v24; // rdx
  struct winrt::impl::hstring_header *v25; // rax
  const unsigned __int16 *v26; // rdx
  __int64 *started; // rdi
  int v28; // eax
  struct IUnknown *v29; // rdx
  int v30; // r14d
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, void **); // rbx
  void **v33; // rax
  unsigned int v34; // eax
  unsigned int v35; // ebx
  unsigned int v36; // eax
  const struct winrt::impl::slim_source_location *v37; // rax
  const char *v38; // [rsp+20h] [rbp-278h]
  int v39; // [rsp+50h] [rbp-248h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-244h]
  struct winrt::impl::hstring_header *v41; // [rsp+58h] [rbp-240h] BYREF
  int *v42; // [rsp+60h] [rbp-238h] BYREF
  int v43; // [rsp+68h] [rbp-230h] BYREF
  __int64 v44; // [rsp+70h] [rbp-228h] BYREF
  int v45; // [rsp+78h] [rbp-220h] BYREF
  _BYTE v46[8]; // [rsp+80h] [rbp-218h] BYREF
  __int64 v47; // [rsp+88h] [rbp-210h] BYREF
  winrt::impl *v48; // [rsp+90h] [rbp-208h] BYREF
  __int64 v49; // [rsp+98h] [rbp-200h] BYREF
  int v50; // [rsp+A0h] [rbp-1F8h]
  int v51; // [rsp+A4h] [rbp-1F4h]
  int v52; // [rsp+A8h] [rbp-1F0h]
  _BYTE v53[8]; // [rsp+B0h] [rbp-1E8h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-1E0h] BYREF
  struct winrt::impl::hstring_header **v55; // [rsp+C0h] [rbp-1D8h] BYREF
  int v56; // [rsp+C8h] [rbp-1D0h]
  struct winrt::impl::hstring_header **v57; // [rsp+D0h] [rbp-1C8h] BYREF
  __int128 v58; // [rsp+D8h] [rbp-1C0h]
  _QWORD v59[2]; // [rsp+F0h] [rbp-1A8h] BYREF
  int v60; // [rsp+100h] [rbp-198h] BYREF
  __int128 v61; // [rsp+108h] [rbp-190h]
  _BYTE v62[4]; // [rsp+118h] [rbp-180h] BYREF
  _BYTE v63[4]; // [rsp+11Ch] [rbp-17Ch] BYREF
  _BYTE v64[4]; // [rsp+120h] [rbp-178h] BYREF
  _BYTE v65[4]; // [rsp+124h] [rbp-174h] BYREF
  _BYTE v66[8]; // [rsp+128h] [rbp-170h] BYREF
  __int64 *v67; // [rsp+130h] [rbp-168h] BYREF
  int v68; // [rsp+138h] [rbp-160h]
  int v69; // [rsp+13Ch] [rbp-15Ch]
  __int64 *v70; // [rsp+140h] [rbp-158h] BYREF
  int v71; // [rsp+148h] [rbp-150h]
  int v72; // [rsp+14Ch] [rbp-14Ch]
  _BYTE pExceptionObject[24]; // [rsp+150h] [rbp-148h] BYREF
  _BYTE v74[32]; // [rsp+168h] [rbp-130h] BYREF
  winrt::impl *v75; // [rsp+188h] [rbp-110h] BYREF
  _BYTE v76[8]; // [rsp+1B0h] [rbp-E8h] BYREF
  _BYTE v77[152]; // [rsp+1B8h] [rbp-E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  try
  {
    v40 = 0;
    CorrelationVector::CorrelationVector((CorrelationVector *)v76);
    WindowsUpdate::CommonTelemetry::BeginRestoreDeviceTask((WindowsUpdate::CommonTelemetry *)v77, v1);
    v43 = 0;
    v42 = &v43;
    v59[1] = &qword_180083CB8;
    _InterlockedIncrement64(&qword_180083CB8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics> )
    {
      _lambda_c1356133bec741214822377ffa044616_::operator()(
        &v42,
        v46,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics>);
      _InterlockedDecrement64(&qword_180083CB8);
    }
    else
    {
      _InterlockedDecrement64(&qword_180083CB8);
      winrt::impl::factory_cache_entry<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics>::call<_lambda_c1356133bec741214822377ffa044616_ &>(
        v2,
        v46,
        &v42);
    }
    v41 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(v46, &v41) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
        (const char *)0x8000FFFFLL,
        (int)v38);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v46);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v76);
      return 2147549183LL;
    }
    winrt::impl::consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics<winrt::WindowsUpdate::Internal::IAppOffloadSettingsStatics>::GetForCurrentUser(
      v46,
      &v47);
    v41 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v47, &v41) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
        (const char *)0x8000FFFFLL,
        (int)v38);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v47);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v46);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v76);
      return 2147549183LL;
    }
    winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager::RequestStore();
    v41 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(v53, &v41) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
        (const char *)0x8000FFFFLL,
        (int)v38);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v53);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v47);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v46);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v76);
      return 2147549183LL;
    }
    winrt::impl::consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics<winrt::WindowsUpdate::Internal::IAppOffloadSettingsStatics>::GetForCurrentUser(
      v53,
      &v49);
    v41 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v49, &v41) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
        (const char *)0x8000FFFFLL,
        (int)v38);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v49);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v53);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v47);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v46);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v76);
      return 2147549183LL;
    }
    winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager((winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *)v59);
    v42 = 0;
    if ( v59[0] )
    {
      v60 = 0;
      v61 = 0;
      v5 = (**(__int64 (__fastcall ***)(_QWORD, __int64 *, int **))v59[0])(
             v59[0],
             winrt::impl::guid_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal9>,
             &v42);
      winrt::check_hresult(&v45, v5, &v60);
    }
    v6 = 15;
    v7 = 0;
    v50 = 0;
    v8 = 0;
    v51 = 0;
    v9 = 0;
    v52 = 0;
    v10 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Internal::Shell::AppRestore::RestorableApp>::Size(&v47);
    v43 = v10;
    v45 = v10;
    while ( 1 )
    {
      if ( v9 == v10 )
      {
        v35 = (unsigned int)CorrelationVector::Increment((CorrelationVector *)v76);
        v36 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Internal::Shell::AppRestore::RestorableApp>::Size(&v47);
        WindowsUpdate::CommonTelemetry::EndRestoreDeviceTask(
          (WindowsUpdate::CommonTelemetry *)v36,
          v7,
          v8,
          v35 + 8,
          v38);
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v42);
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v59);
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v49);
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v53);
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v47);
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v46);
        CorrelationVector::~CorrelationVector((CorrelationVector *)v76);
        return 0;
      }
      v44 = 0;
      v12 = v6 | 0x20;
      v40 = v12;
      v13 = v47;
      LODWORD(v57) = 0;
      v58 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v47 + 48LL);
      v15 = winrt::put_abi((winrt *)&v44, v11);
      v16 = v14(v13, v9, v15);
      winrt::check_hresult(v62, v16, &v57);
      v6 = v12 & 0xFFFFFFCF | 0x10;
      v40 = v6;
      v17 = winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::AutoRestoreAction(&v44);
      v56 = v17;
      LODWORD(v13) = winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CatalogSource(&v44);
      winrt::impl::consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics<winrt::WindowsUpdate::Internal::IAppOffloadSettingsStatics>::GetForCurrentUser(
        &v44,
        &v48);
      if ( (_DWORD)v13 != 1 || !v17 )
        break;
      v55 = &v41;
      v41 = winrt::impl::duplicate_hstring(v48, v18);
      v39 = 0;
      LODWORD(v57) = 0;
      v58 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 56LL))(v49, &v39);
      winrt::check_hresult(v63, v19, &v57);
      v67 = &v49;
      v68 = v39;
      v69 = DWORD1(v61);
      v70 = &v49;
      v71 = 0;
      v72 = DWORD1(v61);
      std::find_if_winrt::impl::fast_iterator_winrt::Windows::Foundation::Collections::IVectorView_winrt::Windows::Internal::Shell::AppRestore::RestorableTile_____lambda_9ea81598592e194020d0a3a4c2e3f74e___(
        &v60,
        &v70,
        &v67,
        &v41);
      v39 = 0;
      LODWORD(v57) = 0;
      v58 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 56LL))(v49, &v39);
      winrt::check_hresult(v65, v20, &v57);
      if ( (_DWORD)v61 == v39 )
      {
        winrt::hstring::c_str((winrt::hstring *)&v48);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
          0x3Eu,
          "RestoreDeviceWorker::DoWork",
          -1,
          L"Placeholder no longer present for app: %ls. Skipping auto-restore.",
          0,
          0);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v48);
LABEL_29:
        winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v44);
        goto LABEL_30;
      }
      v21 = CorrelationVector::Increment((CorrelationVector *)v76);
      v22 = (winrt::impl *)CorrelationVector::hstring(v21);
      v55 = 0;
      v23 = v6 | 0x40;
      v40 = v23;
      v25 = winrt::impl::duplicate_hstring(v22, v24);
      winrt::handle_type<winrt::impl::hstring_traits>::attach(&v55, v25);
      v57 = v55;
      winrt::param::hstring::hstring((winrt::param::hstring *)v74, v26);
      v39 = 1;
      v75 = v48;
      started = (__int64 *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IAppInstallManagerInternal9<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal9>::StartAppRestoreAsync(
                             (unsigned int)&v42,
                             (unsigned int)v66,
                             (unsigned int)&v75,
                             (unsigned int)&v39,
                             v17 == 1,
                             (__int64)v74,
                             (__int64)&v57);
      v28 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>>::Status(started);
      if ( !v28 )
        v28 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>>(started);
      if ( v28 == 2 )
      {
        v37 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v57);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v37);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      v54 = 0;
      v30 = v23 | 0x200;
      v40 = v30;
      v31 = *started;
      LODWORD(v57) = 0;
      v58 = 0;
      v32 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v31 + 64LL);
      v33 = winrt::put_abi((winrt *)&v54, v29);
      v34 = v32(v31, v33);
      winrt::check_hresult(v64, v34, &v57);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)v66);
      v6 = v30 & 0xFFFFFC3F | 0x180;
      v40 = v6;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v55);
      v39 = 3;
      winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem5<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InstallInProgressToastNotificationMode(
        &v54,
        &v39);
      v39 = 3;
      winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem5<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::CompletedInstallToastNotificationMode(
        &v54,
        &v39);
      if ( v56 == 1 )
        v50 = ++v7;
      else
        v51 = ++v8;
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v54);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v48);
      winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings((winrt::WindowsUpdate::Internal::IAppOffloadSettings *)&v44);
LABEL_30:
      v52 = ++v9;
      v10 = v43;
    }
    winrt::hstring::c_str((winrt::hstring *)&v48);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
      0x33u,
      "RestoreDeviceWorker::DoWork",
      -1,
      L"Skipping restore for app: %ls. AutoRestoreAction: %d:",
      0,
      0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v48);
    goto LABEL_29;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x58,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\restoredeviceworker.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180030434  push    rbx
0x180030436  push    rsi
0x180030437  push    rdi
0x180030438  push    r12
0x18003043a  push    r13
0x18003043c  push    r14
0x18003043e  push    r15
0x180030440  sub     rsp, 260h
0x180030447  mov     rax, cs:__security_cookie
0x18003044e  xor     rax, rsp
0x180030451  mov     [rsp+298h+var_48], rax
0x180030459  xor     esi, esi
0x18003045b  mov     [rsp+298h+var_244], esi
0x18003045f  lea     rcx, [rsp+298h+var_E8]; this
0x180030467  call    ??0CorrelationVector@@QEAA@XZ; CorrelationVector::CorrelationVector(void)
0x18003046c  nop
0x18003046d  lea     rcx, [rsp+298h+var_E0]; this
0x180030475  call    ?BeginRestoreDeviceTask@CommonTelemetry@WindowsUpdate@@YAXPEBD@Z; WindowsUpdate::CommonTelemetry::BeginRestoreDeviceTask(char const *)
0x18003047a  mov     [rsp+298h+var_230], esi
0x18003047e  lea     rax, [rsp+298h+var_230]
0x180030483  mov     [rsp+298h+var_238], rax
0x180030488  lea     rax, qword_180083CB8
0x18003048f  mov     [rsp+298h+var_1A0], rax
0x180030497  lock inc cs:qword_180083CB8
0x18003049f  cmp     cs:??$factory_cache_entry_v@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@UIRestorableAppItemsManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@UIRestorableAppItemsManagerStatics@23456@@12@A, rsi; factory_cache_entry<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics>
0x1800304a6  jz      short loc_1800304CC
0x1800304a8  lea     r8, ??$factory_cache_entry_v@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@UIRestorableAppItemsManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@UIRestorableAppItemsManagerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics>
0x1800304af  lea     rdx, [rsp+298h+var_218]
0x1800304b7  lea     rcx, [rsp+298h+var_238]
0x1800304bc  call    ??R_lambda_c1356133bec741214822377ffa044616_@@QEBA@AEBUIRestorableAppItemsManagerStatics@AppRestore@Shell@Internal@Windows@winrt@@@Z; _lambda_c1356133bec741214822377ffa044616_::operator()(winrt::Windows::Internal::Shell::AppRestore::IRestorableAppItemsManagerStatics const &)
0x1800304c1  nop
0x1800304c2  lock dec cs:qword_180083CB8
0x1800304ca  jmp     short loc_1800304E7
0x1800304cc  lock dec cs:qword_180083CB8
0x1800304d4  lea     r8, [rsp+298h+var_238]
0x1800304d9  lea     rdx, [rsp+298h+var_218]
0x1800304e1  call    ??$call@AEAV_lambda_c1356133bec741214822377ffa044616_@@@?$factory_cache_entry@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@UIRestorableAppItemsManagerStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_c1356133bec741214822377ffa044616_@@@Z
0x1800304e6  nop
0x1800304e7  mov     [rsp+298h+var_240], rsi
0x1800304ec  lea     rdx, [rsp+298h+var_240]
0x1800304f1  lea     rcx, [rsp+298h+var_218]
0x1800304f9  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800304fe  test    al, al
0x180030500  jz      short loc_180030546
0x180030502  mov     rcx, [rsp+298h]; this
0x18003050a  mov     ebx, 8000FFFFh
0x18003050f  mov     r9d, ebx; char *
0x180030512  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x180030519  mov     edx, 1Ch; void *
0x18003051e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030523  nop
0x180030524  lea     rcx, [rsp+298h+var_218]; this
0x18003052c  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x180030531  nop
0x180030532  lea     rcx, [rsp+298h+var_E8]; this
0x18003053a  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x18003053f  mov     eax, ebx
0x180030541  jmp     loc_180030CF8
0x180030546  lea     rdx, [rsp+298h+var_210]
0x18003054e  lea     rcx, [rsp+298h+var_218]
0x180030556  call    ?GetForCurrentUser@?$consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics@UIAppOffloadSettingsStatics@Internal@WindowsUpdate@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics<winrt::WindowsUpdate::Internal::IAppOffloadSettingsStatics>::GetForCurrentUser(void)
0x18003055b  nop
0x18003055c  mov     [rsp+298h+var_240], rsi
0x180030561  lea     rdx, [rsp+298h+var_240]
0x180030566  lea     rcx, [rsp+298h+var_210]
0x18003056e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180030573  test    al, al
0x180030575  jz      short loc_1800305C9
0x180030577  mov     rcx, [rsp+298h]; this
0x18003057f  mov     ebx, 8000FFFFh
0x180030584  mov     r9d, ebx; char *
0x180030587  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x18003058e  mov     edx, 1Eh; void *
0x180030593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030598  nop
0x180030599  lea     rcx, [rsp+298h+var_210]; this
0x1800305a1  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x1800305a6  nop
0x1800305a7  lea     rcx, [rsp+298h+var_218]; this
0x1800305af  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x1800305b4  nop
0x1800305b5  lea     rcx, [rsp+298h+var_E8]; this
0x1800305bd  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x1800305c2  mov     eax, ebx
0x1800305c4  jmp     loc_180030CF8
0x1800305c9  lea     rcx, [rsp+298h+var_1E8]
0x1800305d1  call    ?RequestStore@RestorableTileItemsManager@AppRestore@Shell@Internal@Windows@winrt@@SA@XZ; winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager::RequestStore(void)
0x1800305d6  nop
0x1800305d7  mov     [rsp+298h+var_240], rsi
0x1800305dc  lea     rdx, [rsp+298h+var_240]
0x1800305e1  lea     rcx, [rsp+298h+var_1E8]
0x1800305e9  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800305ee  test    al, al
0x1800305f0  jz      short loc_180030652
0x1800305f2  mov     rcx, [rsp+298h]; this
0x1800305fa  mov     ebx, 8000FFFFh
0x1800305ff  mov     r9d, ebx; char *
0x180030602  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x180030609  mov     edx, 22h ; '"'; void *
0x18003060e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030613  nop
0x180030614  lea     rcx, [rsp+298h+var_1E8]; this
0x18003061c  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x180030621  nop
0x180030622  lea     rcx, [rsp+298h+var_210]; this
0x18003062a  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x18003062f  nop
0x180030630  lea     rcx, [rsp+298h+var_218]; this
0x180030638  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x18003063d  nop
0x18003063e  lea     rcx, [rsp+298h+var_E8]; this
0x180030646  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x18003064b  mov     eax, ebx
0x18003064d  jmp     loc_180030CF8
0x180030652  lea     rdx, [rsp+298h+var_200]
0x18003065a  lea     rcx, [rsp+298h+var_1E8]
0x180030662  call    ?GetForCurrentUser@?$consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics@UIAppOffloadSettingsStatics@Internal@WindowsUpdate@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics<winrt::WindowsUpdate::Internal::IAppOffloadSettingsStatics>::GetForCurrentUser(void)
0x180030667  nop
0x180030668  mov     [rsp+298h+var_240], rsi
0x18003066d  lea     rdx, [rsp+298h+var_240]
0x180030672  lea     rcx, [rsp+298h+var_200]
0x18003067a  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18003067f  test    al, al
0x180030681  jz      short loc_1800306F1
0x180030683  mov     rcx, [rsp+298h]; this
0x18003068b  mov     ebx, 8000FFFFh
0x180030690  mov     r9d, ebx; char *
0x180030693  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x18003069a  mov     edx, 24h ; '$'; void *
0x18003069f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800306a4  nop
0x1800306a5  lea     rcx, [rsp+298h+var_200]; this
0x1800306ad  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x1800306b2  nop
0x1800306b3  lea     rcx, [rsp+298h+var_1E8]; this
0x1800306bb  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x1800306c0  nop
0x1800306c1  lea     rcx, [rsp+298h+var_210]; this
0x1800306c9  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x1800306ce  nop
0x1800306cf  lea     rcx, [rsp+298h+var_218]; this
0x1800306d7  call    ??1IAppOffloadSettings@Internal@WindowsUpdate@winrt@@QEAA@XZ; winrt::WindowsUpdate::Internal::IAppOffloadSettings::~IAppOffloadSettings(void)
0x1800306dc  nop
0x1800306dd  lea     rcx, [rsp+298h+var_E8]; this
0x1800306e5  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x1800306ea  mov     eax, ebx
0x1800306ec  jmp     loc_180030CF8
0x1800306f1  lea     rcx, [rsp+298h+var_1A8]; this
0x1800306f9  call    ??0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ; winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(void)
0x1800306fe  nop
0x1800306ff  mov     rcx, [rsp+298h+var_1A8]
0x180030707  mov     [rsp+298h+var_238], rsi
0x18003070c  test    rcx, rcx
0x18003070f  jz      short loc_180030759
0x180030711  mov     [rsp+298h+var_198], esi
0x180030718  xorps   xmm0, xmm0
0x18003071b  movdqu  [rsp+298h+var_190], xmm0
0x180030724  mov     rax, [rcx]
0x180030727  lea     r8, [rsp+298h+var_238]
0x18003072c  lea     rdx, ??$guid_v@UIAppInstallManagerInternal9@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal9>
0x180030733  mov     rax, [rax]
0x180030736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003073b  lea     r8, [rsp+298h+var_198]
0x180030743  mov     edx, eax
0x180030745  lea     rcx, [rsp+298h+var_220]
0x18003074a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003074f  mov     rax, [rsp+298h+var_238]
0x180030754  mov     [rsp+298h+var_238], rax
0x180030759  mov     r14d, 0Fh
0x18003075f  mov     r12d, esi
0x180030762  mov     [rsp+298h+var_1F8], esi
0x180030769  mov     r13d, esi
0x18003076c  mov     [rsp+298h+var_1F4], esi
0x180030773  mov     r15d, esi
0x180030776  mov     [rsp+298h+var_1F0], esi
0x18003077d  lea     rcx, [rsp+298h+var_210]
0x180030785  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@URestorableApp@AppRestore@Shell@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Internal::Shell::AppRestore::RestorableApp>::Size(void)
0x18003078a  mov     [rsp+298h+var_230], eax
0x18003078e  mov     [rsp+298h+var_220], eax
0x180030792  cmp     r15d, eax
0x180030795  jz      loc_180030C63
0x18003079b  mov     [rsp+298h+var_228], rsi
0x1800307a0  or      r14d, 20h
0x1800307a4  mov     [rsp+298h+var_244], r14d
0x1800307a9  mov     rdi, [rsp+298h+var_210]
0x1800307b1  mov     dword ptr [rsp+298h+var_1C8], esi
0x1800307b8  xorps   xmm0, xmm0
0x1800307bb  movdqu  [rsp+298h+var_1C0], xmm0
0x1800307c4  mov     rax, [rdi]
0x1800307c7  mov     rbx, [rax+30h]
0x1800307cb  lea     rcx, [rsp+298h+var_228]; this
0x1800307d0  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x1800307d5  mov     r8, rax
0x1800307d8  mov     edx, r15d
0x1800307db  mov     rcx, rdi
0x1800307de  mov     rax, rbx
0x1800307e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307e6  lea     r8, [rsp+298h+var_1C8]
0x1800307ee  mov     edx, eax
0x1800307f0  lea     rcx, [rsp+298h+var_180]
0x1800307f8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800307fd  and     r14d, 0FFFFFFDFh
0x180030801  or      r14d, 10h
0x180030805  mov     [rsp+298h+var_244], r14d
0x18003080a  lea     rcx, [rsp+298h+var_228]
0x18003080f  call    ?AutoRestoreAction@?$consume_Windows_Internal_Shell_AppRestore_IRestorableApp@UIRestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::AutoRestoreAction(void)
0x180030814  mov     ebx, eax
0x180030816  mov     [rsp+298h+var_1D0], eax
0x18003081d  lea     rcx, [rsp+298h+var_228]
0x180030822  call    ?CatalogSource@?$consume_Windows_Internal_Shell_AppRestore_IRestorableApp@UIRestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CatalogSource(void)
0x180030827  mov     edi, eax
0x180030829  lea     rdx, [rsp+298h+var_208]
0x180030831  lea     rcx, [rsp+298h+var_228]
0x180030836  call    ?GetForCurrentUser@?$consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics@UIAppOffloadSettingsStatics@Internal@WindowsUpdate@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUpdate_Internal_IAppOffloadSettingsStatics<winrt::WindowsUpdate::Internal::IAppOffloadSettingsStatics>::GetForCurrentUser(void)
0x18003083b  nop
0x18003083c  cmp     edi, 1
0x18003083f  jnz     loc_180030BB2
0x180030845  test    ebx, ebx
0x180030847  jz      loc_180030BB2
0x18003084d  lea     rax, [rsp+298h+var_240]
0x180030852  mov     [rsp+298h+var_1D8], rax
0x18003085a  mov     rcx, [rsp+298h+var_208]; this
0x180030862  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180030867  mov     [rsp+298h+var_240], rax
0x18003086c  mov     [rsp+298h+var_248], esi
0x180030870  mov     rcx, [rsp+298h+var_200]
0x180030878  mov     dword ptr [rsp+298h+var_1C8], esi
0x18003087f  xorps   xmm0, xmm0
0x180030882  movdqu  [rsp+298h+var_1C0], xmm0
0x18003088b  mov     rax, [rcx]
0x18003088e  lea     rdx, [rsp+298h+var_248]
0x180030893  mov     rax, [rax+38h]
0x180030897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003089c  lea     r8, [rsp+298h+var_1C8]
0x1800308a4  mov     edx, eax
0x1800308a6  lea     rcx, [rsp+298h+var_17C]
0x1800308ae  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800308b3  mov     eax, [rsp+298h+var_248]
0x1800308b7  lea     rcx, [rsp+298h+var_200]
0x1800308bf  mov     [rsp+298h+var_168], rcx
0x1800308c7  mov     [rsp+298h+var_160], eax
0x1800308ce  mov     eax, dword ptr [rsp+298h+var_190+4]
0x1800308d5  mov     [rsp+298h+var_15C], eax
0x1800308dc  lea     rax, [rsp+298h+var_200]
0x1800308e4  mov     [rsp+298h+var_158], rax
0x1800308ec  mov     [rsp+298h+var_150], esi
0x1800308f3  mov     eax, dword ptr [rsp+298h+var_190+4]
0x1800308fa  mov     [rsp+298h+var_14C], eax
0x180030901  lea     r9, [rsp+298h+var_240]
0x180030906  lea     r8, [rsp+298h+var_168]
0x18003090e  lea     rdx, [rsp+298h+var_158]
0x180030916  lea     rcx, [rsp+298h+var_198]
0x18003091e  call    std__find_if_winrt__impl__fast_iterator_winrt__Windows__Foundation__Collections__IVectorView_winrt__Windows__Internal__Shell__AppRestore__RestorableTile_____lambda_9ea81598592e194020d0a3a4c2e3f74e___
0x180030923  mov     [rsp+298h+var_248], esi
0x180030927  mov     rcx, [rsp+298h+var_200]
0x18003092f  mov     dword ptr [rsp+298h+var_1C8], esi
0x180030936  xorps   xmm0, xmm0
0x180030939  movdqu  [rsp+298h+var_1C0], xmm0
0x180030942  mov     rax, [rcx]
0x180030945  lea     rdx, [rsp+298h+var_248]
0x18003094a  mov     rax, [rax+38h]
0x18003094e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030953  lea     r8, [rsp+298h+var_1C8]
0x18003095b  mov     edx, eax
0x18003095d  lea     rcx, [rsp+298h+var_174]
0x180030965  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003096a  mov     eax, [rsp+298h+var_248]
0x18003096e  cmp     dword ptr [rsp+298h+var_190], eax
0x180030975  jnz     short loc_1800309D4
0x180030977  lea     rcx, [rsp+298h+var_208]; this
0x18003097f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180030984  mov     [rsp+298h+var_258], rax
0x180030989  mov     [rsp+298h+var_260], rsi; unsigned __int16 *
0x18003098e  mov     [rsp+298h+var_268], rsi; char *
0x180030993  lea     rax, aPlaceholderNoL; "Placeholder no longer present for app: "...
0x18003099a  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x18003099f  mov     dword ptr [rsp+298h+var_278], 0FFFFFFFFh; int
0x1800309a7  lea     r9, aRestoredevicew; "RestoreDeviceWorker::DoWork"
0x1800309ae  lea     r8d, [rdi+3Dh]; unsigned int
0x1800309b2  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800309b9  lea     ecx, [rdi+2]; unsigned int
0x1800309bc  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800309c1  nop
0x1800309c2  lea     rcx, [rsp+298h+var_208]
0x1800309ca  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800309cf  jmp     loc_180030C12
0x1800309d4  cmp     ebx, 1
0x1800309d7  setz    bl
0x1800309da  lea     rcx, [rsp+298h+var_E8]; this
0x1800309e2  call    ?Increment@CorrelationVector@@QEAAAEAV1@XZ; CorrelationVector::Increment(void)
0x1800309e7  mov     rcx, rax; this
0x1800309ea  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x1800309ef  nop
0x1800309f0  mov     [rsp+298h+var_1D8], rsi
0x1800309f8  or      r14d, 40h
0x1800309fc  mov     [rsp+298h+var_244], r14d
0x180030a01  mov     rcx, rax; this
0x180030a04  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180030a09  mov     rdx, rax
0x180030a0c  lea     rcx, [rsp+298h+var_1D8]
  ... truncated ...
```
