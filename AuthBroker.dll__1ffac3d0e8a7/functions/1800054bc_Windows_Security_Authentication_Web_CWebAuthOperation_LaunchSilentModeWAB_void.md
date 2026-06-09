# Windows::Security::Authentication::Web::CWebAuthOperation::LaunchSilentModeWAB(void)

- ea: `0x1800054bc`
- end: `0x180006058`
- name: `?LaunchSilentModeWAB@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJXZ`
- size: `2972`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, __int64, bool)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019484`

## callees

- `0x1800035e0`
- `0x1800054bc`
- `0x180006060`
- `0x18000608c`
- `0x1800060b8`
- `0x1800060d8`
- `0x1800060f8`
- `0x18000611c`
- `0x1800066b4`
- `0x180006a58`
- `0x1800159f4`
- `0x180015a74`
- `0x180015b14`
- `0x180015d60`
- `0x180015e00`
- `0x180015ea0`
- `0x180016534`
- `0x1800165bc`
- `0x180016644`
- `0x1800166cc`
- `0x180016754`
- `0x1800169fc`
- `0x180016e78`
- `0x180018148`
- `0x180018258`
- `0x180018ea4`
- `0x1800192e4`
- `0x18001934c`
- `0x1800197e4`
- `0x18001a920`
- `0x18001aea8`
- `0x18001b9e8`
- `0x18001be4c`
- `0x18001f8ec`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e36`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180005827`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180005827`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180005ad1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180005ad1`

## string_xrefs

- `0x1800055cf`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005766`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x1800057c7`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x18000583a`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005887`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005906`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005ae9`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005bfe`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005cb1`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005d3d`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005dea`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180006003`: `onecore\ds\security\webauth\authbroker\lib\webauthbrokerimpl.cpp`
- `0x180005589`: `wab.microsoft.GetTokenSilently`
- `0x1800054f1`: `SilentModeBrokerActivity`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::LaunchSilentModeWAB(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        __int64 a2,
        bool a3)
{
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // rbx
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *v5; // rax
  HRESULT v6; // eax
  int v7; // ebx
  unsigned int v8; // edx
  Windows::ApplicationModel::AppService::IAppServiceConnection *ptr; // rdi
  Windows::ApplicationModel::AppService::IAppServiceConnection_vtbl *v10; // rax
  HRESULT (__fastcall *put_AppServiceName)(Windows::ApplicationModel::AppService::IAppServiceConnection *, HSTRING__ *); // rbx
  Windows::ApplicationModel::AppService::IAppServiceConnection *v12; // rdi
  HRESULT (__fastcall *put_PackageFamilyName)(Windows::ApplicationModel::AppService::IAppServiceConnection *, HSTRING__ *); // rbx
  Microsoft::WRL::Details::Dummy v14; // r8
  __int64 v15; // rax
  Windows::ApplicationModel::AppService::IAppServiceConnection *v16; // rdi
  HRESULT (__fastcall *v17)(Windows::ApplicationModel::AppService::IAppServiceConnection *, HSTRING__ *); // rbx
  Microsoft::WRL::Details::Dummy v18; // r8
  __int64 v19; // rax
  Windows::ApplicationModel::AppService::IAppServiceConnection *v20; // rdi
  HRESULT (__fastcall *OpenAsync)(Windows::ApplicationModel::AppService::IAppServiceConnection *, Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> **); // rbx
  int v22; // eax
  tagCOWAIT_FLAGS v23; // edx
  void *v24; // r8
  HRESULT v25; // r9d
  unsigned int v26; // edx
  Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *v27; // rdi
  HRESULT v28; // eax
  Windows::Foundation::Collections::IPropertySet *v29; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v31; // eax
  HSTRING__ *hstr; // rbx
  HRESULT ActivationFactory; // eax
  Windows::Security::Authentication::Web::CWebAuthOperation *v34; // rcx
  Windows::Security::Authentication::Web::WebAuthenticationOptions m_WebAuthOptions; // edx
  HRESULT v36; // eax
  Windows::Foundation::IPropertyValueStatics *v37; // rsi
  HRESULT (__fastcall *CreateString)(Windows::Foundation::IPropertyValueStatics *, HSTRING__ *, IInspectable **); // rdi
  wchar_t *m_ptr; // rbx
  Microsoft::WRL::Details::Dummy v40; // r8
  __int64 v41; // rax
  int v42; // edi
  unsigned int v43; // edx
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *v44; // r14
  IInspectable *v45; // rdi
  HRESULT (__fastcall *Insert)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *> *, HSTRING__ *, IInspectable *, unsigned __int8 *); // rsi
  Windows::Foundation::IPropertyValueStatics *v47; // rsi
  HRESULT (__fastcall *v48)(Windows::Foundation::IPropertyValueStatics *, HSTRING__ *, IInspectable **); // rdi
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *v49; // r14
  IInspectable *v50; // rdi
  HRESULT (__fastcall *v51)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *> *, HSTRING__ *, IInspectable *, unsigned __int8 *); // rsi
  Windows::Foundation::IPropertyValueStatics *v52; // rsi
  HRESULT (__fastcall *v53)(Windows::Foundation::IPropertyValueStatics *, HSTRING__ *, IInspectable **); // rdi
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *v54; // r14
  IInspectable *v55; // rdi
  HRESULT (__fastcall *v56)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *> *, HSTRING__ *, IInspectable *, unsigned __int8 *); // rsi
  unsigned int v57; // edx
  Windows::Foundation::IPropertyValueStatics *v58; // rsi
  HRESULT (__fastcall *v59)(Windows::Foundation::IPropertyValueStatics *, HSTRING__ *, IInspectable **); // rdi
  Microsoft::WRL::Details::Dummy v60; // r8
  __int64 v61; // rax
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *v62; // r14
  IInspectable *v63; // rdi
  HRESULT (__fastcall *v64)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *> *, HSTRING__ *, IInspectable *, unsigned __int8 *); // rsi
  const wchar_t *StringRawBuffer; // rdi
  const wchar_t *v66; // rax
  HRESULT v67; // eax
  Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *v68; // rcx
  Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *v69; // rdi
  tagCOWAIT_FLAGS v70; // edx
  void *v71; // r8
  int v72; // eax
  HRESULT v73; // r9d
  unsigned int v74; // edx
  Windows::ApplicationModel::AppService::IAppServiceResponse *v75; // rdi
  HRESULT (__fastcall *get_Message)(Windows::ApplicationModel::AppService::IAppServiceResponse *, Windows::Foundation::Collections::IPropertySet **); // rbx
  HRESULT v77; // eax
  HSTRING__ **v78; // rax
  HSTRING__ **v79; // rax
  HRESULT (__fastcall *v80)(Windows::Foundation::IPropertyValue *, HSTRING__ **); // r8
  int v81; // eax
  unsigned int v82; // edx
  HRESULT v83; // r9d
  const wchar_t *v84; // rax
  const wchar_t *v85; // rax
  HSTRING__ **v86; // rax
  HSTRING__ **v87; // rax
  HRESULT (__fastcall *v88)(Windows::Foundation::IPropertyValue *, unsigned int *); // r8
  unsigned int v89; // eax
  HSTRING__ **v90; // rax
  HSTRING__ **v91; // rax
  HRESULT (__fastcall *v92)(Windows::Foundation::IPropertyValue *, int *); // r8
  Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *v93; // rcx
  unsigned __int8 propertyFound; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 replaced[7]; // [rsp+31h] [rbp-CFh] BYREF
  Microsoft::WRL::ComPtr<IInspectable> propVal; // [rsp+38h] [rbp-C8h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> > connectionOperation; // [rsp+40h] [rbp-C0h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> > propertySetMap; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> valueFactory; // [rsp+50h] [rbp-B0h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> message; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> > sendMessageOperation; // [rsp+60h] [rbp-A0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > webAuthOptionsString; // [rsp+68h] [rbp-98h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > stringGuid; // [rsp+70h] [rbp-90h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse> response; // [rsp+78h] [rbp-88h] BYREF
  Windows::Internal::ShellHelpers::PropertySetHelper propHelper; // [rsp+80h] [rbp-80h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> responsePropertySet; // [rsp+88h] [rbp-78h] BYREF
  HSTRING__ *responseStr; // [rsp+90h] [rbp-70h] BYREF
  Windows::ApplicationModel::AppService::AppServiceConnectionStatus connectionStatus; // [rsp+98h] [rbp-68h] BYREF
  Windows::ApplicationModel::AppService::AppServiceResponseStatus status; // [rsp+9Ch] [rbp-64h] BYREF
  int responseHrInt; // [rsp+A0h] [rbp-60h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection> appServiceConnection; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int responseErrorHttp; // [rsp+B0h] [rbp-50h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v114; // [rsp+B8h] [rbp-48h] BYREF
  WebAuthBridgeTelemetry::SilentModeBrokerActivity silentModeBrokerActivity; // [rsp+E0h] [rbp-20h] BYREF
  void *retaddr; // [rsp+268h] [rbp+168h]

  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &silentModeBrokerActivity,
    "SilentModeBrokerActivity",
    a3);
  m_pActivityData = this->m_WamBridgeBrokerActivity.m_pActivityData;
  silentModeBrokerActivity.__vftable = (WebAuthBridgeTelemetry::SilentModeBrokerActivity_vtbl *)WebAuthBridgeTelemetry::SilentModeBrokerActivity::`vftable';
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &silentModeBrokerActivity,
    (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > *)&responseStr);
  v5 = silentModeBrokerActivity.m_pActivityData;
  silentModeBrokerActivity.m_pActivityData->m_CapturedRelatedId = m_pActivityData->m_Id;
  v5->m_HasRelatedId = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > *)&responseStr);
  WebAuthBridgeTelemetry::SilentModeBrokerActivity::StartActivity(&silentModeBrokerActivity);
  appServiceConnection.ptr_ = 0;
  v114.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v114,
    RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection,
    0x39u,
    0x38u);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection>>(
         v114.hstr_,
         (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection> >)&appServiceConnection);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 615;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v8,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v6);
    goto LABEL_106;
  }
  ptr = appServiceConnection.ptr_;
  v10 = appServiceConnection.ptr_->lpVtbl;
  v114.hstr_ = 0;
  put_AppServiceName = v10->put_AppServiceName;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v114, L"wab.microsoft.GetTokenSilently", 0x1Fu, 0x1Eu);
  v6 = put_AppServiceName(ptr, v114.hstr_);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 618;
    goto LABEL_5;
  }
  if ( (this->m_BrokerFlags & 0x100000) != 0 )
  {
    WebAuthBridgeTelemetry::SilentModeBrokerActivity::LaunchIntranetSSO(&silentModeBrokerActivity);
    v12 = appServiceConnection.ptr_;
    put_PackageFamilyName = appServiceConnection.ptr_->put_PackageFamilyName;
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v114, &g_IntranetSSOPackageFamilyName, v14);
    v6 = put_PackageFamilyName(v12, *(HSTRING__ **)(v15 + 24));
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 624;
      goto LABEL_5;
    }
  }
  else
  {
    WebAuthBridgeTelemetry::SilentModeBrokerActivity::LaunchInternetSSO(&silentModeBrokerActivity);
    v16 = appServiceConnection.ptr_;
    v17 = appServiceConnection.ptr_->put_PackageFamilyName;
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v114, &g_InternetSSOPackageFamilyName, v18);
    v6 = v17(v16, *(HSTRING__ **)(v19 + 24));
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 629;
      goto LABEL_5;
    }
  }
  v20 = appServiceConnection.ptr_;
  connectionOperation.ptr_ = 0;
  OpenAsync = appServiceConnection.ptr_->OpenAsync;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&connectionOperation);
  v22 = OpenAsync(v20, &connectionOperation.ptr_);
  v7 = v22;
  if ( v22 < 0 )
  {
    v25 = v22;
    v26 = 634;
LABEL_104:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v26,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v25);
    goto LABEL_105;
  }
  v27 = connectionOperation.ptr_;
  connectionStatus = AppServiceConnectionStatus_Unknown;
  v7 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(
         connectionOperation.ptr_,
         v23,
         v24);
  if ( v7 < 0 || (v7 = v27->GetResults(v27, &connectionStatus), v7 < 0) )
  {
    v26 = 638;
LABEL_103:
    v25 = v7;
    goto LABEL_104;
  }
  WebAuthBridgeTelemetry::SilentModeBrokerActivity::ServiceConnectionStatus<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus &>(
    &silentModeBrokerActivity,
    &connectionStatus);
  if ( connectionStatus )
  {
    if ( connectionStatus == AppServiceConnectionStatus_AppNotInstalled
      || connectionStatus == AppServiceConnectionStatus_AppServiceUnavailable )
    {
      v7 = -2144927148;
      v26 = 650;
    }
    else
    {
      v7 = -2147467259;
      v26 = 656;
    }
    goto LABEL_103;
  }
  message.ptr_ = 0;
  v114.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v114,
    RuntimeClass_Windows_Foundation_Collections_ValueSet,
    0x28u,
    0x27u);
  v28 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
          v114.hstr_,
          (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> >)&message);
  v7 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x295u,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v28);
LABEL_22:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&message);
LABEL_105:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&connectionOperation);
    goto LABEL_106;
  }
  v29 = message.ptr_;
  propertySetMap.ptr_ = 0;
  QueryInterface = message.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propertySetMap);
  v31 = QueryInterface(v29, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, (void **)&propertySetMap.ptr_);
  v7 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x297u,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v31);
LABEL_25:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propertySetMap);
    goto LABEL_22;
  }
  valueFactory.ptr_ = 0;
  v114.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v114,
    RuntimeClass_Windows_Foundation_PropertyValue,
    0x21u,
    0x20u);
  hstr = v114.hstr_;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&valueFactory);
  ActivationFactory = RoGetActivationFactory(hstr, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &valueFactory);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x29Au,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      ActivationFactory);
LABEL_28:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&valueFactory);
    goto LABEL_25;
  }
  m_WebAuthOptions = this->m_WebAuthOptions;
  propVal.ptr_ = 0;
  replaced[0] = 0;
  webAuthOptionsString.m_ptr = 0;
  v36 = Windows::Security::Authentication::Web::CWebAuthOperation::StringFromWebAuthOptions(
          v34,
          m_WebAuthOptions,
          &webAuthOptionsString.m_ptr);
  v7 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2A1u,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v36);
LABEL_31:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&webAuthOptionsString);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
    goto LABEL_28;
  }
  v37 = valueFactory.ptr_;
  CreateString = valueFactory.ptr_->CreateString;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
  m_ptr = webAuthOptionsString.m_ptr;
  responseStr = (HSTRING__ *)webAuthOptionsString.m_ptr;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(
    &v114,
    (const unsigned __int16 *const *)&responseStr,
    v40);
  v42 = CreateString(v37, *(HSTRING__ **)(v41 + 24), &propVal.ptr_);
  if ( v42 < 0 )
  {
    v43 = 674;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v43,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v42);
LABEL_35:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&webAuthOptionsString);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&valueFactory);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propertySetMap);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&message);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&connectionOperation);
    v7 = v42;
    goto LABEL_106;
  }
  v44 = propertySetMap.ptr_;
  v45 = propVal.ptr_;
  Insert = propertySetMap.ptr_->Insert;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&v114,
    g_WAB2WAMBridgeOptionsPropertyName);
  v42 = Insert(v44, (HSTRING__ *)v114.header_.Reserved.Reserved1, v45, replaced);
  if ( v42 < 0 )
  {
    v43 = 676;
    goto LABEL_34;
  }
  v47 = valueFactory.ptr_;
  v48 = valueFactory.ptr_->CreateString;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
  v42 = v48(v47, this->m_TargetUri._hstring, &propVal.ptr_);
  if ( v42 < 0 )
  {
    v43 = 678;
    goto LABEL_34;
  }
  v49 = propertySetMap.ptr_;
  v50 = propVal.ptr_;
  v51 = propertySetMap.ptr_->Insert;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&v114,
    g_WAB2WAMBridgeStartURLPropertyName);
  v42 = v51(v49, (HSTRING__ *)v114.header_.Reserved.Reserved1, v50, replaced);
  if ( v42 < 0 )
  {
    v43 = 679;
    goto LABEL_34;
  }
  v52 = valueFactory.ptr_;
  v53 = valueFactory.ptr_->CreateString;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
  v42 = v53(v52, this->m_EndUri._hstring, &propVal.ptr_);
  if ( v42 < 0 )
  {
    v43 = 681;
    goto LABEL_34;
  }
  v54 = propertySetMap.ptr_;
  v55 = propVal.ptr_;
  v56 = propertySetMap.ptr_->Insert;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&v114,
    g_WAB2WAMBridgeEndURLPropertyName);
  v42 = v56(v54, (HSTRING__ *)v114.header_.Reserved.Reserved1, v55, replaced);
  if ( v42 < 0 )
  {
    v43 = 682;
    goto LABEL_34;
  }
  stringGuid.m_ptr = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &stringGuid,
    0);
  v42 = StringFromCLSID(&silentModeBrokerActivity.m_pActivityData->m_Id, &stringGuid.m_ptr);
  if ( v42 < 0 )
  {
    v57 = 685;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v57,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v42);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&stringGuid);
    goto LABEL_35;
  }
  v58 = valueFactory.ptr_;
  v59 = valueFactory.ptr_->CreateString;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
  responseStr = (HSTRING__ *)stringGuid.m_ptr;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(
    &v114,
    (const unsigned __int16 *const *)&responseStr,
    v60);
  v42 = v59(v58, *(HSTRING__ **)(v61 + 24), &propVal.ptr_);
  if ( v42 < 0 )
  {
    v57 = 687;
    goto LABEL_48;
  }
  v62 = propertySetMap.ptr_;
  v63 = propVal.ptr_;
  v64 = propertySetMap.ptr_->Insert;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&v114,
    g_WAB2WAMBridgeTelemetryIdPropertyName);
  v42 = v64(v62, (HSTRING__ *)v114.header_.Reserved.Reserved1, v63, replaced);
  if ( v42 < 0 )
  {
    v57 = 688;
    goto LABEL_48;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(this->m_EndUri._hstring, 0);
  v66 = WindowsGetStringRawBuffer(this->m_TargetUri._hstring, 0);
  WebAuthBridgeTelemetry::SilentModeBrokerActivity::CreatePropertySet(
    &silentModeBrokerActivity,
    v66,
    StringRawBuffer,
    m_ptr);
  sendMessageOperation.ptr_ = 0;
  v67 = appServiceConnection.ptr_->SendMessageAsync(
          appServiceConnection.ptr_,
          message.ptr_,
          (Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> **)&sendMessageOperation);
  v7 = v67;
  if ( v67 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2B6u,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v67);
LABEL_55:
    v68 = sendMessageOperation.ptr_;
    if ( sendMessageOperation.ptr_ )
    {
      sendMessageOperation.ptr_ = 0;
      v68->Release(v68);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&stringGuid);
    goto LABEL_31;
  }
  v69 = sendMessageOperation.ptr_;
  response.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&response);
  v7 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(
         v69,
         v70,
         v71);
  if ( v7 < 0 || (v7 = v69->GetResults(v69, &response.ptr_), v7 < 0) )
  {
    v73 = v7;
    v74 = 698;
    goto LABEL_62;
  }
  status = AppServiceResponseStatus_Unknown;
  v72 = response.ptr_->get_Status(response.ptr_, &status);
  v7 = v72;
  if ( v72 < 0 )
  {
    v73 = v72;
    v74 = 701;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v74,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v73);
LABEL_63:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&response);
    goto LABEL_55;
  }
  WebAuthBridgeTelemetry::SilentModeBrokerActivity::ServiceResponseStatus<enum Windows::ApplicationModel::AppService::AppServiceResponseStatus &>(
    &silentModeBrokerActivity,
    &status);
  if ( status )
  {
    if ( status == AppServiceResponseStatus_ResourceLimitsExceeded )
    {
      v7 = -2147418113;
      v74 = 711;
      v73 = -2147418113;
    }
    else
    {
      v7 = -2147467259;
      v74 = 716;
      v73 = -2147467259;
    }
    goto LABEL_62;
  }
  v75 = response.ptr_;
  responsePropertySet.ptr_ = 0;
  get_Message = response.ptr_->get_Message;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&responsePropertySet);
  v77 = get_Message(v75, &responsePropertySet.ptr_);
  v7 = v77;
  if ( v77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2D1u,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
      v77);
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&responsePropertySet);
    goto LABEL_63;
  }
  propHelper.m_propSet.ptr_ = responsePropertySet.ptr_;
  if ( responsePropertySet.ptr_ )
    responsePropertySet.ptr_->AddRef(responsePropertySet.ptr_);
  propertyFound = 0;
  Windows::Internal::StringReference::StringReference((Windows::Internal::StringReference *)&v114, &g_WABResultData);
  if ( Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(&propHelper, *v78, &propertyFound) >= 0
    && propertyFound )
  {
    responseStr = 0;
    Windows::Internal::StringReference::StringReference((Windows::Internal::StringReference *)&v114, &g_WABResultData);
    v81 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
            &propHelper,
            *v79,
            v80,
            &responseStr);
    v7 = v81;
    if ( v81 < 0 )
    {
      v82 = 728;
LABEL_77:
      v83 = v81;
LABEL_78:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v82,
        "onecore\\ds\\security\\webauth\\authbroker\\lib\\webauthbrokerimpl.cpp",
        v83);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propHelper);
      goto LABEL_70;
    }
    v84 = WindowsGetStringRawBuffer(responseStr, 0);
    if ( v84 )
    {
      v7 = Windows::Internal::String::_InitializeHelper(&this->m_ResponseData, v84);
      if ( v7 >= 0 )
      {
        v85 = WindowsGetStringRawBuffer(this->m_ResponseData._hstring, 0);
        WebAuthBridgeTelemetry::SilentModeBrokerActivity::ResponseResultData(&silentModeBrokerActivity, v85);
        goto LABEL_82;
      }
    }
    else
    {
      v7 = -2147467261;
    }
    v83 = v7;
    v82 = 729;
    goto LABEL_78;
  }
LABEL_82:
  Windows::Internal::StringReference::StringReference((Windows::Internal::StringReference *)&v114, &g_WABErrorHttp);
  if ( Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(&propHelper, *v86, &propertyFound) >= 0
    && propertyFound )
  {
    responseErrorHttp = 0;
    Windows::Internal::StringReference::StringReference((Windows::Internal::StringReference *)&v114, &g_WABErrorHttp);
    v81 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(
            &propHelper,
            *v87,
            v88,
            &responseErrorHttp);
    v7 = v81;
    if ( v81 < 0 )
    {
      v82 = 737;
      goto LABEL_77;
    }
    v89 = responseErrorHttp;
    this->m_ResponseErrorDetail = responseErrorHttp;
    if ( v89 )
      this->m_ResponseStatus = WebAuthenticationStatus_ErrorHttp;
    WebAuthBridgeTelemetry::SilentModeBrokerActivity::ResponseHttpError<unsigned int &>(
      &silentModeBrokerActivity,
      &this->m_ResponseErrorDetail);
  }
  else
  {
    Windows::Internal::StringReference::StringReference((Windows::Internal::StringReference *)&v114, &g_WABResultHr);
    if ( Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(&propHelper, *v90, &propertyFound) >= 0
      && propertyFound )
    {
      responseHrInt = 0;
      Windows::Internal::StringReference::StringReference((Windows::Internal::StringReference *)&v114, &g_WABResultHr);
      v81 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(&propHelper, *v91, v92, &responseHrInt);
      v7 = v81;
      if ( v81 < 0 )
      {
        v82 = 749;
        goto LABEL_77;
      }
      if ( responseHrInt >= 0 )
        this->m_ResponseStatus = WebAuthenticationStatus_Success;
      WebAuthBridgeTelemetry::SilentModeBrokerActivity::ResponseHr<int &>(&silentModeBrokerActivity, &responseHrInt);
    }
  }
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &silentModeBrokerActivity,
    0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propHelper);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&responsePropertySet);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&response);
  v93 = sendMessageOperation.ptr_;
  if ( sendMessageOperation.ptr_ )
  {
    sendMessageOperation.ptr_ = 0;
    v93->Release(v93);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&stringGuid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&webAuthOptionsString);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propVal);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&valueFactory);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&propertySetMap);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&message);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&connectionOperation);
  v7 = 0;
LABEL_106:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&appServiceConnection);
  WebAuthBridgeTelemetry::SilentModeBrokerActivity::~SilentModeBrokerActivity(&silentModeBrokerActivity);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800054bc  mov     [rsp-8+arg_8], rbx
0x1800054c1  mov     [rsp-8+arg_10], rsi
0x1800054c6  push    rbp
0x1800054c7  push    rdi
0x1800054c8  push    r12
0x1800054ca  push    r14
0x1800054cc  push    r15
0x1800054ce  lea     rbp, [rsp-140h]
0x1800054d6  sub     rsp, 240h
0x1800054dd  mov     rax, cs:__security_cookie
0x1800054e4  xor     rax, rsp
0x1800054e7  mov     [rbp+160h+var_30], rax
0x1800054ee  mov     r15, this
0x1800054f1  lea     rdx, contextName; "SilentModeBrokerActivity"
0x1800054f8  lea     this, [rbp+160h+silentModeBrokerActivity]; this
0x1800054fc  call    ??0?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180005501  mov     rbx, [r15+228h]
0x180005508  lea     rax, ??_7SilentModeBrokerActivity@WebAuthBridgeTelemetry@@6B@; const WebAuthBridgeTelemetry::SilentModeBrokerActivity::`vftable'
0x18000550f  lea     rdx, [rbp+160h+responseStr]; result
0x180005513  mov     [rbp+160h+silentModeBrokerActivity.__vftable], rax
0x180005517  lea     this, [rbp+160h+silentModeBrokerActivity]; this
0x18000551b  call    ?LockExclusive@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180005520  mov     rax, [rbp+160h+silentModeBrokerActivity.m_pActivityData]
0x180005527  lea     this, [rbp+160h+responseStr]; this
0x18000552b  movups  xmm0, xmmword ptr [rbx+8]
0x18000552f  movdqu  xmmword ptr [rax+18h], xmm0
0x180005534  mov     byte ptr [rax+4], 1
0x180005538  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000553d  lea     this, [rbp+160h+silentModeBrokerActivity]; this
0x180005541  call    ?StartActivity@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ; WebAuthBridgeTelemetry::SilentModeBrokerActivity::StartActivity(void)
0x180005546  xor     r12d, r12d
0x180005549  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; str
0x180005550  lea     this, [rbp+160h+var_1A8]; this
0x180005554  mov     [rbp+160h+appServiceConnection.ptr_], r12
0x180005558  mov     [rbp+160h+var_1A8.hstr_], r12
0x18000555c  lea     r9d, [r12+38h]; len
0x180005561  lea     r8d, [r12+39h]; bufferLen
0x180005566  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000556b  mov     this, [rbp+160h+var_1A8.hstr_]; activatableClassId
0x18000556f  lea     rdx, [rbp+160h+appServiceConnection]; instance
0x180005573  call    ??$ActivateInstance@V?$ComPtr@UIAppServiceConnection@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppServiceConnection@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection>>)
0x180005578  mov     ebx, eax
0x18000557a  test    eax, eax
0x18000557c  jns     short loc_180005585
0x18000557e  mov     edx, 267h
0x180005583  jmp     short loc_1800055C8
0x180005585  mov     rdi, [rbp+160h+appServiceConnection.ptr_]
0x180005589  lea     rdx, aWabMicrosoftGe; "wab.microsoft.GetTokenSilently"
0x180005590  mov     r9d, 1Eh; len
0x180005596  lea     this, [rbp+160h+var_1A8]; this
0x18000559a  mov     rax, [rdi]
0x18000559d  lea     r8d, [r9+1]; bufferLen
0x1800055a1  mov     [rbp+160h+var_1A8.hstr_], r12
0x1800055a5  mov     rbx, [rax+38h]
0x1800055a9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800055ae  mov     rdx, [rbp+160h+var_1A8.hstr_]
0x1800055b2  mov     this, rdi
0x1800055b5  mov     rax, rbx
0x1800055b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bd  mov     ebx, eax
0x1800055bf  test    eax, eax
0x1800055c1  jns     short loc_1800055E3
0x1800055c3  mov     edx, 26Ah; lineNumber
0x1800055c8  mov     this, [rbp+168h]; callerReturnAddress
0x1800055cf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\webauth\\authbro"...
0x1800055d6  mov     r9d, eax; hr
0x1800055d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055de  jmp     loc_180006019
0x1800055e3  test    dword ptr [r15+0FCh], 100000h
0x1800055ee  lea     this, [rbp+160h+silentModeBrokerActivity]; this
0x1800055f2  jz      short loc_180005630
0x1800055f4  call    ?LaunchIntranetSSO@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ; WebAuthBridgeTelemetry::SilentModeBrokerActivity::LaunchIntranetSSO(void)
0x1800055f9  mov     rdi, [rbp+160h+appServiceConnection.ptr_]
0x1800055fd  lea     rdx, g_IntranetSSOPackageFamilyName; strRef
0x180005604  lea     this, [rbp+160h+var_1A8]; this
0x180005608  mov     rax, [rdi]
0x18000560b  mov     rbx, [rax+48h]
0x18000560f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180005614  mov     this, rdi
0x180005617  mov     rdx, [rax+18h]
0x18000561b  mov     rax, rbx
0x18000561e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005623  mov     ebx, eax
0x180005625  test    eax, eax
0x180005627  jns     short loc_18000566F
0x180005629  mov     edx, 270h
0x18000562e  jmp     short loc_1800055C8
0x180005630  call    ?LaunchInternetSSO@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ; WebAuthBridgeTelemetry::SilentModeBrokerActivity::LaunchInternetSSO(void)
0x180005635  mov     rdi, [rbp+160h+appServiceConnection.ptr_]
0x180005639  lea     rdx, g_InternetSSOPackageFamilyName; strRef
0x180005640  lea     this, [rbp+160h+var_1A8]; this
0x180005644  mov     rax, [rdi]
0x180005647  mov     rbx, [rax+48h]
0x18000564b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180005650  mov     this, rdi
0x180005653  mov     rdx, [rax+18h]
0x180005657  mov     rax, rbx
0x18000565a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565f  mov     ebx, eax
0x180005661  test    eax, eax
0x180005663  jns     short loc_18000566F
0x180005665  mov     edx, 275h
0x18000566a  jmp     loc_1800055C8
0x18000566f  mov     rdi, [rbp+160h+appServiceConnection.ptr_]
0x180005673  lea     this, [rsp+260h+connectionOperation]; this
0x180005678  mov     [rsp+260h+connectionOperation.ptr_], r12
0x18000567d  mov     rax, [rdi]
0x180005680  mov     rbx, [rax+50h]
0x180005684  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005689  lea     rdx, [rsp+260h+connectionOperation]
0x18000568e  mov     this, rdi
0x180005691  mov     rax, rbx
0x180005694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005699  mov     ebx, eax
0x18000569b  test    eax, eax
0x18000569d  jns     short loc_1800056AC
0x18000569f  mov     r9d, eax
0x1800056a2  mov     edx, 27Ah
0x1800056a7  jmp     loc_180005FFC
0x1800056ac  mov     rdi, [rsp+260h+connectionOperation.ptr_]
0x1800056b1  mov     this, rdi; pOperation
0x1800056b4  mov     [rbp+160h+connectionStatus], 4
0x1800056bb  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)
0x1800056c0  mov     ebx, eax
0x1800056c2  test    eax, eax
0x1800056c4  js      loc_180005FF4
0x1800056ca  mov     rax, [rdi]
0x1800056cd  lea     rdx, [rbp+160h+connectionStatus]
0x1800056d1  mov     this, rdi
0x1800056d4  mov     rax, [rax+40h]
0x1800056d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056dd  mov     ebx, eax
0x1800056df  test    eax, eax
0x1800056e1  js      loc_180005FF4
0x1800056e7  lea     rdx, [rbp+160h+connectionStatus]; connectionStatus
0x1800056eb  lea     this, [rbp+160h+silentModeBrokerActivity]; this
0x1800056ef  call    ??$ServiceConnectionStatus@AEAW4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXAEAW4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Z; WebAuthBridgeTelemetry::SilentModeBrokerActivity::ServiceConnectionStatus<Windows::ApplicationModel::AppService::AppServiceConnectionStatus &>(Windows::ApplicationModel::AppService::AppServiceConnectionStatus &)
0x1800056f4  mov     ecx, [rbp+160h+connectionStatus]
0x1800056f7  test    ecx, ecx
0x1800056f9  jz      short loc_180005728
0x1800056fb  sub     ecx, 1
0x1800056fe  jz      short loc_180005719
0x180005700  sub     ecx, 1
0x180005703  jz      short loc_18000570A
0x180005705  cmp     ecx, 1
0x180005708  jz      short loc_180005719
0x18000570a  mov     ebx, 80004005h
0x18000570f  mov     edx, 290h
0x180005714  jmp     loc_180005FF9
0x180005719  mov     ebx, 80270254h
0x18000571e  mov     edx, 28Ah
0x180005723  jmp     loc_180005FF9
0x180005728  mov     r9d, 27h ; '''; len
0x18000572e  mov     [rsp+260h+message.ptr_], r12
0x180005733  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; str
0x18000573a  mov     [rbp+160h+var_1A8.hstr_], r12
0x18000573e  lea     this, [rbp+160h+var_1A8]; this
0x180005742  lea     r8d, [r9+1]; bufferLen
0x180005746  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000574b  mov     this, [rbp+160h+var_1A8.hstr_]; activatableClassId
0x18000574f  lea     rdx, [rsp+260h+message]; instance
0x180005754  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180005759  mov     ebx, eax
0x18000575b  test    eax, eax
0x18000575d  jns     short loc_180005789
0x18000575f  mov     this, [rbp+168h]; callerReturnAddress
0x180005766  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\webauth\\authbro"...
0x18000576d  mov     r9d, eax; hr
0x180005770  mov     edx, 295h; lineNumber
0x180005775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000577a  lea     this, [rsp+260h+message]; this
0x18000577f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005784  jmp     loc_18000600F
0x180005789  mov     rbx, [rsp+260h+message.ptr_]
0x18000578e  lea     this, [rsp+260h+propertySetMap]; this
0x180005793  mov     [rsp+260h+propertySetMap.ptr_], r12
0x180005798  mov     rax, [rbx]
0x18000579b  mov     rdi, [rax]
0x18000579e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800057a3  lea     r8, [rsp+260h+propertySetMap]
0x1800057a8  mov     this, rbx
0x1800057ab  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800057b2  mov     rax, rdi
0x1800057b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ba  mov     ebx, eax
0x1800057bc  test    eax, eax
0x1800057be  jns     short loc_1800057E7
0x1800057c0  mov     this, [rbp+168h]; callerReturnAddress
0x1800057c7  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\webauth\\authbro"...
0x1800057ce  mov     r9d, eax; hr
0x1800057d1  mov     edx, 297h; lineNumber
0x1800057d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057db  lea     this, [rsp+260h+propertySetMap]; this
0x1800057e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800057e5  jmp     short loc_18000577A
0x1800057e7  mov     r9d, 20h ; ' '; len
0x1800057ed  mov     [rsp+260h+valueFactory.ptr_], r12
0x1800057f2  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; str
0x1800057f9  mov     [rbp+160h+var_1A8.hstr_], r12
0x1800057fd  lea     this, [rbp+160h+var_1A8]; this
0x180005801  lea     r8d, [r9+1]; bufferLen
0x180005805  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000580a  mov     rbx, [rbp+160h+var_1A8.hstr_]
0x18000580e  lea     this, [rsp+260h+valueFactory]; this
0x180005813  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005818  lea     r8, [rsp+260h+valueFactory]
0x18000581d  mov     this, rbx
0x180005820  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180005827  call    cs:__imp_RoGetActivationFactory
0x18000582d  mov     ebx, eax
0x18000582f  test    eax, eax
0x180005831  jns     short loc_18000585A
0x180005833  mov     this, [rbp+168h]; callerReturnAddress
0x18000583a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\webauth\\authbro"...
0x180005841  mov     r9d, eax; hr
0x180005844  mov     edx, 29Ah; lineNumber
0x180005849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000584e  lea     this, [rsp+260h+valueFactory]; this
0x180005853  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005858  jmp     short loc_1800057DB
0x18000585a  mov     edx, [r15+104h]; options
0x180005861  lea     r8, [rsp+260h+webAuthOptionsString]; result
0x180005866  mov     [rsp+260h+propVal.ptr_], r12
0x18000586b  mov     [rsp+260h+replaced], r12b
0x180005870  mov     [rsp+260h+webAuthOptionsString.m_ptr], r12
0x180005875  call    ?StringFromWebAuthOptions@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJW4WebAuthenticationOptions@2345@PEAPEAG@Z; Windows::Security::Authentication::Web::CWebAuthOperation::StringFromWebAuthOptions(Windows::Security::Authentication::Web::WebAuthenticationOptions,ushort * *)
0x18000587a  mov     ebx, eax
0x18000587c  test    eax, eax
0x18000587e  jns     short loc_1800058B1
0x180005880  mov     this, [rbp+168h]; callerReturnAddress
0x180005887  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\webauth\\authbro"...
0x18000588e  mov     r9d, eax; hr
0x180005891  mov     edx, 2A1h; lineNumber
0x180005896  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000589b  lea     this, [rsp+260h+webAuthOptionsString]; this
0x1800058a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800058a5  lea     this, [rsp+260h+propVal]; this
0x1800058aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800058af  jmp     short loc_18000584E
0x1800058b1  mov     rsi, [rsp+260h+valueFactory.ptr_]
0x1800058b6  lea     this, [rsp+260h+propVal]; this
0x1800058bb  mov     rax, [rsi]
0x1800058be  mov     rdi, [rax+90h]
0x1800058c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800058ca  mov     rbx, [rsp+260h+webAuthOptionsString.m_ptr]
0x1800058cf  lea     rdx, [rbp+160h+responseStr]; strRef
0x1800058d3  lea     this, [rbp+160h+var_1A8]; this
0x1800058d7  mov     [rbp+160h+responseStr], rbx
0x1800058db  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800058e0  lea     r8, [rsp+260h+propVal]
0x1800058e5  mov     this, rsi
0x1800058e8  mov     rdx, [rax+18h]
0x1800058ec  mov     rax, rdi
0x1800058ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f4  mov     edi, eax
0x1800058f6  test    eax, eax
0x1800058f8  jns     short loc_180005958
0x1800058fa  mov     edx, 2A2h; lineNumber
0x1800058ff  mov     this, [rbp+168h]; callerReturnAddress
0x180005906  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\webauth\\authbro"...
0x18000590d  mov     r9d, edi; hr
0x180005910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005915  lea     this, [rsp+260h+webAuthOptionsString]; this
0x18000591a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000591f  lea     this, [rsp+260h+propVal]; this
0x180005924  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005929  lea     this, [rsp+260h+valueFactory]; this
0x18000592e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005933  lea     this, [rsp+260h+propertySetMap]; this
0x180005938  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000593d  lea     this, [rsp+260h+message]; this
0x180005942  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005947  lea     this, [rsp+260h+connectionOperation]; this
0x18000594c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005951  mov     ebx, edi
0x180005953  jmp     loc_180006019
0x180005958  mov     r14, [rsp+260h+propertySetMap.ptr_]
0x18000595d  lea     this, [rbp+160h+var_1A8]; this
0x180005961  mov     rdx, cs:g_WAB2WAMBridgeOptionsPropertyName; stringRef
0x180005968  mov     rdi, [rsp+260h+propVal.ptr_]
0x18000596d  mov     rax, [r14]
0x180005970  mov     rsi, [rax+50h]
0x180005974  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180005979  mov     rdx, qword ptr [rbp+160h+var_1A8.header_.Reserved]
0x18000597d  lea     r9, [rsp+260h+replaced]
0x180005982  mov     r8, rdi
0x180005985  mov     this, r14
0x180005988  mov     rax, rsi
0x18000598b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005990  mov     edi, eax
0x180005992  test    eax, eax
0x180005994  jns     short loc_1800059A0
0x180005996  mov     edx, 2A4h
0x18000599b  jmp     loc_1800058FF
0x1800059a0  mov     rsi, [rsp+260h+valueFactory.ptr_]
0x1800059a5  lea     this, [rsp+260h+propVal]; this
0x1800059aa  mov     rax, [rsi]
0x1800059ad  mov     rdi, [rax+90h]
0x1800059b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800059b9  mov     rdx, [r15+0C8h]
  ... truncated ...
```
