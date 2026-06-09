# PluginEngine::RunProvisioningTurn(Windows::Management::Provisioning::ProvisioningTurn)

- ea: `0x180026b60`
- end: `0x180027321`
- name: `?RunProvisioningTurn@PluginEngine@@UEAAJW4ProvisioningTurn@Provisioning@Management@Windows@@@Z`
- size: `1985`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000334c`
- `0x1800067fc`
- `0x1800087ec`
- `0x18001e560`
- `0x18001fbfc`
- `0x18001ff18`
- `0x18001ffe0`
- `0x180024840`
- `0x180024898`
- `0x180024918`
- `0x1800249c0`
- `0x180024a10`
- `0x180024d00`
- `0x180026b60`
- `0x1800280f4`
- `0x180028168`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026dfe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026dfe`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180026c77`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180026c77`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026d8e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026ebe`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026f72`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027011`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800270ab`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027143`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800271e9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027281`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800272e2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026d8e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026ebe`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026f72`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027011`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800270ab`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027143`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800271e9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027281`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800272e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026e21`

## string_xrefs

- `0x180026c36`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026c94`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026d3b`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026e5b`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026f0f`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026fae`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027048`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800270e0`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027186`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002721e`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall PluginEngine::RunProvisioningTurn(unsigned int *a1, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z; // rax
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  const WCHAR *v20; // rbx
  unsigned __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, int *); // rbx
  int v26; // eax
  unsigned int v27; // ebx
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rdx
  int v39[2]; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+28h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+30h] [rbp-B8h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-B0h] BYREF
  int v43; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v44[24]; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+60h] [rbp-88h]
  PCWSTR sourceString[3]; // [rsp+68h] [rbp-80h] BYREF
  unsigned __int64 v47; // [rsp+80h] [rbp-68h]
  HSTRING string; // [rsp+88h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-58h] BYREF
  HSTRING v50; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( (unsigned __int8)IsShellExecuteExWPresent() )
  {
    v47 = 7;
    sourceString[2] = 0;
    LOWORD(sourceString[0]) = 0;
    std::wstring::append(sourceString, L"/Turn ");
    v4 = std::to_wstring(&string, a2);
    std::wstring::append(sourceString, v4, 0, -1);
    LOBYTE(v5) = 1;
    std::wstring::_Tidy(&string, v5, 0);
    v6 = 1800000;
    if ( a2 != 3 )
      v6 = 600000;
    v7 = (*(__int64 (__fastcall **)(unsigned int *, PCWSTR *, __int64))(*(_QWORD *)a1 + 104LL))(a1, sourceString, v6);
    v9 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v7,
        v39[0]);
      LOBYTE(v10) = 1;
      std::wstring::_Tidy(sourceString, v10, 0);
      return v9;
    }
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(sourceString, v8, 0);
    return 0;
  }
  v12 = RoInitialize(1);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v12,
      v39[0]);
    return v13;
  }
  v44[17] = 1;
  length[0] = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v44,
    length);
  *(_QWORD *)v39 = 0;
  v41 = 0;
  V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = (__int64 *)___Make_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(length, v44);
  v16 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  v45 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = 0;
  v17 = *(_QWORD *)length;
  if ( *(_QWORD *)length )
  {
    *(_QWORD *)length = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  Windows::Internal::StringReference::StringReference(&v50, (const unsigned __int16 (*)[47])v15);
  v40 = 0;
  v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(
          v50,
          &v40);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v18,
      v39[0]);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_14:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v44);
    RoUninitialize();
    return v19;
  }
  (*(void (__fastcall **)(unsigned int *, PCWSTR *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, sourceString, a1[14]);
  v20 = (const WCHAR *)sourceString;
  if ( v47 >= 8 )
    v20 = sourceString[0];
  length[0] = 0;
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( (int)ULongLongToUInt(v21, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(v20, length[0], &hstringHeader, &string);
  v22 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v40 + 88LL))(v40, string);
  v19 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v22,
      v39[0]);
    LOBYTE(v23) = 1;
    std::wstring::_Tidy(sourceString, v23, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_14;
  }
  v24 = v40;
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v40 + 64LL);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
  v26 = v25(v24, a2, v39);
  v27 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v26,
      v39[0]);
    LOBYTE(v28) = 1;
    std::wstring::_Tidy(sourceString, v28, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_48;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v39 + 48LL))(*(_QWORD *)v39, v16);
  v27 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v29,
      v39[0]);
    LOBYTE(v30) = 1;
    std::wstring::_Tidy(sourceString, v30, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_48;
  }
  v31 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<unsigned int>>::As<IAsyncInfo>(v39, &v41);
  v27 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v31,
      v39[0]);
    LOBYTE(v32) = 1;
    std::wstring::_Tidy(sourceString, v32, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_48;
  }
  if ( (unsigned __int8)_wait___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(v44) )
  {
    v43 = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v39 + 64LL))(*(_QWORD *)v39, &v43);
    v27 = v34;
    if ( v34 >= 0 )
    {
      v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 80LL))(v41);
      v27 = v36;
      if ( v36 >= 0 )
      {
        LOBYTE(v37) = 1;
        std::wstring::_Tidy(sourceString, v37, 0);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
        __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v44);
        RoUninitialize();
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v36,
        v39[0]);
      LOBYTE(v38) = 1;
      std::wstring::_Tidy(sourceString, v38, 0);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v34,
        v39[0]);
      LOBYTE(v35) = 1;
      std::wstring::_Tidy(sourceString, v35, 0);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
LABEL_48:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v44);
    RoUninitialize();
    return v27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x129,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)0x800705B4LL,
    v39[0]);
  LOBYTE(v33) = 1;
  std::wstring::_Tidy(sourceString, v33, 0);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
  __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v44);
  RoUninitialize();
  return 2147943860LL;
}

```

## disassembly

```asm
0x180026b60  mov     [rsp+arg_10], rbx
0x180026b65  mov     [rsp+arg_18], rsi
0x180026b6a  push    rdi
0x180026b6b  push    r14
0x180026b6d  push    r15
0x180026b6f  sub     rsp, 0D0h
0x180026b76  mov     rax, cs:__security_cookie
0x180026b7d  xor     rax, rsp
0x180026b80  mov     [rsp+0E8h+var_20], rax
0x180026b88  mov     r14d, edx
0x180026b8b  mov     rdi, rcx
0x180026b8e  call    IsShellExecuteExWPresent
0x180026b93  xor     r15d, r15d
0x180026b96  test    al, al
0x180026b98  jz      loc_180026C72
0x180026b9e  mov     [rsp+0E8h+var_68], 7
0x180026baa  mov     [rsp+0E8h+var_70], r15
0x180026baf  mov     word ptr [rsp+0E8h+sourceString], r15w
0x180026bb5  lea     rdx, aTurn; "/Turn "
0x180026bbc  lea     rcx, [rsp+0E8h+sourceString]
0x180026bc1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180026bc6  mov     edx, r14d
0x180026bc9  lea     rcx, [rsp+0E8h+string]
0x180026bd1  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180026bd6  nop
0x180026bd7  or      r9, 0FFFFFFFFFFFFFFFFh
0x180026bdb  xor     r8d, r8d
0x180026bde  mov     rdx, rax
0x180026be1  lea     rcx, [rsp+0E8h+sourceString]
0x180026be6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180026beb  nop
0x180026bec  xor     r8d, r8d
0x180026bef  mov     dl, 1
0x180026bf1  lea     rcx, [rsp+0E8h+string]
0x180026bf9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026bfe  mov     rax, [rdi]
0x180026c01  mov     ecx, 927C0h
0x180026c06  mov     r8d, 1B7740h
0x180026c0c  cmp     r14d, 3
0x180026c10  cmovnz  r8d, ecx
0x180026c14  lea     rdx, [rsp+0E8h+sourceString]
0x180026c19  mov     rcx, rdi
0x180026c1c  mov     rax, [rax+68h]
0x180026c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c25  mov     ebx, eax
0x180026c27  test    eax, eax
0x180026c29  jns     short loc_180026C5E
0x180026c2b  mov     rcx, [rsp+0E8h]; this
0x180026c33  mov     r9d, eax; char *
0x180026c36  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026c3d  mov     edx, 109h; void *
0x180026c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c47  nop
0x180026c48  xor     r8d, r8d
0x180026c4b  mov     dl, 1
0x180026c4d  lea     rcx, [rsp+0E8h+sourceString]
0x180026c52  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026c57  mov     eax, ebx
0x180026c59  jmp     loc_1800272F7
0x180026c5e  xor     r8d, r8d
0x180026c61  mov     dl, 1
0x180026c63  lea     rcx, [rsp+0E8h+sourceString]
0x180026c68  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026c6d  jmp     loc_1800272EF
0x180026c72  mov     ecx, 1
0x180026c77  call    cs:__imp_RoInitialize
0x180026c7e  nop     dword ptr [rax+rax+00h]
0x180026c83  mov     ebx, eax
0x180026c85  test    eax, eax
0x180026c87  jns     short loc_180026CAC
0x180026c89  mov     rcx, [rsp+0E8h]; this
0x180026c91  mov     r9d, eax; char *
0x180026c94  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026c9b  mov     edx, 10Eh; void *
0x180026ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ca5  mov     eax, ebx
0x180026ca7  jmp     loc_1800272F7
0x180026cac  mov     [rsp+0E8h+var_8F], 1
0x180026cb1  mov     [rsp+0E8h+length], r15d
0x180026cb6  lea     rdx, [rsp+0E8h+length]
0x180026cbb  lea     rcx, [rsp+0E8h+var_A0]
0x180026cc0  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180026cc5  nop
0x180026cc6  mov     qword ptr [rsp+0E8h+var_C8], r15; int
0x180026ccb  mov     [rsp+0E8h+var_B8], r15
0x180026cd0  lea     rdx, [rsp+0E8h+var_A0]
0x180026cd5  lea     rcx, [rsp+0E8h+length]
0x180026cda  call    ??$Make@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@12@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x180026cdf  mov     rsi, [rax]
0x180026ce2  mov     [rsp+0E8h+var_88], rsi
0x180026ce7  mov     [rax], r15
0x180026cea  mov     rcx, qword ptr [rsp+0E8h+length]
0x180026cef  test    rcx, rcx
0x180026cf2  jz      short loc_180026D06
0x180026cf4  mov     qword ptr [rsp+0E8h+length], r15
0x180026cf9  mov     rax, [rcx]
0x180026cfc  mov     rax, [rax+10h]
0x180026d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d05  nop
0x180026d06  lea     rcx, [rsp+0E8h+var_40]; string
0x180026d0e  call    ??$?0$0CP@@StringReference@Internal@Windows@@QEAA@AEAY0CP@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[47])
0x180026d13  mov     [rsp+0E8h+var_C0], r15
0x180026d18  lea     rdx, [rsp+0E8h+var_C0]
0x180026d1d  mov     rcx, [rsp+0E8h+var_40]
0x180026d25  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>)
0x180026d2a  mov     ebx, eax
0x180026d2c  test    eax, eax
0x180026d2e  jns     short loc_180026DA1
0x180026d30  mov     rcx, [rsp+0E8h]; this
0x180026d38  mov     r9d, eax; char *
0x180026d3b  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026d42  mov     edx, 11Dh; void *
0x180026d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d4c  nop
0x180026d4d  lea     rcx, [rsp+0E8h+var_C0]
0x180026d52  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026d57  nop
0x180026d58  test    rsi, rsi
0x180026d5b  jz      short loc_180026D6D
0x180026d5d  mov     rax, [rsi]
0x180026d60  mov     rcx, rsi
0x180026d63  mov     rax, [rax+10h]
0x180026d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d6c  nop
0x180026d6d  lea     rcx, [rsp+0E8h+var_B8]
0x180026d72  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026d77  nop
0x180026d78  lea     rcx, [rsp+0E8h+var_C8]
0x180026d7d  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026d82  nop
0x180026d83  lea     rcx, [rsp+0E8h+var_A0]
0x180026d88  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180026d8d  nop
0x180026d8e  call    cs:__imp_RoUninitialize
0x180026d95  nop     dword ptr [rax+rax+00h]
0x180026d9a  mov     eax, ebx
0x180026d9c  jmp     loc_1800272F7
0x180026da1  mov     rax, [rdi]
0x180026da4  mov     r8d, [rdi+38h]
0x180026da8  lea     rdx, [rsp+0E8h+sourceString]
0x180026dad  mov     rcx, rdi
0x180026db0  mov     rax, [rax+70h]
0x180026db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026db9  nop
0x180026dba  lea     rbx, [rsp+0E8h+sourceString]
0x180026dbf  cmp     [rsp+0E8h+var_68], 8
0x180026dc8  cmovnb  rbx, [rsp+0E8h+sourceString]
0x180026dce  mov     [rsp+0E8h+length], r15d
0x180026dd3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026dd7  inc     rcx; unsigned __int64
0x180026dda  cmp     [rbx+rcx*2], r15w
0x180026ddf  jnz     short loc_180026DD7
0x180026de1  lea     rdx, [rsp+0E8h+length]; unsigned int *
0x180026de6  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180026deb  test    eax, eax
0x180026ded  jns     short loc_180026E0A
0x180026def  xor     r9d, r9d; lpArguments
0x180026df2  xor     r8d, r8d; nNumberOfArguments
0x180026df5  lea     edx, [r9+1]; dwExceptionFlags
0x180026df9  mov     ecx, 0C000000Dh; dwExceptionCode
0x180026dfe  call    cs:__imp_RaiseException
0x180026e05  nop     dword ptr [rax+rax+00h]
0x180026e0a  lea     r9, [rsp+0E8h+string]; string
0x180026e12  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x180026e1a  mov     edx, [rsp+0E8h+length]; length
0x180026e1e  mov     rcx, rbx; sourceString
0x180026e21  call    cs:__imp_WindowsCreateStringReference
0x180026e28  nop     dword ptr [rax+rax+00h]
0x180026e2d  mov     rcx, [rsp+0E8h+var_C0]
0x180026e32  mov     rax, [rcx]
0x180026e35  mov     rdx, [rsp+0E8h+string]
0x180026e3d  mov     rax, [rax+58h]
0x180026e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e46  mov     ebx, eax
0x180026e48  test    eax, eax
0x180026e4a  jns     loc_180026ED1
0x180026e50  mov     rcx, [rsp+0E8h]; this
0x180026e58  mov     r9d, eax; char *
0x180026e5b  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026e62  mov     edx, 121h; void *
0x180026e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e6c  nop
0x180026e6d  xor     r8d, r8d
0x180026e70  mov     dl, 1
0x180026e72  lea     rcx, [rsp+0E8h+sourceString]
0x180026e77  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026e7c  nop
0x180026e7d  lea     rcx, [rsp+0E8h+var_C0]
0x180026e82  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026e87  nop
0x180026e88  test    rsi, rsi
0x180026e8b  jz      short loc_180026E9D
0x180026e8d  mov     rax, [rsi]
0x180026e90  mov     rcx, rsi
0x180026e93  mov     rax, [rax+10h]
0x180026e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e9c  nop
0x180026e9d  lea     rcx, [rsp+0E8h+var_B8]
0x180026ea2  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026ea7  nop
0x180026ea8  lea     rcx, [rsp+0E8h+var_C8]
0x180026ead  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026eb2  nop
0x180026eb3  lea     rcx, [rsp+0E8h+var_A0]
0x180026eb8  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180026ebd  nop
0x180026ebe  call    cs:__imp_RoUninitialize
0x180026ec5  nop     dword ptr [rax+rax+00h]
0x180026eca  mov     eax, ebx
0x180026ecc  jmp     loc_1800272F7
0x180026ed1  mov     rdi, [rsp+0E8h+var_C0]
0x180026ed6  mov     rax, [rdi]
0x180026ed9  mov     rbx, [rax+40h]
0x180026edd  lea     rcx, [rsp+0E8h+var_C8]
0x180026ee2  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026ee7  lea     r8, [rsp+0E8h+var_C8]
0x180026eec  mov     edx, r14d
0x180026eef  mov     rcx, rdi
0x180026ef2  mov     rax, rbx
0x180026ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026efa  mov     ebx, eax
0x180026efc  test    eax, eax
0x180026efe  jns     loc_180026F85
0x180026f04  mov     rcx, [rsp+0E8h]; this
0x180026f0c  mov     r9d, eax; char *
0x180026f0f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026f16  mov     edx, 124h; void *
0x180026f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f20  nop
0x180026f21  xor     r8d, r8d
0x180026f24  mov     dl, 1
0x180026f26  lea     rcx, [rsp+0E8h+sourceString]
0x180026f2b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026f30  nop
0x180026f31  lea     rcx, [rsp+0E8h+var_C0]
0x180026f36  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026f3b  nop
0x180026f3c  test    rsi, rsi
0x180026f3f  jz      short loc_180026F51
0x180026f41  mov     rax, [rsi]
0x180026f44  mov     rcx, rsi
0x180026f47  mov     rax, [rax+10h]
0x180026f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f50  nop
0x180026f51  lea     rcx, [rsp+0E8h+var_B8]
0x180026f56  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026f5b  nop
0x180026f5c  lea     rcx, [rsp+0E8h+var_C8]
0x180026f61  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026f66  nop
0x180026f67  lea     rcx, [rsp+0E8h+var_A0]
0x180026f6c  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180026f71  nop
0x180026f72  call    cs:__imp_RoUninitialize
0x180026f79  nop     dword ptr [rax+rax+00h]
0x180026f7e  mov     eax, ebx
0x180026f80  jmp     loc_1800272F7
0x180026f85  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x180026f8a  mov     rax, [rcx]
0x180026f8d  mov     rdx, rsi
0x180026f90  mov     rax, [rax+30h]
0x180026f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f99  mov     ebx, eax
0x180026f9b  test    eax, eax
0x180026f9d  jns     loc_180027024
0x180026fa3  mov     rcx, [rsp+0E8h]; this
0x180026fab  mov     r9d, eax; char *
0x180026fae  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026fb5  mov     edx, 127h; void *
0x180026fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026fbf  nop
0x180026fc0  xor     r8d, r8d
0x180026fc3  mov     dl, 1
0x180026fc5  lea     rcx, [rsp+0E8h+sourceString]
0x180026fca  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026fcf  nop
0x180026fd0  lea     rcx, [rsp+0E8h+var_C0]
0x180026fd5  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026fda  nop
0x180026fdb  test    rsi, rsi
0x180026fde  jz      short loc_180026FF0
0x180026fe0  mov     rax, [rsi]
0x180026fe3  mov     rcx, rsi
0x180026fe6  mov     rax, [rax+10h]
0x180026fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fef  nop
0x180026ff0  lea     rcx, [rsp+0E8h+var_B8]
0x180026ff5  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026ffa  nop
0x180026ffb  lea     rcx, [rsp+0E8h+var_C8]
0x180027000  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180027005  nop
0x180027006  lea     rcx, [rsp+0E8h+var_A0]
0x18002700b  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180027010  nop
0x180027011  call    cs:__imp_RoUninitialize
0x180027018  nop     dword ptr [rax+rax+00h]
0x18002701d  mov     eax, ebx
0x18002701f  jmp     loc_1800272F7
0x180027024  lea     rdx, [rsp+0E8h+var_B8]
  ... truncated ...
```
