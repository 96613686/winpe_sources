# DesktopStoreRemediationHandler::ActivateExtensionFailed(long,ushort const *,IServiceProvider *)

- ea: `0x180161a40`
- end: `0x18016221d`
- name: `?ActivateExtensionFailed@DesktopStoreRemediationHandler@@UEAAJJPEBGPEAUIServiceProvider@@@Z`
- size: `2013`
- prototype: `int(DesktopStoreRemediationHandler *__hidden this, int, const unsigned __int16 *, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009dfc`
- `0x18000e498`
- `0x18001c710`
- `0x1800378dc`
- `0x180037b9c`
- `0x18003d434`
- `0x180053740`
- `0x180055268`
- `0x1800eb8b4`
- `0x180120c24`
- `0x180142e10`
- `0x18016134c`
- `0x180161a40`
- `0x180164c60`
- `0x180164d18`
- `0x180164d7c`
- `0x180166638`
- `0x180166660`
- `0x18016667c`
- `0x1803703fc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180161e57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180161e57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016219f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801621d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180162006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016219f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801621d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180161fcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180162066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180161fcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180162066`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180161cc5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180161cc5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180161cff`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180161cff`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180161d4f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180161d4f`

## string_xrefs

- `0x180161d7f`: `Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices`
- `0x180161cf5`: `GamingServices`
- `0x180162042`: `page=SettingsPageInstalledApps&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=`
- `0x180161fab`: `page=SettingsPageAppsSizes&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DesktopStoreRemediationHandler::ActivateExtensionFailed(
        DesktopStoreRemediationHandler *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct IServiceProvider *a4)
{
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // r15d
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, char **); // rbx
  char v17; // bl
  SC_HANDLE v18; // rax
  const char *v19; // r9
  SC_HANDLE v20; // rax
  const char *v21; // r9
  const char *v22; // r9
  unsigned int v23; // ebx
  int v24; // ecx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  HSTRING v28; // rbx
  HRESULT v29; // eax
  __int64 v30; // rdx
  HSTRING v31; // rbx
  int SettingsAppAumid; // eax
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, _QWORD, HSTRING, _QWORD); // rdi
  HSTRING v37; // rbx
  __int64 v38; // rax
  int *bIgnoreCase; // [rsp+20h] [rbp-108h]
  int bIgnoreCasea; // [rsp+20h] [rbp-108h]
  char v41; // [rsp+30h] [rbp-F8h]
  char v42; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v43[7]; // [rsp+41h] [rbp-E7h] BYREF
  HSTRING string; // [rsp+48h] [rbp-E0h] BYREF
  char *v45; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-D0h] BYREF
  unsigned __int16 *v47; // [rsp+60h] [rbp-C8h] BYREF
  int v48; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+6Ch] [rbp-BCh] BYREF
  unsigned int v50; // [rsp+70h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+78h] [rbp-B0h] BYREF
  unsigned int v52; // [rsp+80h] [rbp-A8h] BYREF
  int v53; // [rsp+84h] [rbp-A4h] BYREF
  unsigned __int16 *v54; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+90h] [rbp-98h] BYREF
  const unsigned __int16 *v56; // [rsp+98h] [rbp-90h] BYREF
  SC_HANDLE v57; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE ServiceStatus[32]; // [rsp+A8h] [rbp-80h] BYREF
  _BYTE v59[32]; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  LODWORD(v47) = a2;
  v56 = a3;
  v46 = 0;
  QueryService = a4->lpVtbl->QueryService;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v9 = ((__int64 (__fastcall *)(struct IServiceProvider *, GUID *, GUID *, __int64 *))QueryService)(
         a4,
         &GUID_23655ae6_d92b_416f_b4d6_7c8218038718,
         &GUID_23655ae6_d92b_416f_b4d6_7c8218038718,
         &v46);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v9,
      (int)bIgnoreCase);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    return v10;
  }
  v53 = 0;
  v48 = 0;
  v52 = 0;
  v45 = 0;
  v55 = 0;
  v50 = 0;
  v49 = 0;
  v42 = 0;
  v43[0] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 24LL))(v46, &v48);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 444;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v11,
      (int)bIgnoreCase);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
    goto LABEL_21;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 32LL))(v46, &v52);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 445;
    goto LABEL_19;
  }
  v13 = v52;
  LODWORD(v51) = v52;
  v14 = v46;
  v15 = *(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v46 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v45,
    0);
  v11 = v15(v14, &v45);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 447;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 64LL))(v46, &v55);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 448;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 48LL))(v46, &v50);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 449;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 80LL))(v46, &v49);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 450;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v46 + 88LL))(v46, &v42);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 451;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v46 + 96LL))(v46, v43);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 452;
    goto LABEL_19;
  }
  if ( (v48 & 0x10003) != 0 || !v42 || (v48 & 0x80000) != 0 )
    goto LABEL_41;
  if ( v43[0] )
  {
    v17 = 1;
    v18 = OpenSCManagerW(0, 0, 1u);
    v54 = (unsigned __int16 *)v18;
    if ( !v18 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1D6,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        v19);
    v20 = OpenServiceW(v18, L"GamingServices", 4u);
    v57 = v20;
    if ( !v20 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        v21);
    memset(ServiceStatus, 0, 28);
    if ( !QueryServiceStatus(v20, (LPSERVICE_STATUS)ServiceStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        v22);
    if ( *(_DWORD *)&ServiceStatus[4] != 4 )
    {
      v23 = MaybeShowActivationErrorPopupIfCritical(
              2147943462LL,
              v13,
              L"Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices",
              v49);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v57);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      return v23;
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v57);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v54);
    v24 = -2147024894;
    if ( a2 == -2147024894 )
    {
      v41 = 1;
LABEL_33:
      LODWORD(bIgnoreCase) = v13;
      v10 = LaunchStoreForError(v24, (const WCHAR *)v45, (int)a3, v50, (__int64)bIgnoreCase, v55, v41);
      goto LABEL_20;
    }
  }
  else
  {
    v17 = 1;
  }
  if ( CompareStringOrdinal(a3, -1, L"Microsoft.WindowsStore_8wekyb3d8bbwe!App", -1, 1) != 2 )
  {
    if ( a2 == -2147009284 && GetPackageArchitectureIsArmFromPackageFullName(v45) )
    {
LABEL_45:
      v26 = 2147958074LL;
      if ( !v17 )
        v26 = a2;
      bIgnoreCase = &v53;
      v27 = MaybeShowActivationErrorPopupIfCritical(v26, v13, a3, v49);
      v10 = v27;
      if ( v27 >= 0 )
        goto LABEL_20;
      if ( ShouldLaunchStoreForError(v27) )
      {
        v41 = 0;
        goto LABEL_33;
      }
      if ( v10 != -2147217655 )
        goto LABEL_20;
      string = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::GetImpl'::`2'::impl) )
      {
        WindowsDeleteString(string);
        string = 0;
        v31 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v59, &v56) + 24);
        *(_QWORD *)&ServiceStatus[24] = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)ServiceStatus,
          L"page=SettingsPageInstalledApps&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=",
          0x73u,
          0x72u);
        v29 = WindowsConcatString(*(HSTRING *)&ServiceStatus[24], v31, &string);
        v10 = v29;
        if ( v29 < 0 )
        {
          v30 = 527;
          goto LABEL_54;
        }
      }
      else
      {
        WindowsDeleteString(string);
        string = 0;
        v28 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v59, &v56) + 24);
        *(_QWORD *)&ServiceStatus[24] = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)ServiceStatus,
          L"page=SettingsPageAppsSizes&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=",
          0x6Fu,
          0x6Eu);
        v29 = WindowsConcatString(*(HSTRING *)&ServiceStatus[24], v28, &string);
        v10 = v29;
        if ( v29 < 0 )
        {
          v30 = 532;
LABEL_54:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
            (const char *)(unsigned int)v29,
            (int)&v53);
LABEL_65:
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_20;
        }
      }
      v47 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v47,
        0);
      SettingsAppAumid = GetSettingsAppAumid(&v47);
      v10 = SettingsAppAumid;
      if ( SettingsAppAumid >= 0 )
      {
        v51 = 0;
        *(_QWORD *)&ServiceStatus[24] = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)ServiceStatus,
          L"Windows.ApplicationModel.Activation.Private.ApplicationActivation",
          0x42u,
          0x41u);
        v33 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>(
                *(_QWORD *)&ServiceStatus[24],
                &v51);
        v10 = v33;
        if ( v33 >= 0 )
        {
          v35 = v51;
          v36 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v51 + 48LL);
          v37 = string;
          v54 = v47;
          v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v59, &v54);
          LODWORD(bIgnoreCase) = 0;
          v33 = v36(v35, *(_QWORD *)(v38 + 24), v37, 0);
          v10 = v33;
          if ( v33 >= 0 )
          {
            v10 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
            WindowsDeleteString(string);
            goto LABEL_20;
          }
          v34 = 543;
        }
        else
        {
          v34 = 541;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
          (const char *)(unsigned int)v33,
          (int)bIgnoreCase);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x218,
          (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
          (const char *)(unsigned int)SettingsAppAumid,
          (int)&v53);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
      goto LABEL_65;
    }
LABEL_44:
    v17 = 0;
    goto LABEL_45;
  }
  if ( a2 == -2147023636 || a2 == -2144927149 )
    goto LABEL_44;
  if ( a2 == -2147009284 )
  {
    v25 = AttemptStoreRepairAsync();
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v25,
        bIgnoreCasea);
  }
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  return a2;
}

```

## disassembly

```asm
0x180161a40  push    rbx
0x180161a42  push    rsi
0x180161a43  push    rdi
0x180161a44  push    r12
0x180161a46  push    r13
0x180161a48  push    r14
0x180161a4a  push    r15
0x180161a4c  sub     rsp, 0F0h
0x180161a53  mov     rax, cs:__security_cookie
0x180161a5a  xor     rax, rsp
0x180161a5d  mov     [rsp+128h+var_40], rax
0x180161a65  mov     rdi, r9
0x180161a68  mov     r12, r8
0x180161a6b  mov     r13d, edx
0x180161a6e  mov     esi, edx
0x180161a70  mov     dword ptr [rsp+128h+var_C8], edx
0x180161a74  mov     [rsp+128h+var_90], r8
0x180161a7c  xor     r14d, r14d
0x180161a7f  mov     [rsp+128h+var_D0], r14
0x180161a84  mov     rax, [r9]
0x180161a87  mov     rbx, [rax+18h]
0x180161a8b  lea     rcx, [rsp+128h+var_D0]
0x180161a90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161a95  lea     r9, [rsp+128h+var_D0]
0x180161a9a  lea     rdx, _GUID_23655ae6_d92b_416f_b4d6_7c8218038718
0x180161aa1  mov     r8, rdx
0x180161aa4  mov     rcx, rdi
0x180161aa7  mov     rax, rbx
0x180161aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161aaf  mov     ebx, eax
0x180161ab1  test    eax, eax
0x180161ab3  jns     short loc_180161AD6
0x180161ab5  mov     rcx, [rsp+128h]; this
0x180161abd  mov     r9d, eax; char *
0x180161ac0  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180161ac7  mov     edx, 1AEh; void *
0x180161acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161ad1  jmp     loc_180161C76
0x180161ad6  mov     [rsp+128h+var_A4], r14d
0x180161ade  mov     [rsp+128h+var_C0], r14d
0x180161ae3  mov     [rsp+128h+var_A8], r14d
0x180161aeb  mov     [rsp+128h+var_D8], r14
0x180161af0  mov     [rsp+128h+var_98], r14
0x180161af8  mov     [rsp+128h+var_B8], r14d
0x180161afd  mov     [rsp+128h+var_BC], r14d
0x180161b02  mov     [rsp+128h+var_E8], r14b
0x180161b07  mov     [rsp+128h+var_E7], r14b
0x180161b0c  mov     rcx, [rsp+128h+var_D0]
0x180161b11  mov     rax, [rcx]
0x180161b14  lea     rdx, [rsp+128h+var_C0]
0x180161b19  mov     rax, [rax+18h]
0x180161b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161b22  mov     ebx, eax
0x180161b24  test    eax, eax
0x180161b26  jns     short loc_180161B32
0x180161b28  mov     edx, 1BCh
0x180161b2d  jmp     loc_180161C53
0x180161b32  mov     rcx, [rsp+128h+var_D0]
0x180161b37  mov     rax, [rcx]
0x180161b3a  lea     rdx, [rsp+128h+var_A8]
0x180161b42  mov     rax, [rax+20h]
0x180161b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161b4b  mov     ebx, eax
0x180161b4d  test    eax, eax
0x180161b4f  jns     short loc_180161B5B
0x180161b51  mov     edx, 1BDh
0x180161b56  jmp     loc_180161C53
0x180161b5b  mov     r15d, [rsp+128h+var_A8]
0x180161b63  mov     dword ptr [rsp+128h+var_B0], r15d
0x180161b68  mov     rdi, [rsp+128h+var_D0]
0x180161b6d  mov     rax, [rdi]
0x180161b70  mov     rbx, [rax+28h]
0x180161b74  xor     edx, edx
0x180161b76  lea     rcx, [rsp+128h+var_D8]
0x180161b7b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180161b80  lea     rdx, [rsp+128h+var_D8]
0x180161b85  mov     rcx, rdi
0x180161b88  mov     rax, rbx
0x180161b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161b90  mov     ebx, eax
0x180161b92  test    eax, eax
0x180161b94  jns     short loc_180161BA0
0x180161b96  mov     edx, 1BFh
0x180161b9b  jmp     loc_180161C53
0x180161ba0  mov     rcx, [rsp+128h+var_D0]
0x180161ba5  mov     rax, [rcx]
0x180161ba8  lea     rdx, [rsp+128h+var_98]
0x180161bb0  mov     rax, [rax+40h]
0x180161bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161bb9  mov     ebx, eax
0x180161bbb  test    eax, eax
0x180161bbd  jns     short loc_180161BC9
0x180161bbf  mov     edx, 1C0h
0x180161bc4  jmp     loc_180161C53
0x180161bc9  mov     rcx, [rsp+128h+var_D0]
0x180161bce  mov     rax, [rcx]
0x180161bd1  lea     rdx, [rsp+128h+var_B8]
0x180161bd6  mov     rax, [rax+30h]
0x180161bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161bdf  mov     ebx, eax
0x180161be1  test    eax, eax
0x180161be3  jns     short loc_180161BEC
0x180161be5  mov     edx, 1C1h
0x180161bea  jmp     short loc_180161C53
0x180161bec  mov     rcx, [rsp+128h+var_D0]
0x180161bf1  mov     rax, [rcx]
0x180161bf4  lea     rdx, [rsp+128h+var_BC]
0x180161bf9  mov     rax, [rax+50h]
0x180161bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161c02  mov     ebx, eax
0x180161c04  test    eax, eax
0x180161c06  jns     short loc_180161C0F
0x180161c08  mov     edx, 1C2h
0x180161c0d  jmp     short loc_180161C53
0x180161c0f  mov     rcx, [rsp+128h+var_D0]
0x180161c14  mov     rax, [rcx]
0x180161c17  lea     rdx, [rsp+128h+var_E8]
0x180161c1c  mov     rax, [rax+58h]
0x180161c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161c25  mov     ebx, eax
0x180161c27  test    eax, eax
0x180161c29  jns     short loc_180161C32
0x180161c2b  mov     edx, 1C3h
0x180161c30  jmp     short loc_180161C53
0x180161c32  mov     rcx, [rsp+128h+var_D0]
0x180161c37  mov     rax, [rcx]
0x180161c3a  lea     rdx, [rsp+128h+var_E7]
0x180161c3f  mov     rax, [rax+60h]
0x180161c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161c48  mov     ebx, eax
0x180161c4a  test    eax, eax
0x180161c4c  jns     short loc_180161C87
0x180161c4e  mov     edx, 1C4h; void *
0x180161c53  mov     r9d, eax; char *
0x180161c56  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180161c5d  mov     rcx, [rsp+128h]; this
0x180161c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180161c6a  nop
0x180161c6b  lea     rcx, [rsp+128h+var_D8]
0x180161c70  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180161c75  nop
0x180161c76  lea     rcx, [rsp+128h+var_D0]
0x180161c7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161c80  mov     eax, ebx
0x180161c82  jmp     loc_180161EC1
0x180161c87  test    [rsp+128h+var_C0], 10003h
0x180161c8f  jnz     loc_180161EAA
0x180161c95  cmp     [rsp+128h+var_E8], r14b
0x180161c9a  jz      loc_180161EAA
0x180161ca0  test    [rsp+128h+var_C0], 80000h
0x180161ca8  jnz     loc_180161EAA
0x180161cae  cmp     [rsp+128h+var_E7], r14b
0x180161cb3  jz      loc_180161E3E
0x180161cb9  mov     ebx, 1
0x180161cbe  mov     r8d, ebx; dwDesiredAccess
0x180161cc1  xor     edx, edx; lpDatabaseName
0x180161cc3  xor     ecx, ecx; lpMachineName
0x180161cc5  call    cs:__imp_OpenSCManagerW
0x180161ccc  nop     dword ptr [rax+rax+00h]
0x180161cd1  mov     [rsp+128h+var_A0], rax
0x180161cd9  test    rax, rax
0x180161cdc  setz    dl
0x180161cdf  mov     rcx, [rsp+128h]; this
0x180161ce7  test    dl, dl
0x180161ce9  jnz     loc_1801621E4
0x180161cef  mov     r8d, 4; dwDesiredAccess
0x180161cf5  lea     rdx, aGamingservices; "GamingServices"
0x180161cfc  mov     rcx, rax; hSCManager
0x180161cff  call    cs:__imp_OpenServiceW
0x180161d06  nop     dword ptr [rax+rax+00h]
0x180161d0b  mov     [rsp+128h+var_88], rax
0x180161d13  test    rax, rax
0x180161d16  setz    dl
0x180161d19  mov     rcx, [rsp+128h]; this
0x180161d21  test    dl, dl
0x180161d23  jnz     loc_1801621F6
0x180161d29  xorps   xmm0, xmm0
0x180161d2c  movups  xmmword ptr [rsp+128h+ServiceStatus], xmm0
0x180161d34  movups  xmmword ptr [rsp+128h+ServiceStatus+0Ch], xmm0
0x180161d3c  mov     rdi, [rsp+128h]
0x180161d44  lea     rdx, [rsp+128h+ServiceStatus]; lpServiceStatus
0x180161d4c  mov     rcx, rax; hService
0x180161d4f  call    cs:__imp_QueryServiceStatus
0x180161d56  nop     dword ptr [rax+rax+00h]
0x180161d5b  test    eax, eax
0x180161d5d  jz      loc_180162207
0x180161d63  cmp     dword ptr [rsp+128h+ServiceStatus+4], 4
0x180161d6b  jz      short loc_180161DCD
0x180161d6d  lea     rax, [rsp+128h+var_A4]
0x180161d75  mov     qword ptr [rsp+128h+bIgnoreCase], rax
0x180161d7a  mov     r9d, [rsp+128h+var_BC]
0x180161d7f  lea     r8, aMicrosoftGamin_0; "Microsoft.GamingServices_8wekyb3d8bbwe!"...
0x180161d86  mov     edx, r15d
0x180161d89  mov     ecx, 80070426h
0x180161d8e  call    ?MaybeShowActivationErrorPopupIfCritical@@YAJJW4_PackageOrigin@@PEBGW4ACTIVATION_PHASE@@PEAW4ACTIVATIONERROR_DISMISS_METHOD@@@Z; MaybeShowActivationErrorPopupIfCritical(long,_PackageOrigin,ushort const *,ACTIVATION_PHASE,ACTIVATIONERROR_DISMISS_METHOD *)
0x180161d93  mov     ebx, eax
0x180161d95  lea     rcx, [rsp+128h+var_88]
0x180161d9d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180161da2  nop
0x180161da3  lea     rcx, [rsp+128h+var_A0]
0x180161dab  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180161db0  nop
0x180161db1  lea     rcx, [rsp+128h+var_D8]
0x180161db6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180161dbb  nop
0x180161dbc  lea     rcx, [rsp+128h+var_D0]
0x180161dc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161dc6  mov     eax, ebx
0x180161dc8  jmp     loc_180161EC1
0x180161dcd  lea     rcx, [rsp+128h+var_88]
0x180161dd5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180161dda  nop
0x180161ddb  lea     rcx, [rsp+128h+var_A0]
0x180161de3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180161de8  nop
0x180161de9  jmp     short loc_180161E06
0x180161deb  xor     r14d, r14d
0x180161dee  lea     ebx, [r14+1]
0x180161df2  mov     r15d, dword ptr [rsp+128h+var_B0]
0x180161df7  mov     esi, dword ptr [rsp+128h+var_C8]
0x180161dfb  mov     r12, [rsp+128h+var_90]
0x180161e03  mov     r13d, esi
0x180161e06  mov     ecx, 80070002h
0x180161e0b  cmp     esi, ecx
0x180161e0d  jnz     short loc_180161E43
0x180161e0f  mov     [rsp+128h+var_F8], bl
0x180161e13  mov     rax, [rsp+128h+var_98]
0x180161e1b  mov     [rsp+128h+var_100], rax
0x180161e20  mov     [rsp+128h+bIgnoreCase], r15d
0x180161e25  mov     r9d, [rsp+128h+var_B8]
0x180161e2a  mov     r8, r12
0x180161e2d  mov     rdx, [rsp+128h+var_D8]
0x180161e32  call    ?LaunchStoreForError@@YAJJPEBG0IW4_PackageOrigin@@_K_N@Z; LaunchStoreForError(long,ushort const *,ushort const *,uint,_PackageOrigin,unsigned __int64,bool)
0x180161e37  mov     ebx, eax
0x180161e39  jmp     loc_180161C6B
0x180161e3e  mov     ebx, 1
0x180161e43  mov     [rsp+128h+bIgnoreCase], ebx; int
0x180161e47  or      edx, 0FFFFFFFFh; cchCount1
0x180161e4a  mov     r9d, edx; cchCount2
0x180161e4d  lea     r8, aMicrosoftWindo_17; "Microsoft.WindowsStore_8wekyb3d8bbwe!Ap"...
0x180161e54  mov     rcx, r12; lpString1
0x180161e57  call    cs:__imp_CompareStringOrdinal
0x180161e5e  nop     dword ptr [rax+rax+00h]
0x180161e63  cmp     eax, 2
0x180161e66  jnz     short loc_180161EE5
0x180161e68  cmp     esi, 800704ECh
0x180161e6e  jz      loc_180161EFB
0x180161e74  cmp     esi, 80270253h
0x180161e7a  jz      short loc_180161EFB
0x180161e7c  cmp     esi, 80073CFCh
0x180161e82  jnz     short loc_180161EAA
0x180161e84  call    ?AttemptStoreRepairAsync@@YAJXZ; AttemptStoreRepairAsync(void)
0x180161e89  mov     rcx, [rsp+128h]; this
0x180161e91  test    eax, eax
0x180161e93  jns     short loc_180161EAA
0x180161e95  mov     r9d, eax; char *
0x180161e98  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180161e9f  mov     edx, 1F7h; void *
0x180161ea4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180161ea9  nop
0x180161eaa  lea     rcx, [rsp+128h+var_D8]
0x180161eaf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180161eb4  nop
0x180161eb5  lea     rcx, [rsp+128h+var_D0]
0x180161eba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180161ebf  mov     eax, esi
0x180161ec1  mov     rcx, [rsp+128h+var_40]
0x180161ec9  xor     rcx, rsp; StackCookie
0x180161ecc  call    __security_check_cookie
0x180161ed1  add     rsp, 0F0h
0x180161ed8  pop     r15
0x180161eda  pop     r14
0x180161edc  pop     r13
0x180161ede  pop     r12
0x180161ee0  pop     rdi
0x180161ee1  pop     rsi
0x180161ee2  pop     rbx
0x180161ee3  retn
0x180161ee5  cmp     esi, 80073CFCh
0x180161eeb  jnz     short loc_180161EFB
0x180161eed  mov     rcx, [rsp+128h+var_D8]; char *
0x180161ef2  call    ?GetPackageArchitectureIsArmFromPackageFullName@@YA_NPEBG@Z; GetPackageArchitectureIsArmFromPackageFullName(ushort const *)
0x180161ef7  test    al, al
0x180161ef9  jnz     short loc_180161EFE
0x180161efb  mov     bl, r14b
0x180161efe  mov     ecx, 80073D3Ah
0x180161f03  test    bl, bl
0x180161f05  cmovz   ecx, r13d
0x180161f09  lea     rax, [rsp+128h+var_A4]
0x180161f11  mov     qword ptr [rsp+128h+bIgnoreCase], rax; int
0x180161f16  mov     r9d, [rsp+128h+var_BC]
0x180161f1b  mov     r8, r12
0x180161f1e  mov     edx, r15d
0x180161f21  call    ?MaybeShowActivationErrorPopupIfCritical@@YAJJW4_PackageOrigin@@PEBGW4ACTIVATION_PHASE@@PEAW4ACTIVATIONERROR_DISMISS_METHOD@@@Z; MaybeShowActivationErrorPopupIfCritical(long,_PackageOrigin,ushort const *,ACTIVATION_PHASE,ACTIVATIONERROR_DISMISS_METHOD *)
0x180161f26  mov     ebx, eax
0x180161f28  test    eax, eax
0x180161f2a  jns     loc_180161C6B
0x180161f30  mov     ecx, eax; int
0x180161f32  call    ?ShouldLaunchStoreForError@@YA_NJ@Z; ShouldLaunchStoreForError(long)
0x180161f37  test    al, al
  ... truncated ...
```
