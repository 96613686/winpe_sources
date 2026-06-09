# GetBestMatchPackageFullNameAndStatus

- ea: `0x180147b50`
- end: `0x1801484e1`
- name: `GetBestMatchPackageFullNameAndStatus`
- size: `2449`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1801138e0`
- `0x1801484e8`

## callees

- `0x180002390`
- `0x1800024a4`
- `0x180028d1c`
- `0x18002bf64`
- `0x18002c6dc`
- `0x18002ca5c`
- `0x18002cd6c`
- `0x18002ce88`
- `0x18002da14`
- `0x18002f738`
- `0x18002fd98`
- `0x180032f18`
- `0x1800504e0`
- `0x180058768`
- `0x1800a7858`
- `0x1800ead10`
- `0x1801106e4`
- `0x1801125c8`
- `0x180127df4`
- `0x1801474ac`
- `0x180147688`
- `0x18014794c`
- `0x180147b50`
- `0x18014a9d4`
- `0x18014c4d8`
- `0x18014cf3c`
- `0x18014d29c`
- `0x18014ddd4`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180147e2f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180147e2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180147ba0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180147ba0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180147cc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801482e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180148337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014838f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801483e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801484b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180147cc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801482e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180148337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014838f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801483e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801484b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180147bfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1801483f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1801484c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180147bfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1801483f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1801484c5`

## string_xrefs

- `0x180147bbc`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`
- `0x18014847f`: `AddDependencyToProcessPackageGraph: Found inbox package %ls that hasn't been registered for the user. Should service = %x.`
- `0x1801480a2`: `AddDependencyToProcessPackageGraph: Package %ls is updating, needs registration, needs remediation and/or not available, but caller said they will service as needed (PackageStatus = %x)`

## pseudocode

```c
__int64 __fastcall GetBestMatchPackageFullNameAndStatus(
        unsigned __int16 *a1,
        _DWORD *a2,
        const char **a3,
        char a4,
        char *a5,
        char a6,
        __int64 a7,
        _QWORD *a8,
        _BYTE *a9)
{
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v14; // eax
  __int64 v15; // rcx
  unsigned __int8 IsEnabled; // al
  int v17; // eax
  int v18; // ebx
  char v19; // al
  __int64 v20; // rcx
  __int64 v21; // r12
  bool v22; // di
  char v23; // r14
  char v24; // si
  __int64 v25; // rcx
  _DWORD *v26; // r8
  const unsigned __int16 *v27; // rsi
  const char *v28; // rdx
  const char *v29; // rax
  __int64 v30; // r9
  tip2::test_flag *v31; // rax
  int v32; // r9d
  char *v33; // r13
  int IsBetterMatch; // edi
  char v35; // al
  __int64 v36; // rcx
  char v37; // r15
  int v38; // eax
  bool v39; // di
  __int64 v40; // rcx
  BOOL v41; // r14d
  unsigned int EffectivePackageStatusForUser; // eax
  int v43; // edi
  char v44; // si
  __int64 v45; // rdx
  _DWORD *v46; // rax
  __int64 v47; // rcx
  char v48; // di
  char v49; // al
  __int64 v50; // rdx
  unsigned __int16 *v51; // rbx
  int v52; // r8d
  int v53; // r9d
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  unsigned __int16 *v59; // rdx
  const char **v60; // rbx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  int v64; // [rsp+20h] [rbp-E0h]
  unsigned int v65; // [rsp+20h] [rbp-E0h]
  __int64 v66; // [rsp+30h] [rbp-D0h]
  bool v67; // [rsp+50h] [rbp-B0h] BYREF
  char v68; // [rsp+51h] [rbp-AFh]
  __int64 v69; // [rsp+58h] [rbp-A8h] BYREF
  char v70; // [rsp+60h] [rbp-A0h] BYREF
  char v71[7]; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned __int16 *v72; // [rsp+68h] [rbp-98h] BYREF
  __int64 v73; // [rsp+70h] [rbp-90h] BYREF
  char *v74; // [rsp+78h] [rbp-88h] BYREF
  int v75; // [rsp+80h] [rbp-80h] BYREF
  __int64 v76; // [rsp+88h] [rbp-78h] BYREF
  int v77; // [rsp+90h] [rbp-70h]
  __int64 v78; // [rsp+98h] [rbp-68h]
  __int64 v79; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v80; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v81; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-48h] BYREF
  char *v83[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-30h]
  __int64 v85; // [rsp+D8h] [rbp-28h]
  __int64 v86; // [rsp+E0h] [rbp-20h]
  __int64 v87; // [rsp+E8h] [rbp-18h]
  __int64 v88; // [rsp+F0h] [rbp-10h]
  __int64 v89; // [rsp+F8h] [rbp-8h]
  __int128 v90; // [rsp+100h] [rbp+0h]
  int v91; // [rsp+110h] [rbp+10h]
  __int64 v92; // [rsp+118h] [rbp+18h]
  __int64 v93; // [rsp+120h] [rbp+20h]
  __int64 *v94; // [rsp+130h] [rbp+30h] BYREF
  __int64 v95; // [rsp+138h] [rbp+38h] BYREF
  char v96; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  _DWORD *v99; // [rsp+1A8h] [rbp+A8h] BYREF
  const char **v100; // [rsp+1B0h] [rbp+B0h]
  char v101; // [rsp+1B8h] [rbp+B8h]

  v101 = a4;
  v100 = a3;
  v99 = a2;
  v96 = 1;
  *a2 = 0;
  v69 = 0;
  v94 = &v69;
  v95 = 0;
  v10 = SRCacheManager_Open(0, &v95);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v94);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)(unsigned int)v10,
      v64);
    v11 = 1176;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v10,
      v64);
LABEL_4:
    v12 = v69;
    v69 = 0;
LABEL_5:
    if ( v12 )
      SRCacheManager_Close(v12);
    return (unsigned int)v10;
  }
  v81 = 0;
  v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
          (struct StateRepository::Cache::Manager_NoThrow *)&v69,
          0,
          &v81);
  if ( v10 < 0 )
  {
    v11 = 1180;
    goto LABEL_3;
  }
  if ( !v81 )
  {
    v10 = -2147009196;
    v11 = 1181;
    goto LABEL_3;
  }
  v82 = 0;
  v10 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v69,
          a1,
          &v82);
  if ( v10 < 0 )
  {
    v11 = 1185;
    goto LABEL_3;
  }
  if ( !v82 )
  {
    v10 = -2147023728;
    v11 = 1186;
    goto LABEL_3;
  }
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v14 = StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(
          (struct StateRepository::Cache::Manager_NoThrow *)&v69,
          v82,
          (struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v76);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A6,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v14,
      v64);
    goto LABEL_18;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl);
  *(_OWORD *)v83 = 0;
  v80 = 32LL * IsEnabled + 13;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v75 = 0;
  v67 = 0;
  v72 = 0;
  v17 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v76, v80, v83, &v67);
  v10 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B6,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v17,
      v64);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v83);
LABEL_18:
    v15 = v76;
    v76 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_4;
  }
  v18 = 0;
  v19 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl);
  v21 = a7;
  v22 = v67;
  v23 = a6;
  if ( v19 )
  {
    LOBYTE(v20) = a6;
    if ( !(unsigned __int8)IsPackageHardeningAllowed(v20) && v22 && HIDWORD(v86) == 2 && v21 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::operator->(
                              v21,
                              &v73)
               + 274LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>(&v73);
    }
  }
  v24 = 0;
  v68 = 0;
  v70 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v25) = v23;
    if ( (unsigned __int8)IsPackageHardeningAllowed(v25) )
    {
      if ( v22 && HIDWORD(v86) == 2 )
      {
        LODWORD(v74) = -1;
        RtlGetDeviceFamilyInfoEnum(0, &v74, 0);
        if ( (_DWORD)v74 != 10 )
        {
          v24 = 1;
          v68 = 1;
          if ( a9 )
            *a9 = 1;
          if ( v21 )
          {
            tip2::tip_test<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::operator->(
              v21,
              &v73);
            *(_BYTE *)(v73 + 274) = 1;
            v27 = (const unsigned __int16 *)v83[1];
            v29 = tip2::details::reason_string(
                    (tip2::details *)"AddDependencyToProcessPackageGraphInboxScenarioTipTest::reason::packageFullNameFlag",
                    v28);
            v31 = (tip2::test_flag *)tip2::details::shared_data<0,0,0>::get_or_add_flag_under_lock(v30 + 8, 5, v29);
            if ( v31 )
              tip2::test_flag::set_value(v31, v27);
            tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::close(&v73);
            tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>(&v73);
            v24 = v68;
          }
          LODWORD(v26) = (_DWORD)a8;
          if ( a8 )
          {
            v26 = (_DWORD *)*a8;
            if ( *(_DWORD *)*a8 > 5u )
            {
              if ( (unsigned __int8)tlgKeywordOn(v26, 0x400000000000LL) )
              {
                v74 = v83[1];
                v73 = 0x1000000;
                v79 = (__int64)a1;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                  (_DWORD)v26,
                  (unsigned int)byte_18035B03B,
                  (_DWORD)v26,
                  v32,
                  (__int64)&v79,
                  (__int64)&v74,
                  (__int64)&v73);
              }
            }
          }
        }
      }
    }
  }
  v33 = a5;
  while ( 1 )
  {
    if ( !v22 )
    {
      v51 = v72;
      v48 = a6;
      goto LABEL_102;
    }
    v74 = 0;
    v71[0] = 0;
    LOBYTE(v26) = v24;
    IsBetterMatch = AddDependencyToProcessPackageGraph_IsBetterMatch(
                      v18,
                      (unsigned int)v83,
                      (_DWORD)v26,
                      (unsigned int)&v70,
                      v23,
                      v21,
                      (__int64)&v74,
                      (__int64)v71);
    if ( IsBetterMatch < 0 )
    {
      v50 = 1264;
      goto LABEL_95;
    }
    v35 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl);
    v37 = v70;
    if ( v35 )
    {
      LOBYTE(v36) = v23;
      if ( (unsigned __int8)IsPackageHardeningAllowed(v36) )
      {
        if ( v24 && !v37 )
        {
          IsBetterMatch = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(&v76, v80, v83, &v67);
          if ( IsBetterMatch >= 0 )
            goto LABEL_51;
          v50 = 1273;
LABEL_95:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v50,
            (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
            (const char *)(unsigned int)IsBetterMatch,
            v65);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v83);
          v58 = v76;
          v76 = 0;
          if ( v58 )
            SRCacheContext_Close(v58);
          v55 = v69;
          v69 = 0;
LABEL_98:
          if ( v55 )
            SRCacheManager_Close(v55);
          return (unsigned int)IsBetterMatch;
        }
      }
    }
    if ( v71[0] )
      break;
LABEL_75:
    IsBetterMatch = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(&v76, v80, v83, &v67);
    if ( IsBetterMatch < 0 )
    {
      v50 = 1370;
      goto LABEL_95;
    }
LABEL_51:
    v22 = v67;
  }
  v38 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
          (struct StateRepository::Cache::Manager_NoThrow *)&v69,
          v81,
          (unsigned __int64)v83[0],
          &v67);
  IsBetterMatch = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x501,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v38,
      v65);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v83);
    v57 = v76;
    v76 = 0;
    if ( v57 )
      SRCacheContext_Close(v57);
    v55 = v69;
    v69 = 0;
    goto LABEL_98;
  }
  v39 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v40) = v23;
    if ( (unsigned __int8)IsPackageHardeningAllowed(v40) )
    {
      if ( v24 )
        v39 = v101 != 0;
    }
  }
  v41 = v67;
  if ( !v67 && !v39 )
    goto LABEL_74;
  EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v83[1], &v75);
  if ( EffectivePackageStatusForUser )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x50E,
            (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
            (const char *)EffectivePackageStatusForUser,
            v65);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v83);
    v56 = v76;
    v76 = 0;
    if ( v56 )
      SRCacheContext_Close(v56);
    v12 = v69;
    v69 = 0;
    goto LABEL_5;
  }
  v43 = v75;
  v44 = 0;
  if ( (v75 & 0x40813FF) != 0 )
  {
    if ( v101 )
    {
      v44 = 1;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x51C,
        (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
        (const char *)0x80073D00LL,
        (int)"AddDependencyToProcessPackageGraph: Package %ls is updating, needs registration, needs remediation and/or n"
             "ot available, but caller said they will service as needed (PackageStatus = %x)",
        v83[1]);
      goto LABEL_64;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x523,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x80073D00LL,
      (int)"AddDependencyToProcessPackageGraph: Package %ls is updating, needs registration, needs remediation and/or not"
           " available and thus not a candidate (PackageStatus = %x)",
      v83[1]);
    v24 = v68;
LABEL_74:
    v23 = a6;
    goto LABEL_75;
  }
LABEL_64:
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v73,
    v83[1],
    -1);
  v45 = v73;
  if ( !v73 )
  {
    IsBetterMatch = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52B,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x8007000ELL,
      v65);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v83);
    v54 = v76;
    v76 = 0;
    if ( v54 )
      SRCacheContext_Close(v54);
    v55 = v69;
    v69 = 0;
    goto LABEL_98;
  }
  v73 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v72,
    v45);
  v46 = v99;
  *v33 = v44;
  *v46 = v43;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl) )
  {
    v24 = v68;
LABEL_73:
    v18 = (int)v74;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
    goto LABEL_74;
  }
  v48 = a6;
  LOBYTE(v47) = a6;
  v49 = IsPackageHardeningAllowed(v47);
  v24 = v68;
  if ( !v49 || !v68 || !v37 )
    goto LABEL_73;
  if ( v41 )
  {
    if ( v21 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::operator->(
                              v21,
                              &v79)
               + 276LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>(&v79);
    }
  }
  else
  {
    *v33 = 1;
  }
  v51 = v72;
  if ( a8 && *(_DWORD *)*a8 > 5u && (unsigned __int8)tlgKeywordOn(*a8, 0x400000000000LL) )
  {
    v79 = 0x1000000;
    LODWORD(v74) = v41;
    v80 = (__int64)v51;
    LODWORD(v99) = *v99;
    v75 = (unsigned __int8)*v33;
    v72 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v52,
      (unsigned int)&word_18035AF6E,
      v52,
      v53,
      (__int64)&v72,
      (__int64)&v80,
      (__int64)&v74,
      (__int64)&v75,
      (__int64)&v99,
      (__int64)&v79);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
LABEL_102:
  v59 = v51;
  v72 = 0;
  v60 = v100;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v100,
    v59);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v61) = v48;
    if ( (unsigned __int8)IsPackageHardeningAllowed(v61) )
    {
      if ( v24 && v101 && *v33 )
      {
        LODWORD(v66) = (unsigned __int8)*v33;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x569,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)0x80073D35LL,
          (int)"AddDependencyToProcessPackageGraph: Found inbox package %ls that hasn't been registered for the user. Sho"
               "uld service = %x.",
          *v60,
          v66);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v83);
  v62 = v76;
  v76 = 0;
  if ( v62 )
    SRCacheContext_Close(v62);
  v63 = v69;
  v69 = 0;
  if ( v63 )
    SRCacheManager_Close(v63);
  return 0;
}

```

## disassembly

```asm
0x180147b50  mov     rax, rsp
0x180147b53  mov     [rax+20h], r9b
0x180147b57  mov     [rax+18h], r8
0x180147b5b  mov     [rax+10h], rdx
0x180147b5f  mov     [rax+8], rcx
0x180147b63  push    rbp
0x180147b64  push    rbx
0x180147b65  push    rsi
0x180147b66  push    rdi
0x180147b67  push    r12
0x180147b69  push    r13
0x180147b6b  push    r14
0x180147b6d  push    r15
0x180147b6f  lea     rbp, [rsp-58h]
0x180147b74  sub     rsp, 158h
0x180147b7b  xor     r13d, r13d
0x180147b7e  mov     [rbp+90h+var_50], 1
0x180147b82  mov     [rdx], r13d
0x180147b85  lea     rax, [rsp+190h+var_138]
0x180147b8a  mov     r15, rcx
0x180147b8d  mov     [rsp+190h+var_138], r13
0x180147b92  lea     rdx, [rbp+90h+var_58]
0x180147b96  mov     [rbp+90h+var_60], rax
0x180147b9a  xor     ecx, ecx
0x180147b9c  mov     [rbp+90h+var_58], r13
0x180147ba0  call    cs:__imp_SRCacheManager_Open
0x180147ba6  lea     rcx, [rbp+90h+var_60]
0x180147baa  mov     ebx, eax
0x180147bac  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180147bb1  test    ebx, ebx
0x180147bb3  jns     short loc_180147C07
0x180147bb5  mov     rcx, [rbp+98h]; this
0x180147bbc  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180147bc3  mov     r9d, ebx; char *
0x180147bc6  mov     edx, 0A5h; void *
0x180147bcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147bd0  mov     edx, 498h; void *
0x180147bd5  mov     rcx, [rbp+98h]; this
0x180147bdc  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180147be3  mov     r9d, ebx; char *
0x180147be6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147beb  mov     rcx, [rsp+190h+var_138]
0x180147bf0  mov     [rsp+190h+var_138], r13
0x180147bf5  test    rcx, rcx
0x180147bf8  jz      short loc_180147C00
0x180147bfa  call    cs:__imp_SRCacheManager_Close
0x180147c00  mov     eax, ebx
0x180147c02  jmp     loc_1801484CD
0x180147c07  lea     r8, [rbp+90h+var_E0]; __int64 *
0x180147c0b  mov     [rbp+90h+var_E0], r13
0x180147c0f  xor     edx, edx; void *
0x180147c11  lea     rcx, [rsp+190h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x180147c16  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180147c1b  mov     ebx, eax
0x180147c1d  test    eax, eax
0x180147c1f  jns     short loc_180147C28
0x180147c21  mov     edx, 49Ch
0x180147c26  jmp     short loc_180147BD5
0x180147c28  cmp     [rbp+90h+var_E0], r13
0x180147c2c  jnz     short loc_180147C3A
0x180147c2e  mov     ebx, 80073D54h
0x180147c33  mov     edx, 49Dh
0x180147c38  jmp     short loc_180147BD5
0x180147c3a  lea     r8, [rbp+90h+var_D8]; __int64 *
0x180147c3e  mov     [rbp+90h+var_D8], r13
0x180147c42  mov     rdx, r15; unsigned __int16 *
0x180147c45  lea     rcx, [rsp+190h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x180147c4a  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180147c4f  mov     ebx, eax
0x180147c51  test    eax, eax
0x180147c53  jns     short loc_180147C5F
0x180147c55  mov     edx, 4A1h
0x180147c5a  jmp     loc_180147BD5
0x180147c5f  mov     rdx, [rbp+90h+var_D8]; __int64
0x180147c63  test    rdx, rdx
0x180147c66  jnz     short loc_180147C77
0x180147c68  mov     ebx, 80070490h
0x180147c6d  mov     edx, 4A2h
0x180147c72  jmp     loc_180147BD5
0x180147c77  lea     r8, [rbp+90h+var_108]; struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *
0x180147c7b  mov     [rbp+90h+var_108], r13
0x180147c7f  lea     rcx, [rsp+190h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x180147c84  mov     [rbp+90h+var_100], r13d
0x180147c88  mov     [rbp+90h+var_F8], r13
0x180147c8c  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x180147c91  mov     ebx, eax
0x180147c93  test    eax, eax
0x180147c95  jns     short loc_180147CCE
0x180147c97  mov     rcx, [rbp+98h]; this
0x180147c9e  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180147ca5  mov     r9d, eax; char *
0x180147ca8  mov     edx, 4A6h; void *
0x180147cad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147cb2  mov     rcx, [rbp+90h+var_108]
0x180147cb6  mov     [rbp+90h+var_108], r13
0x180147cba  test    rcx, rcx
0x180147cbd  jz      loc_180147BEB
0x180147cc3  call    cs:__imp_SRCacheContext_Close
0x180147cc9  jmp     loc_180147BEB
0x180147cce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded> `wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl(void)'::`2'::impl
0x180147cd5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(void)
0x180147cda  movzx   eax, al
0x180147cdd  lea     r9, [rsp+190h+var_140]
0x180147ce2  xorps   xmm0, xmm0
0x180147ce5  shl     rax, 5
0x180147ce9  add     rax, 0Dh
0x180147ced  movdqa  xmmword ptr [rbp+90h+var_D0], xmm0
0x180147cf2  mov     rdx, rax
0x180147cf5  mov     [rbp+90h+var_E8], rax
0x180147cf9  lea     r8, [rbp+90h+var_D0]
0x180147cfd  mov     [rbp+90h+var_C0], r13
0x180147d01  lea     rcx, [rbp+90h+var_108]
0x180147d05  mov     [rbp+90h+var_B8], r13
0x180147d09  mov     [rbp+90h+var_B0], r13
0x180147d0d  mov     [rbp+90h+var_A8], r13
0x180147d11  mov     [rbp+90h+var_A0], r13
0x180147d15  mov     [rbp+90h+var_98], r13
0x180147d19  movdqa  [rbp+90h+var_90], xmm0
0x180147d1e  mov     [rbp+90h+var_80], r13d
0x180147d22  mov     [rbp+90h+var_78], r13
0x180147d26  mov     [rbp+90h+var_70], r13
0x180147d2a  mov     [rbp+90h+var_110], r13d
0x180147d2e  mov     [rsp+190h+var_140], r13b
0x180147d33  mov     [rsp+190h+var_128], r13
0x180147d38  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180147d3d  mov     ebx, eax
0x180147d3f  test    eax, eax
0x180147d41  jns     short loc_180147D76
0x180147d43  mov     rcx, [rbp+98h]; this
0x180147d4a  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180147d51  mov     r9d, eax; char *
0x180147d54  mov     edx, 4B6h; void *
0x180147d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180147d5e  lea     rcx, [rsp+190h+var_128]
0x180147d63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180147d68  lea     rcx, [rbp+90h+var_D0]; this
0x180147d6c  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180147d71  jmp     loc_180147CB2
0x180147d76  mov     rbx, r13
0x180147d79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded> `wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl(void)'::`2'::impl
0x180147d80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(void)
0x180147d85  mov     r12, [rbp+90h+arg_30]
0x180147d8c  mov     dil, [rsp+190h+var_140]
0x180147d91  mov     r14b, [rbp+90h+arg_28]
0x180147d98  test    al, al
0x180147d9a  jz      short loc_180147DD9
0x180147d9c  mov     cl, r14b
0x180147d9f  call    IsPackageHardeningAllowed
0x180147da4  test    al, al
0x180147da6  jnz     short loc_180147DD9
0x180147da8  test    dil, dil
0x180147dab  jz      short loc_180147DD9
0x180147dad  cmp     dword ptr [rbp+90h+var_B0+4], 2
0x180147db1  jnz     short loc_180147DD9
0x180147db3  test    r12, r12
0x180147db6  jz      short loc_180147DD9
0x180147db8  lea     rdx, [rsp+190h+var_120]
0x180147dbd  mov     rcx, r12
0x180147dc0  call    ??C?$tip_test@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::operator->(void)
0x180147dc5  mov     rcx, [rax]
0x180147dc8  mov     byte ptr [rcx+112h], 1
0x180147dcf  lea     rcx, [rsp+190h+var_120]
0x180147dd4  call    ??1?$test_data_control@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>(void)
0x180147dd9  mov     sil, r13b
0x180147ddc  mov     [rsp+190h+var_13F], r13b
0x180147de1  mov     [rsp+190h+var_130], r13b
0x180147de6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded> `wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl(void)'::`2'::impl
0x180147ded  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(void)
0x180147df2  test    al, al
0x180147df4  jz      loc_180147F2E
0x180147dfa  mov     cl, r14b
0x180147dfd  call    IsPackageHardeningAllowed
0x180147e02  test    al, al
0x180147e04  jz      loc_180147F2E
0x180147e0a  test    dil, dil
0x180147e0d  jz      loc_180147F2E
0x180147e13  cmp     dword ptr [rbp+90h+var_B0+4], 2
0x180147e17  jnz     loc_180147F2E
0x180147e1d  xor     r8d, r8d
0x180147e20  mov     dword ptr [rsp+190h+var_118], 0FFFFFFFFh
0x180147e28  lea     rdx, [rsp+190h+var_118]
0x180147e2d  xor     ecx, ecx
0x180147e2f  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180147e35  cmp     dword ptr [rsp+190h+var_118], 0Ah
0x180147e3a  jz      loc_180147F2E
0x180147e40  mov     rax, [rbp+90h+arg_40]
0x180147e47  mov     sil, 1
0x180147e4a  mov     [rsp+190h+var_13F], sil
0x180147e4f  test    rax, rax
0x180147e52  jz      short loc_180147E57
0x180147e54  mov     [rax], sil
0x180147e57  test    r12, r12
0x180147e5a  jz      short loc_180147EBF
0x180147e5c  lea     rdx, [rsp+190h+var_120]
0x180147e61  mov     rcx, r12
0x180147e64  call    ??C?$tip_test@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::operator->(void)
0x180147e69  mov     r9, [rsp+190h+var_120]
0x180147e6e  lea     rcx, aAdddependencyt_6; "AddDependencyToProcessPackageGraphInbox"...
0x180147e75  mov     [r9+112h], sil
0x180147e7c  mov     rsi, [rbp+90h+var_D0+8]
0x180147e80  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180147e85  mov     r8, rax
0x180147e88  lea     rcx, [r9+8]
0x180147e8c  mov     edx, 5
0x180147e91  call    ?get_or_add_flag_under_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<0,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x180147e96  test    rax, rax
0x180147e99  jz      short loc_180147EA6
0x180147e9b  mov     rdx, rsi; unsigned __int16 *
0x180147e9e  mov     rcx, rax; this
0x180147ea1  call    ?set_value@test_flag@tip2@@QEAAXPEBG@Z; tip2::test_flag::set_value(ushort const *)
0x180147ea6  lea     rcx, [rsp+190h+var_120]
0x180147eab  call    ?close@?$test_data_control@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::close(void)
0x180147eb0  lea     rcx, [rsp+190h+var_120]
0x180147eb5  call    ??1?$test_data_control@V?$merged_data@U_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest,_tip_AddDependencyToProcessPackageGraphInboxScenarioTipTest>>(void)
0x180147eba  mov     sil, [rsp+190h+var_13F]
0x180147ebf  mov     r8, [rbp+90h+arg_38]
0x180147ec6  test    r8, r8
0x180147ec9  jz      short loc_180147F2E
0x180147ecb  mov     r8, [r8]
0x180147ece  mov     eax, [r8]
0x180147ed1  cmp     eax, 5
0x180147ed4  jbe     short loc_180147F2E
0x180147ed6  mov     rdx, 400000000000h
0x180147ee0  mov     rcx, r8
0x180147ee3  call    _tlgKeywordOn
0x180147ee8  test    al, al
0x180147eea  jz      short loc_180147F2E
0x180147eec  mov     rax, [rbp+90h+var_D0+8]
0x180147ef0  lea     rdx, byte_18035B03B
0x180147ef7  mov     [rsp+190h+var_118], rax
0x180147efc  mov     rcx, r8
0x180147eff  lea     rax, [rsp+190h+var_120]
0x180147f04  mov     [rsp+190h+var_120], 1000000h
0x180147f0d  mov     [rsp+190h+var_160], rax
0x180147f12  lea     rax, [rsp+190h+var_118]
0x180147f17  mov     [rsp+190h+var_168], rax
0x180147f1c  lea     rax, [rbp+90h+var_F0]
0x180147f20  mov     qword ptr [rsp+190h+var_170], rax
0x180147f25  mov     [rbp+90h+var_F0], r15
0x180147f29  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180147f2e  mov     r13, [rbp+90h+arg_20]
0x180147f35  xor     r15d, r15d
0x180147f38  test    dil, dil
0x180147f3b  jz      loc_180148402
0x180147f41  lea     rax, [rsp+190h+var_12F]
0x180147f46  mov     [rsp+190h+var_118], r15
0x180147f4b  mov     [rsp+190h+var_158], rax
0x180147f50  lea     r9, [rsp+190h+var_130]
0x180147f55  lea     rax, [rsp+190h+var_118]
0x180147f5a  mov     [rsp+190h+var_12F], r15b
0x180147f5f  mov     [rsp+190h+var_160], rax
0x180147f64  lea     rdx, [rbp+90h+var_D0]
0x180147f68  mov     [rsp+190h+var_168], r12
0x180147f6d  mov     r8b, sil
0x180147f70  mov     rcx, rbx
0x180147f73  mov     byte ptr [rsp+190h+var_170], r14b; int
0x180147f78  call    AddDependencyToProcessPackageGraph_IsBetterMatch
0x180147f7d  mov     edi, eax
0x180147f7f  test    eax, eax
0x180147f81  js      loc_1801483A5
0x180147f87  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded> `wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl(void)'::`2'::impl
0x180147f8e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(void)
0x180147f93  mov     r15b, [rsp+190h+var_130]
0x180147f98  test    al, al
0x180147f9a  jz      short loc_180147FDF
0x180147f9c  mov     cl, r14b
0x180147f9f  call    IsPackageHardeningAllowed
0x180147fa4  test    al, al
0x180147fa6  jz      short loc_180147FDF
0x180147fa8  test    sil, sil
0x180147fab  jz      short loc_180147FDF
0x180147fad  test    r15b, r15b
0x180147fb0  jnz     short loc_180147FDF
0x180147fb2  mov     rdx, [rbp+90h+var_E8]
0x180147fb6  lea     r9, [rsp+190h+var_140]
0x180147fbb  lea     r8, [rbp+90h+var_D0]
0x180147fbf  lea     rcx, [rbp+90h+var_108]
0x180147fc3  call    ?GetNext@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180147fc8  xor     r15d, r15d
0x180147fcb  mov     edi, eax
0x180147fcd  test    eax, eax
0x180147fcf  js      loc_1801481A2
0x180147fd5  mov     dil, [rsp+190h+var_140]
0x180147fda  jmp     loc_180147F38
0x180147fdf  cmp     [rsp+190h+var_12F], 0
0x180147fe4  jz      loc_180148175
0x180147fea  mov     r8, [rbp+90h+var_D0]; __int64
0x180147fee  lea     r9, [rsp+190h+var_140]; bool *
0x180147ff3  mov     rdx, [rbp+90h+var_E0]; __int64
0x180147ff7  lea     rcx, [rsp+190h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x180147ffc  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x180148001  mov     edi, eax
0x180148003  test    eax, eax
0x180148005  js      loc_180148350
0x18014800b  xor     dil, dil
0x18014800e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded> `wil::Feature<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::GetImpl(void)'::`2'::impl
0x180148015  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureProcessPackageGraphApisPickCorrectInboxPackageAndRegisterIfNeeded>::__private_IsEnabled(void)
0x18014801a  test    al, al
0x18014801c  jz      short loc_18014803B
0x18014801e  mov     cl, r14b
  ... truncated ...
```
