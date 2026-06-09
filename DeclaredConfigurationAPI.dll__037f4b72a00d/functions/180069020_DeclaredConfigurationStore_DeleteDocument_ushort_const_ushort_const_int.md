# DeclaredConfigurationStore_DeleteDocument(ushort const *,ushort const *,int)

- ea: `0x180069020`
- end: `0x1800699c7`
- name: `?DeclaredConfigurationStore_DeleteDocument@@YAJPEBG0H@Z`
- size: `2471`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180019d38`
- `0x18001cce4`
- `0x18001ce5c`
- `0x18001cfa4`
- `0x18001d0b0`
- `0x18001df44`
- `0x18001e090`
- `0x18004b7f4`
- `0x18004b870`
- `0x18004d1ac`
- `0x1800556cc`
- `0x180058b08`
- `0x1800591d8`
- `0x18005a2e4`
- `0x180063350`
- `0x180069020`
- `0x1800725e0`
- `0x180086554`
- `0x1800a01ec`
- `0x1800a0228`
- `0x1800a0264`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180069504`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180069504`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800695d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800695d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006907c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006907c`
- `RPCRT4!UuidFromStringW` at `0x180069139`
- `RPCRT4!UuidFromStringW` at `0x180069139`
- `OLEAUT32!__imp_SysAllocString` at `0x1800691dd`
- `OLEAUT32!__imp_SysAllocString` at `0x180069233`
- `OLEAUT32!__imp_SysAllocString` at `0x1800695c5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800691dd`
- `OLEAUT32!__imp_SysAllocString` at `0x180069233`
- `OLEAUT32!__imp_SysAllocString` at `0x1800695c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695ba`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x1800690bb`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x1800690bb`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180069527`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180069527`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18006948d`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18006948d`
- `dmEnrollEngine!GetEnrollmentType` at `0x18006918b`
- `dmEnrollEngine!GetEnrollmentType` at `0x18006918b`

## string_xrefs

- `0x1800690ce`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180069105`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006914c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800691b4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800691f4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006924a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800694a4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180069561`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800695f3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006969d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180069736`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006979c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180069890`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800698f6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180069995`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DeclaredConfigurationStore_DeleteDocument(unsigned __int16 *a1, unsigned __int16 *a2, int a3)
{
  int IsSystemOrAdmin; // eax
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  int EnrollmentType; // eax
  BSTR v7; // rax
  OLECHAR *v8; // rax
  _QWORD *v9; // rax
  int v10; // ebx
  int v11; // edi
  int v12; // ebx
  unsigned __int16 *v13; // rcx
  unsigned __int16 v14; // ax
  RPC_WSTR v15; // rcx
  unsigned __int16 v16; // ax
  int v17; // ebx
  unsigned __int16 *v18; // rbx
  char **v19; // rcx
  __int64 v20; // r8
  int CurrentUserSid; // eax
  char IsEnabled; // al
  int v23; // eax
  int v24; // eax
  char v25; // al
  __int64 v26; // r9
  int v27; // eax
  int v29; // eax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  char *v32; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v35; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v37; // [rsp+60h] [rbp-A0h]
  BSTR v38; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h]
  int v40; // [rsp+80h] [rbp-80h]
  int v41; // [rsp+84h] [rbp-7Ch]
  int v42; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+8Ch] [rbp-74h] BYREF
  RPC_WSTR StringUuid; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v45[5]; // [rsp+98h] [rbp-68h] BYREF
  char v46; // [rsp+C0h] [rbp-40h]
  _QWORD v47[5]; // [rsp+C8h] [rbp-38h] BYREF
  char v48; // [rsp+F0h] [rbp-10h]
  ULONGLONG TickCount64; // [rsp+F8h] [rbp-8h] BYREF
  __int64 *v50; // [rsp+100h] [rbp+0h] BYREF
  HKEY v51; // [rsp+108h] [rbp+8h] BYREF
  char v52; // [rsp+110h] [rbp+10h]
  UUID Uuid; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  int v55; // [rsp+170h] [rbp+70h] BYREF

  v55 = a3;
  StringUuid = a1;
  v35 = a2;
  LODWORD(v32) = 0;
  if ( !a1 || !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x593F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x80070057LL,
      v30);
    return v4;
  }
  TickCount64 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
    TickCount64 = GetTickCount64();
  v45[0] = &TickCount64;
  v45[1] = &StringUuid;
  v45[2] = &v35;
  v45[3] = &v55;
  v45[4] = &v32;
  v46 = 1;
  v43 = 0;
  IsSystemOrAdmin = DmIsSystemOrAdmin(&v43);
  v4 = IsSystemOrAdmin;
  if ( IsSystemOrAdmin < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5956,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)IsSystemOrAdmin,
      v30);
    v46 = 0;
    lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
    return v4;
  }
  if ( v43 != 1 )
  {
    v4 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5957,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x80070005LL,
      v30);
    v46 = 0;
    lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
    return v4;
  }
  Uuid = 0;
  v5 = UuidFromStringW(StringUuid, &Uuid);
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x595A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v5,
      v30);
    v46 = 0;
    lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
    return v4;
  }
  v42 = 63;
  *(UUID *)hMem = Uuid;
  EnrollmentType = GetEnrollmentType(hMem, &v42);
  v4 = EnrollmentType;
  LODWORD(v32) = EnrollmentType;
  if ( EnrollmentType == -2147024894 )
  {
    v4 = -2102525946;
    LODWORD(v32) = -2102525946;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5962,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)v4,
      v30);
    v46 = 0;
    lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
    return v4;
  }
  if ( EnrollmentType < 0 )
    goto LABEL_14;
  v7 = SysAllocString(StringUuid);
  if ( v7 )
  {
    bstrString = 0;
    v40 = 0;
    v38 = v7;
    v41 = v42;
    v8 = SysAllocString(L"Device");
    if ( v8 )
    {
      bstrString = v8;
      v40 = 0;
      v33 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
      {
        v9 = tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(hMem);
        wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(
          &v33,
          v9);
        wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(hMem);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                 &v33,
                                 hMem)
                  + 272LL) = 5;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
        v10 = v55;
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                 &v33,
                                 hMem)
                  + 280LL) = v10;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
        v11 = -2128831035;
        v12 = -2128831035;
        v13 = v35;
        if ( v35 )
        {
          while ( 1 )
          {
            v14 = *v13;
            if ( !*v13 )
              break;
            ++v13;
            v12 = 16777619 * (v14 ^ v12);
          }
        }
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                 &v33,
                                 hMem)
                  + 284LL) = v12;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
        v15 = StringUuid;
        if ( StringUuid )
        {
          while ( 1 )
          {
            v16 = *v15;
            if ( !*v15 )
              break;
            ++v15;
            v11 = 16777619 * (v16 ^ v11);
          }
        }
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                 &v33,
                                 hMem)
                  + 288LL) = v11;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
        v17 = v42;
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                 &v33,
                                 hMem)
                  + 292LL) = v17;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
        {
          v18 = v35;
          v19 = (char **)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                       &v33,
                                       hMem)
                        + 304LL);
          v20 = -1;
          do
            ++v20;
          while ( v18[v20] );
          std::wstring::_Assign<unsigned short>(v19, v18, (char *)v20);
          tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(hMem);
        }
      }
      v47[0] = &v33;
      v47[1] = &v32;
      v47[2] = &StringUuid;
      v47[3] = &v35;
      v47[4] = &v55;
      v48 = 1;
      v34 = 0;
      hMem[0] = &v34;
      hMem[1] = 0;
      v37 = 1;
      LODWORD(v32) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                       (struct DeclaredConfigurationScopeData *)&v38,
                       v35,
                       (HKEY *)&hMem[1],
                       0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(hMem);
      if ( (int)v32 < 0 )
      {
        hMem[0] = 0;
        CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)hMem);
        v4 = CurrentUserSid;
        LODWORD(v32) = CurrentUserSid;
        if ( CurrentUserSid < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59B9,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)CurrentUserSid,
            v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
          v48 = 0;
          lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
          v46 = 0;
          lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
          return v4;
        }
        if ( !(unsigned int)_o__wcsicmp(L"S-1-5-18", hMem[0]) )
        {
          LocalFree(hMem[0]);
          hMem[0] = 0;
          LODWORD(v32) = DmGetActiveUserSid((unsigned __int16 **)hMem);
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigSupportUserless>::GetImpl'::`2'::impl);
          v4 = (unsigned int)v32;
          if ( IsEnabled && (_DWORD)v32 == -2102788088 )
          {
            v4 = -2147023728;
            LODWORD(v32) = -2147023728;
          }
          if ( (v4 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x59C8,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)v4,
              v30);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
            v48 = 0;
            lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
            wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
            v46 = 0;
            lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
            return v4;
          }
        }
        SysFreeString(bstrString);
        bstrString = SysAllocString((const OLECHAR *)hMem[0]);
        LocalFree(hMem[0]);
        hMem[0] = 0;
        if ( !bstrString )
        {
          v4 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59D2,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8007000ELL,
            v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
          v48 = 0;
          lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
          v46 = 0;
          lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
          return v4;
        }
        v40 = 1;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v34,
          0);
        v50 = &v34;
        v51 = 0;
        v52 = 1;
        LODWORD(v32) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                         (struct DeclaredConfigurationScopeData *)&v38,
                         v35,
                         &v51,
                         0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v50);
        v4 = (unsigned int)v32;
        if ( (int)v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59DE,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v32,
            v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
          v48 = 0;
          lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
          v46 = 0;
          lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
          return v4;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v34,
        0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
      {
        v23 = DeclaredConfigurationStore_AsyncDeleteEnrollmentIdSidStateDocId_Internal(
                (struct DeclaredConfigurationScopeData *)&v38,
                v35,
                (__int64)&v33);
        v4 = v23;
        LODWORD(v32) = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59E5,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v23,
            v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
          v48 = 0;
          lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
          v46 = 0;
          lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
          return v4;
        }
      }
      else
      {
        v24 = DeclaredConfigurationStore_AsyncDeleteEnrollmentIdSidStateDocId_Internal(
                (struct DeclaredConfigurationScopeData *)&v38,
                v35,
                (__int64)&v33);
        v4 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59E9,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v24,
            v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
          v48 = 0;
          lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
          v46 = 0;
          lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
          return v4;
        }
      }
      if ( v55 > 0 )
      {
        v25 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl);
        LOBYTE(v26) = 1;
        v31 = v55;
        if ( v25 )
        {
          v27 = DeclaredConfigurationStore_WaitForRequestsToCompleteGivenEnrollmentIdDocIdVersion(
                  StringUuid,
                  v35,
                  0,
                  v26);
          v4 = v27;
          LODWORD(v32) = v27;
          if ( v27 != -2147024894 && v27 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x59FB,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)(unsigned int)v27,
              v31);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
            v48 = 0;
            lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
            wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
            v46 = 0;
            lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
            return v4;
          }
        }
        else
        {
          v29 = DeclaredConfigurationStore_WaitForRequestsToCompleteGivenEnrollmentIdDocIdVersion(
                  StringUuid,
                  v35,
                  0,
                  v26);
          v4 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5A05,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)(unsigned int)v29,
              v31);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
            v48 = 0;
            lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
            wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
            v46 = 0;
            lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
            return v4;
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      v48 = 0;
      lambda_0679990b76f8bdbc56c59f135c9533ad_::operator()(v47);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v33);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
      v46 = 0;
      lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
      return 0;
    }
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x596B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      v30);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v38);
    v46 = 0;
    lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
  }
  else
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5965,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      v30);
    v46 = 0;
    lambda_e731de9e6b76c838594bc0af8ff7f0ad_::operator()(v45);
  }
  return v4;
}

```

## disassembly

```asm
0x180069020  mov     [rsp-8+arg_18], rbx
0x180069025  mov     [rsp-8+arg_10], r8d
0x18006902a  push    rbp
0x18006902b  push    rsi
0x18006902c  push    rdi
0x18006902d  lea     rbp, [rsp-40h]
0x180069032  sub     rsp, 140h
0x180069039  mov     rax, cs:__security_cookie
0x180069040  xor     rax, rsp
0x180069043  mov     [rbp+50h+var_20], rax
0x180069047  mov     [rbp+50h+StringUuid], rcx
0x18006904b  mov     [rsp+150h+var_108], rdx
0x180069050  xor     esi, esi
0x180069052  mov     dword ptr [rsp+150h+var_120], esi
0x180069056  test    rcx, rcx
0x180069059  jz      loc_180069989
0x18006905f  test    rdx, rdx
0x180069062  jz      loc_180069989
0x180069068  mov     [rbp+50h+var_58], rsi
0x18006906c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x180069073  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x180069078  test    al, al
0x18006907a  jz      short loc_180069086
0x18006907c  call    cs:__imp_GetTickCount64
0x180069082  mov     [rbp+50h+var_58], rax
0x180069086  lea     rax, [rbp+50h+var_58]
0x18006908a  mov     [rbp+50h+var_B8], rax
0x18006908e  lea     rax, [rbp+50h+StringUuid]
0x180069092  mov     [rbp+50h+var_B0], rax
0x180069096  lea     rax, [rsp+150h+var_108]
0x18006909b  mov     [rbp+50h+var_A8], rax
0x18006909f  lea     rax, [rbp+50h+arg_10]
0x1800690a3  mov     [rbp+50h+var_A0], rax
0x1800690a7  lea     rax, [rsp+150h+var_120]
0x1800690ac  mov     [rbp+50h+var_98], rax
0x1800690b0  mov     [rbp+50h+var_90], 1
0x1800690b4  mov     [rbp+50h+var_C4], esi
0x1800690b7  lea     rcx, [rbp+50h+var_C4]
0x1800690bb  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x1800690c1  mov     ebx, eax
0x1800690c3  test    eax, eax
0x1800690c5  jns     short loc_1800690F3
0x1800690c7  mov     rcx, [rbp+58h]; this
0x1800690cb  mov     r9d, eax; char *
0x1800690ce  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800690d5  mov     edx, 5956h; void *
0x1800690da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800690df  nop
0x1800690e0  mov     [rbp+50h+var_90], sil
0x1800690e4  lea     rcx, [rbp+50h+var_B8]
0x1800690e8  call    _lambda_e731de9e6b76c838594bc0af8ff7f0ad___operator__
0x1800690ed  nop
0x1800690ee  jmp     loc_1800699A6
0x1800690f3  cmp     [rbp+50h+var_C4], 1
0x1800690f7  jz      short loc_18006912A
0x1800690f9  mov     rcx, [rbp+58h]; this
0x1800690fd  mov     ebx, 80070005h
0x180069102  mov     r9d, ebx; char *
0x180069105  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006910c  mov     edx, 5957h; void *
0x180069111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069116  nop
0x180069117  mov     [rbp+50h+var_90], sil
0x18006911b  lea     rcx, [rbp+50h+var_B8]
0x18006911f  call    _lambda_e731de9e6b76c838594bc0af8ff7f0ad___operator__
0x180069124  nop
0x180069125  jmp     loc_1800699A6
0x18006912a  xorps   xmm0, xmm0
0x18006912d  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x180069131  lea     rdx, [rbp+50h+Uuid]; Uuid
0x180069135  mov     rcx, [rbp+50h+StringUuid]; StringUuid
0x180069139  call    cs:__imp_UuidFromStringW
0x18006913f  mov     ebx, eax
0x180069141  test    eax, eax
0x180069143  jns     short loc_180069171
0x180069145  mov     rcx, [rbp+58h]; this
0x180069149  mov     r9d, eax; char *
0x18006914c  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180069153  mov     edx, 595Ah; void *
0x180069158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006915d  nop
0x18006915e  mov     [rbp+50h+var_90], sil
0x180069162  lea     rcx, [rbp+50h+var_B8]
0x180069166  call    _lambda_e731de9e6b76c838594bc0af8ff7f0ad___operator__
0x18006916b  nop
0x18006916c  jmp     loc_1800699A6
0x180069171  mov     [rbp+50h+var_C8], 3Fh ; '?'
0x180069178  movaps  xmm0, xmmword ptr [rbp+50h+Uuid.Data1]
0x18006917c  movdqa  xmmword ptr [rsp+150h+hMem], xmm0
0x180069182  lea     rdx, [rbp+50h+var_C8]
0x180069186  lea     rcx, [rsp+150h+hMem]
0x18006918b  call    cs:__imp_GetEnrollmentType
0x180069191  mov     ebx, eax
0x180069193  mov     dword ptr [rsp+150h+var_120], eax
0x180069197  cmp     eax, 80070002h
0x18006919c  jnz     short loc_1800691A9
0x18006919e  mov     ebx, 82AE0006h
0x1800691a3  mov     dword ptr [rsp+150h+var_120], ebx
0x1800691a7  jmp     short loc_1800691AD
0x1800691a9  test    eax, eax
0x1800691ab  jns     short loc_1800691D9
0x1800691ad  mov     rcx, [rbp+58h]; this
0x1800691b1  mov     r9d, ebx; char *
0x1800691b4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800691bb  mov     edx, 5962h; void *
0x1800691c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800691c5  nop
0x1800691c6  mov     [rbp+50h+var_90], sil
0x1800691ca  lea     rcx, [rbp+50h+var_B8]
0x1800691ce  call    _lambda_e731de9e6b76c838594bc0af8ff7f0ad___operator__
0x1800691d3  nop
0x1800691d4  jmp     loc_1800699A6
0x1800691d9  mov     rcx, [rbp+50h+StringUuid]; psz
0x1800691dd  call    cs:__imp_SysAllocString
0x1800691e3  test    rax, rax
0x1800691e6  jnz     short loc_180069219
0x1800691e8  mov     rcx, [rbp+58h]; this
0x1800691ec  mov     ebx, 8007000Eh
0x1800691f1  mov     r9d, ebx; char *
0x1800691f4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800691fb  mov     edx, 5965h; void *
0x180069200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069205  nop
0x180069206  mov     [rbp+50h+var_90], sil
0x18006920a  lea     rcx, [rbp+50h+var_B8]
0x18006920e  call    _lambda_e731de9e6b76c838594bc0af8ff7f0ad___operator__
0x180069213  nop
0x180069214  jmp     loc_1800699A6
0x180069219  mov     [rsp+150h+bstrString], rsi
0x18006921e  mov     [rbp+50h+var_D0], esi
0x180069221  mov     [rsp+150h+var_E0], rax
0x180069226  mov     eax, [rbp+50h+var_C8]
0x180069229  mov     [rbp+50h+var_CC], eax
0x18006922c  lea     rcx, aDevice_2; "Device"
0x180069233  call    cs:__imp_SysAllocString
0x180069239  test    rax, rax
0x18006923c  jnz     short loc_18006927A
0x18006923e  mov     rcx, [rbp+58h]; this
0x180069242  mov     ebx, 8007000Eh
0x180069247  mov     r9d, ebx; char *
0x18006924a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180069251  mov     edx, 596Bh; void *
0x180069256  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006925b  nop
0x18006925c  lea     rcx, [rsp+150h+var_E0]; this
0x180069261  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180069266  nop
0x180069267  mov     [rbp+50h+var_90], sil
0x18006926b  lea     rcx, [rbp+50h+var_B8]
0x18006926f  call    _lambda_e731de9e6b76c838594bc0af8ff7f0ad___operator__
0x180069274  nop
0x180069275  jmp     loc_1800699A6
0x18006927a  mov     [rsp+150h+bstrString], rax
0x18006927f  mov     [rbp+50h+var_D0], esi
0x180069282  mov     [rsp+150h+var_118], rsi
0x180069287  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl(void)'::`2'::impl
0x18006928e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(void)
0x180069293  test    al, al
0x180069295  jz      loc_18006940C
0x18006929b  lea     rcx, [rsp+150h+hMem]
0x1800692a0  call    ??$start@V?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(void)
0x1800692a5  mov     rdx, rax
0x1800692a8  lea     rcx, [rsp+150h+var_118]
0x1800692ad  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy> &&)
0x1800692b2  lea     rcx, [rsp+150h+hMem]
0x1800692b7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x1800692bc  lea     rdx, [rsp+150h+hMem]
0x1800692c1  lea     rcx, [rsp+150h+var_118]
0x1800692c6  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x1800692cb  mov     rcx, [rax]
0x1800692ce  mov     dword ptr [rcx+110h], 5
0x1800692d8  lea     rcx, [rsp+150h+hMem]
0x1800692dd  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x1800692e2  mov     ebx, [rbp+50h+arg_10]
0x1800692e5  lea     rdx, [rsp+150h+hMem]
0x1800692ea  lea     rcx, [rsp+150h+var_118]
0x1800692ef  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x1800692f4  mov     rcx, [rax]
0x1800692f7  mov     [rcx+118h], ebx
0x1800692fd  lea     rcx, [rsp+150h+hMem]
0x180069302  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180069307  mov     edi, 811C9DC5h
0x18006930c  mov     ebx, edi
0x18006930e  mov     rcx, [rsp+150h+var_108]
0x180069313  test    rcx, rcx
0x180069316  jz      short loc_180069331
0x180069318  jmp     short loc_180069329
0x18006931a  movzx   eax, ax
0x18006931d  lea     rcx, [rcx+2]
0x180069321  xor     ebx, eax
0x180069323  imul    ebx, 1000193h
0x180069329  movzx   eax, word ptr [rcx]
0x18006932c  test    ax, ax
0x18006932f  jnz     short loc_18006931A
0x180069331  lea     rdx, [rsp+150h+hMem]
0x180069336  lea     rcx, [rsp+150h+var_118]
0x18006933b  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x180069340  mov     rcx, [rax]
0x180069343  mov     [rcx+11Ch], ebx
0x180069349  lea     rcx, [rsp+150h+hMem]
0x18006934e  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180069353  mov     rcx, [rbp+50h+StringUuid]
0x180069357  test    rcx, rcx
0x18006935a  jz      short loc_180069375
0x18006935c  jmp     short loc_18006936D
0x18006935e  movzx   eax, ax
0x180069361  lea     rcx, [rcx+2]
0x180069365  xor     edi, eax
0x180069367  imul    edi, 1000193h
0x18006936d  movzx   eax, word ptr [rcx]
0x180069370  test    ax, ax
0x180069373  jnz     short loc_18006935E
0x180069375  lea     rdx, [rsp+150h+hMem]
0x18006937a  lea     rcx, [rsp+150h+var_118]
0x18006937f  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x180069384  mov     rcx, [rax]
0x180069387  mov     [rcx+120h], edi
0x18006938d  lea     rcx, [rsp+150h+hMem]
0x180069392  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180069397  mov     ebx, [rbp+50h+var_C8]
0x18006939a  lea     rdx, [rsp+150h+hMem]
0x18006939f  lea     rcx, [rsp+150h+var_118]
0x1800693a4  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x1800693a9  mov     rcx, [rax]
0x1800693ac  mov     [rcx+124h], ebx
0x1800693b2  lea     rcx, [rsp+150h+hMem]
0x1800693b7  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x1800693bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl(void)'::`2'::impl
0x1800693c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(void)
0x1800693c8  test    al, al
0x1800693ca  jz      short loc_18006940C
0x1800693cc  mov     rbx, [rsp+150h+var_108]
0x1800693d1  lea     rdx, [rsp+150h+hMem]
0x1800693d6  lea     rcx, [rsp+150h+var_118]
0x1800693db  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x1800693e0  nop
0x1800693e1  mov     rcx, [rax]
0x1800693e4  add     rcx, 130h
0x1800693eb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800693ef  inc     r8
0x1800693f2  cmp     [rbx+r8*2], si
0x1800693f7  jnz     short loc_1800693EF
0x1800693f9  mov     rdx, rbx
0x1800693fc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180069401  nop
0x180069402  lea     rcx, [rsp+150h+hMem]
0x180069407  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18006940c  lea     rax, [rsp+150h+var_118]
0x180069411  mov     [rbp+50h+var_88], rax
0x180069415  lea     rax, [rsp+150h+var_120]
0x18006941a  mov     [rbp+50h+var_80], rax
0x18006941e  lea     rax, [rbp+50h+StringUuid]
0x180069422  mov     [rbp+50h+var_78], rax
0x180069426  lea     rax, [rsp+150h+var_108]
0x18006942b  mov     [rbp+50h+var_70], rax
0x18006942f  lea     rax, [rbp+50h+arg_10]
0x180069433  mov     [rbp+50h+var_68], rax
0x180069437  mov     [rbp+50h+var_60], 1
0x18006943b  mov     [rsp+150h+var_110], rsi
0x180069440  lea     rax, [rsp+150h+var_110]
0x180069445  mov     [rsp+150h+hMem], rax
0x18006944a  mov     [rsp+150h+hMem+8], rsi
0x18006944f  mov     [rsp+150h+var_F0], 1
0x180069454  xor     r9d, r9d; int
0x180069457  lea     r8, [rsp+150h+hMem+8]; HKEY *
0x18006945c  mov     rdx, [rsp+150h+var_108]; unsigned __int16 *
0x180069461  lea     rcx, [rsp+150h+var_E0]; struct DeclaredConfigurationScopeData *
0x180069466  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18006946b  mov     dword ptr [rsp+150h+var_120], eax
0x18006946f  lea     rcx, [rsp+150h+hMem]
0x180069474  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180069479  cmp     dword ptr [rsp+150h+var_120], esi
0x18006947d  jge     loc_1800696F1
0x180069483  mov     [rsp+150h+hMem], rsi
0x180069488  lea     rcx, [rsp+150h+hMem]
0x18006948d  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180069493  mov     ebx, eax
0x180069495  mov     dword ptr [rsp+150h+var_120], eax
0x180069499  test    eax, eax
0x18006949b  jns     short loc_1800694F8
0x18006949d  mov     rcx, [rbp+58h]; this
0x1800694a1  mov     r9d, eax; char *
0x1800694a4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800694ab  mov     edx, 59B9h; void *
0x1800694b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800694b5  nop
0x1800694b6  lea     rcx, [rsp+150h+var_110]
0x1800694bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800694c0  nop
0x1800694c1  mov     [rbp+50h+var_60], sil
0x1800694c5  lea     rcx, [rbp+50h+var_88]
0x1800694c9  call    _lambda_0679990b76f8bdbc56c59f135c9533ad___operator__
0x1800694ce  nop
0x1800694cf  lea     rcx, [rsp+150h+var_118]
0x1800694d4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x1800694d9  nop
0x1800694da  lea     rcx, [rsp+150h+var_E0]; this
0x1800694df  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1800694e4  nop
0x1800694e5  mov     [rbp+50h+var_90], sil
  ... truncated ...
```
