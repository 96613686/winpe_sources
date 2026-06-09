# _lambda_ea28e87ebffcac95e533c6a1f7a61a0f_::operator()

- ea: `0x18002c480`
- end: `0x18002cb24`
- name: `_lambda_ea28e87ebffcac95e533c6a1f7a61a0f_::operator()`
- size: `1700`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035cd8`

## callees

- `0x18000720c`
- `0x180009d10`
- `0x180009d50`
- `0x18000a938`
- `0x18000b510`
- `0x18000bd90`
- `0x18000bde0`
- `0x18000c410`
- `0x18000de10`
- `0x1800104b0`
- `0x180010510`
- `0x180018190`
- `0x180018dbc`
- `0x18001a0d4`
- `0x18001a37c`
- `0x18001a594`
- `0x18001a654`
- `0x18001d014`
- `0x18001d228`
- `0x18002c480`
- `0x18002ce70`
- `0x18003130c`
- `0x180036898`
- `0x180039dfc`
- `0x180046e50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c5e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c8f8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c5e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c8f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c6d7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ca04`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ca0f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cad1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c6d7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ca04`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ca0f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cad1`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002c748`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002c748`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002c7ba`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002c7ba`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002c672`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002c672`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x18002c622`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x18002c6a3`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x18002c622`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x18002c6a3`

## string_xrefs

- `0x18002c53a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c572`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c5ca`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c5f8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c770`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c7d6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c909`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c9ee`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002ca3c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cac5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002c4b1`: `GetPackageActivationTokenForFilePath`

## pseudocode

```c
__int64 __fastcall lambda_ea28e87ebffcac95e533c6a1f7a61a0f_::operator()(__int64 a1)
{
  void **v2; // rcx
  void *v3; // rcx
  unsigned int ClientInformation; // ebx
  int LastError; // ebx
  int v6; // eax
  HANDLE *v7; // rax
  HANDLE v8; // rsi
  int UserContextAndUnmodifiedLogonTokenOfTokenUser; // eax
  const char *v10; // r9
  int PackagedAppInfoForFile; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  _QWORD *v14; // rdx
  int v15; // eax
  int v16; // eax
  _BYTE *v17; // rcx
  _DWORD *v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // r8
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  __int64 v23; // rdx
  _DWORD *v24; // rax
  __int64 v25; // rax
  int PackageProperties; // eax
  __int64 v27; // rax
  int AppModelIdentityActivationProperties; // eax
  const char *v29; // r9
  __int64 v30; // r8
  int v31; // ebx
  int BnoIsolationPrefixForRpc; // eax
  _QWORD **v33; // rax
  void *v34; // rdx
  __int64 v35; // rbx
  const unsigned __int16 *v36; // rax
  int *v38; // [rsp+20h] [rbp-F0h]
  bool v39; // [rsp+90h] [rbp-80h] BYREF
  bool v40; // [rsp+91h] [rbp-7Fh] BYREF
  bool v41; // [rsp+92h] [rbp-7Eh] BYREF
  bool v42; // [rsp+93h] [rbp-7Dh] BYREF
  bool v43[4]; // [rsp+94h] [rbp-7Ch] BYREF
  HANDLE hToken; // [rsp+98h] [rbp-78h] BYREF
  bool v45; // [rsp+A0h] [rbp-70h] BYREF
  bool v46; // [rsp+A1h] [rbp-6Fh] BYREF
  bool v47; // [rsp+A2h] [rbp-6Eh] BYREF
  __int64 v48; // [rsp+A8h] [rbp-68h] BYREF
  void *v49; // [rsp+B0h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+B8h] [rbp-58h] BYREF
  HANDLE *p_TokenHandle; // [rsp+C0h] [rbp-50h] BYREF
  void *v52; // [rsp+C8h] [rbp-48h] BYREF
  char v53; // [rsp+D0h] [rbp-40h]
  int v54; // [rsp+D8h] [rbp-38h] BYREF
  unsigned int v55; // [rsp+DCh] [rbp-34h] BYREF
  __int64 v56; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int64 v57; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v58; // [rsp+F0h] [rbp-20h] BYREF
  __int64 *v59; // [rsp+F8h] [rbp-18h] BYREF
  void *v60; // [rsp+100h] [rbp-10h] BYREF
  __int64 v61; // [rsp+108h] [rbp-8h]
  __int128 v62; // [rsp+110h] [rbp+0h]
  _QWORD v63[3]; // [rsp+120h] [rbp+10h] BYREF
  __int128 v64; // [rsp+138h] [rbp+28h]
  _QWORD v65[42]; // [rsp+150h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1B8h]

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v65,
    "GetPackageActivationTokenForFilePath");
  v65[0] = &LUATelemetry::GetPackageActivationTokenForFilePath::`vftable';
  LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity((LUATelemetry::GetPackageActivationTokenForFilePath *)v65);
  v2 = *(void ***)a1;
  p_TokenHandle = &TokenHandle;
  v58 = 0;
  TokenHandle = 0;
  v3 = *v2;
  v52 = 0;
  v53 = 1;
  v59 = &v58;
  v60 = 0;
  LOBYTE(v61) = 1;
  ClientInformation = AiGetClientInformation(v3, &v60, &v52, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v59);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( !ClientInformation )
  {
    v6 = AccessCheckIncomingToken(TokenHandle, **(HANDLE **)(a1 + 8));
    LastError = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194C,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v6,
        (int)v38);
      goto LABEL_51;
    }
    v7 = *(HANDLE **)(a1 + 8);
    v8 = TokenHandle;
    if ( *v7 )
      v8 = *v7;
    v57 = 0;
    hToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hToken,
      0);
    UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v8, &v57, &hToken);
    LastError = UserContextAndUnmodifiedLogonTokenOfTokenUser;
    if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1955,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
        (int)v38);
LABEL_50:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      goto LABEL_51;
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1958,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v10);
      goto LABEL_50;
    }
    PackagedAppInfoForFile = BasepGetPackagedAppInfoForFile(**(_QWORD **)(a1 + 16), hToken, 0, *(_QWORD *)(a1 + 24));
    LastError = PackagedAppInfoForFile;
    if ( PackagedAppInfoForFile < 0 )
    {
      v12 = (unsigned int)PackagedAppInfoForFile;
      v13 = 6491;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)v12,
        (int)v38);
      RevertToSelf();
      goto LABEL_50;
    }
    v14 = *(_QWORD **)(a1 + 24);
    if ( !*v14 || !*(_BYTE *)*v14 )
    {
      v13 = 6492;
      goto LABEL_48;
    }
    v54 = 0;
    v38 = &v54;
    v15 = RegisterAppXPackageIfNecessary2(v57, *v14 + 2LL, 0, 0);
    LastError = v15;
    if ( v15 < 0 )
    {
      v12 = (unsigned int)v15;
      v13 = 6495;
      goto LABEL_49;
    }
    if ( v54 )
    {
      v16 = BasepGetPackagedAppInfoForFile(**(_QWORD **)(a1 + 16), hToken, 0, *(_QWORD *)(a1 + 24));
      LastError = v16;
      if ( v16 < 0 )
      {
        v12 = (unsigned int)v16;
        v13 = 6500;
        goto LABEL_49;
      }
      v17 = **(_BYTE ***)(a1 + 24);
      if ( !v17 || !*v17 )
      {
        v13 = 6501;
LABEL_48:
        LastError = -2147024894;
        v12 = 2147942402LL;
        goto LABEL_49;
      }
    }
    RevertToSelf();
    v18 = *(_DWORD **)(a1 + 32);
    v52 = 0;
    v53 = 1;
    *v18 = 1;
    v19 = *(_QWORD *)(a1 + 24);
    v20 = *(_QWORD **)(a1 + 16);
    v48 = 0;
    v21 = *(_QWORD *)v19 + 262LL;
    if ( *(_DWORD *)(*(_QWORD *)v19 + 548LL) == 4 )
    {
      v59 = (__int64 *)hToken;
      v62 = 0;
      v60 = TokenHandle;
      v61 = v21;
      *(_QWORD *)&v62 = *v20;
      p_TokenHandle = (HANDLE *)&v48;
      DWORD2(v62) = 2;
      LastError = PrepareDesktopAppXActivation(&v59, &v52);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( LastError < 0 )
      {
        v22 = (unsigned int)LastError;
        v23 = 6518;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)v22,
          (int)v38);
LABEL_27:
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v48);
        goto LABEL_50;
      }
    }
    else
    {
      v63[0] = hToken;
      v63[1] = TokenHandle;
      v64 = 0;
      v63[2] = v21;
      *(_QWORD *)&v64 = *v20;
      p_TokenHandle = (HANDLE *)&v56;
      v56 = 0;
      LastError = PrepareAppXActivation(v63, &v52);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( LastError < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1981,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)LastError,
          (int)&v54);
        wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v56);
        goto LABEL_27;
      }
      wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v56);
    }
    v24 = *(_DWORD **)(a1 + 32);
    v43[0] = 0;
    v42 = 0;
    *v24 = 4;
    v25 = *(_QWORD *)(a1 + 24);
    v41 = 0;
    v40 = 0;
    v39 = 0;
    PackageProperties = GetPackageProperties(
                          (const unsigned __int16 *)(*(_QWORD *)v25 + 262LL),
                          v43,
                          0,
                          &v42,
                          &v41,
                          &v40,
                          0,
                          &v39,
                          0);
    LastError = PackageProperties;
    if ( PackageProperties >= 0 )
    {
      v27 = *(_QWORD *)(a1 + 24);
      v55 = 0;
      v43[1] = 0;
      v47 = 0;
      v46 = 0;
      v45 = 0;
      v43[2] = 0;
      AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                               hToken,
                                               (const unsigned __int16 *)(*(_QWORD *)v27 + 2LL),
                                               *(const unsigned __int16 **)(*(_QWORD *)v27 + 536LL),
                                               0,
                                               (enum AppModel::RuntimeBehavior *)&v55,
                                               &v43[1],
                                               &v47,
                                               &v46,
                                               &v45,
                                               &v43[2]);
      LastError = AppModelIdentityActivationProperties;
      if ( AppModelIdentityActivationProperties >= 0 )
      {
        v49 = 0;
        if ( ImpersonateLoggedOnUser(v8) )
        {
          v52 = 0;
          p_TokenHandle = &v49;
          v53 = 1;
          if ( v48 )
            v30 = *(_QWORD *)(v48 + 56);
          else
            v30 = 0;
          LOBYTE(v29) = *(_DWORD *)(**(_QWORD **)(a1 + 24) + 548LL) == 3;
          LOBYTE(v30) = v43[1];
          LOBYTE(v38) = v43[0];
          v31 = AdjustActivationToken(v8, v55, v30, v29);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v31 >= 0 )
          {
            RevertToSelf();
            if ( !v43[2]
              || (BnoIsolationPrefixForRpc = CreateBnoIsolationPrefixForRpc(
                                               v49,
                                               (unsigned __int16 **)(**(_QWORD **)(a1 + 40) + 8LL)),
                  LastError = BnoIsolationPrefixForRpc,
                  BnoIsolationPrefixForRpc >= 0) )
            {
              v33 = *(_QWORD ***)(a1 + 40);
              v34 = v49;
              v49 = 0;
              **v33 = v34;
              v35 = **(_QWORD **)(a1 + 24);
              v36 = AipJustFileName(**(const unsigned __int16 ***)(a1 + 16));
              LUATelemetry::GetPackageActivationTokenForFilePath::Stop(
                (LUATelemetry::GetPackageActivationTokenForFilePath *)v65,
                v36,
                (const unsigned __int16 *)(v35 + 2),
                (const unsigned __int16 *)(v35 + 262));
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v49);
              wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v48);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
              LastError = 0;
              goto LABEL_51;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19BB,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)(unsigned int)BnoIsolationPrefixForRpc,
              (int)v38);
          }
          else
          {
            LastError = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x19B7,
                          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                          (const char *)(unsigned int)v31,
                          (int)v38);
            RevertToSelf();
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x19A2,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        v29);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v49);
        goto LABEL_27;
      }
      v22 = (unsigned int)AppModelIdentityActivationProperties;
      v23 = 6557;
    }
    else
    {
      v22 = (unsigned int)PackageProperties;
      v23 = 6547;
    }
    goto LABEL_26;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x194A,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)ClientInformation,
                (unsigned int)v38);
LABEL_51:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v58);
  LUATelemetry::GetPackageActivationTokenForFilePath::~GetPackageActivationTokenForFilePath((LUATelemetry::GetPackageActivationTokenForFilePath *)v65);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002c480  mov     [rsp-8+arg_8], rbx
0x18002c485  mov     [rsp-8+arg_10], rsi
0x18002c48a  push    rbp
0x18002c48b  push    rdi
0x18002c48c  push    r14
0x18002c48e  lea     rbp, [rsp-1A0h]
0x18002c496  sub     rsp, 2B0h
0x18002c49d  mov     rax, cs:__security_cookie
0x18002c4a4  xor     rax, rsp
0x18002c4a7  mov     [rbp+1B0h+var_20], rax
0x18002c4ae  mov     rdi, rcx
0x18002c4b1  lea     rdx, aGetpackageacti_1; "GetPackageActivationTokenForFilePath"
0x18002c4b8  lea     rcx, [rbp+1B0h+var_170]
0x18002c4bc  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002c4c1  lea     rax, ??_7GetPackageActivationTokenForFilePath@LUATelemetry@@6B@; const LUATelemetry::GetPackageActivationTokenForFilePath::`vftable'
0x18002c4c8  lea     rcx, [rbp+1B0h+var_170]; this
0x18002c4cc  mov     [rbp+1B0h+var_170], rax
0x18002c4d0  call    ?StartActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXXZ; LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(void)
0x18002c4d5  mov     rcx, [rdi]
0x18002c4d8  lea     rax, [rbp+1B0h+TokenHandle]
0x18002c4dc  xor     r14d, r14d
0x18002c4df  mov     [rbp+1B0h+var_200], rax
0x18002c4e3  mov     [rbp+1B0h+var_1D0], r14
0x18002c4e7  lea     rax, [rbp+1B0h+var_1D0]
0x18002c4eb  mov     [rbp+1B0h+TokenHandle], r14
0x18002c4ef  lea     r8, [rbp+1B0h+var_1F8]; void **
0x18002c4f3  mov     rcx, [rcx]; void *
0x18002c4f6  lea     rdx, [rbp+1B0h+var_1C0]; void **
0x18002c4fa  xor     r9d, r9d; unsigned int *
0x18002c4fd  mov     [rbp+1B0h+var_1F8], r14
0x18002c501  mov     [rbp+1B0h+var_1F0], 1
0x18002c505  mov     [rbp+1B0h+var_1C8], rax
0x18002c509  mov     [rbp+1B0h+var_1C0], r14
0x18002c50d  mov     byte ptr [rbp+1B0h+var_1B8], 1
0x18002c511  mov     [rsp+2C0h+var_2A0], r14; int
0x18002c516  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18002c51b  lea     rcx, [rbp+1B0h+var_1C8]
0x18002c51f  mov     ebx, eax
0x18002c521  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002c526  lea     rcx, [rbp+1B0h+var_200]
0x18002c52a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002c52f  test    ebx, ebx
0x18002c531  jz      short loc_18002C555
0x18002c533  mov     rcx, [rbp+1B8h]; this
0x18002c53a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c541  mov     r9d, ebx; char *
0x18002c544  mov     edx, 194Ah; void *
0x18002c549  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c54e  mov     ebx, eax
0x18002c550  jmp     loc_18002CAE0
0x18002c555  mov     rdx, [rdi+8]
0x18002c559  mov     rcx, [rbp+1B0h+TokenHandle]; TokenHandle
0x18002c55d  mov     rdx, [rdx]; HANDLE
0x18002c560  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x18002c565  mov     ebx, eax
0x18002c567  test    eax, eax
0x18002c569  jns     short loc_18002C58B
0x18002c56b  mov     rcx, [rbp+1B8h]; this
0x18002c572  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c579  mov     r9d, eax; char *
0x18002c57c  mov     edx, 194Ch; void *
0x18002c581  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c586  jmp     loc_18002CAE0
0x18002c58b  mov     rax, [rdi+8]
0x18002c58f  lea     rcx, [rbp+1B0h+hToken]
0x18002c593  mov     rsi, [rbp+1B0h+TokenHandle]
0x18002c597  cmp     [rax], r14
0x18002c59a  cmovnz  rsi, [rax]
0x18002c59e  xor     edx, edx
0x18002c5a0  mov     [rbp+1B0h+var_1D8], r14
0x18002c5a4  mov     [rbp+1B0h+hToken], r14
0x18002c5a8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002c5ad  lea     r8, [rbp+1B0h+hToken]; void **
0x18002c5b1  mov     rcx, rsi; void *
0x18002c5b4  lea     rdx, [rbp+1B0h+var_1D8]; unsigned __int64 *
0x18002c5b8  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x18002c5bd  mov     ebx, eax
0x18002c5bf  test    eax, eax
0x18002c5c1  jns     short loc_18002C5E3
0x18002c5c3  mov     rcx, [rbp+1B8h]; this
0x18002c5ca  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c5d1  mov     r9d, eax; char *
0x18002c5d4  mov     edx, 1955h; void *
0x18002c5d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5de  jmp     loc_18002CAD7
0x18002c5e3  mov     rcx, [rbp+1B0h+hToken]; hToken
0x18002c5e7  call    cs:__imp_ImpersonateLoggedOnUser
0x18002c5ed  test    eax, eax
0x18002c5ef  jnz     short loc_18002C610
0x18002c5f1  mov     rcx, [rbp+1B8h]; this
0x18002c5f8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c5ff  mov     edx, 1958h; void *
0x18002c604  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c609  mov     ebx, eax
0x18002c60b  jmp     loc_18002CAD7
0x18002c610  mov     rcx, [rdi+10h]
0x18002c614  xor     r8d, r8d
0x18002c617  mov     r9, [rdi+18h]
0x18002c61b  mov     rdx, [rbp+1B0h+hToken]
0x18002c61f  mov     rcx, [rcx]
0x18002c622  call    cs:__imp_BasepGetPackagedAppInfoForFile
0x18002c628  mov     ebx, eax
0x18002c62a  test    eax, eax
0x18002c62c  jns     short loc_18002C63B
0x18002c62e  mov     r9d, eax
0x18002c631  mov     edx, 195Bh
0x18002c636  jmp     loc_18002CABE
0x18002c63b  mov     rdx, [rdi+18h]
0x18002c63f  mov     rax, [rdx]
0x18002c642  test    rax, rax
0x18002c645  jz      loc_18002CAB1
0x18002c64b  cmp     [rax], r14b
0x18002c64e  jz      loc_18002CAB1
0x18002c654  mov     rcx, [rbp+1B0h+var_1D8]
0x18002c658  lea     rax, [rbp+1B0h+var_1E8]
0x18002c65c  mov     [rbp+1B0h+var_1E8], r14d
0x18002c660  xor     r9d, r9d
0x18002c663  mov     rdx, [rdx]
0x18002c666  xor     r8d, r8d
0x18002c669  add     rdx, 2
0x18002c66d  mov     [rsp+2C0h+var_2A0], rax; int
0x18002c672  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x18002c678  mov     ebx, eax
0x18002c67a  test    eax, eax
0x18002c67c  jns     short loc_18002C68B
0x18002c67e  mov     r9d, eax
0x18002c681  mov     edx, 195Fh
0x18002c686  jmp     loc_18002CABE
0x18002c68b  cmp     [rbp+1B0h+var_1E8], r14d
0x18002c68f  jz      short loc_18002C6D7
0x18002c691  mov     rcx, [rdi+10h]
0x18002c695  xor     r8d, r8d
0x18002c698  mov     r9, [rdi+18h]
0x18002c69c  mov     rdx, [rbp+1B0h+hToken]
0x18002c6a0  mov     rcx, [rcx]
0x18002c6a3  call    cs:__imp_BasepGetPackagedAppInfoForFile
0x18002c6a9  mov     ebx, eax
0x18002c6ab  test    eax, eax
0x18002c6ad  jns     short loc_18002C6BC
0x18002c6af  mov     r9d, eax
0x18002c6b2  mov     edx, 1964h
0x18002c6b7  jmp     loc_18002CABE
0x18002c6bc  mov     rax, [rdi+18h]
0x18002c6c0  mov     rcx, [rax]
0x18002c6c3  test    rcx, rcx
0x18002c6c6  jz      short loc_18002C6CD
0x18002c6c8  cmp     [rcx], r14b
0x18002c6cb  jnz     short loc_18002C6D7
0x18002c6cd  mov     edx, 1965h
0x18002c6d2  jmp     loc_18002CAB6
0x18002c6d7  call    cs:__imp_RevertToSelf
0x18002c6dd  mov     rax, [rdi+20h]
0x18002c6e1  xorps   xmm0, xmm0
0x18002c6e4  mov     [rbp+1B0h+var_1F8], r14
0x18002c6e8  mov     [rbp+1B0h+var_1F0], 1
0x18002c6ec  mov     dword ptr [rax], 1
0x18002c6f2  mov     rax, [rdi+18h]
0x18002c6f6  mov     r8, [rdi+10h]
0x18002c6fa  mov     [rbp+1B0h+var_218], r14
0x18002c6fe  mov     rcx, [rax]
0x18002c701  mov     rax, [rbp+1B0h+hToken]
0x18002c705  cmp     dword ptr [rcx+224h], 4
0x18002c70c  lea     rdx, [rcx+106h]
0x18002c713  jnz     short loc_18002C78A
0x18002c715  mov     [rbp+1B0h+var_1C8], rax
0x18002c719  lea     rcx, [rbp+1B0h+var_1C8]
0x18002c71d  mov     rax, [rbp+1B0h+TokenHandle]
0x18002c721  movdqu  [rbp+1B0h+var_1B0], xmm0
0x18002c726  mov     [rbp+1B0h+var_1C0], rax
0x18002c72a  mov     [rbp+1B0h+var_1B8], rdx
0x18002c72e  lea     rdx, [rbp+1B0h+var_1F8]
0x18002c732  mov     rax, [r8]
0x18002c735  mov     qword ptr [rbp+1B0h+var_1B0], rax
0x18002c739  lea     rax, [rbp+1B0h+var_218]
0x18002c73d  mov     [rbp+1B0h+var_200], rax
0x18002c741  mov     dword ptr [rbp+1B0h+var_1B0+8], 2
0x18002c748  call    cs:__imp_PrepareDesktopAppXActivation
0x18002c74e  lea     rcx, [rbp+1B0h+var_200]
0x18002c752  mov     ebx, eax
0x18002c754  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x18002c759  test    ebx, ebx
0x18002c75b  jns     loc_18002C7FE
0x18002c761  mov     r9d, ebx; char *
0x18002c764  mov     edx, 1976h; void *
0x18002c769  mov     rcx, [rbp+1B8h]; this
0x18002c770  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c77c  lea     rcx, [rbp+1B0h+var_218]
0x18002c780  call    ??1?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002c785  jmp     loc_18002CAD7
0x18002c78a  mov     [rbp+1B0h+var_1A0], rax
0x18002c78e  lea     rcx, [rbp+1B0h+var_1A0]
0x18002c792  mov     rax, [rbp+1B0h+TokenHandle]
0x18002c796  mov     [rbp+1B0h+var_198], rax
0x18002c79a  movdqu  [rbp+1B0h+var_188], xmm0
0x18002c79f  mov     [rbp+1B0h+var_190], rdx
0x18002c7a3  lea     rdx, [rbp+1B0h+var_1F8]
0x18002c7a7  mov     rax, [r8]
0x18002c7aa  mov     qword ptr [rbp+1B0h+var_188], rax
0x18002c7ae  lea     rax, [rbp+1B0h+var_1E0]
0x18002c7b2  mov     [rbp+1B0h+var_200], rax
0x18002c7b6  mov     [rbp+1B0h+var_1E0], r14
0x18002c7ba  call    cs:__imp_PrepareAppXActivation
0x18002c7c0  lea     rcx, [rbp+1B0h+var_200]
0x18002c7c4  mov     ebx, eax
0x18002c7c6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x18002c7cb  test    ebx, ebx
0x18002c7cd  jns     short loc_18002C7F5
0x18002c7cf  mov     rcx, [rbp+1B8h]; this
0x18002c7d6  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c7dd  mov     r9d, ebx; char *
0x18002c7e0  mov     edx, 1981h; void *
0x18002c7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7ea  lea     rcx, [rbp+1B0h+var_1E0]
0x18002c7ee  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002c7f3  jmp     short loc_18002C77C
0x18002c7f5  lea     rcx, [rbp+1B0h+var_1E0]
0x18002c7f9  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x18002c7fe  mov     rax, [rdi+20h]
0x18002c802  lea     r9, [rbp+1B0h+var_22D]; bool *
0x18002c806  mov     [rsp+2C0h+var_280], r14; bool *
0x18002c80b  lea     rdx, [rbp+1B0h+var_22C]; bool *
0x18002c80f  xor     r8d, r8d; bool *
0x18002c812  mov     [rbp+1B0h+var_22C], r14b
0x18002c816  mov     [rbp+1B0h+var_22D], r14b
0x18002c81a  mov     dword ptr [rax], 4
0x18002c820  mov     rax, [rdi+18h]
0x18002c824  mov     [rbp+1B0h+var_22E], r14b
0x18002c828  mov     [rbp+1B0h+var_22F], r14b
0x18002c82c  mov     [rbp+1B0h+var_230], r14b
0x18002c830  mov     rcx, [rax]
0x18002c833  lea     rax, [rbp+1B0h+var_230]
0x18002c837  mov     [rsp+2C0h+var_288], rax; bool *
0x18002c83c  add     rcx, 106h; unsigned __int16 *
0x18002c843  lea     rax, [rbp+1B0h+var_22F]
0x18002c847  mov     [rsp+2C0h+var_290], r14; bool *
0x18002c84c  mov     [rsp+2C0h+var_298], rax; bool *
0x18002c851  lea     rax, [rbp+1B0h+var_22E]
0x18002c855  mov     [rsp+2C0h+var_2A0], rax; bool *
0x18002c85a  call    ?GetPackageProperties@@YAJPEBGPEA_N1111111@Z; GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)
0x18002c85f  mov     ebx, eax
0x18002c861  test    eax, eax
0x18002c863  jns     short loc_18002C872
0x18002c865  mov     r9d, eax
0x18002c868  mov     edx, 1993h
0x18002c86d  jmp     loc_18002C769
0x18002c872  mov     rax, [rdi+18h]
0x18002c876  xor     r9d, r9d; unsigned int
0x18002c879  mov     rcx, [rbp+1B0h+hToken]; void *
0x18002c87d  mov     [rbp+1B0h+var_1E4], r14d
0x18002c881  mov     [rbp+1B0h+var_22C+1], r14b
0x18002c885  mov     [rbp+1B0h+var_21E], r14b
0x18002c889  mov     [rbp+1B0h+var_21F], r14b
0x18002c88d  mov     [rbp+1B0h+var_220], r14b
0x18002c891  mov     [rbp+1B0h+var_22C+2], r14b
0x18002c895  mov     r8, [rax]
0x18002c898  lea     rax, [rbp+1B0h+var_22C+2]
0x18002c89c  mov     [rsp+2C0h+var_278], rax; bool *
0x18002c8a1  lea     rax, [rbp+1B0h+var_220]
0x18002c8a5  mov     [rsp+2C0h+var_280], rax; bool *
0x18002c8aa  lea     rax, [rbp+1B0h+var_21F]
0x18002c8ae  mov     [rsp+2C0h+var_288], rax; bool *
0x18002c8b3  lea     rax, [rbp+1B0h+var_21E]
0x18002c8b7  mov     [rsp+2C0h+var_290], rax; bool *
0x18002c8bc  lea     rdx, [r8+2]; unsigned __int16 *
0x18002c8c0  mov     r8, [r8+218h]; unsigned __int16 *
0x18002c8c7  lea     rax, [rbp+1B0h+var_22C+1]
0x18002c8cb  mov     [rsp+2C0h+var_298], rax; bool *
0x18002c8d0  lea     rax, [rbp+1B0h+var_1E4]
0x18002c8d4  mov     [rsp+2C0h+var_2A0], rax; enum AppModel::RuntimeBehavior *
0x18002c8d9  call    ?GetAppModelIdentityActivationProperties@@YAJPEAXPEBG1KPEAW4RuntimeBehavior@AppModel@@PEA_N3333@Z; GetAppModelIdentityActivationProperties(void *,ushort const *,ushort const *,ulong,AppModel::RuntimeBehavior *,bool *,bool *,bool *,bool *,bool *)
0x18002c8de  mov     ebx, eax
0x18002c8e0  test    eax, eax
0x18002c8e2  jns     short loc_18002C8F1
0x18002c8e4  mov     r9d, eax
0x18002c8e7  mov     edx, 199Dh
0x18002c8ec  jmp     loc_18002C769
0x18002c8f1  mov     rcx, rsi; hToken
0x18002c8f4  mov     [rbp+1B0h+var_210], r14
0x18002c8f8  call    cs:__imp_ImpersonateLoggedOnUser
0x18002c8fe  test    eax, eax
0x18002c900  jnz     short loc_18002C92A
0x18002c902  mov     rcx, [rbp+1B8h]; this
0x18002c909  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002c910  mov     edx, 19A2h; void *
0x18002c915  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c91a  mov     ebx, eax
0x18002c91c  lea     rcx, [rbp+1B0h+var_210]
0x18002c920  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c925  jmp     loc_18002C77C
0x18002c92a  lea     rax, [rbp+1B0h+var_210]
0x18002c92e  mov     [rbp+1B0h+var_1F8], r14
0x18002c932  mov     [rbp+1B0h+var_200], rax
0x18002c936  mov     rax, [rbp+1B0h+var_218]
0x18002c93a  mov     [rbp+1B0h+var_1F0], 1
0x18002c93e  test    rax, rax
0x18002c941  jz      short loc_18002C949
0x18002c943  mov     r8, [rax+38h]
0x18002c947  jmp     short loc_18002C94C
0x18002c949  mov     r8, r14
  ... truncated ...
```
