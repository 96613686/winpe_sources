# _lambda_7afef5c17c8d8b23c4e30a183fcce678_::operator()

- ea: `0x180029474`
- end: `0x180029cdc`
- name: `_lambda_7afef5c17c8d8b23c4e30a183fcce678_::operator()`
- size: `2152`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009e20`

## callees

- `0x180007c78`
- `0x1800092f0`
- `0x18000a1f0`
- `0x18000a230`
- `0x18000af10`
- `0x18000bb10`
- `0x18000be90`
- `0x18000c4c0`
- `0x18000c790`
- `0x18000d3b0`
- `0x18000e900`
- `0x18000f8b0`
- `0x180010860`
- `0x180010890`
- `0x180013714`
- `0x180018150`
- `0x180018280`
- `0x18001866c`
- `0x1800198d4`
- `0x18001aba8`
- `0x18001ae74`
- `0x18002719c`
- `0x1800272e0`
- `0x180029474`
- `0x18002e37c`
- `0x1800334c8`
- `0x180033de0`
- `0x18003420c`
- `0x180038dac`
- `0x180038e3c`
- `0x180038f68`
- `0x180042950`
- `0x180043010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029bd7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029bd7`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180029775`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180029775`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029c47`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029c47`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180029599`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180029599`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029654`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029654`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002961c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002961c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800295d7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800295d7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800296a4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800296a4`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x180029aef`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x180029aef`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180029a80`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180029a80`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x1800298e7`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x1800298e7`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x180029948`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x180029948`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x180029b38`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x180029b38`

## string_xrefs

- `0x180029546`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029579`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800295bd`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800295fb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002966b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800296bd`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002971d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800297b3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029825`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029911`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002998f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800299d4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029aaa`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029bad`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029bee`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall lambda_7afef5c17c8d8b23c4e30a183fcce678_::operator()(__int64 *a1)
{
  _DWORD *v2; // rax
  void **v3; // rax
  unsigned int ClientInformation; // edi
  int LastError; // eax
  HANDLE *v6; // r14
  int v7; // eax
  int PackageProperties; // edi
  HANDLE *v9; // rsi
  DWORD ProcessId; // eax
  const char *v11; // r9
  DWORD *v12; // r12
  __int64 v13; // rdx
  int v14; // ebx
  HANDLE *v15; // rdi
  DWORD ProcessIdOfThread; // eax
  DWORD ThreadId; // r13d
  const char *v18; // r9
  int v19; // eax
  WCHAR *v20; // r15
  unsigned int PackageFullNameFromToken; // eax
  __int64 v22; // rdx
  HANDLE v23; // rcx
  HANDLE v24; // rdi
  void *v25; // r14
  int UserContextAndUnmodifiedLogonTokenOfTokenUser; // eax
  int v27; // esi
  bool v28; // si
  __int64 v29; // rdx
  int v30; // edi
  const unsigned __int16 **v31; // rsi
  int *v32; // rax
  __int64 v33; // r9
  unsigned __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // r9
  __int64 v38; // rdx
  _QWORD *v39; // rax
  unsigned int v40; // ecx
  int v41; // eax
  __int64 v42; // r9
  unsigned __int64 v43; // r9
  __int64 v44; // rdx
  int ProcessDesktopAppXActivation; // eax
  unsigned int PackageStatus; // eax
  __int64 v47; // rbx
  int v48; // eax
  const char *v49; // r9
  __int64 v50; // rbx
  __int64 (__fastcall *v51)(__int64, _QWORD); // rdi
  __int64 v52; // rax
  int v53; // eax
  unsigned int v54; // r8d
  const unsigned __int16 *v55; // rax
  unsigned int v57; // [rsp+28h] [rbp-E0h]
  unsigned int v58; // [rsp+28h] [rbp-E0h]
  bool v59[8]; // [rsp+58h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A8h] BYREF
  void *v61; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v62; // [rsp+70h] [rbp-98h] BYREF
  __int64 v63; // [rsp+78h] [rbp-90h] BYREF
  __int64 v64; // [rsp+80h] [rbp-88h] BYREF
  HANDLE v65; // [rsp+88h] [rbp-80h] BYREF
  int v66; // [rsp+90h] [rbp-78h] BYREF
  UINT32 packageFullNameLength; // [rsp+94h] [rbp-74h] BYREF
  __int64 *v68; // [rsp+98h] [rbp-70h] BYREF
  void *v69; // [rsp+A0h] [rbp-68h] BYREF
  DWORD v70; // [rsp+A8h] [rbp-60h]
  DWORD v71; // [rsp+ACh] [rbp-5Ch]
  __int64 v72; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 v73; // [rsp+B8h] [rbp-50h] BYREF
  const unsigned __int16 **v74; // [rsp+C0h] [rbp-48h]
  _QWORD v75[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v76; // [rsp+E8h] [rbp-20h]
  _QWORD v77[2]; // [rsp+F0h] [rbp-18h] BYREF
  DWORD v78; // [rsp+100h] [rbp-8h]
  DWORD v79; // [rsp+104h] [rbp-4h]
  _QWORD v80[4]; // [rsp+108h] [rbp+0h] BYREF
  int v81; // [rsp+128h] [rbp+20h]
  int v82; // [rsp+12Ch] [rbp+24h]
  HSTRING_HEADER hstringHeader; // [rsp+130h] [rbp+28h] BYREF
  __int64 v84; // [rsp+148h] [rbp+40h]
  char v85[40]; // [rsp+150h] [rbp+48h] BYREF
  _QWORD v86[42]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+300h] [rbp+1F8h]

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
  v86[0] = &LUATelemetry::FinishPackageActivationActivity::`vftable';
  LUATelemetry::FinishPackageActivationActivity::StartActivity((LUATelemetry::FinishPackageActivationActivity *)v86);
  v63 = *a1;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v2 = *(_DWORD **)v63;
  v69 = 0;
  LOBYTE(v70) = 1;
  *v2 = 0;
  hstringHeader.Reserved.Reserved1 = &v65;
  v68 = &v72;
  v3 = (void **)a1[1];
  v72 = 0;
  v65 = 0;
  ClientInformation = AiGetClientInformation(*v3, &v69, (void **)&hstringHeader.Reserved.Reserved2[8], 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v68);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
  if ( !ClientInformation )
  {
    v6 = (HANDLE *)a1[2];
    v7 = AccessCheckIncomingToken(v65, *v6);
    PackageProperties = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B34,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v7,
        v57);
LABEL_85:
      v14 = PackageProperties;
      goto LABEL_86;
    }
    v9 = (HANDLE *)a1[4];
    ProcessId = GetProcessId(*v9);
    v12 = (DWORD *)a1[3];
    *v12 = ProcessId;
    if ( !ProcessId )
    {
      v13 = 6967;
LABEL_7:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v13,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v11);
      goto LABEL_8;
    }
    v15 = (HANDLE *)a1[5];
    ProcessIdOfThread = GetProcessIdOfThread(*v15);
    if ( !ProcessIdOfThread )
    {
      v13 = 6971;
      goto LABEL_7;
    }
    if ( *v12 != ProcessIdOfThread )
    {
      v14 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B3C,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)0x80070057LL,
        v57);
      goto LABEL_86;
    }
    ThreadId = GetThreadId(*v15);
    if ( !ThreadId )
    {
      v13 = 6975;
      goto LABEL_7;
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    if ( !OpenProcessToken(*v9, 8u, &TokenHandle) )
    {
      v19 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1B42,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              v18);
LABEL_17:
      v14 = v19;
LABEL_18:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_86;
    }
    v20 = (WCHAR *)a1[6];
    packageFullNameLength = 128;
    PackageFullNameFromToken = GetPackageFullNameFromToken(TokenHandle, &packageFullNameLength, v20);
    if ( PackageFullNameFromToken )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1B46,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)PackageFullNameFromToken,
              v57);
      goto LABEL_17;
    }
    v59[0] = 0;
    v59[1] = 0;
    PackageProperties = GetPackageProperties(v20, 0, v59, 0, 0, 0, 0, 0, &v59[1]);
    if ( PackageProperties < 0 )
    {
      v22 = 6986;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)PackageProperties,
        v58);
LABEL_84:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_85;
    }
    v23 = *v9;
    v74 = (const unsigned __int16 **)a1[7];
    PackageProperties = GetExecutablePathFromProcessHandle(v23);
    if ( PackageProperties < 0 )
    {
      v22 = 6989;
      goto LABEL_23;
    }
    v24 = v65;
    if ( *v6 )
      v24 = *v6;
    v61 = 0;
    v25 = v24;
    if ( IsTokenIntegrityLevelLessThanMedium(v24) || IsTokenRestricted(v24) )
    {
      v73 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v61,
        0);
      UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v24, &v73, &v61);
      v27 = UserContextAndUnmodifiedLogonTokenOfTokenUser;
      if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B59,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
          v58);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v61);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        v14 = v27;
        goto LABEL_86;
      }
      v25 = v61;
    }
    v28 = v59[0];
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl'::`2'::impl)
      && !v28 )
    {
      PackageProperties = IsWin32alacarteWithDisabledProcessTreeBreakawayToken(v24, v59);
      if ( PackageProperties < 0 )
      {
        v29 = 7010;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackageProperties,
          v58);
LABEL_83:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v61);
        goto LABEL_84;
      }
      v28 = v59[0];
    }
    LODWORD(v62) = 0;
    PackageProperties = AppModelPolicy_GetPolicy(TokenHandle, 17, &v62);
    if ( PackageProperties < 0 )
    {
      v29 = 7015;
      goto LABEL_37;
    }
    v30 = (int)v62;
    if ( (_DWORD)v62 == 1114113 )
    {
      PackageProperties = 0;
      *(_DWORD *)a1[8] = 1;
      if ( !*(_QWORD *)a1[9] || !*(_QWORD *)a1[10] )
      {
        v14 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B6B,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)0x80070057LL,
          v58);
        goto LABEL_53;
      }
      v31 = (const unsigned __int16 **)a1[7];
      v81 = 0;
      v80[1] = v65;
      v80[0] = v25;
      v80[2] = v20;
      v80[3] = *v31;
      v32 = (int *)a1[11];
      v81 = 4;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v82 = *v32;
      hstringHeader.Reserved.Reserved1 = &v62;
      v62 = 0;
      v14 = PrepareAppXActivation(v80, &hstringHeader.Reserved.Reserved2[8]);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&hstringHeader);
      if ( v14 < 0 )
      {
        v34 = (unsigned int)v14;
        v35 = 7030;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)v34,
          v58);
        wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v62);
LABEL_53:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v61);
        goto LABEL_18;
      }
      v68 = 0;
      v69 = 0;
      v70 = *v12;
      v71 = ThreadId;
      v36 = PostCreateProcessAppXActivation(v25, v62, &v68, v33);
      v14 = v36;
      if ( v36 < 0 )
      {
        v34 = (unsigned int)v36;
        v35 = 7035;
        goto LABEL_46;
      }
      if ( v62[2] )
        **(_DWORD **)v63 |= 1u;
      wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v62);
LABEL_71:
      v66 = 0;
      PackageStatus = GetPackageStatus(v20, &v66);
      if ( PackageStatus )
      {
        v37 = PackageStatus;
        v38 = 7089;
        goto LABEL_56;
      }
      if ( (v66 & 0x20000) != 0 )
      {
        v63 = 0;
        v84 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Management.Deployment.Internal.PackageManagerInternal",
          0x3Eu,
          0x3Du);
        v47 = v84;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
        v48 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(
                v47,
                &v63);
        v14 = v48;
        if ( v48 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BB6,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)(unsigned int)v48,
            v58);
LABEL_76:
          v84 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
          goto LABEL_53;
        }
        if ( !ImpersonateLoggedOnUser(v25) )
        {
          v14 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1BB8,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v49);
          goto LABEL_76;
        }
        v50 = v63;
        v51 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63 + 376LL);
        v52 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                (Microsoft::WRL::Wrappers::HStringReference *)v85,
                (unsigned __int16 (*)[128])v20);
        v53 = v51(v50, *(_QWORD *)(v52 + 24));
        PackageProperties = 0;
        if ( v53 < 0 )
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x1BBE, v54, (const char *)(unsigned int)v53, v58);
        RevertToSelf();
        v84 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
      }
      v55 = AipJustFileName(*v31);
      LUATelemetry::FinishPackageActivationActivity::Stop(
        (LUATelemetry::FinishPackageActivationActivity *)v86,
        v55,
        v20);
      goto LABEL_83;
    }
    if ( (unsigned int)((_DWORD)v62 - 1114114) > 1 )
    {
      v37 = 50;
      v38 = 7085;
LABEL_56:
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v38,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)v37,
              v58);
      goto LABEL_53;
    }
    v62 = (_DWORD *)a1[8];
    *v62 = 1;
    v76 = 0;
    v75[1] = v65;
    v39 = (_QWORD *)a1[7];
    v75[0] = v25;
    v75[2] = v20;
    v75[3] = *v39;
    v76 = v28 | 6u;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl'::`2'::impl)
      || v28 )
    {
      v40 = v76;
    }
    else
    {
      v40 = v59[1] | (unsigned int)v76;
    }
    v41 = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    if ( v30 == 1114115 )
      v41 = 8;
    PackageProperties = 0;
    v64 = 0;
    LODWORD(v76) = v41 | v40;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)&v64;
    v14 = PrepareDesktopAppXActivation(v75, &hstringHeader.Reserved.Reserved2[8]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&hstringHeader);
    if ( v14 >= 0 )
    {
      *v62 = 6;
      v77[0] = 0;
      v77[1] = 0;
      v78 = *v12;
      v79 = ThreadId;
      ProcessDesktopAppXActivation = PostCreateProcessDesktopAppXActivation(v25, v64, v77, v42);
      v14 = ProcessDesktopAppXActivation;
      if ( ProcessDesktopAppXActivation >= 0 )
      {
        if ( *(_DWORD *)(v64 + 16) )
          **(_DWORD **)v63 |= 1u;
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v64);
        v31 = v74;
        goto LABEL_71;
      }
      v43 = (unsigned int)ProcessDesktopAppXActivation;
      v44 = 7077;
    }
    else
    {
      v43 = (unsigned int)v14;
      v44 = 7071;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)v43,
      v58);
    wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v64);
    goto LABEL_53;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1B32,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)ClientInformation,
                v57);
LABEL_8:
  v14 = LastError;
LABEL_86:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v65);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v72);
  LUATelemetry::FinishPackageActivationActivity::~FinishPackageActivationActivity((LUATelemetry::FinishPackageActivationActivity *)v86);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180029474  mov     rax, rsp
0x180029477  mov     [rax+10h], rbx
0x18002947b  mov     [rax+18h], rsi
0x18002947f  mov     [rax+20h], rdi
0x180029483  push    rbp
0x180029484  push    r12
0x180029486  push    r13
0x180029488  push    r14
0x18002948a  push    r15
0x18002948c  lea     rbp, [rax-1F8h]
0x180029493  sub     rsp, 2D0h
0x18002949a  mov     rax, cs:__security_cookie
0x1800294a1  xor     rax, rsp
0x1800294a4  mov     [rbp+1F0h+var_30], rax
0x1800294ab  mov     rbx, rcx
0x1800294ae  lea     rdx, aFinishpackagea; "FinishPackageActivationActivity"
0x1800294b5  lea     rcx, [rbp+1F0h+var_180]; struct wil::details::IFailureCallback *
0x1800294b9  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800294be  lea     rax, ??_7FinishPackageActivationActivity@LUATelemetry@@6B@; const LUATelemetry::FinishPackageActivationActivity::`vftable'
0x1800294c5  lea     rcx, [rbp+1F0h+var_180]; this
0x1800294c9  mov     [rbp+1F0h+var_180], rax
0x1800294cd  call    ?StartActivity@FinishPackageActivationActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::FinishPackageActivationActivity::StartActivity(void)
0x1800294d2  mov     rax, [rbx]
0x1800294d5  lea     r8, [rbp+1F0h+hstringHeader.Reserved+8]; void **
0x1800294d9  xor     r15d, r15d
0x1800294dc  mov     [rsp+2F0h+var_280], rax
0x1800294e1  xor     r9d, r9d; unsigned int *
0x1800294e4  mov     qword ptr [rbp+1F0h+hstringHeader.Reserved+8], r15
0x1800294e8  lea     rdx, [rbp+1F0h+var_258]; void **
0x1800294ec  mov     byte ptr [rbp+1F0h+hstringHeader.Reserved+10h], 1
0x1800294f0  mov     rax, [rax]
0x1800294f3  mov     [rbp+1F0h+var_258], r15
0x1800294f7  mov     byte ptr [rbp+1F0h+var_250], 1
0x1800294fb  mov     [rsp+2F0h+var_2D0], r15; unsigned int
0x180029500  mov     [rax], r15d
0x180029503  lea     rax, [rbp+1F0h+var_270]
0x180029507  mov     qword ptr [rbp+1F0h+hstringHeader.Reserved], rax
0x18002950b  lea     rax, [rbp+1F0h+var_248]
0x18002950f  mov     [rbp+1F0h+var_260], rax
0x180029513  mov     rax, [rbx+8]
0x180029517  mov     [rbp+1F0h+var_248], r15
0x18002951b  mov     [rbp+1F0h+var_270], r15
0x18002951f  mov     rcx, [rax]; void *
0x180029522  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180029527  lea     rcx, [rbp+1F0h+var_260]
0x18002952b  mov     edi, eax
0x18002952d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180029532  lea     rcx, [rbp+1F0h+hstringHeader]
0x180029536  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002953b  test    edi, edi
0x18002953d  jz      short loc_18002955C
0x18002953f  mov     rcx, [rbp+1F8h]; this
0x180029546  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002954d  mov     r9d, edi; char *
0x180029550  mov     edx, 1B32h; void *
0x180029555  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002955a  jmp     short loc_1800295C9
0x18002955c  mov     r14, [rbx+10h]
0x180029560  mov     rcx, [rbp+1F0h+var_270]; TokenHandle
0x180029564  mov     rdx, [r14]; HANDLE
0x180029567  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x18002956c  mov     edi, eax
0x18002956e  test    eax, eax
0x180029570  jns     short loc_180029592
0x180029572  mov     rcx, [rbp+1F8h]; this
0x180029579  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029580  mov     r9d, eax; char *
0x180029583  mov     edx, 1B34h; void *
0x180029588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002958d  jmp     loc_180029C8C
0x180029592  mov     rsi, [rbx+20h]
0x180029596  mov     rcx, [rsi]; Process
0x180029599  call    cs:__imp_GetProcessId
0x1800295a0  nop     dword ptr [rax+rax+00h]
0x1800295a5  mov     r12, [rbx+18h]
0x1800295a9  mov     [r12], eax
0x1800295ad  test    eax, eax
0x1800295af  jnz     short loc_1800295D0
0x1800295b1  mov     edx, 1B37h; void *
0x1800295b6  mov     rcx, [rbp+1F8h]; this
0x1800295bd  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800295c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800295c9  mov     ebx, eax
0x1800295cb  jmp     loc_180029C8E
0x1800295d0  mov     rdi, [rbx+28h]
0x1800295d4  mov     rcx, [rdi]; Thread
0x1800295d7  call    cs:__imp_GetProcessIdOfThread
0x1800295de  nop     dword ptr [rax+rax+00h]
0x1800295e3  test    eax, eax
0x1800295e5  jnz     short loc_1800295EE
0x1800295e7  mov     edx, 1B3Bh
0x1800295ec  jmp     short loc_1800295B6
0x1800295ee  cmp     [r12], eax
0x1800295f2  jz      short loc_180029619
0x1800295f4  mov     rcx, [rbp+1F8h]; this
0x1800295fb  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029602  mov     ebx, 80070057h
0x180029607  mov     edx, 1B3Ch; void *
0x18002960c  mov     r9d, ebx; char *
0x18002960f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029614  jmp     loc_180029C8E
0x180029619  mov     rcx, [rdi]; Thread
0x18002961c  call    cs:__imp_GetThreadId
0x180029623  nop     dword ptr [rax+rax+00h]
0x180029628  mov     r13d, eax
0x18002962b  test    eax, eax
0x18002962d  jnz     short loc_180029636
0x18002962f  mov     edx, 1B3Fh
0x180029634  jmp     short loc_1800295B6
0x180029636  xor     edx, edx
0x180029638  mov     [rsp+2F0h+TokenHandle], r15
0x18002963d  lea     rcx, [rsp+2F0h+TokenHandle]
0x180029642  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180029647  mov     rcx, [rsi]; ProcessHandle
0x18002964a  lea     r8, [rsp+2F0h+TokenHandle]; TokenHandle
0x18002964f  mov     edx, 8; DesiredAccess
0x180029654  call    cs:__imp_OpenProcessToken
0x18002965b  nop     dword ptr [rax+rax+00h]
0x180029660  test    eax, eax
0x180029662  jnz     short loc_18002968D
0x180029664  mov     rcx, [rbp+1F8h]; this
0x18002966b  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029672  mov     edx, 1B42h; void *
0x180029677  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002967c  mov     ebx, eax
0x18002967e  lea     rcx, [rsp+2F0h+TokenHandle]
0x180029683  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029688  jmp     loc_180029C8E
0x18002968d  mov     r15, [rbx+30h]
0x180029691  lea     rdx, [rbp+1F0h+packageFullNameLength]; packageFullNameLength
0x180029695  mov     rcx, [rsp+2F0h+TokenHandle]; token
0x18002969a  mov     r8, r15; packageFullName
0x18002969d  mov     [rbp+1F0h+packageFullNameLength], 80h
0x1800296a4  call    cs:__imp_GetPackageFullNameFromToken
0x1800296ab  nop     dword ptr [rax+rax+00h]
0x1800296b0  xor     ecx, ecx
0x1800296b2  test    eax, eax
0x1800296b4  jz      short loc_1800296D3
0x1800296b6  mov     rcx, [rbp+1F8h]; this
0x1800296bd  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800296c4  mov     r9d, eax; char *
0x1800296c7  mov     edx, 1B46h; void *
0x1800296cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800296d1  jmp     short loc_18002967C
0x1800296d3  lea     rax, [rsp+2F0h+var_2A0+1]
0x1800296d8  mov     [rsp+2F0h+var_2A0], cl
0x1800296dc  mov     [rsp+2F0h+var_2B0], rax; bool *
0x1800296e1  lea     r8, [rsp+2F0h+var_2A0]; bool *
0x1800296e6  mov     [rsp+2F0h+var_2B8], rcx; bool *
0x1800296eb  xor     r9d, r9d; bool *
0x1800296ee  mov     [rsp+2F0h+var_2C0], rcx; bool *
0x1800296f3  xor     edx, edx; bool *
0x1800296f5  mov     [rsp+2F0h+var_2C8], rcx; bool *
0x1800296fa  mov     [rsp+2F0h+var_2D0], rcx; int
0x1800296ff  mov     [rsp+2F0h+var_2A0+1], cl
0x180029703  mov     rcx, r15; unsigned __int16 *
0x180029706  call    ?GetPackageProperties@@YAJPEBGPEA_N1111111@Z; GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)
0x18002970b  mov     edi, eax
0x18002970d  test    eax, eax
0x18002970f  jns     short loc_180029731
0x180029711  mov     edx, 1B4Ah; void *
0x180029716  mov     rcx, [rbp+1F8h]; this
0x18002971d  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029724  mov     r9d, edi; char *
0x180029727  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002972c  jmp     loc_180029C82
0x180029731  mov     rax, [rbx+38h]
0x180029735  mov     rcx, [rsi]; hProcess
0x180029738  mov     rdx, rax
0x18002973b  mov     [rbp+1F0h+var_238], rax
0x18002973f  call    ?GetExecutablePathFromProcessHandle@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetExecutablePathFromProcessHandle(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180029744  xor     esi, esi
0x180029746  mov     edi, eax
0x180029748  test    eax, eax
0x18002974a  jns     short loc_180029753
0x18002974c  mov     edx, 1B4Dh
0x180029751  jmp     short loc_180029716
0x180029753  cmp     [r14], rsi
0x180029756  mov     rdi, [rbp+1F0h+var_270]
0x18002975a  cmovnz  rdi, [r14]
0x18002975e  mov     rcx, rdi; void *
0x180029761  mov     [rsp+2F0h+var_290], rsi
0x180029766  mov     r14, rdi
0x180029769  call    ?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z; IsTokenIntegrityLevelLessThanMedium(void *)
0x18002976e  test    al, al
0x180029770  jnz     short loc_180029785
0x180029772  mov     rcx, rdi; TokenHandle
0x180029775  call    cs:__imp_IsTokenRestricted
0x18002977c  nop     dword ptr [rax+rax+00h]
0x180029781  test    eax, eax
0x180029783  jz      short loc_1800297E7
0x180029785  xor     edx, edx
0x180029787  mov     [rbp+1F0h+var_240], rsi
0x18002978b  lea     rcx, [rsp+2F0h+var_290]
0x180029790  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180029795  lea     r8, [rsp+2F0h+var_290]; void **
0x18002979a  mov     rcx, rdi; void *
0x18002979d  lea     rdx, [rbp+1F0h+var_240]; unsigned __int64 *
0x1800297a1  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x1800297a6  mov     esi, eax
0x1800297a8  test    eax, eax
0x1800297aa  jns     short loc_1800297E2
0x1800297ac  mov     rcx, [rbp+1F8h]; this
0x1800297b3  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800297ba  mov     r9d, eax; char *
0x1800297bd  mov     edx, 1B59h; void *
0x1800297c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800297c7  lea     rcx, [rsp+2F0h+var_290]
0x1800297cc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800297d1  lea     rcx, [rsp+2F0h+TokenHandle]
0x1800297d6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800297db  mov     ebx, esi
0x1800297dd  jmp     loc_180029C8E
0x1800297e2  mov     r14, [rsp+2F0h+var_290]
0x1800297e7  mov     sil, [rsp+2F0h+var_2A0]
0x1800297ec  mov     [rsp+2F0h+var_2A0], sil
0x1800297f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte> `wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl(void)'::`2'::impl
0x1800297f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(void)
0x1800297fd  test    al, al
0x1800297ff  jz      short loc_18002983E
0x180029801  test    sil, sil
0x180029804  jnz     short loc_18002983E
0x180029806  lea     rdx, [rsp+2F0h+var_2A0]; bool *
0x18002980b  mov     rcx, rdi; void *
0x18002980e  call    ?IsWin32alacarteWithDisabledProcessTreeBreakawayToken@@YAJPEAXAEA_N@Z; IsWin32alacarteWithDisabledProcessTreeBreakawayToken(void *,bool &)
0x180029813  mov     edi, eax
0x180029815  test    eax, eax
0x180029817  jns     short loc_180029839
0x180029819  mov     edx, 1B62h; void *
0x18002981e  mov     rcx, [rbp+1F8h]; this
0x180029825  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002982c  mov     r9d, edi; char *
0x18002982f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029834  jmp     loc_180029C78
0x180029839  mov     sil, [rsp+2F0h+var_2A0]
0x18002983e  mov     rcx, [rsp+2F0h+TokenHandle]
0x180029843  lea     r8, [rsp+2F0h+var_288]
0x180029848  and     dword ptr [rsp+2F0h+var_288], 0
0x18002984d  mov     edx, 11h
0x180029852  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x180029857  mov     edi, eax
0x180029859  test    eax, eax
0x18002985b  jns     short loc_180029864
0x18002985d  mov     edx, 1B67h
0x180029862  jmp     short loc_18002981E
0x180029864  mov     edi, dword ptr [rsp+2F0h+var_288]
0x180029868  cmp     edi, 110001h
0x18002986e  jnz     loc_1800299B7
0x180029874  mov     rax, [rbx+40h]
0x180029878  xor     edi, edi
0x18002987a  mov     dword ptr [rax], 1
0x180029880  mov     rax, [rbx+48h]
0x180029884  cmp     [rax], rdi
0x180029887  jz      loc_180029988
0x18002988d  mov     rax, [rbx+50h]
0x180029891  cmp     [rax], rdi
0x180029894  jz      loc_180029988
0x18002989a  mov     rax, [rbp+1F0h+var_270]
0x18002989e  lea     rdx, [rbp+1F0h+hstringHeader.Reserved+8]
0x1800298a2  mov     rsi, [rbx+38h]
0x1800298a6  mov     ecx, edi
0x1800298a8  mov     [rbp+1F0h+var_1D0], ecx
0x1800298ab  or      ecx, 4
0x1800298ae  mov     [rbp+1F0h+var_1E8], rax
0x1800298b2  mov     [rbp+1F0h+var_1F0], r14
0x1800298b6  mov     [rbp+1F0h+var_1E0], r15
0x1800298ba  mov     rax, [rsi]
0x1800298bd  mov     [rbp+1F0h+var_1D8], rax
0x1800298c1  mov     rax, [rbx+58h]
0x1800298c5  mov     [rbp+1F0h+var_1D0], ecx
0x1800298c8  mov     qword ptr [rbp+1F0h+hstringHeader.Reserved+8], rdi
0x1800298cc  mov     byte ptr [rbp+1F0h+hstringHeader.Reserved+10h], 1
0x1800298d0  mov     ecx, [rax]
0x1800298d2  lea     rax, [rsp+2F0h+var_288]
0x1800298d7  mov     [rbp+1F0h+var_1CC], ecx
0x1800298da  lea     rcx, [rbp+1F0h+var_1F0]
0x1800298de  mov     qword ptr [rbp+1F0h+hstringHeader.Reserved], rax
0x1800298e2  mov     [rsp+2F0h+var_288], rdi
0x1800298e7  call    cs:__imp_PrepareAppXActivation
0x1800298ee  nop     dword ptr [rax+rax+00h]
0x1800298f3  lea     rcx, [rbp+1F0h+hstringHeader]
0x1800298f7  mov     ebx, eax
0x1800298f9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x1800298fe  test    ebx, ebx
0x180029900  jns     short loc_180029929
0x180029902  mov     r9d, ebx; char *
0x180029905  mov     edx, 1B76h; void *
0x18002990a  mov     rcx, [rbp+1F8h]; this
0x180029911  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002991d  lea     rcx, [rsp+2F0h+var_288]
0x180029922  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x180029927  jmp     short loc_1800299A8
0x180029929  mov     rdx, [rsp+2F0h+var_288]
0x18002992e  lea     r8, [rbp+1F0h+var_260]
0x180029932  mov     [rbp+1F0h+var_260], rdi
0x180029936  mov     rcx, r14
0x180029939  mov     [rbp+1F0h+var_258], rdi
0x18002993d  mov     eax, [r12]
0x180029941  mov     [rbp+1F0h+var_250], eax
  ... truncated ...
```
