# _lambda_8291fc1f5fa6071ad5d26ee0de0f9af2_::operator()

- ea: `0x1800286a4`
- end: `0x180028d9e`
- name: `_lambda_8291fc1f5fa6071ad5d26ee0de0f9af2_::operator()`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180032730`

## callees

- `0x180007c78`
- `0x1800092f0`
- `0x18000a1f0`
- `0x18000a230`
- `0x18000bb10`
- `0x18000c4c0`
- `0x18000c790`
- `0x18000f9e0`
- `0x1800109a0`
- `0x1800109d0`
- `0x180012cdc`
- `0x180018400`
- `0x18001847c`
- `0x180018530`
- `0x18001891c`
- `0x1800189c0`
- `0x180018ad4`
- `0x18001af78`
- `0x18001b244`
- `0x18001b344`
- `0x1800286a4`
- `0x180029110`
- `0x18002cb30`
- `0x180033538`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002880b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028b46`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002880b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028b46`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002887c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002892a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028c62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028c73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028d40`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002887c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002892a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028c62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028c73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028d40`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002899c`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002899c`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x180028a13`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x180028a13`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x1800288cb`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x1800288cb`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x18002884f`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x1800288f7`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x18002884f`
- `ext-ms-win-kernelbase-processthread-l1-1-2!BasepGetPackagedAppInfoForFile` at `0x1800288f7`

## string_xrefs

- `0x180028762`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002879a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800287ee`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180028822`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002886d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800289c7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180028a35`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180028b5d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180028c4c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180028ca6`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180028d2c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800286d9`: `GetPackageActivationTokenForFilePath`

## pseudocode

```c
__int64 __fastcall lambda_8291fc1f5fa6071ad5d26ee0de0f9af2_::operator()(__int64 a1)
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
  int v22; // esi
  int BnoIsolationPrefixForRpc; // eax
  void *v24; // rdx
  _QWORD **v25; // rax
  __int64 v26; // rbx
  const unsigned __int16 *v27; // rax
  int *v29; // [rsp+20h] [rbp-F0h]
  bool v30; // [rsp+90h] [rbp-80h] BYREF
  bool v31; // [rsp+91h] [rbp-7Fh] BYREF
  bool v32; // [rsp+92h] [rbp-7Eh] BYREF
  bool v33; // [rsp+93h] [rbp-7Dh] BYREF
  bool v34[4]; // [rsp+94h] [rbp-7Ch] BYREF
  HANDLE hToken; // [rsp+98h] [rbp-78h] BYREF
  bool v36; // [rsp+A0h] [rbp-70h] BYREF
  bool v37; // [rsp+A1h] [rbp-6Fh] BYREF
  bool v38; // [rsp+A2h] [rbp-6Eh] BYREF
  __int64 v39; // [rsp+A8h] [rbp-68h] BYREF
  void *v40; // [rsp+B0h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+B8h] [rbp-58h] BYREF
  HANDLE *p_TokenHandle; // [rsp+C0h] [rbp-50h] BYREF
  void *v43; // [rsp+C8h] [rbp-48h] BYREF
  char v44; // [rsp+D0h] [rbp-40h]
  int v45; // [rsp+D8h] [rbp-38h] BYREF
  unsigned int v46; // [rsp+DCh] [rbp-34h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int64 v48; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-20h] BYREF
  __int64 *v50; // [rsp+F8h] [rbp-18h] BYREF
  void *v51; // [rsp+100h] [rbp-10h] BYREF
  __int64 v52; // [rsp+108h] [rbp-8h]
  __int64 v53; // [rsp+110h] [rbp+0h]
  __int64 v54; // [rsp+118h] [rbp+8h]
  _QWORD v55[6]; // [rsp+120h] [rbp+10h] BYREF
  _QWORD v56[42]; // [rsp+150h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1C8h]

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v56);
  v56[0] = &LUATelemetry::GetPackageActivationTokenForFilePath::`vftable';
  LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity((LUATelemetry::GetPackageActivationTokenForFilePath *)v56);
  v44 = 1;
  v49 = 0;
  p_TokenHandle = &TokenHandle;
  TokenHandle = 0;
  v50 = &v49;
  v2 = *(void ***)a1;
  v43 = 0;
  v51 = 0;
  LOBYTE(v52) = 1;
  ClientInformation = AiGetClientInformation(*v2, &v51, &v43, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v50);
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
        (void *)0x16CD,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v6,
        (int)v29);
      goto LABEL_49;
    }
    v7 = TokenHandle;
    if ( *v5 )
      v7 = *v5;
    v48 = 0;
    hToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hToken,
      0);
    UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v7, &v48, &hToken);
    LastError = UserContextAndUnmodifiedLogonTokenOfTokenUser;
    if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D6,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
        (int)v29);
LABEL_48:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      goto LABEL_49;
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x16D9,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v9);
      goto LABEL_48;
    }
    v10 = *(_QWORD **)(a1 + 16);
    v11 = *(__int64 **)(a1 + 24);
    PackagedAppInfoForFile = BasepGetPackagedAppInfoForFile(*v10, hToken, 0, v11);
    if ( PackagedAppInfoForFile < 0 )
    {
      v13 = 5852;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)PackagedAppInfoForFile,
        (int)v29);
      RevertToSelf();
LABEL_14:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      LastError = PackagedAppInfoForFile;
      goto LABEL_49;
    }
    if ( !*v11 || !*(_BYTE *)*v11 )
    {
      v14 = 5853;
      goto LABEL_47;
    }
    v45 = 0;
    v29 = &v45;
    PackagedAppInfoForFile = RegisterAppXPackageIfNecessary2(v48, *v11 + 2, 0, 0);
    if ( PackagedAppInfoForFile < 0 )
    {
      v13 = 5856;
      goto LABEL_13;
    }
    if ( v45 )
    {
      PackagedAppInfoForFile = BasepGetPackagedAppInfoForFile(*v10, hToken, 0, v11);
      if ( PackagedAppInfoForFile < 0 )
      {
        v13 = 5861;
        goto LABEL_13;
      }
      if ( !*v11 || !*(_BYTE *)*v11 )
      {
        v14 = 5862;
LABEL_47:
        LastError = -2147024894;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)0x80070002LL,
          (int)v29);
        RevertToSelf();
        goto LABEL_48;
      }
    }
    RevertToSelf();
    v15 = *(_DWORD **)(a1 + 32);
    v16 = *(__int64 **)(a1 + 16);
    v43 = 0;
    v44 = 1;
    *v15 = 1;
    v39 = 0;
    v17 = *v11 + 262;
    if ( *(_DWORD *)(*v11 + 548) == 4 )
    {
      v50 = (__int64 *)hToken;
      v51 = TokenHandle;
      v54 = 0;
      v52 = v17;
      v53 = *v16;
      v54 = 2;
      p_TokenHandle = (HANDLE *)&v39;
      PackagedAppInfoForFile = PrepareDesktopAppXActivation(&v50, &v43);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( PackagedAppInfoForFile < 0 )
      {
        v18 = 5879;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackagedAppInfoForFile,
          (int)v29);
LABEL_29:
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v39);
        goto LABEL_14;
      }
    }
    else
    {
      v55[0] = hToken;
      v55[1] = TokenHandle;
      v55[2] = v17;
      v55[4] = 0;
      v55[3] = *v16;
      p_TokenHandle = (HANDLE *)&v47;
      v47 = 0;
      PackagedAppInfoForFile = PrepareAppXActivation(v55, &v43);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( PackagedAppInfoForFile < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1702,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)PackagedAppInfoForFile,
          (int)&v45);
        wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v47);
        goto LABEL_29;
      }
      wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&void FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v47);
    }
    *v15 = 4;
    v19 = (const unsigned __int16 *)(*v11 + 262);
    v34[0] = 0;
    v33 = 0;
    v32 = 0;
    v31 = 0;
    v30 = 0;
    PackagedAppInfoForFile = GetPackageProperties(v19, v34, 0, &v33, &v32, &v31, 0, &v30, 0);
    if ( PackagedAppInfoForFile >= 0 )
    {
      v46 = 0;
      v34[1] = 0;
      v38 = 0;
      v37 = 0;
      v36 = 0;
      v34[2] = 0;
      PackagedAppInfoForFile = GetAppModelIdentityActivationProperties(
                                 hToken,
                                 (const unsigned __int16 *)(*v11 + 2),
                                 *(const unsigned __int16 **)(*v11 + 536),
                                 0,
                                 (enum AppModel::RuntimeBehavior *)&v46,
                                 &v34[1],
                                 &v38,
                                 &v37,
                                 &v36,
                                 &v34[2]);
      if ( PackagedAppInfoForFile >= 0 )
      {
        v40 = 0;
        if ( ImpersonateLoggedOnUser(v7) )
        {
          v43 = 0;
          p_TokenHandle = &v40;
          v44 = 1;
          LOBYTE(v21) = *(_DWORD *)(*v11 + 548) == 3;
          LOBYTE(v20) = v34[1];
          LOBYTE(v29) = v34[0];
          v22 = AdjustActivationToken(v7, v46, v20, v21);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v22 >= 0 )
          {
            RevertToSelf();
            if ( !v34[2]
              || (BnoIsolationPrefixForRpc = CreateBnoIsolationPrefixForRpc(
                                               v40,
                                               (unsigned __int16 **)(**(_QWORD **)(a1 + 40) + 8LL)),
                  PackagedAppInfoForFile = BnoIsolationPrefixForRpc,
                  BnoIsolationPrefixForRpc >= 0) )
            {
              v24 = v40;
              v25 = *(_QWORD ***)(a1 + 40);
              v40 = 0;
              **v25 = v24;
              v26 = *v11;
              v27 = AipJustFileName(**(const unsigned __int16 ***)(a1 + 16));
              LUATelemetry::GetPackageActivationTokenForFilePath::Stop(
                (LUATelemetry::GetPackageActivationTokenForFilePath *)v56,
                v27,
                (const unsigned __int16 *)(v26 + 2),
                (const unsigned __int16 *)(v26 + 262));
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
              wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v39);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
              LastError = 0;
              goto LABEL_49;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x173C,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)(unsigned int)BnoIsolationPrefixForRpc,
              (int)v29);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
            goto LABEL_29;
          }
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x1738,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        (const char *)(unsigned int)v22,
                        (int)v29);
          RevertToSelf();
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1723,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        v21);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v39);
        goto LABEL_48;
      }
      v18 = 5918;
    }
    else
    {
      v18 = 5908;
    }
    goto LABEL_28;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x16CB,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)ClientInformation,
                (unsigned int)v29);
LABEL_49:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v49);
  LUATelemetry::GetPackageActivationTokenForFilePath::~GetPackageActivationTokenForFilePath((LUATelemetry::GetPackageActivationTokenForFilePath *)v56);
  return LastError;
}

```

## disassembly

```asm
0x1800286a4  mov     [rsp-8+arg_8], rbx
0x1800286a9  mov     [rsp-8+arg_10], rsi
0x1800286ae  push    rbp
0x1800286af  push    rdi
0x1800286b0  push    r12
0x1800286b2  push    r14
0x1800286b4  push    r15
0x1800286b6  lea     rbp, [rsp-1A0h]
0x1800286be  sub     rsp, 2B0h
0x1800286c5  mov     rax, cs:__security_cookie
0x1800286cc  xor     rax, rsp
0x1800286cf  mov     [rbp+1C0h+var_30], rax
0x1800286d6  mov     rdi, rcx
0x1800286d9  lea     rdx, aGetpackageacti_1; "GetPackageActivationTokenForFilePath"
0x1800286e0  lea     rcx, [rbp+1C0h+var_180]; struct wil::details::IFailureCallback *
0x1800286e4  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800286e9  lea     rax, ??_7GetPackageActivationTokenForFilePath@LUATelemetry@@6B@; const LUATelemetry::GetPackageActivationTokenForFilePath::`vftable'
0x1800286f0  lea     rcx, [rbp+1C0h+var_180]; this
0x1800286f4  mov     [rbp+1C0h+var_180], rax
0x1800286f8  call    ?StartActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXXZ; LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(void)
0x1800286fd  xor     r12d, r12d
0x180028700  mov     [rbp+1C0h+var_200], 1
0x180028704  lea     rax, [rbp+1C0h+TokenHandle]
0x180028708  mov     [rbp+1C0h+var_1E0], r12
0x18002870c  mov     [rbp+1C0h+var_210], rax
0x180028710  lea     r8, [rbp+1C0h+var_208]; void **
0x180028714  lea     rax, [rbp+1C0h+var_1E0]
0x180028718  mov     [rbp+1C0h+TokenHandle], r12
0x18002871c  mov     [rbp+1C0h+var_1D8], rax
0x180028720  lea     rdx, [rbp+1C0h+var_1D0]; void **
0x180028724  mov     rax, [rdi]
0x180028727  xor     r9d, r9d; unsigned int *
0x18002872a  mov     [rbp+1C0h+var_208], r12
0x18002872e  mov     [rbp+1C0h+var_1D0], r12
0x180028732  mov     byte ptr [rbp+1C0h+var_1C8], 1
0x180028736  mov     rcx, [rax]; void *
0x180028739  mov     [rsp+2D0h+var_2B0], r12; int
0x18002873e  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180028743  lea     rcx, [rbp+1C0h+var_1D8]
0x180028747  mov     ebx, eax
0x180028749  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002874e  lea     rcx, [rbp+1C0h+var_210]
0x180028752  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180028757  test    ebx, ebx
0x180028759  jz      short loc_18002877D
0x18002875b  mov     rcx, [rbp+1C8h]; this
0x180028762  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180028769  mov     r9d, ebx; char *
0x18002876c  mov     edx, 16CBh; void *
0x180028771  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028776  mov     ebx, eax
0x180028778  jmp     loc_180028D55
0x18002877d  mov     rsi, [rdi+8]
0x180028781  mov     rcx, [rbp+1C0h+TokenHandle]; TokenHandle
0x180028785  mov     rdx, [rsi]; HANDLE
0x180028788  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x18002878d  mov     ebx, eax
0x18002878f  test    eax, eax
0x180028791  jns     short loc_1800287B3
0x180028793  mov     rcx, [rbp+1C8h]; this
0x18002879a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800287a1  mov     r9d, eax; char *
0x1800287a4  mov     edx, 16CDh; void *
0x1800287a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800287ae  jmp     loc_180028D55
0x1800287b3  cmp     [rsi], r12
0x1800287b6  lea     rcx, [rbp+1C0h+hToken]
0x1800287ba  mov     r14, [rbp+1C0h+TokenHandle]
0x1800287be  cmovnz  r14, [rsi]
0x1800287c2  xor     edx, edx
0x1800287c4  mov     [rbp+1C0h+var_1E8], r12
0x1800287c8  mov     [rbp+1C0h+hToken], r12
0x1800287cc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800287d1  lea     r8, [rbp+1C0h+hToken]; void **
0x1800287d5  mov     rcx, r14; void *
0x1800287d8  lea     rdx, [rbp+1C0h+var_1E8]; unsigned __int64 *
0x1800287dc  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x1800287e1  mov     ebx, eax
0x1800287e3  test    eax, eax
0x1800287e5  jns     short loc_180028807
0x1800287e7  mov     rcx, [rbp+1C8h]; this
0x1800287ee  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800287f5  mov     r9d, eax; char *
0x1800287f8  mov     edx, 16D6h; void *
0x1800287fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028802  jmp     loc_180028D4C
0x180028807  mov     rcx, [rbp+1C0h+hToken]; hToken
0x18002880b  call    cs:__imp_ImpersonateLoggedOnUser
0x180028812  nop     dword ptr [rax+rax+00h]
0x180028817  test    eax, eax
0x180028819  jnz     short loc_18002883A
0x18002881b  mov     rcx, [rbp+1C8h]; this
0x180028822  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180028829  mov     edx, 16D9h; void *
0x18002882e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028833  mov     ebx, eax
0x180028835  jmp     loc_180028D4C
0x18002883a  mov     r15, [rdi+10h]
0x18002883e  xor     r8d, r8d
0x180028841  mov     rbx, [rdi+18h]
0x180028845  mov     rdx, [rbp+1C0h+hToken]
0x180028849  mov     r9, rbx
0x18002884c  mov     rcx, [r15]
0x18002884f  call    cs:__imp_BasepGetPackagedAppInfoForFile
0x180028856  nop     dword ptr [rax+rax+00h]
0x18002885b  mov     esi, eax
0x18002885d  test    eax, eax
0x18002885f  jns     short loc_180028898
0x180028861  mov     edx, 16DCh; void *
0x180028866  mov     rcx, [rbp+1C8h]; this
0x18002886d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180028874  mov     r9d, esi; char *
0x180028877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002887c  call    cs:__imp_RevertToSelf
0x180028883  nop     dword ptr [rax+rax+00h]
0x180028888  lea     rcx, [rbp+1C0h+hToken]
0x18002888c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028891  mov     ebx, esi
0x180028893  jmp     loc_180028D55
0x180028898  mov     rax, [rbx]
0x18002889b  test    rax, rax
0x18002889e  jz      loc_180028D20
0x1800288a4  cmp     [rax], r12b
0x1800288a7  jz      loc_180028D20
0x1800288ad  mov     rcx, [rbp+1C0h+var_1E8]
0x1800288b1  lea     rax, [rbp+1C0h+var_1F8]
0x1800288b5  mov     [rbp+1C0h+var_1F8], r12d
0x1800288b9  xor     r9d, r9d
0x1800288bc  mov     rdx, [rbx]
0x1800288bf  xor     r8d, r8d
0x1800288c2  add     rdx, 2
0x1800288c6  mov     [rsp+2D0h+var_2B0], rax; int
0x1800288cb  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x1800288d2  nop     dword ptr [rax+rax+00h]
0x1800288d7  mov     esi, eax
0x1800288d9  test    eax, eax
0x1800288db  jns     short loc_1800288E4
0x1800288dd  mov     edx, 16E0h
0x1800288e2  jmp     short loc_180028866
0x1800288e4  cmp     [rbp+1C0h+var_1F8], r12d
0x1800288e8  jz      short loc_18002892A
0x1800288ea  mov     rdx, [rbp+1C0h+hToken]
0x1800288ee  mov     r9, rbx
0x1800288f1  mov     rcx, [r15]
0x1800288f4  xor     r8d, r8d
0x1800288f7  call    cs:__imp_BasepGetPackagedAppInfoForFile
0x1800288fe  nop     dword ptr [rax+rax+00h]
0x180028903  mov     esi, eax
0x180028905  test    eax, eax
0x180028907  jns     short loc_180028913
0x180028909  mov     edx, 16E5h
0x18002890e  jmp     loc_180028866
0x180028913  mov     rax, [rbx]
0x180028916  test    rax, rax
0x180028919  jz      short loc_180028920
0x18002891b  cmp     [rax], r12b
0x18002891e  jnz     short loc_18002892A
0x180028920  mov     edx, 16E6h
0x180028925  jmp     loc_180028D25
0x18002892a  call    cs:__imp_RevertToSelf
0x180028931  nop     dword ptr [rax+rax+00h]
0x180028936  mov     r15, [rdi+20h]
0x18002893a  mov     rdx, [rdi+10h]
0x18002893e  mov     [rbp+1C0h+var_208], r12
0x180028942  mov     [rbp+1C0h+var_200], 1
0x180028946  mov     dword ptr [r15], 1
0x18002894d  mov     [rbp+1C0h+var_228], r12
0x180028951  mov     rax, [rbx]
0x180028954  cmp     dword ptr [rax+224h], 4
0x18002895b  lea     rcx, [rax+106h]
0x180028962  mov     rax, [rbp+1C0h+hToken]
0x180028966  jnz     short loc_1800289E4
0x180028968  mov     [rbp+1C0h+var_1D8], rax
0x18002896c  mov     rax, [rbp+1C0h+TokenHandle]
0x180028970  mov     [rbp+1C0h+var_1D0], rax
0x180028974  mov     [rbp+1C0h+var_1B8], r12
0x180028978  mov     [rbp+1C0h+var_1C8], rcx
0x18002897c  lea     rcx, [rbp+1C0h+var_1D8]
0x180028980  mov     rax, [rdx]
0x180028983  lea     rdx, [rbp+1C0h+var_208]
0x180028987  mov     [rbp+1C0h+var_1C0], rax
0x18002898b  mov     eax, r12d
0x18002898e  or      eax, 2
0x180028991  mov     dword ptr [rbp+1C0h+var_1B8], eax
0x180028994  lea     rax, [rbp+1C0h+var_228]
0x180028998  mov     [rbp+1C0h+var_210], rax
0x18002899c  call    cs:__imp_PrepareDesktopAppXActivation
0x1800289a3  nop     dword ptr [rax+rax+00h]
0x1800289a8  lea     rcx, [rbp+1C0h+var_210]
0x1800289ac  mov     esi, eax
0x1800289ae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x1800289b3  test    esi, esi
0x1800289b5  jns     loc_180028A5D
0x1800289bb  mov     edx, 16F7h; void *
0x1800289c0  mov     rcx, [rbp+1C8h]; this
0x1800289c7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800289ce  mov     r9d, esi; char *
0x1800289d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800289d6  lea     rcx, [rbp+1C0h+var_228]
0x1800289da  call    ??1?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x1800289df  jmp     loc_180028888
0x1800289e4  mov     [rbp+1C0h+var_1B0], rax
0x1800289e8  mov     rax, [rbp+1C0h+TokenHandle]
0x1800289ec  mov     [rbp+1C0h+var_1A8], rax
0x1800289f0  mov     [rbp+1C0h+var_1A0], rcx
0x1800289f4  lea     rcx, [rbp+1C0h+var_1B0]
0x1800289f8  mov     [rbp+1C0h+var_190], r12
0x1800289fc  mov     rax, [rdx]
0x1800289ff  lea     rdx, [rbp+1C0h+var_208]
0x180028a03  mov     [rbp+1C0h+var_198], rax
0x180028a07  lea     rax, [rbp+1C0h+var_1F0]
0x180028a0b  mov     [rbp+1C0h+var_210], rax
0x180028a0f  mov     [rbp+1C0h+var_1F0], r12
0x180028a13  call    cs:__imp_PrepareAppXActivation
0x180028a1a  nop     dword ptr [rax+rax+00h]
0x180028a1f  lea     rcx, [rbp+1C0h+var_210]
0x180028a23  mov     esi, eax
0x180028a25  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(void)
0x180028a2a  test    esi, esi
0x180028a2c  jns     short loc_180028A54
0x180028a2e  mov     rcx, [rbp+1C8h]; this
0x180028a35  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180028a3c  mov     r9d, esi; char *
0x180028a3f  mov     edx, 1702h; void *
0x180028a44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a49  lea     rcx, [rbp+1C0h+var_1F0]
0x180028a4d  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x180028a52  jmp     short loc_1800289D6
0x180028a54  lea     rcx, [rbp+1C0h+var_1F0]
0x180028a58  call    ??1?$unique_storage@U?$resource_policy@PEAUAPPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<APPX_LAUNCH_CONTEXT *,void (*)(APPX_LAUNCH_CONTEXT *),&FreeAppXLaunchContext(APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,APPX_LAUNCH_CONTEXT *,APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x180028a5d  mov     [rsp+2D0h+var_290], r12; bool *
0x180028a62  lea     rax, [rbp+1C0h+var_240]
0x180028a66  mov     [rsp+2D0h+var_298], rax; bool *
0x180028a6b  lea     r9, [rbp+1C0h+var_23D]; bool *
0x180028a6f  lea     rax, [rbp+1C0h+var_23F]
0x180028a73  mov     dword ptr [r15], 4
0x180028a7a  mov     rcx, [rbx]
0x180028a7d  lea     rdx, [rbp+1C0h+var_23C]; bool *
0x180028a81  mov     [rsp+2D0h+var_2A0], r12; bool *
0x180028a86  add     rcx, 106h; unsigned __int16 *
0x180028a8d  mov     [rsp+2D0h+var_2A8], rax; bool *
0x180028a92  xor     r8d, r8d; bool *
0x180028a95  lea     rax, [rbp+1C0h+var_23E]
0x180028a99  mov     [rbp+1C0h+var_23C], r12b
0x180028a9d  mov     [rsp+2D0h+var_2B0], rax; bool *
0x180028aa2  mov     [rbp+1C0h+var_23D], r12b
0x180028aa6  mov     [rbp+1C0h+var_23E], r12b
0x180028aaa  mov     [rbp+1C0h+var_23F], r12b
0x180028aae  mov     [rbp+1C0h+var_240], r12b
0x180028ab2  call    ?GetPackageProperties@@YAJPEBGPEA_N1111111@Z; GetPackageProperties(ushort const *,bool *,bool *,bool *,bool *,bool *,bool *,bool *,bool *)
0x180028ab7  mov     esi, eax
0x180028ab9  test    eax, eax
0x180028abb  jns     short loc_180028AC7
0x180028abd  mov     edx, 1714h
0x180028ac2  jmp     loc_1800289C0
0x180028ac7  mov     rcx, [rbp+1C0h+hToken]; void *
0x180028acb  lea     rax, [rbp+1C0h+var_23C+2]
0x180028acf  mov     [rsp+2D0h+var_288], rax; bool *
0x180028ad4  xor     r9d, r9d; unsigned int
0x180028ad7  mov     [rbp+1C0h+var_1F4], r12d
0x180028adb  lea     rax, [rbp+1C0h+var_230]
0x180028adf  mov     [rsp+2D0h+var_290], rax; bool *
0x180028ae4  lea     rax, [rbp+1C0h+var_22F]
0x180028ae8  mov     [rsp+2D0h+var_298], rax; bool *
0x180028aed  lea     rax, [rbp+1C0h+var_22E]
0x180028af1  mov     [rsp+2D0h+var_2A0], rax; bool *
0x180028af6  lea     rax, [rbp+1C0h+var_23C+1]
0x180028afa  mov     [rbp+1C0h+var_23C+1], r12b
0x180028afe  mov     [rbp+1C0h+var_22E], r12b
0x180028b02  mov     [rbp+1C0h+var_22F], r12b
0x180028b06  mov     [rbp+1C0h+var_230], r12b
0x180028b0a  mov     [rbp+1C0h+var_23C+2], r12b
0x180028b0e  mov     rdx, [rbx]
0x180028b11  mov     [rsp+2D0h+var_2A8], rax; bool *
0x180028b16  lea     rax, [rbp+1C0h+var_1F4]
0x180028b1a  mov     [rsp+2D0h+var_2B0], rax; enum AppModel::RuntimeBehavior *
0x180028b1f  mov     r8, [rdx+218h]; unsigned __int16 *
0x180028b26  add     rdx, 2; unsigned __int16 *
0x180028b2a  call    ?GetAppModelIdentityActivationProperties@@YAJPEAXPEBG1KPEAW4RuntimeBehavior@AppModel@@PEA_N3333@Z; GetAppModelIdentityActivationProperties(void *,ushort const *,ushort const *,ulong,AppModel::RuntimeBehavior *,bool *,bool *,bool *,bool *,bool *)
0x180028b2f  mov     esi, eax
0x180028b31  test    eax, eax
0x180028b33  jns     short loc_180028B3F
0x180028b35  mov     edx, 171Eh
0x180028b3a  jmp     loc_1800289C0
0x180028b3f  mov     rcx, r14; hToken
0x180028b42  mov     [rbp+1C0h+var_220], r12
0x180028b46  call    cs:__imp_ImpersonateLoggedOnUser
0x180028b4d  nop     dword ptr [rax+rax+00h]
0x180028b52  test    eax, eax
0x180028b54  jnz     short loc_180028B87
0x180028b56  mov     rcx, [rbp+1C8h]; this
0x180028b5d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180028b64  mov     edx, 1723h; void *
0x180028b69  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028b6e  mov     ebx, eax
0x180028b70  lea     rcx, [rbp+1C0h+var_220]
0x180028b74  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028b79  lea     rcx, [rbp+1C0h+var_228]
0x180028b7d  call    ??1?$unique_storage@U?$resource_policy@PEAUDESKTOP_APPX_LAUNCH_CONTEXT@@P6AXPEAU1@@Z$1?FreeDesktopAppXLaunchContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(void)
0x180028b82  jmp     loc_180028D4C
  ... truncated ...
```
