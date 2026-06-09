# CResultSetFactory::_AddResultSetsForConfigs(IObjectArray *,IResultShape *,REUSE_MODE,ICondition *,_tagpropertykey const &,IObjectArray *,IRowset *,IProviderConfig *,QUERY_RESULT_TYPE,FORCE_RESULT_TYPE,IServiceProvider *,IIndexerExternalDataSource *,IObjectCollection *)

- ea: `0x1800aea58`
- end: `0x1800af2c1`
- name: `?_AddResultSetsForConfigs@CResultSetFactory@@AEAAJPEAUIObjectArray@@PEAUIResultShape@@W4REUSE_MODE@@PEAUICondition@@AEBU_tagpropertykey@@0PEAUIRowset@@PEAUIProviderConfig@@W4QUERY_RESULT_TYPE@@W4FORCE_RESULT_TYPE@@PEAUIServiceProvider@@PEAUIIndexerExternalDataSource@@PEAUIObjectCollection@@@Z`
- size: `2153`
- prototype: `__int64 __fastcall(__int64, struct IObjectArray *, __int64, unsigned int, struct ICondition *, __int64, struct IObjectArray *, __int64, struct IProviderConfig *, int, int, struct IServiceProvider *punkSite, __int64, struct IObjectArray *)`
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180060620`
- `0x1800a5930`
- `0x1800a62a0`

## callees

- `0x180006ca8`
- `0x18001dbac`
- `0x180022498`
- `0x180034c14`
- `0x180047ae0`
- `0x18004f5b4`
- `0x180052b94`
- `0x1800549e4`
- `0x180055610`
- `0x180056024`
- `0x180062160`
- `0x180062d00`
- `0x180063a68`
- `0x180063f24`
- `0x180064158`
- `0x180066f8c`
- `0x180070088`
- `0x180071dc0`
- `0x18007ec2c`
- `0x1800a96b4`
- `0x1800a983c`
- `0x1800aa8d8`
- `0x1800abba0`
- `0x1800ad1d0`
- `0x1800ae490`
- `0x1800ae5e4`
- `0x1800aea58`
- `0x1800af2c8`
- `0x1800d2640`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x1800aee6e`
- `SHCORE!IUnknown_SetSite` at `0x1800af0e7`
- `SHCORE!IUnknown_SetSite` at `0x1800aee6e`
- `SHCORE!IUnknown_SetSite` at `0x1800af0e7`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x1800aee3d`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x1800aee3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aedb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800af1aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aedb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800af1aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CResultSetFactory::_AddResultSetsForConfigs(
        __int64 a1,
        struct IObjectArray *a2,
        __int64 a3,
        unsigned int a4,
        struct ICondition *a5,
        __int64 a6,
        struct IObjectArray *a7,
        __int64 a8,
        struct IProviderConfig *a9,
        int a10,
        int a11,
        struct IServiceProvider *punkSite,
        __int64 a13,
        struct IObjectArray *a14)
{
  int v15; // edi
  char IsEnabled; // al
  CResultSetFactory *v17; // rcx
  HDPA v18; // rbx
  unsigned int v19; // esi
  unsigned int v20; // eax
  CConfigMergeGroup *Ptr; // rax
  CConfigMergeGroup *v22; // r15
  __int64 (__fastcall ***v23)(_QWORD, GUID *, struct IExternalDataCollector **); // r14
  int v24; // eax
  int v25; // esi
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  bool v28; // si
  __int64 v29; // r8
  struct IFreeThreadedItemContainer *v30; // rcx
  int ExternalProviderIds; // eax
  __int64 v32; // rdx
  unsigned int v33; // r12d
  unsigned int v34; // eax
  PVOID v35; // rsi
  const struct _GUID *v36; // r9
  int v37; // eax
  int Condition; // eax
  int Instance; // eax
  CResultSetFactory *v40; // rcx
  int Config; // eax
  wil::details::in1diag3 *v42; // rcx
  __int64 v43; // rdx
  struct IObjectArray *v44; // r9
  const struct _GUID *v45; // rdx
  CResultSetFactory *v46; // r15
  int v47; // eax
  __int64 v48; // rdx
  struct IObjectArray *v49; // r15
  int updated; // eax
  int v52; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  __int64 v56; // [rsp+38h] [rbp-C8h]
  __int64 v57; // [rsp+40h] [rbp-C0h]
  void *v59; // [rsp+80h] [rbp-80h] BYREF
  CResultSetFactory *v60; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v61)(_QWORD, GUID *, struct IExternalDataCollector **); // [rsp+90h] [rbp-70h] BYREF
  struct IExternalDataCollector *v62; // [rsp+98h] [rbp-68h] BYREF
  void *v63; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-58h] BYREF
  struct IObjectArray *v65; // [rsp+B0h] [rbp-50h]
  unsigned int v66; // [rsp+B8h] [rbp-48h] BYREF
  int v67[2]; // [rsp+C0h] [rbp-40h]
  HDPA hdpa; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v69; // [rsp+D0h] [rbp-30h]
  struct ICondition *v70; // [rsp+D8h] [rbp-28h]
  struct IProviderConfig *v71; // [rsp+E0h] [rbp-20h]
  PROPVARIANT pvar[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v73; // [rsp+F8h] [rbp-8h]
  CResultSetFactory *retaddr; // [rsp+148h] [rbp+48h]

  *(_QWORD *)v67 = a3;
  v60 = (CResultSetFactory *)a1;
  v70 = a5;
  v69 = a8;
  v71 = a9;
  v65 = a14;
  hdpa = 0;
  v15 = CConfigurationGroups::AddConfigurations(
          (CConfigurationGroups *)&hdpa,
          a2,
          a7,
          (const struct _tagpropertykey *)(a1 + 60),
          punkSite);
  wil::com_ptr_t<ICommand,wil::err_returncode_policy>::com_ptr_t<ICommand,wil::err_returncode_policy>(&v61, a13);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl);
  v18 = hdpa;
  if ( !IsEnabled || (v19 = 0, v15 < 0) )
  {
LABEL_30:
    v33 = 0;
    v23 = v61;
    goto LABEL_68;
  }
  while ( 1 )
  {
    if ( v18 )
      v20 = *(_DWORD *)v18;
    else
      v20 = 0;
    if ( v19 >= v20 )
      goto LABEL_30;
    Ptr = (CConfigMergeGroup *)g_pfn_DPA_GetPtr(v18, v19);
    v22 = Ptr;
    v17 = *(CResultSetFactory **)Ptr;
    if ( *(_QWORD *)Ptr == *(_QWORD *)&GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data1 )
    {
      v17 = (CResultSetFactory *)*((_QWORD *)Ptr + 1);
      if ( v17 == *(CResultSetFactory **)GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data4 )
        break;
    }
    ++v19;
  }
  v23 = v61;
  if ( !v61 )
  {
    v66 = 0;
    v24 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)Ptr + 5) + 24LL))(
            *((_QWORD *)Ptr + 5),
            &v66);
    v25 = v24;
    if ( v24 < 0 )
    {
      v26 = (unsigned int)v24;
      v27 = 10905;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)v26,
        v52);
      goto LABEL_89;
    }
    v28 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl'::`2'::impl) )
    {
      v30 = *(struct IFreeThreadedItemContainer **)(a1 + 416);
      if ( v30 )
        v28 = (unsigned int)IsWinRTDataModelItem(v30) != 0;
    }
    v61 = 0;
    *(_OWORD *)pvar = 0;
    v73 = 0;
    LOBYTE(v29) = v28;
    v25 = CreateExternalDataCollector(v66, pvar, v29, &v61);
    std::vector<wil::com_ptr_t<IIndexerExternalDataSource,wil::err_returncode_policy>>::_Tidy(pvar);
    if ( v25 < 0 )
    {
      v26 = (unsigned int)v25;
      v27 = 10914;
      goto LABEL_18;
    }
    v23 = v61;
  }
  v62 = 0;
  ExternalProviderIds = (**v23)(v23, &GUID_01042ba2_b4e2_4c1c_8ccb_63e1fa6523eb, &v62);
  v25 = ExternalProviderIds;
  if ( ExternalProviderIds < 0 )
  {
    v32 = 10919;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)ExternalProviderIds,
      v52);
    wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v62);
    goto LABEL_89;
  }
  ExternalProviderIds = CConfigMergeGroup::GetExternalProviderIds(v22, v62);
  v25 = ExternalProviderIds;
  if ( ExternalProviderIds < 0 )
  {
    v32 = 10920;
    goto LABEL_22;
  }
  LODWORD(v57) = a11;
  LODWORD(v56) = a10;
  ExternalProviderIds = CResultSetFactory::_AddResultSetsForCloudConfigs(
                          a1,
                          v22,
                          *(__int64 *)v67,
                          a4,
                          v70,
                          a6,
                          v69,
                          v56,
                          v57,
                          punkSite);
  v25 = ExternalProviderIds;
  if ( ExternalProviderIds < 0 )
  {
    v32 = 10922;
    goto LABEL_22;
  }
  wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v62);
  v33 = 0;
  while ( 1 )
  {
    if ( v18 )
      v34 = *(_DWORD *)v18;
    else
      v34 = 0;
    if ( v33 >= v34 )
    {
      v49 = v65;
      v15 = CResultSetFactory::_AdjustCompareFlags(v17, v65);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
      {
        if ( v15 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2B10,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)v15,
            v52);
          goto LABEL_87;
        }
        updated = CResultSetFactory::UpdateResultSetsWithExternalData(v60, v49);
        v15 = updated;
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2B12,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)updated,
            v52);
      }
      goto LABEL_86;
    }
    v35 = g_pfn_DPA_GetPtr(v18, v33);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
      goto LABEL_41;
    v17 = *(CResultSetFactory **)v35;
    if ( *(_QWORD *)v35 != *(_QWORD *)&GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data1 )
      break;
    v17 = (CResultSetFactory *)*((_QWORD *)v35 + 1);
    if ( v17 != *(CResultSetFactory **)GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data4 )
      break;
LABEL_67:
    ++v33;
LABEL_68:
    if ( v15 < 0 )
      goto LABEL_69;
  }
  if ( !v23 )
    goto LABEL_41;
  v64 = 0;
  v37 = (**v23)(v23, &GUID_01042ba2_b4e2_4c1c_8ccb_63e1fa6523eb, (struct IExternalDataCollector **)&v64);
  v15 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AC1,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v37,
      v52);
    goto LABEL_77;
  }
  LOWORD(pvar[0]) = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *))(*(_QWORD *)v64 + 40LL))(v64, pvar);
  if ( v15 < 0 )
  {
    v48 = 10947;
    goto LABEL_76;
  }
  v15 = CConfigMergeGroup::SetExternalProviderIds((CConfigMergeGroup *)v35, (struct wil::PropVariant *)pvar);
  if ( v15 < 0 )
  {
    v48 = 10948;
LABEL_76:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v48,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v15,
      v52);
    PropVariantClear(pvar);
LABEL_77:
    wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v64);
    goto LABEL_88;
  }
  PropVariantClear(pvar);
  wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v64);
LABEL_41:
  if ( v71 )
    v17 = (CResultSetFactory *)-(__int64)((unsigned int)CConfigMergeGroup::IsConfigMemberOfGroup(
                                                          (CConfigMergeGroup *)v35,
                                                          v71) != 0);
  v63 = 0;
  Condition = CResultSetFactory::_GetCondition(v17, (struct CConfigMergeGroup *)v35, v70, v36, &v63);
  v15 = Condition;
  if ( Condition >= 0 )
  {
    Instance = SHExtCoCreateInstance(v35, 0, 1025, 0);
    v15 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AD4,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)Instance,
        (int)&GUID_0c733a8a_2a1c_11ce_ade5_00aa0044773d);
LABEL_66:
      SafeRelease<IShellItemArray>(&v63);
      goto LABEL_67;
    }
    IUnknown_SetSite(0, (IUnknown *)punkSite);
    LODWORD(v59) = 0;
    if ( (*(int (__fastcall **)(_QWORD, void **))(**((_QWORD **)v35 + 5) + 24LL))(*((_QWORD *)v35 + 5), &v59) < 0
      || (unsigned int)v59 <= 1 )
    {
      Config = CResultSetFactory::_InitializeProviderWithFirstConfig(
                 v40,
                 (const struct _GUID *)v35,
                 0,
                 *((struct IObjectArray **)v35 + 5),
                 punkSite);
      v15 = Config;
      v42 = retaddr;
      if ( Config >= 0 )
        goto LABEL_64;
      v43 = 11007;
    }
    else
    {
      LODWORD(v59) = 0;
      Config = CResultSetFactory::_GetPreInitDSOProperties(v40, (const struct _GUID *)v35, 0, punkSite, (int *)&v59);
      v15 = Config;
      v42 = retaddr;
      if ( Config < 0 )
      {
        v43 = 10971;
        goto LABEL_63;
      }
      v44 = (struct IObjectArray *)*((_QWORD *)v35 + 5);
      if ( ((unsigned __int8)v59 & 1) != 0 )
      {
        Config = SetDataSourceProperties((const struct _GUID *)v35, 0, 0, v44, punkSite);
        v15 = Config;
        v42 = retaddr;
        if ( Config < 0 )
        {
          v43 = 10976;
          goto LABEL_63;
        }
LABEL_64:
        v52 = v67[0];
        v15 = CResultSetFactory::_AddResultSetsForProvider(v60, 0, v35, *((_QWORD *)v35 + 5));
LABEL_65:
        IUnknown_SetSite(0, 0);
        (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
        goto LABEL_66;
      }
      Config = CResultSetFactory::_InitializeProviderWithFirstConfig(
                 retaddr,
                 (const struct _GUID *)v35,
                 0,
                 v44,
                 punkSite);
      v15 = Config;
      v42 = retaddr;
      if ( Config >= 0 )
      {
        v59 = 0;
        Config = CConfigMergeGroup::GetFirstConfigOnly((CConfigMergeGroup *)v35, v45, &v59);
        v15 = Config;
        v42 = retaddr;
        if ( Config >= 0 )
        {
          v55 = v67[0];
          v46 = v60;
          v47 = CResultSetFactory::_AddResultSetsForProvider(v60, 0, v35, v59);
          v15 = v47;
          if ( v47 >= 0 )
          {
            v52 = (int)v63;
            v15 = CResultSetFactory::_AddResultSetsForConfigsAfterFirst(v46, v35, *(_QWORD *)v67, a4);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2AF2,
              (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
              (const char *)(unsigned int)v47,
              v55);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v59 + 16LL))(v59);
          goto LABEL_65;
        }
        v43 = 10991;
      }
      else
      {
        v43 = 10987;
      }
    }
LABEL_63:
    wil::details::in1diag3::_Log_Hr(
      v42,
      (void *)v43,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)Config,
      v54);
    goto LABEL_65;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2AD0,
    (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
    (const char *)(unsigned int)Condition,
    v53);
LABEL_69:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
    || v15 != -2147023673 )
  {
LABEL_86:
    if ( v15 < 0 )
      goto LABEL_87;
    goto LABEL_88;
  }
  if ( v23 )
  {
    ResultSetFactoryTelemetry::RSF_QueryCancelled((const char *)v60 + 88);
    v60 = 0;
    if ( (int)(**v23)(v23, &GUID_01042ba2_b4e2_4c1c_8ccb_63e1fa6523eb, &v60) >= 0 )
      (*(void (__fastcall **)(CResultSetFactory *))(*(_QWORD *)v60 + 48LL))(v60);
    wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v60);
  }
LABEL_87:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2B27,
    (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
    (const char *)(unsigned int)v15,
    v52);
LABEL_88:
  v25 = v15;
LABEL_89:
  wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v61);
  CConfigurationGroups::~CConfigurationGroups((CConfigurationGroups *)&hdpa);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800aea58  mov     [rsp-8+arg_18], rbx
0x1800aea5d  push    rbp
0x1800aea5e  push    rsi
0x1800aea5f  push    rdi
0x1800aea60  push    r12
0x1800aea62  push    r13
0x1800aea64  push    r14
0x1800aea66  push    r15
0x1800aea68  lea     rbp, [rsp-10h]
0x1800aea6d  sub     rsp, 110h
0x1800aea74  mov     rax, cs:__security_cookie
0x1800aea7b  xor     rax, rsp
0x1800aea7e  mov     [rbp+40h+var_40], rax
0x1800aea82  mov     [rsp+140h+var_D0], r9d
0x1800aea87  mov     qword ptr [rbp+40h+var_80], r8
0x1800aea8b  mov     r12, rcx
0x1800aea8e  mov     [rbp+40h+var_B8], rcx
0x1800aea92  mov     rax, [rbp+40h+arg_20]
0x1800aea96  mov     [rbp+40h+var_68], rax
0x1800aea9a  mov     r8, [rbp+40h+arg_30]; struct IObjectArray *
0x1800aeaa1  mov     rax, [rbp+40h+arg_38]
0x1800aeaa8  mov     [rbp+40h+var_70], rax
0x1800aeaac  mov     rcx, [rbp+40h+arg_40]
0x1800aeab3  mov     [rbp+40h+var_60], rcx
0x1800aeab7  mov     r13, [rbp+40h+punkSite]
0x1800aeabe  mov     rbx, [rbp+40h+arg_60]
0x1800aeac5  mov     r15, [rbp+40h+arg_68]
0x1800aeacc  mov     [rbp+40h+var_90], r15
0x1800aead0  mov     [rbp+40h+hdpa], 0
0x1800aead8  lea     r9, [r12+3Ch]; struct _tagpropertykey *
0x1800aeadd  mov     [rsp+140h+var_120], r13; int
0x1800aeae2  lea     rcx, [rbp+40h+hdpa]; this
0x1800aeae6  call    ?AddConfigurations@CConfigurationGroups@@QEAAJPEAUIObjectArray@@0AEBU_tagpropertykey@@PEAUIServiceProvider@@@Z; CConfigurationGroups::AddConfigurations(IObjectArray *,IObjectArray *,_tagpropertykey const &,IServiceProvider *)
0x1800aeaeb  mov     edi, eax
0x1800aeaed  mov     rdx, rbx
0x1800aeaf0  lea     rcx, [rbp+40h+var_B0]
0x1800aeaf4  call    ??0?$com_ptr_t@UICommand@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUICommand@@@Z; wil::com_ptr_t<ICommand,wil::err_returncode_policy>::com_ptr_t<ICommand,wil::err_returncode_policy>(ICommand *)
0x1800aeaf9  nop
0x1800aeafa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x1800aeb01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1800aeb06  mov     rbx, [rbp+40h+hdpa]
0x1800aeb0a  test    al, al
0x1800aeb0c  jz      loc_1800AECF0
0x1800aeb12  xor     esi, esi
0x1800aeb14  test    edi, edi
0x1800aeb16  js      loc_1800AECF0
0x1800aeb1c  test    rbx, rbx
0x1800aeb1f  jz      short loc_1800AEB25
0x1800aeb21  mov     eax, [rbx]
0x1800aeb23  jmp     short loc_1800AEB27
0x1800aeb25  xor     eax, eax
0x1800aeb27  cmp     esi, eax
0x1800aeb29  jnb     loc_1800AECF0
0x1800aeb2f  mov     edx, esi; i
0x1800aeb31  mov     rcx, rbx; hdpa
0x1800aeb34  call    cs:g_pfn_DPA_GetPtr
0x1800aeb3a  mov     r15, rax
0x1800aeb3d  mov     rcx, [rax]
0x1800aeb40  cmp     rcx, qword ptr cs:_GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data1
0x1800aeb47  jnz     short loc_1800AEB56
0x1800aeb49  mov     rcx, [rax+8]
0x1800aeb4d  cmp     rcx, qword ptr cs:_GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data4
0x1800aeb54  jz      short loc_1800AEB5A
0x1800aeb56  inc     esi
0x1800aeb58  jmp     short loc_1800AEB1C
0x1800aeb5a  mov     r14, [rbp+40h+var_B0]
0x1800aeb5e  test    r14, r14
0x1800aeb61  jnz     loc_1800AEC0E
0x1800aeb67  mov     [rbp+40h+var_88], r14d
0x1800aeb6b  mov     rcx, [rax+28h]
0x1800aeb6f  mov     rax, [rcx]
0x1800aeb72  lea     rdx, [rbp+40h+var_88]
0x1800aeb76  mov     rax, [rax+18h]
0x1800aeb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb7f  mov     esi, eax
0x1800aeb81  test    eax, eax
0x1800aeb83  jns     short loc_1800AEB8F
0x1800aeb85  mov     r9d, eax
0x1800aeb88  mov     edx, 2A99h
0x1800aeb8d  jmp     short loc_1800AEBF5
0x1800aeb8f  mov     sil, r14b
0x1800aeb92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59687846@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846> `wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl(void)'::`2'::impl
0x1800aeb99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(void)
0x1800aeb9e  test    al, al
0x1800aeba0  jz      short loc_1800AEBBB
0x1800aeba2  mov     rcx, [r12+1A0h]; struct IFreeThreadedItemContainer *
0x1800aebaa  test    rcx, rcx
0x1800aebad  jz      short loc_1800AEBBB
0x1800aebaf  call    ?IsWinRTDataModelItem@@YAHPEAUIFreeThreadedItemContainer@@@Z; IsWinRTDataModelItem(IFreeThreadedItemContainer *)
0x1800aebb4  test    eax, eax
0x1800aebb6  jz      short loc_1800AEBBB
0x1800aebb8  mov     sil, 1
0x1800aebbb  mov     [rbp+40h+var_B0], r14
0x1800aebbf  xorps   xmm0, xmm0
0x1800aebc2  movdqu  xmmword ptr [rbp+40h+pvar], xmm0
0x1800aebc7  mov     [rbp+40h+var_48], r14
0x1800aebcb  mov     ecx, [rbp+40h+var_88]
0x1800aebce  lea     r9, [rbp+40h+var_B0]
0x1800aebd2  mov     r8b, sil
0x1800aebd5  lea     rdx, [rbp+40h+pvar]
0x1800aebd9  call    ?CreateExternalDataCollector@@YAJ_KAEAV?$vector@V?$com_ptr_t@UIIndexerExternalDataSource@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIIndexerExternalDataSource@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@_NPEAPEAUIIndexerExternalDataSource@@@Z; CreateExternalDataCollector(unsigned __int64,std::vector<wil::com_ptr_t<IIndexerExternalDataSource,wil::err_returncode_policy>> &,bool,IIndexerExternalDataSource * *)
0x1800aebde  mov     esi, eax
0x1800aebe0  lea     rcx, [rbp+40h+pvar]
0x1800aebe4  call    ?_Tidy@?$vector@V?$com_ptr_t@UIIndexerExternalDataSource@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIIndexerExternalDataSource@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<IIndexerExternalDataSource,wil::err_returncode_policy>>::_Tidy(void)
0x1800aebe9  test    esi, esi
0x1800aebeb  jns     short loc_1800AEC0A
0x1800aebed  mov     r9d, esi; char *
0x1800aebf0  mov     edx, 2AA2h; void *
0x1800aebf5  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800aebfc  mov     rcx, [rbp+48h]; this
0x1800aec00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aec05  jmp     loc_1800AF285
0x1800aec0a  mov     r14, [rbp+40h+var_B0]
0x1800aec0e  mov     [rbp+40h+var_A8], 0
0x1800aec16  mov     rax, [r14]
0x1800aec19  lea     r8, [rbp+40h+var_A8]
0x1800aec1d  lea     rdx, _GUID_01042ba2_b4e2_4c1c_8ccb_63e1fa6523eb
0x1800aec24  mov     rcx, r14
0x1800aec27  mov     rax, [rax]
0x1800aec2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec2f  mov     esi, eax
0x1800aec31  test    eax, eax
0x1800aec33  jns     short loc_1800AEC5C
0x1800aec35  mov     edx, 2AA7h; void *
0x1800aec3a  mov     rcx, [rbp+48h]; this
0x1800aec3e  mov     r9d, eax; char *
0x1800aec41  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800aec48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aec4d  nop
0x1800aec4e  lea     rcx, [rbp+40h+var_A8]
0x1800aec52  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x1800aec57  jmp     loc_1800AF285
0x1800aec5c  mov     rdx, [rbp+40h+var_A8]; struct IExternalDataCollector *
0x1800aec60  mov     rcx, r15; this
0x1800aec63  call    ?GetExternalProviderIds@CConfigMergeGroup@@QEAAJPEAUIExternalDataCollector@@@Z; CConfigMergeGroup::GetExternalProviderIds(IExternalDataCollector *)
0x1800aec68  mov     esi, eax
0x1800aec6a  test    eax, eax
0x1800aec6c  jns     short loc_1800AEC75
0x1800aec6e  mov     edx, 2AA8h
0x1800aec73  jmp     short loc_1800AEC3A
0x1800aec75  mov     [rsp+140h+var_E8], r14
0x1800aec7a  mov     rax, [rbp+40h+var_90]
0x1800aec7e  mov     [rsp+140h+var_F0], rax
0x1800aec83  mov     [rsp+140h+var_F8], r13
0x1800aec88  mov     eax, [rbp+40h+arg_50]
0x1800aec8e  mov     dword ptr [rsp+140h+var_100], eax
0x1800aec92  mov     eax, [rbp+40h+arg_48]
0x1800aec98  mov     dword ptr [rsp+140h+var_108], eax
0x1800aec9c  mov     rax, [rbp+40h+var_70]
0x1800aeca0  mov     [rsp+140h+var_110], rax
0x1800aeca5  mov     rax, [rbp+40h+arg_28]
0x1800aeca9  mov     [rsp+140h+var_118], rax
0x1800aecae  mov     rax, [rbp+40h+var_68]
0x1800aecb2  mov     [rsp+140h+var_120], rax; int
0x1800aecb7  mov     r9d, [rsp+140h+var_D0]
0x1800aecbc  mov     r8, qword ptr [rbp+40h+var_80]
0x1800aecc0  mov     rdx, r15
0x1800aecc3  mov     rcx, r12
0x1800aecc6  call    ?_AddResultSetsForCloudConfigs@CResultSetFactory@@AEAAJPEAVCConfigMergeGroup@@PEAUIResultShape@@W4REUSE_MODE@@PEAUICondition@@AEBU_tagpropertykey@@PEAUIRowset@@W4QUERY_RESULT_TYPE@@W4FORCE_RESULT_TYPE@@PEAUIServiceProvider@@PEAUIObjectCollection@@PEAUIIndexerExternalDataSource@@@Z; CResultSetFactory::_AddResultSetsForCloudConfigs(CConfigMergeGroup *,IResultShape *,REUSE_MODE,ICondition *,_tagpropertykey const &,IRowset *,QUERY_RESULT_TYPE,FORCE_RESULT_TYPE,IServiceProvider *,IObjectCollection *,IIndexerExternalDataSource *)
0x1800aeccb  mov     esi, eax
0x1800aeccd  test    eax, eax
0x1800aeccf  jns     short loc_1800AECDB
0x1800aecd1  mov     edx, 2AAAh
0x1800aecd6  jmp     loc_1800AEC3A
0x1800aecdb  lea     rcx, [rbp+40h+var_A8]
0x1800aecdf  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x1800aece4  xor     r12d, r12d
0x1800aece7  test    rbx, rbx
0x1800aecea  jz      short loc_1800AECFC
0x1800aecec  mov     eax, [rbx]
0x1800aecee  jmp     short loc_1800AECFE
0x1800aecf0  xor     r12d, r12d
0x1800aecf3  mov     r14, [rbp+40h+var_B0]
0x1800aecf7  jmp     loc_1800AF10A
0x1800aecfc  xor     eax, eax
0x1800aecfe  cmp     r12d, eax
0x1800aed01  jnb     loc_1800AF1F9
0x1800aed07  mov     edx, r12d; i
0x1800aed0a  mov     rcx, rbx; hdpa
0x1800aed0d  call    cs:g_pfn_DPA_GetPtr
0x1800aed13  mov     rsi, rax
0x1800aed16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x1800aed1d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1800aed22  test    al, al
0x1800aed24  jz      loc_1800AEDC5
0x1800aed2a  mov     rcx, [rsi]
0x1800aed2d  cmp     rcx, qword ptr cs:_GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data1
0x1800aed34  jnz     short loc_1800AED47
0x1800aed36  mov     rcx, [rsi+8]
0x1800aed3a  cmp     rcx, qword ptr cs:_GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data4
0x1800aed41  jz      loc_1800AF107
0x1800aed47  test    r14, r14
0x1800aed4a  jz      short loc_1800AEDC5
0x1800aed4c  mov     [rbp+40h+var_98], 0
0x1800aed54  mov     rax, [r14]
0x1800aed57  lea     r8, [rbp+40h+var_98]
0x1800aed5b  lea     rdx, _GUID_01042ba2_b4e2_4c1c_8ccb_63e1fa6523eb
0x1800aed62  mov     rcx, r14
0x1800aed65  mov     rax, [rax]
0x1800aed68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed6d  mov     edi, eax
0x1800aed6f  test    eax, eax
0x1800aed71  js      loc_1800AF1C6
0x1800aed77  xor     eax, eax
0x1800aed79  mov     word ptr [rbp+40h+pvar], ax
0x1800aed7d  mov     rcx, [rbp+40h+var_98]
0x1800aed81  mov     rax, [rcx]
0x1800aed84  lea     rdx, [rbp+40h+pvar]
0x1800aed88  mov     rax, [rax+28h]
0x1800aed8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed91  mov     edi, eax
0x1800aed93  test    eax, eax
0x1800aed95  js      loc_1800AF1BF
0x1800aed9b  lea     rdx, [rbp+40h+pvar]; struct wil::PropVariant *
0x1800aed9f  mov     rcx, rsi; this
0x1800aeda2  call    ?SetExternalProviderIds@CConfigMergeGroup@@QEAAJAEAVPropVariant@wil@@@Z; CConfigMergeGroup::SetExternalProviderIds(wil::PropVariant &)
0x1800aeda7  mov     edi, eax
0x1800aeda9  test    eax, eax
0x1800aedab  js      loc_1800AF18D
0x1800aedb1  lea     rcx, [rbp+40h+pvar]; pvar
0x1800aedb5  call    cs:__imp_PropVariantClear
0x1800aedbb  nop
0x1800aedbc  lea     rcx, [rbp+40h+var_98]
0x1800aedc0  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x1800aedc5  mov     r15, [rbp+40h+var_70]
0x1800aedc9  mov     rax, [rbp+40h+var_60]
0x1800aedcd  test    rax, rax
0x1800aedd0  jz      short loc_1800AEDE5
0x1800aedd2  mov     rdx, rax; struct IProviderConfig *
0x1800aedd5  mov     rcx, rsi; this
0x1800aedd8  call    ?IsConfigMemberOfGroup@CConfigMergeGroup@@QEAAHPEAUIProviderConfig@@@Z; CConfigMergeGroup::IsConfigMemberOfGroup(IProviderConfig *)
0x1800aeddd  neg     eax
0x1800aeddf  sbb     rcx, rcx; this
0x1800aede2  and     r15, rcx
0x1800aede5  mov     [rbp+40h+var_A0], 0
0x1800aeded  lea     rax, [rbp+40h+var_A0]
0x1800aedf1  mov     [rsp+140h+var_120], rax; int
0x1800aedf6  mov     r8, [rbp+40h+var_68]; struct ICondition *
0x1800aedfa  mov     rdx, rsi; struct CConfigMergeGroup *
0x1800aedfd  call    ?_GetCondition@CResultSetFactory@@AEAAJPEAVCConfigMergeGroup@@PEAUICondition@@AEBU_GUID@@PEAPEAX@Z; CResultSetFactory::_GetCondition(CConfigMergeGroup *,ICondition *,_GUID const &,void * *)
0x1800aee02  mov     edi, eax
0x1800aee04  mov     rcx, [rbp+48h]; this
0x1800aee08  test    eax, eax
0x1800aee0a  js      loc_1800AF1E0
0x1800aee10  mov     [rsp+140h+punk], 0
0x1800aee19  lea     rax, [rsp+140h+punk]
0x1800aee1e  mov     [rsp+140h+var_118], rax
0x1800aee23  lea     rax, _GUID_0c733a8a_2a1c_11ce_ade5_00aa0044773d
0x1800aee2a  mov     [rsp+140h+var_120], rax; int
0x1800aee2f  xor     r9d, r9d
0x1800aee32  xor     edx, edx
0x1800aee34  mov     r8d, 401h
0x1800aee3a  mov     rcx, rsi
0x1800aee3d  call    cs:__imp_SHExtCoCreateInstance
0x1800aee43  mov     edi, eax
0x1800aee45  mov     rcx, [rbp+48h]; this
0x1800aee49  test    eax, eax
0x1800aee4b  jns     short loc_1800AEE66
0x1800aee4d  mov     r9d, eax; char *
0x1800aee50  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800aee57  mov     edx, 2AD4h; void *
0x1800aee5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aee61  jmp     loc_1800AF0FE
0x1800aee66  mov     rdx, r13; punkSite
0x1800aee69  mov     rcx, [rsp+140h+punk]; punk
0x1800aee6e  call    cs:__imp_IUnknown_SetSite
0x1800aee74  mov     dword ptr [rbp+40h+var_C0], 0
0x1800aee7b  mov     rcx, [rsi+28h]
0x1800aee7f  mov     rax, [rcx]
0x1800aee82  lea     rdx, [rbp+40h+var_C0]
0x1800aee86  mov     rax, [rax+18h]
0x1800aee8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aee8f  test    eax, eax
0x1800aee91  js      loc_1800AF044
0x1800aee97  cmp     dword ptr [rbp+40h+var_C0], 1
0x1800aee9b  jbe     loc_1800AF044
0x1800aeea1  mov     dword ptr [rbp+40h+var_C0], 0
0x1800aeea8  lea     rax, [rbp+40h+var_C0]
0x1800aeeac  mov     [rsp+140h+var_120], rax; int *
0x1800aeeb1  mov     r9, r13; struct IServiceProvider *
0x1800aeeb4  mov     r8, [rsp+140h+punk]; struct IDBProperties *
0x1800aeeb9  mov     rdx, rsi; struct _GUID *
0x1800aeebc  call    ?_GetPreInitDSOProperties@CResultSetFactory@@AEAAJAEBU_GUID@@PEAUIDBProperties@@PEAUIServiceProvider@@PEAH@Z; CResultSetFactory::_GetPreInitDSOProperties(_GUID const &,IDBProperties *,IServiceProvider *,int *)
0x1800aeec1  mov     edi, eax
0x1800aeec3  mov     rcx, [rbp+48h]; this
0x1800aeec7  test    eax, eax
0x1800aeec9  jns     short loc_1800AEED5
0x1800aeecb  mov     edx, 2ADBh
0x1800aeed0  jmp     loc_1800AF069
0x1800aeed5  mov     r9, [rsi+28h]; struct IObjectArray *
0x1800aeed9  mov     [rsp+140h+var_120], r13; struct IServiceProvider *
0x1800aeede  test    byte ptr [rbp+40h+var_C0], 1
0x1800aeee2  jz      short loc_1800AEF0C
0x1800aeee4  xor     r8d, r8d; struct IProviderConfig *
0x1800aeee7  mov     rdx, [rsp+140h+punk]; struct IUnknown *
0x1800aeeec  mov     rcx, rsi; struct _GUID *
0x1800aeeef  call    ?SetDataSourceProperties@@YAJAEBU_GUID@@PEAUIUnknown@@PEAUIProviderConfig@@PEAUIObjectArray@@PEAUIServiceProvider@@@Z; SetDataSourceProperties(_GUID const &,IUnknown *,IProviderConfig *,IObjectArray *,IServiceProvider *)
0x1800aeef4  mov     edi, eax
0x1800aeef6  mov     rcx, [rbp+48h]
0x1800aeefa  test    eax, eax
  ... truncated ...
```
