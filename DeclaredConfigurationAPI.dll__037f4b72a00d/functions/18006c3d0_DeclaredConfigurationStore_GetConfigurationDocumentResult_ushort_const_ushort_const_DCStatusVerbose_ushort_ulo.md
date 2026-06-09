# DeclaredConfigurationStore_GetConfigurationDocumentResult(ushort const *,ushort const *,DCStatusVerbose,ushort *,ulong *)

- ea: `0x18006c3d0`
- end: `0x18006cc66`
- name: `?DeclaredConfigurationStore_GetConfigurationDocumentResult@@YAJPEBG0W4DCStatusVerbose@@PEAGPEAK@Z`
- size: `2198`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, enum DCStatusVerbose, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011f9c`
- `0x180019d38`
- `0x18001cce4`
- `0x18001ce5c`
- `0x18001cfa4`
- `0x18001d0b0`
- `0x18001df44`
- `0x18001e090`
- `0x180023400`
- `0x18004b870`
- `0x18004d1ac`
- `0x1800556cc`
- `0x180058b08`
- `0x180059834`
- `0x18006c3d0`
- `0x1800725e0`
- `0x1800a0228`
- `0x1800a0264`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1800f9e64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c79d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c79d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c7b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c851`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c7b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c851`
- `RPCRT4!UuidFromStringW` at `0x18006c452`
- `RPCRT4!UuidFromStringW` at `0x18006c452`
- `OLEAUT32!__imp_SysAllocString` at `0x18006c4b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006c696`
- `OLEAUT32!__imp_SysAllocString` at `0x18006c841`
- `OLEAUT32!__imp_SysAllocString` at `0x18006c4b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006c696`
- `OLEAUT32!__imp_SysAllocString` at `0x18006c841`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c836`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c836`
- `OLEAUT32!__imp_SysStringLen` at `0x18006cadd`
- `OLEAUT32!__imp_SysStringLen` at `0x18006cadd`
- `OLEAUT32!__imp_VariantInit` at `0x18006c97b`
- `OLEAUT32!__imp_VariantInit` at `0x18006c97b`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006c7c0`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006c7c0`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18006c73f`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18006c73f`
- `dmEnrollEngine!GetEnrollmentType` at `0x18006c482`
- `dmEnrollEngine!GetEnrollmentType` at `0x18006c482`

## string_xrefs

- `0x18006c6ad`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006c756`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006c7f6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006c86f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006c8ff`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006ca4f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006ca9f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006cb09`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006cb68`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006cbe5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006cc34`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006c9d3`: `DeclaredConfigurationStore_GetJsonDeclaredConfigurationResults failed to generate JSON results`
- `0x18006c9da`: `DeclaredConfigurationStore_GetConfigurationDocumentResult`
- `0x18006ca29`: `DeclaredConfigurationStore_GetConfigurationDocumentResult`
- `0x18006ca1b`: `JSON results generated successfully`
- `0x18006ca22`: `DeclaredConfigurationStore_GetJsonDeclaredConfigurationResults`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DeclaredConfigurationStore_GetConfigurationDocumentResult(
        OLECHAR *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        UINT *a5)
{
  __int64 v7; // rdx
  RPC_STATUS v8; // ebx
  int EnrollmentType; // eax
  BSTR v10; // r15
  _QWORD *v11; // rax
  int v12; // edi
  int v13; // ebx
  unsigned __int16 *v14; // rcx
  unsigned __int16 v15; // ax
  OLECHAR *v16; // rcx
  OLECHAR v17; // ax
  int v18; // ebx
  unsigned __int16 *v19; // rbx
  char **v20; // rcx
  __int64 v21; // r8
  OLECHAR *v22; // rax
  int CurrentUserSid; // eax
  char IsEnabled; // al
  int JsonDeclaredConfigurationResults; // eax
  CDeclaredConfigurationLogger *v26; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *bstrVal; // rbx
  UINT v29; // eax
  UINT v30; // r11d
  int v31; // eax
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  char *v35; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v39; // [rsp+60h] [rbp-A0h]
  BSTR v40; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h]
  int v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+84h] [rbp-7Ch]
  int v44; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v45; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v46[4]; // [rsp+98h] [rbp-68h] BYREF
  char v47; // [rsp+B8h] [rbp-48h]
  OLECHAR *psz; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v50; // [rsp+E0h] [rbp-20h] BYREF
  HKEY v51; // [rsp+E8h] [rbp-18h] BYREF
  char v52; // [rsp+F0h] [rbp-10h]
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  psz = a1;
  v45 = a2;
  LODWORD(v35) = 0;
  if ( !a1 || !a2 || !a5 )
  {
    v7 = 22611;
    goto LABEL_67;
  }
  if ( a4 )
  {
    if ( !*a5 )
    {
      v7 = 22618;
LABEL_67:
      v8 = -2147024809;
      goto LABEL_68;
    }
    *a4 = 0;
  }
  Uuid = 0;
  v8 = UuidFromStringW(a1, &Uuid);
  if ( v8 < 0 )
  {
    v7 = 22624;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v8,
      v33);
    return (unsigned int)v8;
  }
  v44 = 63;
  *(UUID *)hMem = Uuid;
  EnrollmentType = GetEnrollmentType(hMem, &v44);
  v8 = EnrollmentType;
  LODWORD(v35) = EnrollmentType;
  if ( EnrollmentType == -2147024894 )
  {
    v8 = -2102525946;
    LODWORD(v35) = -2102525946;
LABEL_13:
    v7 = 22632;
    goto LABEL_68;
  }
  if ( EnrollmentType < 0 )
    goto LABEL_13;
  v10 = SysAllocString(psz);
  if ( !v10 )
  {
    v8 = -2147024882;
    v7 = 22635;
    goto LABEL_68;
  }
  v37[0] = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
  {
    v11 = tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(hMem);
    wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(
      v37,
      v11);
    wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(hMem);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             v37,
                             hMem)
              + 272LL) = 3;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
    v12 = -2128831035;
    v13 = -2128831035;
    v14 = v45;
    if ( v45 )
    {
      while ( 1 )
      {
        v15 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        v13 = 16777619 * (v15 ^ v13);
      }
    }
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             v37,
                             hMem)
              + 284LL) = v13;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
    v16 = psz;
    if ( psz )
    {
      while ( 1 )
      {
        v17 = *v16;
        if ( !*v16 )
          break;
        ++v16;
        v12 = 16777619 * (v17 ^ v12);
      }
    }
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             v37,
                             hMem)
              + 288LL) = v12;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
    v18 = v44;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             v37,
                             hMem)
              + 292LL) = v18;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             v37,
                             hMem)
              + 276LL) = a3;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
    {
      v19 = v45;
      v20 = (char **)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                   v37,
                                   hMem)
                    + 304LL);
      v21 = -1;
      do
        ++v21;
      while ( v19[v21] );
      std::wstring::_Assign<unsigned short>(v20, v19, (char *)v21);
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
    }
  }
  v46[0] = v37;
  v46[1] = &v35;
  v46[2] = &psz;
  v46[3] = &v45;
  v47 = 1;
  bstrString = 0;
  v42 = 0;
  v40 = v10;
  v43 = v44;
  v22 = SysAllocString(L"Device");
  if ( v22 )
  {
    bstrString = v22;
    v42 = 0;
    v36 = 0;
    hMem[0] = &v36;
    hMem[1] = 0;
    v39 = 1;
    LODWORD(v35) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                     (struct DeclaredConfigurationScopeData *)&v40,
                     v45,
                     (HKEY *)&hMem[1],
                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(hMem);
    if ( (int)v35 < 0 )
    {
      hMem[0] = 0;
      CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)hMem);
      v8 = CurrentUserSid;
      LODWORD(v35) = CurrentUserSid;
      if ( CurrentUserSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58B3,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)CurrentUserSid,
          v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
        v47 = 0;
        lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
        goto LABEL_65;
      }
      if ( !(unsigned int)_o__wcsicmp(L"S-1-5-18", hMem[0]) )
      {
        LocalFree(hMem[0]);
        hMem[0] = 0;
        LODWORD(v35) = DmGetActiveUserSid((unsigned __int16 **)hMem);
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl'::`2'::impl);
        v8 = (int)v35;
        if ( IsEnabled && (_DWORD)v35 == -2102788088 )
        {
          v8 = -2147023728;
          LODWORD(v35) = -2147023728;
        }
        if ( v8 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x58C2,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v8,
            v33);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
          v47 = 0;
          lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
          goto LABEL_65;
        }
      }
      SysFreeString(bstrString);
      bstrString = SysAllocString((const OLECHAR *)hMem[0]);
      LocalFree(hMem[0]);
      hMem[0] = 0;
      if ( !bstrString )
      {
        v8 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58CC,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
        v47 = 0;
        lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
        goto LABEL_65;
      }
      v42 = 1;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v36,
        0);
      v50 = &v36;
      v51 = 0;
      v52 = 1;
      LODWORD(v35) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                       (struct DeclaredConfigurationScopeData *)&v40,
                       v45,
                       &v51,
                       0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v50);
      v8 = (int)v35;
      if ( (int)v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58D8,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v35,
          v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
        v47 = 0;
        lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
        goto LABEL_65;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl'::`2'::impl) )
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v36,
          0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl'::`2'::impl) )
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v36,
        0);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
      JsonDeclaredConfigurationResults = DeclaredConfigurationStore_GetJsonDeclaredConfigurationResults(
                                           v45,
                                           (struct DeclaredConfigurationScopeData *)&v40,
                                           a3,
                                           &pvarg,
                                           (__int64)v37);
    else
      JsonDeclaredConfigurationResults = DeclaredConfigurationStore_GetJsonDeclaredConfigurationResults(
                                           v45,
                                           (struct DeclaredConfigurationScopeData *)&v40,
                                           a3,
                                           &pvarg,
                                           0);
    LODWORD(v35) = JsonDeclaredConfigurationResults;
    if ( JsonDeclaredConfigurationResults >= 0 )
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
        Logger,
        L"DeclaredConfigurationStore_GetConfigurationDocumentResult",
        L"DeclaredConfigurationStore_GetJsonDeclaredConfigurationResults",
        L"JSON results generated successfully");
      if ( pvarg.vt == 8 )
      {
        bstrVal = pvarg.bstrVal;
        if ( pvarg.llVal )
        {
          v29 = SysStringLen(pvarg.bstrVal);
          v30 = v29 + 1;
          if ( v29 + 1 < v29 )
          {
            v8 = -2147024362;
            LODWORD(v35) = -2147024362;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5913,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)0x80070216LL,
              v34);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
            v47 = 0;
            lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
          }
          else
          {
            LODWORD(v35) = 0;
            if ( *a5 >= v30 )
            {
              if ( !a4 || (v31 = StringCchCopyW(a4, v30, bstrVal), v8 = v31, LODWORD(v35) = v31, v31 >= 0) )
              {
                *a5 = v30;
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
                DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
                v47 = 0;
                lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
                wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(v37);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x591F,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)(unsigned int)v31,
                v34);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
              DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
              v47 = 0;
              lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
            }
            else
            {
              *a5 = v30;
              v8 = -2147024774;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5919,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)0x8007007ALL,
                v34);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
              DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
              v47 = 0;
              lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
            }
          }
        }
        else
        {
          v8 = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x590D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8000FFFFLL,
            v34);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
          v47 = 0;
          lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
        }
      }
      else
      {
        v8 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5905,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8000FFFFLL,
          v34);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
        v47 = 0;
        lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
      }
    }
    else
    {
      v26 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v26,
        L"DeclaredConfigurationStore_GetConfigurationDocumentResult",
        L"DeclaredConfigurationStore_GetJsonDeclaredConfigurationResults failed to generate JSON results",
        &word_180142E98,
        (int)v35);
      v8 = (int)v35;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
      v47 = 0;
      lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
    }
    goto LABEL_65;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x589A,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)0x8007000ELL,
    v33);
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
  v47 = 0;
  lambda_5f4611dcbc0b3efea0751769cca0839c_::operator()(v46);
LABEL_65:
  wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006c3d0  push    rbp
0x18006c3d2  push    rbx
0x18006c3d3  push    rsi
0x18006c3d4  push    rdi
0x18006c3d5  push    r12
0x18006c3d7  push    r13
0x18006c3d9  push    r14
0x18006c3db  push    r15
0x18006c3dd  lea     rbp, [rsp-28h]
0x18006c3e2  sub     rsp, 128h
0x18006c3e9  mov     rax, cs:__security_cookie
0x18006c3f0  xor     rax, rsp
0x18006c3f3  mov     [rbp+60h+var_50], rax
0x18006c3f7  mov     r14, r9
0x18006c3fa  mov     r12d, r8d
0x18006c3fd  mov     [rbp+60h+psz], rcx
0x18006c401  mov     [rbp+60h+var_D0], rdx
0x18006c405  mov     rsi, [rbp+60h+arg_20]
0x18006c40c  xor     r13d, r13d
0x18006c40f  mov     dword ptr [rsp+160h+var_130], r13d
0x18006c414  test    rcx, rcx
0x18006c417  jz      loc_18006CC27
0x18006c41d  test    rdx, rdx
0x18006c420  jz      loc_18006CC27
0x18006c426  test    rsi, rsi
0x18006c429  jz      loc_18006CC27
0x18006c42f  test    r9, r9
0x18006c432  jz      short loc_18006C447
0x18006c434  cmp     [rsi], r13d
0x18006c437  jnz     short loc_18006C443
0x18006c439  mov     edx, 585Ah
0x18006c43e  jmp     loc_18006CC2C
0x18006c443  mov     [r9], r13w
0x18006c447  xorps   xmm0, xmm0
0x18006c44a  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x18006c44e  lea     rdx, [rbp+60h+Uuid]; Uuid
0x18006c452  call    cs:__imp_UuidFromStringW
0x18006c458  mov     ebx, eax
0x18006c45a  test    eax, eax
0x18006c45c  jns     short loc_18006C468
0x18006c45e  mov     edx, 5860h
0x18006c463  jmp     loc_18006CC31
0x18006c468  mov     [rbp+60h+var_D8], 3Fh ; '?'
0x18006c46f  movaps  xmm0, xmmword ptr [rbp+60h+Uuid.Data1]
0x18006c473  movdqa  xmmword ptr [rsp+160h+hMem], xmm0
0x18006c479  lea     rdx, [rbp+60h+var_D8]
0x18006c47d  lea     rcx, [rsp+160h+hMem]
0x18006c482  call    cs:__imp_GetEnrollmentType
0x18006c488  mov     ebx, eax
0x18006c48a  mov     dword ptr [rsp+160h+var_130], eax
0x18006c48e  cmp     eax, 80070002h
0x18006c493  jnz     short loc_18006C4A0
0x18006c495  mov     ebx, 82AE0006h
0x18006c49a  mov     dword ptr [rsp+160h+var_130], ebx
0x18006c49e  jmp     short loc_18006C4A4
0x18006c4a0  test    eax, eax
0x18006c4a2  jns     short loc_18006C4AE
0x18006c4a4  mov     edx, 5868h
0x18006c4a9  jmp     loc_18006CC31
0x18006c4ae  mov     rcx, [rbp+60h+psz]; psz
0x18006c4b2  call    cs:__imp_SysAllocString
0x18006c4b8  mov     r15, rax
0x18006c4bb  test    rax, rax
0x18006c4be  jnz     short loc_18006C4CF
0x18006c4c0  mov     ebx, 8007000Eh
0x18006c4c5  mov     edx, 586Bh
0x18006c4ca  jmp     loc_18006CC31
0x18006c4cf  mov     [rsp+160h+var_120], r13
0x18006c4d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl(void)'::`2'::impl
0x18006c4db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(void)
0x18006c4e0  test    al, al
0x18006c4e2  jz      loc_18006C655
0x18006c4e8  lea     rcx, [rsp+160h+hMem]
0x18006c4ed  call    ??$start@V?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(void)
0x18006c4f2  mov     rdx, rax
0x18006c4f5  lea     rcx, [rsp+160h+var_120]
0x18006c4fa  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy> &&)
0x18006c4ff  lea     rcx, [rsp+160h+hMem]
0x18006c504  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x18006c509  lea     rdx, [rsp+160h+hMem]
0x18006c50e  lea     rcx, [rsp+160h+var_120]
0x18006c513  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18006c518  mov     rcx, [rax]
0x18006c51b  mov     dword ptr [rcx+110h], 3
0x18006c525  lea     rcx, [rsp+160h+hMem]
0x18006c52a  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006c52f  mov     edi, 811C9DC5h
0x18006c534  mov     ebx, edi
0x18006c536  mov     rcx, [rbp+60h+var_D0]
0x18006c53a  test    rcx, rcx
0x18006c53d  jz      short loc_18006C558
0x18006c53f  jmp     short loc_18006C550
0x18006c541  movzx   eax, ax
0x18006c544  lea     rcx, [rcx+2]
0x18006c548  xor     ebx, eax
0x18006c54a  imul    ebx, 1000193h
0x18006c550  movzx   eax, word ptr [rcx]
0x18006c553  test    ax, ax
0x18006c556  jnz     short loc_18006C541
0x18006c558  lea     rdx, [rsp+160h+hMem]
0x18006c55d  lea     rcx, [rsp+160h+var_120]
0x18006c562  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18006c567  mov     rcx, [rax]
0x18006c56a  mov     [rcx+11Ch], ebx
0x18006c570  lea     rcx, [rsp+160h+hMem]
0x18006c575  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006c57a  mov     rcx, [rbp+60h+psz]
0x18006c57e  test    rcx, rcx
0x18006c581  jz      short loc_18006C59C
0x18006c583  jmp     short loc_18006C594
0x18006c585  movzx   eax, ax
0x18006c588  lea     rcx, [rcx+2]
0x18006c58c  xor     edi, eax
0x18006c58e  imul    edi, 1000193h
0x18006c594  movzx   eax, word ptr [rcx]
0x18006c597  test    ax, ax
0x18006c59a  jnz     short loc_18006C585
0x18006c59c  lea     rdx, [rsp+160h+hMem]
0x18006c5a1  lea     rcx, [rsp+160h+var_120]
0x18006c5a6  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18006c5ab  mov     rcx, [rax]
0x18006c5ae  mov     [rcx+120h], edi
0x18006c5b4  lea     rcx, [rsp+160h+hMem]
0x18006c5b9  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006c5be  mov     ebx, [rbp+60h+var_D8]
0x18006c5c1  lea     rdx, [rsp+160h+hMem]
0x18006c5c6  lea     rcx, [rsp+160h+var_120]
0x18006c5cb  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18006c5d0  mov     rcx, [rax]
0x18006c5d3  mov     [rcx+124h], ebx
0x18006c5d9  lea     rcx, [rsp+160h+hMem]
0x18006c5de  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006c5e3  lea     rdx, [rsp+160h+hMem]
0x18006c5e8  lea     rcx, [rsp+160h+var_120]
0x18006c5ed  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18006c5f2  mov     rcx, [rax]
0x18006c5f5  mov     [rcx+114h], r12d
0x18006c5fc  lea     rcx, [rsp+160h+hMem]
0x18006c601  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006c606  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl(void)'::`2'::impl
0x18006c60d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(void)
0x18006c612  test    al, al
0x18006c614  jz      short loc_18006C655
0x18006c616  mov     rbx, [rbp+60h+var_D0]
0x18006c61a  lea     rdx, [rsp+160h+hMem]
0x18006c61f  lea     rcx, [rsp+160h+var_120]
0x18006c624  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18006c629  nop
0x18006c62a  mov     rcx, [rax]
0x18006c62d  add     rcx, 130h
0x18006c634  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006c638  inc     r8
0x18006c63b  cmp     [rbx+r8*2], r13w
0x18006c640  jnz     short loc_18006C638
0x18006c642  mov     rdx, rbx
0x18006c645  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18006c64a  nop
0x18006c64b  lea     rcx, [rsp+160h+hMem]
0x18006c650  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006c655  lea     rax, [rsp+160h+var_120]
0x18006c65a  mov     [rbp+60h+var_C8], rax
0x18006c65e  lea     rax, [rsp+160h+var_130]
0x18006c663  mov     [rbp+60h+var_C0], rax
0x18006c667  lea     rax, [rbp+60h+psz]
0x18006c66b  mov     [rbp+60h+var_B8], rax
0x18006c66f  lea     rax, [rbp+60h+var_D0]
0x18006c673  mov     [rbp+60h+var_B0], rax
0x18006c677  mov     [rbp+60h+var_A8], 1
0x18006c67b  mov     [rsp+160h+bstrString], r13
0x18006c680  mov     [rbp+60h+var_E0], r13d
0x18006c684  mov     [rsp+160h+var_F0], r15
0x18006c689  mov     eax, [rbp+60h+var_D8]
0x18006c68c  mov     [rbp+60h+var_DC], eax
0x18006c68f  lea     rcx, aDevice_2; "Device"
0x18006c696  call    cs:__imp_SysAllocString
0x18006c69c  test    rax, rax
0x18006c69f  jnz     short loc_18006C6DD
0x18006c6a1  mov     rcx, [rbp+68h]; this
0x18006c6a5  mov     ebx, 8007000Eh
0x18006c6aa  mov     r9d, ebx; char *
0x18006c6ad  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006c6b4  mov     edx, 589Ah; void *
0x18006c6b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c6be  nop
0x18006c6bf  lea     rcx, [rsp+160h+var_F0]; this
0x18006c6c4  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006c6c9  nop
0x18006c6ca  mov     [rbp+60h+var_A8], r13b
0x18006c6ce  lea     rcx, [rbp+60h+var_C8]
0x18006c6d2  call    _lambda_5f4611dcbc0b3efea0751769cca0839c___operator__
0x18006c6d7  nop
0x18006c6d8  jmp     loc_18006CC1B
0x18006c6dd  mov     [rsp+160h+bstrString], rax
0x18006c6e2  mov     [rbp+60h+var_E0], r13d
0x18006c6e6  mov     [rsp+160h+var_128], r13
0x18006c6eb  lea     rax, [rsp+160h+var_128]
0x18006c6f0  mov     [rsp+160h+hMem], rax
0x18006c6f5  mov     [rsp+160h+hMem+8], r13
0x18006c6fa  mov     [rsp+160h+var_100], 1
0x18006c6ff  xor     r9d, r9d; int
0x18006c702  lea     r8, [rsp+160h+hMem+8]; HKEY *
0x18006c707  mov     rdx, [rbp+60h+var_D0]; unsigned __int16 *
0x18006c70b  lea     rcx, [rsp+160h+var_F0]; struct DeclaredConfigurationScopeData *
0x18006c710  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18006c715  mov     dword ptr [rsp+160h+var_130], eax
0x18006c719  lea     rcx, [rsp+160h+hMem]
0x18006c71e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18006c723  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl(void)'::`2'::impl
0x18006c72a  cmp     dword ptr [rsp+160h+var_130], r13d
0x18006c72f  jge     loc_18006C952
0x18006c735  mov     [rsp+160h+hMem], r13
0x18006c73a  lea     rcx, [rsp+160h+hMem]
0x18006c73f  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x18006c745  mov     ebx, eax
0x18006c747  mov     dword ptr [rsp+160h+var_130], eax
0x18006c74b  test    eax, eax
0x18006c74d  jns     short loc_18006C791
0x18006c74f  mov     rcx, [rbp+68h]; this
0x18006c753  mov     r9d, eax; char *
0x18006c756  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006c75d  mov     edx, 58B3h; void *
0x18006c762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c767  nop
0x18006c768  lea     rcx, [rsp+160h+var_128]
0x18006c76d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c772  nop
0x18006c773  lea     rcx, [rsp+160h+var_F0]; this
0x18006c778  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006c77d  nop
0x18006c77e  mov     [rbp+60h+var_A8], r13b
0x18006c782  lea     rcx, [rbp+60h+var_C8]
0x18006c786  call    _lambda_5f4611dcbc0b3efea0751769cca0839c___operator__
0x18006c78b  nop
0x18006c78c  jmp     loc_18006CC1B
0x18006c791  mov     rdx, [rsp+160h+hMem]
0x18006c796  lea     rcx, aS1518; "S-1-5-18"
0x18006c79d  call    cs:__imp__o__wcsicmp
0x18006c7a3  test    eax, eax
0x18006c7a5  jnz     loc_18006C831
0x18006c7ab  mov     rcx, [rsp+160h+hMem]; hMem
0x18006c7b0  call    cs:__imp_LocalFree
0x18006c7b6  mov     [rsp+160h+hMem], r13
0x18006c7bb  lea     rcx, [rsp+160h+hMem]
0x18006c7c0  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18006c7c6  mov     dword ptr [rsp+160h+var_130], eax
0x18006c7ca  mov     rcx, rdi
0x18006c7cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(void)
0x18006c7d2  mov     ebx, dword ptr [rsp+160h+var_130]
0x18006c7d6  test    al, al
0x18006c7d8  jz      short loc_18006C7EB
0x18006c7da  cmp     ebx, 82AA0008h
0x18006c7e0  jnz     short loc_18006C7EB
0x18006c7e2  mov     ebx, 80070490h
0x18006c7e7  mov     dword ptr [rsp+160h+var_130], ebx
0x18006c7eb  test    ebx, ebx
0x18006c7ed  jns     short loc_18006C831
0x18006c7ef  mov     rcx, [rbp+68h]; this
0x18006c7f3  mov     r9d, ebx; char *
0x18006c7f6  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006c7fd  mov     edx, 58C2h; void *
0x18006c802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c807  nop
0x18006c808  lea     rcx, [rsp+160h+var_128]
0x18006c80d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c812  nop
0x18006c813  lea     rcx, [rsp+160h+var_F0]; this
0x18006c818  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006c81d  nop
0x18006c81e  mov     [rbp+60h+var_A8], r13b
0x18006c822  lea     rcx, [rbp+60h+var_C8]
0x18006c826  call    _lambda_5f4611dcbc0b3efea0751769cca0839c___operator__
0x18006c82b  nop
0x18006c82c  jmp     loc_18006CC1B
0x18006c831  mov     rcx, [rsp+160h+bstrString]; bstrString
0x18006c836  call    cs:__imp_SysFreeString
0x18006c83c  mov     rcx, [rsp+160h+hMem]; psz
0x18006c841  call    cs:__imp_SysAllocString
0x18006c847  mov     [rsp+160h+bstrString], rax
0x18006c84c  mov     rcx, [rsp+160h+hMem]; hMem
0x18006c851  call    cs:__imp_LocalFree
0x18006c857  mov     [rsp+160h+hMem], r13
0x18006c85c  cmp     [rsp+160h+bstrString], r13
0x18006c861  jnz     short loc_18006C8AA
0x18006c863  mov     rcx, [rbp+68h]; this
0x18006c867  mov     ebx, 8007000Eh
0x18006c86c  mov     r9d, ebx; char *
0x18006c86f  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006c876  mov     edx, 58CCh; void *
0x18006c87b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c880  nop
0x18006c881  lea     rcx, [rsp+160h+var_128]
0x18006c886  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006c88b  nop
0x18006c88c  lea     rcx, [rsp+160h+var_F0]; this
0x18006c891  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18006c896  nop
0x18006c897  mov     [rbp+60h+var_A8], r13b
0x18006c89b  lea     rcx, [rbp+60h+var_C8]
0x18006c89f  call    _lambda_5f4611dcbc0b3efea0751769cca0839c___operator__
0x18006c8a4  nop
  ... truncated ...
```
