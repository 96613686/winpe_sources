# PluginEngine::RemoveProvisioning(ProvPackageInfo const &)

- ea: `0x180026280`
- end: `0x180026b59`
- name: `?RemoveProvisioning@PluginEngine@@UEAAJAEBVProvPackageInfo@@@Z`
- size: `2265`
- prototype: `__int64 __fastcall(PluginEngine *__hidden this, const struct ProvPackageInfo *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000334c`
- `0x1800067fc`
- `0x1800087ec`
- `0x18000b46c`
- `0x18000f534`
- `0x18001e560`
- `0x18001fbfc`
- `0x18001ff18`
- `0x18001ffe0`
- `0x1800247cc`
- `0x180024840`
- `0x180024898`
- `0x180024918`
- `0x1800249c0`
- `0x180024a10`
- `0x180024d00`
- `0x180026280`
- `0x180028168`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026515`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026515`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180026385`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180026385`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002649c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800265d8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800266ef`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800267ac`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026864`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002691a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800269de`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026a98`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026b1a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002649c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800265d8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800266ef`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800267ac`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026864`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002691a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800269de`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026a98`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180026b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026538`

## string_xrefs

- `0x180026344`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800263a2`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026449`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026572`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002666e`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002672b`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800267e3`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026899`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002695d`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180026a17`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800262be`: `/delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall PluginEngine::RemoveProvisioning(PluginEngine *this, const struct ProvPackageInfo *a2)
{
  __int64 PackageId; // rax
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z; // rax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  const WCHAR *v19; // rbx
  unsigned __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, int *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rdx
  int v45[2]; // [rsp+20h] [rbp-108h] BYREF
  __int64 v46; // [rsp+28h] [rbp-100h] BYREF
  __int64 v47; // [rsp+30h] [rbp-F8h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-F0h] BYREF
  int v49; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v50[24]; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v51; // [rsp+60h] [rbp-C8h]
  _BYTE v52[24]; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+80h] [rbp-A8h]
  PCWSTR sourceString[4]; // [rsp+88h] [rbp-A0h] BYREF
  _QWORD v55[4]; // [rsp+A8h] [rbp-80h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-58h] BYREF
  HSTRING v58; // [rsp+E8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  if ( (unsigned __int8)IsShellExecuteExWPresent() )
  {
    std::wstring::wstring(v52, L"/delete");
    std::wstring::append(v52, L" ");
    PackageId = ProvPackageInfo::GetPackageId(a2, &string);
    std::wstring::append(v52, PackageId, 0, -1);
    LOBYTE(v5) = 1;
    std::wstring::_Tidy(&string, v5, 0);
    v6 = (*(__int64 (__fastcall **)(PluginEngine *, _BYTE *, __int64))(*(_QWORD *)this + 104LL))(this, v52, 600000);
    v8 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v6,
        v45[0]);
      LOBYTE(v9) = 1;
      std::wstring::_Tidy(v52, v9, 0);
      return v8;
    }
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v52, v7, 0);
    return 0;
  }
  v11 = RoInitialize(1);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v11,
      v45[0]);
    return v12;
  }
  v50[17] = 1;
  length[0] = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v50,
    length);
  v47 = 0;
  V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = (__int64 *)___Make_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(length, v50);
  v15 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  v51 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = 0;
  v16 = *(_QWORD *)length;
  if ( *(_QWORD *)length )
  {
    *(_QWORD *)length = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  *(_QWORD *)v45 = 0;
  Windows::Internal::StringReference::StringReference(&v58, (const unsigned __int16 (*)[47])v14);
  v46 = 0;
  v17 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(
          v58,
          &v46);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v17,
      v45[0]);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_48;
  }
  (*(void (__fastcall **)(PluginEngine *, PCWSTR *, _QWORD))(*(_QWORD *)this + 112LL))(
    this,
    sourceString,
    *((unsigned int *)this + 14));
  v19 = (const WCHAR *)sourceString;
  if ( sourceString[3] >= (PCWSTR)8 )
    v19 = sourceString[0];
  length[0] = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  if ( (int)ULongLongToUInt(v20, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(v19, length[0], &hstringHeader, &string);
  v21 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v46 + 88LL))(v46, string);
  v18 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v21,
      v45[0]);
    LOBYTE(v22) = 1;
    std::wstring::_Tidy(sourceString, v22, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_48;
  }
  ProvPackageInfo::GetPackageId(a2, v55);
  v23 = v55;
  if ( v55[3] >= 8u )
    v23 = (_QWORD *)v55[0];
  *(_QWORD *)length = v23;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v52, length);
  v24 = v46;
  v25 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v46 + 56LL);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
  v26 = v25(v24, v53, v45);
  v18 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v26,
      v45[0]);
    v53 = 0;
    LOBYTE(v27) = 1;
    std::wstring::_Tidy(v55, v27, 0);
    LOBYTE(v28) = 1;
    std::wstring::_Tidy(sourceString, v28, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_48;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v45 + 48LL))(*(_QWORD *)v45, v15);
  v18 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v29,
      v45[0]);
    v53 = 0;
    LOBYTE(v30) = 1;
    std::wstring::_Tidy(v55, v30, 0);
    LOBYTE(v31) = 1;
    std::wstring::_Tidy(sourceString, v31, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_48;
  }
  v32 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<unsigned int>>::As<IAsyncInfo>(v45, &v47);
  v18 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v32,
      v45[0]);
    v53 = 0;
    LOBYTE(v33) = 1;
    std::wstring::_Tidy(v55, v33, 0);
    LOBYTE(v34) = 1;
    std::wstring::_Tidy(sourceString, v34, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_48;
  }
  if ( (unsigned __int8)_wait___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(v50) )
  {
    v49 = 0;
    v37 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v45 + 64LL))(*(_QWORD *)v45, &v49);
    v18 = v37;
    if ( v37 >= 0 )
    {
      v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 80LL))(v47);
      v18 = v40;
      if ( v40 >= 0 )
      {
        v53 = 0;
        LOBYTE(v41) = 1;
        std::wstring::_Tidy(v55, v41, 0);
        LOBYTE(v44) = 1;
        std::wstring::_Tidy(sourceString, v44, 0);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v47);
        __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v50);
        RoUninitialize();
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v40,
        v45[0]);
      v53 = 0;
      LOBYTE(v42) = 1;
      std::wstring::_Tidy(v55, v42, 0);
      LOBYTE(v43) = 1;
      std::wstring::_Tidy(sourceString, v43, 0);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v37,
        v45[0]);
      v53 = 0;
      LOBYTE(v38) = 1;
      std::wstring::_Tidy(v55, v38, 0);
      LOBYTE(v39) = 1;
      std::wstring::_Tidy(sourceString, v39, 0);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
LABEL_48:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v47);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v50);
    RoUninitialize();
    return v18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A7,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)0x800705B4LL,
    v45[0]);
  v53 = 0;
  LOBYTE(v35) = 1;
  std::wstring::_Tidy(v55, v35, 0);
  LOBYTE(v36) = 1;
  std::wstring::_Tidy(sourceString, v36, 0);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v45);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v47);
  __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v50);
  RoUninitialize();
  return 2147943860LL;
}

```

## disassembly

```asm
0x180026280  mov     [rsp+arg_10], rbx
0x180026285  mov     [rsp+arg_18], rsi
0x18002628a  push    rdi
0x18002628b  push    r14
0x18002628d  push    r15
0x18002628f  sub     rsp, 110h
0x180026296  mov     rax, cs:__security_cookie
0x18002629d  xor     rax, rsp
0x1800262a0  mov     [rsp+128h+var_20], rax
0x1800262a8  mov     r14, rdx
0x1800262ab  mov     rdi, rcx
0x1800262ae  call    IsShellExecuteExWPresent
0x1800262b3  xor     r15d, r15d
0x1800262b6  test    al, al
0x1800262b8  jz      loc_180026380
0x1800262be  lea     rdx, aDelete; "/delete"
0x1800262c5  lea     rcx, [rsp+128h+var_C0]
0x1800262ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800262cf  nop
0x1800262d0  lea     rdx, asc_180034B44; " "
0x1800262d7  lea     rcx, [rsp+128h+var_C0]
0x1800262dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800262e1  lea     rdx, [rsp+128h+string]
0x1800262e9  mov     rcx, r14
0x1800262ec  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x1800262f1  nop
0x1800262f2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800262f6  xor     r8d, r8d
0x1800262f9  mov     rdx, rax
0x1800262fc  lea     rcx, [rsp+128h+var_C0]
0x180026301  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180026306  nop
0x180026307  xor     r8d, r8d
0x18002630a  mov     dl, 1
0x18002630c  lea     rcx, [rsp+128h+string]
0x180026314  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026319  mov     rax, [rdi]
0x18002631c  mov     r8d, 927C0h
0x180026322  lea     rdx, [rsp+128h+var_C0]
0x180026327  mov     rcx, rdi
0x18002632a  mov     rax, [rax+68h]
0x18002632e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026333  mov     ebx, eax
0x180026335  test    eax, eax
0x180026337  jns     short loc_18002636C
0x180026339  mov     rcx, [rsp+128h]; this
0x180026341  mov     r9d, eax; char *
0x180026344  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002634b  mov     edx, 187h; void *
0x180026350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026355  nop
0x180026356  xor     r8d, r8d
0x180026359  mov     dl, 1
0x18002635b  lea     rcx, [rsp+128h+var_C0]
0x180026360  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026365  mov     eax, ebx
0x180026367  jmp     loc_180026B2F
0x18002636c  xor     r8d, r8d
0x18002636f  mov     dl, 1
0x180026371  lea     rcx, [rsp+128h+var_C0]
0x180026376  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002637b  jmp     loc_180026B27
0x180026380  mov     ecx, 1
0x180026385  call    cs:__imp_RoInitialize
0x18002638c  nop     dword ptr [rax+rax+00h]
0x180026391  mov     ebx, eax
0x180026393  test    eax, eax
0x180026395  jns     short loc_1800263BA
0x180026397  mov     rcx, [rsp+128h]; this
0x18002639f  mov     r9d, eax; char *
0x1800263a2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800263a9  mov     edx, 18Bh; void *
0x1800263ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263b3  mov     eax, ebx
0x1800263b5  jmp     loc_180026B2F
0x1800263ba  mov     [rsp+128h+var_CF], 1
0x1800263bf  mov     [rsp+128h+length], r15d
0x1800263c4  lea     rdx, [rsp+128h+length]
0x1800263c9  lea     rcx, [rsp+128h+var_E0]
0x1800263ce  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800263d3  nop
0x1800263d4  mov     [rsp+128h+var_F8], r15
0x1800263d9  lea     rdx, [rsp+128h+var_E0]
0x1800263de  lea     rcx, [rsp+128h+length]
0x1800263e3  call    ??$Make@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@12@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x1800263e8  mov     rsi, [rax]
0x1800263eb  mov     [rsp+128h+var_C8], rsi
0x1800263f0  mov     [rax], r15
0x1800263f3  mov     rcx, qword ptr [rsp+128h+length]
0x1800263f8  test    rcx, rcx
0x1800263fb  jz      short loc_18002640F
0x1800263fd  mov     qword ptr [rsp+128h+length], r15
0x180026402  mov     rax, [rcx]
0x180026405  mov     rax, [rax+10h]
0x180026409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002640e  nop
0x18002640f  mov     qword ptr [rsp+128h+var_108], r15; int
0x180026414  lea     rcx, [rsp+128h+var_40]; string
0x18002641c  call    ??$?0$0CP@@StringReference@Internal@Windows@@QEAA@AEAY0CP@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[47])
0x180026421  mov     [rsp+128h+var_100], r15
0x180026426  lea     rdx, [rsp+128h+var_100]
0x18002642b  mov     rcx, [rsp+128h+var_40]
0x180026433  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>)
0x180026438  mov     ebx, eax
0x18002643a  test    eax, eax
0x18002643c  jns     short loc_1800264AF
0x18002643e  mov     rcx, [rsp+128h]; this
0x180026446  mov     r9d, eax; char *
0x180026449  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026450  mov     edx, 199h; void *
0x180026455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002645a  nop
0x18002645b  lea     rcx, [rsp+128h+var_100]
0x180026460  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026465  nop
0x180026466  lea     rcx, [rsp+128h+var_108]
0x18002646b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026470  nop
0x180026471  test    rsi, rsi
0x180026474  jz      short loc_180026486
0x180026476  mov     rax, [rsi]
0x180026479  mov     rcx, rsi
0x18002647c  mov     rax, [rax+10h]
0x180026480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026485  nop
0x180026486  lea     rcx, [rsp+128h+var_F8]
0x18002648b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026490  nop
0x180026491  lea     rcx, [rsp+128h+var_E0]
0x180026496  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x18002649b  nop
0x18002649c  call    cs:__imp_RoUninitialize
0x1800264a3  nop     dword ptr [rax+rax+00h]
0x1800264a8  mov     eax, ebx
0x1800264aa  jmp     loc_180026B2F
0x1800264af  mov     rax, [rdi]
0x1800264b2  mov     r8d, [rdi+38h]
0x1800264b6  lea     rdx, [rsp+128h+sourceString]
0x1800264be  mov     rcx, rdi
0x1800264c1  mov     rax, [rax+70h]
0x1800264c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ca  nop
0x1800264cb  lea     rbx, [rsp+128h+sourceString]
0x1800264d3  cmp     [rsp+128h+var_88], 8
0x1800264dc  cmovnb  rbx, [rsp+128h+sourceString]
0x1800264e5  mov     [rsp+128h+length], r15d
0x1800264ea  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800264ee  inc     rcx; unsigned __int64
0x1800264f1  cmp     [rbx+rcx*2], r15w
0x1800264f6  jnz     short loc_1800264EE
0x1800264f8  lea     rdx, [rsp+128h+length]; unsigned int *
0x1800264fd  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180026502  test    eax, eax
0x180026504  jns     short loc_180026521
0x180026506  xor     r9d, r9d; lpArguments
0x180026509  xor     r8d, r8d; nNumberOfArguments
0x18002650c  lea     edx, [r9+1]; dwExceptionFlags
0x180026510  mov     ecx, 0C000000Dh; dwExceptionCode
0x180026515  call    cs:__imp_RaiseException
0x18002651c  nop     dword ptr [rax+rax+00h]
0x180026521  lea     r9, [rsp+128h+string]; string
0x180026529  lea     r8, [rsp+128h+hstringHeader]; hstringHeader
0x180026531  mov     edx, [rsp+128h+length]; length
0x180026535  mov     rcx, rbx; sourceString
0x180026538  call    cs:__imp_WindowsCreateStringReference
0x18002653f  nop     dword ptr [rax+rax+00h]
0x180026544  mov     rcx, [rsp+128h+var_100]
0x180026549  mov     rax, [rcx]
0x18002654c  mov     rdx, [rsp+128h+string]
0x180026554  mov     rax, [rax+58h]
0x180026558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002655d  mov     ebx, eax
0x18002655f  test    eax, eax
0x180026561  jns     loc_1800265EB
0x180026567  mov     rcx, [rsp+128h]; this
0x18002656f  mov     r9d, eax; char *
0x180026572  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026579  mov     edx, 19Dh; void *
0x18002657e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026583  nop
0x180026584  xor     r8d, r8d
0x180026587  mov     dl, 1
0x180026589  lea     rcx, [rsp+128h+sourceString]
0x180026591  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026596  nop
0x180026597  lea     rcx, [rsp+128h+var_100]
0x18002659c  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800265a1  nop
0x1800265a2  lea     rcx, [rsp+128h+var_108]
0x1800265a7  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800265ac  nop
0x1800265ad  test    rsi, rsi
0x1800265b0  jz      short loc_1800265C2
0x1800265b2  mov     rax, [rsi]
0x1800265b5  mov     rcx, rsi
0x1800265b8  mov     rax, [rax+10h]
0x1800265bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265c1  nop
0x1800265c2  lea     rcx, [rsp+128h+var_F8]
0x1800265c7  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800265cc  nop
0x1800265cd  lea     rcx, [rsp+128h+var_E0]
0x1800265d2  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800265d7  nop
0x1800265d8  call    cs:__imp_RoUninitialize
0x1800265df  nop     dword ptr [rax+rax+00h]
0x1800265e4  mov     eax, ebx
0x1800265e6  jmp     loc_180026B2F
0x1800265eb  lea     rdx, [rsp+128h+var_80]
0x1800265f3  mov     rcx, r14
0x1800265f6  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x1800265fb  nop
0x1800265fc  lea     rax, [rsp+128h+var_80]
0x180026604  cmp     [rsp+128h+var_68], 8
0x18002660d  cmovnb  rax, [rsp+128h+var_80]
0x180026616  mov     qword ptr [rsp+128h+length], rax
0x18002661b  lea     rdx, [rsp+128h+length]
0x180026620  lea     rcx, [rsp+128h+var_C0]
0x180026625  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002662a  nop
0x18002662b  mov     rdi, [rsp+128h+var_100]
0x180026630  mov     rax, [rdi]
0x180026633  mov     rbx, [rax+38h]
0x180026637  lea     rcx, [rsp+128h+var_108]
0x18002663c  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180026641  lea     r8, [rsp+128h+var_108]
0x180026646  mov     rdx, [rsp+128h+var_A8]
0x18002664e  mov     rcx, rdi
0x180026651  mov     rax, rbx
0x180026654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026659  mov     ebx, eax
0x18002665b  test    eax, eax
0x18002665d  jns     loc_180026702
0x180026663  mov     rcx, [rsp+128h]; this
0x18002666b  mov     r9d, eax; char *
0x18002666e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026675  mov     edx, 1A2h; void *
0x18002667a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002667f  nop
0x180026680  mov     [rsp+128h+var_A8], r15
0x180026688  xor     r8d, r8d
0x18002668b  mov     dl, 1
0x18002668d  lea     rcx, [rsp+128h+var_80]
0x180026695  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002669a  nop
0x18002669b  xor     r8d, r8d
0x18002669e  mov     dl, 1
0x1800266a0  lea     rcx, [rsp+128h+sourceString]
0x1800266a8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800266ad  nop
0x1800266ae  lea     rcx, [rsp+128h+var_100]
0x1800266b3  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800266b8  nop
0x1800266b9  lea     rcx, [rsp+128h+var_108]
0x1800266be  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800266c3  nop
0x1800266c4  test    rsi, rsi
0x1800266c7  jz      short loc_1800266D9
0x1800266c9  mov     rax, [rsi]
0x1800266cc  mov     rcx, rsi
0x1800266cf  mov     rax, [rax+10h]
0x1800266d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266d8  nop
0x1800266d9  lea     rcx, [rsp+128h+var_F8]
0x1800266de  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800266e3  nop
0x1800266e4  lea     rcx, [rsp+128h+var_E0]
0x1800266e9  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800266ee  nop
0x1800266ef  call    cs:__imp_RoUninitialize
0x1800266f6  nop     dword ptr [rax+rax+00h]
0x1800266fb  mov     eax, ebx
0x1800266fd  jmp     loc_180026B2F
0x180026702  mov     rcx, qword ptr [rsp+128h+var_108]
0x180026707  mov     rax, [rcx]
0x18002670a  mov     rdx, rsi
0x18002670d  mov     rax, [rax+30h]
0x180026711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026716  mov     ebx, eax
0x180026718  test    eax, eax
0x18002671a  jns     loc_1800267BF
0x180026720  mov     rcx, [rsp+128h]; this
0x180026728  mov     r9d, eax; char *
0x18002672b  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180026732  mov     edx, 1A5h; void *
0x180026737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002673c  nop
0x18002673d  mov     [rsp+128h+var_A8], r15
0x180026745  xor     r8d, r8d
0x180026748  mov     dl, 1
0x18002674a  lea     rcx, [rsp+128h+var_80]
0x180026752  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026757  nop
0x180026758  xor     r8d, r8d
0x18002675b  mov     dl, 1
0x18002675d  lea     rcx, [rsp+128h+sourceString]
0x180026765  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002676a  nop
0x18002676b  lea     rcx, [rsp+128h+var_100]
0x180026770  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
  ... truncated ...
```
