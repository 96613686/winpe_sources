# _ActivateAppContainerWorker

- ea: `0x18001449c`
- end: `0x1800154b3`
- name: `_ActivateAppContainerWorker`
- size: `4119`
- prototype: `__int64 __fastcall(IAuthBrokerUIContext *pUIContext, int fInProcActivation)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014170`

## callees

- `0x180001150`
- `0x1800011b4`
- `0x180006060`
- `0x180006bec`
- `0x180006e5c`
- `0x180006f58`
- `0x18000737c`
- `0x180007a68`
- `0x180008068`
- `0x1800090e8`
- `0x18000eb40`
- `0x18000eca4`
- `0x18000ed84`
- `0x18000f488`
- `0x180011b30`
- `0x180011b58`
- `0x180012530`
- `0x180012d80`
- `0x180012fe0`
- `0x180013520`
- `0x180013b2c`
- `0x180013b58`
- `0x18001449c`
- `0x18001de7c`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180014fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180014fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014fd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800152bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014fd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800152bc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001454e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014756`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001454e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014a40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014a40`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014a69`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147ac`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014bd7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800146db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800146db`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180014c3c`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180014c3c`
- `ext-ms-win-security-authbrokerui-l1-1-0!CreateWndMgmt` at `0x180014e5a`
- `ext-ms-win-security-authbrokerui-l1-1-0!CreateWndMgmt` at `0x180014e5a`
- `ext-ms-win-security-authbrokerui-l1-1-0!FreeWndMgmt` at `0x1800145df`
- `ext-ms-win-security-authbrokerui-l1-1-0!FreeWndMgmt` at `0x1800145df`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall ActivateAppContainerWorker(IAuthBrokerUIContext *pUIContext, int fInProcActivation)
{
  IAuthBrokerUIContext_vtbl *v2; // rax
  HRESULT (__fastcall *GetActivityID)(IAuthBrokerUIContext *, _GUID *); // rax
  HWND__ *v6; // r13
  __int64 (__fastcall ***v7)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *); // rdi
  Windows::Internal::Security::Authentication::CAuthBrokerContext *v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *); // rax
  HRESULT v10; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v11; // rcx
  unsigned __int16 v12; // dx
  Windows::Security::Authentication::Web::WebAuthenticationStatus v13; // r14d
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v18; // rcx
  const _tlgProvider_t *v19; // rcx
  const _GUID *v20; // r8
  const _GUID *v21; // r9
  IInitializeHostedWindowFactory *v22; // rcx
  char *v23; // rcx
  int v25; // eax
  WPP_PROJECT_CONTROL_BLOCK *v26; // rcx
  unsigned __int16 v27; // dx
  unsigned int v28; // r9d
  IAuthBrokerUIContext_vtbl *v29; // rax
  int v30; // eax
  IAuthBrokerUIContext_vtbl *v31; // rax
  HANDLE CurrentProcess; // rax
  void *v33; // rsi
  void *v34; // rbx
  HANDLE v35; // rax
  HRESULT Error; // eax
  signed int AuthCookies; // eax
  WPP_PROJECT_CONTROL_BLOCK *v38; // rcx
  HRESULT v39; // ebx
  __int64 (__fastcall **v40)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *); // rsi
  IAuthBrokerUIContext_vtbl *v41; // rax
  signed int v42; // eax
  signed int LastError; // eax
  IUnknown *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rsi
  IAuthHost *v46; // rbx
  HRESULT (__fastcall *v47)(IUnknown *, const _GUID *, void **); // r14
  __int64 (__fastcall *v48)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *); // rbx
  IAuthBrokerUIContext_vtbl *v49; // rax
  IAuthBrokerUIContext_vtbl *v50; // rax
  unsigned int v51; // ebx
  unsigned int v52; // esi
  HWND__ *v53; // r14
  HRESULT (__fastcall *Initialize)(WndMgmtAbstract *, const wchar_t *, HWND__ *, unsigned int, unsigned int); // r13
  PCWSTR StringRawBuffer; // rax
  signed int v56; // eax
  signed int v57; // eax
  signed int v58; // eax
  WPP_PROJECT_CONTROL_BLOCK *v59; // rcx
  unsigned __int16 v60; // dx
  signed int v61; // eax
  signed int v62; // eax
  WPP_PROJECT_CONTROL_BLOCK *v63; // rcx
  unsigned __int16 v64; // dx
  HWND__ *v65; // rcx
  signed int CompleteResults; // eax
  WPP_PROJECT_CONTROL_BLOCK *v67; // rcx
  unsigned __int16 v68; // dx
  unsigned int v69; // esi
  void *obj; // rbx
  const wchar_t *v71; // rax
  signed int v72; // eax
  signed int v73; // eax
  signed int v74; // eax
  unsigned int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  Windows::Security::Authentication::Web::WebAuthenticationStatus responseStatus; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int dwBrokerFlags; // [rsp+54h] [rbp-ACh] BYREF
  WndMgmtAbstract *wndMgmt; // [rsp+58h] [rbp-A8h] BYREF
  HRESULT responseHr; // [rsp+60h] [rbp-A0h] BYREF
  HWND__ *dwResponseErrorDetail; // [rsp+68h] [rbp-98h] BYREF
  int fUseSsoAppContainer; // [rsp+70h] [rbp-90h] BYREF
  unsigned int dwProcessId; // [rsp+74h] [rbp-8Ch] BYREF
  CAutoHandle<void *> tokenHandle; // [rsp+78h] [rbp-88h] BYREF
  Microsoft::WRL::ComPtr<IAuthHost> spAuthHost; // [rsp+80h] [rbp-80h] BYREF
  unsigned int dwClientThreadId; // [rsp+88h] [rbp-78h] BYREF
  _GUID pszResponseData; // [rsp+90h] [rbp-70h] OVERLAPPED BYREF
  Microsoft::WRL::ComPtr<IInitializeHostedWindowFactory> windowFactory; // [rsp+A0h] [rbp-60h] BYREF
  Windows::Internal::String pszTitle; // [rsp+A8h] [rbp-58h] BYREF
  Windows::Internal::String pszTarget; // [rsp+B0h] [rbp-50h] BYREF
  Microsoft::WRL::ComPtr<IUnknown> spBrokerContext; // [rsp+B8h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<IUnknown> spAuthHostIUnknown; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 i64TokenClient; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+D0h] [rbp-30h]
  wchar_t *systemDirectoryPath; // [rsp+D8h] [rbp-28h] BYREF
  Windows::Internal::String pszEnd; // [rsp+E0h] [rbp-20h] BYREF
  HWND__ *hwndParent; // [rsp+E8h] [rbp-18h] BYREF
  _AUTH_HOST_PROCESS_CONTEXT processContext; // [rsp+F0h] [rbp-10h] BYREF
  _GUID activityID; // [rsp+100h] [rbp+0h] BYREF
  TraceLoggingThreadActivityIdSetter threadActivitySetter; // [rsp+110h] [rbp+10h] BYREF
  wchar_t applicationName[264]; // [rsp+130h] [rbp+30h] BYREF

  v2 = pUIContext->lpVtbl;
  spAuthHost.ptr_ = 0;
  wndMgmt = 0;
  spAuthHostIUnknown.ptr_ = 0;
  GetActivityID = v2->GetActivityID;
  spBrokerContext.ptr_ = 0;
  v6 = 0;
  tokenHandle._obj = 0;
  processContext = 0;
  pszTarget._hstring = 0;
  pszEnd._hstring = 0;
  pszTitle._hstring = 0;
  hObject = 0;
  systemDirectoryPath = 0;
  responseStatus = WebAuthenticationStatus_Success;
  dwResponseErrorDetail = 0;
  i64TokenClient = 0;
  activityID = 0;
  windowFactory.ptr_ = 0;
  GetActivityID(pUIContext, &activityID);
  threadActivitySetter.m_ActivityId = activityID;
  threadActivitySetter.m_SavedActivityId = activityID;
  EventActivityIdControl(4u, &threadActivitySetter.m_SavedActivityId);
  v7 = 0;
  v8 = (Windows::Internal::Security::Authentication::CAuthBrokerContext *)operator new(0x128u, &std::nothrow);
  *(_QWORD *)&pszResponseData.Data1 = v8;
  if ( v8 )
  {
    Windows::Internal::Security::Authentication::CAuthBrokerContext::CAuthBrokerContext(v8);
    v7 = v9;
    *(_QWORD *)&pszResponseData.Data1 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>::~MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>((Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&pszResponseData);
  if ( !v7 )
  {
    v10 = -2147024882;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 19;
    goto LABEL_8;
  }
  v25 = pUIContext->GetTargetUri(pUIContext, (HSTRING__ **)&pszTarget);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 20;
    goto LABEL_54;
  }
  v25 = pUIContext->GetEndUri(pUIContext, (HSTRING__ **)&pszEnd);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 21;
    goto LABEL_54;
  }
  v29 = pUIContext->lpVtbl;
  dwBrokerFlags = 0;
  v30 = v29->GetBrokerFlags(pUIContext, &dwBrokerFlags);
  v10 = v30;
  if ( v30 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 22;
    goto LABEL_66;
  }
  pszResponseData = activityID;
  v25 = Windows::Internal::Security::Authentication::CAuthBrokerContext::Initialize(
          (Windows::Internal::Security::Authentication::CAuthBrokerContext *)v7,
          pszTarget._hstring,
          pszEnd._hstring,
          dwBrokerFlags,
          &pszResponseData);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 23;
    goto LABEL_54;
  }
  v31 = pUIContext->lpVtbl;
  fUseSsoAppContainer = 0;
  v30 = v31->GetUseSsoAppContainer(pUIContext, &fUseSsoAppContainer);
  v10 = v30;
  if ( v30 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 24;
    goto LABEL_66;
  }
  v30 = pUIContext->GetClientTokenHandle(pUIContext, &i64TokenClient);
  v10 = v30;
  if ( v30 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 25;
LABEL_66:
    v28 = v30;
    goto LABEL_55;
  }
  if ( i64TokenClient )
  {
    if ( fInProcActivation )
    {
      CurrentProcess = GetCurrentProcess();
      v33 = (void *)i64TokenClient;
      v34 = CurrentProcess;
      v35 = GetCurrentProcess();
      if ( DuplicateHandle(v35, v33, v34, &tokenHandle._obj, 0x100000u, 0, 2u) )
      {
        v10 = 0;
        goto LABEL_89;
      }
      Error = ResultFromKnownLastError();
    }
    else
    {
      Error = DuplicateCallingProcessHandleIntoCurrentProcess(i64TokenClient, &tokenHandle._obj);
    }
    v10 = Error;
LABEL_89:
    if ( v10 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_9;
      }
      v27 = 26;
      v28 = v10;
      goto LABEL_55;
    }
  }
  if ( !fUseSsoAppContainer && (dwBrokerFlags & 0x10) == 0 )
    goto LABEL_109;
  responseHr = 0;
  *(_QWORD *)&pszResponseData.Data1 = 0;
  AuthCookies = GetAuthCookies(tokenHandle._obj, (unsigned int *)&responseHr, (_AUTH_COOKIE_ENTRY **)&pszResponseData);
  if ( AuthCookies >= 0 )
    goto LABEL_101;
  v38 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x1Bu, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, AuthCookies);
LABEL_101:
    v38 = WPP_GLOBAL_Control;
  }
  v39 = responseHr;
  if ( responseHr )
  {
    v40 = *(__int64 (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *))&pszResponseData.Data1;
    if ( *(_QWORD *)&pszResponseData.Data1 )
    {
      if ( v38 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (v38[1].ReserveSpace[28] & 8) != 0
        && v38[1].Control.Level >= 5u )
      {
        WPP_SF_d(v38[1].Control.Logger, 0x1Cu, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, responseHr);
      }
      *((_DWORD *)v7 + 24) = v39;
      v7[13] = v40;
    }
  }
LABEL_109:
  v41 = pUIContext->lpVtbl;
  dwProcessId = 0;
  v42 = v41->GetClientProcessId(pUIContext, &dwProcessId);
  if ( v42 < 0
    && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x1Du, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v42);
  }
  if ( dwProcessId )
  {
    hObject = OpenProcess(0x100000u, 0, dwProcessId);
    if ( !hObject )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_9;
      }
      v27 = 30;
LABEL_122:
      v28 = v10;
      goto LABEL_55;
    }
  }
  v10 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &systemDirectoryPath);
  if ( v10 < 0
    || (v10 = StringCchPrintfW(applicationName, 0x104u, L"\"%s\\%s\"", systemDirectoryPath, L"AuthHost.exe"), v10 < 0) )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 31;
    goto LABEL_122;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_S(
      WPP_GLOBAL_Control[1].Control.Logger,
      0x20u,
      WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids,
      applicationName);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAuthHostIUnknown);
  v25 = ActivateAuthHostProcess(
          applicationName,
          &CLSID_AuthHostObject,
          &IID_IAuthHost,
          tokenHandle._obj,
          dwProcessId,
          dwBrokerFlags,
          fUseSsoAppContainer,
          &spAuthHostIUnknown.ptr_,
          &processContext);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 33;
    goto LABEL_54;
  }
  ptr = spAuthHostIUnknown.ptr_;
  QueryInterface = spAuthHostIUnknown.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAuthHost);
  v25 = QueryInterface(ptr, &GUID_5de7918b_bfd7_4c1e_b4e0_b16d0a3ea76b, (void **)&spAuthHost.ptr_);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 34;
    goto LABEL_54;
  }
  v46 = spAuthHost.ptr_;
  v47 = spAuthHost.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(
    (Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)v7
  + 14);
  v25 = v47(v46, &GUID_5de7918b_bfd7_4c1e_b4e0_b16d0a3ea76b, (void **)v7 + 14);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 35;
    goto LABEL_54;
  }
  v48 = **v7;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spBrokerContext);
  v25 = v48(v7, &GUID_00000000_0000_0000_c000_000000000046, &spBrokerContext);
  v10 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v27 = 36;
LABEL_54:
    v28 = v25;
LABEL_55:
    WPP_SF_d(v26[1].Control.Logger, v27, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v28);
    goto LABEL_9;
  }
  if ( !IsDirectUIUnInitThreadPresent() )
  {
    v10 = -2147467263;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 38;
LABEL_8:
    WPP_SF_(v11[1].Control.Logger, v12, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids);
LABEL_9:
    v13 = (int)v6;
    goto $Cleanup_2;
  }
  v10 = CreateWndMgmt(spBrokerContext.ptr_, &wndMgmt);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 37;
    goto LABEL_8;
  }
  if ( !wndMgmt )
  {
    v10 = -2147024882;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 39;
    goto LABEL_8;
  }
  v10 = pUIContext->GetDialogTitle(pUIContext, (HSTRING__ **)&pszTitle);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 40;
    goto LABEL_8;
  }
  v49 = pUIContext->lpVtbl;
  hwndParent = 0;
  v10 = v49->GetParentWindow(pUIContext, &hwndParent);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 41;
    goto LABEL_8;
  }
  v50 = pUIContext->lpVtbl;
  dwClientThreadId = 0;
  v10 = v50->GetClientThreadId(pUIContext, &dwClientThreadId);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_9;
    }
    v12 = 42;
    goto LABEL_8;
  }
  v51 = dwBrokerFlags;
  v52 = dwClientThreadId;
  v53 = hwndParent;
  Initialize = wndMgmt->Initialize;
  if ( WindowsGetStringLen(pszTitle._hstring) )
    StringRawBuffer = WindowsGetStringRawBuffer(pszTitle._hstring, 0);
  else
    StringRawBuffer = 0;
  dwDesiredAccess = v51;
  v56 = ((__int64 (__fastcall *)(WndMgmtAbstract *, PCWSTR, HWND__ *, _QWORD))Initialize)(
          wndMgmt,
          StringRawBuffer,
          v53,
          v52);
  v10 = v56;
  if ( v56 < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x2Bu, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v56);
    }
    v6 = dwResponseErrorDetail;
    goto LABEL_9;
  }
  if ( (dwBrokerFlags & 0x20000) == 0 )
    v7[11] = (__int64 (__fastcall **)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *))wndMgmt;
  v7[30] = (__int64 (__fastcall **)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *))wndMgmt;
  v6 = wndMgmt->GetWABWindow(wndMgmt);
  v57 = RegisterWindowServiceForAccountsControl(v6, (IUnknown *)v7);
  v10 = v57;
  if ( v57 >= 0 )
  {
    v13 = WebAuthenticationStatus_UserCancel;
    v58 = wndMgmt->ShowFrames(wndMgmt);
    v10 = v58;
    if ( v58 < 0 )
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $Cleanup_2;
      }
      v60 = 45;
      goto LABEL_197;
    }
    v61 = wndMgmt->GetWindowFactory(wndMgmt, (IInitializeHostedWindowFactory **)&windowFactory);
    if ( v61 < 0
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x2Eu, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v61);
    }
    v62 = spAuthHost.ptr_->Initialize(spAuthHost.ptr_, (IInspectable *)v7, windowFactory.ptr_);
    v10 = v62;
    if ( v62 >= 0 )
    {
      v62 = spAuthHost.ptr_->Start(spAuthHost.ptr_);
      v10 = v62;
      if ( v62 >= 0 )
      {
        wndMgmt->OnActivationComplete(wndMgmt);
        v69 = dwBrokerFlags & 0x20000;
        obj = tokenHandle._obj;
        v71 = WindowsGetStringRawBuffer(pszTarget._hstring, 0);
        v58 = ProcessMessages(
                wndMgmt,
                v69,
                processContext.processHandle,
                hObject,
                (Windows::Internal::Security::Authentication::CAuthBrokerContext *)v7,
                pUIContext,
                v71,
                obj);
        v10 = v58;
        if ( v58 < 0 )
        {
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto $Cleanup_2;
          }
          v60 = 49;
LABEL_197:
          WPP_SF_d(v59[1].Control.Logger, v60, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v58);
          goto $Cleanup_2;
        }
LABEL_215:
        responseHr = 0;
        responseStatus = WebAuthenticationStatus_Success;
        LODWORD(dwResponseErrorDetail) = 0;
        *(_QWORD *)&pszResponseData.Data1 = 0;
        CompleteResults = Windows::Internal::Security::Authentication::CAuthBrokerContext::GetCompleteResults(
                            (Windows::Internal::Security::Authentication::CAuthBrokerContext *)v7,
                            &responseHr,
                            &responseStatus,
                            (unsigned int *)&dwResponseErrorDetail,
                            (HSTRING__ **)&pszResponseData);
        v10 = CompleteResults;
        if ( CompleteResults >= 0 )
        {
          v72 = pUIContext->PutResponseData(pUIContext, *(HSTRING__ **)&pszResponseData.Data1);
          if ( v72 < 0
            && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x33u, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v72);
          }
          v73 = pUIContext->PutResponseError(pUIContext, responseHr);
          if ( v73 < 0
            && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x34u, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v73);
          }
          v74 = pUIContext->PutResponseStatus(pUIContext, responseStatus);
          if ( v74 < 0
            && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x35u, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v74);
          }
          CompleteResults = pUIContext->PutResponseErrorDetail(pUIContext, (unsigned int)dwResponseErrorDetail);
          v10 = CompleteResults;
          if ( CompleteResults >= 0 )
            goto LABEL_246;
          v67 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_246;
          }
          v68 = 54;
        }
        else
        {
          v67 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_246;
          }
          v68 = 50;
        }
        WPP_SF_d(v67[1].Control.Logger, v68, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, CompleteResults);
LABEL_246:
        Windows::Internal::String::~String((Windows::Internal::String *)&pszResponseData);
        goto $Cleanup_2;
      }
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v64 = 48;
        goto LABEL_213;
      }
    }
    else
    {
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v64 = 47;
LABEL_213:
        WPP_SF_d(v63[1].Control.Logger, v64, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v62);
      }
    }
    wndMgmt->Cleanup(wndMgmt);
    SHProcessMessagesUntilEventsEx(v65, 0, 0, 0x2710u, dwDesiredAccess, 4u);
    if ( v10 < 0 )
      goto $Cleanup_2;
    goto LABEL_215;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x2Cu, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v57);
  }
  v13 = responseStatus;
$Cleanup_2:
  if ( IsDirectUIUnInitThreadPresent() )
  {
    if ( wndMgmt )
    {
      v14 = FreeWndMgmt();
      if ( v14 < 0
        && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x37u, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v14);
      }
    }
  }
  if ( v13 )
    UnregisterWindowServiceForAccountsControl(v6);
  if ( v10 < 0 )
  {
    v15 = pUIContext->PutResponseError(pUIContext, v10);
    if ( v15 < 0
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x38u, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v15);
    }
  }
  v16 = ReleaseAuthHostProcess(&processContext);
  v17 = v16;
  if ( v16 >= 0 )
    goto LABEL_30;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x39u, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v16);
LABEL_30:
    v18 = WPP_GLOBAL_Control;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    v18 = WPP_GLOBAL_Control;
  }
  if ( systemDirectoryPath )
  {
    CoTaskMemFree(systemDirectoryPath);
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (v18[1].ReserveSpace[28] & 8) != 0
    && v18[1].Control.Level >= 5u )
  {
    WPP_SF_(v18[1].Control.Logger, 0x3Au, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids);
  }
  if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
    && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
  {
    LODWORD(dwResponseErrorDetail) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v19,
      &tlgEvent._tlgChannel,
      v20,
      v21,
      (const _tlgWrapperByVal<4> *)&dwResponseErrorDetail);
  }
  EventActivityIdControl(4u, &threadActivitySetter.m_SavedActivityId);
  v22 = windowFactory.ptr_;
  if ( windowFactory.ptr_ )
  {
    windowFactory.ptr_ = 0;
    v22->Release(v22);
  }
  Windows::Internal::String::~String(&pszTitle);
  Windows::Internal::String::~String(&pszEnd);
  Windows::Internal::String::~String(&pszTarget);
  v23 = (char *)tokenHandle._obj;
  tokenHandle._obj = 0;
  if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spBrokerContext);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAuthHostIUnknown);
  if ( v7 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, Microsoft::WRL::ComPtr<IUnknown> *)))(*v7)[2])(v7);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAuthHost);
  return 0;
}

```

## disassembly

```asm
0x18001449c  push    rbp
0x18001449e  push    rbx
0x18001449f  push    rsi
0x1800144a0  push    rdi
0x1800144a1  push    r12
0x1800144a3  push    r13
0x1800144a5  push    r14
0x1800144a7  push    r15
0x1800144a9  lea     rbp, [rsp-258h]
0x1800144b1  sub     rsp, 358h
0x1800144b8  mov     rax, cs:__security_cookie
0x1800144bf  xor     rax, rsp
0x1800144c2  mov     [rbp+290h+var_50], rax
0x1800144c9  mov     rax, [pUIContext]
0x1800144cc  xor     r14d, r14d
0x1800144cf  xorps   xmm0, xmm0
0x1800144d2  mov     [rbp+290h+spAuthHost.ptr_], r14
0x1800144d6  mov     esi, fInProcActivation
0x1800144d8  mov     [rsp+390h+wndMgmt], r14
0x1800144dd  lea     rdx, [rbp+290h+activityID]
0x1800144e1  mov     [rbp+290h+spAuthHostIUnknown.ptr_], r14
0x1800144e5  mov     rax, [rax+80h]
0x1800144ec  mov     r12, pUIContext
0x1800144ef  mov     [rbp+290h+spBrokerContext.ptr_], r14
0x1800144f3  mov     r13d, r14d
0x1800144f6  mov     [rsp+390h+tokenHandle._obj], r14
0x1800144fb  movups  xmmword ptr [rbp+290h+processContext.appContainerIndex], xmm0
0x1800144ff  mov     [rbp+290h+pszTarget._hstring], r14
0x180014503  mov     [rbp+290h+pszEnd._hstring], r14
0x180014507  mov     [rbp+290h+pszTitle._hstring], r14
0x18001450b  mov     [rbp+290h+hObject], r14
0x18001450f  mov     [rbp+290h+systemDirectoryPath], r14
0x180014513  mov     [rsp+390h+responseStatus], r14d
0x180014518  mov     [rsp+390h+dwResponseErrorDetail], r14
0x18001451d  mov     [rbp+290h+i64TokenClient], r14
0x180014521  movups  xmmword ptr [rbp+290h+activityID.Data1], xmm0
0x180014525  mov     [rbp+290h+windowFactory.ptr_], r14
0x180014529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001452e  mov     pUIContext, qword ptr [rbp+290h+activityID.Data1]
0x180014532  lea     rdx, [rbp+290h+threadActivitySetter.m_SavedActivityId]; ActivityId
0x180014536  mov     rax, qword ptr [rbp+290h+activityID.Data4]
0x18001453a  mov     qword ptr [rbp+290h+threadActivitySetter.m_ActivityId.Data1], pUIContext
0x18001453e  mov     qword ptr [rbp+290h+threadActivitySetter.m_SavedActivityId.Data1], pUIContext
0x180014542  lea     ecx, [r14+4]; ControlCode
0x180014546  mov     qword ptr [rbp+290h+threadActivitySetter.m_ActivityId.Data4], rax
0x18001454a  mov     qword ptr [rbp+290h+threadActivitySetter.m_SavedActivityId.Data4], rax
0x18001454e  call    cs:__imp_EventActivityIdControl
0x180014554  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x18001455b  mov     ecx, 128h; count
0x180014560  mov     edi, r14d
0x180014563  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014568  mov     [rbp+290h+pszResponseData._hstring], rax
0x18001456c  test    rax, rax
0x18001456f  jz      short loc_180014580
0x180014571  mov     pUIContext, rax; this
0x180014574  call    ??0CAuthBrokerContext@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::CAuthBrokerContext::CAuthBrokerContext(void)
0x180014579  mov     rdi, rax
0x18001457c  mov     [rbp+290h+pszResponseData._hstring], r14
0x180014580  lea     pUIContext, [rbp+290h+pszResponseData]; this
0x180014584  call    ??1?$MakeAllocator@VCWebAuthOperation@Web@Authentication@Security@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>::~MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>(void)
0x180014589  test    rdi, rdi
0x18001458c  jnz     loc_180014806
0x180014592  mov     ebx, 8007000Eh
0x180014597  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001459e  lea     r15, WPP_GLOBAL_Control
0x1800145a5  cmp     pUIContext, r15
0x1800145a8  jz      short loc_1800145C9
0x1800145aa  test    byte ptr [pUIContext+44h], 8
0x1800145ae  jz      short loc_1800145C9
0x1800145b0  cmp     byte ptr [pUIContext+41h], 2
0x1800145b4  jb      short loc_1800145C9
0x1800145b6  lea     fInProcActivation, [rdi+13h]; id
0x1800145b9  mov     pUIContext, [pUIContext+38h]; Logger
0x1800145bd  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x1800145c4  call    WPP_SF_
0x1800145c9  mov     r14d, r13d
0x1800145cc  call    IsDirectUIUnInitThreadPresent
0x1800145d1  test    al, al
0x1800145d3  jz      short loc_180014619
0x1800145d5  mov     pUIContext, [rsp+390h+wndMgmt]
0x1800145da  test    pUIContext, pUIContext
0x1800145dd  jz      short loc_180014619
0x1800145df  call    cs:__imp_FreeWndMgmt
0x1800145e5  test    eax, eax
0x1800145e7  jns     short loc_180014619
0x1800145e9  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800145f0  cmp     pUIContext, r15
0x1800145f3  jz      short loc_180014619
0x1800145f5  test    byte ptr [pUIContext+44h], 8
0x1800145f9  jz      short loc_180014619
0x1800145fb  cmp     byte ptr [pUIContext+41h], 2
0x1800145ff  jb      short loc_180014619
0x180014601  mov     pUIContext, [pUIContext+38h]; Logger
0x180014605  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x18001460c  mov     fInProcActivation, 37h ; '7'; id
0x180014611  mov     r9d, eax; _a1
0x180014614  call    WPP_SF_d
0x180014619  test    r14d, r14d
0x18001461c  jz      short loc_180014626
0x18001461e  mov     pUIContext, r13; hWnd
0x180014621  call    ?UnregisterWindowServiceForAccountsControl@@YAXPEAUHWND__@@@Z; UnregisterWindowServiceForAccountsControl(HWND__ *)
0x180014626  test    ebx, ebx
0x180014628  jns     short loc_180014670
0x18001462a  mov     rax, [r12]
0x18001462e  mov     fInProcActivation, ebx
0x180014630  mov     pUIContext, r12
0x180014633  mov     rax, [rax+68h]
0x180014637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001463c  test    eax, eax
0x18001463e  jns     short loc_180014670
0x180014640  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014647  cmp     pUIContext, r15
0x18001464a  jz      short loc_180014670
0x18001464c  test    byte ptr [pUIContext+44h], 8
0x180014650  jz      short loc_180014670
0x180014652  cmp     byte ptr [pUIContext+41h], 2
0x180014656  jb      short loc_180014670
0x180014658  mov     pUIContext, [pUIContext+38h]; Logger
0x18001465c  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180014663  mov     fInProcActivation, 38h ; '8'; id
0x180014668  mov     r9d, eax; _a1
0x18001466b  call    WPP_SF_d
0x180014670  lea     pUIContext, [rbp+290h+processContext]; processContext
0x180014674  call    ?ReleaseAuthHostProcess@@YAJPEAU_AUTH_HOST_PROCESS_CONTEXT@@@Z; ReleaseAuthHostProcess(_AUTH_HOST_PROCESS_CONTEXT *)
0x180014679  mov     ebx, eax
0x18001467b  test    eax, eax
0x18001467d  jns     short loc_1800146AF
0x18001467f  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014686  cmp     pUIContext, r15
0x180014689  jz      short loc_1800146B6
0x18001468b  test    byte ptr [pUIContext+44h], 8
0x18001468f  jz      short loc_1800146B6
0x180014691  cmp     byte ptr [pUIContext+41h], 2
0x180014695  jb      short loc_1800146B6
0x180014697  mov     pUIContext, [pUIContext+38h]; Logger
0x18001469b  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x1800146a2  mov     fInProcActivation, 39h ; '9'; id
0x1800146a7  mov     r9d, eax; _a1
0x1800146aa  call    WPP_SF_d
0x1800146af  mov     pUIContext, cs:WPP_GLOBAL_Control
0x1800146b6  mov     rax, [rbp+290h+hObject]
0x1800146ba  test    rax, rax
0x1800146bd  jz      short loc_1800146CF
0x1800146bf  mov     pUIContext, rax; hObject
0x1800146c2  call    cs:__imp_CloseHandle
0x1800146c8  mov     pUIContext, cs:WPP_GLOBAL_Control
0x1800146cf  mov     rax, [rbp+290h+systemDirectoryPath]
0x1800146d3  test    rax, rax
0x1800146d6  jz      short loc_1800146E8
0x1800146d8  mov     pUIContext, rax; pv
0x1800146db  call    cs:__imp_CoTaskMemFree
0x1800146e1  mov     pUIContext, cs:WPP_GLOBAL_Control
0x1800146e8  cmp     pUIContext, r15; __annotation("TMF:",
0x1800146eb  jz      short loc_18001470E
0x1800146ed  test    byte ptr [pUIContext+44h], 8
0x1800146f1  jz      short loc_18001470E
0x1800146f3  cmp     byte ptr [pUIContext+41h], 5
0x1800146f7  jb      short loc_18001470E
0x1800146f9  mov     pUIContext, [pUIContext+38h]; Logger
0x1800146fd  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180014704  mov     fInProcActivation, 3Ah ; ':'; id
0x180014709  call    WPP_SF_
0x18001470e  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x180014714  cmp     eax, 5
0x180014717  jbe     short loc_18001474D
0x180014719  mov     rdx, 400000000000h; keyword
0x180014723  lea     pUIContext, _Tlgg_hMyWABTraceLoggingProviderProv; hProvider
0x18001472a  call    _tlgKeywordOn
0x18001472f  test    al, al
0x180014731  jz      short loc_18001474D
0x180014733  lea     rax, [rsp+390h+dwResponseErrorDetail]; __annotation("_TlgWrite:|844|g_hMyWABTraceLoggingProvider|"WAB_ActivateAppContainerError"=|"HResult"=")
0x180014738  mov     dword ptr [rsp+390h+dwResponseErrorDetail], ebx
0x18001473c  lea     rdx, _tlgEvent._tlgChannel; <wrappedArgs_0>
0x180014743  mov     qword ptr [rsp+390h+dwDesiredAccess], rax; <writerArgs_0>
0x180014748  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001474d  lea     rdx, [rbp+290h+threadActivitySetter.m_SavedActivityId]; ActivityId
0x180014751  mov     ecx, 4; ControlCode
0x180014756  call    cs:__imp_EventActivityIdControl
0x18001475c  mov     pUIContext, [rbp+290h+windowFactory.ptr_]
0x180014760  test    pUIContext, pUIContext
0x180014763  jz      short loc_180014779
0x180014765  mov     [rbp+290h+windowFactory.ptr_], 0
0x18001476d  mov     rax, [pUIContext]
0x180014770  mov     rax, [rax+10h]
0x180014774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014779  lea     pUIContext, [rbp+290h+pszTitle]; this
0x18001477d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180014782  lea     pUIContext, [rbp+290h+pszEnd]; this
0x180014786  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001478b  lea     pUIContext, [rbp+290h+pszTarget]; this
0x18001478f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180014794  mov     pUIContext, [rsp+390h+tokenHandle._obj]; hObject
0x180014799  mov     [rsp+390h+tokenHandle._obj], 0
0x1800147a2  lea     rax, [pUIContext-1]
0x1800147a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800147aa  ja      short loc_1800147B2
0x1800147ac  call    cs:__imp_CloseHandle
0x1800147b2  lea     pUIContext, [rbp+290h+spBrokerContext]; this
0x1800147b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147bb  lea     pUIContext, [rbp+290h+spAuthHostIUnknown]; this
0x1800147bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147c4  test    rdi, rdi
0x1800147c7  jz      short loc_1800147D8
0x1800147c9  mov     rax, [rdi]
0x1800147cc  mov     pUIContext, rdi
0x1800147cf  mov     rax, [rax+10h]
0x1800147d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147d8  lea     pUIContext, [rbp+290h+spAuthHost]; this
0x1800147dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147e1  xor     eax, eax
0x1800147e3  mov     pUIContext, [rbp+290h+var_50]
0x1800147ea  xor     pUIContext, rsp; StackCookie
0x1800147ed  call    __security_check_cookie
0x1800147f2  add     rsp, 358h
0x1800147f9  pop     r15
0x1800147fb  pop     r14
0x1800147fd  pop     r13
0x1800147ff  pop     r12
0x180014801  pop     rdi
0x180014802  pop     rsi
0x180014803  pop     rbx
0x180014804  pop     rbp
0x180014805  retn
0x180014806  mov     rax, [r12]
0x18001480a  lea     rdx, [rbp+290h+pszTarget]
0x18001480e  mov     pUIContext, r12
0x180014811  mov     rax, [rax+40h]
0x180014815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001481a  mov     ebx, eax
0x18001481c  test    eax, eax
0x18001481e  jns     short loc_180014868
0x180014820  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014827  lea     r15, WPP_GLOBAL_Control
0x18001482e  cmp     pUIContext, r15
0x180014831  jz      loc_1800145C9
0x180014837  test    byte ptr [pUIContext+44h], 8
0x18001483b  jz      loc_1800145C9
0x180014841  cmp     byte ptr [pUIContext+41h], 2
0x180014845  jb      loc_1800145C9
0x18001484b  mov     fInProcActivation, 14h; id
0x180014850  mov     r9d, eax; _a1
0x180014853  mov     pUIContext, [pUIContext+38h]; Logger
0x180014857  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x18001485e  call    WPP_SF_d
0x180014863  jmp     loc_1800145C9
0x180014868  mov     rax, [r12]
0x18001486c  lea     rdx, [rbp+290h+pszEnd]
0x180014870  mov     pUIContext, r12
0x180014873  mov     rax, [rax+48h]
0x180014877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001487c  mov     ebx, eax
0x18001487e  test    eax, eax
0x180014880  jns     short loc_1800148B4
0x180014882  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014889  lea     r15, WPP_GLOBAL_Control
0x180014890  cmp     pUIContext, r15
0x180014893  jz      loc_1800145C9
0x180014899  test    byte ptr [pUIContext+44h], 8
0x18001489d  jz      loc_1800145C9
0x1800148a3  cmp     byte ptr [pUIContext+41h], 2
0x1800148a7  jb      loc_1800145C9
0x1800148ad  mov     fInProcActivation, 15h
0x1800148b2  jmp     short loc_180014850
0x1800148b4  mov     rax, [r12]
0x1800148b8  lea     rdx, [rsp+390h+dwBrokerFlags]
0x1800148bd  mov     pUIContext, r12
0x1800148c0  mov     [rsp+390h+dwBrokerFlags], r14d
0x1800148c5  mov     rax, [rax+50h]
0x1800148c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ce  mov     ebx, eax
0x1800148d0  test    eax, eax
0x1800148d2  jns     short loc_18001491C
0x1800148d4  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800148db  lea     r15, WPP_GLOBAL_Control
0x1800148e2  cmp     pUIContext, r15
0x1800148e5  jz      loc_1800145C9
0x1800148eb  test    byte ptr [pUIContext+44h], 8
0x1800148ef  jz      loc_1800145C9
0x1800148f5  cmp     byte ptr [pUIContext+41h], 2
0x1800148f9  jb      loc_1800145C9
0x1800148ff  mov     fInProcActivation, 16h; id
0x180014904  mov     r9d, eax; _a1
0x180014907  mov     pUIContext, [pUIContext+38h]; Logger
0x18001490b  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180014912  call    WPP_SF_d
0x180014917  jmp     loc_1800145C9
0x18001491c  movaps  xmm0, xmmword ptr [rbp+290h+activityID.Data1]
0x180014920  lea     rax, [rbp+290h+pszResponseData]
0x180014924  mov     r9d, [rsp+390h+dwBrokerFlags]
0x180014929  mov     pUIContext, rdi
0x18001492c  mov     r8, [rbp+290h+pszEnd._hstring]
0x180014930  mov     rdx, [rbp+290h+pszTarget._hstring]
0x180014934  movdqa  xmmword ptr [rbp+290h+pszResponseData._hstring], xmm0
0x180014939  mov     qword ptr [rsp+390h+dwDesiredAccess], rax
0x18001493e  call    ?Initialize@CAuthBrokerContext@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@0IU_GUID@@@Z; Windows::Internal::Security::Authentication::CAuthBrokerContext::Initialize(HSTRING__ *,HSTRING__ *,uint,_GUID)
0x180014943  mov     ebx, eax
0x180014945  test    eax, eax
0x180014947  jns     short loc_18001497E
0x180014949  mov     pUIContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014950  lea     r15, WPP_GLOBAL_Control
  ... truncated ...
```
