# CAppListBackupLauncher::Worker(void)

- ea: `0x18000dfe0`
- end: `0x18000e699`
- name: `?Worker@CAppListBackupLauncher@@EEAAJXZ`
- size: `1721`
- prototype: `__int64 __fastcall(CAppListBackupLauncher *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002300`
- `0x180002de0`
- `0x1800034e0`
- `0x18000355c`
- `0x180005bfc`
- `0x180008564`
- `0x18000ca14`
- `0x18000cc18`
- `0x18000dfe0`
- `0x18000e858`
- `0x18000e87c`
- `0x18000e9a0`
- `0x18000ec24`
- `0x18000f214`
- `0x18000f544`
- `0x180012010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18000e1a5`
- `msvcp_win!_Xtime_get_ticks` at `0x18000e265`
- `msvcp_win!_Xtime_get_ticks` at `0x18000e1a5`
- `msvcp_win!_Xtime_get_ticks` at `0x18000e265`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e64a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e651`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e64a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1c6`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000e1ef`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000e1ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e11f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e11f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e165`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e165`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e19f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e1d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e19f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e1d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e212`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000e2b7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000e2b7`

## string_xrefs

- `0x18000e2f3`: `WindowsUdk.System.UserProfile.AppListBackupExtension`
- `0x18000e330`: `com.microsoft.windows.extension.applistbackup`
- `0x18000e4b0`: `com.microsoft.windows.extension.applistbackup`

## pseudocode

```c
__int64 __fastcall CAppListBackupLauncher::Worker(CAppListBackupLauncher *this)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  __int64 v4; // rdi
  char v5; // si
  __int64 v6; // rbx
  HKEY v7; // rdi
  DWORD LastError; // ebx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  void (__fastcall ***v15)(_QWORD, __int64 *, HKEY *); // rcx
  __int64 v16; // rdi
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  void (__fastcall ***v20)(_QWORD, __int64 *, HKEY *); // rcx
  __int64 v21; // rbx
  __int64 v22; // rsi
  int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-278h]
  unsigned int phkResulta; // [rsp+20h] [rbp-278h]
  __int64 pvData; // [rsp+40h] [rbp-258h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-250h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-248h] BYREF
  __int64 Data; // [rsp+58h] [rbp-240h] BYREF
  int v30; // [rsp+60h] [rbp-238h] BYREF
  __int128 v31; // [rsp+68h] [rbp-230h]
  _DWORD *v32; // [rsp+78h] [rbp-220h]
  _DWORD v33[4]; // [rsp+80h] [rbp-218h] BYREF
  const wchar_t *v34; // [rsp+90h] [rbp-208h]
  _DWORD *v35; // [rsp+98h] [rbp-200h] BYREF
  _DWORD v36[4]; // [rsp+A0h] [rbp-1F8h] BYREF
  const wchar_t *v37; // [rsp+B0h] [rbp-1E8h]
  _DWORD *v38; // [rsp+B8h] [rbp-1E0h]
  _DWORD v39[4]; // [rsp+C0h] [rbp-1D8h] BYREF
  const wchar_t *v40; // [rsp+D0h] [rbp-1C8h]
  _DWORD *v41; // [rsp+D8h] [rbp-1C0h] BYREF
  _DWORD v42[4]; // [rsp+E0h] [rbp-1B8h] BYREF
  const wchar_t *v43; // [rsp+F0h] [rbp-1A8h]
  void **v44; // [rsp+110h] [rbp-188h] BYREF
  int v45; // [rsp+118h] [rbp-180h] BYREF
  char v46; // [rsp+11Ch] [rbp-17Ch]
  int v47; // [rsp+140h] [rbp-158h] BYREF
  const char *v48; // [rsp+148h] [rbp-150h]
  __int64 v49; // [rsp+150h] [rbp-148h]
  char v50; // [rsp+158h] [rbp-140h]
  int v51; // [rsp+160h] [rbp-138h]
  _BYTE v52[168]; // [rsp+168h] [rbp-130h] BYREF
  int v53; // [rsp+210h] [rbp-88h]
  __int64 v54; // [rsp+218h] [rbp-80h]
  int *v55; // [rsp+220h] [rbp-78h]
  __int64 v56; // [rsp+228h] [rbp-70h]
  __int64 v57; // [rsp+230h] [rbp-68h]
  void ***v58; // [rsp+238h] [rbp-60h]
  __int64 v59; // [rsp+240h] [rbp-58h]
  int v60; // [rsp+248h] [rbp-50h]
  int *v61; // [rsp+250h] [rbp-48h]
  char v62; // [rsp+258h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v45 = 0;
  v46 = 0;
  v50 = 0;
  v47 = 0;
  v48 = "AppListBackupLauncher";
  v49 = 0;
  v51 = 0;
  *(_OWORD *)&v52[152] = 0;
  memset_0(v52, 0, 0x98u);
  v53 = 1;
  v54 = 0;
  v55 = &v45;
  v56 = 0;
  v57 = 0;
  v58 = &v44;
  v59 = 0;
  v60 = 0;
  v61 = &v47;
  v62 = 0;
  v44 = &AppListBackupLauncherTelemetry::AppListBackupLauncher::`vftable';
  AppListBackupLauncherTelemetry::AppListBackupLauncher::StartActivity((AppListBackupLauncherTelemetry::AppListBackupLauncher *)&v44);
  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\AppListBackup", 0, 1u, &hkey);
  if ( v2 )
  {
    if ( v2 != 2 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x5C, v3, (const char *)v2, phkResult);
    v7 = hkey;
    if ( hkey )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    hkey = 0;
    v9 = RegCreateKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\AppListBackup", &hkey);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x58, v10, (const char *)v9, phkResult);
  }
  else
  {
    pvData = 0;
    pcbData[0] = 8;
    if ( !RegGetValueW(hkey, 0, L"LastRun", 0x40u, 0, &pvData, pcbData) )
    {
      v4 = 36000000000LL * (10000 * pvData / 36000000000LL);
      v5 = 1;
      if ( hkey )
        RegCloseKey(hkey);
      v6 = _Xtime_get_ticks() - v4;
      goto LABEL_13;
    }
  }
  v5 = 0;
  if ( hkey )
    RegCloseKey(hkey);
  v6 = 0;
LABEL_13:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetImpl'::`2'::impl)
    && _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
  {
    goto LABEL_15;
  }
  if ( !v5 || v6 > 6048000000000LL )
  {
    Data = _Xtime_get_ticks() / 10000;
    v12 = RegSetKeyValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\AppListBackup",
            L"LastRun",
            0xBu,
            &Data,
            8u);
    if ( v12 )
      wil::details::in1diag3::_Log_Win32(retaddr, v13, v14, (const char *)v12, phkResulta);
    if ( aWindowsudkSyst[52]
      || (v33[0] = 1,
          v33[1] = 52,
          v34 = L"WindowsUdk.System.UserProfile.AppListBackupExtension",
          v32 = v33,
          aComMicrosoftWi[45]) )
    {
      abort();
    }
    v36[0] = 1;
    v36[1] = 45;
    v37 = L"com.microsoft.windows.extension.applistbackup";
    v35 = v36;
    v15 = *(void (__fastcall ****)(_QWORD, __int64 *, HKEY *))winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(
                                                                (const struct winrt::param::hstring *)pcbData,
                                                                (const struct winrt::param::hstring *)&v35);
    if ( v15 )
    {
      pvData = 0;
      (**v15)(
        v15,
        winrt::impl::guid_v<winrt::WindowsUdk::System::UserProfile::IAppListBackupExtensionStatics>,
        (HKEY *)&pvData);
      v16 = pvData;
      hkey = (HKEY)pvData;
      v17 = pvData;
    }
    else
    {
      v16 = 0;
      hkey = 0;
      v17 = 0;
    }
    if ( *(_QWORD *)pcbData )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(pcbData);
    if ( v17 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetImpl'::`2'::impl)
        && _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
      {
        if ( v16 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&hkey);
LABEL_15:
        AppListBackupLauncherTelemetry::AppListBackupLauncher::~AppListBackupLauncher((AppListBackupLauncherTelemetry::AppListBackupLauncher *)&v44);
        return 2147943623LL;
      }
      pvData = 0;
      v30 = 0;
      v31 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 48LL))(v16, &pvData);
      if ( v18 < 0 )
        winrt::throw_hresult((unsigned int)v18, &v30);
      v19 = pvData;
      winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(&pvData);
      if ( v19 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pvData);
    }
    else
    {
      AppListBackupLauncherTelemetry::NullFactory_Error<unsigned short const (&)[45]>();
    }
    if ( aWindowsudkSyst[52]
      || (v39[0] = 1,
          v39[1] = 52,
          v40 = L"WindowsUdk.System.UserProfile.AppListBackupExtension",
          v38 = v39,
          aComMicrosoftWi[45]) )
    {
      abort();
    }
    v42[0] = 1;
    v42[1] = 45;
    v43 = L"com.microsoft.windows.extension.applistbackup";
    v41 = v42;
    v20 = *(void (__fastcall ****)(_QWORD, __int64 *, HKEY *))winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(
                                                                (const struct winrt::param::hstring *)&Data,
                                                                (const struct winrt::param::hstring *)&v41);
    if ( v20 )
    {
      pvData = 0;
      (**v20)(
        v20,
        winrt::impl::guid_v<winrt::WindowsUdk::System::UserProfile::IAppListBackupExtensionStatics5>,
        (HKEY *)&pvData);
      v21 = pvData;
      v22 = pvData;
    }
    else
    {
      v21 = 0;
      v22 = 0;
    }
    *(_QWORD *)pcbData = v21;
    if ( Data )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&Data);
    if ( v22 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetImpl'::`2'::impl)
        && _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
      {
        if ( v21 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(pcbData);
        if ( v16 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&hkey);
        goto LABEL_15;
      }
      pvData = 0;
      v30 = 0;
      v31 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 48LL))(v21, &pvData);
      if ( v23 < 0 )
        winrt::throw_hresult((unsigned int)v23, &v30);
      Data = pvData;
      if ( pvData )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&Data);
    }
    else
    {
      AppListBackupLauncherTelemetry::NullFactory_Error<unsigned short const (&)[83]>();
      v21 = 0;
    }
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(pcbData);
    if ( v16 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&hkey);
  }
  wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v44);
  AppListBackupLauncherTelemetry::AppListBackupLauncher::~AppListBackupLauncher((AppListBackupLauncherTelemetry::AppListBackupLauncher *)&v44);
  return 0;
}

```

## disassembly

```asm
0x18000dfe0  mov     r11, rsp
0x18000dfe3  mov     [r11+10h], rbx
0x18000dfe7  mov     [r11+18h], rsi
0x18000dfeb  push    rdi
0x18000dfec  push    r12
0x18000dfee  push    r13
0x18000dff0  push    r14
0x18000dff2  push    r15
0x18000dff4  sub     rsp, 270h
0x18000dffb  mov     rax, cs:__security_cookie
0x18000e002  xor     rax, rsp
0x18000e005  mov     [rsp+298h+var_38], rax
0x18000e00d  mov     r14, rcx
0x18000e010  xor     r15d, r15d
0x18000e013  mov     [r11-180h], r15d
0x18000e01a  mov     [r11-17Ch], r15b
0x18000e021  mov     [r11-140h], r15b
0x18000e028  mov     [r11-158h], r15d
0x18000e02f  lea     rax, aApplistbackupl_2; "AppListBackupLauncher"
0x18000e036  mov     [r11-150h], rax
0x18000e03d  mov     [r11-148h], r15
0x18000e044  mov     [r11-138h], r15d
0x18000e04b  xorps   xmm0, xmm0
0x18000e04e  movdqa  [rsp+298h+var_98], xmm0
0x18000e057  xor     edx, edx; Val
0x18000e059  mov     r8d, 98h; Size
0x18000e05f  lea     rcx, [r11-130h]; void *
0x18000e066  call    memset_0
0x18000e06b  lea     r12d, [r15+1]
0x18000e06f  mov     [rsp+298h+var_88], r12d
0x18000e077  xor     eax, eax
0x18000e079  mov     [rsp+298h+var_80], rax
0x18000e081  lea     rax, [rsp+298h+var_180]
0x18000e089  mov     [rsp+298h+var_78], rax
0x18000e091  mov     [rsp+298h+var_70], r15
0x18000e099  mov     [rsp+298h+var_68], r15
0x18000e0a1  lea     rax, [rsp+298h+var_188]
0x18000e0a9  mov     [rsp+298h+var_60], rax
0x18000e0b1  mov     [rsp+298h+var_58], r15
0x18000e0b9  mov     [rsp+298h+var_50], r15d
0x18000e0c1  lea     rax, [rsp+298h+var_158]
0x18000e0c9  mov     [rsp+298h+var_48], rax
0x18000e0d1  mov     [rsp+298h+var_40], r15b
0x18000e0d9  lea     rax, ??_7AppListBackupLauncher@AppListBackupLauncherTelemetry@@6B@; const AppListBackupLauncherTelemetry::AppListBackupLauncher::`vftable'
0x18000e0e0  mov     [rsp+298h+var_188], rax
0x18000e0e8  lea     rcx, [rsp+298h+var_188]; this
0x18000e0f0  call    ?StartActivity@AppListBackupLauncher@AppListBackupLauncherTelemetry@@QEAAXXZ; AppListBackupLauncherTelemetry::AppListBackupLauncher::StartActivity(void)
0x18000e0f5  nop
0x18000e0f6  mov     [rsp+298h+hkey], r15
0x18000e0fb  lea     rax, [rsp+298h+hkey]
0x18000e100  mov     [rsp+298h+phkResult], rax; unsigned int
0x18000e105  mov     r9d, r12d; samDesired
0x18000e108  xor     r8d, r8d; ulOptions
0x18000e10b  lea     r13, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e112  mov     rdx, r13; lpSubKey
0x18000e115  mov     rsi, 0FFFFFFFF80000001h
0x18000e11c  mov     rcx, rsi; hKey
0x18000e11f  call    cs:__imp_RegOpenKeyExW
0x18000e125  test    eax, eax
0x18000e127  jnz     loc_18000E1B3
0x18000e12d  mov     [rsp+298h+var_258], r15
0x18000e132  mov     [rsp+298h+var_250], 8
0x18000e13a  lea     rax, [rsp+298h+var_250]
0x18000e13f  mov     [rsp+298h+pcbData], rax; pcbData
0x18000e144  lea     rax, [rsp+298h+var_258]
0x18000e149  mov     [rsp+298h+pvData], rax; pvData
0x18000e14e  mov     [rsp+298h+phkResult], r15; pdwType
0x18000e153  lea     r9d, [r15+40h]; dwFlags
0x18000e157  lea     r8, Value; "LastRun"
0x18000e15e  xor     edx, edx; lpSubKey
0x18000e160  mov     rcx, [rsp+298h+hkey]; hkey
0x18000e165  call    cs:__imp_RegGetValueW
0x18000e16b  test    eax, eax
0x18000e16d  jnz     loc_18000E205
0x18000e173  imul    rax, [rsp+298h+var_258], 2710h
0x18000e17c  cqo
0x18000e17e  mov     rcx, 861C46800h
0x18000e188  idiv    rcx
0x18000e18b  movsxd  rdi, eax
0x18000e18e  imul    rdi, rcx
0x18000e192  mov     sil, r12b
0x18000e195  mov     rcx, [rsp+298h+hkey]; hKey
0x18000e19a  test    rcx, rcx
0x18000e19d  jz      short loc_18000E1A5
0x18000e19f  call    cs:__imp_RegCloseKey
0x18000e1a5  call    cs:__imp__Xtime_get_ticks
0x18000e1ab  mov     rbx, rax
0x18000e1ae  sub     rbx, rdi
0x18000e1b1  jmp     short loc_18000E21B
0x18000e1b3  cmp     eax, 2
0x18000e1b6  jnz     loc_18000E682
0x18000e1bc  mov     rdi, [rsp+298h+hkey]
0x18000e1c1  test    rdi, rdi
0x18000e1c4  jz      short loc_18000E1DF
0x18000e1c6  call    cs:__imp_GetLastError
0x18000e1cc  mov     ebx, eax
0x18000e1ce  mov     rcx, rdi; hKey
0x18000e1d1  call    cs:__imp_RegCloseKey
0x18000e1d7  mov     ecx, ebx; dwErrCode
0x18000e1d9  call    cs:__imp_SetLastError
0x18000e1df  mov     [rsp+298h+hkey], r15
0x18000e1e4  lea     r8, [rsp+298h+hkey]; phkResult
0x18000e1e9  mov     rdx, r13; lpSubKey
0x18000e1ec  mov     rcx, rsi; hKey
0x18000e1ef  call    cs:__imp_RegCreateKeyW
0x18000e1f5  mov     rcx, [rsp+298h]; this
0x18000e1fd  test    eax, eax
0x18000e1ff  jnz     loc_18000E65A
0x18000e205  mov     sil, r15b
0x18000e208  mov     rcx, [rsp+298h+hkey]; hKey
0x18000e20d  test    rcx, rcx
0x18000e210  jz      short loc_18000E218
0x18000e212  call    cs:__imp_RegCloseKey
0x18000e218  mov     rbx, r15
0x18000e21b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup> `wil::Feature<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetImpl(void)'::`2'::impl
0x18000e222  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::__private_IsEnabled(void)
0x18000e227  test    al, al
0x18000e229  jz      short loc_18000E24D
0x18000e22b  mov     eax, r12d
0x18000e22e  lock cmpxchg [r14+24h], r12d
0x18000e234  jnz     short loc_18000E24D
0x18000e236  lea     rcx, [rsp+298h+var_188]; this
0x18000e23e  call    ??1AppListBackupLauncher@AppListBackupLauncherTelemetry@@QEAA@XZ; AppListBackupLauncherTelemetry::AppListBackupLauncher::~AppListBackupLauncher(void)
0x18000e243  mov     eax, 800704C7h
0x18000e248  jmp     loc_18000E61D
0x18000e24d  test    sil, sil
0x18000e250  jz      short loc_18000E265
0x18000e252  mov     rax, 58028E44000h
0x18000e25c  cmp     rbx, rax
0x18000e25f  jle     loc_18000E600
0x18000e265  call    cs:__imp__Xtime_get_ticks
0x18000e26b  mov     rcx, rax
0x18000e26e  mov     rax, 346DC5D63886594Bh
0x18000e278  imul    rcx
0x18000e27b  sar     rdx, 0Bh
0x18000e27f  mov     rax, rdx
0x18000e282  shr     rax, 3Fh
0x18000e286  add     rdx, rax
0x18000e289  mov     [rsp+298h+Data], rdx
0x18000e28e  mov     dword ptr [rsp+298h+pvData], 8; cbData
0x18000e296  lea     rax, [rsp+298h+Data]
0x18000e29b  mov     [rsp+298h+phkResult], rax; unsigned int
0x18000e2a0  mov     r9d, 0Bh; dwType
0x18000e2a6  lea     r8, Value; "LastRun"
0x18000e2ad  mov     rdx, r13; lpSubKey
0x18000e2b0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e2b7  call    cs:__imp_RegSetKeyValueW
0x18000e2bd  mov     rcx, [rsp+298h]; this
0x18000e2c5  test    eax, eax
0x18000e2c7  jz      short loc_18000E2D1
0x18000e2c9  mov     r9d, eax; char *
0x18000e2cc  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000e2d1  cmp     word ptr cs:aWindowsudkSyst+68h, r15w; ""
0x18000e2d9  jnz     loc_18000E651
0x18000e2df  mov     [rsp+298h+var_218], r12d
0x18000e2e7  mov     esi, 34h ; '4'
0x18000e2ec  mov     [rsp+298h+var_214], esi
0x18000e2f3  lea     r13, aWindowsudkSyst; "WindowsUdk.System.UserProfile.AppListBa"...
0x18000e2fa  mov     [rsp+298h+var_208], r13
0x18000e302  lea     rax, [rsp+298h+var_218]
0x18000e30a  mov     [rsp+298h+var_220], rax
0x18000e30f  cmp     word ptr cs:aComMicrosoftWi+5Ah, r15w; ""
0x18000e317  jnz     loc_18000E651
0x18000e31d  mov     [rsp+298h+var_1F8], r12d
0x18000e325  mov     [rsp+298h+var_1F4], 2Dh ; '-'
0x18000e330  lea     rax, aComMicrosoftWi; "com.microsoft.windows.extension.applist"...
0x18000e337  mov     [rsp+298h+var_1E8], rax
0x18000e33f  lea     rax, [rsp+298h+var_1F8]
0x18000e347  mov     [rsp+298h+var_200], rax
0x18000e34f  lea     r8, [rsp+298h+var_220]
0x18000e354  lea     rdx, [rsp+298h+var_200]; struct winrt::param::hstring *
0x18000e35c  lea     rcx, [rsp+298h+var_250]; struct winrt::param::hstring *
0x18000e361  call    ?GetFactory@ExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@0@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(winrt::param::hstring const &,winrt::param::hstring const &)
0x18000e366  mov     rcx, [rax]
0x18000e369  test    rcx, rcx
0x18000e36c  jnz     short loc_18000E37B
0x18000e36e  mov     rdi, r15
0x18000e371  mov     [rsp+298h+hkey], r15
0x18000e376  mov     rbx, r15
0x18000e379  jmp     short loc_18000E3A4
0x18000e37b  mov     [rsp+298h+var_258], r15
0x18000e380  mov     rax, [rcx]
0x18000e383  lea     r8, [rsp+298h+var_258]
0x18000e388  lea     rdx, ??$guid_v@UIAppListBackupExtensionStatics@UserProfile@System@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::System::UserProfile::IAppListBackupExtensionStatics>
0x18000e38f  mov     rax, [rax]
0x18000e392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e397  mov     rdi, [rsp+298h+var_258]
0x18000e39c  mov     [rsp+298h+hkey], rdi
0x18000e3a1  mov     rbx, rdi
0x18000e3a4  cmp     qword ptr [rsp+298h+var_250], r15
0x18000e3a9  jz      short loc_18000E3B5
0x18000e3ab  lea     rcx, [rsp+298h+var_250]
0x18000e3b0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e3b5  test    rbx, rbx
0x18000e3b8  jz      loc_18000E455
0x18000e3be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup> `wil::Feature<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetImpl(void)'::`2'::impl
0x18000e3c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::__private_IsEnabled(void)
0x18000e3ca  test    al, al
0x18000e3cc  jz      short loc_18000E400
0x18000e3ce  mov     eax, r12d
0x18000e3d1  lock cmpxchg [r14+24h], r12d
0x18000e3d7  jnz     short loc_18000E400
0x18000e3d9  test    rdi, rdi
0x18000e3dc  jz      short loc_18000E3E9
0x18000e3de  lea     rcx, [rsp+298h+hkey]
0x18000e3e3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e3e8  nop
0x18000e3e9  lea     rcx, [rsp+298h+var_188]; this
0x18000e3f1  call    ??1AppListBackupLauncher@AppListBackupLauncherTelemetry@@QEAA@XZ; AppListBackupLauncherTelemetry::AppListBackupLauncher::~AppListBackupLauncher(void)
0x18000e3f6  mov     eax, 800704C7h
0x18000e3fb  jmp     loc_18000E61D
0x18000e400  mov     [rsp+298h+var_258], r15
0x18000e405  mov     [rsp+298h+var_238], r15d
0x18000e40a  xorps   xmm0, xmm0
0x18000e40d  movdqu  [rsp+298h+var_230], xmm0
0x18000e413  mov     rax, [rdi]
0x18000e416  lea     rdx, [rsp+298h+var_258]
0x18000e41b  mov     rcx, rdi
0x18000e41e  mov     rax, [rax+30h]
0x18000e422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e427  test    eax, eax
0x18000e429  js      loc_18000E668
0x18000e42f  mov     rbx, [rsp+298h+var_258]
0x18000e434  mov     [rsp+298h+var_258], rbx
0x18000e439  lea     rcx, [rsp+298h+var_258]
0x18000e43e  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18000e443  nop
0x18000e444  test    rbx, rbx
0x18000e447  jz      short loc_18000E45A
0x18000e449  lea     rcx, [rsp+298h+var_258]
0x18000e44e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e453  jmp     short loc_18000E45A
0x18000e455  call    ??$NullFactory_Error@AEAY0CN@$$CBG@AppListBackupLauncherTelemetry@@SAXAEAY0CN@$$CBG@Z; AppListBackupLauncherTelemetry::NullFactory_Error<ushort const (&)[45]>(ushort const (&)[45])
0x18000e45a  cmp     word ptr cs:aWindowsudkSyst+68h, r15w; ""
0x18000e462  jnz     loc_18000E64A
0x18000e468  mov     [rsp+298h+var_1D8], r12d
0x18000e470  mov     [rsp+298h+var_1D4], esi
0x18000e477  mov     [rsp+298h+var_1C8], r13
0x18000e47f  lea     rax, [rsp+298h+var_1D8]
0x18000e487  mov     [rsp+298h+var_1E0], rax
0x18000e48f  cmp     word ptr cs:aComMicrosoftWi+5Ah, r15w; ""
0x18000e497  jnz     loc_18000E64A
0x18000e49d  mov     [rsp+298h+var_1B8], r12d
0x18000e4a5  mov     [rsp+298h+var_1B4], 2Dh ; '-'
0x18000e4b0  lea     rax, aComMicrosoftWi; "com.microsoft.windows.extension.applist"...
0x18000e4b7  mov     [rsp+298h+var_1A8], rax
0x18000e4bf  lea     rax, [rsp+298h+var_1B8]
0x18000e4c7  mov     [rsp+298h+var_1C0], rax
0x18000e4cf  lea     r8, [rsp+298h+var_1E0]
0x18000e4d7  lea     rdx, [rsp+298h+var_1C0]; struct winrt::param::hstring *
0x18000e4df  lea     rcx, [rsp+298h+Data]; struct winrt::param::hstring *
0x18000e4e4  call    ?GetFactory@ExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@0@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(winrt::param::hstring const &,winrt::param::hstring const &)
0x18000e4e9  mov     rcx, [rax]
0x18000e4ec  test    rcx, rcx
0x18000e4ef  jnz     short loc_18000E4F9
0x18000e4f1  mov     rbx, r15
0x18000e4f4  mov     rsi, r15
0x18000e4f7  jmp     short loc_18000E51D
0x18000e4f9  mov     [rsp+298h+var_258], r15
0x18000e4fe  mov     rax, [rcx]
0x18000e501  lea     r8, [rsp+298h+var_258]
0x18000e506  lea     rdx, ??$guid_v@UIAppListBackupExtensionStatics5@UserProfile@System@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::System::UserProfile::IAppListBackupExtensionStatics5>
0x18000e50d  mov     rax, [rax]
0x18000e510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e515  mov     rbx, [rsp+298h+var_258]
0x18000e51a  mov     rsi, rbx
0x18000e51d  mov     qword ptr [rsp+298h+var_250], rbx
0x18000e522  cmp     [rsp+298h+Data], r15
0x18000e527  jz      short loc_18000E533
0x18000e529  lea     rcx, [rsp+298h+Data]
0x18000e52e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e533  test    rsi, rsi
0x18000e536  jz      loc_18000E5D8
0x18000e53c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup> `wil::Feature<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::GetImpl(void)'::`2'::impl
0x18000e543  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OptimizationsInApplistBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptimizationsInApplistBackup>::__private_IsEnabled(void)
0x18000e548  test    al, al
0x18000e54a  jz      short loc_18000E58E
0x18000e54c  mov     eax, r12d
0x18000e54f  lock cmpxchg [r14+24h], r12d
0x18000e555  jnz     short loc_18000E58E
0x18000e557  test    rbx, rbx
0x18000e55a  jz      short loc_18000E567
0x18000e55c  lea     rcx, [rsp+298h+var_250]
0x18000e561  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e566  nop
0x18000e567  test    rdi, rdi
0x18000e56a  jz      short loc_18000E577
0x18000e56c  lea     rcx, [rsp+298h+hkey]
0x18000e571  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e576  nop
0x18000e577  lea     rcx, [rsp+298h+var_188]; this
0x18000e57f  call    ??1AppListBackupLauncher@AppListBackupLauncherTelemetry@@QEAA@XZ; AppListBackupLauncherTelemetry::AppListBackupLauncher::~AppListBackupLauncher(void)
0x18000e584  mov     eax, 800704C7h
0x18000e589  jmp     loc_18000E61D
0x18000e58e  mov     [rsp+298h+var_258], r15
0x18000e593  mov     [rsp+298h+var_238], r15d
0x18000e598  xorps   xmm0, xmm0
0x18000e59b  movdqu  [rsp+298h+var_230], xmm0
0x18000e5a1  mov     rax, [rbx]
0x18000e5a4  lea     rdx, [rsp+298h+var_258]
  ... truncated ...
```
