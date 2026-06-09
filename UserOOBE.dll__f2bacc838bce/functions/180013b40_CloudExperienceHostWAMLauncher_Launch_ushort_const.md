# CloudExperienceHostWAMLauncher::Launch(ushort const *)

- ea: `0x180013b40`
- end: `0x18001443f`
- name: `?Launch@CloudExperienceHostWAMLauncher@@EEAAJPEBG@Z`
- size: `2303`
- prototype: `__int64 __fastcall(CloudExperienceHostWAMLauncher *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032b0`
- `0x1800056c8`
- `0x180007134`
- `0x180010380`
- `0x18001051c`
- `0x1800111f8`
- `0x18001136c`
- `0x180012328`
- `0x180013b40`
- `0x18001680c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b71`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013be0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013e02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013be0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013e02`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x180014153`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x180014153`

## string_xrefs

- `0x180013bb8`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180013dda`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x180013bf7`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013ceb`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013e19`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013f17`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013fc1`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x1800140a8`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x1800141c9`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x1800142aa`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x1800143a5`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013cab`: `https://login.microsoft.com`
- `0x180013ecd`: `service::ads.arcct.msn.com::MBI_SSL`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CloudExperienceHostWAMLauncher::Launch(
        CloudExperienceHostWAMLauncher *this,
        const unsigned __int16 *a2)
{
  int ActivationFactory; // eax
  unsigned int v3; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, PVOID, __int64 *); // rsi
  PVOID Reserved1; // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, PVOID, __int64); // rsi
  __int64 v16; // rbx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, PVOID, __int64, _BYTE *); // rdi
  __int64 v24; // rbx
  int v25; // eax
  unsigned int v26; // ebx
  HWND WindowW; // rbx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HWND, _QWORD, GUID *); // rsi
  _QWORD *v30; // rcx
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rcx
  _QWORD *v34; // rdi
  int v35; // ebx
  int v36; // [rsp+20h] [rbp-D8h]
  _BYTE v37[8]; // [rsp+30h] [rbp-C8h] BYREF
  int v38[2]; // [rsp+38h] [rbp-C0h] BYREF
  int v39[2]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-98h] BYREF
  __int64 v44; // [rsp+68h] [rbp-90h] BYREF
  _BYTE v45[8]; // [rsp+70h] [rbp-88h] BYREF
  __int64 v46; // [rsp+78h] [rbp-80h] BYREF
  __int64 v47; // [rsp+80h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-58h]
  _QWORD v50[4]; // [rsp+A8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  __0__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_PEBG_Z(
    v45,
    L"Local\\Windows.User.CloudExperienceHostWAM");
  if ( GetLastError() != 183 )
  {
    v42 = 0;
    *(_QWORD *)v38 = 0;
    v41 = 0;
    v40 = 0;
    *(_QWORD *)v39 = 0;
    v43 = 0;
    v44 = 0;
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
      0x46u,
      0x45u);
    ActivationFactory = RoGetActivationFactory(v49, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v44);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v36);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return v3;
    }
    v5 = v44;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, PVOID, __int64 *))(*(_QWORD *)v44 + 96LL);
    v42 = 0;
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&hstringHeader,
      L"consumers");
    Reserved1 = hstringHeader.Reserved.Reserved1;
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v50,
      L"https://login.microsoft.com");
    v8 = v6(v5, v50[0], Reserved1, &v42);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v8,
        v36);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return v9;
    }
    v41 = 0;
    v10 = v42;
    v11 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(v42);
    if ( v11 < 0 || (v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 64LL))(v10, &v41), v11 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v11,
        v36);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return (unsigned int)v11;
    }
    v40 = 0;
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
      0x39u,
      0x38u);
    v12 = RoGetActivationFactory(v49, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v40);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v12,
        v36);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return v13;
    }
    v14 = v40;
    v15 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, __int64))(*(_QWORD *)v40 + 48LL);
    *(_QWORD *)v38 = 0;
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v50,
      L"4b0964e4-58f1-47f4-a552-e2e1fc56dcd7");
    v16 = v50[0];
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&hstringHeader,
      L"service::ads.arcct.msn.com::MBI_SSL");
    v17 = v15(v14, v41, hstringHeader.Reserved.Reserved1, v16);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v17,
        (int)v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return v18;
    }
    v37[0] = 0;
    v46 = 0;
    v19 = **(_QWORD **)v38;
    v46 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v19 + 80))(*(_QWORD *)v38, &v46);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v20,
        (int)v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v46);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return v21;
    }
    v22 = v46;
    v23 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v46 + 80LL);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v50, L"2.0");
    v24 = v50[0];
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&hstringHeader,
      L"api-version");
    v25 = v23(v22, hstringHeader.Reserved.Reserved1, v24, v37);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v25,
        (int)v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v46);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return v26;
    }
    v47 = 0;
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v44)(v44, &GUID_f4b8e804_811e_4436_b69c_44cb67b72084, &v47);
    WindowW = FindWindowW(L"Shell_TrayWnd", 0);
    if ( WindowW )
    {
      v28 = v47;
      v29 = *(__int64 (__fastcall **)(__int64, HWND, _QWORD, GUID *))(*(_QWORD *)v47 + 48LL);
      v30 = *(_QWORD **)v39;
      *(_QWORD *)v39 = 0;
      if ( v30 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v30 + 16LL))(v30, *v30);
      v31 = v29(v28, WindowW, *(_QWORD *)v38, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)v31,
          (int)v39);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v47);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v46);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
        return v32;
      }
      v33 = v43;
      v43 = 0;
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v34 = *(_QWORD **)v39;
      v35 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(*(_QWORD *)v39);
      if ( v35 < 0 || (v35 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v34 + 64LL))(v34, &v43), v35 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)v35,
          (int)v39);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v47);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v46);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
        return (unsigned int)v35;
      }
    }
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v47);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v46);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v43);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v39);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v41);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v38);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v44);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
  return 0;
}

```

## disassembly

```asm
0x180013b40  push    rbx
0x180013b42  push    rsi
0x180013b43  push    rdi
0x180013b44  push    r14
0x180013b46  sub     rsp, 0D8h
0x180013b4d  mov     rax, cs:__security_cookie
0x180013b54  xor     rax, rsp
0x180013b57  mov     [rsp+0F8h+var_30], rax
0x180013b5f  lea     rdx, aLocalWindowsUs_0; "Local\\Windows.User.CloudExperienceHost"...
0x180013b66  lea     rcx, [rsp+0F8h+var_88]
0x180013b6b  call    ??0?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@PEBG@Z
0x180013b70  nop
0x180013b71  call    cs:__imp_GetLastError
0x180013b77  cmp     eax, 0B7h
0x180013b7c  jz      loc_180014412
0x180013b82  xor     r14d, r14d
0x180013b85  mov     [rsp+0F8h+var_A0], r14
0x180013b8a  mov     qword ptr [rsp+0F8h+var_C0], r14
0x180013b8f  mov     [rsp+0F8h+var_A8], r14
0x180013b94  mov     [rsp+0F8h+var_B0], r14
0x180013b99  mov     qword ptr [rsp+0F8h+var_B8], r14
0x180013b9e  mov     [rsp+0F8h+var_98], r14
0x180013ba3  mov     [rsp+0F8h+var_90], r14
0x180013ba8  mov     [rsp+0F8h+var_58], r14
0x180013bb0  lea     r9d, [r14+45h]; unsigned int
0x180013bb4  lea     r8d, [r14+46h]; unsigned int
0x180013bb8  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180013bbf  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180013bc7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013bcc  lea     r8, [rsp+0F8h+var_90]
0x180013bd1  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180013bd8  mov     rcx, [rsp+0F8h+var_58]
0x180013be0  call    cs:__imp_RoGetActivationFactory
0x180013be6  mov     ebx, eax
0x180013be8  test    eax, eax
0x180013bea  jns     short loc_180013C67
0x180013bec  mov     rcx, [rsp+0F8h]; this
0x180013bf4  mov     r9d, eax; char *
0x180013bf7  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013bfe  mov     edx, 92h; void *
0x180013c03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c08  nop
0x180013c09  lea     rcx, [rsp+0F8h+var_98]
0x180013c0e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c13  nop
0x180013c14  lea     rcx, [rsp+0F8h+var_B8]
0x180013c19  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c1e  nop
0x180013c1f  lea     rcx, [rsp+0F8h+var_B0]
0x180013c24  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c29  nop
0x180013c2a  lea     rcx, [rsp+0F8h+var_A8]
0x180013c2f  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c34  nop
0x180013c35  lea     rcx, [rsp+0F8h+var_C0]
0x180013c3a  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c3f  nop
0x180013c40  lea     rcx, [rsp+0F8h+var_A0]
0x180013c45  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c4a  nop
0x180013c4b  lea     rcx, [rsp+0F8h+var_90]
0x180013c50  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013c55  nop
0x180013c56  lea     rcx, [rsp+0F8h+var_88]
0x180013c5b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013c60  mov     eax, ebx
0x180013c62  jmp     loc_180014421
0x180013c67  mov     rdi, [rsp+0F8h+var_90]
0x180013c6c  mov     rax, [rdi]
0x180013c6f  mov     rsi, [rax+60h]
0x180013c73  mov     rcx, [rsp+0F8h+var_A0]
0x180013c78  mov     [rsp+0F8h+var_A0], r14
0x180013c7d  test    rcx, rcx
0x180013c80  jz      short loc_180013C8F
0x180013c82  mov     rax, [rcx]
0x180013c85  mov     rax, [rax+10h]
0x180013c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c8e  nop
0x180013c8f  lea     rdx, aConsumers; "consumers"
0x180013c96  lea     rcx, [rsp+0F8h+hstringHeader]; this
0x180013c9e  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180013ca3  mov     rbx, qword ptr [rsp+0F8h+hstringHeader.Reserved]
0x180013cab  lea     rdx, aHttpsLoginMicr; "https://login.microsoft.com"
0x180013cb2  lea     rcx, [rsp+0F8h+var_50]; this
0x180013cba  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180013cbf  lea     r9, [rsp+0F8h+var_A0]
0x180013cc4  mov     r8, rbx
0x180013cc7  mov     rdx, [rsp+0F8h+var_50]
0x180013ccf  mov     rcx, rdi
0x180013cd2  mov     rax, rsi
0x180013cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cda  mov     ebx, eax
0x180013cdc  test    eax, eax
0x180013cde  jns     short loc_180013D5B
0x180013ce0  mov     rcx, [rsp+0F8h]; this
0x180013ce8  mov     r9d, eax; char *
0x180013ceb  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013cf2  mov     edx, 93h; void *
0x180013cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013cfc  nop
0x180013cfd  lea     rcx, [rsp+0F8h+var_98]
0x180013d02  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d07  nop
0x180013d08  lea     rcx, [rsp+0F8h+var_B8]
0x180013d0d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d12  nop
0x180013d13  lea     rcx, [rsp+0F8h+var_B0]
0x180013d18  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d1d  nop
0x180013d1e  lea     rcx, [rsp+0F8h+var_A8]
0x180013d23  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d28  nop
0x180013d29  lea     rcx, [rsp+0F8h+var_C0]
0x180013d2e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d33  nop
0x180013d34  lea     rcx, [rsp+0F8h+var_A0]
0x180013d39  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d3e  nop
0x180013d3f  lea     rcx, [rsp+0F8h+var_90]
0x180013d44  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013d49  nop
0x180013d4a  lea     rcx, [rsp+0F8h+var_88]
0x180013d4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013d54  mov     eax, ebx
0x180013d56  jmp     loc_180014421
0x180013d5b  mov     rcx, [rsp+0F8h+var_A8]
0x180013d60  mov     [rsp+0F8h+var_A8], r14
0x180013d65  test    rcx, rcx
0x180013d68  jz      short loc_180013D77
0x180013d6a  mov     rax, [rcx]
0x180013d6d  mov     rax, [rax+10h]
0x180013d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d76  nop
0x180013d77  mov     rdi, [rsp+0F8h+var_A0]
0x180013d7c  mov     rcx, rdi
0x180013d7f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x180013d84  mov     ebx, eax
0x180013d86  test    eax, eax
0x180013d88  js      loc_18001439A
0x180013d8e  mov     rax, [rdi]
0x180013d91  lea     rdx, [rsp+0F8h+var_A8]
0x180013d96  mov     rcx, rdi
0x180013d99  mov     rax, [rax+40h]
0x180013d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da2  mov     ebx, eax
0x180013da4  test    eax, eax
0x180013da6  js      loc_18001439A
0x180013dac  mov     rcx, [rsp+0F8h+var_B0]
0x180013db1  mov     [rsp+0F8h+var_B0], r14
0x180013db6  test    rcx, rcx
0x180013db9  jz      short loc_180013DC8
0x180013dbb  mov     rax, [rcx]
0x180013dbe  mov     rax, [rax+10h]
0x180013dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc7  nop
0x180013dc8  mov     [rsp+0F8h+var_58], r14
0x180013dd0  mov     r9d, 38h ; '8'; unsigned int
0x180013dd6  lea     r8d, [r9+1]; unsigned int
0x180013dda  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180013de1  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180013de9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013dee  lea     r8, [rsp+0F8h+var_B0]
0x180013df3  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x180013dfa  mov     rcx, [rsp+0F8h+var_58]
0x180013e02  call    cs:__imp_RoGetActivationFactory
0x180013e08  mov     ebx, eax
0x180013e0a  test    eax, eax
0x180013e0c  jns     short loc_180013E89
0x180013e0e  mov     rcx, [rsp+0F8h]; this
0x180013e16  mov     r9d, eax; char *
0x180013e19  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013e20  mov     edx, 95h; void *
0x180013e25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e2a  nop
0x180013e2b  lea     rcx, [rsp+0F8h+var_98]
0x180013e30  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e35  nop
0x180013e36  lea     rcx, [rsp+0F8h+var_B8]
0x180013e3b  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e40  nop
0x180013e41  lea     rcx, [rsp+0F8h+var_B0]
0x180013e46  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e4b  nop
0x180013e4c  lea     rcx, [rsp+0F8h+var_A8]
0x180013e51  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e56  nop
0x180013e57  lea     rcx, [rsp+0F8h+var_C0]
0x180013e5c  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e61  nop
0x180013e62  lea     rcx, [rsp+0F8h+var_A0]
0x180013e67  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e6c  nop
0x180013e6d  lea     rcx, [rsp+0F8h+var_90]
0x180013e72  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013e77  nop
0x180013e78  lea     rcx, [rsp+0F8h+var_88]
0x180013e7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013e82  mov     eax, ebx
0x180013e84  jmp     loc_180014421
0x180013e89  mov     rdi, [rsp+0F8h+var_B0]
0x180013e8e  mov     rax, [rdi]
0x180013e91  mov     rsi, [rax+30h]
0x180013e95  mov     rcx, qword ptr [rsp+0F8h+var_C0]
0x180013e9a  mov     qword ptr [rsp+0F8h+var_C0], r14
0x180013e9f  test    rcx, rcx
0x180013ea2  jz      short loc_180013EB1
0x180013ea4  mov     rax, [rcx]
0x180013ea7  mov     rax, [rax+10h]
0x180013eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eb0  nop
0x180013eb1  lea     rdx, a4b0964e458f147; "4b0964e4-58f1-47f4-a552-e2e1fc56dcd7"
0x180013eb8  lea     rcx, [rsp+0F8h+var_50]; this
0x180013ec0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180013ec5  mov     rbx, [rsp+0F8h+var_50]
0x180013ecd  lea     rdx, aServiceAdsArcc; "service::ads.arcct.msn.com::MBI_SSL"
0x180013ed4  lea     rcx, [rsp+0F8h+hstringHeader]; this
0x180013edc  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180013ee1  lea     rax, [rsp+0F8h+var_C0]
0x180013ee6  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180013eeb  mov     r9, rbx
0x180013eee  mov     r8, qword ptr [rsp+0F8h+hstringHeader.Reserved]
0x180013ef6  mov     rdx, [rsp+0F8h+var_A8]
0x180013efb  mov     rcx, rdi
0x180013efe  mov     rax, rsi
0x180013f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f06  mov     ebx, eax
0x180013f08  test    eax, eax
0x180013f0a  jns     short loc_180013F87
0x180013f0c  mov     rcx, [rsp+0F8h]; this
0x180013f14  mov     r9d, eax; char *
0x180013f17  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013f1e  mov     edx, 96h; void *
0x180013f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f28  nop
0x180013f29  lea     rcx, [rsp+0F8h+var_98]
0x180013f2e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f33  nop
0x180013f34  lea     rcx, [rsp+0F8h+var_B8]
0x180013f39  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f3e  nop
0x180013f3f  lea     rcx, [rsp+0F8h+var_B0]
0x180013f44  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f49  nop
0x180013f4a  lea     rcx, [rsp+0F8h+var_A8]
0x180013f4f  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f54  nop
0x180013f55  lea     rcx, [rsp+0F8h+var_C0]
0x180013f5a  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f5f  nop
0x180013f60  lea     rcx, [rsp+0F8h+var_A0]
0x180013f65  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f6a  nop
0x180013f6b  lea     rcx, [rsp+0F8h+var_90]
0x180013f70  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013f75  nop
0x180013f76  lea     rcx, [rsp+0F8h+var_88]
0x180013f7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013f80  mov     eax, ebx
0x180013f82  jmp     loc_180014421
0x180013f87  mov     [rsp+0F8h+var_C8], r14b
0x180013f8c  mov     [rsp+0F8h+var_80], r14
0x180013f91  mov     rcx, qword ptr [rsp+0F8h+var_C0]
0x180013f96  mov     rax, [rcx]
0x180013f99  mov     [rsp+0F8h+var_80], r14
0x180013f9e  lea     rdx, [rsp+0F8h+var_80]
0x180013fa3  mov     rax, [rax+50h]
0x180013fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fac  mov     ebx, eax
0x180013fae  test    eax, eax
0x180013fb0  jns     loc_18001403C
0x180013fb6  mov     rcx, [rsp+0F8h]; this
0x180013fbe  mov     r9d, eax; char *
0x180013fc1  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013fc8  mov     edx, 9Ah; void *
0x180013fcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fd2  nop
0x180013fd3  lea     rcx, [rsp+0F8h+var_80]
0x180013fd8  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013fdd  nop
0x180013fde  lea     rcx, [rsp+0F8h+var_98]
0x180013fe3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013fe8  nop
0x180013fe9  lea     rcx, [rsp+0F8h+var_B8]
0x180013fee  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013ff3  nop
0x180013ff4  lea     rcx, [rsp+0F8h+var_B0]
0x180013ff9  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013ffe  nop
0x180013fff  lea     rcx, [rsp+0F8h+var_A8]
0x180014004  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180014009  nop
0x18001400a  lea     rcx, [rsp+0F8h+var_C0]
0x18001400f  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180014014  nop
0x180014015  lea     rcx, [rsp+0F8h+var_A0]
0x18001401a  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001401f  nop
0x180014020  lea     rcx, [rsp+0F8h+var_90]
0x180014025  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001402a  nop
  ... truncated ...
```
