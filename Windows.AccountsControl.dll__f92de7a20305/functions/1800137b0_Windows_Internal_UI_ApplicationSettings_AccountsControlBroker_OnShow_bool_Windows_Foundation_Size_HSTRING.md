# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::OnShow(bool *,Windows::Foundation::Size *,HSTRING__ * *)

- ea: `0x1800137b0`
- end: `0x1800141d9`
- name: `?OnShow@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@EEAAJPEA_NPEAUSize@Foundation@5@PEAPEAUHSTRING__@@@Z`
- size: `2601`
- prototype: `int(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, bool *, struct Windows::Foundation::Size *, HSTRING *)`
- caller_count: `0`
- callee_count: `38`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006eac`
- `0x180008088`
- `0x180008d78`
- `0x180009174`
- `0x1800091fc`
- `0x18000a084`
- `0x18000aa50`
- `0x18000ab30`
- `0x18000abe0`
- `0x18000c14c`
- `0x18000c258`
- `0x18000c798`
- `0x18000d610`
- `0x18000e87c`
- `0x18000fc40`
- `0x180010594`
- `0x18001113c`
- `0x180011f88`
- `0x180011ffc`
- `0x180012028`
- `0x1800123bc`
- `0x1800137b0`
- `0x180015850`
- `0x180015c60`
- `0x180015d98`
- `0x180015ed0`
- `0x180016438`
- `0x180017094`
- `0x18001745c`
- `0x180017e68`
- `0x1800183c0`
- `0x180018c04`
- `0x180018f90`
- `0x180041130`
- `0x180067f50`
- `0x1800680a0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800138dd`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800138dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001406e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800140bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001416b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001406e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800140bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001416b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001413d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001413d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013dd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013dd6`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180013df1`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180013df1`

## string_xrefs

- `0x180013eb4`: `Windows.Internal.UI.ApplicationSettings.AccountsControlIconCache`
- `0x180013824`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013913`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800139af`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013a42`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013b2a`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013c22`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013d25`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013e25`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013edd`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180013fa9`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180014040`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::OnShow(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        bool *a2,
        struct Windows::Foundation::Size *a3,
        HSTRING *a4)
{
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v6; // r14
  _QWORD *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  int IsCallingProcessAppContainer; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdi
  void (__fastcall *v17)(__int64, __int64); // rbx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned __int16 **v21; // rdx
  int CallingProcessPackageFamilyName; // eax
  __int64 v23; // rdx
  PVOID Reserved1; // rdi
  int FilteredTokenBrokerAccounts; // eax
  __int64 v26; // rdx
  _QWORD *v27; // r15
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdx
  unsigned __int64 v33; // r9
  const unsigned __int16 *v34; // rdx
  HKEY v35; // rcx
  const unsigned __int16 *v36; // r8
  unsigned int v37; // r9d
  int SupportedProviderTypes; // eax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, __int64 *); // rbx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 *v44; // rax
  __int64 v45; // rbx
  DWORD CurrentThreadId; // eax
  int v47; // edi
  int v48; // eax
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v49; // rcx
  __int64 v50; // rdx
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64, HSTRING *); // rbx
  HRESULT v56; // eax
  __int64 v57; // rdx
  __int64 (__fastcall *v58)(__int64, __int64, HSTRING *); // rbx
  int v59; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v60[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v61; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v62; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v63; // [rsp+48h] [rbp-B8h] BYREF
  char v64; // [rsp+49h] [rbp-B7h] BYREF
  _BYTE v65[6]; // [rsp+4Ah] [rbp-B6h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v67[8]; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Internal::UI::ApplicationSettings::IAccountsControlIconCache *v68; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+68h] [rbp-98h] BYREF
  __int64 v70; // [rsp+70h] [rbp-90h] BYREF
  int v71; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+80h] [rbp-80h] BYREF
  PVOID v73; // [rsp+88h] [rbp-78h] BYREF
  int v74; // [rsp+90h] [rbp-70h] BYREF
  bool *v75; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v76; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v79; // [rsp+C8h] [rbp-38h]
  _QWORD v80[34]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v81; // [rsp+1E0h] [rbp+E0h]
  _QWORD v82[42]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v83[42]; // [rsp+370h] [rbp+270h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v75 = a2;
  *a4 = 0;
  v6 = (Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *)((char *)this - 32);
  v7 = (_QWORD *)((char *)this + 960);
  v8 = (*(__int64 (__fastcall **)(_QWORD, char *, struct Windows::Foundation::Size *))(**((_QWORD **)this + 74) + 128LL))(
         *((_QWORD *)this + 74),
         (char *)this + 960,
         a3);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v8,
      v59);
    return v9;
  }
  wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v80);
  v80[0] = &AccountsControlTelemetry::AccountsControlBrokerActivity::`vftable';
  v11 = *v7 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *v7 == *(_QWORD *)&GUID_NULL.Data1 )
    v11 = *((_QWORD *)this + 121) - *(_QWORD *)GUID_NULL.Data4;
  if ( v11 )
  {
    wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      v80,
      &v73);
    v12 = v81;
    *(_OWORD *)(v81 + 24) = *(_OWORD *)v7;
    *(_BYTE *)(v12 + 4) = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v73);
  }
  v63 = 0;
  IsCallingProcessAppContainer = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *))(**((_QWORD **)this + 74) + 112LL))(
                                   *((_QWORD *)this + 74),
                                   &v63);
  v14 = IsCallingProcessAppContainer;
  if ( IsCallingProcessAppContainer >= 0 )
  {
    AccountsControlTelemetry::AccountsControlBrokerActivity::StartActivity(
      (AccountsControlTelemetry::AccountsControlBrokerActivity *)v80,
      v63);
    v16 = *((_QWORD *)this + 74);
    v17 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 216LL);
    LOBYTE(v18) = (unsigned __int8)RtlIsMultiUsersInSessionSku() != 0;
    v17(v16, v18);
    v60[0] = 0;
    IsCallingProcessAppContainer = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyAccountsControlData(
                                     v6,
                                     (bool *)v60);
    v14 = IsCallingProcessAppContainer;
    if ( IsCallingProcessAppContainer < 0 )
    {
      v15 = 340;
      goto LABEL_11;
    }
    if ( !v60[0] )
    {
      AccountsControlTelemetry::AccountsControlBrokerActivity::WrongUser((AccountsControlTelemetry::AccountsControlBrokerActivity *)v80);
      wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(v80);
      v14 = -2147024891;
      v20 = 2147942405LL;
      v15 = 345;
      goto LABEL_12;
    }
    v60[0] = 0;
    IsCallingProcessAppContainer = CallerIdentity::IsCallingProcessAppContainer(v19, v60);
    v14 = IsCallingProcessAppContainer;
    if ( IsCallingProcessAppContainer < 0 )
    {
      v15 = 351;
      goto LABEL_11;
    }
    if ( v60[0] )
    {
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
      CallingProcessPackageFamilyName = CallerIdentity::GetCallingProcessPackageFamilyName(
                                          (CallerIdentity *)&hstringHeader,
                                          v21);
      v14 = CallingProcessPackageFamilyName;
      if ( CallingProcessPackageFamilyName < 0 )
      {
        v23 = 360;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)CallingProcessPackageFamilyName,
          v59);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        goto LABEL_98;
      }
      Reserved1 = hstringHeader.Reserved.Reserved1;
      v73 = hstringHeader.Reserved.Reserved1;
      CallingProcessPackageFamilyName = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
                                          (char *)this + 608,
                                          &v73);
      v14 = CallingProcessPackageFamilyName;
      if ( CallingProcessPackageFamilyName < 0 )
      {
        v23 = 361;
        goto LABEL_20;
      }
      v73 = Reserved1;
      AccountsControlTelemetry::AccountsControlBrokerActivity::InvokedFromAppContainer<unsigned short const *>(
        v80,
        &v73);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
    }
    v61 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    FilteredTokenBrokerAccounts = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetFilteredTokenBrokerAccounts(v6);
    v14 = FilteredTokenBrokerAccounts;
    if ( FilteredTokenBrokerAccounts < 0 )
    {
      v26 = 368;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)FilteredTokenBrokerAccounts,
        v59);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      goto LABEL_98;
    }
    v76 = 0;
    FilteredTokenBrokerAccounts = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 74) + 144LL))(
                                    *((_QWORD *)this + 74),
                                    &v76);
    v14 = FilteredTokenBrokerAccounts;
    if ( FilteredTokenBrokerAccounts < 0 )
    {
      v26 = 371;
      goto LABEL_26;
    }
    v27 = (_QWORD *)((char *)this + 616);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 616);
    FilteredTokenBrokerAccounts = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetInternalAccountDataCollectionForTokenBrokerAccounts(
                                    v28,
                                    v76,
                                    v61,
                                    (char *)this + 616);
    v14 = FilteredTokenBrokerAccounts;
    if ( FilteredTokenBrokerAccounts < 0 )
    {
      v26 = 372;
      goto LABEL_26;
    }
    AccountsControlTelemetry::AccountsControlBrokerActivity::TokenBrokerAccountsFiltered((AccountsControlTelemetry::AccountsControlBrokerActivity *)v80);
    v74 = 0;
    FilteredTokenBrokerAccounts = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v27 + 56LL))(*v27, &v74);
    v14 = FilteredTokenBrokerAccounts;
    if ( FilteredTokenBrokerAccounts < 0 )
    {
      v26 = 376;
      goto LABEL_26;
    }
    v62 = 0;
    v29 = *((_QWORD *)this + 74);
    v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v31 = v30(v29, &v62);
    v14 = v31;
    if ( v31 < 0 )
    {
      v32 = 379;
LABEL_36:
      v33 = (unsigned int)v31;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)v33,
        v59);
LABEL_38:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      goto LABEL_27;
    }
    v64 = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 74) + 160LL))(*((_QWORD *)this + 74), &v64);
    v14 = v31;
    if ( v31 < 0 )
    {
      v32 = 385;
      goto LABEL_36;
    }
    if ( v64 )
    {
      v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 120LL))(v62);
      v14 = v31;
      if ( v31 < 0 )
      {
        v32 = 388;
        goto LABEL_36;
      }
    }
    v71 = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 56LL))(v62, &v71);
    v14 = v31;
    if ( v31 < 0 )
    {
      v32 = 392;
      goto LABEL_36;
    }
    if ( !v71 && !v74 )
    {
      v69 = 0;
      if ( (int)SHRegGetBOOLWithREGSAM(v35, v34, v36, v37, &v69) < 0 || !v69 )
      {
        v60[0] = 0;
        v67[0] = 0;
        SupportedProviderTypes = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetSupportedProviderTypes(
                                   v6,
                                   v67,
                                   v60);
        v14 = SupportedProviderTypes;
        if ( SupportedProviderTypes < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x389,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
            (const char *)(unsigned int)SupportedProviderTypes,
            v59);
          v33 = v14;
          v32 = 399;
          goto LABEL_37;
        }
      }
    }
    wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v82);
    v82[0] = &AccountsControlTelemetry::AccountsControlBrokerActivity::`vftable';
    wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v83);
    v83[0] = &AccountsControlTelemetry::AccountsControlBrokerActivity::`vftable';
    wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::operator=(
      (char *)this + 624,
      v82);
    AccountsControlTelemetry::AccountsControlBrokerActivity::~AccountsControlBrokerActivity((AccountsControlTelemetry::AccountsControlBrokerActivity *)v83);
    AccountsControlTelemetry::AccountsControlBrokerActivity::~AccountsControlBrokerActivity((AccountsControlTelemetry::AccountsControlBrokerActivity *)v82);
    v65[0] = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 74) + 192LL))(*((_QWORD *)this + 74), v65);
    v14 = v31;
    if ( v31 < 0 )
    {
      v32 = 405;
      goto LABEL_36;
    }
    if ( v65[0] )
    {
      v72 = 0;
      v39 = *((_QWORD *)this + 74);
      v40 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      v41 = v40(v39, &v72);
      v14 = v41;
      if ( v41 < 0 )
      {
        v42 = 413;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v41,
          v59);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        goto LABEL_38;
      }
      v69 = 0;
      v41 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v72 + 56LL))(v72, &v69);
      v14 = v41;
      if ( v41 < 0 )
      {
        v42 = 416;
        goto LABEL_57;
      }
      if ( v69 == 1 && !v71 && !v74 )
      {
        v75 = (bool *)v6;
        Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalAddRef(&v75);
        v43 = lambda_75ac70275f71133639fd38ca86a04493_::_lambda_75ac70275f71133639fd38ca86a04493_(
                &hstringHeader,
                &v75,
                v6);
        v44 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_75ac70275f71133639fd38ca86a04493_____lambda_75ac70275f71133639fd38ca86a04493___(
                           &v73,
                           v43);
        v45 = *v44;
        v77 = *v44;
        *v44 = 0;
        if ( v73 )
        {
          v73 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release();
        }
        CurrentThreadId = GetCurrentThreadId();
        v47 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalRelease(&hstringHeader);
        if ( v47 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalRelease(&v75);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
          v14 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B1,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
            (const char *)(unsigned int)v47,
            v45);
          Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::AccountsControlBroker>::InternalRelease(&v75);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
          v14 = v47;
        }
        goto LABEL_98;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    }
    v68 = 0;
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.UI.ApplicationSettings.AccountsControlIconCache",
      0x41u,
      0x40u);
    v48 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlIconCache>>(
            v79,
            &v68);
    v14 = v48;
    if ( v48 < 0 )
    {
      v50 = 440;
LABEL_73:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v48,
        v59);
LABEL_74:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      goto LABEL_38;
    }
    v48 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::ResolveIconsForProviders(
            v49,
            v68,
            *((struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData **)this + 74));
    v14 = v48;
    if ( v48 < 0 )
    {
      v50 = 442;
      goto LABEL_73;
    }
    v48 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::ResolveIconsForCustomAccounts(
            v51,
            v68,
            *((struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData **)this + 74));
    v14 = v48;
    if ( v48 < 0 )
    {
      v50 = 443;
      goto LABEL_73;
    }
    v48 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::ResolveIconsForTokenBrokerAccounts(
            v52,
            v68,
            *v27);
    v14 = v48;
    if ( v48 < 0 )
    {
      v50 = 444;
      goto LABEL_73;
    }
    AccountsControlTelemetry::AccountsControlBrokerActivity::AccountsControlAppLaunched((Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *)((char *)this + 624));
    *v75 = 1;
    v70 = 0;
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.ApplicationModel.Sync.AccountsResourceHelper",
      0x3Eu,
      0x3Du);
    v53 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(
            v79,
            &v70);
    v14 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v53,
        v59);
LABEL_83:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      goto LABEL_74;
    }
    string = 0;
    v54 = v70;
    if ( v71 )
    {
      v58 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v70 + 80LL);
      if ( v71 == 1 )
      {
        WindowsDeleteString(0);
        string = 0;
        v79 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"WindowTitleOneAccount",
          0x16u,
          0x15u);
        v56 = v58(v54, v79, &string);
        v14 = v56;
        if ( v56 < 0 )
        {
          v57 = 460;
          goto LABEL_87;
        }
      }
      else
      {
        WindowsDeleteString(0);
        string = 0;
        v79 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"WindowTitleMoreAccounts",
          0x18u,
          0x17u);
        v56 = v58(v54, v79, &string);
        v14 = v56;
        if ( v56 < 0 )
        {
          v57 = 464;
          goto LABEL_87;
        }
      }
    }
    else
    {
      v55 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v70 + 80LL);
      WindowsDeleteString(0);
      string = 0;
      v79 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SignInWindowTitle", 0x12u, 0x11u);
      v56 = v55(v54, v79, &string);
      v14 = v56;
      if ( v56 < 0 )
      {
        v57 = 456;
LABEL_87:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v57,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v56,
          v59);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_83;
      }
    }
    v56 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 74) + 168LL))(
            *((_QWORD *)this + 74),
            string);
    v14 = v56;
    if ( v56 >= 0 )
    {
      v56 = WindowsDuplicateString(string, a4);
      v14 = v56;
      if ( v56 >= 0 )
      {
        ViewOperationBase::SetAccountsControlData(this, *((_QWORD *)this + 74), *v27);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
        v14 = 0;
        goto LABEL_98;
      }
      v57 = 468;
    }
    else
    {
      v57 = 467;
    }
    goto LABEL_87;
  }
  v15 = 334;
LABEL_11:
  v20 = (unsigned int)IsCallingProcessAppContainer;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)v20,
    v59);
LABEL_98:
  AccountsControlTelemetry::AccountsControlBrokerActivity::~AccountsControlBrokerActivity((AccountsControlTelemetry::AccountsControlBrokerActivity *)v80);
  return v14;
}

```

## disassembly

```asm
0x1800137b0  mov     [rsp-8+arg_10], rbx
0x1800137b5  push    rbp
0x1800137b6  push    rsi
0x1800137b7  push    rdi
0x1800137b8  push    r12
0x1800137ba  push    r13
0x1800137bc  push    r14
0x1800137be  push    r15
0x1800137c0  lea     rbp, [rsp-3D0h]
0x1800137c8  sub     rsp, 4D0h
0x1800137cf  mov     rax, cs:__security_cookie
0x1800137d6  xor     rax, rsp
0x1800137d9  mov     [rbp+400h+var_40], rax
0x1800137e0  mov     r13, r9
0x1800137e3  mov     [rbp+400h+var_468], rdx
0x1800137e7  mov     rsi, rcx
0x1800137ea  xor     r12d, r12d
0x1800137ed  mov     [r9], r12
0x1800137f0  lea     r14, [rcx-20h]
0x1800137f4  mov     rcx, [r14+270h]
0x1800137fb  lea     rbx, [rsi+3C0h]
0x180013802  mov     rax, [rcx]
0x180013805  mov     rdx, rbx
0x180013808  mov     rax, [rax+80h]
0x18001380f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013814  mov     edi, eax
0x180013816  test    eax, eax
0x180013818  jns     short loc_18001383C
0x18001381a  mov     rcx, [rbp+408h]; this
0x180013821  mov     r9d, eax; char *
0x180013824  lea     r8, aOnecoreuapShel_27
0x18001382b  mov     edx, 145h; void *
0x180013830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180013835  mov     eax, edi
0x180013837  jmp     loc_1800141AF
0x18001383c  lea     rcx, [rbp+400h+var_430]; struct wil::details::IFailureCallback *
0x180013840  call    ??0?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z
0x180013845  lea     rax, ??_7AccountsControlBrokerActivity@AccountsControlTelemetry@@6B@
0x18001384c  mov     [rbp+400h+var_430], rax
0x180013850  mov     rax, [rbx]
0x180013853  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18001385a  jnz     short loc_180013867
0x18001385c  mov     rax, [rbx+8]
0x180013860  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180013867  test    rax, rax
0x18001386a  jz      short loc_180013895
0x18001386c  lea     rdx, [rbp+400h+var_478]
0x180013870  lea     rcx, [rbp+400h+var_430]
0x180013874  call    ?LockExclusive@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x180013879  mov     rax, [rbp+400h+var_320]
0x180013880  movups  xmm0, xmmword ptr [rbx]
0x180013883  movdqu  xmmword ptr [rax+18h], xmm0
0x180013888  mov     byte ptr [rax+4], 1
0x18001388c  lea     rcx, [rbp+400h+var_478]
0x180013890  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013895  mov     [rsp+500h+var_4B8], r12b
0x18001389a  mov     rcx, [rsi+250h]
0x1800138a1  mov     rax, [rcx]
0x1800138a4  lea     rdx, [rsp+500h+var_4B8]
0x1800138a9  mov     rax, [rax+70h]
0x1800138ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b2  mov     ebx, eax
0x1800138b4  test    eax, eax
0x1800138b6  jns     short loc_1800138BF
0x1800138b8  mov     edx, 14Eh
0x1800138bd  jmp     short loc_180013910
0x1800138bf  mov     dl, [rsp+500h+var_4B8]; unsigned __int8
0x1800138c3  lea     rcx, [rbp+400h+var_430]; this
0x1800138c7  call    ?StartActivity@AccountsControlBrokerActivity@AccountsControlTelemetry@@QEAAXE@Z
0x1800138cc  mov     rdi, [rsi+250h]
0x1800138d3  mov     rax, [rdi]
0x1800138d6  mov     rbx, [rax+0D8h]
0x1800138dd  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800138e3  test    al, al
0x1800138e5  setnz   dl
0x1800138e8  mov     rcx, rdi
0x1800138eb  mov     rax, rbx
0x1800138ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f3  mov     [rsp+500h+var_4D0], r12b
0x1800138f8  lea     rdx, [rsp+500h+var_4D0]; bool *
0x1800138fd  mov     rcx, r14; this
0x180013900  call    ?VerifyAccountsControlData@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEA_N@Z
0x180013905  mov     ebx, eax
0x180013907  test    eax, eax
0x180013909  jns     short loc_18001392B
0x18001390b  mov     edx, 154h; void *
0x180013910  mov     r9d, eax; char *
0x180013913  lea     r8, aOnecoreuapShel_27
0x18001391a  mov     rcx, [rbp+408h]; this
0x180013921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180013926  jmp     loc_1800141A4
0x18001392b  cmp     [rsp+500h+var_4D0], r12b
0x180013930  jnz     short loc_180013953
0x180013932  lea     rcx, [rbp+400h+var_430]; this
0x180013936  call    ?WrongUser@AccountsControlBrokerActivity@AccountsControlTelemetry@@QEAAXXZ
0x18001393b  lea     rcx, [rbp+400h+var_430]
0x18001393f  call    ?Stop@?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z
0x180013944  mov     ebx, 80070005h
0x180013949  mov     r9d, ebx
0x18001394c  mov     edx, 159h
0x180013951  jmp     short loc_180013913
0x180013953  mov     [rsp+500h+var_4D0], r12b
0x180013958  lea     rdx, [rsp+500h+var_4D0]
0x18001395d  call    ?IsCallingProcessAppContainer@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEA_N@Z
0x180013962  mov     ebx, eax
0x180013964  test    eax, eax
0x180013966  jns     short loc_18001396F
0x180013968  mov     edx, 15Fh
0x18001396d  jmp     short loc_180013910
0x18001396f  cmp     [rsp+500h+var_4D0], r12b
0x180013974  jz      loc_180013A14
0x18001397a  mov     qword ptr [rbp+400h+hstringHeader.Reserved], r12
0x18001397e  mov     qword ptr [rbp+400h+hstringHeader.Reserved+8], r12
0x180013982  mov     qword ptr [rbp+400h+hstringHeader.Reserved+10h], r12
0x180013986  lea     rcx, [rbp+400h+hstringHeader]
0x18001398a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x18001398f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013993  mov     qword ptr [rbp+400h+hstringHeader.Reserved+8], rax
0x180013997  mov     qword ptr [rbp+400h+hstringHeader.Reserved+10h], rax
0x18001399b  lea     rcx, [rbp+400h+hstringHeader]; this
0x18001399f  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z
0x1800139a4  mov     ebx, eax
0x1800139a6  test    eax, eax
0x1800139a8  jns     short loc_1800139D4
0x1800139aa  mov     edx, 168h; void *
0x1800139af  lea     r8, aOnecoreuapShel_27
0x1800139b6  mov     r9d, eax; char *
0x1800139b9  mov     rcx, [rbp+408h]; this
0x1800139c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800139c5  nop
0x1800139c6  lea     rcx, [rbp+400h+hstringHeader]
0x1800139ca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x1800139cf  jmp     loc_1800141A4
0x1800139d4  mov     rdi, qword ptr [rbp+400h+hstringHeader.Reserved]
0x1800139d8  mov     [rbp+400h+var_478], rdi
0x1800139dc  lea     rcx, [rsi+260h]
0x1800139e3  lea     rdx, [rbp+400h+var_478]
0x1800139e7  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z
0x1800139ec  mov     ebx, eax
0x1800139ee  test    eax, eax
0x1800139f0  jns     short loc_1800139F9
0x1800139f2  mov     edx, 169h
0x1800139f7  jmp     short loc_1800139AF
0x1800139f9  mov     [rbp+400h+var_478], rdi
0x1800139fd  lea     rdx, [rbp+400h+var_478]
0x180013a01  lea     rcx, [rbp+400h+var_430]
0x180013a05  call    ??$InvokedFromAppContainer@PEBG@AccountsControlBrokerActivity@AccountsControlTelemetry@@QEAAX$$QEAPEBG@Z
0x180013a0a  nop
0x180013a0b  lea     rcx, [rbp+400h+hstringHeader]
0x180013a0f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ
0x180013a14  mov     [rsp+500h+var_4C8], r12
0x180013a19  lea     rcx, [rsp+500h+var_4C8]
0x180013a1e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180013a23  lea     r8, [rsp+500h+var_4C8]
0x180013a28  mov     rdx, [rsi+250h]
0x180013a2f  mov     rcx, r14; this
0x180013a32  call    ?GetFilteredTokenBrokerAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIAccountsControlData@2345@PEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z
0x180013a37  mov     ebx, eax
0x180013a39  test    eax, eax
0x180013a3b  jns     short loc_180013A68
0x180013a3d  mov     edx, 170h; void *
0x180013a42  lea     r8, aOnecoreuapShel_27
0x180013a49  mov     r9d, eax; char *
0x180013a4c  mov     rcx, [rbp+408h]; this
0x180013a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180013a58  nop
0x180013a59  lea     rcx, [rsp+500h+var_4C8]
0x180013a5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180013a63  jmp     loc_1800141A4
0x180013a68  mov     [rbp+400h+var_460], r12d
0x180013a6c  mov     rcx, [rsi+250h]
0x180013a73  mov     rax, [rcx]
0x180013a76  lea     rdx, [rbp+400h+var_460]
0x180013a7a  mov     rax, [rax+90h]
0x180013a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a86  mov     ebx, eax
0x180013a88  test    eax, eax
0x180013a8a  jns     short loc_180013A93
0x180013a8c  mov     edx, 173h
0x180013a91  jmp     short loc_180013A42
0x180013a93  lea     r15, [rsi+268h]
0x180013a9a  mov     rcx, r15
0x180013a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180013aa2  mov     r9, r15
0x180013aa5  mov     r8, [rsp+500h+var_4C8]
0x180013aaa  mov     edx, [rbp+400h+var_460]
0x180013aad  call    ?GetInternalAccountDataCollectionForTokenBrokerAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJIPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAPEAU?$IVectorView@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@785@@Z
0x180013ab2  mov     ebx, eax
0x180013ab4  test    eax, eax
0x180013ab6  jns     short loc_180013ABF
0x180013ab8  mov     edx, 174h
0x180013abd  jmp     short loc_180013A42
0x180013abf  lea     rcx, [rbp+400h+var_430]; this
0x180013ac3  call    ?TokenBrokerAccountsFiltered@AccountsControlBrokerActivity@AccountsControlTelemetry@@QEAAXXZ
0x180013ac8  mov     [rbp+400h+var_470], r12d
0x180013acc  mov     rcx, [r15]
0x180013acf  mov     rax, [rcx]
0x180013ad2  lea     rdx, [rbp+400h+var_470]
0x180013ad6  mov     rax, [rax+38h]
0x180013ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013adf  mov     ebx, eax
0x180013ae1  test    eax, eax
0x180013ae3  jns     short loc_180013AEF
0x180013ae5  mov     edx, 178h
0x180013aea  jmp     loc_180013A42
0x180013aef  mov     [rsp+500h+var_4C0], r12
0x180013af4  mov     rdi, [rsi+250h]
0x180013afb  mov     rax, [rdi]
0x180013afe  mov     rbx, [rax+38h]
0x180013b02  lea     rcx, [rsp+500h+var_4C0]
0x180013b07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180013b0c  lea     rdx, [rsp+500h+var_4C0]
0x180013b11  mov     rcx, rdi
0x180013b14  mov     rax, rbx
0x180013b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b1c  mov     ebx, eax
0x180013b1e  test    eax, eax
0x180013b20  jns     short loc_180013B4D
0x180013b22  mov     edx, 17Bh; void *
0x180013b27  mov     r9d, eax; char *
0x180013b2a  lea     r8, aOnecoreuapShel_27
0x180013b31  mov     rcx, [rbp+408h]; this
0x180013b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180013b3d  nop
0x180013b3e  lea     rcx, [rsp+500h+var_4C0]
0x180013b43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180013b48  jmp     loc_180013A59
0x180013b4d  mov     [rsp+500h+var_4B7], r12b
0x180013b52  mov     rcx, [rsi+250h]
0x180013b59  mov     rax, [rcx]
0x180013b5c  lea     rdx, [rsp+500h+var_4B7]
0x180013b61  mov     rax, [rax+0A0h]
0x180013b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b6d  mov     ebx, eax
0x180013b6f  test    eax, eax
0x180013b71  jns     short loc_180013B7A
0x180013b73  mov     edx, 181h
0x180013b78  jmp     short loc_180013B27
0x180013b7a  cmp     [rsp+500h+var_4B7], r12b
0x180013b7f  jz      short loc_180013B9F
0x180013b81  mov     rcx, [rsp+500h+var_4C0]
0x180013b86  mov     rax, [rcx]
0x180013b89  mov     rax, [rax+78h]
0x180013b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b92  mov     ebx, eax
0x180013b94  test    eax, eax
0x180013b96  jns     short loc_180013B9F
0x180013b98  mov     edx, 184h
0x180013b9d  jmp     short loc_180013B27
0x180013b9f  mov     [rsp+500h+var_488], r12d
0x180013ba4  mov     rcx, [rsp+500h+var_4C0]
0x180013ba9  mov     rax, [rcx]
0x180013bac  lea     rdx, [rsp+500h+var_488]
0x180013bb1  mov     rax, [rax+38h]
0x180013bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bba  mov     ebx, eax
0x180013bbc  test    eax, eax
0x180013bbe  jns     short loc_180013BCA
0x180013bc0  mov     edx, 188h
0x180013bc5  jmp     loc_180013B27
0x180013bca  cmp     [rsp+500h+var_488], r12d
0x180013bcf  jnz     short loc_180013C40
0x180013bd1  cmp     [rbp+400h+var_470], r12d
0x180013bd5  jnz     short loc_180013C40
0x180013bd7  mov     [rsp+500h+var_498], r12d
0x180013bdc  lea     rax, [rsp+500h+var_498]
0x180013be1  mov     [rsp+500h+var_4E0], rax; int
0x180013be6  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z
0x180013beb  test    eax, eax
0x180013bed  js      short loc_180013BF6
0x180013bef  cmp     [rsp+500h+var_498], r12d
0x180013bf4  jnz     short loc_180013C40
0x180013bf6  mov     [rsp+500h+var_4D0], r12b
0x180013bfb  mov     [rsp+500h+var_4A8], r12b
0x180013c00  lea     r8, [rsp+500h+var_4D0]; unsigned __int8 *
0x180013c05  lea     rdx, [rsp+500h+var_4A8]; unsigned __int8 *
0x180013c0a  mov     rcx, r14; this
0x180013c0d  call    ?GetSupportedProviderTypes@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAE0@Z
0x180013c12  mov     ebx, eax
0x180013c14  test    eax, eax
0x180013c16  jns     short loc_180013C40
0x180013c18  mov     rcx, [rbp+408h]; this
0x180013c1f  mov     r9d, eax; char *
0x180013c22  lea     r8, aOnecoreuapShel_27
0x180013c29  mov     edx, 389h; void *
0x180013c2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180013c33  mov     r9d, ebx
0x180013c36  mov     edx, 18Fh
0x180013c3b  jmp     loc_180013B2A
0x180013c40  xor     r8d, r8d
0x180013c43  lea     rdx, [rbp+400h+var_430]
0x180013c47  lea     rcx, [rbp+400h+var_2E0]; struct wil::details::IFailureCallback *
0x180013c4e  call    ??0?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z
0x180013c53  lea     rbx, ??_7AccountsControlBrokerActivity@AccountsControlTelemetry@@6B@
0x180013c5a  mov     [rbp+400h+var_2E0], rbx
0x180013c61  lea     r12, [rsi+270h]
0x180013c68  xor     edi, edi
0x180013c6a  cmp     [r12+138h], edi
0x180013c72  setnz   r8b
0x180013c76  mov     rdx, r12
  ... truncated ...
```
