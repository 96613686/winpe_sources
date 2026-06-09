# DeclaredConfigurationStore_SetConfigurationDocument(ushort const *,ushort const *,int,bool,ushort const *)

- ea: `0x180084570`
- end: `0x180084fd9`
- name: `?DeclaredConfigurationStore_SetConfigurationDocument@@YAJPEBG0H_N0@Z`
- size: `2665`
- prototype: `__int64 __fastcall(OLECHAR *, const unsigned __int16 *, int, char, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x18001c32c`
- `0x18001cce4`
- `0x18001ce80`
- `0x18001cfa4`
- `0x18001d03c`
- `0x18001d37c`
- `0x18001def8`
- `0x18001df44`
- `0x18001e090`
- `0x180025710`
- `0x18004b7f4`
- `0x18004b870`
- `0x1800556cc`
- `0x180058954`
- `0x180058b08`
- `0x180059310`
- `0x1800595dc`
- `0x18005a78c`
- `0x180067160`
- `0x1800726a4`
- `0x180084570`
- `0x180086554`
- `0x18009a348`
- `0x1800a0228`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800849fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084a7a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800849fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084a89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084b11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084a89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084b11`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180084d4b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180084d4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180084724`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180084724`
- `RPCRT4!UuidFromStringW` at `0x1800845fa`
- `RPCRT4!UuidFromStringW` at `0x1800845fa`
- `OLEAUT32!__imp_SysAllocString` at `0x180084694`
- `OLEAUT32!__imp_SysAllocString` at `0x1800846cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180084b01`
- `OLEAUT32!__imp_SysAllocString` at `0x180084694`
- `OLEAUT32!__imp_SysAllocString` at `0x1800846cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180084b01`
- `OLEAUT32!__imp_SysFreeString` at `0x180084af6`
- `OLEAUT32!__imp_SysFreeString` at `0x180084af6`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x18008465d`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x18008465d`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180084a99`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180084a99`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180084a16`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180084a16`
- `dmEnrollEngine!GetEnrollmentType` at `0x180084627`
- `dmEnrollEngine!GetEnrollmentType` at `0x180084627`

## string_xrefs

- `0x180084eb1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\DCMutex.h`
- `0x1800845d2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800846e6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18008497b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084a30`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084ab3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084b3f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084c8c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084d6d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084e0e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084ecc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180084f2c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DeclaredConfigurationStore_SetConfigurationDocument(
        OLECHAR *a1,
        const unsigned __int16 *a2,
        int a3,
        char a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v6; // rsi
  __int64 v7; // rdx
  RPC_STATUS IsSystemOrAdmin; // ebx
  int EnrollmentType; // eax
  BSTR v10; // rax
  OLECHAR *v11; // rax
  __int64 v12; // rax
  int v13; // ebx
  BOOL v14; // ebx
  int v15; // ebx
  OLECHAR *v16; // rcx
  OLECHAR v17; // ax
  int v18; // ebx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rdx
  int CurrentUserSid; // eax
  int ActiveUserSid; // eax
  int v24; // eax
  const unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // rdx
  signed int FilePathForOriginalDocStorage; // ebx
  _QWORD *v28; // r8
  unsigned __int16 **v29; // rdx
  int v30; // eax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  char *v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v41; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h]
  int v43; // [rsp+68h] [rbp-98h]
  int v44; // [rsp+6Ch] [rbp-94h]
  int v45; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *psz; // [rsp+78h] [rbp-88h] BYREF
  UUID v47; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v48[5]; // [rsp+90h] [rbp-70h] BYREF
  char v49; // [rsp+B8h] [rbp-48h]
  _QWORD v50[7]; // [rsp+C0h] [rbp-40h] BYREF
  char v51; // [rsp+F8h] [rbp-8h]
  ULONGLONG TickCount64; // [rsp+100h] [rbp+0h] BYREF
  WCHAR WideCharStr[4]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v54; // [rsp+110h] [rbp+10h] BYREF
  char v55; // [rsp+118h] [rbp+18h]
  UUID Uuid; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v57[3]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v58; // [rsp+158h] [rbp+58h]
  _QWORD v59[8]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v60[22]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v61; // [rsp+250h] [rbp+150h]
  int v62; // [rsp+254h] [rbp+154h]
  int v63; // [rsp+258h] [rbp+158h]
  unsigned __int16 *v64[12]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v65[16]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v66; // [rsp+370h] [rbp+270h]
  int v67; // [rsp+3E4h] [rbp+2E4h]
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]
  int v69; // [rsp+490h] [rbp+390h] BYREF
  char v70; // [rsp+498h] [rbp+398h] BYREF

  v70 = a4;
  v69 = a3;
  psz = a1;
  v6 = a5;
  LODWORD(v36) = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v7 = 22306;
      goto LABEL_3;
    }
    Uuid = 0;
    IsSystemOrAdmin = UuidFromStringW(a1, &Uuid);
    if ( IsSystemOrAdmin < 0 )
    {
      v7 = 22309;
      goto LABEL_4;
    }
    v40 = 63;
    v47 = Uuid;
    EnrollmentType = GetEnrollmentType(&v47, &v40);
    IsSystemOrAdmin = EnrollmentType;
    LODWORD(v36) = EnrollmentType;
    if ( EnrollmentType == -2147024894 )
    {
      IsSystemOrAdmin = -2102525946;
      LODWORD(v36) = -2102525946;
LABEL_12:
      v7 = 22317;
      goto LABEL_4;
    }
    if ( EnrollmentType < 0 )
      goto LABEL_12;
    v45 = 0;
    IsSystemOrAdmin = DmIsSystemOrAdmin(&v45);
    if ( IsSystemOrAdmin < 0 )
    {
      v7 = 22320;
      goto LABEL_4;
    }
    if ( v45 != 1 )
    {
      IsSystemOrAdmin = -2147024891;
      v7 = 22321;
      goto LABEL_4;
    }
    v10 = SysAllocString(psz);
    if ( !v10 )
    {
      IsSystemOrAdmin = -2147024882;
      v7 = 22324;
      goto LABEL_4;
    }
    bstrString = 0;
    v43 = 0;
    v41 = v10;
    v44 = v40;
    v11 = SysAllocString(L"Device");
    if ( !v11 )
    {
      IsSystemOrAdmin = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x573A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        v32);
LABEL_90:
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v41);
      return (unsigned int)IsSystemOrAdmin;
    }
    bstrString = v11;
    v43 = 0;
    DCDocument::DCDocument((DCDocument *)v57);
    TickCount64 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
      TickCount64 = GetTickCount64();
    v50[0] = &TickCount64;
    v50[1] = &psz;
    v50[2] = v57;
    v50[3] = &v70;
    v50[4] = &v69;
    v50[5] = &v36;
    v50[6] = &v41;
    v51 = 1;
    v37 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
    {
      v12 = tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(&lpFileName);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(
        &v37,
        v12);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&lpFileName);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                               &v37,
                               &lpFileName)
                + 272LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
      v13 = v69;
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                               &v37,
                               &lpFileName)
                + 280LL) = v13;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
      v14 = v70 != 0;
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                               &v37,
                               &lpFileName)
                + 276LL) = v14;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
      v15 = -2128831035;
      v16 = psz;
      if ( psz )
      {
        while ( 1 )
        {
          v17 = *v16;
          if ( !*v16 )
            break;
          ++v16;
          v15 = 16777619 * (v15 ^ v17);
        }
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                               &v37,
                               &lpFileName)
                + 288LL) = v15;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
      v18 = v40;
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                               &v37,
                               &lpFileName)
                + 292LL) = v18;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
    }
    v48[0] = &v37;
    v48[1] = &v36;
    v48[2] = v57;
    v48[3] = &psz;
    v48[4] = &v69;
    v49 = 1;
    LODWORD(v36) = DeclaredConfigurationStore_ParseDeclaredConfigurationJson(
                     0,
                     (struct DeclaredConfigurationScopeData *)&v41,
                     a2,
                     (struct DCDocument *)v57,
                     v6);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
    {
      if ( v60[2] )
      {
        v19 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                          &v37,
                          &lpFileName);
        std::wstring::operator=(*v19 + 368LL, v60);
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
      }
      if ( v66 )
      {
        v20 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                          &v37,
                          &lpFileName);
        std::wstring::operator=(*v20 + 336LL, v65);
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(&lpFileName);
      }
    }
    IsSystemOrAdmin = (int)v36;
    if ( (int)v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57C0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v36,
        v33);
      v49 = 0;
      lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
      v51 = 0;
      lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
LABEL_89:
      DCDocument::~DCDocument((DCDocument *)v57);
      goto LABEL_90;
    }
    if ( v61 == 1 )
    {
      v63 = 1;
    }
    else
    {
      if ( v61 != 4 )
      {
        IsSystemOrAdmin = -2147024809;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
        {
          LODWORD(v36) = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57D0,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x80070057LL,
            v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57D4,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x80070057LL,
            v33);
        }
        goto LABEL_51;
      }
      v63 = 20;
      v67 |= 0x10u;
    }
    v21 = v59;
    if ( v59[3] > 7u )
      v21 = (_QWORD *)v59[0];
    if ( !(unsigned int)_o__wcsicmp(L"user", v21) )
    {
      hMem = 0;
      CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
      IsSystemOrAdmin = CurrentUserSid;
      LODWORD(v36) = CurrentUserSid;
      if ( CurrentUserSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57E3,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)CurrentUserSid,
          v33);
        v49 = 0;
        lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
        wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
        v51 = 0;
        lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
        goto LABEL_89;
      }
      if ( !(unsigned int)_o__wcsicmp(L"S-1-5-18", hMem) )
      {
        LocalFree(hMem);
        hMem = 0;
        ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
        IsSystemOrAdmin = ActiveUserSid;
        LODWORD(v36) = ActiveUserSid;
        if ( ActiveUserSid < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57EB,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)ActiveUserSid,
            v33);
          v49 = 0;
          lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
          v51 = 0;
          lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
          goto LABEL_89;
        }
      }
      SysFreeString(bstrString);
      bstrString = SysAllocString((const OLECHAR *)hMem);
      LocalFree(hMem);
      hMem = 0;
      if ( !bstrString )
      {
        IsSystemOrAdmin = -2147024882;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
        {
          LODWORD(v36) = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57F8,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8007000ELL,
            v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57FC,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8007000ELL,
            v33);
        }
LABEL_51:
        v49 = 0;
        lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
        wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
        v51 = 0;
        lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
        goto LABEL_89;
      }
      v43 = 1;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl)
      && v62 == 2
      && v61 == 1
      && v70 )
    {
      v67 |= 0x400u;
    }
    *(_QWORD *)&v47.Data1 = 0;
    v47.Data4[0] = 0;
    v24 = v69;
    v25 = (const unsigned __int16 *)v57;
    if ( v58 > 7 )
      v25 = v57[0];
    if ( v69 )
    {
      if ( (unsigned int)v69 > 0x418937 )
      {
        IsSystemOrAdmin = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\DCMutex.h",
          (const char *)0x80070057LL,
          v33);
LABEL_85:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x580E,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)IsSystemOrAdmin,
          v34);
        DCMutex::~DCMutex((DCMutex *)&v47);
        v49 = 0;
        lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
        wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
        v51 = 0;
        lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
        goto LABEL_89;
      }
    }
    else
    {
      v24 = 300;
    }
    IsSystemOrAdmin = DCMutex::AcquireInternal((DCMutex *)&v47, psz, v25, 0, 1000 * v24);
    if ( IsSystemOrAdmin >= 0 )
    {
      std::wstring::wstring(WideCharStr, a2);
      LODWORD(v36) = SaveOriginalConfigurationDocument(
                       (struct DeclaredConfigurationScopeData *)&v41,
                       (struct DCDocument *)v57,
                       WideCharStr);
      std::wstring::_Tidy_deallocate(WideCharStr);
      IsSystemOrAdmin = (int)v36;
      if ( (int)v36 >= 0 )
      {
        IsSystemOrAdmin = DeclaredConfigurationStore_ConstructURIStorage(
                            (struct DeclaredConfigurationScopeData *)&v41,
                            (struct DCDocument *)v57,
                            1);
        LODWORD(v36) = IsSystemOrAdmin;
        if ( IsSystemOrAdmin < 0 && v64[2] )
        {
          lpFileName = 0;
          *(_QWORD *)WideCharStr = &lpFileName;
          v54 = 0;
          v55 = 1;
          v26 = (const unsigned __int16 *)v64;
          if ( v64[3] > (unsigned __int16 *)7 )
            v26 = v64[0];
          FilePathForOriginalDocStorage = DeclaredConfigurationStore_GetFilePathForOriginalDocStorage(
                                            (struct DeclaredConfigurationScopeData *)&v41,
                                            v26,
                                            (struct DCDocument *)v57,
                                            &v54);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(WideCharStr);
          if ( FilePathForOriginalDocStorage >= 0 )
            DeleteFileW(lpFileName);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpFileName);
          IsSystemOrAdmin = (int)v36;
        }
        if ( IsSystemOrAdmin >= 0 )
        {
          if ( v69 <= 0 )
            goto LABEL_83;
          v28 = v60;
          if ( v60[3] > 7u )
            v28 = (_QWORD *)v60[0];
          v29 = v57;
          if ( v58 > 7 )
            v29 = (unsigned __int16 **)v57[0];
          v35 = v69;
          v30 = DeclaredConfigurationStore_WaitForRequestsToCompleteGivenEnrollmentIdDocIdVersion(v41, v29, v28, 0);
          IsSystemOrAdmin = v30;
          if ( v30 >= 0 )
          {
LABEL_83:
            DCMutex::~DCMutex((DCMutex *)&v47);
            v49 = 0;
            lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
            wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
            v51 = 0;
            lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
            DCDocument::~DCDocument((DCDocument *)v57);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v41);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x582C,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v30,
            v35);
          DCMutex::~DCMutex((DCMutex *)&v47);
          v49 = 0;
          lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
          v51 = 0;
          lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5822,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)IsSystemOrAdmin,
            v34);
          DCMutex::~DCMutex((DCMutex *)&v47);
          v49 = 0;
          lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
          v51 = 0;
          lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5812,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v36,
          v34);
        DCMutex::~DCMutex((DCMutex *)&v47);
        v49 = 0;
        lambda_20beab322fd1a2bfd14aef26fadca585_::operator()(v48);
        wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v37);
        v51 = 0;
        lambda_2a396926707aedf7c3df209a68c826ed_::operator()(v50);
      }
      goto LABEL_89;
    }
    goto LABEL_85;
  }
  v7 = 22305;
LABEL_3:
  IsSystemOrAdmin = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)(unsigned int)IsSystemOrAdmin,
    v32);
  return (unsigned int)IsSystemOrAdmin;
}

```

## disassembly

```asm
0x180084570  mov     [rsp-8+arg_18], r9b
0x180084575  mov     [rsp-8+arg_10], r8d
0x18008457a  push    rbp
0x18008457b  push    rbx
0x18008457c  push    rsi
0x18008457d  push    rdi
0x18008457e  push    r14
0x180084580  push    r15
0x180084582  lea     rbp, [rsp-348h]
0x18008458a  sub     rsp, 448h
0x180084591  mov     rax, cs:__security_cookie
0x180084598  xor     rax, rsp
0x18008459b  mov     [rbp+370h+var_40], rax
0x1800845a2  mov     rdi, rdx
0x1800845a5  mov     [rsp+470h+psz], rcx
0x1800845aa  mov     rsi, [rbp+370h+arg_20]
0x1800845b1  xor     r14d, r14d
0x1800845b4  mov     dword ptr [rsp+470h+var_440], r14d
0x1800845b9  test    rcx, rcx
0x1800845bc  jnz     short loc_1800845E3
0x1800845be  mov     edx, 5721h; void *
0x1800845c3  mov     ebx, 80070057h
0x1800845c8  mov     rcx, [rbp+378h]; this
0x1800845cf  mov     r9d, ebx; char *
0x1800845d2  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800845d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800845de  jmp     loc_180084FB8
0x1800845e3  test    rdi, rdi
0x1800845e6  jnz     short loc_1800845EF
0x1800845e8  mov     edx, 5722h
0x1800845ed  jmp     short loc_1800845C3
0x1800845ef  xorps   xmm0, xmm0
0x1800845f2  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x1800845f6  lea     rdx, [rbp+370h+Uuid]; Uuid
0x1800845fa  call    cs:__imp_UuidFromStringW
0x180084600  mov     ebx, eax
0x180084602  test    eax, eax
0x180084604  jns     short loc_18008460D
0x180084606  mov     edx, 5725h
0x18008460b  jmp     short loc_1800845C8
0x18008460d  mov     [rsp+470h+var_420], 3Fh ; '?'
0x180084615  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x180084619  movdqa  [rbp+370h+var_3F0], xmm0
0x18008461e  lea     rdx, [rsp+470h+var_420]
0x180084623  lea     rcx, [rbp+370h+var_3F0]
0x180084627  call    cs:__imp_GetEnrollmentType
0x18008462d  mov     ebx, eax
0x18008462f  mov     dword ptr [rsp+470h+var_440], eax
0x180084633  cmp     eax, 80070002h
0x180084638  jnz     short loc_180084645
0x18008463a  mov     ebx, 82AE0006h
0x18008463f  mov     dword ptr [rsp+470h+var_440], ebx
0x180084643  jmp     short loc_180084649
0x180084645  test    eax, eax
0x180084647  jns     short loc_180084653
0x180084649  mov     edx, 572Dh
0x18008464e  jmp     loc_1800845C8
0x180084653  mov     [rsp+470h+var_400], r14d
0x180084658  lea     rcx, [rsp+470h+var_400]
0x18008465d  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x180084663  mov     ebx, eax
0x180084665  test    eax, eax
0x180084667  jns     short loc_180084673
0x180084669  mov     edx, 5730h
0x18008466e  jmp     loc_1800845C8
0x180084673  mov     r15d, 1
0x180084679  cmp     [rsp+470h+var_400], r15d
0x18008467e  jz      short loc_18008468F
0x180084680  mov     ebx, 80070005h
0x180084685  mov     edx, 5731h
0x18008468a  jmp     loc_1800845C8
0x18008468f  mov     rcx, [rsp+470h+psz]; psz
0x180084694  call    cs:__imp_SysAllocString
0x18008469a  test    rax, rax
0x18008469d  jnz     short loc_1800846AE
0x18008469f  mov     ebx, 8007000Eh
0x1800846a4  mov     edx, 5734h
0x1800846a9  jmp     loc_1800845C8
0x1800846ae  mov     [rsp+470h+bstrString], r14
0x1800846b3  mov     [rsp+470h+var_408], r14d
0x1800846b8  mov     [rsp+470h+var_418], rax
0x1800846bd  mov     eax, [rsp+470h+var_420]
0x1800846c1  mov     [rsp+470h+var_404], eax
0x1800846c5  lea     rcx, aDevice_2; "Device"
0x1800846cc  call    cs:__imp_SysAllocString
0x1800846d2  test    rax, rax
0x1800846d5  jnz     short loc_1800846FC
0x1800846d7  mov     rcx, [rbp+378h]; this
0x1800846de  mov     ebx, 8007000Eh
0x1800846e3  mov     r9d, ebx; char *
0x1800846e6  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800846ed  mov     edx, 573Ah; void *
0x1800846f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800846f7  jmp     loc_180084FAE
0x1800846fc  mov     [rsp+470h+bstrString], rax
0x180084701  mov     [rsp+470h+var_408], r14d
0x180084706  lea     rcx, [rbp+370h+var_330]; this
0x18008470a  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x18008470f  nop
0x180084710  mov     [rbp+370h+var_370], r14
0x180084714  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x18008471b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x180084720  test    al, al
0x180084722  jz      short loc_18008472E
0x180084724  call    cs:__imp_GetTickCount64
0x18008472a  mov     [rbp+370h+var_370], rax
0x18008472e  lea     rax, [rbp+370h+var_370]
0x180084732  mov     [rbp+370h+var_3B0], rax
0x180084736  lea     rax, [rsp+470h+psz]
0x18008473b  mov     [rbp+370h+var_3A8], rax
0x18008473f  lea     rax, [rbp+370h+var_330]
0x180084743  mov     [rbp+370h+var_3A0], rax
0x180084747  lea     rax, [rbp+370h+arg_18]
0x18008474e  mov     [rbp+370h+var_398], rax
0x180084752  lea     rax, [rbp+370h+arg_10]
0x180084759  mov     [rbp+370h+var_390], rax
0x18008475d  lea     rax, [rsp+470h+var_440]
0x180084762  mov     [rbp+370h+var_388], rax
0x180084766  lea     rax, [rsp+470h+var_418]
0x18008476b  mov     [rbp+370h+var_380], rax
0x18008476f  mov     [rbp+370h+var_378], r15b
0x180084773  mov     [rsp+470h+var_438], r14
0x180084778  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl(void)'::`2'::impl
0x18008477f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(void)
0x180084784  test    al, al
0x180084786  jz      loc_180084897
0x18008478c  lea     rcx, [rsp+470h+lpFileName]
0x180084791  call    ??$start@V?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(void)
0x180084796  mov     rdx, rax
0x180084799  lea     rcx, [rsp+470h+var_438]
0x18008479e  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy> &&)
0x1800847a3  lea     rcx, [rsp+470h+lpFileName]
0x1800847a8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x1800847ad  lea     rdx, [rsp+470h+lpFileName]
0x1800847b2  lea     rcx, [rsp+470h+var_438]
0x1800847b7  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x1800847bc  mov     rcx, [rax]
0x1800847bf  mov     [rcx+110h], r15d
0x1800847c6  lea     rcx, [rsp+470h+lpFileName]
0x1800847cb  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x1800847d0  mov     ebx, [rbp+370h+arg_10]
0x1800847d6  lea     rdx, [rsp+470h+lpFileName]
0x1800847db  lea     rcx, [rsp+470h+var_438]
0x1800847e0  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x1800847e5  mov     rcx, [rax]
0x1800847e8  mov     [rcx+118h], ebx
0x1800847ee  lea     rcx, [rsp+470h+lpFileName]
0x1800847f3  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x1800847f8  mov     ebx, r14d
0x1800847fb  cmp     [rbp+370h+arg_18], r14b
0x180084802  setnz   bl
0x180084805  lea     rdx, [rsp+470h+lpFileName]
0x18008480a  lea     rcx, [rsp+470h+var_438]
0x18008480f  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x180084814  mov     rcx, [rax]
0x180084817  mov     [rcx+114h], ebx
0x18008481d  lea     rcx, [rsp+470h+lpFileName]
0x180084822  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180084827  mov     ebx, 811C9DC5h
0x18008482c  mov     rcx, [rsp+470h+psz]
0x180084831  test    rcx, rcx
0x180084834  jz      short loc_18008484F
0x180084836  jmp     short loc_180084847
0x180084838  movzx   eax, ax
0x18008483b  lea     rcx, [rcx+2]
0x18008483f  xor     eax, ebx
0x180084841  imul    ebx, eax, 1000193h
0x180084847  movzx   eax, word ptr [rcx]
0x18008484a  test    ax, ax
0x18008484d  jnz     short loc_180084838
0x18008484f  lea     rdx, [rsp+470h+lpFileName]
0x180084854  lea     rcx, [rsp+470h+var_438]
0x180084859  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18008485e  mov     rcx, [rax]
0x180084861  mov     [rcx+120h], ebx
0x180084867  lea     rcx, [rsp+470h+lpFileName]
0x18008486c  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180084871  mov     ebx, [rsp+470h+var_420]
0x180084875  lea     rdx, [rsp+470h+lpFileName]
0x18008487a  lea     rcx, [rsp+470h+var_438]
0x18008487f  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x180084884  mov     rcx, [rax]
0x180084887  mov     [rcx+124h], ebx
0x18008488d  lea     rcx, [rsp+470h+lpFileName]
0x180084892  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180084897  lea     rax, [rsp+470h+var_438]
0x18008489c  mov     [rbp+370h+var_3E0], rax
0x1800848a0  lea     rax, [rsp+470h+var_440]
0x1800848a5  mov     [rbp+370h+var_3D8], rax
0x1800848a9  lea     rax, [rbp+370h+var_330]
0x1800848ad  mov     [rbp+370h+var_3D0], rax
0x1800848b1  lea     rax, [rsp+470h+psz]
0x1800848b6  mov     [rbp+370h+var_3C8], rax
0x1800848ba  lea     rax, [rbp+370h+arg_10]
0x1800848c1  mov     [rbp+370h+var_3C0], rax
0x1800848c5  mov     [rbp+370h+var_3B8], r15b
0x1800848c9  mov     [rsp+470h+var_450], rsi; int
0x1800848ce  lea     r9, [rbp+370h+var_330]; struct DCDocument *
0x1800848d2  mov     r8, rdi; unsigned __int16 *
0x1800848d5  lea     rdx, [rsp+470h+var_418]; struct DeclaredConfigurationScopeData *
0x1800848da  xor     ecx, ecx; unsigned __int16 *
0x1800848dc  call    ?DeclaredConfigurationStore_ParseDeclaredConfigurationJson@@YAJPEBGPEAUDeclaredConfigurationScopeData@@0AEAVDCDocument@@0@Z; DeclaredConfigurationStore_ParseDeclaredConfigurationJson(ushort const *,DeclaredConfigurationScopeData *,ushort const *,DCDocument &,ushort const *)
0x1800848e1  mov     dword ptr [rsp+470h+var_440], eax
0x1800848e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl(void)'::`2'::impl
0x1800848ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(void)
0x1800848f1  test    al, al
0x1800848f3  jz      short loc_180084969
0x1800848f5  cmp     [rbp+370h+var_2C0], r14
0x1800848fc  jz      short loc_18008492F
0x1800848fe  lea     rdx, [rsp+470h+lpFileName]
0x180084903  lea     rcx, [rsp+470h+var_438]
0x180084908  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18008490d  nop
0x18008490e  mov     rcx, [rax]
0x180084911  add     rcx, 170h
0x180084918  lea     rdx, [rbp+370h+var_2D0]
0x18008491f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180084924  nop
0x180084925  lea     rcx, [rsp+470h+lpFileName]
0x18008492a  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18008492f  cmp     [rbp+370h+var_100], r14
0x180084936  jz      short loc_180084969
0x180084938  lea     rdx, [rsp+470h+lpFileName]
0x18008493d  lea     rcx, [rsp+470h+var_438]
0x180084942  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x180084947  nop
0x180084948  mov     rcx, [rax]
0x18008494b  add     rcx, 150h
0x180084952  lea     rdx, [rbp+370h+var_110]
0x180084959  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008495e  nop
0x18008495f  lea     rcx, [rsp+470h+lpFileName]
0x180084964  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x180084969  mov     ebx, dword ptr [rsp+470h+var_440]
0x18008496d  test    ebx, ebx
0x18008496f  jns     short loc_1800849B9
0x180084971  mov     rcx, [rbp+378h]; this
0x180084978  mov     r9d, ebx; char *
0x18008497b  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180084982  mov     edx, 57C0h; void *
0x180084987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008498c  nop
0x18008498d  mov     [rbp+370h+var_3B8], r14b
0x180084991  lea     rcx, [rbp+370h+var_3E0]
0x180084995  call    _lambda_20beab322fd1a2bfd14aef26fadca585___operator__
0x18008499a  nop
0x18008499b  lea     rcx, [rsp+470h+var_438]
0x1800849a0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x1800849a5  nop
0x1800849a6  mov     [rbp+370h+var_378], r14b
0x1800849aa  lea     rcx, [rbp+370h+var_3B0]
0x1800849ae  call    _lambda_2a396926707aedf7c3df209a68c826ed___operator__
0x1800849b3  nop
0x1800849b4  jmp     loc_180084FA4
0x1800849b9  cmp     [rbp+370h+var_220], r15d
0x1800849c0  jnz     short loc_1800849CB
0x1800849c2  mov     [rbp+370h+var_218], r15d
0x1800849c9  jmp     short loc_1800849E9
0x1800849cb  cmp     [rbp+370h+var_220], 4
0x1800849d2  jnz     loc_180084F14
0x1800849d8  mov     [rbp+370h+var_218], 14h
0x1800849e2  or      [rbp+370h+var_8C], 10h
0x1800849e9  lea     rdx, [rbp+370h+var_310]
0x1800849ed  cmp     [rbp+370h+var_2F8], 7
0x1800849f2  cmova   rdx, [rbp+370h+var_310]
0x1800849f7  lea     rcx, aUser_0; "user"
0x1800849fe  call    cs:__imp__o__wcsicmp
0x180084a04  test    eax, eax
0x180084a06  jnz     loc_180084BC4
0x180084a0c  mov     [rsp+470h+hMem], r14
0x180084a11  lea     rcx, [rsp+470h+hMem]
0x180084a16  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180084a1c  mov     ebx, eax
0x180084a1e  mov     dword ptr [rsp+470h+var_440], eax
0x180084a22  test    eax, eax
0x180084a24  jns     short loc_180084A6E
0x180084a26  mov     rcx, [rbp+378h]; this
0x180084a2d  mov     r9d, eax; char *
0x180084a30  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180084a37  mov     edx, 57E3h; void *
0x180084a3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084a41  nop
0x180084a42  mov     [rbp+370h+var_3B8], r14b
0x180084a46  lea     rcx, [rbp+370h+var_3E0]
0x180084a4a  call    _lambda_20beab322fd1a2bfd14aef26fadca585___operator__
0x180084a4f  nop
0x180084a50  lea     rcx, [rsp+470h+var_438]
0x180084a55  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x180084a5a  nop
0x180084a5b  mov     [rbp+370h+var_378], r14b
0x180084a5f  lea     rcx, [rbp+370h+var_3B0]
0x180084a63  call    _lambda_2a396926707aedf7c3df209a68c826ed___operator__
0x180084a68  nop
0x180084a69  jmp     loc_180084FA4
0x180084a6e  mov     rdx, [rsp+470h+hMem]
0x180084a73  lea     rcx, aS1518; "S-1-5-18"
0x180084a7a  call    cs:__imp__o__wcsicmp
0x180084a80  test    eax, eax
0x180084a82  jnz     short loc_180084AF1
0x180084a84  mov     rcx, [rsp+470h+hMem]; hMem
  ... truncated ...
```
