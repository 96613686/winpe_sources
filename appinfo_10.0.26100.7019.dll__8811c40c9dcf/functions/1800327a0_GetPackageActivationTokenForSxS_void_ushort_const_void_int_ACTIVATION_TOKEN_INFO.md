# GetPackageActivationTokenForSxS(void *,ushort const *,void *,int,_ACTIVATION_TOKEN_INFO *)

- ea: `0x1800327a0`
- end: `0x180033387`
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
- `0x18000f630`
- `0x18000f8b0`
- `0x180010860`
- `0x180010890`
- `0x180011ba0`
- `0x1800124f4`
- `0x180012b9c`
- `0x180018150`
- `0x1800181cc`
- `0x180018280`
- `0x18001866c`
- `0x1800213f0`
- `0x18002a750`
- `0x18002e150`
- `0x180031e98`
- `0x1800320a8`
- `0x1800327a0`
- `0x1800334c8`
- `0x180033e6c`
- `0x18003860c`
- `0x180038740`
- `0x180038dac`
- `0x180038eb4`
- `0x180038ef0`
- `0x18003901c`
- `0x18003ba20`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180032a7a`
- `msvcrt!wcsncmp` at `0x180032a7a`
- `RPCRT4!RpcImpersonateClient` at `0x1800330ce`
- `RPCRT4!RpcImpersonateClient` at `0x1800330ce`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800331cb`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800331df`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800331cb`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800331df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032b51`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032c25`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800331f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032b51`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180032c25`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800331f3`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x1800328e7`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x1800328e7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032baa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032cb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e0d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e1e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800332e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800332f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032baa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032cb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e0d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032e1e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800332e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800332f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032e95`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032e95`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180032e3f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180032e3f`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180032975`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180032975`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180032e68`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180032e68`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180032fc3`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18003306f`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x180032fc3`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18003306f`
- `ext-ms-win-desktopappx-l1-1-5!RegisterDesktopAppXPackageFamilyIfNecessary` at `0x180032b9c`
- `ext-ms-win-desktopappx-l1-1-5!RegisterDesktopAppXPackageFamilyIfNecessary` at `0x180032b9c`

## string_xrefs

- `0x180032877`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800328ab`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032923`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003298c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032a11`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032a97`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032b2a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032b6d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032beb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032c9f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032cf2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032d78`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032f1f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180032ff8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033096`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800330e5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800331b2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003320a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800332cc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033323`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800327e1`: `GetPackageActivationTokenForSxS`

## pseudocode

```c
__int64 __fastcall GetPackageActivationTokenForSxS(
        void *a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
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
  int packageRelativeApplicationIdc; // [rsp+20h] [rbp-F0h]
  int v62; // [rsp+28h] [rbp-E8h]
  int v63; // [rsp+30h] [rbp-E0h]
  int v64; // [rsp+38h] [rbp-D8h]
  int v65; // [rsp+40h] [rbp-D0h]
  int v66; // [rsp+48h] [rbp-C8h]
  bool v67; // [rsp+90h] [rbp-80h] BYREF
  bool v68[4]; // [rsp+91h] [rbp-7Fh] BYREF
  bool v69; // [rsp+95h] [rbp-7Bh] BYREF
  void *v70; // [rsp+98h] [rbp-78h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-70h] BYREF
  bool v72; // [rsp+A8h] [rbp-68h] BYREF
  bool v73; // [rsp+A9h] [rbp-67h] BYREF
  unsigned int v74; // [rsp+ACh] [rbp-64h] BYREF
  bool v75; // [rsp+B0h] [rbp-60h] BYREF
  bool v76; // [rsp+B1h] [rbp-5Fh] BYREF
  bool v77; // [rsp+B2h] [rbp-5Eh] BYREF
  __int64 v78; // [rsp+B8h] [rbp-58h] BYREF
  void *v79; // [rsp+C0h] [rbp-50h] BYREF
  HANDLE *p_TokenHandle; // [rsp+C8h] [rbp-48h] BYREF
  void *v81; // [rsp+D0h] [rbp-40h] BYREF
  char v82; // [rsp+D8h] [rbp-38h]
  wchar_t *Source; // [rsp+E0h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+E8h] [rbp-28h] BYREF
  UINT32 v85; // [rsp+F0h] [rbp-20h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+F4h] [rbp-1Ch] BYREF
  int v87; // [rsp+F8h] [rbp-18h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+FCh] [rbp-14h] BYREF
  int v89; // [rsp+100h] [rbp-10h] BYREF
  struct _ACTIVATION_TOKEN_INFO *v90; // [rsp+108h] [rbp-8h]
  __int64 v91; // [rsp+110h] [rbp+0h] BYREF
  __int64 *v92; // [rsp+118h] [rbp+8h] BYREF
  void *v93; // [rsp+120h] [rbp+10h] BYREF
  unsigned __int16 *v94; // [rsp+128h] [rbp+18h]
  __int128 v95; // [rsp+130h] [rbp+20h]
  unsigned __int64 v96; // [rsp+140h] [rbp+30h] BYREF
  _QWORD v97[3]; // [rsp+148h] [rbp+38h] BYREF
  __int128 v98; // [rsp+160h] [rbp+50h]
  _QWORD v99[42]; // [rsp+180h] [rbp+70h] BYREF
  unsigned __int16 v100[128]; // [rsp+2D0h] [rbp+1C0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+3D0h] [rbp+2C0h] BYREF
  WCHAR String2[72]; // [rsp+460h] [rbp+350h] BYREF
  WCHAR v103[72]; // [rsp+4F0h] [rbp+3E0h] BYREF
  WCHAR packageFullName[128]; // [rsp+580h] [rbp+470h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5B8h]

  v90 = a5;
  v87 = a4;
  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v99);
  v99[0] = &LUATelemetry::GetPackageActivationTokenForSxS::`vftable';
  LUATelemetry::GetPackageActivationTokenForSxS::StartActivity((LUATelemetry::GetPackageActivationTokenForSxS *)v99, a2);
  v82 = 1;
  v91 = 0;
  p_TokenHandle = &TokenHandle;
  TokenHandle = 0;
  v92 = &v91;
  v81 = 0;
  v93 = 0;
  LOBYTE(v94) = 1;
  *(_OWORD *)a5 = 0;
  ClientInformation = AiGetClientInformation(a1, &v93, &v81, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v92);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( !ClientInformation )
  {
    v10 = AccessCheckIncomingToken(TokenHandle, a3);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1917,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v10,
        packageRelativeApplicationId);
      goto LABEL_29;
    }
    v11 = TokenHandle;
    if ( a3 )
      v11 = a3;
    v12 = 0;
    v70 = 0;
    v13 = v11;
    if ( IsTokenIntegrityLevelLessThanMedium(v11) || IsTokenRestricted(v11) )
    {
      v96 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v70,
        0);
      UserContextAndUnmodifiedLogonTokenOfTokenUser = GetUserContextAndUnmodifiedLogonTokenOfTokenUser(v11, &v96, &v70);
      v9 = UserContextAndUnmodifiedLogonTokenOfTokenUser;
      if ( UserContextAndUnmodifiedLogonTokenOfTokenUser < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1923,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)UserContextAndUnmodifiedLogonTokenOfTokenUser,
          packageRelativeApplicationId);
LABEL_11:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v70);
        goto LABEL_29;
      }
      v13 = v70;
    }
    packageFamilyNameLength = 65;
    packageRelativeApplicationIdLength = 65;
    v15 = 0;
    v16 = ParseApplicationUserModelId(
            a2,
            &packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            v103);
    if ( v16 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x192E,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)v16,
             packageRelativeApplicationIda);
      goto LABEL_11;
    }
    v74 = 0;
    v68[1] = 0;
    v73 = 0;
    memset_0(v100, 0, sizeof(v100));
    v89 = 128;
    v71 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl'::`2'::impl) )
    {
LABEL_36:
      if ( !ImpersonateLoggedOnUser(v13) )
      {
        v28 = 6495;
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
      v9 = RegisterDesktopAppXPackageFamilyIfNecessary(packageFamilyName, 1, &v89, v100);
      RevertToSelf();
      if ( v9 == -2147009295 )
        goto LABEL_28;
      if ( v9 == -2144927148 )
      {
        v68[0] = 0;
        v30 = IsFamilyProvisioned(packageFamilyName);
        v12 = v30;
        if ( v30 >= 0 )
          v12 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x197E,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)(unsigned int)v30,
            0);
        goto LABEL_28;
      }
      if ( v9 < 0 )
      {
        v19 = (unsigned int)v9;
        v18 = 6533;
        goto LABEL_20;
      }
      if ( !ImpersonateLoggedOnUser(v13) )
      {
        v28 = 6536;
        goto LABEL_38;
      }
      v77 = 0;
      v76 = 0;
      v75 = 0;
      AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                               v13,
                                               a2,
                                               0,
                                               0,
                                               (enum AppModel::RuntimeBehavior *)&v74,
                                               &v68[1],
                                               &v77,
                                               &v76,
                                               &v75,
                                               &v73);
      v9 = AppModelIdentityActivationProperties;
      if ( AppModelIdentityActivationProperties < 0 )
      {
        v32 = retaddr;
        v33 = (unsigned int)AppModelIdentityActivationProperties;
        v34 = 6544;
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
        if ( v68[1] && v74 != 3 )
        {
          v35 = 6550;
LABEL_57:
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v35,
                 (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                 (const char *)5,
                 packageRelativeApplicationIdb);
          goto LABEL_52;
        }
        if ( ((v74 - 1) & 0xFFFFFFFD) == 0 )
        {
          v67 = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl'::`2'::impl) )
            HasProperConditionalACE = VerifyExecutableHasProperConditionalACE(&v71, a2, &v67);
          else
            HasProperConditionalACE = VerifyExecutableHasProperConditionalACE(v13, a2, &v67);
          v9 = HasProperConditionalACE;
          if ( HasProperConditionalACE < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x19AB,
              v37,
              (const char *)(unsigned int)HasProperConditionalACE,
              packageRelativeApplicationIdb);
          if ( !v67 )
          {
            if ( v74 != 1 )
            {
              v32 = retaddr;
              if ( v9 >= 0 )
              {
                v9 = -2147024809;
                v34 = 6583;
                v33 = 2147942487LL;
              }
              else
              {
                v33 = (unsigned int)v9;
                v34 = 6582;
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
          v85 = 65;
          if ( !PackageFamilyNameFromFullName(packageFullName, &v85, String2) )
            v15 = CompareStringOrdinal(packageFamilyName, packageFamilyNameLength, String2, v85, 1) == 2;
        }
        v68[0] = 0;
        v72 = 0;
        v69 = 0;
        v68[3] = 0;
        v68[2] = 0;
        v67 = 0;
        PackageProperties = GetPackageProperties(v100, v68, &v72, &v69, &v68[3], &v68[2], 0, &v67, 0);
        v9 = PackageProperties;
        if ( PackageProperties < 0 )
        {
          v18 = 6660;
          goto LABEL_19;
        }
        if ( !v72 && !v15 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1A08,
                        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                        (const char *)5,
                        packageRelativeApplicationIda);
          goto LABEL_39;
        }
        v78 = 0;
        if ( v74 - 1 > 1 )
        {
          if ( v74 == 3 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppSiloSparsePackageLaunch>::GetImpl'::`2'::impl) )
            {
              v93 = TokenHandle;
              v95 = 0;
              v94 = v100;
              v41 = 0;
              v92 = (__int64 *)v13;
              v81 = 0;
              v42 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) | 3;
              v82 = 1;
              if ( v74 == 2 )
                v41 = 8;
              DWORD2(v95) = v42 | v41;
              p_TokenHandle = (HANDLE *)&v78;
              v9 = PrepareDesktopAppXActivation(&v92, &v81);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
              if ( v9 < 0 )
              {
                v43 = 6697;
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
            v44 = 6701;
          }
          else
          {
            v44 = 6706;
          }
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v44,
                 (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                 (const char *)0x32,
                 packageRelativeApplicationIda);
LABEL_103:
          wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v78);
          goto LABEL_21;
        }
        v97[1] = TokenHandle;
        v98 = 0;
        v97[0] = v13;
        v97[2] = v100;
        v45 = 0;
        v81 = 0;
        v82 = 1;
        v46 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) | 3;
        if ( v74 == 2 )
          v45 = 8;
        DWORD2(v98) = v46 | v45;
        p_TokenHandle = (HANDLE *)&v78;
        v9 = PrepareDesktopAppXActivation(v97, &v81);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>>>(&p_TokenHandle);
        if ( v9 < 0 )
        {
          v43 = 6681;
          goto LABEL_102;
        }
LABEL_104:
        v79 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowILPackagedProcessesCannotBeSpawnedViaSxsManifest>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_LowILPackagedProcessesCannotBeSpawnedViaSxsManifest>::GetImpl'::`2'::impl) )
        {
          v47 = RpcImpersonateClient(a1);
          if ( v47 )
          {
            v49 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x1A39,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    (const char *)v47,
                    packageRelativeApplicationIda);
LABEL_107:
            v9 = v49;
LABEL_108:
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v79);
            goto LABEL_103;
          }
          p_TokenHandle = &v79;
          v81 = 0;
          v82 = 1;
          LOBYTE(v66) = v74 == 0;
          LOBYTE(v48) = v68[1];
          LOBYTE(v65) = 0;
          LOBYTE(v64) = v68[2];
          LOBYTE(v63) = v68[3];
          LOBYTE(v62) = v69;
          LOBYTE(packageRelativeApplicationIda) = v68[0];
          v50 = AdjustActivationToken(
                  v11,
                  v74,
                  v48,
                  0,
                  packageRelativeApplicationIda,
                  v62,
                  v63,
                  v64,
                  v65,
                  v66,
                  v67,
                  v87 != 0,
                  v100,
                  a2,
                  0,
                  0,
                  *(_QWORD *)(v78 + 56),
                  &v81);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v50 < 0 )
          {
            v9 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x1A43,
                   (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                   (const char *)(unsigned int)v50,
                   packageRelativeApplicationIdc);
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
                    (void *)0x1A47,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v52);
            goto LABEL_107;
          }
          p_TokenHandle = &v79;
          v81 = 0;
          v82 = 1;
          LOBYTE(v66) = v74 == 0;
          LOBYTE(v51) = v68[1];
          LOBYTE(v65) = 0;
          LOBYTE(v64) = v68[2];
          LOBYTE(v63) = v68[3];
          LOBYTE(v62) = v69;
          LOBYTE(packageRelativeApplicationIda) = v68[0];
          v53 = AdjustActivationToken(
                  v11,
                  v74,
                  v51,
                  0,
                  packageRelativeApplicationIda,
                  v62,
                  v63,
                  v64,
                  v65,
                  v66,
                  v67,
                  v87 != 0,
                  v100,
                  a2,
                  0,
                  0,
                  *(_QWORD *)(v78 + 56),
                  &v81);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
          if ( v53 < 0 )
          {
            v9 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x1A51,
                   (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                   (const char *)(unsigned int)v53,
                   packageRelativeApplicationIdc);
            RevertToSelf();
            goto LABEL_108;
          }
          RevertToSelf();
        }
        v54 = v90;
        if ( !v73
          || (BnoIsolationPrefixForRpc = CreateBnoIsolationPrefixForRpc(v79, (unsigned __int16 **)v90 + 1),
              v9 = BnoIsolationPrefixForRpc,
              BnoIsolationPrefixForRpc >= 0) )
        {
          v56 = v79;
          v57 = v74;
          v79 = 0;
          *(_QWORD *)v54 = v56;
          LUATelemetry::GetPackageActivationTokenForSxS::Stop(
            (LUATelemetry::GetPackageActivationTokenForSxS *)v99,
            v100,
            v57);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v79);
          wil::details::unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<DESKTOP_APPX_LAUNCH_CONTEXT *,void (*)(DESKTOP_APPX_LAUNCH_CONTEXT *),&void FreeDesktopAppXLaunchContext(DESKTOP_APPX_LAUNCH_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,DESKTOP_APPX_LAUNCH_CONTEXT *,DESKTOP_APPX_LAUNCH_CONTEXT *,0,std::nullptr_t>>(&v78);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v70);
          v9 = 0;
          goto LABEL_29;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A56,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)BnoIsolationPrefixForRpc,
          packageRelativeApplicationIdc);
        goto LABEL_108;
      }
      if ( v68[1] )
      {
        v35 = 6591;
        goto LABEL_57;
      }
      if ( v74 != 1 )
        goto LABEL_80;
      v67 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl'::`2'::impl) )
      {
        v38 = VerifyExecutableHasProperConditionalACE(&v71, a2, &v67);
        if ( v38 >= 0 )
          goto LABEL_78;
        v40 = 6607;
      }
      else
      {
        v38 = VerifyExecutableHasProperConditionalACE(v13, a2, &v67);
        if ( v38 >= 0 )
          goto LABEL_78;
        v40 = 6611;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v40,
        v39,
        (const char *)(unsigned int)v38,
        packageRelativeApplicationIdb);
LABEL_78:
      if ( !v67 )
        goto LABEL_79;
      goto LABEL_80;
    }
    PackageProperties = GetFullPathToAUMIDExecutable(v13, a2, &v71);
    v9 = PackageProperties;
    if ( PackageProperties == -2147024809 )
    {
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v70);
      v9 = v12;
      goto LABEL_29;
    }
    if ( PackageProperties < 0 )
    {
      v18 = 6465;
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
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
      goto LABEL_11;
    }
    Source = 0;
    EAAumidIfPresent = GetEAAumidIfPresent(v71, &Source);
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
              (void *)0x1953,
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
      (void *)0x195A,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)EAAumidIfPresent,
      packageRelativeApplicationIda);
    goto LABEL_27;
  }
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x1915,
         (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
         (const char *)ClientInformation,
         packageRelativeApplicationId);
LABEL_29:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v91);
  LUATelemetry::GetPackageActivationTokenForSxS::~GetPackageActivationTokenForSxS((LUATelemetry::GetPackageActivationTokenForSxS *)v99);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800327a0  mov     [rsp-8+arg_18], rbx
0x1800327a5  push    rbp
0x1800327a6  push    rsi
0x1800327a7  push    rdi
0x1800327a8  push    r12
0x1800327aa  push    r13
0x1800327ac  push    r14
0x1800327ae  push    r15
0x1800327b0  lea     rbp, [rsp-580h]
0x1800327b8  sub     rsp, 690h
0x1800327bf  mov     rax, cs:__security_cookie
0x1800327c6  xor     rax, rsp
0x1800327c9  mov     [rbp+5B0h+var_40], rax
0x1800327d0  mov     rbx, [rbp+5B0h+arg_20]
0x1800327d7  mov     r15, rdx
0x1800327da  mov     r13, rcx
0x1800327dd  mov     [rbp+5B0h+var_5B8], rbx
0x1800327e1  lea     rdx, aGetpackageacti; "GetPackageActivationTokenForSxS"
0x1800327e8  mov     [rbp+5B0h+var_5C8], r9d
0x1800327ec  lea     rcx, [rbp+5B0h+var_540]; struct wil::details::IFailureCallback *
0x1800327f0  mov     rdi, r8
0x1800327f3  call    ??0?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800327f8  lea     rax, ??_7GetPackageActivationTokenForSxS@LUATelemetry@@6B@; const LUATelemetry::GetPackageActivationTokenForSxS::`vftable'
0x1800327ff  mov     rdx, r15; unsigned __int16 *
0x180032802  lea     rcx, [rbp+5B0h+var_540]; this
0x180032806  mov     [rbp+5B0h+var_540], rax
0x18003280a  call    ?StartActivity@GetPackageActivationTokenForSxS@LUATelemetry@@QEAAXPEBG@Z; LUATelemetry::GetPackageActivationTokenForSxS::StartActivity(ushort const *)
0x18003280f  xor     r14d, r14d
0x180032812  mov     [rbp+5B0h+var_5E8], 1
0x180032816  lea     rax, [rbp+5B0h+TokenHandle]
0x18003281a  mov     [rbp+5B0h+var_5B0], r14
0x18003281e  mov     [rbp+5B0h+var_5F8], rax
0x180032822  lea     r8, [rbp+5B0h+var_5F0]; void **
0x180032826  lea     rax, [rbp+5B0h+var_5B0]
0x18003282a  mov     [rbp+5B0h+TokenHandle], r14
0x18003282e  xorps   xmm0, xmm0
0x180032831  mov     [rbp+5B0h+var_5A8], rax
0x180032835  xor     r9d, r9d; unsigned int *
0x180032838  mov     [rbp+5B0h+var_5F0], r14
0x18003283c  lea     rdx, [rbp+5B0h+var_5A0]; void **
0x180032840  mov     [rbp+5B0h+var_5A0], r14
0x180032844  mov     rcx, r13; void *
0x180032847  mov     byte ptr [rbp+5B0h+var_598], 1
0x18003284b  movups  xmmword ptr [rbx], xmm0
0x18003284e  mov     [rsp+6C0h+packageRelativeApplicationId], r14; int
0x180032853  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180032858  lea     rcx, [rbp+5B0h+var_5A8]
0x18003285c  mov     ebx, eax
0x18003285e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180032863  lea     rcx, [rbp+5B0h+var_5F8]
0x180032867  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18003286c  test    ebx, ebx
0x18003286e  jz      short loc_180032892
0x180032870  mov     rcx, [rbp+5B8h]; this
0x180032877  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003287e  mov     r9d, ebx; char *
0x180032881  mov     edx, 1915h; void *
0x180032886  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003288b  mov     ebx, eax
0x18003288d  jmp     loc_180032ACB
0x180032892  mov     rcx, [rbp+5B0h+TokenHandle]; TokenHandle
0x180032896  mov     rdx, rdi; HANDLE
0x180032899  call    ?AccessCheckIncomingToken@@YAJPEAX0@Z; AccessCheckIncomingToken(void *,void *)
0x18003289e  mov     ebx, eax
0x1800328a0  test    eax, eax
0x1800328a2  jns     short loc_1800328C4
0x1800328a4  mov     rcx, [rbp+5B8h]; this
0x1800328ab  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800328b2  mov     r9d, eax; char *
0x1800328b5  mov     edx, 1917h; void *
0x1800328ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800328bf  jmp     loc_180032ACB
0x1800328c4  mov     rsi, [rbp+5B0h+TokenHandle]
0x1800328c8  test    rdi, rdi
0x1800328cb  cmovnz  rsi, rdi
0x1800328cf  xor     edi, edi
0x1800328d1  mov     rcx, rsi; void *
0x1800328d4  mov     [rbp+5B0h+var_628], rdi
0x1800328d8  mov     r14, rsi
0x1800328db  call    ?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z; IsTokenIntegrityLevelLessThanMedium(void *)
0x1800328e0  test    al, al
0x1800328e2  jnz     short loc_1800328F7
0x1800328e4  mov     rcx, rsi; TokenHandle
0x1800328e7  call    cs:__imp_IsTokenRestricted
0x1800328ee  nop     dword ptr [rax+rax+00h]
0x1800328f3  test    eax, eax
0x1800328f5  jz      short loc_180032949
0x1800328f7  xor     edx, edx
0x1800328f9  mov     [rbp+5B0h+var_580], rdi
0x1800328fd  lea     rcx, [rbp+5B0h+var_628]
0x180032901  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180032906  lea     r8, [rbp+5B0h+var_628]; void **
0x18003290a  mov     rcx, rsi; void *
0x18003290d  lea     rdx, [rbp+5B0h+var_580]; unsigned __int64 *
0x180032911  call    ?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z; GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)
0x180032916  mov     ebx, eax
0x180032918  test    eax, eax
0x18003291a  jns     short loc_180032945
0x18003291c  mov     rcx, [rbp+5B8h]; this
0x180032923  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003292a  mov     r9d, eax; char *
0x18003292d  mov     edx, 1923h; void *
0x180032932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032937  lea     rcx, [rbp+5B0h+var_628]
0x18003293b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032940  jmp     loc_180032ACB
0x180032945  mov     r14, [rbp+5B0h+var_628]
0x180032949  mov     eax, 41h ; 'A'
0x18003294e  lea     r9, [rbp+5B0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180032952  mov     [rbp+5B0h+packageFamilyNameLength], eax
0x180032955  lea     r8, [rbp+5B0h+packageFamilyName]; packageFamilyName
0x18003295c  mov     [rbp+5B0h+packageRelativeApplicationIdLength], eax
0x18003295f  lea     rdx, [rbp+5B0h+packageFamilyNameLength]; packageFamilyNameLength
0x180032963  lea     rax, [rbp+5B0h+var_1D0]
0x18003296a  mov     rcx, r15; applicationUserModelId
0x18003296d  mov     [rsp+6C0h+packageRelativeApplicationId], rax; int
0x180032972  mov     r12b, dil
0x180032975  call    cs:__imp_ParseApplicationUserModelId
0x18003297c  nop     dword ptr [rax+rax+00h]
0x180032981  test    eax, eax
0x180032983  jz      short loc_1800329A4
0x180032985  mov     rcx, [rbp+5B8h]; this
0x18003298c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032993  mov     r9d, eax; char *
0x180032996  mov     edx, 192Eh; void *
0x18003299b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800329a0  mov     ebx, eax
0x1800329a2  jmp     short loc_180032937
0x1800329a4  xor     edx, edx; Val
0x1800329a6  mov     [rbp+5B0h+var_614], edi
0x1800329a9  mov     r8d, 100h; Size
0x1800329af  mov     [rbp+5B0h+var_62F+1], dil
0x1800329b3  lea     rcx, [rbp+5B0h+var_3F0]; void *
0x1800329ba  mov     [rbp+5B0h+var_617], dil
0x1800329be  call    memset_0
0x1800329c3  mov     [rbp+5B0h+var_5C0], 80h
0x1800329ca  mov     [rbp+5B0h+var_620], rdi
0x1800329ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoGenerateSparsePackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages> `wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::GetImpl(void)'::`2'::impl
0x1800329d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackages>::__private_IsEnabled(void)
0x1800329da  test    al, al
0x1800329dc  jz      loc_180032B4E
0x1800329e2  lea     r8, [rbp+5B0h+var_620]
0x1800329e6  mov     rdx, r15
0x1800329e9  mov     rcx, r14
0x1800329ec  call    ?GetFullPathToAUMIDExecutable@@YAJPEAXPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetFullPathToAUMIDExecutable(void *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800329f1  mov     ebx, eax
0x1800329f3  cmp     eax, 80070057h
0x1800329f8  jz      loc_180032AB7
0x1800329fe  test    eax, eax
0x180032a00  jns     short loc_180032A2B
0x180032a02  mov     edx, 1941h; void *
0x180032a07  mov     r9d, eax; char *
0x180032a0a  mov     rcx, [rbp+5B8h]; this
0x180032a11  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032a18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032a1d  lea     rcx, [rbp+5B0h+var_620]
0x180032a21  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032a26  jmp     loc_180032937
0x180032a2b  mov     rcx, [rbp+5B0h+var_620]
0x180032a2f  lea     rdx, [rbp+5B0h+Source]
0x180032a33  mov     [rbp+5B0h+Source], rdi
0x180032a37  call    ?GetEAAumidIfPresent@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetEAAumidIfPresent(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180032a3c  mov     edi, eax
0x180032a3e  cmp     eax, 80090032h
0x180032a43  jnz     loc_180032B13
0x180032a49  mov     rbx, [rbp+5B0h+Source]
0x180032a4d  test    rbx, rbx
0x180032a50  jz      loc_180032B23
0x180032a56  mov     rcx, r15; Source
0x180032a59  call    wcsnlen_s
0x180032a5e  mov     rcx, rbx; Source
0x180032a61  mov     rdi, rax
0x180032a64  call    wcsnlen_s
0x180032a69  cmp     eax, edi
0x180032a6b  jnz     loc_180032B43
0x180032a71  mov     r8d, edi; MaxCount
0x180032a74  mov     rdx, rbx; String2
0x180032a77  mov     rcx, r15; String1
0x180032a7a  call    cs:__imp_wcsncmp
0x180032a81  nop     dword ptr [rax+rax+00h]
0x180032a86  xor     edi, edi
0x180032a88  test    eax, eax
0x180032a8a  jnz     loc_180032B45
0x180032a90  mov     rcx, [rbp+5B8h]; this
0x180032a97  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032a9e  mov     r9d, 80090032h; char *
0x180032aa4  mov     edx, 1953h; void *
0x180032aa9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180032aae  lea     rcx, [rbp+5B0h+Source]
0x180032ab2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032ab7  lea     rcx, [rbp+5B0h+var_620]
0x180032abb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032ac0  lea     rcx, [rbp+5B0h+var_628]
0x180032ac4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032ac9  mov     ebx, edi
0x180032acb  lea     rcx, [rbp+5B0h+TokenHandle]
0x180032acf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032ad4  lea     rcx, [rbp+5B0h+var_5B0]
0x180032ad8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032add  lea     rcx, [rbp+5B0h+var_540]; this
0x180032ae1  call    ??1GetPackageActivationTokenForSxS@LUATelemetry@@QEAA@XZ; LUATelemetry::GetPackageActivationTokenForSxS::~GetPackageActivationTokenForSxS(void)
0x180032ae6  mov     eax, ebx
0x180032ae8  mov     rcx, [rbp+5B0h+var_40]
0x180032aef  xor     rcx, rsp; StackCookie
0x180032af2  call    __security_check_cookie
0x180032af7  mov     rbx, [rsp+6C0h+arg_18]
0x180032aff  add     rsp, 690h
0x180032b06  pop     r15
0x180032b08  pop     r14
0x180032b0a  pop     r13
0x180032b0c  pop     r12
0x180032b0e  pop     rdi
0x180032b0f  pop     rsi
0x180032b10  pop     rbp
0x180032b11  retn
0x180032b13  test    edi, edi
0x180032b15  jz      short loc_180032B43
0x180032b17  cmp     edi, 80070490h
0x180032b1d  jz      short loc_180032B43
0x180032b1f  test    edi, edi
0x180032b21  jns     short loc_180032AAE
0x180032b23  mov     rcx, [rbp+5B8h]; this
0x180032b2a  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032b31  mov     r9d, edi; char *
0x180032b34  mov     edx, 195Ah; void *
0x180032b39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032b3e  jmp     loc_180032AAE
0x180032b43  xor     edi, edi
0x180032b45  lea     rcx, [rbp+5B0h+Source]
0x180032b49  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032b4e  mov     rcx, r14; hToken
0x180032b51  call    cs:__imp_ImpersonateLoggedOnUser
0x180032b58  nop     dword ptr [rax+rax+00h]
0x180032b5d  test    eax, eax
0x180032b5f  jnz     short loc_180032B80
0x180032b61  mov     edx, 195Fh; void *
0x180032b66  mov     rcx, [rbp+5B8h]; this
0x180032b6d  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032b74  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032b79  mov     ebx, eax
0x180032b7b  jmp     loc_180032A1D
0x180032b80  lea     r9, [rbp+5B0h+var_3F0]
0x180032b87  mov     [rsp+6C0h+packageRelativeApplicationId], rdi; int
0x180032b8c  lea     r8, [rbp+5B0h+var_5C0]
0x180032b90  mov     edx, 1
0x180032b95  lea     rcx, [rbp+5B0h+packageFamilyName]
0x180032b9c  call    cs:__imp_RegisterDesktopAppXPackageFamilyIfNecessary
0x180032ba3  nop     dword ptr [rax+rax+00h]
0x180032ba8  mov     ebx, eax
0x180032baa  call    cs:__imp_RevertToSelf
0x180032bb1  nop     dword ptr [rax+rax+00h]
0x180032bb6  cmp     ebx, 80073CF1h
0x180032bbc  jz      loc_180032AB7
0x180032bc2  cmp     ebx, 80270254h
0x180032bc8  jnz     short loc_180032C11
0x180032bca  lea     rdx, [rbp+5B0h+var_62F]
0x180032bce  mov     [rbp+5B0h+var_62F], dil
0x180032bd2  lea     rcx, [rbp+5B0h+packageFamilyName]; lpString2
0x180032bd9  call    IsFamilyProvisioned
0x180032bde  mov     edi, eax
0x180032be0  test    eax, eax
0x180032be2  jns     short loc_180032C04
0x180032be4  mov     rcx, [rbp+5B8h]; this
0x180032beb  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180032bf2  mov     r9d, eax; char *
0x180032bf5  mov     edx, 197Eh; void *
0x180032bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032bff  jmp     loc_180032AB7
0x180032c04  xor     edi, edi
0x180032c06  cmp     [rbp+5B0h+var_62F], dil
0x180032c0a  jnz     short loc_180032C15
0x180032c0c  jmp     loc_180032AB7
0x180032c11  test    ebx, ebx
0x180032c13  jns     short loc_180032C22
0x180032c15  mov     r9d, ebx
0x180032c18  mov     edx, 1985h
0x180032c1d  jmp     loc_180032A0A
0x180032c22  mov     rcx, r14; hToken
0x180032c25  call    cs:__imp_ImpersonateLoggedOnUser
0x180032c2c  nop     dword ptr [rax+rax+00h]
0x180032c31  test    eax, eax
0x180032c33  jnz     short loc_180032C3F
0x180032c35  mov     edx, 1988h
0x180032c3a  jmp     loc_180032B66
0x180032c3f  lea     rax, [rbp+5B0h+var_617]
0x180032c43  mov     [rbp+5B0h+var_60E], dil
0x180032c47  mov     [rsp+6C0h+var_678], rax; bool *
0x180032c4c  xor     r9d, r9d; unsigned int
0x180032c4f  lea     rax, [rbp+5B0h+var_610]
0x180032c53  mov     [rbp+5B0h+var_60F], dil
0x180032c57  mov     [rsp+6C0h+var_680], rax; bool *
0x180032c5c  xor     r8d, r8d; unsigned __int16 *
0x180032c5f  lea     rax, [rbp+5B0h+var_60F]
0x180032c63  mov     [rbp+5B0h+var_610], dil
0x180032c67  mov     [rsp+6C0h+var_688], rax; bool *
0x180032c6c  mov     rdx, r15; unsigned __int16 *
0x180032c6f  lea     rax, [rbp+5B0h+var_60E]
0x180032c73  mov     rcx, r14; void *
0x180032c76  mov     [rsp+6C0h+var_690], rax; bool *
0x180032c7b  lea     rax, [rbp+5B0h+var_62F+1]
  ... truncated ...
```
