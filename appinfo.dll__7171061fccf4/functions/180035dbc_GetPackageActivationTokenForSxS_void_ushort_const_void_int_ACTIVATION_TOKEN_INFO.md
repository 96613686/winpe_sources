# GetPackageActivationTokenForSxS(void *,ushort const *,void *,int,_ACTIVATION_TOKEN_INFO *)

- ea: `0x180035dbc`
- end: `0x18003688f`
- name: `?GetPackageActivationTokenForSxS@@YAJPEAXPEBG0HPEAU_ACTIVATION_TOKEN_INFO@@@Z`
- size: `2771`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, void *, int, struct _ACTIVATION_TOKEN_INFO *)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000bcc0`

## callees

- `0x18000720c`
- `0x180009d50`
- `0x18000a938`
- `0x18000b510`
- `0x18000b8f0`
- `0x18000bd90`
- `0x18000bde0`
- `0x18000c410`
- `0x18000de10`
- `0x18000f0ac`
- `0x1800104b0`
- `0x180010510`
- `0x180011414`
- `0x180012c20`
- `0x1800156b0`
- `0x180018190`
- `0x180018228`
- `0x180018dbc`
- `0x18001a0d4`
- `0x18001a594`
- `0x18002ce70`
- `0x180030a50`
- `0x18003130c`
- `0x180035494`
- `0x180035698`
- `0x180035dbc`
- `0x180036898`
- `0x180037274`
- `0x1800379a4`
- `0x180038880`
- `0x18003b9ec`
- `0x18003bbc4`
- `0x18003bd14`
- `0x18003bd54`
- `0x18003be44`
- `0x18003be80`
- `0x180046e1a`
- `0x180046e26`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800360e2`
- `msvcrt!wcsnlen` at `0x1800360fd`
- `msvcrt!wcsnlen` at `0x1800360e2`
- `msvcrt!wcsnlen` at `0x1800360fd`
- `RPCRT4!RpcImpersonateClient` at `0x1800365b2`
- `RPCRT4!RpcImpersonateClient` at `0x1800365b2`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800366ac`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800366ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800366ac`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800366ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003642a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003642a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800363de`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800363de`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180035ffc`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180035ffc`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180036403`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180036403`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003617d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180036251`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800366c8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003617d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180036251`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800366c8`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180035f72`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180035f72`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800361ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800362d9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180036387`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800363c3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800367b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800367bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800361ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800362d9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180036387`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800363c3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800367b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800367bf`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180036537`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180036537`
- `ext-ms-win-desktopappx-l1-1-5!RegisterDesktopAppXPackageFamilyIfNecessary` at `0x1800361c2`
- `ext-ms-win-desktopappx-l1-1-5!RegisterDesktopAppXPackageFamilyIfNecessary` at `0x1800361c2`

## string_xrefs

- `0x180035ea7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180035f3b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180035fad`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003600d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036093`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003614f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036193`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036205`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800362c5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036311`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036399`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800364a8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036553`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003657c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800365c3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180036693`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800366d9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003679e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800367e9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180035dfd`: `GetPackageActivationTokenForSxS`

## pseudocode

```c
__int64 __fastcall GetPackageActivationTokenForSxS(
        void *a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        struct _ACTIVATION_TOKEN_INFO *a5)
{
  bool v8; // r12
  unsigned int ClientInformation; // ebx
  int v10; // ebx
  char IsEnabled; // al
  int v12; // eax
  HANDLE v13; // rdi
  void *v14; // r15
  int UserContextAndUnmodifiedLogonTokenOfTokenUser; // eax
  unsigned int v16; // eax
  int PackageProperties; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int EAAumidIfPresent; // eax
  wchar_t *v21; // r14
  unsigned int v22; // ebx
  int v23; // eax
  void *v24; // rdx
  unsigned int v25; // r8d
  const char *v26; // r9
  __int64 v27; // rdx
  int LastError; // eax
  int v29; // eax
  int v30; // edi
  int AppModelIdentityActivationProperties; // eax
  __int64 v32; // rdx
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // r14d
  int HasProperConditionalACE; // eax
  unsigned int v38; // r8d
  __int64 v39; // rdx
  unsigned int v40; // eax
  int v41; // eax
  void **v42; // r8
  int v43; // ebx
  const char *v44; // r9
  void **v45; // r8
  int v46; // ebx
  _QWORD *v47; // rdi
  int BnoIsolationPrefixForRpc; // eax
  unsigned int v49; // r8d
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-F0h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-F0h]
  unsigned int packageRelativeApplicationIdb; // [rsp+20h] [rbp-F0h]
  bool v54; // [rsp+90h] [rbp-80h] BYREF
  bool v55[4]; // [rsp+91h] [rbp-7Fh] BYREF
  bool v56; // [rsp+95h] [rbp-7Bh] BYREF
  void *v57; // [rsp+98h] [rbp-78h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-70h] BYREF
  bool v59; // [rsp+A8h] [rbp-68h] BYREF
  bool v60; // [rsp+A9h] [rbp-67h] BYREF
  unsigned int v61; // [rsp+ACh] [rbp-64h] BYREF
  bool v62; // [rsp+B0h] [rbp-60h] BYREF
  bool v63; // [rsp+B1h] [rbp-5Fh] BYREF
  bool v64; // [rsp+B2h] [rbp-5Eh] BYREF
  __int64 v65; // [rsp+B8h] [rbp-58h] BYREF
  void *v66; // [rsp+C0h] [rbp-50h] BYREF
  HANDLE *p_TokenHandle; // [rsp+C8h] [rbp-48h] BYREF
  void *v68; // [rsp+D0h] [rbp-40h] BYREF
  char v69; // [rsp+D8h] [rbp-38h]
  wchar_t *Source; // [rsp+E0h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+E8h] [rbp-28h] BYREF
  int v72; // [rsp+F0h] [rbp-20h]
  UINT32 packageFamilyNameLength; // [rsp+F4h] [rbp-1Ch] BYREF
  UINT32 v74; // [rsp+F8h] [rbp-18h] BYREF
  int v75; // [rsp+FCh] [rbp-14h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+100h] [rbp-10h] BYREF
  __int64 v77; // [rsp+108h] [rbp-8h] BYREF
  HANDLE *v78; // [rsp+110h] [rbp+0h] BYREF
  void *v79; // [rsp+118h] [rbp+8h] BYREF
  unsigned __int16 *v80; // [rsp+120h] [rbp+10h]
  __int64 v81; // [rsp+128h] [rbp+18h]
  int v82; // [rsp+130h] [rbp+20h]
  int v83; // [rsp+134h] [rbp+24h]
  struct _ACTIVATION_TOKEN_INFO *v84; // [rsp+138h] [rbp+28h]
  unsigned __int64 v85; // [rsp+140h] [rbp+30h] BYREF
  _QWORD v86[42]; // [rsp+150h] [rbp+40h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+2A0h] [rbp+190h] BYREF
  unsigned __int16 v88[128]; // [rsp+330h] [rbp+220h] BYREF
  WCHAR String2[72]; // [rsp+430h] [rbp+320h] BYREF
  WCHAR v90[72]; // [rsp+4C0h] [rbp+3B0h] BYREF
  WCHAR packageFullName[128]; // [rsp+550h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+698h] [rbp+588h]

  v84 = a5;
  v72 = a4;
  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v86,
    "GetPackageActivationTokenForSxS");
  v86[0] = &LUATelemetry::GetPackageActivationTokenForSxS::`vftable';
  LUATelemetry::GetPackageActivationTokenForSxS::StartActivity((LUATelemetry::GetPackageActivationTokenForSxS *)v86, a2);
  v8 = 0;
  *(_OWORD *)a5 = 0;
  v77 = 0;
  TokenHandle = 0;
  v68 = 0;
  v69 = 1;
  v79 = 0;
  LOBYTE(v80) = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSIVelocityBugLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSIVelocityBugLogging>::GetImpl'::`2'::impl) )
  {
    p_TokenHandle = &TokenHandle;
    v78 = (HANDLE *)&v77;
    ClientInformation = AiGetClientInformation(a1, &v79, &v68, 0, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v78);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
    if ( ClientInformation )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1C72,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)ClientInformation,
              packageRelativeApplicationId);
      goto LABEL_111;
    }
LABEL_7:
    v12 = AccessCheckIncomingToken(TokenHandle, a3);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C75,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v12,
        packageRelativeApplicationId);
      goto LABEL_111;
    }
    v13 = TokenHandle;
    v57 = 0;
    if ( a3 )
      v13 = a3;
    if ( IsTokenIntegrityLevelLessThanMedium(v13) || IsTokenRestricted(v13) )
    {
      v85 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v57,
        0);
      UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v13, &v85, &v57);
      v10 = UserContextAndUnmodifiedLogonTokenOfTokenUser;
      if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C81,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
          packageRelativeApplicationId);
LABEL_16:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v57);
        goto LABEL_111;
      }
      v14 = v57;
    }
    else
    {
      v14 = v13;
    }
    packageFamilyNameLength = 65;
    packageRelativeApplicationIdLength = 65;
    v16 = ParseApplicationUserModelId(
            a2,
            &packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            v90);
    if ( v16 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1C8C,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)v16,
              packageRelativeApplicationIda);
      goto LABEL_16;
    }
    v61 = 0;
    v55[1] = 0;
    v60 = 0;
    memset_0(v88, 0, sizeof(v88));
    v75 = 128;
    v58 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch>::GetImpl'::`2'::impl) )
    {
LABEL_44:
      if ( !ImpersonateLoggedOnUser(v14) )
      {
        v27 = 7357;
LABEL_46:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v27,
                      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                      v26);
LABEL_47:
        v10 = LastError;
        goto LABEL_26;
      }
      packageRelativeApplicationIda = 0;
      v10 = RegisterDesktopAppXPackageFamilyIfNecessary(packageFamilyName, 1, &v75, v88);
      RevertToSelf();
      if ( v10 == -2147009295 )
        goto LABEL_110;
      if ( v10 == -2144927148 )
      {
        v55[0] = 0;
        v29 = IsFamilyProvisioned(packageFamilyName);
        v30 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CDC,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)(unsigned int)v29,
            0);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v57);
          v10 = v30;
          goto LABEL_111;
        }
LABEL_110:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v57);
        v10 = 0;
        goto LABEL_111;
      }
      if ( v10 < 0 )
      {
        v19 = (unsigned int)v10;
        v18 = 7395;
        goto LABEL_25;
      }
      if ( !ImpersonateLoggedOnUser(v14) )
      {
        v27 = 7398;
        goto LABEL_46;
      }
      v64 = 0;
      v63 = 0;
      v62 = 0;
      AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                               v14,
                                               a2,
                                               0,
                                               0,
                                               (enum AppModel::RuntimeBehavior *)&v61,
                                               &v55[1],
                                               &v64,
                                               &v63,
                                               &v62,
                                               &v60);
      v10 = AppModelIdentityActivationProperties;
      if ( AppModelIdentityActivationProperties < 0 )
      {
        v33 = retaddr;
        v34 = (unsigned int)AppModelIdentityActivationProperties;
        v35 = 7406;
LABEL_59:
        wil::details::in1diag3::Return_Hr(
          v33,
          (void *)v35,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)v34,
          packageRelativeApplicationIdb);
LABEL_60:
        RevertToSelf();
        goto LABEL_26;
      }
      LOBYTE(v32) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl,
        v32);
      v36 = 3;
      if ( v55[1] && v61 != 3 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1CF4,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)5,
                packageRelativeApplicationIdb);
        goto LABEL_60;
      }
      if ( ((v61 - 1) & 0xFFFFFFFD) == 0 )
      {
        v54 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch>::GetImpl'::`2'::impl) )
          HasProperConditionalACE = VerifyExecutableHasProperConditionalACE(&v58, a2, &v54);
        else
          HasProperConditionalACE = VerifyExecutableHasProperConditionalACE(v14, a2, &v54);
        v10 = HasProperConditionalACE;
        if ( HasProperConditionalACE < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1D09,
            v38,
            (const char *)(unsigned int)HasProperConditionalACE,
            packageRelativeApplicationIdb);
        if ( !v54 )
        {
          if ( v61 == 1 )
          {
            RevertToSelf();
            goto LABEL_110;
          }
          v33 = retaddr;
          if ( v10 >= 0 )
          {
            v10 = -2147024809;
            v35 = 7445;
            v34 = 2147942487LL;
          }
          else
          {
            v34 = (unsigned int)v10;
            v35 = 7444;
          }
          goto LABEL_59;
        }
      }
      RevertToSelf();
      LODWORD(Source) = 128;
      if ( !GetPackageFullNameFromToken(v13, (UINT32 *)&Source, packageFullName) )
      {
        v74 = 65;
        if ( !PackageFamilyNameFromFullName(packageFullName, &v74, String2) )
          v8 = CompareStringOrdinal(packageFamilyName, packageFamilyNameLength, String2, v74, 1) == 2;
      }
      v55[0] = 0;
      v59 = 0;
      v56 = 0;
      v55[3] = 0;
      v55[2] = 0;
      v54 = 0;
      PackageProperties = GetPackageProperties(v88, v55, &v59, &v56, &v55[3], &v55[2], 0, &v54, 0);
      v10 = PackageProperties;
      if ( PackageProperties < 0 )
      {
        v18 = 7522;
        goto LABEL_24;
      }
      if ( !v59 && !v8 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x1D66,
                      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                      (const char *)5,
                      packageRelativeApplicationIda);
        goto LABEL_47;
      }
      v39 = v61;
      v65 = 0;
      if ( v61 - 1 > 1 )
      {
        if ( v61 != 3 )
        {
          v10 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1D7D,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)0x32,
                  packageRelativeApplicationIda);
          goto LABEL_91;
        }
        LOBYTE(v39) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl,
          v39);
        LODWORD(v39) = v61;
      }
      v79 = TokenHandle;
      v81 = 0;
      v80 = v88;
      v83 = 0;
      if ( (_DWORD)v39 == 2 )
        v36 = 11;
      v78 = (HANDLE *)v14;
      v82 = v36;
      p_TokenHandle = (HANDLE *)&v65;
      v68 = 0;
      v69 = 1;
      v10 = PrepareDesktopAppXActivation(&v78, &v68);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D79,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v10,
          packageRelativeApplicationIda);
LABEL_91:
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v65);
        goto LABEL_26;
      }
      v66 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowILPackagedProcessesCannotBeSpawnedViaSxsManifest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LowILPackagedProcessesCannotBeSpawnedViaSxsManifest>::GetImpl'::`2'::impl) )
      {
        v40 = RpcImpersonateClient(a1);
        if ( v40 )
        {
          v41 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1D84,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)v40,
                  packageRelativeApplicationIda);
LABEL_96:
          v10 = v41;
LABEL_97:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v66);
          goto LABEL_91;
        }
        v42 = &v68;
        LOBYTE(v42) = v55[1];
        p_TokenHandle = &v66;
        v68 = 0;
        v69 = 1;
        LOBYTE(packageRelativeApplicationIda) = v55[0];
        v43 = AdjustActivationToken(v13, v61, v42, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
        if ( v43 < 0 )
        {
          v10 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1D8E,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)(unsigned int)v43,
                  packageRelativeApplicationIda);
          RpcRevertToSelfEx(a1);
          goto LABEL_97;
        }
        RpcRevertToSelfEx(a1);
      }
      else
      {
        if ( !ImpersonateLoggedOnUser(v13) )
        {
          v41 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1D92,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v44);
          goto LABEL_96;
        }
        v45 = &v68;
        LOBYTE(v45) = v55[1];
        p_TokenHandle = &v66;
        v68 = 0;
        v69 = 1;
        LOBYTE(packageRelativeApplicationIda) = v55[0];
        v46 = AdjustActivationToken(v13, v61, v45, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
        if ( v46 < 0 )
        {
          v10 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1D9C,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)(unsigned int)v46,
                  packageRelativeApplicationIda);
          RevertToSelf();
          goto LABEL_97;
        }
        RevertToSelf();
      }
      v47 = v84;
      if ( !v60
        || (BnoIsolationPrefixForRpc = CreateBnoIsolationPrefixForRpc(v66, (unsigned __int16 **)v84 + 1),
            v10 = BnoIsolationPrefixForRpc,
            BnoIsolationPrefixForRpc >= 0) )
      {
        v49 = v61;
        *v47 = v66;
        v66 = 0;
        LUATelemetry::GetPackageActivationTokenForSxS::Stop(
          (LUATelemetry::GetPackageActivationTokenForSxS *)v86,
          v88,
          v49);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v66);
        wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v65);
        goto LABEL_110;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DA1,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)BnoIsolationPrefixForRpc,
        packageRelativeApplicationIda);
      goto LABEL_97;
    }
    PackageProperties = GetFullPathToAUMIDExecutable(v14, a2, &v58);
    v10 = PackageProperties;
    if ( PackageProperties == -2147024809 )
      goto LABEL_110;
    if ( PackageProperties < 0 )
    {
      v18 = 7327;
LABEL_24:
      v19 = (unsigned int)PackageProperties;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)v19,
        packageRelativeApplicationIda);
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
      goto LABEL_16;
    }
    Source = 0;
    EAAumidIfPresent = GetEAAumidIfPresent(v58, &Source);
    v10 = EAAumidIfPresent;
    if ( EAAumidIfPresent == -2146893774 )
    {
      v21 = Source;
      if ( Source )
      {
        if ( a2 )
          v22 = wcsnlen(a2, 0x82u);
        else
          v22 = 0;
        if ( v21 )
          v23 = wcsnlen(v21, 0x82u);
        else
          v23 = 0;
        if ( v23 == v22 && !wcsncmp_0(a2, v21, v22) )
        {
          wil::details::in1diag3::Log_Hr(retaddr, v24, v25, (const char *)0x80090032LL, packageRelativeApplicationIda);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
          goto LABEL_110;
        }
        goto LABEL_43;
      }
    }
    else
    {
      if ( !EAAumidIfPresent || EAAumidIfPresent == -2147023728 )
      {
LABEL_43:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
        goto LABEL_44;
      }
      if ( EAAumidIfPresent >= 0 )
      {
LABEL_42:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
        goto LABEL_26;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB8,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)EAAumidIfPresent,
      packageRelativeApplicationIda);
    goto LABEL_42;
  }
  v78 = &TokenHandle;
  p_TokenHandle = (HANDLE *)&v77;
  v10 = AiGetClientInformation(a1, &v68, &v79, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v78);
  if ( !v10 )
    goto LABEL_7;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::GetImpl'::`2'::impl);
  AipLogGetClientInformationFailureFromTokenForSxs(v10, a2, IsEnabled);
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
LABEL_111:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v77);
  LUATelemetry::GetPackageActivationTokenForSxS::~GetPackageActivationTokenForSxS((LUATelemetry::GetPackageActivationTokenForSxS *)v86);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180035dbc  mov     [rsp-8+arg_18], rbx
0x180035dc1  push    rbp
0x180035dc2  push    rsi
0x180035dc3  push    rdi
0x180035dc4  push    r12
0x180035dc6  push    r13
0x180035dc8  push    r14
0x180035dca  push    r15
0x180035dcc  lea     rbp, [rsp-550h]
0x180035dd4  sub     rsp, 660h
0x180035ddb  mov     rax, cs:__security_cookie
0x180035de2  xor     rax, rsp
0x180035de5  mov     [rbp+580h+var_40], rax
0x180035dec  mov     rbx, [rbp+580h+arg_20]
0x180035df3  mov     rsi, rdx
0x180035df6  mov     r13, rcx
0x180035df9  mov     [rbp+580h+var_558], rbx
0x180035dfd  lea     rdx, aGetpackageacti; "GetPackageActivationTokenForSxS"
0x180035e04  mov     [rbp+580h+var_5A0], r9d
0x180035e08  lea     rcx, [rbp+580h+var_540]
0x180035e0c  mov     r14, r8
0x180035e0f  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180035e14  lea     rax, ??_7GetPackageActivationTokenForSxS@LUATelemetry@@6B@; const LUATelemetry::GetPackageActivationTokenForSxS::`vftable'
0x180035e1b  mov     rdx, rsi; unsigned __int16 *
0x180035e1e  lea     rcx, [rbp+580h+var_540]; this
0x180035e22  mov     [rbp+580h+var_540], rax
0x180035e26  call    ?StartActivity@GetPackageActivationTokenForSxS@LUATelemetry@@QEAAXPEBG@Z; LUATelemetry::GetPackageActivationTokenForSxS::StartActivity(ushort const *)
0x180035e2b  xor     r12d, r12d
0x180035e2e  xorps   xmm0, xmm0
0x180035e31  movups  xmmword ptr [rbx], xmm0
0x180035e34  mov     [rbp+580h+var_588], r12
0x180035e38  mov     [rbp+580h+TokenHandle], r12
0x180035e3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MSIVelocityBugLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MSIVelocityBugLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSIVelocityBugLogging> `wil::Feature<__WilFeatureTraits_Feature_MSIVelocityBugLogging>::GetImpl(void)'::`2'::impl
0x180035e43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MSIVelocityBugLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSIVelocityBugLogging>::__private_IsEnabled(void)
0x180035e48  xor     r9d, r9d; unsigned int *
0x180035e4b  mov     [rbp+580h+var_5C0], r12
0x180035e4f  test    al, al
0x180035e51  mov     [rbp+580h+var_5B8], 1
0x180035e55  lea     rax, [rbp+580h+TokenHandle]
0x180035e59  mov     [rbp+580h+var_578], r12
0x180035e5d  mov     byte ptr [rbp+580h+var_570], 1
0x180035e61  mov     rcx, r13; void *
0x180035e64  mov     [rsp+690h+packageRelativeApplicationId], r12; int
0x180035e69  jnz     short loc_180035EC2
0x180035e6b  mov     [rbp+580h+var_5C8], rax
0x180035e6f  lea     r8, [rbp+580h+var_5C0]; void **
0x180035e73  lea     rax, [rbp+580h+var_588]
0x180035e77  lea     rdx, [rbp+580h+var_578]; void **
0x180035e7b  mov     [rbp+580h+var_580], rax
0x180035e7f  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180035e84  lea     rcx, [rbp+580h+var_580]
0x180035e88  mov     ebx, eax
0x180035e8a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180035e8f  lea     rcx, [rbp+580h+var_5C8]
0x180035e93  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180035e98  test    ebx, ebx
0x180035e9a  jz      loc_180035F22
0x180035ea0  mov     rcx, [rbp+588h]; this
0x180035ea7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035eae  mov     r9d, ebx; char *
0x180035eb1  mov     edx, 1C72h; void *
0x180035eb6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035ebb  mov     ebx, eax
0x180035ebd  jmp     loc_180036848
0x180035ec2  mov     [rbp+580h+var_580], rax
0x180035ec6  lea     r8, [rbp+580h+var_578]; void **
0x180035eca  lea     rax, [rbp+580h+var_588]
0x180035ece  lea     rdx, [rbp+580h+var_5C0]; void **
0x180035ed2  mov     [rbp+580h+var_5C8], rax
0x180035ed6  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180035edb  lea     rcx, [rbp+580h+var_5C8]
0x180035edf  mov     ebx, eax
0x180035ee1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180035ee6  lea     rcx, [rbp+580h+var_580]
0x180035eea  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180035eef  test    ebx, ebx
0x180035ef1  jz      short loc_180035F22
0x180035ef3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook> `wil::Feature<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::GetImpl(void)'::`2'::impl
0x180035efa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoIdentityGenerationHook@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoIdentityGenerationHook>::__private_IsEnabled(void)
0x180035eff  mov     r8b, al; bool
0x180035f02  mov     rdx, rsi; unsigned __int16 *
0x180035f05  mov     ecx, ebx; unsigned int
0x180035f07  call    ?AipLogGetClientInformationFailureFromTokenForSxs@@YAXKPEBG_N@Z; AipLogGetClientInformationFailureFromTokenForSxs(ulong,ushort const *,bool)
0x180035f0c  test    ebx, ebx
0x180035f0e  jle     loc_180036848
0x180035f14  movzx   ebx, bx
0x180035f17  or      ebx, 80070000h
0x180035f1d  jmp     loc_180036848
0x180035f22  mov     rcx, [rbp+580h+TokenHandle]; TokenHandle
0x180035f26  mov     rdx, r14; HANDLE
0x180035f29  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x180035f2e  mov     ebx, eax
0x180035f30  test    eax, eax
0x180035f32  jns     short loc_180035F54
0x180035f34  mov     rcx, [rbp+588h]; this
0x180035f3b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035f42  mov     r9d, eax; char *
0x180035f45  mov     edx, 1C75h; void *
0x180035f4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f4f  jmp     loc_180036848
0x180035f54  mov     rdi, [rbp+580h+TokenHandle]
0x180035f58  test    r14, r14
0x180035f5b  mov     [rbp+580h+var_5F8], r12
0x180035f5f  cmovnz  rdi, r14
0x180035f63  mov     rcx, rdi; void *
0x180035f66  call    ?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z; IsTokenIntegrityLevelLessThanMedium(void *)
0x180035f6b  test    al, al
0x180035f6d  jnz     short loc_180035F81
0x180035f6f  mov     rcx, rdi; TokenHandle
0x180035f72  call    cs:__imp_IsTokenRestricted
0x180035f78  test    eax, eax
0x180035f7a  jnz     short loc_180035F81
0x180035f7c  mov     r15, rdi
0x180035f7f  jmp     short loc_180035FD3
0x180035f81  xor     edx, edx
0x180035f83  mov     [rbp+580h+var_550], r12
0x180035f87  lea     rcx, [rbp+580h+var_5F8]
0x180035f8b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180035f90  lea     r8, [rbp+580h+var_5F8]; void **
0x180035f94  mov     rcx, rdi; void *
0x180035f97  lea     rdx, [rbp+580h+var_550]; unsigned __int64 *
0x180035f9b  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x180035fa0  mov     ebx, eax
0x180035fa2  test    eax, eax
0x180035fa4  jns     short loc_180035FCF
0x180035fa6  mov     rcx, [rbp+588h]; this
0x180035fad  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035fb4  mov     r9d, eax; char *
0x180035fb7  mov     edx, 1C81h; void *
0x180035fbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035fc1  lea     rcx, [rbp+580h+var_5F8]
0x180035fc5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180035fca  jmp     loc_180036848
0x180035fcf  mov     r15, [rbp+580h+var_5F8]
0x180035fd3  mov     eax, 41h ; 'A'
0x180035fd8  lea     r9, [rbp+580h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180035fdc  mov     [rbp+580h+packageFamilyNameLength], eax
0x180035fdf  lea     r8, [rbp+580h+packageFamilyName]; packageFamilyName
0x180035fe6  mov     [rbp+580h+packageRelativeApplicationIdLength], eax
0x180035fe9  lea     rdx, [rbp+580h+packageFamilyNameLength]; packageFamilyNameLength
0x180035fed  lea     rax, [rbp+580h+var_1D0]
0x180035ff4  mov     rcx, rsi; applicationUserModelId
0x180035ff7  mov     [rsp+690h+packageRelativeApplicationId], rax; int
0x180035ffc  call    cs:__imp_ParseApplicationUserModelId
0x180036002  test    eax, eax
0x180036004  jz      short loc_180036025
0x180036006  mov     rcx, [rbp+588h]; this
0x18003600d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180036014  mov     r9d, eax; char *
0x180036017  mov     edx, 1C8Ch; void *
0x18003601c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036021  mov     ebx, eax
0x180036023  jmp     short loc_180035FC1
0x180036025  xor     edx, edx; Val
0x180036027  mov     [rbp+580h+var_5E4], r12d
0x18003602b  mov     r8d, 100h; Size
0x180036031  mov     [rbp+580h+var_5FF+1], r12b
0x180036035  lea     rcx, [rbp+580h+var_360]; void *
0x18003603c  mov     [rbp+580h+var_5E7], r12b
0x180036040  call    memset_0
0x180036045  mov     [rbp+580h+var_594], 80h
0x18003604c  mov     [rbp+580h+var_5F0], r12
0x180036050  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoGeneratedIdLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGeneratedIdLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch> `wil::Feature<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch>::GetImpl(void)'::`2'::impl
0x180036057  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGeneratedIdLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGeneratedIdLaunch>::__private_IsEnabled(void)
0x18003605c  test    al, al
0x18003605e  jz      loc_18003617A
0x180036064  lea     r8, [rbp+580h+var_5F0]
0x180036068  mov     rdx, rsi
0x18003606b  mov     rcx, r15
0x18003606e  call    ?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180036073  mov     ebx, eax
0x180036075  cmp     eax, 80070057h
0x18003607a  jz      loc_180036833
0x180036080  test    eax, eax
0x180036082  jns     short loc_1800360AD
0x180036084  mov     edx, 1C9Fh; void *
0x180036089  mov     r9d, eax; char *
0x18003608c  mov     rcx, [rbp+588h]; this
0x180036093  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003609a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003609f  lea     rcx, [rbp+580h+var_5F0]
0x1800360a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800360a8  jmp     loc_180035FC1
0x1800360ad  mov     rcx, [rbp+580h+var_5F0]
0x1800360b1  lea     rdx, [rbp+580h+Source]
0x1800360b5  mov     [rbp+580h+Source], r12
0x1800360b9  call    ?GetEAAumidIfPresent@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetEAAumidIfPresent(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800360be  mov     ebx, eax
0x1800360c0  cmp     eax, 80090032h
0x1800360c5  jnz     short loc_180036139
0x1800360c7  mov     r14, [rbp+580h+Source]
0x1800360cb  test    r14, r14
0x1800360ce  jz      short loc_180036148
0x1800360d0  test    rsi, rsi
0x1800360d3  jnz     short loc_1800360DA
0x1800360d5  mov     rbx, r12
0x1800360d8  jmp     short loc_1800360EB
0x1800360da  mov     edx, 82h; MaxCount
0x1800360df  mov     rcx, rsi; Source
0x1800360e2  call    cs:__imp_wcsnlen
0x1800360e8  mov     rbx, rax
0x1800360eb  test    r14, r14
0x1800360ee  jnz     short loc_1800360F5
0x1800360f0  mov     rax, r12
0x1800360f3  jmp     short loc_180036103
0x1800360f5  mov     edx, 82h; MaxCount
0x1800360fa  mov     rcx, r14; Source
0x1800360fd  call    cs:__imp_wcsnlen
0x180036103  cmp     eax, ebx
0x180036105  jnz     short loc_180036171
0x180036107  mov     r8d, ebx; MaxCount
0x18003610a  mov     rdx, r14; String2
0x18003610d  mov     rcx, rsi; String1
0x180036110  call    wcsncmp_0
0x180036115  test    eax, eax
0x180036117  jnz     short loc_180036171
0x180036119  mov     rcx, [rbp+588h]; this
0x180036120  mov     r9d, 80090032h; char *
0x180036126  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003612b  lea     rcx, [rbp+580h+Source]
0x18003612f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036134  jmp     loc_180036833
0x180036139  test    eax, eax
0x18003613b  jz      short loc_180036171
0x18003613d  cmp     eax, 80070490h
0x180036142  jz      short loc_180036171
0x180036144  test    eax, eax
0x180036146  jns     short loc_180036163
0x180036148  mov     rcx, [rbp+588h]; this
0x18003614f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180036156  mov     r9d, eax; char *
0x180036159  mov     edx, 1CB8h; void *
0x18003615e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036163  lea     rcx, [rbp+580h+Source]
0x180036167  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003616c  jmp     loc_18003609F
0x180036171  lea     rcx, [rbp+580h+Source]
0x180036175  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003617a  mov     rcx, r15; hToken
0x18003617d  call    cs:__imp_ImpersonateLoggedOnUser
0x180036183  test    eax, eax
0x180036185  jnz     short loc_1800361A6
0x180036187  mov     edx, 1CBDh; void *
0x18003618c  mov     rcx, [rbp+588h]; this
0x180036193  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003619a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003619f  mov     ebx, eax
0x1800361a1  jmp     loc_18003609F
0x1800361a6  lea     r9, [rbp+580h+var_360]
0x1800361ad  mov     [rsp+690h+packageRelativeApplicationId], r12; int
0x1800361b2  lea     r8, [rbp+580h+var_594]
0x1800361b6  mov     edx, 1
0x1800361bb  lea     rcx, [rbp+580h+packageFamilyName]
0x1800361c2  call    cs:__imp_RegisterDesktopAppXPackageFamilyIfNecessary
0x1800361c8  mov     ebx, eax
0x1800361ca  call    cs:__imp_RevertToSelf
0x1800361d0  cmp     ebx, 80073CF1h
0x1800361d6  jz      loc_180036833
0x1800361dc  cmp     ebx, 80270254h
0x1800361e2  jnz     short loc_18003623D
0x1800361e4  lea     rdx, [rbp+580h+var_5FF]
0x1800361e8  mov     [rbp+580h+var_5FF], r12b
0x1800361ec  lea     rcx, [rbp+580h+packageFamilyName]; lpString2
0x1800361f3  call    IsFamilyProvisioned
0x1800361f8  mov     edi, eax
0x1800361fa  test    eax, eax
0x1800361fc  jns     short loc_180036232
0x1800361fe  mov     rcx, [rbp+588h]; this
0x180036205  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003620c  mov     r9d, eax; char *
0x18003620f  mov     edx, 1CDCh; void *
0x180036214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036219  lea     rcx, [rbp+580h+var_5F0]
0x18003621d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036222  lea     rcx, [rbp+580h+var_5F8]
0x180036226  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003622b  mov     ebx, edi
0x18003622d  jmp     loc_180036848
0x180036232  cmp     [rbp+580h+var_5FF], r12b
0x180036236  jnz     short loc_180036241
0x180036238  jmp     loc_180036833
0x18003623d  test    ebx, ebx
0x18003623f  jns     short loc_18003624E
0x180036241  mov     r9d, ebx
0x180036244  mov     edx, 1CE3h
0x180036249  jmp     loc_18003608C
0x18003624e  mov     rcx, r15; hToken
0x180036251  call    cs:__imp_ImpersonateLoggedOnUser
0x180036257  test    eax, eax
0x180036259  jnz     short loc_180036265
0x18003625b  mov     edx, 1CE6h
0x180036260  jmp     loc_18003618C
0x180036265  lea     rax, [rbp+580h+var_5E7]
0x180036269  mov     [rbp+580h+var_5DE], r12b
0x18003626d  mov     [rsp+690h+var_648], rax; bool *
0x180036272  xor     r9d, r9d; unsigned int
0x180036275  lea     rax, [rbp+580h+var_5E0]
0x180036279  mov     [rbp+580h+var_5DF], r12b
0x18003627d  mov     [rsp+690h+var_650], rax; bool *
0x180036282  xor     r8d, r8d; unsigned __int16 *
  ... truncated ...
```
