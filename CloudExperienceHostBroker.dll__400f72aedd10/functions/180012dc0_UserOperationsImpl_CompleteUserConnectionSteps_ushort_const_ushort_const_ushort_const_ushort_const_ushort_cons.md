# UserOperationsImpl::CompleteUserConnectionSteps(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,int,uint *)

- ea: `0x180012dc0`
- end: `0x180013b67`
- name: `?CompleteUserConnectionSteps@UserOperationsImpl@@UEAAJPEBG000000HHPEAI@Z`
- size: `3495`
- prototype: `int(UserOperationsImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, unsigned int *)`
- caller_count: `0`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002a3c`
- `0x1800059e0`
- `0x180007df0`
- `0x180008274`
- `0x180008344`
- `0x1800084c8`
- `0x180009f30`
- `0x18000a8fc`
- `0x18000e6f4`
- `0x1800102a8`
- `0x180010330`
- `0x180010714`
- `0x18001079c`
- `0x1800109b4`
- `0x18001192c`
- `0x1800119d0`
- `0x180012228`
- `0x1800122dc`
- `0x180012344`
- `0x18001237c`
- `0x180012408`
- `0x180012444`
- `0x18001256c`
- `0x180012dc0`
- `0x180013e54`
- `0x180015734`
- `0x1800177c8`
- `0x180017c50`
- `0x180017e44`
- `0x180018be8`
- `0x180018c64`
- `0x180018f10`
- `0x180019048`
- `0x18001a980`
- `0x18001b4bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800133ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001364b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013737`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800137bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001381a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800133ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001364b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013737`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800137bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001381a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013af1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ee0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800138b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ee0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800138b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a67`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001337a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001337a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800134a1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800134a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001353c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001353c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800131e1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800131e1`

## string_xrefs

- `0x180012e29`: `CreateConnectedAccountOobe`
- `0x180012e87`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180012ef6`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180012f7b`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180013011`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x1800130cb`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180013136`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall UserOperationsImpl::CompleteUserConnectionSteps(
        UserOperationsImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int *a6,
        unsigned __int16 *a7,
        const unsigned __int16 *a8,
        int a9,
        int a10,
        unsigned int *a11)
{
  signed int LastError; // edi
  HRESULT v15; // eax
  _BYTE *v16; // rcx
  __int64 v17; // rax
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  void *v24; // rbx
  LPVOID v25; // rsi
  __int64 (__fastcall *v26)(LPVOID, GUID *, GUID *, __int64 *); // rdi
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  signed int ActivationFactory; // eax
  signed int v31; // edi
  char v32; // al
  __int64 v33; // rax
  const char *v34; // r9
  HLOCAL v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r9
  const char *v38; // r9
  HLOCAL v39; // rcx
  __int64 v40; // rax
  BOOL v41; // edi
  const char *v42; // r9
  HLOCAL v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int v46; // eax
  HLOCAL v47; // rcx
  __int64 v48; // rax
  bool v49; // zf
  __int64 (__fastcall *v50)(__int64, void *, const unsigned __int16 *, GUID *); // rax
  const unsigned __int16 *v51; // rax
  HLOCAL v52; // rcx
  __int64 v53; // rax
  int v54; // eax
  HLOCAL v55; // rcx
  __int64 v56; // rax
  HLOCAL v57; // rcx
  __int64 v58; // rbx
  HRESULT v59; // eax
  __int64 v60; // rax
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rax
  LPVOID v64; // rdi
  __int64 (__fastcall *v65)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v66; // eax
  wil::details::in1diag3 *v67; // rcx
  __int64 v68; // rdx
  HRESULT v69; // eax
  wil::details::in1diag3 *v70; // rcx
  __int64 v71; // rdx
  _BYTE *v72; // rcx
  __int64 v73; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  int ppvd; // [rsp+20h] [rbp-E0h]
  int ppve; // [rsp+20h] [rbp-E0h]
  unsigned int v81; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  char v85[4]; // [rsp+80h] [rbp-80h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+84h] [rbp-7Ch] BYREF
  void *v87; // [rsp+88h] [rbp-78h] BYREF
  __int64 v88; // [rsp+90h] [rbp-70h] BYREF
  __int64 v89; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v90; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v91; // [rsp+A8h] [rbp-58h] BYREF
  DWORD cchName[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v93; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v94; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v95; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int16 *v96; // [rsp+D0h] [rbp-30h] BYREF
  DWORD cbSid; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v98[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v99[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v100; // [rsp+110h] [rbp+10h]
  __int64 v101; // [rsp+118h] [rbp+18h]
  char v102; // [rsp+120h] [rbp+20h]
  _QWORD v103[3]; // [rsp+128h] [rbp+28h] BYREF
  char v104; // [rsp+140h] [rbp+40h]
  HSTRING_HEADER hstringHeader; // [rsp+148h] [rbp+48h] BYREF
  __int64 v106; // [rsp+160h] [rbp+60h]
  _QWORD v107[42]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE Sid[80]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR Name[264]; // [rsp+540h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7A8h] [rbp+6A8h]

  v98[0] = this;
  v87 = a7;
  v96 = a8;
  *a11 = 0;
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v107,
    (__int64)"CreateConnectedAccountOobe");
  v107[0] = &MSAClientTraceTelemetry::CreateConnectedAccountOobe::`vftable';
  MSAClientTraceTelemetry::CreateConnectedAccountOobe::StartActivity((MSAClientTraceTelemetry::CreateConnectedAccountOobe *)v107);
  v90 = 0;
  v91 = 0;
  v89 = 0;
  v95 = 0;
  v94 = 0;
  v93 = 0;
  if ( !IsUserOOBE() )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)0x80070005LL,
      ppv);
    goto LABEL_121;
  }
  pv = 0;
  v81 = 0;
  v103[1] = &pv;
  v103[2] = &v81;
  v104 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
  v15 = CoCreateInstance(
          &GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e,
          0,
          1u,
          &GUID_10316cc3_d36e_46cd_8344_d85f12419862,
          &v90);
  LastError = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v15,
      ppva);
    v16 = pv;
    if ( !pv )
      goto LABEL_121;
    v17 = v81;
    if ( !v81 )
    {
LABEL_8:
      CoTaskMemFree(v16);
      goto LABEL_121;
    }
    do
    {
      *v16++ = 0;
      --v17;
    }
    while ( v17 );
LABEL_7:
    v16 = pv;
    goto LABEL_8;
  }
  v18 = v90;
  v19 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v90 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
  v20 = v19(v18, &GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2, &GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f, &v91);
  LastError = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v20,
      ppva);
    v16 = pv;
    if ( !pv )
      goto LABEL_121;
    v21 = v81;
    if ( !v81 )
      goto LABEL_8;
    do
    {
      *v16++ = 0;
      --v21;
    }
    while ( v21 );
    goto LABEL_7;
  }
  ppvb = (int)a5;
  v22 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v91 + 24LL))(
          v91,
          a2,
          a3,
          a4);
  LastError = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v22,
      (int)a5);
    v16 = pv;
    if ( !pv )
      goto LABEL_121;
    v23 = v81;
    if ( !v81 )
      goto LABEL_8;
    do
    {
      *v16++ = 0;
      --v23;
    }
    while ( v23 );
    goto LABEL_7;
  }
  v24 = 0;
  v87 = 0;
  v88 = 0;
  v99[0] = &tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::`vftable';
  v99[1] = 0;
  v99[2] = v99;
  v99[3] = 0;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,>(v103);
  v25 = v90;
  v26 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v90 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  v27 = v26(v25, &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e, &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1, &v89);
  LastError = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v27,
      (int)a5);
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
    v16 = pv;
    if ( !pv )
      goto LABEL_121;
    v28 = v81;
    if ( !v81 )
      goto LABEL_8;
    do
    {
      *v16++ = 0;
      --v28;
    }
    while ( v28 );
    goto LABEL_7;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58663440>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58663440>::GetImpl'::`2'::impl) )
  {
    LastError = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, GUID *))(*(_QWORD *)v89 + 32LL))(
                  v89,
                  0,
                  a2,
                  &GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f);
    cchReferencedDomainName = LastError;
    goto LABEL_34;
  }
  v29 = tip2::tip_test<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::start_and_watch_errors(
          &v88,
          &hstringHeader);
  tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::operator=(
    v99,
    v29);
  tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(&hstringHeader);
  peUse = SidTypeGroup;
  hMem = 0;
  v106 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Profile.SystemSetupInfo",
    0x27u,
    0x26u);
  ActivationFactory = RoGetActivationFactory(v106, &GUID_b8366a4b_fb6a_4571_be0a_9a0f67954123, &hMem);
  v31 = ActivationFactory;
  cchReferencedDomainName = ActivationFactory;
  v106 = 0;
  if ( ActivationFactory >= 0 )
  {
    if ( hMem )
    {
      v31 = (*(__int64 (__fastcall **)(HLOCAL, enum _SID_NAME_USE *))(*(_QWORD *)hMem + 48LL))(hMem, &peUse);
      cchReferencedDomainName = v31;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)a5);
  }
  MSAClientTraceTelemetry::CreateConnectedAccountOobe::OOBEStateForCustomSAMRead<long &>(
    (__int64)v107,
    (int *)&cchReferencedDomainName);
  MSAClientTraceTelemetry::CreateConnectedAccountOobe::SystemOutOfTheBoxExperienceState<enum Windows::System::Profile::SystemOutOfBoxExperienceState &>(
    (__int64)v107,
    (int *)&peUse);
  if ( v31 >= 0 )
  {
    if ( peUse != SidTypeGroup )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v87,
        0);
      cchReferencedDomainName = SHRegAllocData(
                                  HKEY_CURRENT_USER,
                                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
                                  L"SetSAMFolderName",
                                  v37,
                                  &v87);
      MSAClientTraceTelemetry::CreateConnectedAccountOobe::CustomSAMNameReadAttempt<long const &>(
        (__int64)v107,
        (int *)&cchReferencedDomainName);
      v24 = v87;
      if ( v87 )
      {
        v32 = 1;
        goto LABEL_33;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v31,
      ppvb);
  }
  v32 = 0;
LABEL_33:
  v85[0] = v32;
  MSAClientTraceTelemetry::ProvidedCustomSAMName<bool>(v85);
  LastError = (*(__int64 (__fastcall **)(__int64, void *, const unsigned __int16 *, GUID *))(*(_QWORD *)v89 + 32LL))(
                v89,
                v24,
                a2,
                &GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f);
  cchReferencedDomainName = LastError;
  tip2::tip_test<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::data(
    &v88,
    cchName);
  v33 = *(_QWORD *)cchName;
  ++*(_DWORD *)(*(_QWORD *)cchName + 276LL);
  *(_BYTE *)(v33 + 272) = v24 != 0;
  *(_DWORD *)(v33 + 280) = LastError;
  tip2::test_data_control<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_data_control<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(cchName);
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&hMem);
LABEL_34:
  MSAClientTraceTelemetry::CreateConnectedAccountOobe::CreateConnectedAccountFirstAttempt<long &>(
    (__int64)v107,
    (int *)&cchReferencedDomainName);
  if ( LastError != -805306269 )
  {
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
        (const char *)(unsigned int)LastError,
        1);
      tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
      wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
      v16 = pv;
      if ( !pv )
        goto LABEL_121;
      v61 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v61;
      }
      while ( v61 );
      goto LABEL_7;
    }
LABEL_85:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58663440>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58663440>::GetImpl'::`2'::impl)
      && v88 )
    {
      v58 = v88 + 8;
      wil::EnterCriticalSection(v98, v88 + 200);
      *(_DWORD *)(v58 + 64) |= 0x300u;
      if ( *(_QWORD *)(v58 + 240) )
        tip2::details::shared_data<1,0,0>::complete_helper(v58, 2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v98);
    }
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v59 = CoCreateInstance(
            &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
            0,
            1u,
            &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
            &v95);
    LastError = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
        (const char *)(unsigned int)v59,
        ppvd);
      v16 = pv;
      if ( !pv )
        goto LABEL_121;
      v60 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v60;
      }
      while ( v60 );
      goto LABEL_7;
    }
    v62 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, _QWORD))(*(_QWORD *)v95 + 24LL))(v95, pv, v81);
    LastError = v62;
    if ( v62 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
        (const char *)(unsigned int)v62,
        ppvd);
      v16 = pv;
      if ( !pv )
        goto LABEL_121;
      v63 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v63;
      }
      while ( v63 );
      goto LABEL_7;
    }
    v64 = v90;
    v65 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v90 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
    v66 = v65(v64, &GUID_6447e897_294b_409a_bf15_5f349a20f2c0, &GUID_ef65a750_6f76_4b47_b603_c99692a7d5d8, &v94);
    v67 = retaddr;
    if ( v66 >= 0 )
    {
      v66 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v94 + 24LL))(v94, a2);
      v67 = retaddr;
      if ( v66 >= 0 )
        goto LABEL_110;
      v68 = 229;
    }
    else
    {
      v68 = 227;
    }
    wil::details::in1diag3::_Log_Hr(
      v67,
      (void *)v68,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v66,
      ppvd);
LABEL_110:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
    v69 = CoCreateInstance(
            &GUID_66a1c746_b147_43b8_8d08_a2657bebbe8f,
            0,
            1u,
            &GUID_6c14b719_4fcc_437e_a81b_4536dd29f358,
            &v93);
    v70 = retaddr;
    if ( v69 >= 0 )
    {
      ppve = 1;
      v69 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, LPVOID, _QWORD))(*(_QWORD *)v93 + 24LL))(
              v93,
              a2,
              pv,
              v81);
      v70 = retaddr;
      if ( v69 >= 0 )
      {
LABEL_115:
        wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(v107);
        v72 = pv;
        if ( pv )
        {
          v73 = v81;
          if ( v81 )
          {
            do
            {
              *v72++ = 0;
              --v73;
            }
            while ( v73 );
            v72 = pv;
          }
          CoTaskMemFree(v72);
        }
        LastError = 0;
        goto LABEL_121;
      }
      v71 = 239;
    }
    else
    {
      v71 = 233;
    }
    wil::details::in1diag3::_Log_Hr(
      v70,
      (void *)v71,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v69,
      ppve);
    goto LABEL_115;
  }
  cbSid = 68;
  cchReferencedDomainName = 260;
  peUse = SidTypeInvalid;
  memset_0(Name, 0, 0x208u);
  cchName[0] = 260;
  hMem = 0;
  if ( !LookupAccountNameW(0, a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA9,
                  (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
                  v34);
    v35 = hMem;
    hMem = 0;
    if ( v35 )
      LocalFree(v35);
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
    v16 = pv;
    if ( pv )
    {
      v36 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v36;
      }
      while ( v36 );
      goto LABEL_7;
    }
    goto LABEL_121;
  }
  peUse = SidTypeInvalid;
  cchReferencedDomainName = 260;
  if ( !LookupAccountSidW(0, Sid, Name, cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAE,
                  (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
                  v38);
    v39 = hMem;
    hMem = 0;
    if ( v39 )
      LocalFree(v39);
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
    v16 = pv;
    if ( pv )
    {
      v40 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v40;
      }
      while ( v40 );
      goto LABEL_7;
    }
    goto LABEL_121;
  }
  hstringHeader.Reserved.Reserved1 = &hMem;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v41 = ConvertSidToStringSidW(Sid, (LPWSTR *)&hstringHeader.Reserved.Reserved2[8]);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&hstringHeader);
  if ( !v41 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xB0,
                  (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
                  v42);
    v43 = hMem;
    hMem = 0;
    if ( v43 )
      LocalFree(v43);
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
    v16 = pv;
    if ( pv )
    {
      v44 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v44;
      }
      while ( v44 );
      goto LABEL_7;
    }
    goto LABEL_121;
  }
  v45 = UserOperationsImpl::DisconnectUser((UserOperationsImpl *)(v98[0] - 8LL), a2, (unsigned __int8 *)pv, v81);
  if ( v45 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v45,
      ppvc);
  v46 = (*(__int64 (__fastcall **)(__int64, HLOCAL, WCHAR *, WCHAR *))(*(_QWORD *)v91 + 72LL))(
          v91,
          hMem,
          Name,
          ReferencedDomainName);
  LastError = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v46,
      ppvc);
    v47 = hMem;
    hMem = 0;
    if ( v47 )
      LocalFree(v47);
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
    v16 = pv;
    if ( pv )
    {
      v48 = v81;
      if ( !v81 )
        goto LABEL_8;
      do
      {
        *v16++ = 0;
        --v48;
      }
      while ( v48 );
      goto LABEL_7;
    }
    goto LABEL_121;
  }
  v49 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58663440>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58663440>::GetImpl'::`2'::impl) == 0;
  v50 = *(__int64 (__fastcall **)(__int64, void *, const unsigned __int16 *, GUID *))(*(_QWORD *)v89 + 32LL);
  if ( !v49 )
  {
    LastError = v50(v89, v24, a2, &GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f);
    tip2::tip_test<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::data(
      &v88,
      &v96);
    v51 = v96;
    ++*((_DWORD *)v96 + 69);
    *((_DWORD *)v51 + 71) = LastError;
    tip2::test_data_control<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_data_control<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(&v96);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
        (const char *)(unsigned int)LastError,
        1);
      v52 = hMem;
      hMem = 0;
      if ( v52 )
        LocalFree(v52);
      tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
      wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
      v16 = pv;
      if ( pv )
      {
        v53 = v81;
        if ( !v81 )
          goto LABEL_8;
        do
        {
          *v16++ = 0;
          --v53;
        }
        while ( v53 );
        goto LABEL_7;
      }
      goto LABEL_121;
    }
    goto LABEL_83;
  }
  v54 = v50(v89, 0, a2, &GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f);
  LastError = v54;
  if ( v54 >= 0 )
  {
LABEL_83:
    v57 = hMem;
    hMem = 0;
    if ( v57 )
      LocalFree(v57);
    goto LABEL_85;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD0,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
    (const char *)(unsigned int)v54,
    1);
  v55 = hMem;
  hMem = 0;
  if ( v55 )
    LocalFree(v55);
  tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(v99);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(&v88);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v87);
  v16 = pv;
  if ( pv )
  {
    v56 = v81;
    if ( !v81 )
      goto LABEL_8;
    do
    {
      *v16++ = 0;
      --v56;
    }
    while ( v56 );
    goto LABEL_7;
  }
LABEL_121:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v91);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
  MSAClientTraceTelemetry::CreateConnectedAccountOobe::~CreateConnectedAccountOobe((MSAClientTraceTelemetry::CreateConnectedAccountOobe *)v107);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012dc0  push    rbp
0x180012dc2  push    rbx
0x180012dc3  push    rsi
0x180012dc4  push    rdi
0x180012dc5  push    r12
0x180012dc7  push    r13
0x180012dc9  push    r14
0x180012dcb  push    r15
0x180012dcd  lea     rbp, [rsp-668h]
0x180012dd5  sub     rsp, 768h
0x180012ddc  mov     rax, cs:__security_cookie
0x180012de3  xor     rax, rsp
0x180012de6  mov     [rbp+6A0h+var_50], rax
0x180012ded  mov     r15, r9
0x180012df0  mov     rsi, r8
0x180012df3  mov     r14, rdx
0x180012df6  mov     [rbp+6A0h+var_6C0], rcx
0x180012dfa  mov     r12, [rbp+6A0h+arg_20]
0x180012e01  mov     r13, [rbp+6A0h+arg_28]
0x180012e08  mov     rax, [rbp+6A0h+arg_30]
0x180012e0f  mov     [rbp+6A0h+var_718], rax
0x180012e13  mov     rax, [rbp+6A0h+arg_38]
0x180012e1a  mov     [rbp+6A0h+var_6D0], rax
0x180012e1e  mov     rax, [rbp+6A0h+arg_50]
0x180012e25  xor     ebx, ebx
0x180012e27  mov     [rax], ebx
0x180012e29  lea     rdx, aCreateconnecte_1; "CreateConnectedAccountOobe"
0x180012e30  lea     rcx, [rbp+6A0h+var_610]; struct wil::details::IFailureCallback *
0x180012e37  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012e3c  lea     rax, ??_7CreateConnectedAccountOobe@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::CreateConnectedAccountOobe::`vftable'
0x180012e43  mov     [rbp+6A0h+var_610], rax
0x180012e4a  lea     rcx, [rbp+6A0h+var_610]; this
0x180012e51  call    ?StartActivity@CreateConnectedAccountOobe@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::CreateConnectedAccountOobe::StartActivity(void)
0x180012e56  nop
0x180012e57  mov     [rbp+6A0h+var_700], rbx
0x180012e5b  mov     [rbp+6A0h+var_6F8], rbx
0x180012e5f  mov     [rbp+6A0h+var_708], rbx
0x180012e63  mov     [rbp+6A0h+var_6D8], rbx
0x180012e67  mov     [rbp+6A0h+var_6E0], rbx
0x180012e6b  mov     [rbp+6A0h+var_6E8], rbx
0x180012e6f  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x180012e74  test    al, al
0x180012e76  jnz     short loc_180012E9B
0x180012e78  mov     rcx, [rbp+6A8h]; this
0x180012e7f  mov     edi, 80070005h
0x180012e84  mov     r9d, edi; char *
0x180012e87  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180012e8e  lea     edx, [rbx+41h]; void *
0x180012e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e96  jmp     loc_180013AFA
0x180012e9b  mov     [rsp+7A0h+pv], rbx
0x180012ea0  mov     [rsp+7A0h+var_740], ebx
0x180012ea4  lea     rax, [rsp+7A0h+pv]
0x180012ea9  mov     [rbp+6A0h+var_670], rax
0x180012ead  lea     rax, [rsp+7A0h+var_740]
0x180012eb2  mov     [rbp+6A0h+var_668], rax
0x180012eb6  mov     [rbp+6A0h+var_660], 1
0x180012eba  lea     rcx, [rbp+6A0h+var_700]
0x180012ebe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012ec3  lea     rax, [rbp+6A0h+var_700]
0x180012ec7  mov     [rsp+7A0h+ppv], rax; int
0x180012ecc  lea     r9, _GUID_10316cc3_d36e_46cd_8344_d85f12419862; riid
0x180012ed3  xor     edx, edx; pUnkOuter
0x180012ed5  lea     r8d, [rdx+1]; dwClsContext
0x180012ed9  lea     rcx, _GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e; rclsid
0x180012ee0  call    cs:__imp_CoCreateInstance
0x180012ee6  mov     edi, eax
0x180012ee8  test    eax, eax
0x180012eea  jns     short loc_180012F3A
0x180012eec  mov     rcx, [rbp+6A8h]; this
0x180012ef3  mov     r9d, eax; char *
0x180012ef6  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180012efd  mov     edx, 50h ; 'P'; void *
0x180012f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f07  nop
0x180012f08  mov     rcx, [rsp+7A0h+pv]
0x180012f0d  test    rcx, rcx
0x180012f10  jz      loc_180013AFA
0x180012f16  mov     eax, [rsp+7A0h+var_740]
0x180012f1a  test    rax, rax
0x180012f1d  jz      short loc_180012F2F
0x180012f1f  mov     [rcx], bl
0x180012f21  inc     rcx
0x180012f24  sub     rax, 1
0x180012f28  jnz     short loc_180012F1F
0x180012f2a  mov     rcx, [rsp+7A0h+pv]; pv
0x180012f2f  call    cs:__imp_CoTaskMemFree
0x180012f35  jmp     loc_180013AFA
0x180012f3a  mov     rdi, [rbp+6A0h+var_700]
0x180012f3e  mov     rax, [rdi]
0x180012f41  mov     rbx, [rax+18h]
0x180012f45  lea     rcx, [rbp+6A0h+var_6F8]
0x180012f49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012f4e  lea     r9, [rbp+6A0h+var_6F8]
0x180012f52  lea     r8, _GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f
0x180012f59  lea     rdx, _GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2
0x180012f60  mov     rcx, rdi
0x180012f63  mov     rax, rbx
0x180012f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f6b  mov     edi, eax
0x180012f6d  test    eax, eax
0x180012f6f  jns     short loc_180012FB5
0x180012f71  mov     rcx, [rbp+6A8h]; this
0x180012f78  mov     r9d, eax; char *
0x180012f7b  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180012f82  mov     edx, 51h ; 'Q'; void *
0x180012f87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f8c  nop
0x180012f8d  mov     rcx, [rsp+7A0h+pv]
0x180012f92  test    rcx, rcx
0x180012f95  jz      loc_180013AFA
0x180012f9b  mov     eax, [rsp+7A0h+var_740]
0x180012f9f  test    rax, rax
0x180012fa2  jz      short loc_180012F2F
0x180012fa4  mov     byte ptr [rcx], 0
0x180012fa7  inc     rcx
0x180012faa  sub     rax, 1
0x180012fae  jnz     short loc_180012FA4
0x180012fb0  jmp     loc_180012F2A
0x180012fb5  mov     rcx, [rbp+6A0h+var_6F8]
0x180012fb9  mov     rax, [rcx]
0x180012fbc  lea     rdx, [rsp+7A0h+var_740]
0x180012fc1  mov     [rsp+7A0h+var_758], rdx
0x180012fc6  lea     rdx, [rsp+7A0h+pv]
0x180012fcb  mov     [rsp+7A0h+var_760], rdx
0x180012fd0  mov     rdx, [rbp+6A0h+var_6D0]
0x180012fd4  mov     [rsp+7A0h+var_768], rdx
0x180012fd9  mov     rdx, [rbp+6A0h+var_718]
0x180012fdd  mov     [rsp+7A0h+peUse], rdx
0x180012fe2  mov     [rsp+7A0h+cchReferencedDomainName], r13; unsigned int *
0x180012fe7  mov     [rsp+7A0h+ppv], r12; int
0x180012fec  mov     r9, r15
0x180012fef  mov     r8, rsi
0x180012ff2  mov     rdx, r14
0x180012ff5  mov     rax, [rax+18h]
0x180012ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffe  mov     edi, eax
0x180013000  xor     r15d, r15d
0x180013003  test    eax, eax
0x180013005  jns     short loc_18001304E
0x180013007  mov     rcx, [rbp+6A8h]; this
0x18001300e  mov     r9d, eax; char *
0x180013011  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180013018  lea     edx, [r15+5Bh]; void *
0x18001301c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013021  nop
0x180013022  mov     rcx, [rsp+7A0h+pv]
0x180013027  test    rcx, rcx
0x18001302a  jz      loc_180013AFA
0x180013030  mov     eax, [rsp+7A0h+var_740]
0x180013034  test    rax, rax
0x180013037  jz      loc_180012F2F
0x18001303d  mov     [rcx], r15b
0x180013040  inc     rcx
0x180013043  sub     rax, 1
0x180013047  jnz     short loc_18001303D
0x180013049  jmp     loc_180012F2A
0x18001304e  mov     rbx, r15
0x180013051  mov     [rbp+6A0h+var_718], rbx
0x180013055  mov     [rbp+6A0h+var_710], r15
0x180013059  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::`vftable'
0x180013060  mov     [rbp+6A0h+var_6B0], rax
0x180013064  mov     [rbp+6A0h+var_6A8], r15
0x180013068  lea     rax, [rbp+6A0h+var_6B0]
0x18001306c  mov     [rbp+6A0h+var_6A0], rax
0x180013070  mov     [rbp+6A0h+var_698], r15
0x180013074  mov     [rbp+6A0h+var_690], r15d
0x180013078  mov     [rbp+6A0h+var_688], r15
0x18001307c  mov     [rbp+6A0h+var_680], r15b
0x180013080  lea     rcx, [rbp+6A0h+var_678]
0x180013084  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,>(void)
0x180013089  nop
0x18001308a  mov     rsi, [rbp+6A0h+var_700]
0x18001308e  mov     rax, [rsi]
0x180013091  mov     rdi, [rax+18h]
0x180013095  lea     rcx, [rbp+6A0h+var_708]
0x180013099  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001309e  lea     r9, [rbp+6A0h+var_708]
0x1800130a2  lea     r8, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1
0x1800130a9  lea     rdx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e
0x1800130b0  mov     rcx, rsi
0x1800130b3  mov     rax, rdi
0x1800130b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130bb  mov     edi, eax
0x1800130bd  test    eax, eax
0x1800130bf  jns     short loc_180013127
0x1800130c1  mov     rcx, [rbp+6A8h]; this
0x1800130c8  mov     r9d, eax; char *
0x1800130cb  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800130d2  mov     edx, 63h ; 'c'; void *
0x1800130d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130dc  nop
0x1800130dd  lea     rcx, [rbp+6A0h+var_6B0]
0x1800130e1  call    ??1?$test_watcher@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(void)
0x1800130e6  nop
0x1800130e7  lea     rcx, [rbp+6A0h+var_710]
0x1800130eb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>,wil::err_returncode_policy>(void)
0x1800130f0  nop
0x1800130f1  lea     rcx, [rbp+6A0h+var_718]
0x1800130f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800130fa  nop
0x1800130fb  mov     rcx, [rsp+7A0h+pv]
0x180013100  test    rcx, rcx
0x180013103  jz      loc_180013AFA
0x180013109  mov     eax, [rsp+7A0h+var_740]
0x18001310d  test    rax, rax
0x180013110  jz      loc_180012F2F
0x180013116  mov     [rcx], r15b
0x180013119  inc     rcx
0x18001311c  sub     rax, 1
0x180013120  jnz     short loc_180013116
0x180013122  jmp     loc_180012F2A
0x180013127  lea     r13, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID58663440@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID58663440@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58663440> `wil::Feature<__WilFeatureTraits_Feature_ID58663440>::GetImpl(void)'::`2'::impl
0x18001312e  mov     rcx, r13
0x180013131  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58663440@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58663440>::__private_IsEnabled(void)
0x180013136  lea     rsi, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x18001313d  test    al, al
0x18001313f  jnz     short loc_180013185
0x180013141  mov     rcx, [rbp+6A0h+var_708]
0x180013145  mov     rax, [rcx]
0x180013148  mov     edx, [rsp+7A0h+var_740]
0x18001314c  mov     dword ptr [rsp+7A0h+peUse], edx
0x180013150  mov     rdx, [rsp+7A0h+pv]
0x180013155  mov     [rsp+7A0h+cchReferencedDomainName], rdx
0x18001315a  mov     r12d, 1
0x180013160  mov     dword ptr [rsp+7A0h+ppv], r12d
0x180013165  lea     r9, _GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f
0x18001316c  mov     r8, r14
0x18001316f  xor     edx, edx
0x180013171  mov     rax, [rax+20h]
0x180013175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001317a  mov     edi, eax
0x18001317c  mov     [rsp+7A0h+var_730], eax
0x180013180  jmp     loc_1800132FB
0x180013185  lea     rdx, [rbp+6A0h+hstringHeader]
0x180013189  lea     rcx, [rbp+6A0h+var_710]
0x18001318d  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::start_and_watch_errors(void)
0x180013192  mov     rdx, rax
0x180013195  lea     rcx, [rbp+6A0h+var_6B0]
0x180013199  call    ??4?$test_watcher@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@@tip2@@QEAAAEAV01@$$QEAV01@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::operator=(tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>> &&)
0x18001319e  lea     rcx, [rbp+6A0h+hstringHeader]
0x1800131a2  call    ??1?$test_watcher@V?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>>(void)
0x1800131a7  mov     [rbp+6A0h+var_71C], 2
0x1800131ae  mov     [rsp+7A0h+hMem], r15
0x1800131b3  mov     [rbp+6A0h+var_640], r15
0x1800131b7  mov     r9d, 26h ; '&'; unsigned int
0x1800131bd  lea     r8d, [r9+1]; unsigned int
0x1800131c1  lea     rdx, ?RuntimeClass_Windows_System_Profile_SystemSetupInfo@@3QBGB; "Windows.System.Profile.SystemSetupInfo"
0x1800131c8  lea     rcx, [rbp+6A0h+hstringHeader]; hstringHeader
0x1800131cc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800131d1  lea     r8, [rsp+7A0h+hMem]
0x1800131d6  lea     rdx, _GUID_b8366a4b_fb6a_4571_be0a_9a0f67954123
0x1800131dd  mov     rcx, [rbp+6A0h+var_640]
0x1800131e1  call    cs:__imp_RoGetActivationFactory
0x1800131e7  mov     edi, eax
0x1800131e9  mov     [rsp+7A0h+var_730], eax
0x1800131ed  mov     [rbp+6A0h+var_640], r15
0x1800131f1  mov     rcx, [rbp+6A8h]; this
0x1800131f8  test    eax, eax
0x1800131fa  jns     short loc_18001320E
0x1800131fc  mov     r9d, eax; char *
0x1800131ff  mov     r8, rsi; unsigned int
0x180013202  mov     edx, 6Dh ; 'm'; void *
0x180013207  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001320c  jmp     short loc_18001322E
0x18001320e  mov     rcx, [rsp+7A0h+hMem]
0x180013213  test    rcx, rcx
0x180013216  jz      short loc_18001322E
0x180013218  mov     rax, [rcx]
0x18001321b  lea     rdx, [rbp+6A0h+var_71C]
0x18001321f  mov     rax, [rax+30h]
0x180013223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013228  mov     edi, eax
0x18001322a  mov     [rsp+7A0h+var_730], eax
0x18001322e  lea     rdx, [rsp+7A0h+var_730]
0x180013233  lea     rcx, [rbp+6A0h+var_610]
0x18001323a  call    ??$OOBEStateForCustomSAMRead@AEAJ@CreateConnectedAccountOobe@MSAClientTraceTelemetry@@QEAAXAEAJ@Z; MSAClientTraceTelemetry::CreateConnectedAccountOobe::OOBEStateForCustomSAMRead<long &>(long &)
0x18001323f  lea     rdx, [rbp+6A0h+var_71C]
0x180013243  lea     rcx, [rbp+6A0h+var_610]
0x18001324a  call    ??$SystemOutOfTheBoxExperienceState@AEAW4SystemOutOfBoxExperienceState@Profile@System@Windows@@@CreateConnectedAccountOobe@MSAClientTraceTelemetry@@QEAAXAEAW4SystemOutOfBoxExperienceState@Profile@System@Windows@@@Z; MSAClientTraceTelemetry::CreateConnectedAccountOobe::SystemOutOfTheBoxExperienceState<Windows::System::Profile::SystemOutOfBoxExperienceState &>(Windows::System::Profile::SystemOutOfBoxExperienceState &)
0x18001324f  mov     rcx, [rbp+6A8h]; this
0x180013256  test    edi, edi
0x180013258  jns     loc_1800133FB
0x18001325e  mov     r9d, edi; char *
0x180013261  mov     r8, rsi; unsigned int
0x180013264  mov     edx, 74h ; 't'; void *
0x180013269  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001326e  mov     al, r15b
0x180013271  mov     r12d, 1
0x180013277  mov     [rbp+6A0h+var_720], al
0x18001327a  lea     rcx, [rbp+6A0h+var_720]
0x18001327e  call    ??$ProvidedCustomSAMName@_N@MSAClientTraceTelemetry@@SAX$$QEA_N@Z; MSAClientTraceTelemetry::ProvidedCustomSAMName<bool>(bool &&)
0x180013283  mov     rcx, [rbp+6A0h+var_708]
0x180013287  mov     rax, [rcx]
0x18001328a  mov     edx, [rsp+7A0h+var_740]
0x18001328e  mov     dword ptr [rsp+7A0h+peUse], edx
0x180013292  mov     rdx, [rsp+7A0h+pv]
0x180013297  mov     [rsp+7A0h+cchReferencedDomainName], rdx
0x18001329c  mov     dword ptr [rsp+7A0h+ppv], r12d; int
0x1800132a1  lea     r9, _GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f
  ... truncated ...
```
