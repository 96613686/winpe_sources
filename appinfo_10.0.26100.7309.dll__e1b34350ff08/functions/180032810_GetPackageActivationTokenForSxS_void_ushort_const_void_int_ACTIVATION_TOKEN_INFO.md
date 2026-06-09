# GetPackageActivationTokenForSxS(void *,ushort const *,void *,int,_ACTIVATION_TOKEN_INFO *)

- ea: `0x180032810`
- end: `0x1800333f7`
- name: `?GetPackageActivationTokenForSxS@@YAJPEAXPEBG0HPEAU_ACTIVATION_TOKEN_INFO@@@Z`
- size: `3047`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, const unsigned __int16 *@<rdx>, void *@<r8>, int@<r9d>, struct _ACTIVATION_TOKEN_INFO *)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c6a0`

## callees

- `0x180007c78`
- `0x1800092f0`
- `0x18000a230`
- `0x18000bb10`
- `0x18000be90`
- `0x18000c4c0`
- `0x18000c790`
- `0x18000cb60`
- `0x18000f760`
- `0x18000f9e0`
- `0x1800109a0`
- `0x1800109d0`
- `0x180011ce0`
- `0x180012634`
- `0x180012cdc`
- `0x180018400`
- `0x18001847c`
- `0x180018530`
- `0x18001891c`
- `0x18002017c`
- `0x180029110`
- `0x18002cb30`
- `0x180031f0c`
- `0x180032118`
- `0x180032810`
- `0x180033538`
- `0x180033f1c`
- `0x180038cac`
- `0x180038de0`
- `0x18003944c`
- `0x180039554`
- `0x180039590`
- `0x1800396f8`
- `0x18003c660`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180032aea`
- `msvcrt!wcsncmp` at `0x180032aea`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003323b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003324f`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003323b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003324f`
- `RPCRT4!RpcImpersonateClient` at `0x18003313e`
- `RPCRT4!RpcImpersonateClient` at `0x18003313e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032bc1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032c95`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180033263`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032bc1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032c95`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180033263`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180032957`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180032957`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032c1a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032d23`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e7d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033352`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033363`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032c1a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032d23`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e7d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033352`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180033363`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032f05`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032f05`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800329e5`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800329e5`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180032eaf`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180032eaf`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180032ed8`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180032ed8`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180033033`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x1800330df`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180033033`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x1800330df`
- `ext-ms-win-desktopappx-l1-1-5!RegisterDesktopAppXPackageFamilyIfNecessary` at `0x180032c0c`
- `ext-ms-win-desktopappx-l1-1-5!RegisterDesktopAppXPackageFamilyIfNecessary` at `0x180032c0c`

## string_xrefs

- `0x1800328e7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003291b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032993`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800329fc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032a81`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032b07`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032b9a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032bdd`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032c5b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032d0f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032d62`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032de8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032f8f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033068`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033106`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033155`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033222`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003327a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003333c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033393`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032851`: `GetPackageActivationTokenForSxS`

## pseudocode

```c
__int64 __fastcall GetPackageActivationTokenForSxS(
        void *a1,
        const unsigned __int16 *a2,
        void *a3,
        UINT32 a4,
        struct _ACTIVATION_TOKEN_INFO *a5)
{
  unsigned int ClientInformation; // ebx
  int v9; // ebx
  int v10; // eax
  HANDLE v11; // rsi
  int v12; // edi
  void *v13; // r14
  int UserContextAndUnmodifiedLogonTokenOfTokenUser; // eax
  bool v15; // r12
  unsigned int v16; // eax
  int PackageProperties; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int EAAumidIfPresent; // eax
  size_t v21; // rdx
  wchar_t *v22; // rbx
  unsigned int v23; // edi
  size_t v24; // rdx
  int v25; // eax
  const char *v27; // r9
  __int64 v28; // rdx
  int LastError; // eax
  int v30; // eax
  int AppModelIdentityActivationProperties; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rdx
  int HasProperConditionalACE; // eax
  unsigned int v37; // r8d
  int v38; // eax
  unsigned int v39; // r8d
  __int64 v40; // rdx
  int v41; // eax
  int v42; // ecx
  __int64 v43; // rdx
  __int64 v44; // rdx
  int v45; // eax
  int v46; // ecx
  unsigned int v47; // eax
  __int64 v48; // r8
  int v49; // eax
  int v50; // ebx
  __int64 v51; // r8
  const char *v52; // r9
  int v53; // ebx
  struct _ACTIVATION_TOKEN_INFO *v54; // rdi
  int BnoIsolationPrefixForRpc; // eax
  void *v56; // rax
  unsigned int v57; // r8d
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-F0h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-F0h]
  unsigned int packageRelativeApplicationIdb; // [rsp+20h] [rbp-F0h]
  bool v61; // [rsp+90h] [rbp-80h] BYREF
  bool v62[4]; // [rsp+91h] [rbp-7Fh] BYREF
  bool v63; // [rsp+95h] [rbp-7Bh] BYREF
  void *v64; // [rsp+98h] [rbp-78h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-70h] BYREF
  bool v66; // [rsp+A8h] [rbp-68h] BYREF
  bool v67; // [rsp+A9h] [rbp-67h] BYREF
  unsigned int v68; // [rsp+ACh] [rbp-64h] BYREF
  bool v69; // [rsp+B0h] [rbp-60h] BYREF
  bool v70; // [rsp+B1h] [rbp-5Fh] BYREF
  bool v71; // [rsp+B2h] [rbp-5Eh] BYREF
  __int64 v72; // [rsp+B8h] [rbp-58h] BYREF
  void *v73; // [rsp+C0h] [rbp-50h] BYREF
  HANDLE *p_TokenHandle; // [rsp+C8h] [rbp-48h] BYREF
  void *v75; // [rsp+D0h] [rbp-40h] BYREF
  char v76; // [rsp+D8h] [rbp-38h]
  wchar_t *Source; // [rsp+E0h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+E8h] [rbp-28h] BYREF
  UINT32 v79; // [rsp+F0h] [rbp-20h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+F4h] [rbp-1Ch] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+FCh] [rbp-14h] BYREF
  int v82; // [rsp+100h] [rbp-10h] BYREF
  struct _ACTIVATION_TOKEN_INFO *v83; // [rsp+108h] [rbp-8h]
  __int64 v84; // [rsp+110h] [rbp+0h] BYREF
  __int64 *v85; // [rsp+118h] [rbp+8h] BYREF
  void *v86; // [rsp+120h] [rbp+10h] BYREF
  unsigned __int16 *v87; // [rsp+128h] [rbp+18h]
  __int128 v88; // [rsp+130h] [rbp+20h]
  unsigned __int64 v89; // [rsp+140h] [rbp+30h] BYREF
  _QWORD v90[3]; // [rsp+148h] [rbp+38h] BYREF
  __int128 v91; // [rsp+160h] [rbp+50h]
  _QWORD v92[42]; // [rsp+180h] [rbp+70h] BYREF
  unsigned __int16 v93[128]; // [rsp+2D0h] [rbp+1C0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+3D0h] [rbp+2C0h] BYREF
  WCHAR String2[72]; // [rsp+460h] [rbp+350h] BYREF
  WCHAR v96[72]; // [rsp+4F0h] [rbp+3E0h] BYREF
  WCHAR packageFullName[128]; // [rsp+580h] [rbp+470h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5B8h]

  v83 = a5;
  packageFamilyNameLength[1] = a4;
  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v92);
  v92[0] = &LUATelemetry::GetPackageActivationTokenForSxS::`vftable';
  LUATelemetry::GetPackageActivationTokenForSxS::StartActivity((LUATelemetry::GetPackageActivationTokenForSxS *)v92, a2);
  v76 = 1;
  v84 = 0;
  p_TokenHandle = &TokenHandle;
  TokenHandle = 0;
  v85 = &v84;
  v75 = 0;
  v86 = 0;
  LOBYTE(v87) = 1;
  *(_OWORD *)a5 = 0;
  ClientInformation = AiGetClientInformation(a1, &v86, &v75, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v85);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( !ClientInformation )
  {
    v10 = AccessCheckIncomingToken(TokenHandle, a3);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E4,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v10,
        packageRelativeApplicationId);
      goto LABEL_29;
    }
    v11 = TokenHandle;
    if ( a3 )
      v11 = a3;
    v12 = 0;
    v64 = 0;
    v13 = v11;
    if ( IsTokenIntegrityLevelLessThanMedium(v11) || IsTokenRestricted(v11) )
    {
      v89 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v64,
        0);
      UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v11, &v89, &v64);
      v9 = UserContextAndUnmodifiedLogonTokenOfTokenUser;
      if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19F0,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
          packageRelativeApplicationId);
LABEL_11:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v64);
        goto LABEL_29;
      }
      v13 = v64;
    }
    packageFamilyNameLength[0] = 65;
    packageRelativeApplicationIdLength = 65;
    v15 = 0;
    v16 = ParseApplicationUserModelId(
            a2,
            packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            v96);
    if ( v16 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x19FB,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)v16,
             packageRelativeApplicationIda);
      goto LABEL_11;
    }
    v68 = 0;
    v62[1] = 0;
    v67 = 0;
    memset_0(v93, 0, sizeof(v93));
    v82 = 128;
    v65 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl'::`2'::impl) )
    {
LABEL_36:
      if ( !ImpersonateLoggedOnUser(v13) )
      {
        v28 = 6700;
LABEL_38:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v28,
                      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                      v27);
LABEL_39:
        v9 = LastError;
        goto LABEL_21;
      }
      packageRelativeApplicationIda = 0;
      v9 = RegisterDesktopAppXPackageFamilyIfNecessary(packageFamilyName, 1, &v82, v93);
      RevertToSelf();
      if ( v9 == -2147009295 )
        goto LABEL_28;
      if ( v9 == -2144927148 )
      {
        v62[0] = 0;
        v30 = IsFamilyProvisioned(packageFamilyName);
        v12 = v30;
        if ( v30 >= 0 )
          v12 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A4B,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)(unsigned int)v30,
            0);
        goto LABEL_28;
      }
      if ( v9 < 0 )
      {
        v19 = (unsigned int)v9;
        v18 = 6738;
        goto LABEL_20;
      }
      if ( !ImpersonateLoggedOnUser(v13) )
      {
        v28 = 6741;
        goto LABEL_38;
      }
      v71 = 0;
      v70 = 0;
      v69 = 0;
      AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                               v13,
                                               a2,
                                               0,
                                               0,
                                               (enum AppModel::RuntimeBehavior *)&v68,
                                               &v62[1],
                                               &v71,
                                               &v70,
                                               &v69,
                                               &v67);
      v9 = AppModelIdentityActivationProperties;
      if ( AppModelIdentityActivationProperties < 0 )
      {
        v32 = retaddr;
        v33 = (unsigned int)AppModelIdentityActivationProperties;
        v34 = 6749;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          v32,
          (void *)v34,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)v33,
          packageRelativeApplicationIdb);
LABEL_52:
        RevertToSelf();
        goto LABEL_21;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
      {
        if ( v62[1] && v68 != 3 )
        {
          v35 = 6755;
LABEL_57:
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v35,
                 (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                 (const char *)5,
                 packageRelativeApplicationIdb);
          goto LABEL_52;
        }
        if ( ((v68 - 1) & 0xFFFFFFFD) == 0 )
        {
          v61 = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl'::`2'::impl) )
            HasProperConditionalACE = VerifyExecutableHasProperConditionalACE(&v65, a2, &v61);
          else
            HasProperConditionalACE = VerifyExecutableHasProperConditionalACE(v13, a2, &v61);
          v9 = HasProperConditionalACE;
          if ( HasProperConditionalACE < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1A78,
              v37,
              (const char *)(unsigned int)HasProperConditionalACE,
              packageRelativeApplicationIdb);
          if ( !v61 )
          {
            if ( v68 != 1 )
            {
              v32 = retaddr;
              if ( v9 >= 0 )
              {
                v9 = -2147024809;
                v34 = 6788;
                v33 = 2147942487LL;
              }
              else
              {
                v33 = (unsigned int)v9;
                v34 = 6787;
              }
              goto LABEL_51;
            }
LABEL_79:
            RevertToSelf();
            goto LABEL_28;
          }
        }
LABEL_80:
        RevertToSelf();
        LODWORD(Source) = 128;
        if ( !GetPackageFullNameFromToken(v11, (UINT32 *)&Source, packageFullName) )
        {
          v79 = 65;
          if ( !PackageFamilyNameFromFullName(packageFullName, &v79, String2) )
            v15 = CompareStringOrdinal(packageFamilyName, packageFamilyNameLength[0], String2, v79, 1) == 2;
        }
        v62[0] = 0;
        v66 = 0;
        v63 = 0;
        v62[3] = 0;
        v62[2] = 0;
        v61 = 0;
        PackageProperties = GetPackageProperties(v93, v62, &v66, &v63, &v62[3], &v62[2], 0, &v61, 0);
        v9 = PackageProperties;
        if ( PackageProperties < 0 )
        {
          v18 = 6865;
          goto LABEL_19;
        }
        if ( !v66 && !v15 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1AD5,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        (const char *)5,
                        packageRelativeApplicationIda);
          goto LABEL_39;
        }
        v72 = 0;
        if ( v68 - 1 > 1 )
        {
          if ( v68 == 3 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
            {
              v86 = TokenHandle;
              v88 = 0;
              v87 = v93;
              v41 = 0;
              v85 = (__int64 *)v13;
              v75 = 0;
              v42 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) | 3;
              v76 = 1;
              if ( v68 == 2 )
                v41 = 8;
              DWORD2(v88) = v42 | v41;
              p_TokenHandle = (HANDLE *)&v72;
              v9 = PrepareDesktopAppXActivation(&v85, &v75);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
              if ( v9 < 0 )
              {
                v43 = 6902;
LABEL_102:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v43,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)(unsigned int)v9,
                  packageRelativeApplicationIda);
                goto LABEL_103;
              }
              goto LABEL_104;
            }
            v44 = 6906;
          }
          else
          {
            v44 = 6911;
          }
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v44,
                 (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                 (const char *)0x32,
                 packageRelativeApplicationIda);
LABEL_103:
          wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v72);
          goto LABEL_21;
        }
        v90[1] = TokenHandle;
        v91 = 0;
        v90[0] = v13;
        v90[2] = v93;
        v45 = 0;
        v75 = 0;
        v76 = 1;
        v46 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) | 3;
        if ( v68 == 2 )
          v45 = 8;
        DWORD2(v91) = v46 | v45;
        p_TokenHandle = (HANDLE *)&v72;
        v9 = PrepareDesktopAppXActivation(v90, &v75);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
        if ( v9 < 0 )
        {
          v43 = 6886;
          goto LABEL_102;
        }
LABEL_104:
        v73 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowILPackagedProcessesCannotBeSpawnedViaSxsManifest>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_LowILPackagedProcessesCannotBeSpawnedViaSxsManifest>::GetImpl'::`2'::impl) )
        {
          v47 = RpcImpersonateClient(a1);
          if ( v47 )
          {
            v49 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x1B06,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    (const char *)v47,
                    packageRelativeApplicationIda);
LABEL_107:
            v9 = v49;
LABEL_108:
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v73);
            goto LABEL_103;
          }
          p_TokenHandle = &v73;
          v75 = 0;
          v76 = 1;
          LOBYTE(v48) = v62[1];
          LOBYTE(packageRelativeApplicationIda) = v62[0];
          v50 = AdjustActivationToken(v11, v68, v48, 0);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v50 < 0 )
          {
            v9 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x1B10,
                   (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                   (const char *)(unsigned int)v50,
                   packageRelativeApplicationIda);
            RpcRevertToSelfEx(a1);
            goto LABEL_108;
          }
          RpcRevertToSelfEx(a1);
        }
        else
        {
          if ( !ImpersonateLoggedOnUser(v11) )
          {
            v49 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1B14,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v52);
            goto LABEL_107;
          }
          p_TokenHandle = &v73;
          v75 = 0;
          v76 = 1;
          LOBYTE(v51) = v62[1];
          LOBYTE(packageRelativeApplicationIda) = v62[0];
          v53 = AdjustActivationToken(v11, v68, v51, 0);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v53 < 0 )
          {
            v9 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x1B1E,
                   (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                   (const char *)(unsigned int)v53,
                   packageRelativeApplicationIda);
            RevertToSelf();
            goto LABEL_108;
          }
          RevertToSelf();
        }
        v54 = v83;
        if ( !v67
          || (BnoIsolationPrefixForRpc = CreateBnoIsolationPrefixForRpc(v73, (unsigned __int16 **)v83 + 1),
              v9 = BnoIsolationPrefixForRpc,
              BnoIsolationPrefixForRpc >= 0) )
        {
          v56 = v73;
          v57 = v68;
          v73 = 0;
          *(_QWORD *)v54 = v56;
          LUATelemetry::GetPackageActivationTokenForSxS::Stop(
            (LUATelemetry::GetPackageActivationTokenForSxS *)v92,
            v93,
            v57);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v73);
          wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v64);
          v9 = 0;
          goto LABEL_29;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B23,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)BnoIsolationPrefixForRpc,
          packageRelativeApplicationIda);
        goto LABEL_108;
      }
      if ( v62[1] )
      {
        v35 = 6796;
        goto LABEL_57;
      }
      if ( v68 != 1 )
        goto LABEL_80;
      v61 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl'::`2'::impl) )
      {
        v38 = VerifyExecutableHasProperConditionalACE(&v65, a2, &v61);
        if ( v38 >= 0 )
          goto LABEL_78;
        v40 = 6812;
      }
      else
      {
        v38 = VerifyExecutableHasProperConditionalACE(v13, a2, &v61);
        if ( v38 >= 0 )
          goto LABEL_78;
        v40 = 6816;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v40,
        v39,
        (const char *)(unsigned int)v38,
        packageRelativeApplicationIdb);
LABEL_78:
      if ( !v61 )
        goto LABEL_79;
      goto LABEL_80;
    }
    PackageProperties = GetFullPathToAUMIDExecutable(v13, a2, &v65);
    v9 = PackageProperties;
    if ( PackageProperties == -2147024809 )
    {
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v64);
      v9 = v12;
      goto LABEL_29;
    }
    if ( PackageProperties < 0 )
    {
      v18 = 6670;
LABEL_19:
      v19 = (unsigned int)PackageProperties;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)v19,
        packageRelativeApplicationIda);
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
      goto LABEL_11;
    }
    Source = 0;
    EAAumidIfPresent = GetEAAumidIfPresent(v65, &Source);
    v12 = EAAumidIfPresent;
    if ( EAAumidIfPresent == -2146893774 )
    {
      v22 = Source;
      if ( Source )
      {
        v23 = wcsnlen_s(a2, v21);
        if ( (unsigned int)wcsnlen_s(v22, v24) == v23 )
        {
          v25 = wcsncmp(a2, v22, v23);
          v12 = 0;
          if ( !v25 )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x1A20,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)0x80090032LL,
              packageRelativeApplicationIda);
LABEL_27:
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
            goto LABEL_28;
          }
          goto LABEL_35;
        }
LABEL_34:
        v12 = 0;
LABEL_35:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
        goto LABEL_36;
      }
    }
    else
    {
      if ( !EAAumidIfPresent || EAAumidIfPresent == -2147023728 )
        goto LABEL_34;
      if ( EAAumidIfPresent >= 0 )
        goto LABEL_27;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A27,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)EAAumidIfPresent,
      packageRelativeApplicationIda);
    goto LABEL_27;
  }
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x19E2,
         (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
         (const char *)ClientInformation,
         packageRelativeApplicationId);
LABEL_29:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v84);
  LUATelemetry::GetPackageActivationTokenForSxS::~GetPackageActivationTokenForSxS((LUATelemetry::GetPackageActivationTokenForSxS *)v92);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180032810  mov     [rsp-8+arg_18], rbx
0x180032815  push    rbp
0x180032816  push    rsi
0x180032817  push    rdi
0x180032818  push    r12
0x18003281a  push    r13
0x18003281c  push    r14
0x18003281e  push    r15
0x180032820  lea     rbp, [rsp-580h]
0x180032828  sub     rsp, 690h
0x18003282f  mov     rax, cs:__security_cookie
0x180032836  xor     rax, rsp
0x180032839  mov     [rbp+5B0h+var_40], rax
0x180032840  mov     rbx, [rbp+5B0h+arg_20]
0x180032847  mov     r15, rdx
0x18003284a  mov     r13, rcx
0x18003284d  mov     [rbp+5B0h+var_5B8], rbx
0x180032851  lea     rdx, aGetpackageacti; "GetPackageActivationTokenForSxS"
0x180032858  mov     [rbp+5B0h+var_5C8], r9d
0x18003285c  lea     rcx, [rbp+5B0h+var_540]; struct wil::details::IFailureCallback *
0x180032860  mov     rdi, r8
0x180032863  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180032868  lea     rax, ??_7GetPackageActivationTokenForSxS@LUATelemetry@@6B@; const LUATelemetry::GetPackageActivationTokenForSxS::`vftable'
0x18003286f  mov     rdx, r15; unsigned __int16 *
0x180032872  lea     rcx, [rbp+5B0h+var_540]; this
0x180032876  mov     [rbp+5B0h+var_540], rax
0x18003287a  call    ?StartActivity@GetPackageActivationTokenForSxS@LUATelemetry@@QEAAXPEBG@Z; LUATelemetry::GetPackageActivationTokenForSxS::StartActivity(ushort const *)
0x18003287f  xor     r14d, r14d
0x180032882  mov     [rbp+5B0h+var_5E8], 1
0x180032886  lea     rax, [rbp+5B0h+TokenHandle]
0x18003288a  mov     [rbp+5B0h+var_5B0], r14
0x18003288e  mov     [rbp+5B0h+var_5F8], rax
0x180032892  lea     r8, [rbp+5B0h+var_5F0]; void **
0x180032896  lea     rax, [rbp+5B0h+var_5B0]
0x18003289a  mov     [rbp+5B0h+TokenHandle], r14
0x18003289e  xorps   xmm0, xmm0
0x1800328a1  mov     [rbp+5B0h+var_5A8], rax
0x1800328a5  xor     r9d, r9d; unsigned int *
0x1800328a8  mov     [rbp+5B0h+var_5F0], r14
0x1800328ac  lea     rdx, [rbp+5B0h+var_5A0]; void **
0x1800328b0  mov     [rbp+5B0h+var_5A0], r14
0x1800328b4  mov     rcx, r13; void *
0x1800328b7  mov     byte ptr [rbp+5B0h+var_598], 1
0x1800328bb  movups  xmmword ptr [rbx], xmm0
0x1800328be  mov     [rsp+6C0h+packageRelativeApplicationId], r14; int
0x1800328c3  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x1800328c8  lea     rcx, [rbp+5B0h+var_5A8]
0x1800328cc  mov     ebx, eax
0x1800328ce  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800328d3  lea     rcx, [rbp+5B0h+var_5F8]
0x1800328d7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800328dc  test    ebx, ebx
0x1800328de  jz      short loc_180032902
0x1800328e0  mov     rcx, [rbp+5B8h]; this
0x1800328e7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800328ee  mov     r9d, ebx; char *
0x1800328f1  mov     edx, 19E2h; void *
0x1800328f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800328fb  mov     ebx, eax
0x1800328fd  jmp     loc_180032B3B
0x180032902  mov     rcx, [rbp+5B0h+TokenHandle]; TokenHandle
0x180032906  mov     rdx, rdi; HANDLE
0x180032909  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x18003290e  mov     ebx, eax
0x180032910  test    eax, eax
0x180032912  jns     short loc_180032934
0x180032914  mov     rcx, [rbp+5B8h]; this
0x18003291b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032922  mov     r9d, eax; char *
0x180032925  mov     edx, 19E4h; void *
0x18003292a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003292f  jmp     loc_180032B3B
0x180032934  mov     rsi, [rbp+5B0h+TokenHandle]
0x180032938  test    rdi, rdi
0x18003293b  cmovnz  rsi, rdi
0x18003293f  xor     edi, edi
0x180032941  mov     rcx, rsi; void *
0x180032944  mov     [rbp+5B0h+var_628], rdi
0x180032948  mov     r14, rsi
0x18003294b  call    ?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z; IsTokenIntegrityLevelLessThanMedium(void *)
0x180032950  test    al, al
0x180032952  jnz     short loc_180032967
0x180032954  mov     rcx, rsi; TokenHandle
0x180032957  call    cs:__imp_IsTokenRestricted
0x18003295e  nop     dword ptr [rax+rax+00h]
0x180032963  test    eax, eax
0x180032965  jz      short loc_1800329B9
0x180032967  xor     edx, edx
0x180032969  mov     [rbp+5B0h+var_580], rdi
0x18003296d  lea     rcx, [rbp+5B0h+var_628]
0x180032971  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032976  lea     r8, [rbp+5B0h+var_628]; void **
0x18003297a  mov     rcx, rsi; void *
0x18003297d  lea     rdx, [rbp+5B0h+var_580]; unsigned __int64 *
0x180032981  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x180032986  mov     ebx, eax
0x180032988  test    eax, eax
0x18003298a  jns     short loc_1800329B5
0x18003298c  mov     rcx, [rbp+5B8h]; this
0x180032993  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003299a  mov     r9d, eax; char *
0x18003299d  mov     edx, 19F0h; void *
0x1800329a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800329a7  lea     rcx, [rbp+5B0h+var_628]
0x1800329ab  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800329b0  jmp     loc_180032B3B
0x1800329b5  mov     r14, [rbp+5B0h+var_628]
0x1800329b9  mov     eax, 41h ; 'A'
0x1800329be  lea     r9, [rbp+5B0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800329c2  mov     [rbp+5B0h+packageFamilyNameLength], eax
0x1800329c5  lea     r8, [rbp+5B0h+packageFamilyName]; packageFamilyName
0x1800329cc  mov     [rbp+5B0h+packageRelativeApplicationIdLength], eax
0x1800329cf  lea     rdx, [rbp+5B0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800329d3  lea     rax, [rbp+5B0h+var_1D0]
0x1800329da  mov     rcx, r15; applicationUserModelId
0x1800329dd  mov     [rsp+6C0h+packageRelativeApplicationId], rax; int
0x1800329e2  mov     r12b, dil
0x1800329e5  call    cs:__imp_ParseApplicationUserModelId
0x1800329ec  nop     dword ptr [rax+rax+00h]
0x1800329f1  test    eax, eax
0x1800329f3  jz      short loc_180032A14
0x1800329f5  mov     rcx, [rbp+5B8h]; this
0x1800329fc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032a03  mov     r9d, eax; char *
0x180032a06  mov     edx, 19FBh; void *
0x180032a0b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032a10  mov     ebx, eax
0x180032a12  jmp     short loc_1800329A7
0x180032a14  xor     edx, edx; Val
0x180032a16  mov     [rbp+5B0h+var_614], edi
0x180032a19  mov     r8d, 100h; Size
0x180032a1f  mov     [rbp+5B0h+var_62F+1], dil
0x180032a23  lea     rcx, [rbp+5B0h+var_3F0]; void *
0x180032a2a  mov     [rbp+5B0h+var_617], dil
0x180032a2e  call    memset_0
0x180032a33  mov     [rbp+5B0h+var_5C0], 80h
0x180032a3a  mov     [rbp+5B0h+var_620], rdi
0x180032a3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoGenerateSparsePackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages> `wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl(void)'::`2'::impl
0x180032a45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(void)
0x180032a4a  test    al, al
0x180032a4c  jz      loc_180032BBE
0x180032a52  lea     r8, [rbp+5B0h+var_620]
0x180032a56  mov     rdx, r15
0x180032a59  mov     rcx, r14
0x180032a5c  call    ?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180032a61  mov     ebx, eax
0x180032a63  cmp     eax, 80070057h
0x180032a68  jz      loc_180032B27
0x180032a6e  test    eax, eax
0x180032a70  jns     short loc_180032A9B
0x180032a72  mov     edx, 1A0Eh; void *
0x180032a77  mov     r9d, eax; char *
0x180032a7a  mov     rcx, [rbp+5B8h]; this
0x180032a81  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a8d  lea     rcx, [rbp+5B0h+var_620]
0x180032a91  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032a96  jmp     loc_1800329A7
0x180032a9b  mov     rcx, [rbp+5B0h+var_620]
0x180032a9f  lea     rdx, [rbp+5B0h+Source]
0x180032aa3  mov     [rbp+5B0h+Source], rdi
0x180032aa7  call    ?GetEAAumidIfPresent@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetEAAumidIfPresent(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180032aac  mov     edi, eax
0x180032aae  cmp     eax, 80090032h
0x180032ab3  jnz     loc_180032B83
0x180032ab9  mov     rbx, [rbp+5B0h+Source]
0x180032abd  test    rbx, rbx
0x180032ac0  jz      loc_180032B93
0x180032ac6  mov     rcx, r15; Source
0x180032ac9  call    wcsnlen_s
0x180032ace  mov     rcx, rbx; Source
0x180032ad1  mov     rdi, rax
0x180032ad4  call    wcsnlen_s
0x180032ad9  cmp     eax, edi
0x180032adb  jnz     loc_180032BB3
0x180032ae1  mov     r8d, edi; MaxCount
0x180032ae4  mov     rdx, rbx; String2
0x180032ae7  mov     rcx, r15; String1
0x180032aea  call    cs:__imp_wcsncmp
0x180032af1  nop     dword ptr [rax+rax+00h]
0x180032af6  xor     edi, edi
0x180032af8  test    eax, eax
0x180032afa  jnz     loc_180032BB5
0x180032b00  mov     rcx, [rbp+5B8h]; this
0x180032b07  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032b0e  mov     r9d, 80090032h; char *
0x180032b14  mov     edx, 1A20h; void *
0x180032b19  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180032b1e  lea     rcx, [rbp+5B0h+Source]
0x180032b22  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032b27  lea     rcx, [rbp+5B0h+var_620]
0x180032b2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032b30  lea     rcx, [rbp+5B0h+var_628]
0x180032b34  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032b39  mov     ebx, edi
0x180032b3b  lea     rcx, [rbp+5B0h+TokenHandle]
0x180032b3f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032b44  lea     rcx, [rbp+5B0h+var_5B0]
0x180032b48  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032b4d  lea     rcx, [rbp+5B0h+var_540]; this
0x180032b51  call    ??1GetPackageActivationTokenForSxS@LUATelemetry@@QEAA@XZ; LUATelemetry::GetPackageActivationTokenForSxS::~GetPackageActivationTokenForSxS(void)
0x180032b56  mov     eax, ebx
0x180032b58  mov     rcx, [rbp+5B0h+var_40]
0x180032b5f  xor     rcx, rsp; StackCookie
0x180032b62  call    __security_check_cookie
0x180032b67  mov     rbx, [rsp+6C0h+arg_18]
0x180032b6f  add     rsp, 690h
0x180032b76  pop     r15
0x180032b78  pop     r14
0x180032b7a  pop     r13
0x180032b7c  pop     r12
0x180032b7e  pop     rdi
0x180032b7f  pop     rsi
0x180032b80  pop     rbp
0x180032b81  retn
0x180032b83  test    edi, edi
0x180032b85  jz      short loc_180032BB3
0x180032b87  cmp     edi, 80070490h
0x180032b8d  jz      short loc_180032BB3
0x180032b8f  test    edi, edi
0x180032b91  jns     short loc_180032B1E
0x180032b93  mov     rcx, [rbp+5B8h]; this
0x180032b9a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032ba1  mov     r9d, edi; char *
0x180032ba4  mov     edx, 1A27h; void *
0x180032ba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032bae  jmp     loc_180032B1E
0x180032bb3  xor     edi, edi
0x180032bb5  lea     rcx, [rbp+5B0h+Source]
0x180032bb9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032bbe  mov     rcx, r14; hToken
0x180032bc1  call    cs:__imp_ImpersonateLoggedOnUser
0x180032bc8  nop     dword ptr [rax+rax+00h]
0x180032bcd  test    eax, eax
0x180032bcf  jnz     short loc_180032BF0
0x180032bd1  mov     edx, 1A2Ch; void *
0x180032bd6  mov     rcx, [rbp+5B8h]; this
0x180032bdd  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032be4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032be9  mov     ebx, eax
0x180032beb  jmp     loc_180032A8D
0x180032bf0  lea     r9, [rbp+5B0h+var_3F0]
0x180032bf7  mov     [rsp+6C0h+packageRelativeApplicationId], rdi; int
0x180032bfc  lea     r8, [rbp+5B0h+var_5C0]
0x180032c00  mov     edx, 1
0x180032c05  lea     rcx, [rbp+5B0h+packageFamilyName]
0x180032c0c  call    cs:__imp_RegisterDesktopAppXPackageFamilyIfNecessary
0x180032c13  nop     dword ptr [rax+rax+00h]
0x180032c18  mov     ebx, eax
0x180032c1a  call    cs:__imp_RevertToSelf
0x180032c21  nop     dword ptr [rax+rax+00h]
0x180032c26  cmp     ebx, 80073CF1h
0x180032c2c  jz      loc_180032B27
0x180032c32  cmp     ebx, 80270254h
0x180032c38  jnz     short loc_180032C81
0x180032c3a  lea     rdx, [rbp+5B0h+var_62F]
0x180032c3e  mov     [rbp+5B0h+var_62F], dil
0x180032c42  lea     rcx, [rbp+5B0h+packageFamilyName]; lpString2
0x180032c49  call    IsFamilyProvisioned
0x180032c4e  mov     edi, eax
0x180032c50  test    eax, eax
0x180032c52  jns     short loc_180032C74
0x180032c54  mov     rcx, [rbp+5B8h]; this
0x180032c5b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032c62  mov     r9d, eax; char *
0x180032c65  mov     edx, 1A4Bh; void *
0x180032c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032c6f  jmp     loc_180032B27
0x180032c74  xor     edi, edi
0x180032c76  cmp     [rbp+5B0h+var_62F], dil
0x180032c7a  jnz     short loc_180032C85
0x180032c7c  jmp     loc_180032B27
0x180032c81  test    ebx, ebx
0x180032c83  jns     short loc_180032C92
0x180032c85  mov     r9d, ebx
0x180032c88  mov     edx, 1A52h
0x180032c8d  jmp     loc_180032A7A
0x180032c92  mov     rcx, r14; hToken
0x180032c95  call    cs:__imp_ImpersonateLoggedOnUser
0x180032c9c  nop     dword ptr [rax+rax+00h]
0x180032ca1  test    eax, eax
0x180032ca3  jnz     short loc_180032CAF
0x180032ca5  mov     edx, 1A55h
0x180032caa  jmp     loc_180032BD6
0x180032caf  lea     rax, [rbp+5B0h+var_617]
0x180032cb3  mov     [rbp+5B0h+var_60E], dil
0x180032cb7  mov     [rsp+6C0h+var_678], rax; bool *
0x180032cbc  xor     r9d, r9d; unsigned int
0x180032cbf  lea     rax, [rbp+5B0h+var_610]
0x180032cc3  mov     [rbp+5B0h+var_60F], dil
0x180032cc7  mov     [rsp+6C0h+var_680], rax; bool *
0x180032ccc  xor     r8d, r8d; unsigned __int16 *
0x180032ccf  lea     rax, [rbp+5B0h+var_60F]
0x180032cd3  mov     [rbp+5B0h+var_610], dil
0x180032cd7  mov     [rsp+6C0h+var_688], rax; bool *
0x180032cdc  mov     rdx, r15; unsigned __int16 *
0x180032cdf  lea     rax, [rbp+5B0h+var_60E]
0x180032ce3  mov     rcx, r14; void *
0x180032ce6  mov     [rsp+6C0h+var_690], rax; bool *
0x180032ceb  lea     rax, [rbp+5B0h+var_62F+1]
  ... truncated ...
```
