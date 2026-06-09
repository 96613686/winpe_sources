# PluginEngine::ApplyProvisioning(ProvPackageInfo const &,Windows::Management::Provisioning::ProvisioningTurn)

- ea: `0x180024f40`
- end: `0x180025840`
- name: `?ApplyProvisioning@PluginEngine@@UEAAJAEBVProvPackageInfo@@W4ProvisioningTurn@Provisioning@Management@Windows@@@Z`
- size: `2304`
- prototype: `int __high(const struct ProvPackageInfo *, enum Windows::Management::Provisioning::ProvisioningTurn)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000334c`
- `0x1800067fc`
- `0x1800087ec`
- `0x18000b46c`
- `0x18001e560`
- `0x18001fbfc`
- `0x18001ff18`
- `0x18001ffe0`
- `0x18002481c`
- `0x180024840`
- `0x180024898`
- `0x180024918`
- `0x1800249c0`
- `0x180024a10`
- `0x180024d00`
- `0x180024f40`
- `0x1800280f4`
- `0x180028168`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025246`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025269`

## string_xrefs

- `0x1800250be`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180025184`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002529f`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800253af`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002545f`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002550a`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800255b3`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002566a`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180025717`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall PluginEngine::ApplyProvisioning(unsigned int *a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 PackagePath; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z; // rax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rsi
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  const WCHAR *v24; // rdi
  unsigned __int64 v25; // rbx
  int v26; // eax
  __int64 v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, UINT32 *, __int64); // rbx
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  int v51; // [rsp+20h] [rbp-158h]
  __int64 v52; // [rsp+40h] [rbp-138h] BYREF
  __int64 v53; // [rsp+48h] [rbp-130h] BYREF
  __int64 v54; // [rsp+50h] [rbp-128h] BYREF
  int v55; // [rsp+58h] [rbp-120h] BYREF
  UINT32 length[4]; // [rsp+60h] [rbp-118h] BYREF
  __int64 v57; // [rsp+70h] [rbp-108h]
  _WORD v58[8]; // [rsp+78h] [rbp-100h] BYREF
  __int64 v59; // [rsp+88h] [rbp-F0h]
  __int64 v60; // [rsp+90h] [rbp-E8h]
  PCWSTR sourceString[4]; // [rsp+98h] [rbp-E0h] BYREF
  _QWORD v62[4]; // [rsp+B8h] [rbp-C0h] BYREF
  _BYTE v63[24]; // [rsp+D8h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+F0h] [rbp-88h]
  HSTRING string; // [rsp+F8h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp-78h] BYREF
  HSTRING v67; // [rsp+118h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  if ( (unsigned __int8)IsShellExecuteExWPresent() )
  {
    v60 = 7;
    v59 = 0;
    v58[0] = 0;
    v6 = *(_QWORD *)(ProvPackageInfo::GetPackagePath(a2, &string) + 16);
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(&string, v7, 0);
    if ( v6 )
    {
      std::wstring::append(v58, L"/add ");
      std::wstring::append(v58, L"\"");
      PackagePath = ProvPackageInfo::GetPackagePath(a2, &string);
      std::wstring::append(v58, PackagePath, 0, -1);
      LOBYTE(v9) = 1;
      std::wstring::_Tidy(&string, v9, 0);
      std::wstring::append(v58, L"\"");
    }
    std::wstring::append(v58, L" /turn ");
    v10 = std::to_wstring(&string, a3);
    std::wstring::append(v58, v10, 0, -1);
    LOBYTE(v11) = 1;
    std::wstring::_Tidy(&string, v11, 0);
    v12 = 1800000;
    if ( a3 != 3 )
      v12 = 600000;
    v13 = (*(__int64 (__fastcall **)(unsigned int *, _WORD *, __int64))(*(_QWORD *)a1 + 104LL))(a1, v58, v12);
    v15 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v13,
        v51);
      LOBYTE(v16) = 1;
      std::wstring::_Tidy(v58, v16, 0);
      return v15;
    }
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v58, v14, 0);
    return 0;
  }
  length[0] = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v58,
    length);
  v52 = 0;
  v54 = 0;
  V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = (__int64 *)___Make_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(length, v58);
  v20 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  v57 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = 0;
  v21 = *(_QWORD *)length;
  if ( *(_QWORD *)length )
  {
    *(_QWORD *)length = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  Windows::Internal::StringReference::StringReference(&v67, (const unsigned __int16 (*)[47])v19);
  v53 = 0;
  v22 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(
          v67,
          &v53);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v22,
      v51);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_14:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v52);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v58);
    return v23;
  }
  (*(void (__fastcall **)(unsigned int *, PCWSTR *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, sourceString, a1[14]);
  v24 = (const WCHAR *)sourceString;
  if ( sourceString[3] >= (PCWSTR)8 )
    v24 = sourceString[0];
  length[0] = 0;
  v25 = -1;
  do
    ++v25;
  while ( v24[v25] );
  if ( (int)ULongLongToUInt(v25, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(v24, length[0], &hstringHeader, &string);
  v26 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v53 + 88LL))(v53, string);
  v23 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v26,
      v51);
    LOBYTE(v27) = 1;
    std::wstring::_Tidy(sourceString, v27, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_14;
  }
  ProvPackageInfo::GetPackagePath(a2, v62);
  v28 = v62;
  if ( v62[3] >= 8u )
    v28 = (_QWORD *)v62[0];
  *(_QWORD *)length = v28;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v63, length);
  v29 = v53;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, UINT32 *, __int64))(*(_QWORD *)v53 + 48LL);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v52);
  *(_OWORD *)length = 0;
  v31 = v30(v29, v64, length, 1);
  v32 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v31,
      a3);
    v64 = 0;
    LOBYTE(v33) = 1;
    std::wstring::_Tidy(v62, v33, 0);
    LOBYTE(v34) = 1;
    std::wstring::_Tidy(sourceString, v34, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_50;
  }
  v35 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 48LL))(v52, v20);
  v32 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v35,
      a3);
    v64 = 0;
    LOBYTE(v36) = 1;
    std::wstring::_Tidy(v62, v36, 0);
    LOBYTE(v37) = 1;
    std::wstring::_Tidy(sourceString, v37, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_50;
  }
  v38 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<unsigned int>>::As<IAsyncInfo>(&v52, &v54);
  v32 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v38,
      a3);
    v64 = 0;
    LOBYTE(v39) = 1;
    std::wstring::_Tidy(v62, v39, 0);
    LOBYTE(v40) = 1;
    std::wstring::_Tidy(sourceString, v40, 0);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_50;
  }
  if ( (unsigned __int8)_wait___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(v58) )
  {
    v55 = 0;
    v43 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 64LL))(v52, &v55);
    v32 = v43;
    if ( v43 >= 0 )
    {
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 80LL))(v54);
      v32 = v46;
      if ( v46 >= 0 )
      {
        v64 = 0;
        LOBYTE(v47) = 1;
        std::wstring::_Tidy(v62, v47, 0);
        LOBYTE(v50) = 1;
        std::wstring::_Tidy(sourceString, v50, 0);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v54);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v52);
        __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v58);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v46,
        a3);
      v64 = 0;
      LOBYTE(v48) = 1;
      std::wstring::_Tidy(v62, v48, 0);
      LOBYTE(v49) = 1;
      std::wstring::_Tidy(sourceString, v49, 0);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v43,
        a3);
      v64 = 0;
      LOBYTE(v44) = 1;
      std::wstring::_Tidy(v62, v44, 0);
      LOBYTE(v45) = 1;
      std::wstring::_Tidy(sourceString, v45, 0);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
LABEL_50:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v52);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v58);
    return v32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16F,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)0x800705B4LL,
    a3);
  v64 = 0;
  LOBYTE(v41) = 1;
  std::wstring::_Tidy(v62, v41, 0);
  LOBYTE(v42) = 1;
  std::wstring::_Tidy(sourceString, v42, 0);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v53);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v52);
  __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v58);
  return 2147943860LL;
}

```

## disassembly

```asm
0x180024f40  mov     rax, rsp
0x180024f43  mov     [rax+20h], rbx
0x180024f47  push    rsi
0x180024f48  push    rdi
0x180024f49  push    r12
0x180024f4b  push    r14
0x180024f4d  push    r15
0x180024f4f  sub     rsp, 150h
0x180024f56  movaps  xmmword ptr [rax-38h], xmm6
0x180024f5a  mov     rax, cs:__security_cookie
0x180024f61  xor     rax, rsp
0x180024f64  mov     [rsp+178h+var_40], rax
0x180024f6c  mov     r15d, r8d
0x180024f6f  mov     r14, rdx
0x180024f72  mov     rdi, rcx
0x180024f75  call    IsShellExecuteExWPresent
0x180024f7a  xor     r12d, r12d
0x180024f7d  test    al, al
0x180024f7f  jz      loc_1800250FA
0x180024f85  mov     [rsp+178h+var_E8], 7
0x180024f91  mov     [rsp+178h+var_F0], r12
0x180024f99  mov     [rsp+178h+var_100], r12w
0x180024f9f  lea     rdx, [rsp+178h+string]
0x180024fa7  mov     rcx, r14
0x180024faa  call    ?GetPackagePath@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackagePath(void)
0x180024faf  mov     rbx, [rax+10h]
0x180024fb3  xor     r8d, r8d
0x180024fb6  mov     dl, 1
0x180024fb8  lea     rcx, [rsp+178h+string]
0x180024fc0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180024fc5  test    rbx, rbx
0x180024fc8  jz      short loc_18002503A
0x180024fca  lea     rdx, aAdd; "/add "
0x180024fd1  lea     rcx, [rsp+178h+var_100]
0x180024fd6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180024fdb  lea     rdx, asc_180035CA4; "\""
0x180024fe2  lea     rcx, [rsp+178h+var_100]
0x180024fe7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180024fec  lea     rdx, [rsp+178h+string]
0x180024ff4  mov     rcx, r14
0x180024ff7  call    ?GetPackagePath@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackagePath(void)
0x180024ffc  nop
0x180024ffd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025001  mov     r9, rbx
0x180025004  xor     r8d, r8d
0x180025007  mov     rdx, rax
0x18002500a  lea     rcx, [rsp+178h+var_100]
0x18002500f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180025014  nop
0x180025015  xor     r8d, r8d
0x180025018  mov     dl, 1
0x18002501a  lea     rcx, [rsp+178h+string]
0x180025022  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025027  lea     rdx, asc_180035CA4; "\""
0x18002502e  lea     rcx, [rsp+178h+var_100]
0x180025033  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180025038  jmp     short loc_18002503E
0x18002503a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002503e  lea     rdx, aTurn_0; " /turn "
0x180025045  lea     rcx, [rsp+178h+var_100]
0x18002504a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18002504f  mov     edx, r15d
0x180025052  lea     rcx, [rsp+178h+string]
0x18002505a  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18002505f  nop
0x180025060  mov     r9, rbx
0x180025063  xor     r8d, r8d
0x180025066  mov     rdx, rax
0x180025069  lea     rcx, [rsp+178h+var_100]
0x18002506e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180025073  nop
0x180025074  xor     r8d, r8d
0x180025077  mov     dl, 1
0x180025079  lea     rcx, [rsp+178h+string]
0x180025081  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025086  mov     rax, [rdi]
0x180025089  mov     ecx, 927C0h
0x18002508e  mov     r8d, 1B7740h
0x180025094  cmp     r15d, 3
0x180025098  cmovnz  r8d, ecx
0x18002509c  lea     rdx, [rsp+178h+var_100]
0x1800250a1  mov     rcx, rdi
0x1800250a4  mov     rax, [rax+68h]
0x1800250a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250ad  mov     ebx, eax
0x1800250af  test    eax, eax
0x1800250b1  jns     short loc_1800250E6
0x1800250b3  mov     rcx, [rsp+178h]; this
0x1800250bb  mov     r9d, eax; char *
0x1800250be  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800250c5  mov     edx, 153h; void *
0x1800250ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800250cf  nop
0x1800250d0  xor     r8d, r8d
0x1800250d3  mov     dl, 1
0x1800250d5  lea     rcx, [rsp+178h+var_100]
0x1800250da  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800250df  mov     eax, ebx
0x1800250e1  jmp     loc_180025812
0x1800250e6  xor     r8d, r8d
0x1800250e9  mov     dl, 1
0x1800250eb  lea     rcx, [rsp+178h+var_100]
0x1800250f0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800250f5  jmp     loc_18002580A
0x1800250fa  mov     [rsp+178h+length], r12d
0x1800250ff  lea     rdx, [rsp+178h+length]
0x180025104  lea     rcx, [rsp+178h+var_100]
0x180025109  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18002510e  nop
0x18002510f  mov     [rsp+178h+var_138], r12
0x180025114  mov     [rsp+178h+var_128], r12
0x180025119  lea     rdx, [rsp+178h+var_100]
0x18002511e  lea     rcx, [rsp+178h+length]
0x180025123  call    ??$Make@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@12@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x180025128  mov     rsi, [rax]
0x18002512b  mov     [rsp+178h+var_108], rsi
0x180025130  mov     [rax], r12
0x180025133  mov     rcx, qword ptr [rsp+178h+length]
0x180025138  test    rcx, rcx
0x18002513b  jz      short loc_18002514F
0x18002513d  mov     qword ptr [rsp+178h+length], r12
0x180025142  mov     rax, [rcx]
0x180025145  mov     rax, [rax+10h]
0x180025149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002514e  nop
0x18002514f  lea     rcx, [rsp+178h+var_60]; string
0x180025157  call    ??$?0$0CP@@StringReference@Internal@Windows@@QEAA@AEAY0CP@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[47])
0x18002515c  mov     [rsp+178h+var_130], r12
0x180025161  lea     rdx, [rsp+178h+var_130]
0x180025166  mov     rcx, [rsp+178h+var_60]
0x18002516e  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>)
0x180025173  mov     ebx, eax
0x180025175  test    eax, eax
0x180025177  jns     short loc_1800251DD
0x180025179  mov     rcx, [rsp+178h]; this
0x180025181  mov     r9d, eax; char *
0x180025184  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002518b  mov     edx, 160h; void *
0x180025190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025195  nop
0x180025196  lea     rcx, [rsp+178h+var_130]
0x18002519b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800251a0  nop
0x1800251a1  test    rsi, rsi
0x1800251a4  jz      short loc_1800251B6
0x1800251a6  mov     rax, [rsi]
0x1800251a9  mov     rcx, rsi
0x1800251ac  mov     rax, [rax+10h]
0x1800251b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251b5  nop
0x1800251b6  lea     rcx, [rsp+178h+var_128]
0x1800251bb  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800251c0  nop
0x1800251c1  lea     rcx, [rsp+178h+var_138]
0x1800251c6  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800251cb  nop
0x1800251cc  lea     rcx, [rsp+178h+var_100]
0x1800251d1  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800251d6  mov     eax, ebx
0x1800251d8  jmp     loc_180025812
0x1800251dd  mov     rax, [rdi]
0x1800251e0  mov     r8d, [rdi+38h]
0x1800251e4  lea     rdx, [rsp+178h+sourceString]
0x1800251ec  mov     rcx, rdi
0x1800251ef  mov     rax, [rax+70h]
0x1800251f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251f8  nop
0x1800251f9  lea     rdi, [rsp+178h+sourceString]
0x180025201  cmp     [rsp+178h+var_C8], 8
0x18002520a  cmovnb  rdi, [rsp+178h+sourceString]
0x180025213  mov     [rsp+178h+length], r12d
0x180025218  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002521c  inc     rbx
0x18002521f  cmp     [rdi+rbx*2], r12w
0x180025224  jnz     short loc_18002521C
0x180025226  lea     rdx, [rsp+178h+length]; unsigned int *
0x18002522b  mov     rcx, rbx; unsigned __int64
0x18002522e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180025233  test    eax, eax
0x180025235  jns     short loc_180025252
0x180025237  xor     r9d, r9d; lpArguments
0x18002523a  xor     r8d, r8d; nNumberOfArguments
0x18002523d  lea     edx, [r9+1]; dwExceptionFlags
0x180025241  mov     ecx, 0C000000Dh; dwExceptionCode
0x180025246  call    cs:__imp_RaiseException
0x18002524d  nop     dword ptr [rax+rax+00h]
0x180025252  lea     r9, [rsp+178h+string]; string
0x18002525a  lea     r8, [rsp+178h+hstringHeader]; hstringHeader
0x180025262  mov     edx, [rsp+178h+length]; length
0x180025266  mov     rcx, rdi; sourceString
0x180025269  call    cs:__imp_WindowsCreateStringReference
0x180025270  nop     dword ptr [rax+rax+00h]
0x180025275  mov     rcx, [rsp+178h+var_130]
0x18002527a  mov     rax, [rcx]
0x18002527d  mov     rdx, [rsp+178h+string]
0x180025285  mov     rax, [rax+58h]
0x180025289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002528e  mov     ebx, eax
0x180025290  test    eax, eax
0x180025292  jns     short loc_18002530B
0x180025294  mov     rcx, [rsp+178h]; this
0x18002529c  mov     r9d, eax; char *
0x18002529f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800252a6  mov     edx, 164h; void *
0x1800252ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800252b0  nop
0x1800252b1  xor     r8d, r8d
0x1800252b4  mov     dl, 1
0x1800252b6  lea     rcx, [rsp+178h+sourceString]
0x1800252be  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800252c3  nop
0x1800252c4  lea     rcx, [rsp+178h+var_130]
0x1800252c9  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800252ce  nop
0x1800252cf  test    rsi, rsi
0x1800252d2  jz      short loc_1800252E4
0x1800252d4  mov     rax, [rsi]
0x1800252d7  mov     rcx, rsi
0x1800252da  mov     rax, [rax+10h]
0x1800252de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252e3  nop
0x1800252e4  lea     rcx, [rsp+178h+var_128]
0x1800252e9  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800252ee  nop
0x1800252ef  lea     rcx, [rsp+178h+var_138]
0x1800252f4  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800252f9  nop
0x1800252fa  lea     rcx, [rsp+178h+var_100]
0x1800252ff  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x180025304  mov     eax, ebx
0x180025306  jmp     loc_180025812
0x18002530b  lea     rdx, [rsp+178h+var_C0]
0x180025313  mov     rcx, r14
0x180025316  call    ?GetPackagePath@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackagePath(void)
0x18002531b  nop
0x18002531c  lea     rax, [rsp+178h+var_C0]
0x180025324  cmp     [rsp+178h+var_A8], 8
0x18002532d  cmovnb  rax, [rsp+178h+var_C0]
0x180025336  mov     qword ptr [rsp+178h+length], rax
0x18002533b  lea     rdx, [rsp+178h+length]
0x180025340  lea     rcx, [rsp+178h+var_A0]
0x180025348  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002534d  nop
0x18002534e  xorps   xmm6, xmm6
0x180025351  mov     rdi, [rsp+178h+var_130]
0x180025356  mov     rax, [rdi]
0x180025359  mov     rbx, [rax+30h]
0x18002535d  lea     rcx, [rsp+178h+var_138]
0x180025362  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180025367  movdqa  xmmword ptr [rsp+178h+length], xmm6
0x18002536d  lea     rax, [rsp+178h+var_138]
0x180025372  mov     [rsp+178h+var_150], rax
0x180025377  mov     [rsp+178h+var_158], r15d; int
0x18002537c  mov     r9d, 1
0x180025382  lea     r8, [rsp+178h+length]
0x180025387  mov     rdx, [rsp+178h+var_88]
0x18002538f  mov     rcx, rdi
0x180025392  mov     rax, rbx
0x180025395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002539a  mov     ebx, eax
0x18002539c  test    eax, eax
0x18002539e  jns     loc_180025436
0x1800253a4  mov     rcx, [rsp+178h]; this
0x1800253ac  mov     r9d, eax; char *
0x1800253af  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800253b6  mov     edx, 16Ah; void *
0x1800253bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800253c0  nop
0x1800253c1  mov     [rsp+178h+var_88], r12
0x1800253c9  xor     r8d, r8d
0x1800253cc  mov     dl, 1
0x1800253ce  lea     rcx, [rsp+178h+var_C0]
0x1800253d6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800253db  nop
0x1800253dc  xor     r8d, r8d
0x1800253df  mov     dl, 1
0x1800253e1  lea     rcx, [rsp+178h+sourceString]
0x1800253e9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800253ee  nop
0x1800253ef  lea     rcx, [rsp+178h+var_130]
0x1800253f4  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800253f9  nop
0x1800253fa  test    rsi, rsi
0x1800253fd  jz      short loc_18002540F
0x1800253ff  mov     rax, [rsi]
0x180025402  mov     rcx, rsi
0x180025405  mov     rax, [rax+10h]
0x180025409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002540e  nop
0x18002540f  lea     rcx, [rsp+178h+var_128]
0x180025414  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180025419  nop
0x18002541a  lea     rcx, [rsp+178h+var_138]
0x18002541f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180025424  nop
0x180025425  lea     rcx, [rsp+178h+var_100]
0x18002542a  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x18002542f  mov     eax, ebx
0x180025431  jmp     loc_180025812
0x180025436  mov     rcx, [rsp+178h+var_138]
  ... truncated ...
```
