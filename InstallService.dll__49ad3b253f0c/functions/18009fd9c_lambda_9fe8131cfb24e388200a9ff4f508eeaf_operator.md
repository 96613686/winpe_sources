# _lambda_9fe8131cfb24e388200a9ff4f508eeaf_::operator()

- ea: `0x18009fd9c`
- end: `0x1800a0979`
- name: `_lambda_9fe8131cfb24e388200a9ff4f508eeaf_::operator()`
- size: `3037`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800be840`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800111c8`
- `0x18001c414`
- `0x180037200`
- `0x180042b9c`
- `0x180044f10`
- `0x1800453bc`
- `0x180045588`
- `0x18004c5d8`
- `0x180052268`
- `0x18006cc00`
- `0x18006cc2c`
- `0x18006e510`
- `0x180082af0`
- `0x18008babc`
- `0x18008c8e8`
- `0x18008fc28`
- `0x180091754`
- `0x18009fd9c`
- `0x1800a86bc`
- `0x1800ad5e8`
- `0x1800b1a84`
- `0x1800b2d60`
- `0x1800b4410`
- `0x1800b50a8`
- `0x1800b63c0`
- `0x1800bf170`
- `0x1800c12a0`
- `0x1800c893c`
- `0x1800cc51c`
- `0x1800cd008`
- `0x1800d1d30`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fdfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a04eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a05e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a070a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a07c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0943`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fdfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a04eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a05e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a070a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a07c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0943`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ff74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ff74`

## string_xrefs

- `0x1800a0920`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800a0913`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithPausedAddAsync::<lambda_9fe8131cfb24e388200a9ff4f508eeaf>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall lambda_9fe8131cfb24e388200a9ff4f508eeaf_::operator()(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  _QWORD *v3; // r12
  _QWORD *v4; // r13
  HSTRING *v5; // r15
  HSTRING v6; // rbx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rdi
  unsigned int v13; // eax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  unsigned int v16; // eax
  wchar_t *StringRawBuffer; // rax
  bool v18; // r8
  bool IsCallerInteractive; // di
  int InstallControl2; // esi
  const unsigned __int16 *v21; // rax
  struct WindowsUpdate::Internal::IInstallItem **v22; // rcx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v23; // rdi
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // edi
  const unsigned __int16 *v27; // rax
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v28; // rdi
  unsigned int v29; // eax
  unsigned int v30; // eax
  int v31; // eax
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rdi
  unsigned int v34; // eax
  unsigned int v35; // eax
  const char *v36; // r9
  __int64 result; // rax
  int View; // r15d
  __int64 v39; // rdx
  __int64 v40; // rcx
  unsigned int v41; // r12d
  __int64 v42; // rsi
  int (__fastcall *v43)(__int64, _QWORD, struct WindowsUpdate::Internal::IInstallItem **); // rdi
  struct WindowsUpdate::Internal::IInstallItem *v44; // rsi
  int (__fastcall *v45)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *); // rdi
  HSTRING v46; // rsi
  int (__fastcall *v47)(HSTRING, HSTRING *); // rdi
  __int64 v48; // rdi
  __int64 v49; // rax
  __int64 v50; // rdi
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v51; // rdi
  __int64 v52; // r9
  const unsigned __int16 *v53; // rax
  TraceLoggingCorrelationVector *v54; // [rsp+20h] [rbp-2F8h]
  unsigned __int16 *v55; // [rsp+28h] [rbp-2F0h]
  char *v56; // [rsp+30h] [rbp-2E8h]
  char v57; // [rsp+50h] [rbp-2C8h] BYREF
  char v58; // [rsp+51h] [rbp-2C7h] BYREF
  bool v59; // [rsp+52h] [rbp-2C6h] BYREF
  bool v60; // [rsp+53h] [rbp-2C5h] BYREF
  int v61; // [rsp+54h] [rbp-2C4h] BYREF
  HSTRING string; // [rsp+58h] [rbp-2C0h] BYREF
  HSTRING v63; // [rsp+60h] [rbp-2B8h] BYREF
  __int64 v64; // [rsp+68h] [rbp-2B0h] BYREF
  __int64 v65; // [rsp+70h] [rbp-2A8h] BYREF
  HSTRING v66; // [rsp+78h] [rbp-2A0h] BYREF
  struct WindowsUpdate::Internal::IInstallItem *v67; // [rsp+80h] [rbp-298h] BYREF
  _QWORD *v68; // [rsp+88h] [rbp-290h] BYREF
  char v69[8]; // [rsp+90h] [rbp-288h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-280h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-278h] BYREF
  __int128 v72; // [rsp+A8h] [rbp-270h]
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v73; // [rsp+C0h] [rbp-258h] BYREF
  struct WindowsUpdate::Internal::IInstallItem *v74; // [rsp+C8h] [rbp-250h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v75; // [rsp+D0h] [rbp-248h] BYREF
  HSTRING v76; // [rsp+D8h] [rbp-240h]
  __int64 v77; // [rsp+E0h] [rbp-238h] BYREF
  __int128 v78; // [rsp+E8h] [rbp-230h] BYREF
  int v79; // [rsp+F8h] [rbp-220h] BYREF
  __int128 v80; // [rsp+100h] [rbp-218h] BYREF
  char v81[8]; // [rsp+110h] [rbp-208h] BYREF
  char v82[8]; // [rsp+118h] [rbp-200h] BYREF
  char v83[8]; // [rsp+120h] [rbp-1F8h] BYREF
  _QWORD *v84; // [rsp+128h] [rbp-1F0h]
  __int64 v85; // [rsp+130h] [rbp-1E8h]
  __int64 v86; // [rsp+140h] [rbp-1D8h]
  char v87[8]; // [rsp+148h] [rbp-1D0h] BYREF
  char v88[8]; // [rsp+150h] [rbp-1C8h] BYREF
  char v89[8]; // [rsp+158h] [rbp-1C0h] BYREF
  char v90[8]; // [rsp+160h] [rbp-1B8h] BYREF
  char v91[8]; // [rsp+168h] [rbp-1B0h] BYREF
  char v92[8]; // [rsp+170h] [rbp-1A8h] BYREF
  char v93[8]; // [rsp+178h] [rbp-1A0h] BYREF
  char v94[8]; // [rsp+180h] [rbp-198h] BYREF
  char v95[8]; // [rsp+188h] [rbp-190h] BYREF
  char v96[8]; // [rsp+190h] [rbp-188h] BYREF
  char v97[8]; // [rsp+198h] [rbp-180h] BYREF
  char v98[8]; // [rsp+1A0h] [rbp-178h] BYREF
  char v99[8]; // [rsp+1A8h] [rbp-170h] BYREF
  char v100[8]; // [rsp+1B0h] [rbp-168h] BYREF
  const winrt::hresult_error *v101; // [rsp+1B8h] [rbp-160h] BYREF
  _QWORD v102[4]; // [rsp+1C0h] [rbp-158h] BYREF
  _BYTE v103[32]; // [rsp+1E0h] [rbp-138h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+200h] [rbp-118h] BYREF
  WCHAR sourceString[24]; // [rsp+220h] [rbp-F8h] BYREF
  char v106[144]; // [rsp+250h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v2 = a2;
  v86 = a2;
  v3 = (_QWORD *)a1;
  v68 = (_QWORD *)a1;
  v84 = (_QWORD *)a1;
  v4 = (_QWORD *)a1;
  v85 = a2;
  v5 = (HSTRING *)(a1 + 48);
  v6 = *(HSTRING *)(a1 + 48);
  WindowsDeleteString(0);
  v76 = v6;
  v70 = 0;
  if ( Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(v7) )
  {
    v63 = 0;
    v64 = 0;
    LODWORD(v77) = 0;
    v78 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v64);
    v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>(
           v8,
           &v64);
    try
    {
      winrt::check_hresult(&v61, v9, &v77);
      v77 = v4[3];
      LODWORD(v78) = 0;
      *((_QWORD *)&v78 + 1) = 0;
      Windows::Foundation::Collections::end<Windows::Internal::StateRepository::Application *>(&v79);
      v31 = v78;
      while ( v31 != (_DWORD)v80 )
      {
        v10 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v77);
        v65 = 0;
        LODWORD(v71) = 0;
        v72 = 0;
        v11 = *(_QWORD *)v10;
        v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v10 + 48LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v65);
        v13 = v12(v11, &v65);
        winrt::check_hresult(&v61, v13, &v71);
        string = 0;
        LODWORD(v71) = 0;
        v72 = 0;
        v14 = v65;
        v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v65 + 104LL);
        WindowsDeleteString(0);
        string = 0;
        v16 = v15(v14, &string);
        winrt::check_hresult(v87, v16, &v71);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::GetImpl'::`2'::impl) )
        {
          StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(*v5, 0);
          IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, 0, v18);
          InstallControl2 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                              *v3,
                              v92);
          v58 = 1;
          v59 = *((_BYTE *)v3 + 32) == 0;
          v60 = 0;
          v57 = IsCallerInteractive;
          ToWinRTType<HSTRING__ *>(v82, v5);
          v66 = *(HSTRING *)(*v3 + 456LL);
          ToWinRTType<HSTRING__ *>(v81, &v66);
          v71 = *(_QWORD *)PluginHelpers::CreatePropertiesJson<PluginHelpers::WorkProperty::UserIdentityInfo,PluginHelpers::WorkProperty::CallerApplicationId,PluginHelpers::WorkProperty::IsInteractive,PluginHelpers::WorkProperty::OfflineShed,PluginHelpers::WorkProperty::AutomaticallyDownloadAndInstallUpdateIfFound,PluginHelpers::WorkProperty::StageButDoNotInstall>(
                             (unsigned int)v91,
                             (unsigned int)v81,
                             (unsigned int)v82,
                             (unsigned int)&v57,
                             (__int64)&v60,
                             (__int64)&v59,
                             (__int64)&v58);
          v66 = string;
          v102[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v90, &v66);
          v21 = (const unsigned __int16 *)AppId::IdTypeName(1);
          winrt::param::hstring::hstring((winrt::param::hstring *)v103, v21);
          *(_QWORD *)sourceString = *(_QWORD *)GetSidForIUser(v89, v3[2]);
          hstringHeader.Reserved.Reserved1 = *(PVOID *)GetCvString(v88, v3[5]);
          winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ScanForUpdate(
            InstallControl2,
            (unsigned int)&v74,
            (unsigned int)&hstringHeader,
            (unsigned int)sourceString,
            (__int64)v103,
            (__int64)v102,
            (__int64)&v71);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v88);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v89);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v90);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v91);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v81);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v82);
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v92);
          v66 = 0;
          if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v74, &v66) )
          {
            v73 = 0;
            LODWORD(v71) = 0;
            v72 = 0;
            v23 = (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)*v3;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v73);
            v24 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(
                    v23,
                    v74,
                    &v73);
            winrt::check_hresult(v100, v24, &v71);
            LODWORD(v71) = 0;
            v72 = 0;
            v25 = (*(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *))(*(_QWORD *)v64 + 104LL))(
                    v64,
                    v73);
            winrt::check_hresult(v98, v25, &v71);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v73);
          }
          v22 = &v74;
        }
        else
        {
          v26 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                  *v3,
                  v97);
          v57 = 1;
          v60 = *((_BYTE *)v3 + 32) == 0;
          v59 = 0;
          v58 = 1;
          ToWinRTType<HSTRING__ *>(&v68, v5);
          v66 = *(HSTRING *)(*v3 + 456LL);
          ToWinRTType<HSTRING__ *>(v83, &v66);
          hstringHeader.Reserved.Reserved1 = *(PVOID *)PluginHelpers::CreatePropertiesJson<PluginHelpers::WorkProperty::UserIdentityInfo,PluginHelpers::WorkProperty::CallerApplicationId,PluginHelpers::WorkProperty::IsInteractive,PluginHelpers::WorkProperty::OfflineShed,PluginHelpers::WorkProperty::AutomaticallyDownloadAndInstallUpdateIfFound,PluginHelpers::WorkProperty::StageButDoNotInstall>(
                                                         (unsigned int)v96,
                                                         (unsigned int)v83,
                                                         (unsigned int)&v68,
                                                         (unsigned int)&v58,
                                                         (__int64)&v59,
                                                         (__int64)&v60,
                                                         (__int64)&v57);
          v66 = string;
          *(_QWORD *)sourceString = *(_QWORD *)ToWinRTType<HSTRING__ *>(v95, &v66);
          v27 = (const unsigned __int16 *)AppId::IdTypeName(1);
          winrt::param::hstring::hstring((winrt::param::hstring *)v103, v27);
          v102[0] = *(_QWORD *)GetSidForIUser(v99, v3[2]);
          v71 = *(_QWORD *)GetCvString(v93, v3[5]);
          winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ScanForUpdate(
            v26,
            (unsigned int)&v67,
            (unsigned int)&v71,
            (unsigned int)v102,
            (__int64)v103,
            (__int64)sourceString,
            (__int64)&hstringHeader);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v93);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v99);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v95);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v96);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v83);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v68);
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v97);
          v66 = 0;
          if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v67, &v66) )
          {
            v75 = 0;
            LODWORD(v71) = 0;
            v72 = 0;
            v28 = (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)*v3;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v75);
            v29 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(
                    v28,
                    v67,
                    &v75);
            winrt::check_hresult(v94, v29, &v71);
            LODWORD(v71) = 0;
            v72 = 0;
            v30 = (*(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *))(*(_QWORD *)v64 + 104LL))(
                    v64,
                    v75);
            winrt::check_hresult(v69, v30, &v71);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v75);
          }
          v22 = &v67;
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v22);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v65);
        v31 = v78 + 1;
        LODWORD(v78) = v78 + 1;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)&v80 + 8);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)&v78 + 8);
      v79 = 0;
      v80 = 0;
      v32 = v64;
      v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 64LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v63);
      v34 = v33(v32, &v63);
      winrt::check_hresult(v69, v34, &v79);
      v79 = 0;
      v80 = 0;
      v35 = Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>::Set(
              v86,
              v63);
      winrt::check_hresult(v69, v35, &v79);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v70);
      WindowsDeleteString(v6);
      v76 = 0;
      result = 0;
    }
    catch ( const winrt::hresult_error *v101 )
    {
      v61 = *((_DWORD *)v101 + 3);
      View = v61;
      v6 = v76;
      v3 = v84;
      v2 = v85;
      v4 = v84;
      goto LABEL_33;
    }
    catch ( ... )
    {
      v61 = wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x1D63,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
              v36);
      View = v61;
      v6 = v76;
      v3 = v84;
      v2 = v85;
      v4 = v84;
      goto LABEL_33;
    }
  }
  else
  {
    if ( !v3[3] )
      goto LABEL_34;
    v64 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(&v64);
    View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(
             v40,
             v39,
             &v64);
    if ( View >= 0 )
    {
      v61 = 0;
      if ( (*(int (__fastcall **)(_QWORD, int *))(*(_QWORD *)v3[3] + 56LL))(v3[3], &v61) >= 0 )
      {
        v41 = 0;
        if ( v61 )
        {
          do
          {
            v67 = 0;
            v42 = v4[3];
            v43 = *(int (__fastcall **)(__int64, _QWORD, struct WindowsUpdate::Internal::IInstallItem **))(*(_QWORD *)v42 + 48LL);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v67);
            if ( v43(v42, v41, &v67) >= 0 )
            {
              string = 0;
              v44 = v67;
              v45 = *(int (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *))(*(_QWORD *)v67 + 48LL);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
              if ( v45(v44, &string) >= 0 )
              {
                v63 = 0;
                v46 = string;
                v47 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 104LL);
                WindowsDeleteString(0);
                v63 = 0;
                if ( v47(v46, &v63) >= 0 )
                {
                  v65 = 0;
                  if ( (*(int (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)string + 56LL))(string, &v65) >= 0 )
                  {
                    LODWORD(v56) = HIWORD(v65);
                    LODWORD(v55) = WORD2(v65);
                    LODWORD(v54) = WORD1(v65);
                    if ( StringCchPrintfW(sourceString, 0x18u, L"%d.%d.%d.%d", (unsigned __int16)v65, v54, v55, v56) >= 0 )
                    {
                      v57 = 0;
                      v48 = v64;
                      v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
                      Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
                        v48,
                        v63,
                        *(_QWORD *)(v49 + 24),
                        &v57);
                    }
                  }
                }
                WindowsDeleteString(v63);
              }
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v67);
            ++v41;
          }
          while ( v41 < v61 );
          v2 = v86;
        }
        v3 = v68;
      }
      if ( (int)Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::get_Size(
                  v64,
                  &v61) >= 0
        && v61 )
      {
        v50 = v64;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v70);
        View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
                 v50,
                 &v70);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(&v64);
LABEL_33:
    if ( View >= 0 )
    {
LABEL_34:
      v63 = 0;
      v51 = (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)*v3;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v63);
      LOBYTE(v52) = *((_BYTE *)v4 + 32) != 0;
      View = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ScanForSpecificUpdatesWorker(
               v51,
               (UserHelpers *)v4[2],
               v70,
               v52,
               (TraceLoggingCorrelationVector *)v4[5],
               &v63);
      if ( View >= 0 )
        View = Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>::Set(
                 v2,
                 v63);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v63);
    }
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v4[5],
      _InterlockedExchangeAdd64((volatile signed __int64 *)(v4[5] + 136LL), 0),
      v106);
    v53 = L"true";
    if ( !*((_BYTE *)v4 + 32) )
      v53 = L"false";
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1DA4u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithPausedAddAsy"
      "nc::<lambda_9fe8131cfb24e388200a9ff4f508eeaf>::operator ()",
      View,
      L"result: addAsPaused = %s, CV = %hs",
      0,
      0,
      v53,
      v106);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v70);
    WindowsDeleteString(v6);
    return (unsigned int)View;
  }
  return result;
}

```

## disassembly

```asm
0x18009fd9c  mov     [rsp+arg_10], rbx
0x18009fda1  mov     [rsp+arg_18], rsi
0x18009fda6  push    rdi
0x18009fda7  push    r12
0x18009fda9  push    r13
0x18009fdab  push    r14
0x18009fdad  push    r15
0x18009fdaf  sub     rsp, 2F0h
0x18009fdb6  mov     rax, cs:__security_cookie
0x18009fdbd  xor     rax, rsp
0x18009fdc0  mov     [rsp+318h+var_38], rax
0x18009fdc8  mov     rsi, rdx
0x18009fdcb  mov     [rsp+318h+var_1D8], rdx
0x18009fdd3  mov     r12, rcx
0x18009fdd6  mov     [rsp+318h+var_290], rcx
0x18009fdde  mov     [rsp+318h+var_1F0], rcx
0x18009fde6  mov     r13, rcx
0x18009fde9  mov     [rsp+318h+var_1E8], rdx
0x18009fdf1  lea     r15, [rcx+30h]
0x18009fdf5  mov     rbx, [r15]
0x18009fdf8  xor     ecx, ecx; string
0x18009fdfa  call    cs:__imp_WindowsDeleteString
0x18009fe00  mov     [rsp+318h+var_240], rbx
0x18009fe08  xor     r14d, r14d
0x18009fe0b  mov     [rsp+318h+var_280], r14
0x18009fe13  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x18009fe18  test    al, al
0x18009fe1a  jz      loc_1800A0623
0x18009fe20  mov     [rsp+318h+var_2B8], r14
0x18009fe25  mov     [rsp+318h+var_2B0], r14
0x18009fe2a  mov     dword ptr [rsp+318h+var_238], r14d
0x18009fe32  xorps   xmm0, xmm0
0x18009fe35  movdqu  [rsp+318h+var_230], xmm0
0x18009fe3e  lea     rcx, [rsp+318h+var_2B0]
0x18009fe43  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18009fe48  lea     rdx, [rsp+318h+var_2B0]
0x18009fe4d  call    ??$CreateExternalObjectVector@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@V?$AgileVector@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@89Foundation@6@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0> * *)
0x18009fe52  lea     r8, [rsp+318h+var_238]
0x18009fe5a  mov     edx, eax
0x18009fe5c  lea     rcx, [rsp+318h+var_2C4]
0x18009fe61  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18009fe66  mov     rdx, [r13+18h]
0x18009fe6a  mov     [rsp+318h+var_238], rdx
0x18009fe72  mov     dword ptr [rsp+318h+var_230], r14d
0x18009fe7a  mov     qword ptr [rsp+318h+var_230+8], r14
0x18009fe82  lea     rcx, [rsp+318h+var_220]
0x18009fe8a  call    ??$end@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@YA?AVvector_iterator@?$vector_range@U?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEAU?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@012@@Z; Windows::Foundation::Collections::end<Windows::Internal::StateRepository::Application *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *> *)
0x18009fe8f  nop
0x18009fe90  mov     eax, dword ptr [rsp+318h+var_230]
0x18009fe97  cmp     eax, dword ptr [rsp+318h+var_218]
0x18009fe9e  jz      loc_1800A0515
0x18009fea4  lea     rcx, [rsp+318h+var_238]
0x18009feac  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18009feb1  mov     [rsp+318h+var_2A8], r14
0x18009feb6  mov     dword ptr [rsp+318h+var_278], r14d
0x18009febe  xorps   xmm0, xmm0
0x18009fec1  movdqu  [rsp+318h+var_270], xmm0
0x18009feca  mov     rsi, [rax]
0x18009fecd  mov     rax, [rsi]
0x18009fed0  mov     rdi, [rax+30h]
0x18009fed4  lea     rcx, [rsp+318h+var_2A8]
0x18009fed9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18009fede  lea     rdx, [rsp+318h+var_2A8]
0x18009fee3  mov     rcx, rsi
0x18009fee6  mov     rax, rdi
0x18009fee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009feee  lea     r8, [rsp+318h+var_278]
0x18009fef6  mov     edx, eax
0x18009fef8  lea     rcx, [rsp+318h+var_2C4]
0x18009fefd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18009ff02  mov     [rsp+318h+string], r14
0x18009ff07  mov     dword ptr [rsp+318h+var_278], r14d
0x18009ff0f  xorps   xmm0, xmm0
0x18009ff12  movdqu  [rsp+318h+var_270], xmm0
0x18009ff1b  mov     rsi, [rsp+318h+var_2A8]
0x18009ff20  mov     rax, [rsi]
0x18009ff23  mov     rdi, [rax+68h]
0x18009ff27  xor     ecx, ecx; string
0x18009ff29  call    cs:__imp_WindowsDeleteString
0x18009ff2f  mov     [rsp+318h+string], r14
0x18009ff34  lea     rdx, [rsp+318h+string]
0x18009ff39  mov     rcx, rsi
0x18009ff3c  mov     rax, rdi
0x18009ff3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff44  lea     r8, [rsp+318h+var_278]
0x18009ff4c  mov     edx, eax
0x18009ff4e  lea     rcx, [rsp+318h+var_1D0]
0x18009ff56  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18009ff5b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate> `wil::Feature<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::GetImpl(void)'::`2'::impl
0x18009ff62  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::__private_IsEnabled(void)
0x18009ff67  test    al, al
0x18009ff69  jz      loc_1800A0236
0x18009ff6f  xor     edx, edx; length
0x18009ff71  mov     rcx, [r15]; string
0x18009ff74  call    cs:__imp_WindowsGetStringRawBuffer
0x18009ff7a  mov     rcx, rax; Str
0x18009ff7d  xor     edx, edx; unsigned __int16 *
0x18009ff7f  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x18009ff84  mov     dil, al
0x18009ff87  lea     rdx, [rsp+318h+var_1A8]
0x18009ff8f  mov     rcx, [r12]
0x18009ff93  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x18009ff98  mov     rsi, rax
0x18009ff9b  mov     [rsp+318h+var_2C7], 1
0x18009ffa0  cmp     [r12+20h], r14b
0x18009ffa5  setz    [rsp+318h+var_2C6]
0x18009ffaa  mov     [rsp+318h+var_2C5], r14b
0x18009ffaf  mov     [rsp+318h+var_2C8], dil
0x18009ffb4  mov     rdx, r15
0x18009ffb7  lea     rcx, [rsp+318h+var_200]
0x18009ffbf  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x18009ffc4  nop
0x18009ffc5  mov     rax, [r12]
0x18009ffc9  mov     rcx, [rax+1C8h]
0x18009ffd0  mov     [rsp+318h+var_2A0], rcx
0x18009ffd5  lea     rdx, [rsp+318h+var_2A0]
0x18009ffda  lea     rcx, [rsp+318h+var_208]
0x18009ffe2  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x18009ffe7  nop
0x18009ffe8  lea     rax, [rsp+318h+var_2C7]
0x18009ffed  mov     [rsp+318h+var_2E8], rax
0x18009fff2  lea     rax, [rsp+318h+var_2C6]
0x18009fff7  mov     [rsp+318h+var_2F0], rax
0x18009fffc  lea     rax, [rsp+318h+var_2C5]
0x1800a0001  mov     [rsp+318h+var_2F8], rax
0x1800a0006  lea     r9, [rsp+318h+var_2C8]
0x1800a000b  lea     r8, [rsp+318h+var_200]
0x1800a0013  lea     rdx, [rsp+318h+var_208]
0x1800a001b  lea     rcx, [rsp+318h+var_1B0]
0x1800a0023  call    ??$CreatePropertiesJson@UUserIdentityInfo@WorkProperty@PluginHelpers@@UCallerApplicationId@23@UIsInteractive@23@UOfflineShed@23@UAutomaticallyDownloadAndInstallUpdateIfFound@23@UStageButDoNotInstall@23@@PluginHelpers@@YA?AUhstring@winrt@@$$QEAUUserIdentityInfo@WorkProperty@0@$$QEAUCallerApplicationId@40@$$QEAUIsInteractive@40@$$QEAUOfflineShed@40@$$QEAUAutomaticallyDownloadAndInstallUpdateIfFound@40@$$QEAUStageButDoNotInstall@40@@Z; PluginHelpers::CreatePropertiesJson<PluginHelpers::WorkProperty::UserIdentityInfo,PluginHelpers::WorkProperty::CallerApplicationId,PluginHelpers::WorkProperty::IsInteractive,PluginHelpers::WorkProperty::OfflineShed,PluginHelpers::WorkProperty::AutomaticallyDownloadAndInstallUpdateIfFound,PluginHelpers::WorkProperty::StageButDoNotInstall>(PluginHelpers::WorkProperty::UserIdentityInfo &&,PluginHelpers::WorkProperty::CallerApplicationId &&,PluginHelpers::WorkProperty::IsInteractive &&,PluginHelpers::WorkProperty::OfflineShed &&,PluginHelpers::WorkProperty::AutomaticallyDownloadAndInstallUpdateIfFound &&,PluginHelpers::WorkProperty::StageButDoNotInstall &&)
0x1800a0028  nop
0x1800a0029  mov     rax, [rax]
0x1800a002c  mov     [rsp+318h+var_278], rax
0x1800a0034  mov     rax, [rsp+318h+string]
0x1800a0039  mov     [rsp+318h+var_2A0], rax
0x1800a003e  lea     rdx, [rsp+318h+var_2A0]
0x1800a0043  lea     rcx, [rsp+318h+var_1B8]
0x1800a004b  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a0050  nop
0x1800a0051  mov     rax, [rax]
0x1800a0054  mov     [rsp+318h+var_158], rax
0x1800a005c  mov     ecx, 1
0x1800a0061  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800a0066  mov     rdx, rax; unsigned __int16 *
0x1800a0069  lea     rcx, [rsp+318h+var_138]; this
0x1800a0071  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800a0076  mov     rdx, [r12+10h]
0x1800a007b  lea     rcx, [rsp+318h+var_1C0]
0x1800a0083  call    ?GetSidForIUser@@YA?AUhstring@winrt@@PEAUIUser@System@Windows@@@Z; GetSidForIUser(Windows::System::IUser *)
0x1800a0088  nop
0x1800a0089  mov     rax, [rax]
0x1800a008c  mov     qword ptr [rsp+318h+sourceString], rax
0x1800a0094  mov     rdx, [r12+28h]
0x1800a0099  lea     rcx, [rsp+318h+var_1C8]
0x1800a00a1  call    ?GetCvString@@YA?AUhstring@winrt@@PEAVTraceLoggingCorrelationVector@@@Z; GetCvString(TraceLoggingCorrelationVector *)
0x1800a00a6  nop
0x1800a00a7  mov     rax, [rax]
0x1800a00aa  mov     qword ptr [rsp+318h+hstringHeader.Reserved], rax
0x1800a00b2  lea     rax, [rsp+318h+var_278]
0x1800a00ba  mov     [rsp+318h+var_2E8], rax
0x1800a00bf  lea     rax, [rsp+318h+var_158]
0x1800a00c7  mov     [rsp+318h+var_2F0], rax
0x1800a00cc  lea     rax, [rsp+318h+var_138]
0x1800a00d4  mov     [rsp+318h+var_2F8], rax
0x1800a00d9  lea     r9, [rsp+318h+sourceString]
0x1800a00e1  lea     r8, [rsp+318h+hstringHeader]
0x1800a00e9  lea     rdx, [rsp+318h+var_250]
0x1800a00f1  mov     rcx, rsi
0x1800a00f4  call    ?ScanForUpdate@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0000@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ScanForUpdate(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800a00f9  nop
0x1800a00fa  lea     rcx, [rsp+318h+var_1C8]
0x1800a0102  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a0107  nop
0x1800a0108  lea     rcx, [rsp+318h+var_1C0]
0x1800a0110  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a0115  nop
0x1800a0116  lea     rcx, [rsp+318h+var_1B8]
0x1800a011e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a0123  nop
0x1800a0124  lea     rcx, [rsp+318h+var_1B0]
0x1800a012c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a0131  nop
0x1800a0132  lea     rcx, [rsp+318h+var_208]
0x1800a013a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a013f  nop
0x1800a0140  lea     rcx, [rsp+318h+var_200]
0x1800a0148  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a014d  nop
0x1800a014e  lea     rcx, [rsp+318h+var_1A8]; void *
0x1800a0156  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800a015b  mov     [rsp+318h+var_2A0], r14
0x1800a0160  lea     rdx, [rsp+318h+var_2A0]
0x1800a0165  lea     rcx, [rsp+318h+var_250]
0x1800a016d  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800a0172  test    al, al
0x1800a0174  jz      short loc_1800A0183
0x1800a0176  lea     rcx, [rsp+318h+var_250]
0x1800a017e  jmp     loc_1800A04E0
0x1800a0183  mov     [rsp+318h+var_258], r14
0x1800a018b  mov     dword ptr [rsp+318h+var_278], r14d
0x1800a0193  xorps   xmm0, xmm0
0x1800a0196  movdqu  [rsp+318h+var_270], xmm0
0x1800a019f  mov     rdi, [r12]
0x1800a01a3  lea     rcx, [rsp+318h+var_258]
0x1800a01ab  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a01b0  lea     r8, [rsp+318h+var_258]; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem **
0x1800a01b8  mov     rdx, [rsp+318h+var_250]; struct WindowsUpdate::Internal::IInstallItem *
0x1800a01c0  mov     rcx, rdi; this
0x1800a01c3  call    ?FindOrCreateInstallItem@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIInstallItem@Internal@WindowsUpdate@@PEAPEAVAppInstallItem@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(WindowsUpdate::Internal::IInstallItem *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *)
0x1800a01c8  lea     r8, [rsp+318h+var_278]
0x1800a01d0  mov     edx, eax
0x1800a01d2  lea     rcx, [rsp+318h+var_168]
0x1800a01da  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800a01df  mov     dword ptr [rsp+318h+var_278], r14d
0x1800a01e7  xorps   xmm0, xmm0
0x1800a01ea  movdqu  [rsp+318h+var_270], xmm0
0x1800a01f3  mov     rcx, [rsp+318h+var_2B0]
0x1800a01f8  mov     rax, [rcx]
0x1800a01fb  mov     rdx, [rsp+318h+var_258]
0x1800a0203  mov     rax, [rax+68h]
0x1800a0207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a020c  lea     r8, [rsp+318h+var_278]
0x1800a0214  mov     edx, eax
0x1800a0216  lea     rcx, [rsp+318h+var_178]
0x1800a021e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800a0223  nop
0x1800a0224  lea     rcx, [rsp+318h+var_258]
0x1800a022c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a0231  jmp     loc_1800A0176
0x1800a0236  lea     rdx, [rsp+318h+var_180]
0x1800a023e  mov     rcx, [r12]
0x1800a0242  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800a0247  mov     rdi, rax
0x1800a024a  mov     [rsp+318h+var_2C8], 1
0x1800a024f  cmp     [r12+20h], r14b
0x1800a0254  setz    [rsp+318h+var_2C5]
0x1800a0259  mov     [rsp+318h+var_2C6], r14b
0x1800a025e  mov     [rsp+318h+var_2C7], 1
0x1800a0263  mov     rdx, r15
0x1800a0266  lea     rcx, [rsp+318h+var_290]
0x1800a026e  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a0273  nop
0x1800a0274  mov     rax, [r12]
0x1800a0278  mov     rcx, [rax+1C8h]
0x1800a027f  mov     [rsp+318h+var_2A0], rcx
0x1800a0284  lea     rdx, [rsp+318h+var_2A0]
0x1800a0289  lea     rcx, [rsp+318h+var_1F8]
0x1800a0291  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a0296  nop
0x1800a0297  lea     rax, [rsp+318h+var_2C8]
0x1800a029c  mov     [rsp+318h+var_2E8], rax
0x1800a02a1  lea     rax, [rsp+318h+var_2C5]
0x1800a02a6  mov     [rsp+318h+var_2F0], rax
0x1800a02ab  lea     rax, [rsp+318h+var_2C6]
0x1800a02b0  mov     [rsp+318h+var_2F8], rax
0x1800a02b5  lea     r9, [rsp+318h+var_2C7]
0x1800a02ba  lea     r8, [rsp+318h+var_290]
0x1800a02c2  lea     rdx, [rsp+318h+var_1F8]
0x1800a02ca  lea     rcx, [rsp+318h+var_188]
0x1800a02d2  call    ??$CreatePropertiesJson@UUserIdentityInfo@WorkProperty@PluginHelpers@@UCallerApplicationId@23@UIsInteractive@23@UOfflineShed@23@UAutomaticallyDownloadAndInstallUpdateIfFound@23@UStageButDoNotInstall@23@@PluginHelpers@@YA?AUhstring@winrt@@$$QEAUUserIdentityInfo@WorkProperty@0@$$QEAUCallerApplicationId@40@$$QEAUIsInteractive@40@$$QEAUOfflineShed@40@$$QEAUAutomaticallyDownloadAndInstallUpdateIfFound@40@$$QEAUStageButDoNotInstall@40@@Z; PluginHelpers::CreatePropertiesJson<PluginHelpers::WorkProperty::UserIdentityInfo,PluginHelpers::WorkProperty::CallerApplicationId,PluginHelpers::WorkProperty::IsInteractive,PluginHelpers::WorkProperty::OfflineShed,PluginHelpers::WorkProperty::AutomaticallyDownloadAndInstallUpdateIfFound,PluginHelpers::WorkProperty::StageButDoNotInstall>(PluginHelpers::WorkProperty::UserIdentityInfo &&,PluginHelpers::WorkProperty::CallerApplicationId &&,PluginHelpers::WorkProperty::IsInteractive &&,PluginHelpers::WorkProperty::OfflineShed &&,PluginHelpers::WorkProperty::AutomaticallyDownloadAndInstallUpdateIfFound &&,PluginHelpers::WorkProperty::StageButDoNotInstall &&)
0x1800a02d7  nop
0x1800a02d8  mov     rax, [rax]
0x1800a02db  mov     qword ptr [rsp+318h+hstringHeader.Reserved], rax
0x1800a02e3  mov     rax, [rsp+318h+string]
0x1800a02e8  mov     [rsp+318h+var_2A0], rax
0x1800a02ed  lea     rdx, [rsp+318h+var_2A0]
0x1800a02f2  lea     rcx, [rsp+318h+var_190]
0x1800a02fa  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a02ff  nop
0x1800a0300  mov     rax, [rax]
0x1800a0303  mov     qword ptr [rsp+318h+sourceString], rax
0x1800a030b  mov     ecx, 1
0x1800a0310  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800a0315  mov     rdx, rax; unsigned __int16 *
0x1800a0318  lea     rcx, [rsp+318h+var_138]; this
0x1800a0320  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800a0325  mov     rdx, [r12+10h]
0x1800a032a  lea     rcx, [rsp+318h+var_170]
0x1800a0332  call    ?GetSidForIUser@@YA?AUhstring@winrt@@PEAUIUser@System@Windows@@@Z; GetSidForIUser(Windows::System::IUser *)
0x1800a0337  nop
0x1800a0338  mov     rax, [rax]
0x1800a033b  mov     [rsp+318h+var_158], rax
0x1800a0343  mov     rdx, [r12+28h]
0x1800a0348  lea     rcx, [rsp+318h+var_1A0]
0x1800a0350  call    ?GetCvString@@YA?AUhstring@winrt@@PEAVTraceLoggingCorrelationVector@@@Z; GetCvString(TraceLoggingCorrelationVector *)
0x1800a0355  nop
0x1800a0356  mov     rax, [rax]
0x1800a0359  mov     [rsp+318h+var_278], rax
0x1800a0361  lea     rax, [rsp+318h+hstringHeader]
0x1800a0369  mov     [rsp+318h+var_2E8], rax
0x1800a036e  lea     rax, [rsp+318h+sourceString]
0x1800a0376  mov     [rsp+318h+var_2F0], rax
0x1800a037b  lea     rax, [rsp+318h+var_138]
0x1800a0383  mov     [rsp+318h+var_2F8], rax
0x1800a0388  lea     r9, [rsp+318h+var_158]
0x1800a0390  lea     r8, [rsp+318h+var_278]
0x1800a0398  lea     rdx, [rsp+318h+var_298]
0x1800a03a0  mov     rcx, rdi
0x1800a03a3  call    ?ScanForUpdate@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0000@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ScanForUpdate(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800a03a8  nop
  ... truncated ...
```
