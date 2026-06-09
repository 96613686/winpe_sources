# _lambda_97c28e8e79e727caaebeca243053c7e4_::operator()

- ea: `0x180029ce4`
- end: `0x18002a3de`
- name: `_lambda_97c28e8e79e727caaebeca243053c7e4_::operator()`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800326c0`

## callees

- `0x180007c78`
- `0x1800092f0`
- `0x18000a1f0`
- `0x18000a230`
- `0x18000bb10`
- `0x18000c4c0`
- `0x18000c790`
- `0x18000f8b0`
- `0x180010860`
- `0x180010890`
- `0x180012b9c`
- `0x180018150`
- `0x1800181cc`
- `0x180018280`
- `0x18001866c`
- `0x180018710`
- `0x180018824`
- `0x18001aba8`
- `0x18001ae74`
- `0x18001af74`
- `0x180029ce4`
- `0x18002a750`
- `0x18002e150`
- `0x1800334c8`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029e4b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002a186`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029e4b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002a186`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029ebc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029f6a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a2a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a2b3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a380`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029ebc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029f6a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a2a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a2b3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a380`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180029fdc`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180029fdc`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002a053`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002a053`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x180029f0b`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x180029f0b`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x180029e8f`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x180029f37`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x180029e8f`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x180029f37`

## string_xrefs

- `0x180029da2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029dda`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029e2e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029e62`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029ead`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a007`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a075`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a19d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a28c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a2e6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002a36c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180029d19`: `GetPackageActivationTokenForFilePath`

## pseudocode

```c
__int64 __fastcall lambda_97c28e8e79e727caaebeca243053c7e4_::operator()(__int64 a1)
{
  void **v2; // rax
  unsigned int ClientInformation; // ebx
  unsigned int LastError; // ebx
  HANDLE *v5; // rsi
  int v6; // eax
  HANDLE v7; // r14
  int UserContextAndUnmodifiedLogonTokenOfTokenUser; // eax
  const char *v9; // r9
  _QWORD *v10; // r15
  __int64 *v11; // rbx
  int PackagedAppInfoForFile; // esi
  __int64 v13; // rdx
  __int64 v14; // rdx
  _DWORD *v15; // r15
  __int64 *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  const unsigned __int16 *v19; // rcx
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r11
  int v23; // esi
  int BnoIsolationPrefixForRpc; // eax
  void *v25; // rdx
  _QWORD **v26; // rax
  __int64 v27; // rbx
  const unsigned __int16 *v28; // rax
  unsigned int v30; // [rsp+20h] [rbp-F0h]
  int v31; // [rsp+20h] [rbp-F0h]
  int v32; // [rsp+28h] [rbp-E8h]
  int v33; // [rsp+30h] [rbp-E0h]
  int v34; // [rsp+38h] [rbp-D8h]
  int v35; // [rsp+40h] [rbp-D0h]
  int v36; // [rsp+48h] [rbp-C8h]
  bool v37; // [rsp+90h] [rbp-80h] BYREF
  bool v38; // [rsp+91h] [rbp-7Fh] BYREF
  bool v39; // [rsp+92h] [rbp-7Eh] BYREF
  bool v40; // [rsp+93h] [rbp-7Dh] BYREF
  bool v41[4]; // [rsp+94h] [rbp-7Ch] BYREF
  HANDLE hToken; // [rsp+98h] [rbp-78h] BYREF
  bool v43; // [rsp+A0h] [rbp-70h] BYREF
  bool v44; // [rsp+A1h] [rbp-6Fh] BYREF
  bool v45; // [rsp+A2h] [rbp-6Eh] BYREF
  __int64 v46; // [rsp+A8h] [rbp-68h] BYREF
  void *v47; // [rsp+B0h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+B8h] [rbp-58h] BYREF
  HANDLE *p_TokenHandle; // [rsp+C0h] [rbp-50h] BYREF
  void *v50; // [rsp+C8h] [rbp-48h] BYREF
  char v51; // [rsp+D0h] [rbp-40h]
  int v52; // [rsp+D8h] [rbp-38h] BYREF
  unsigned int v53; // [rsp+DCh] [rbp-34h] BYREF
  __int64 v54; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int64 v55; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-20h] BYREF
  __int64 *v57; // [rsp+F8h] [rbp-18h] BYREF
  void *v58; // [rsp+100h] [rbp-10h] BYREF
  __int64 v59; // [rsp+108h] [rbp-8h]
  __int64 v60; // [rsp+110h] [rbp+0h]
  __int64 v61; // [rsp+118h] [rbp+8h]
  _QWORD v62[6]; // [rsp+120h] [rbp+10h] BYREF
  _QWORD v63[42]; // [rsp+150h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1C8h]

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v63);
  v63[0] = &LUATelemetry::GetPackageActivationTokenForFilePath::`vftable';
  LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity((LUATelemetry::GetPackageActivationTokenForFilePath *)v63);
  v51 = 1;
  v56 = 0;
  p_TokenHandle = &TokenHandle;
  TokenHandle = 0;
  v57 = &v56;
  v2 = *(void ***)a1;
  v50 = 0;
  v58 = 0;
  LOBYTE(v59) = 1;
  ClientInformation = AiGetClientInformation(*v2, &v58, &v50, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v57);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( !ClientInformation )
  {
    v5 = *(HANDLE **)(a1 + 8);
    v6 = AccessCheckIncomingToken(TokenHandle, *v5);
    LastError = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1600,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v6,
        v30);
      goto LABEL_52;
    }
    v7 = TokenHandle;
    if ( *v5 )
      v7 = *v5;
    v55 = 0;
    hToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hToken,
      0);
    UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v7, &v55, &hToken);
    LastError = UserContextAndUnmodifiedLogonTokenOfTokenUser;
    if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1609,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
        v30);
LABEL_51:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      goto LABEL_52;
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x160C,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v9);
      goto LABEL_51;
    }
    v10 = *(_QWORD **)(a1 + 16);
    v11 = *(__int64 **)(a1 + 24);
    PackagedAppInfoForFile = BasepGetPackagedAppInfoForFile(*v10, hToken, 0, v11);
    if ( PackagedAppInfoForFile < 0 )
    {
      v13 = 5647;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)PackagedAppInfoForFile,
        v30);
      RevertToSelf();
LABEL_14:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      LastError = PackagedAppInfoForFile;
      goto LABEL_52;
    }
    if ( !*v11 || !*(_BYTE *)*v11 )
    {
      v14 = 5648;
      goto LABEL_50;
    }
    v52 = 0;
    PackagedAppInfoForFile = RegisterAppXPackageIfNecessary2(v55, *v11 + 2, 0, 0, &v52);
    if ( PackagedAppInfoForFile < 0 )
    {
      v13 = 5651;
      goto LABEL_13;
    }
    if ( v52 )
    {
      PackagedAppInfoForFile = BasepGetPackagedAppInfoForFile(*v10, hToken, 0, v11);
      if ( PackagedAppInfoForFile < 0 )
      {
        v13 = 5656;
        goto LABEL_13;
      }
      if ( !*v11 || !*(_BYTE *)*v11 )
      {
        v14 = 5657;
LABEL_50:
        LastError = -2147024894;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)0x80070002LL,
          v30);
        RevertToSelf();
        goto LABEL_51;
      }
    }
    RevertToSelf();
    v15 = *(_DWORD **)(a1 + 32);
    v16 = *(__int64 **)(a1 + 16);
    v50 = 0;
    v51 = 1;
    *v15 = 1;
    v46 = 0;
    v17 = *v11 + 262;
    if ( *(_DWORD *)(*v11 + 548) == 4 )
    {
      v57 = (__int64 *)hToken;
      v58 = TokenHandle;
      v61 = 0;
      v59 = v17;
      v60 = *v16;
      v61 = 2;
      p_TokenHandle = (HANDLE *)&v46;
      PackagedAppInfoForFile = PrepareDesktopAppXActivation(&v57, &v50);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( PackagedAppInfoForFile < 0 )
      {
        v18 = 5674;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackagedAppInfoForFile,
          v30);
LABEL_29:
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v46);
        goto LABEL_14;
      }
    }
    else
    {
      v62[0] = hToken;
      v62[1] = TokenHandle;
      v62[2] = v17;
      v62[4] = 0;
      v62[3] = *v16;
      p_TokenHandle = (HANDLE *)&v54;
      v54 = 0;
      PackagedAppInfoForFile = PrepareAppXActivation(v62, &v50);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( PackagedAppInfoForFile < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1635,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackagedAppInfoForFile,
          v30);
        wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v54);
        goto LABEL_29;
      }
      wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v54);
    }
    *v15 = 4;
    v19 = (const unsigned __int16 *)(*v11 + 262);
    v41[0] = 0;
    v40 = 0;
    v39 = 0;
    v38 = 0;
    v37 = 0;
    PackagedAppInfoForFile = GetPackageProperties(v19, v41, 0, &v40, &v39, &v38, 0, &v37, 0);
    if ( PackagedAppInfoForFile >= 0 )
    {
      v53 = 0;
      v41[1] = 0;
      v45 = 0;
      v44 = 0;
      v43 = 0;
      v41[2] = 0;
      PackagedAppInfoForFile = GetAppModelIdentityActivationProperties(
                                 hToken,
                                 (const unsigned __int16 *)(*v11 + 2),
                                 *(const unsigned __int16 **)(*v11 + 536),
                                 0,
                                 (enum AppModel::RuntimeBehavior *)&v53,
                                 &v41[1],
                                 &v45,
                                 &v44,
                                 &v43,
                                 &v41[2]);
      if ( PackagedAppInfoForFile >= 0 )
      {
        v47 = 0;
        if ( ImpersonateLoggedOnUser(v7) )
        {
          v50 = 0;
          p_TokenHandle = &v47;
          v51 = 1;
          if ( v46 )
            v22 = *(_QWORD *)(v46 + 56);
          else
            v22 = 0;
          LOBYTE(v21) = *(_DWORD *)(*v11 + 548) == 3;
          LOBYTE(v36) = v53 == 0;
          LOBYTE(v20) = v41[1];
          LOBYTE(v35) = 0;
          LOBYTE(v34) = v38;
          LOBYTE(v33) = v39;
          LOBYTE(v32) = v40;
          LOBYTE(v30) = v41[0];
          v23 = AdjustActivationToken(
                  v7,
                  v53,
                  v20,
                  v21,
                  v30,
                  v32,
                  v33,
                  v34,
                  v35,
                  v36,
                  v37,
                  0,
                  *v11 + 262,
                  *v11 + 2,
                  0,
                  0,
                  v22,
                  &v50);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v23 >= 0 )
          {
            RevertToSelf();
            if ( !v41[2]
              || (BnoIsolationPrefixForRpc = CreateBnoIsolationPrefixForRpc(
                                               v47,
                                               (unsigned __int16 **)(**(_QWORD **)(a1 + 40) + 8LL)),
                  PackagedAppInfoForFile = BnoIsolationPrefixForRpc,
                  BnoIsolationPrefixForRpc >= 0) )
            {
              v25 = v47;
              v26 = *(_QWORD ***)(a1 + 40);
              v47 = 0;
              **v26 = v25;
              v27 = *v11;
              v28 = AipJustFileName(**(const unsigned __int16 ***)(a1 + 16));
              LUATelemetry::GetPackageActivationTokenForFilePath::Stop(
                (LUATelemetry::GetPackageActivationTokenForFilePath *)v63,
                v28,
                (const unsigned __int16 *)(v27 + 2),
                (const unsigned __int16 *)(v27 + 262));
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
              wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v46);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
              LastError = 0;
              goto LABEL_52;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x166F,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)(unsigned int)BnoIsolationPrefixForRpc,
              v31);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
            goto LABEL_29;
          }
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x166B,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        (const char *)(unsigned int)v23,
                        v31);
          RevertToSelf();
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1656,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        v21);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v46);
        goto LABEL_51;
      }
      v18 = 5713;
    }
    else
    {
      v18 = 5703;
    }
    goto LABEL_28;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x15FE,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)ClientInformation,
                v30);
LABEL_52:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v56);
  LUATelemetry::GetPackageActivationTokenForFilePath::~GetPackageActivationTokenForFilePath((LUATelemetry::GetPackageActivationTokenForFilePath *)v63);
  return LastError;
}

```

## disassembly

```asm
0x180029ce4  mov     [rsp-8+arg_8], rbx
0x180029ce9  mov     [rsp-8+arg_10], rsi
0x180029cee  push    rbp
0x180029cef  push    rdi
0x180029cf0  push    r12
0x180029cf2  push    r14
0x180029cf4  push    r15
0x180029cf6  lea     rbp, [rsp-1A0h]
0x180029cfe  sub     rsp, 2B0h
0x180029d05  mov     rax, cs:__security_cookie
0x180029d0c  xor     rax, rsp
0x180029d0f  mov     [rbp+1C0h+var_30], rax
0x180029d16  mov     rdi, rcx
0x180029d19  lea     rdx, aGetpackageacti_1; "GetPackageActivationTokenForFilePath"
0x180029d20  lea     rcx, [rbp+1C0h+var_180]; struct wil::details::IFailureCallback *
0x180029d24  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180029d29  lea     rax, ??_7GetPackageActivationTokenForFilePath@LUATelemetry@@6B@; const LUATelemetry::GetPackageActivationTokenForFilePath::`vftable'
0x180029d30  lea     rcx, [rbp+1C0h+var_180]; this
0x180029d34  mov     [rbp+1C0h+var_180], rax
0x180029d38  call    ?StartActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXXZ; LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(void)
0x180029d3d  xor     r12d, r12d
0x180029d40  mov     [rbp+1C0h+var_200], 1
0x180029d44  lea     rax, [rbp+1C0h+TokenHandle]
0x180029d48  mov     [rbp+1C0h+var_1E0], r12
0x180029d4c  mov     [rbp+1C0h+var_210], rax
0x180029d50  lea     r8, [rbp+1C0h+var_208]; void **
0x180029d54  lea     rax, [rbp+1C0h+var_1E0]
0x180029d58  mov     [rbp+1C0h+TokenHandle], r12
0x180029d5c  mov     [rbp+1C0h+var_1D8], rax
0x180029d60  lea     rdx, [rbp+1C0h+var_1D0]; void **
0x180029d64  mov     rax, [rdi]
0x180029d67  xor     r9d, r9d; unsigned int *
0x180029d6a  mov     [rbp+1C0h+var_208], r12
0x180029d6e  mov     [rbp+1C0h+var_1D0], r12
0x180029d72  mov     byte ptr [rbp+1C0h+var_1C8], 1
0x180029d76  mov     rcx, [rax]; void *
0x180029d79  mov     [rsp+2D0h+var_2B0], r12; int
0x180029d7e  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180029d83  lea     rcx, [rbp+1C0h+var_1D8]
0x180029d87  mov     ebx, eax
0x180029d89  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180029d8e  lea     rcx, [rbp+1C0h+var_210]
0x180029d92  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180029d97  test    ebx, ebx
0x180029d99  jz      short loc_180029DBD
0x180029d9b  mov     rcx, [rbp+1C8h]; this
0x180029da2  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029da9  mov     r9d, ebx; char *
0x180029dac  mov     edx, 15FEh; void *
0x180029db1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180029db6  mov     ebx, eax
0x180029db8  jmp     loc_18002A395
0x180029dbd  mov     rsi, [rdi+8]
0x180029dc1  mov     rcx, [rbp+1C0h+TokenHandle]; TokenHandle
0x180029dc5  mov     rdx, [rsi]; HANDLE
0x180029dc8  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x180029dcd  mov     ebx, eax
0x180029dcf  test    eax, eax
0x180029dd1  jns     short loc_180029DF3
0x180029dd3  mov     rcx, [rbp+1C8h]; this
0x180029dda  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029de1  mov     r9d, eax; char *
0x180029de4  mov     edx, 1600h; void *
0x180029de9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029dee  jmp     loc_18002A395
0x180029df3  cmp     [rsi], r12
0x180029df6  lea     rcx, [rbp+1C0h+hToken]
0x180029dfa  mov     r14, [rbp+1C0h+TokenHandle]
0x180029dfe  cmovnz  r14, [rsi]
0x180029e02  xor     edx, edx
0x180029e04  mov     [rbp+1C0h+var_1E8], r12
0x180029e08  mov     [rbp+1C0h+hToken], r12
0x180029e0c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180029e11  lea     r8, [rbp+1C0h+hToken]; void **
0x180029e15  mov     rcx, r14; void *
0x180029e18  lea     rdx, [rbp+1C0h+var_1E8]; unsigned __int64 *
0x180029e1c  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x180029e21  mov     ebx, eax
0x180029e23  test    eax, eax
0x180029e25  jns     short loc_180029E47
0x180029e27  mov     rcx, [rbp+1C8h]; this
0x180029e2e  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029e35  mov     r9d, eax; char *
0x180029e38  mov     edx, 1609h; void *
0x180029e3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e42  jmp     loc_18002A38C
0x180029e47  mov     rcx, [rbp+1C0h+hToken]; hToken
0x180029e4b  call    cs:__imp_ImpersonateLoggedOnUser
0x180029e52  nop     dword ptr [rax+rax+00h]
0x180029e57  test    eax, eax
0x180029e59  jnz     short loc_180029E7A
0x180029e5b  mov     rcx, [rbp+1C8h]; this
0x180029e62  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029e69  mov     edx, 160Ch; void *
0x180029e6e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029e73  mov     ebx, eax
0x180029e75  jmp     loc_18002A38C
0x180029e7a  mov     r15, [rdi+10h]
0x180029e7e  xor     r8d, r8d
0x180029e81  mov     rbx, [rdi+18h]
0x180029e85  mov     rdx, [rbp+1C0h+hToken]
0x180029e89  mov     r9, rbx
0x180029e8c  mov     rcx, [r15]
0x180029e8f  call    cs:__imp_BasepGetPackagedAppInfoForFile
0x180029e96  nop     dword ptr [rax+rax+00h]
0x180029e9b  mov     esi, eax
0x180029e9d  test    eax, eax
0x180029e9f  jns     short loc_180029ED8
0x180029ea1  mov     edx, 160Fh; void *
0x180029ea6  mov     rcx, [rbp+1C8h]; this
0x180029ead  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180029eb4  mov     r9d, esi; char *
0x180029eb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ebc  call    cs:__imp_RevertToSelf
0x180029ec3  nop     dword ptr [rax+rax+00h]
0x180029ec8  lea     rcx, [rbp+1C0h+hToken]
0x180029ecc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029ed1  mov     ebx, esi
0x180029ed3  jmp     loc_18002A395
0x180029ed8  mov     rax, [rbx]
0x180029edb  test    rax, rax
0x180029ede  jz      loc_18002A360
0x180029ee4  cmp     [rax], r12b
0x180029ee7  jz      loc_18002A360
0x180029eed  mov     rcx, [rbp+1C0h+var_1E8]
0x180029ef1  lea     rax, [rbp+1C0h+var_1F8]
0x180029ef5  mov     [rbp+1C0h+var_1F8], r12d
0x180029ef9  xor     r9d, r9d
0x180029efc  mov     rdx, [rbx]
0x180029eff  xor     r8d, r8d
0x180029f02  add     rdx, 2
0x180029f06  mov     [rsp+2D0h+var_2B0], rax; int
0x180029f0b  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x180029f12  nop     dword ptr [rax+rax+00h]
0x180029f17  mov     esi, eax
0x180029f19  test    eax, eax
0x180029f1b  jns     short loc_180029F24
0x180029f1d  mov     edx, 1613h
0x180029f22  jmp     short loc_180029EA6
0x180029f24  cmp     [rbp+1C0h+var_1F8], r12d
0x180029f28  jz      short loc_180029F6A
0x180029f2a  mov     rdx, [rbp+1C0h+hToken]
0x180029f2e  mov     r9, rbx
0x180029f31  mov     rcx, [r15]
0x180029f34  xor     r8d, r8d
0x180029f37  call    cs:__imp_BasepGetPackagedAppInfoForFile
0x180029f3e  nop     dword ptr [rax+rax+00h]
0x180029f43  mov     esi, eax
0x180029f45  test    eax, eax
0x180029f47  jns     short loc_180029F53
0x180029f49  mov     edx, 1618h
0x180029f4e  jmp     loc_180029EA6
0x180029f53  mov     rax, [rbx]
0x180029f56  test    rax, rax
0x180029f59  jz      short loc_180029F60
0x180029f5b  cmp     [rax], r12b
0x180029f5e  jnz     short loc_180029F6A
0x180029f60  mov     edx, 1619h
0x180029f65  jmp     loc_18002A365
0x180029f6a  call    cs:__imp_RevertToSelf
0x180029f71  nop     dword ptr [rax+rax+00h]
0x180029f76  mov     r15, [rdi+20h]
0x180029f7a  mov     rdx, [rdi+10h]
0x180029f7e  mov     [rbp+1C0h+var_208], r12
0x180029f82  mov     [rbp+1C0h+var_200], 1
0x180029f86  mov     dword ptr [r15], 1
0x180029f8d  mov     [rbp+1C0h+var_228], r12
0x180029f91  mov     rax, [rbx]
0x180029f94  cmp     dword ptr [rax+224h], 4
0x180029f9b  lea     rcx, [rax+106h]
0x180029fa2  mov     rax, [rbp+1C0h+hToken]
0x180029fa6  jnz     short loc_18002A024
0x180029fa8  mov     [rbp+1C0h+var_1D8], rax
0x180029fac  mov     rax, [rbp+1C0h+TokenHandle]
0x180029fb0  mov     [rbp+1C0h+var_1D0], rax
0x180029fb4  mov     [rbp+1C0h+var_1B8], r12
0x180029fb8  mov     [rbp+1C0h+var_1C8], rcx
0x180029fbc  lea     rcx, [rbp+1C0h+var_1D8]
0x180029fc0  mov     rax, [rdx]
0x180029fc3  lea     rdx, [rbp+1C0h+var_208]
0x180029fc7  mov     [rbp+1C0h+var_1C0], rax
0x180029fcb  mov     eax, r12d
0x180029fce  or      eax, 2
0x180029fd1  mov     dword ptr [rbp+1C0h+var_1B8], eax
0x180029fd4  lea     rax, [rbp+1C0h+var_228]
0x180029fd8  mov     [rbp+1C0h+var_210], rax
0x180029fdc  call    cs:__imp_PrepareDesktopAppXActivation
0x180029fe3  nop     dword ptr [rax+rax+00h]
0x180029fe8  lea     rcx, [rbp+1C0h+var_210]
0x180029fec  mov     esi, eax
0x180029fee  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x180029ff3  test    esi, esi
0x180029ff5  jns     loc_18002A09D
0x180029ffb  mov     edx, 162Ah; void *
0x18002a000  mov     rcx, [rbp+1C8h]; this
0x18002a007  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a00e  mov     r9d, esi; char *
0x18002a011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a016  lea     rcx, [rbp+1C0h+var_228]
0x18002a01a  call    ??1?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002a01f  jmp     loc_180029EC8
0x18002a024  mov     [rbp+1C0h+var_1B0], rax
0x18002a028  mov     rax, [rbp+1C0h+TokenHandle]
0x18002a02c  mov     [rbp+1C0h+var_1A8], rax
0x18002a030  mov     [rbp+1C0h+var_1A0], rcx
0x18002a034  lea     rcx, [rbp+1C0h+var_1B0]
0x18002a038  mov     [rbp+1C0h+var_190], r12
0x18002a03c  mov     rax, [rdx]
0x18002a03f  lea     rdx, [rbp+1C0h+var_208]
0x18002a043  mov     [rbp+1C0h+var_198], rax
0x18002a047  lea     rax, [rbp+1C0h+var_1F0]
0x18002a04b  mov     [rbp+1C0h+var_210], rax
0x18002a04f  mov     [rbp+1C0h+var_1F0], r12
0x18002a053  call    cs:__imp_PrepareAppXActivation
0x18002a05a  nop     dword ptr [rax+rax+00h]
0x18002a05f  lea     rcx, [rbp+1C0h+var_210]
0x18002a063  mov     esi, eax
0x18002a065  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x18002a06a  test    esi, esi
0x18002a06c  jns     short loc_18002A094
0x18002a06e  mov     rcx, [rbp+1C8h]; this
0x18002a075  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a07c  mov     r9d, esi; char *
0x18002a07f  mov     edx, 1635h; void *
0x18002a084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a089  lea     rcx, [rbp+1C0h+var_1F0]
0x18002a08d  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002a092  jmp     short loc_18002A016
0x18002a094  lea     rcx, [rbp+1C0h+var_1F0]
0x18002a098  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002a09d  mov     [rsp+2D0h+var_290], r12; bool *
0x18002a0a2  lea     rax, [rbp+1C0h+var_240]
0x18002a0a6  mov     [rsp+2D0h+var_298], rax; bool *
0x18002a0ab  lea     r9, [rbp+1C0h+var_23D]; bool *
0x18002a0af  lea     rax, [rbp+1C0h+var_23F]
0x18002a0b3  mov     dword ptr [r15], 4
0x18002a0ba  mov     rcx, [rbx]
0x18002a0bd  lea     rdx, [rbp+1C0h+var_23C]; bool *
0x18002a0c1  mov     [rsp+2D0h+var_2A0], r12; bool *
0x18002a0c6  add     rcx, 106h; unsigned __int16 *
0x18002a0cd  mov     [rsp+2D0h+var_2A8], rax; bool *
0x18002a0d2  xor     r8d, r8d; bool *
0x18002a0d5  lea     rax, [rbp+1C0h+var_23E]
0x18002a0d9  mov     [rbp+1C0h+var_23C], r12b
0x18002a0dd  mov     [rsp+2D0h+var_2B0], rax; bool *
0x18002a0e2  mov     [rbp+1C0h+var_23D], r12b
0x18002a0e6  mov     [rbp+1C0h+var_23E], r12b
0x18002a0ea  mov     [rbp+1C0h+var_23F], r12b
0x18002a0ee  mov     [rbp+1C0h+var_240], r12b
0x18002a0f2  call    ?GetPackageProperties@@YAJPEBGPEA_N1111111@Z; GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)
0x18002a0f7  mov     esi, eax
0x18002a0f9  test    eax, eax
0x18002a0fb  jns     short loc_18002A107
0x18002a0fd  mov     edx, 1647h
0x18002a102  jmp     loc_18002A000
0x18002a107  mov     rcx, [rbp+1C0h+hToken]; void *
0x18002a10b  lea     rax, [rbp+1C0h+var_23C+2]
0x18002a10f  mov     [rsp+2D0h+var_288], rax; bool *
0x18002a114  xor     r9d, r9d; unsigned int
0x18002a117  mov     [rbp+1C0h+var_1F4], r12d
0x18002a11b  lea     rax, [rbp+1C0h+var_230]
0x18002a11f  mov     [rsp+2D0h+var_290], rax; bool *
0x18002a124  lea     rax, [rbp+1C0h+var_22F]
0x18002a128  mov     [rsp+2D0h+var_298], rax; bool *
0x18002a12d  lea     rax, [rbp+1C0h+var_22E]
0x18002a131  mov     [rsp+2D0h+var_2A0], rax; bool *
0x18002a136  lea     rax, [rbp+1C0h+var_23C+1]
0x18002a13a  mov     [rbp+1C0h+var_23C+1], r12b
0x18002a13e  mov     [rbp+1C0h+var_22E], r12b
0x18002a142  mov     [rbp+1C0h+var_22F], r12b
0x18002a146  mov     [rbp+1C0h+var_230], r12b
0x18002a14a  mov     [rbp+1C0h+var_23C+2], r12b
0x18002a14e  mov     rdx, [rbx]
0x18002a151  mov     [rsp+2D0h+var_2A8], rax; bool *
0x18002a156  lea     rax, [rbp+1C0h+var_1F4]
0x18002a15a  mov     [rsp+2D0h+var_2B0], rax; enum AppModel::RuntimeBehavior *
0x18002a15f  mov     r8, [rdx+218h]; unsigned __int16 *
0x18002a166  add     rdx, 2; unsigned __int16 *
0x18002a16a  call    ?GetAppModelIdentityActivationProperties@@YAJPEAXPEBG1KPEAW4RuntimeBehavior@AppModel@@PEA_N3333@Z; GetAppModelIdentityActivationProperties(void *,ushort const *,ushort const *,ulong,AppModel::RuntimeBehavior *,bool *,bool *,bool *,bool *,bool *)
0x18002a16f  mov     esi, eax
0x18002a171  test    eax, eax
0x18002a173  jns     short loc_18002A17F
0x18002a175  mov     edx, 1651h
0x18002a17a  jmp     loc_18002A000
0x18002a17f  mov     rcx, r14; hToken
0x18002a182  mov     [rbp+1C0h+var_220], r12
0x18002a186  call    cs:__imp_ImpersonateLoggedOnUser
0x18002a18d  nop     dword ptr [rax+rax+00h]
0x18002a192  test    eax, eax
0x18002a194  jnz     short loc_18002A1C7
0x18002a196  mov     rcx, [rbp+1C8h]; this
0x18002a19d  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002a1a4  mov     edx, 1656h; void *
0x18002a1a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a1ae  mov     ebx, eax
0x18002a1b0  lea     rcx, [rbp+1C0h+var_220]
0x18002a1b4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a1b9  lea     rcx, [rbp+1C0h+var_228]
0x18002a1bd  call    ??1?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002a1c2  jmp     loc_18002A38C
  ... truncated ...
```
