# CloudStoreUtilities::GetPackageFamilyNameHostInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800107b0`
- end: `0x180010fa0`
- name: `?GetPackageFamilyNameHostInfo@CloudStoreUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `2032`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800106c8`
- `0x1801040e8`

## callees

- `0x18000dfe4`
- `0x18000e8d0`
- `0x18000f840`
- `0x18000f8dc`
- `0x18000fe60`
- `0x1800107b0`
- `0x180011134`
- `0x180016cf4`
- `0x180024fd0`
- `0x180026688`
- `0x180032a50`
- `0x18003f11c`
- `0x180047904`
- `0x180062040`
- `0x180065614`
- `0x180091b04`
- `0x18009a2b0`
- `0x1800d1d50`
- `0x1800f8ea4`
- `0x1800f93b0`
- `0x1801201a0`
- `0x1801c0acc`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010812`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010e77`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180010c3d`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180010c3d`

## string_xrefs

- `0x180010830`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010879`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800108ed`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010926`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800109a5`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800109e8`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010a09`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010a50`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010ae7`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010b2a`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010b4b`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010ba0`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010bfe`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010c4e`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010c97`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010d2d`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010d75`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010de6`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x180010e4b`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall CloudStoreUtilities::GetPackageFamilyNameHostInfo(__int64 a1, HSTRING a2)
{
  HANDLE CurrentProcess; // rax
  bool *v5; // r8
  int IsProcessAppContainer; // eax
  unsigned __int16 **v7; // rdx
  const char *v8; // r9
  int CallingProcessAppId; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, _QWORD, int *); // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, PVOID, __int64); // r14
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  int v18; // eax
  const char *v19; // r9
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, __int64, int *); // rbx
  int v24; // eax
  int v25; // eax
  const char *v26; // r9
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  int v31; // eax
  __int64 (__fastcall **v32)(_QWORD, GUID *, __int64 **); // rax
  int v33; // eax
  __int64 *v34; // rdi
  __int64 (__fastcall *v35)(__int64 *, __int64, int *); // rbx
  unsigned int v36; // ebx
  char v37; // al
  __int64 (__fastcall **v38)(_QWORD, GUID *, __int64 *); // rax
  int v39; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64, __int64 *); // rbx
  unsigned int v42; // eax
  char v43; // cl
  __int64 **v44; // rax
  __int64 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  void *v48; // rcx
  void *v49; // rcx
  int *v51; // [rsp+20h] [rbp-A9h]
  _BYTE v52[8]; // [rsp+30h] [rbp-99h] BYREF
  HSTRING *p_pv; // [rsp+38h] [rbp-91h] BYREF
  int v54[2]; // [rsp+40h] [rbp-89h] BYREF
  char v55; // [rsp+48h] [rbp-81h]
  unsigned int v56; // [rsp+50h] [rbp-79h] BYREF
  __int64 *v57; // [rsp+58h] [rbp-71h] BYREF
  HSTRING v58; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v59; // [rsp+68h] [rbp-61h] BYREF
  HSTRING string; // [rsp+70h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-51h] BYREF
  __int64 v62; // [rsp+80h] [rbp-49h] BYREF
  __int64 v63; // [rsp+88h] [rbp-41h] BYREF
  __int64 *v64; // [rsp+90h] [rbp-39h] BYREF
  __int64 v65; // [rsp+98h] [rbp-31h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-29h] BYREF
  __int64 (__fastcall ***v67)(_QWORD, GUID *, __int64 **); // [rsp+A8h] [rbp-21h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-11h] BYREF
  _QWORD v70[2]; // [rsp+C0h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v72; // [rsp+E8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v70[0] = a1;
  if ( (unsigned int)CloudStoreUtilities::StorageTestHook::GetValue() == 2
    || (unsigned int)CloudStoreUtilities::StorageTestHook::GetValue() == 3 )
  {
    std::wstring::wstring(a1, a2);
    return a1;
  }
  wil::GetActivationFactory<Windows::Internal::StateRepository::IApplicationStatics>(&v68);
  v65 = 0;
  v52[0] = 0;
  CurrentProcess = GetCurrentProcess();
  IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, v52, v5);
  if ( IsProcessAppContainer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x575,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)IsProcessAppContainer,
      (int)v51);
  if ( v52[0] )
  {
    v58 = 0;
    p_pv = &v58;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)v54, v7);
    if ( CallingProcessAppId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x579,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)CallingProcessAppId,
        (int)v51);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
    v10 = v68;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *))(*(_QWORD *)v68 + 240LL);
    p_pv = (HSTRING *)&v65;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    string = v58;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
    v13 = v11(v10, 0, *(_QWORD *)(v12 + 24), v54);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v13,
        (int)v51);
    v72 = 0;
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v58);
  }
  else
  {
    if ( !*((_QWORD *)a2 + 2) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x57E,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        v8);
    v57 = 0;
    v14 = v68;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, PVOID, __int64))(*(_QWORD *)v68 + 296LL);
    p_pv = (HSTRING *)&v57;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(HSTRING *)a2;
    string = a2;
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&string);
    v51 = v54;
    v17 = v15(v14, 0, v16[1].Reserved.Reserved1, 1);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x586,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v17,
        (int)v54);
    v72 = 0;
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
    v56 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v57 + 56))(v57, &v56);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x589,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v18,
        (int)v54);
    if ( !v56 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x58E,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        v19);
    v20 = *v57;
    p_pv = (HSTRING *)&v65;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *))(v20 + 48))(v57, 0, v54);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v21,
        (int)v54);
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
  }
  wil::GetActivationFactory<Windows::Internal::StateRepository::IApplicationExtensionStatics>(&v69);
  v64 = 0;
  v22 = v69;
  v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v69 + 136LL);
  p_pv = (HSTRING *)&v64;
  *(_QWORD *)v54 = 0;
  v55 = 1;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"windows.userActivity", 0x15u, 0x14u);
  v24 = v23(v22, v65, v72, v54);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x595,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v24,
      (int)v51);
  v72 = 0;
  wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
  v59 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v64 + 56))(v64, &v59);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x598,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v25,
      (int)v51);
  if ( v59 > 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x599,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      v26);
  if ( v59 == 1 )
  {
    v58 = 0;
    v27 = *v64;
    p_pv = &v58;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *))(v27 + 48))(v64, 0, v54);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v28,
        (int)v51);
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
    v56 = 0;
    pv = 0;
    v29 = *(_QWORD *)v58;
    p_pv = (HSTRING *)&pv;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    v30 = (*(__int64 (__fastcall **)(HSTRING, unsigned int *, int *))(v29 + 512))(v58, &v56, v54);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A3,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v30,
        (int)v51);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    v67 = 0;
    p_pv = (HSTRING *)&v67;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    v31 = SRDictionaryToPropertySet(v56, pv, v54);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A5,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v31,
        (int)v51);
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
    v57 = 0;
    v32 = *v67;
    v57 = 0;
    v33 = (*v32)(v67, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v57);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A8,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v33,
        (int)v51);
    v66 = 0;
    v34 = v57;
    v35 = *(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v57 + 48);
    p_pv = (HSTRING *)&v66;
    *(_QWORD *)v54 = 0;
    v55 = 1;
    v72 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserActivity", 0xDu, 0xCu);
    v36 = v35(v34, v72, v54);
    v72 = 0;
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_pv);
    if ( !v36 || (v37 = 1, v36 == -2147483637) )
      v37 = 0;
    if ( v37 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AC,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)v36,
        (int)v51);
    if ( v36 != -2147483637 )
    {
      v63 = 0;
      v38 = *v66;
      v63 = 0;
      v39 = (*v38)(v66, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v63);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B1,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
          (const char *)(unsigned int)v39,
          (int)v51);
      v62 = 0;
      v40 = v63;
      v41 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v63 + 48LL);
      v62 = 0;
      v72 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@ActivitySourceHost", 0x14u, 0x13u);
      v42 = v41(v40, v72, &v62);
      if ( !v42 || (v43 = 1, v42 == -2147483637) )
        v43 = 0;
      if ( v43 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B5,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
          (const char *)v42,
          (int)v51);
      if ( v42 != -2147483637 )
      {
        string = 0;
        v44 = (__int64 **)wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Foundation::IPropertyValue>(
                            &v62,
                            v70);
        v45 = *v44;
        v46 = **v44;
        p_pv = &string;
        *(_QWORD *)v54 = 0;
        v55 = 1;
        v47 = (*(__int64 (__fastcall **)(__int64 *, int *))(v46 + 152))(v45, v54);
        if ( v47 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5BA,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
            (const char *)(unsigned int)v47,
            (int)v51);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_pv);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(v70);
        WindowsGetStringRawBuffer(string, 0);
        std::wstring::wstring(a1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v62);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v63);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v66);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v67);
        v48 = pv;
        pv = 0;
        if ( v48 )
          CoTaskMemFree(v48);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
        goto LABEL_58;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v62);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v63);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v66);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v67);
    v49 = pv;
    pv = 0;
    if ( v49 )
      CoTaskMemFree(v49);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
  }
  std::wstring::wstring(a1);
LABEL_58:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v64);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v69);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v65);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v68);
  return a1;
}

```

## disassembly

```asm
0x1800107b0  mov     [rsp-8+arg_10], rbx
0x1800107b5  push    rbp
0x1800107b6  push    rsi
0x1800107b7  push    rdi
0x1800107b8  push    r14
0x1800107ba  push    r15
0x1800107bc  lea     rbp, [rsp-37h]
0x1800107c1  sub     rsp, 100h
0x1800107c8  mov     rax, cs:__security_cookie
0x1800107cf  xor     rax, rsp
0x1800107d2  mov     [rbp+57h+var_30], rax
0x1800107d6  mov     rbx, rdx
0x1800107d9  mov     rsi, rcx
0x1800107dc  mov     [rbp+57h+var_60], rcx
0x1800107e0  xor     r15d, r15d
0x1800107e3  call    ?GetValue@StorageTestHook@CloudStoreUtilities@@YA?AW4CloudStoreTestHookMode@@XZ; CloudStoreUtilities::StorageTestHook::GetValue(void)
0x1800107e8  cmp     eax, 2
0x1800107eb  jz      loc_180010F6F
0x1800107f1  call    ?GetValue@StorageTestHook@CloudStoreUtilities@@YA?AW4CloudStoreTestHookMode@@XZ; CloudStoreUtilities::StorageTestHook::GetValue(void)
0x1800107f6  cmp     eax, 3
0x1800107f9  jz      loc_180010F6F
0x1800107ff  lea     rcx, [rbp+57h+var_70]
0x180010803  call    ??$GetActivationFactory@UIApplicationStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IApplicationStatics>(ushort const *)
0x180010808  nop
0x180010809  mov     [rbp+57h+var_88], r15
0x18001080d  mov     [rsp+120h+var_F0], r15b
0x180010812  call    cs:__imp_GetCurrentProcess
0x180010818  mov     rcx, rax; ProcessHandle
0x18001081b  lea     rdx, [rsp+120h+var_F0]; void *
0x180010820  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180010825  mov     rcx, [rbp+5Fh]; this
0x180010829  test    eax, eax
0x18001082b  jns     short loc_180010842
0x18001082d  mov     r9d, eax; char *
0x180010830  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010837  mov     edx, 575h; void *
0x18001083c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010842  cmp     [rsp+120h+var_F0], r15b
0x180010847  jz      loc_18001091C
0x18001084d  mov     [rbp+57h+var_C0], r15
0x180010851  lea     rax, [rbp+57h+var_C0]
0x180010855  mov     [rsp+120h+var_E8], rax
0x18001085a  mov     qword ptr [rsp+120h+var_E0], r15
0x18001085f  mov     [rsp+120h+var_D8], 1
0x180010864  lea     rcx, [rsp+120h+var_E0]; this
0x180010869  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x18001086e  mov     rcx, [rbp+5Fh]; this
0x180010872  test    eax, eax
0x180010874  jns     short loc_18001088B
0x180010876  mov     r9d, eax; char *
0x180010879  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010880  mov     edx, 579h; void *
0x180010885  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001088b  lea     rcx, [rsp+120h+var_E8]
0x180010890  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180010895  mov     rdi, [rbp+57h+var_70]
0x180010899  mov     rax, [rdi]
0x18001089c  mov     rbx, [rax+0F0h]
0x1800108a3  lea     rax, [rbp+57h+var_88]
0x1800108a7  mov     [rsp+120h+var_E8], rax
0x1800108ac  mov     qword ptr [rsp+120h+var_E0], r15
0x1800108b1  mov     [rsp+120h+var_D8], 1
0x1800108b6  mov     rax, [rbp+57h+var_C0]
0x1800108ba  mov     [rbp+57h+string], rax
0x1800108be  lea     rdx, [rbp+57h+string]
0x1800108c2  lea     rcx, [rbp+57h+hstringHeader]
0x1800108c6  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800108cb  nop
0x1800108cc  lea     r9, [rsp+120h+var_E0]
0x1800108d1  mov     r8, [rax+18h]
0x1800108d5  xor     edx, edx
0x1800108d7  mov     rcx, rdi
0x1800108da  mov     rax, rbx
0x1800108dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e2  mov     rcx, [rbp+5Fh]; this
0x1800108e6  test    eax, eax
0x1800108e8  jns     short loc_1800108FF
0x1800108ea  mov     r9d, eax; char *
0x1800108ed  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800108f4  mov     edx, 57Ah; void *
0x1800108f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800108ff  mov     [rbp+57h+var_38], r15
0x180010903  lea     rcx, [rsp+120h+var_E8]
0x180010908  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x18001090d  nop
0x18001090e  lea     rcx, [rbp+57h+var_C0]
0x180010912  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010917  jmp     loc_180010A76
0x18001091c  mov     rcx, [rbp+5Fh]; this
0x180010920  cmp     [rbx+10h], r15
0x180010924  jnz     short loc_180010938
0x180010926  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18001092d  mov     edx, 57Eh; void *
0x180010932  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010938  mov     [rbp+57h+var_C8], r15
0x18001093c  mov     rdi, [rbp+57h+var_70]
0x180010940  mov     rax, [rdi]
0x180010943  mov     r14, [rax+128h]
0x18001094a  lea     rax, [rbp+57h+var_C8]
0x18001094e  mov     [rsp+120h+var_E8], rax
0x180010953  mov     qword ptr [rsp+120h+var_E0], r15
0x180010958  mov     [rsp+120h+var_D8], 1
0x18001095d  cmp     qword ptr [rbx+18h], 7
0x180010962  jbe     short loc_180010967
0x180010964  mov     rbx, [rbx]
0x180010967  mov     [rbp+57h+string], rbx
0x18001096b  lea     rdx, [rbp+57h+string]
0x18001096f  lea     rcx, [rbp+57h+hstringHeader]
0x180010973  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180010978  nop
0x180010979  lea     rcx, [rsp+120h+var_E0]
0x18001097e  mov     qword ptr [rsp+120h+var_100], rcx; int
0x180010983  mov     r9d, 1
0x180010989  mov     r8, [rax+18h]
0x18001098d  xor     edx, edx
0x18001098f  mov     rcx, rdi
0x180010992  mov     rax, r14
0x180010995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099a  mov     rcx, [rbp+5Fh]; this
0x18001099e  test    eax, eax
0x1800109a0  jns     short loc_1800109B7
0x1800109a2  mov     r9d, eax; char *
0x1800109a5  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800109ac  mov     edx, 586h; void *
0x1800109b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800109b7  mov     [rbp+57h+var_38], r15
0x1800109bb  lea     rcx, [rsp+120h+var_E8]
0x1800109c0  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800109c5  mov     [rbp+57h+var_D0], r15d
0x1800109c9  mov     rcx, [rbp+57h+var_C8]
0x1800109cd  mov     rax, [rcx]
0x1800109d0  lea     rdx, [rbp+57h+var_D0]
0x1800109d4  mov     rax, [rax+38h]
0x1800109d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109dd  mov     rcx, [rbp+5Fh]; this
0x1800109e1  test    eax, eax
0x1800109e3  jns     short loc_1800109FA
0x1800109e5  mov     r9d, eax; char *
0x1800109e8  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800109ef  mov     edx, 589h; void *
0x1800109f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800109fa  cmp     [rbp+57h+var_D0], r15d
0x1800109fe  setz    al
0x180010a01  mov     rcx, [rbp+5Fh]; this
0x180010a05  test    al, al
0x180010a07  jz      short loc_180010A1B
0x180010a09  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010a10  mov     edx, 58Eh; void *
0x180010a15  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010a1b  mov     rcx, [rbp+57h+var_C8]
0x180010a1f  mov     rax, [rcx]
0x180010a22  lea     rdx, [rbp+57h+var_88]
0x180010a26  mov     [rsp+120h+var_E8], rdx
0x180010a2b  mov     qword ptr [rsp+120h+var_E0], r15
0x180010a30  mov     [rsp+120h+var_D8], 1
0x180010a35  lea     r8, [rsp+120h+var_E0]
0x180010a3a  xor     edx, edx
0x180010a3c  mov     rax, [rax+30h]
0x180010a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a45  mov     rcx, [rbp+5Fh]; this
0x180010a49  test    eax, eax
0x180010a4b  jns     short loc_180010A62
0x180010a4d  mov     r9d, eax; char *
0x180010a50  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010a57  mov     edx, 58Fh; void *
0x180010a5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010a62  lea     rcx, [rsp+120h+var_E8]
0x180010a67  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x180010a6c  nop
0x180010a6d  lea     rcx, [rbp+57h+var_C8]
0x180010a71  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180010a76  lea     rcx, [rbp+57h+var_68]
0x180010a7a  call    ??$GetActivationFactory@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IApplicationExtensionStatics>(ushort const *)
0x180010a7f  nop
0x180010a80  mov     [rbp+57h+var_90], r15
0x180010a84  mov     rdi, [rbp+57h+var_68]
0x180010a88  mov     rax, [rdi]
0x180010a8b  mov     rbx, [rax+88h]
0x180010a92  lea     rax, [rbp+57h+var_90]
0x180010a96  mov     [rsp+120h+var_E8], rax
0x180010a9b  mov     qword ptr [rsp+120h+var_E0], r15
0x180010aa0  mov     [rsp+120h+var_D8], 1
0x180010aa5  mov     [rbp+57h+var_38], r15
0x180010aa9  mov     r9d, 14h; unsigned int
0x180010aaf  lea     r8d, [r9+1]; unsigned int
0x180010ab3  lea     rdx, aWindowsUseract; "windows.userActivity"
0x180010aba  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010abe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010ac3  nop
0x180010ac4  lea     r9, [rsp+120h+var_E0]
0x180010ac9  mov     r8, [rbp+57h+var_38]
0x180010acd  mov     rdx, [rbp+57h+var_88]
0x180010ad1  mov     rcx, rdi
0x180010ad4  mov     rax, rbx
0x180010ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010adc  mov     rcx, [rbp+5Fh]; this
0x180010ae0  test    eax, eax
0x180010ae2  jns     short loc_180010AF9
0x180010ae4  mov     r9d, eax; char *
0x180010ae7  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010aee  mov     edx, 595h; void *
0x180010af3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010af9  mov     [rbp+57h+var_38], r15
0x180010afd  lea     rcx, [rsp+120h+var_E8]
0x180010b02  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x180010b07  mov     [rbp+57h+var_B8], r15d
0x180010b0b  mov     rcx, [rbp+57h+var_90]
0x180010b0f  mov     rax, [rcx]
0x180010b12  lea     rdx, [rbp+57h+var_B8]
0x180010b16  mov     rax, [rax+38h]
0x180010b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b1f  mov     rcx, [rbp+5Fh]; this
0x180010b23  test    eax, eax
0x180010b25  jns     short loc_180010B3C
0x180010b27  mov     r9d, eax; char *
0x180010b2a  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010b31  mov     edx, 598h; void *
0x180010b36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010b3c  cmp     [rbp+57h+var_B8], 1
0x180010b40  setnbe  al
0x180010b43  mov     rcx, [rbp+5Fh]; this
0x180010b47  test    al, al
0x180010b49  jz      short loc_180010B5D
0x180010b4b  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010b52  mov     edx, 599h; void *
0x180010b57  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010b5d  cmp     [rbp+57h+var_B8], 1
0x180010b61  jnz     loc_180010F5B
0x180010b67  mov     [rbp+57h+var_C0], r15
0x180010b6b  mov     rcx, [rbp+57h+var_90]
0x180010b6f  mov     rax, [rcx]
0x180010b72  lea     rdx, [rbp+57h+var_C0]
0x180010b76  mov     [rsp+120h+var_E8], rdx
0x180010b7b  mov     qword ptr [rsp+120h+var_E0], r15
0x180010b80  mov     [rsp+120h+var_D8], 1
0x180010b85  lea     r8, [rsp+120h+var_E0]
0x180010b8a  xor     edx, edx
0x180010b8c  mov     rax, [rax+30h]
0x180010b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b95  mov     rcx, [rbp+5Fh]; this
0x180010b99  test    eax, eax
0x180010b9b  jns     short loc_180010BB2
0x180010b9d  mov     r9d, eax; char *
0x180010ba0  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010ba7  mov     edx, 59Fh; void *
0x180010bac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010bb2  lea     rcx, [rsp+120h+var_E8]
0x180010bb7  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x180010bbc  mov     [rbp+57h+var_D0], r15d
0x180010bc0  mov     [rbp+57h+pv], r15
0x180010bc4  mov     rcx, [rbp+57h+var_C0]
0x180010bc8  mov     rax, [rcx]
0x180010bcb  lea     rdx, [rbp+57h+pv]
0x180010bcf  mov     [rsp+120h+var_E8], rdx
0x180010bd4  mov     qword ptr [rsp+120h+var_E0], r15
0x180010bd9  mov     [rsp+120h+var_D8], 1
0x180010bde  lea     r8, [rsp+120h+var_E0]
0x180010be3  lea     rdx, [rbp+57h+var_D0]
0x180010be7  mov     rax, [rax+200h]
0x180010bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bf3  mov     rcx, [rbp+5Fh]; this
0x180010bf7  test    eax, eax
0x180010bf9  jns     short loc_180010C10
0x180010bfb  mov     r9d, eax; char *
0x180010bfe  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010c05  mov     edx, 5A3h; void *
0x180010c0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010c10  lea     rcx, [rsp+120h+var_E8]
0x180010c15  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180010c1a  mov     [rbp+57h+var_78], r15
0x180010c1e  lea     rax, [rbp+57h+var_78]
0x180010c22  mov     [rsp+120h+var_E8], rax
0x180010c27  mov     qword ptr [rsp+120h+var_E0], r15
0x180010c2c  mov     [rsp+120h+var_D8], 1
0x180010c31  lea     r8, [rsp+120h+var_E0]
0x180010c36  mov     rdx, [rbp+57h+pv]
0x180010c3a  mov     ecx, [rbp+57h+var_D0]
0x180010c3d  call    cs:__imp_SRDictionaryToPropertySet
0x180010c43  mov     rcx, [rbp+5Fh]; this
0x180010c47  test    eax, eax
0x180010c49  jns     short loc_180010C60
0x180010c4b  mov     r9d, eax; char *
0x180010c4e  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180010c55  mov     edx, 5A5h; void *
0x180010c5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010c60  lea     rcx, [rsp+120h+var_E8]
0x180010c65  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x180010c6a  mov     [rbp+57h+var_C8], r15
0x180010c6e  mov     rcx, [rbp+57h+var_78]
0x180010c72  mov     rax, [rcx]
0x180010c75  mov     [rbp+57h+var_C8], r15
0x180010c79  lea     r8, [rbp+57h+var_C8]
0x180010c7d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180010c84  mov     rax, [rax]
0x180010c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c8c  mov     rcx, [rbp+5Fh]; this
0x180010c90  test    eax, eax
0x180010c92  jns     short loc_180010CA9
0x180010c94  mov     r9d, eax; char *
0x180010c97  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
  ... truncated ...
```
