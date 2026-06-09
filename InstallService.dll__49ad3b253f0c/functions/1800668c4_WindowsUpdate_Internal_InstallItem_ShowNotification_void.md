# WindowsUpdate::Internal::InstallItem::ShowNotification(void)

- ea: `0x1800668c4`
- end: `0x18006727b`
- name: `?ShowNotification@InstallItem@Internal@WindowsUpdate@@QEAAJXZ`
- size: `2487`
- prototype: `__int64 __fastcall(WindowsUpdate::Internal::InstallItem *__hidden this)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180057fbc`
- `0x180061994`

## callees

- `0x1800101f4`
- `0x1800123f8`
- `0x18001448c`
- `0x180014f18`
- `0x18001c414`
- `0x18001c844`
- `0x180020f5c`
- `0x1800228c4`
- `0x18002865c`
- `0x1800291a8`
- `0x18002ec2c`
- `0x18003fe8c`
- `0x180056c60`
- `0x18005b864`
- `0x1800641b8`
- `0x180064bbc`
- `0x1800668c4`
- `0x1800672a8`
- `0x1800682e0`
- `0x1801047b0`
- `0x180104c94`
- `0x1801db1b0`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180066918`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180066c3d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180066918`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180066c3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066e0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066e70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066b5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066e0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066e70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066efe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066efe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180066f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067155`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006707c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006707c`

## string_xrefs

- `0x180066f64`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180067099`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x1800670e6`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180067187`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x1800671db`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x1800671ef`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180067203`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180067217`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x18006722b`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x18006723f`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180067253`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180067268`: `onecoreuap\enduser\winstore\installservice\lib\installitem.cpp`
- `0x180066f57`: `WindowsUpdate::Internal::InstallItem::ShowNotification`
- `0x18006708d`: `WindowsUpdate::Internal::InstallItem::ShowNotification`
- `0x1800670da`: `WindowsUpdate::Internal::InstallItem::ShowNotification`
- `0x18006717a`: `WindowsUpdate::Internal::InstallItem::ShowNotification`
- `0x180067086`: `CoCreateInstance(__uuidof(InstallServiceUserBroker), nullptr, CLSCTX_LOCAL_SERVER | CLSCTX_ENABLE_CLOAKING | CLSCTX_ENABLE_AAA, IID_PPV_ARGS(&pinToHelper))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WindowsUpdate::Internal::InstallItem::ShowNotification(
        WindowsUpdate::Internal::InstallItem *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  CallerContext *v5; // rbx
  char *v6; // rax
  __int64 *v7; // rax
  __int64 v8; // rcx
  char v9; // r14
  int v10; // ebx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  bool v14; // di
  int v15; // eax
  char v16; // r15
  __int64 (__fastcall *v17)(WindowsUpdate::Internal::InstallItem *, HSTRING *); // rbx
  int v18; // eax
  __int64 result; // rax
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // eax
  int v27; // eax
  int User; // eax
  __int64 v29; // rcx
  unsigned int v30; // ebx
  int v31; // ebx
  unsigned int v32; // eax
  __int64 (__fastcall *v33)(WindowsUpdate::Internal::InstallItem *, HSTRING *); // rbx
  int v34; // eax
  int v35; // eax
  char *v36; // rdx
  __int64 TokenForSid; // rax
  int v38; // eax
  LPVOID v39; // rsi
  void (__fastcall *v40)(LPVOID, PCWSTR, _QWORD); // rdi
  unsigned int v41; // ebx
  PCWSTR StringRawBuffer; // rax
  int ppv; // [rsp+20h] [rbp-158h]
  HRESULT ppva; // [rsp+20h] [rbp-158h]
  int v45; // [rsp+28h] [rbp-150h]
  int v46; // [rsp+28h] [rbp-150h]
  PCWSTR v47; // [rsp+40h] [rbp-138h]
  struct Windows::System::IUser *v48; // [rsp+70h] [rbp-108h] BYREF
  int v49; // [rsp+78h] [rbp-100h]
  HSTRING string[2]; // [rsp+80h] [rbp-F8h] BYREF
  HSTRING v51[2]; // [rsp+90h] [rbp-E8h] BYREF
  HSTRING v52[2]; // [rsp+A0h] [rbp-D8h] BYREF
  HSTRING v53[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-B8h]
  int v55; // [rsp+C8h] [rbp-B0h] BYREF
  __int16 v56; // [rsp+CCh] [rbp-ACh]
  bool v57; // [rsp+CEh] [rbp-AAh]
  _QWORD v58[2]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+E0h] [rbp-98h] BYREF
  _BYTE v60[24]; // [rsp+E8h] [rbp-90h] BYREF
  _BYTE v61[4]; // [rsp+100h] [rbp-78h] BYREF
  int v62; // [rsp+104h] [rbp-74h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]
  unsigned int v64; // [rsp+180h] [rbp+8h] BYREF
  int v65; // [rsp+188h] [rbp+10h] BYREF
  LPVOID v66; // [rsp+190h] [rbp+18h] BYREF

  v5 = (WindowsUpdate::Internal::InstallItem *)((char *)this + 104);
  v6 = (char *)this + 176;
  if ( !*((_QWORD *)this + 22) )
    v6 = (char *)this + 104;
  try
  {
    if ( v6[24] )
      return 0;
    if ( (unsigned int)IsDeviceXbox() )
      return 0;
    InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0);
    if ( ((dword_1802E4F60 - 9) & 0xFFFFFFFB) == 0 || !CallerContext::IsUserLoggedIn(v5) )
      return 0;
    v48 = 0;
    *(_OWORD *)string = 0;
    *(_OWORD *)v51 = 0;
    *(_OWORD *)v52 = 0;
    *(_OWORD *)v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 256;
    v57 = 0;
    wil::AcquireSRWLockExclusive(&v66, (char *)this + 328);
    if ( !*((_QWORD *)this + 40) )
    {
      v7 = (__int64 *)wil::MakeAndInitializeOrThrow<NotificationHelper,HINSTANCE__ * &>(&v64);
      v8 = 0;
      if ( &v59 != v7 )
      {
        v8 = *v7;
        *v7 = 0;
      }
      v59 = *((_QWORD *)this + 40);
      *((_QWORD *)this + 40) = v8;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v59);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v64);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v66);
    WindowsUpdate::Internal::InstallItem::LastProgressStatus(this, v61);
    v9 = 1;
    v10 = v62;
    if ( v62 == 2 )
    {
      v49 = 1;
      goto LABEL_29;
    }
    if ( v62 == 3 )
    {
      v49 = 2;
      goto LABEL_29;
    }
    if ( v62 != 4 )
    {
      if ( v62 == 5 )
      {
        v49 = 7;
      }
      else
      {
        if ( v62 == 6 )
        {
          v49 = 3;
          goto LABEL_29;
        }
        if ( v62 != 12 )
        {
          if ( v62 == 13 )
            v49 = 0;
          goto LABEL_29;
        }
        v49 = 6;
      }
      v9 = 0;
      goto LABEL_29;
    }
    LOBYTE(v64) = 0;
    if ( (*(int (__fastcall **)(WindowsUpdate::Internal::InstallItem *, unsigned int *))(*(_QWORD *)this + 208LL))(
           this,
           &v64) < 0
      || (HIBYTE(v56) = 0, !(_BYTE)v64) )
    {
      HIBYTE(v56) = 1;
    }
    v9 = 0;
    v49 = 4;
LABEL_29:
    v65 = 0;
    v11 = *(_QWORD *)this;
    if ( v9 )
    {
      v12 = (*(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, int *))(v11 + 304))(this, &v65);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
          (const char *)(unsigned int)v12,
          ppv);
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, int *))(v11 + 288))(this, &v65);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
          (const char *)(unsigned int)v13,
          ppv);
    }
    v14 = 0;
    v15 = v65;
    if ( v65 == 3 )
    {
      v16 = 1;
      goto LABEL_35;
    }
    if ( !v65 )
    {
      _m_prefetchw((char *)this + 312);
      if ( (_InterlockedOr((volatile signed __int32 *)this + 78, 0) & 1) == 0 )
        goto LABEL_39;
      v15 = v65;
    }
    v16 = 0;
    if ( *((_DWORD *)this + 70) == 1 )
    {
      if ( v10 != 4 )
      {
LABEL_61:
        if ( v49 == 1 || v49 == 2 || v49 == 3 )
        {
          v27 = (*(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, int *))(*(_QWORD *)this + 96LL))(
                  this,
                  &v55);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x219,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
              (const char *)(unsigned int)v27,
              ppv);
        }
        else if ( v49 == 4 )
        {
          WindowsDeleteString(v52[1]);
          v52[1] = 0;
          v26 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**((_QWORD **)this + 11) + 72LL))(
                  *((_QWORD *)this + 11),
                  &v52[1]);
          if ( v26 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x21C,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
              (const char *)(unsigned int)v26,
              ppv);
        }
LABEL_35:
        v17 = *(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, HSTRING *))(*(_QWORD *)this + 48LL);
        WindowsDeleteString(string[1]);
        string[1] = 0;
        v18 = v17(this, &string[1]);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x224,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
            (const char *)(unsigned int)v18,
            ppv);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v48);
        User = WindowsUpdate::Internal::InstallItem::get_User(this, &v48);
        if ( User < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x225,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
            (const char *)(unsigned int)User,
            ppv);
        if ( v16 )
        {
          CallerContext::ImpersonateUser((char *)this + 104, v58);
          v30 = NotificationHelper::RemoveNotification(v29, &v48, string[1]);
          TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v58);
          NotificationMetadata::~NotificationMetadata((NotificationMetadata *)&v48);
          return v30;
        }
        if ( v14 )
        {
          WindowsDeleteString(v53[0]);
          v53[0] = 0;
          v31 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**((_QWORD **)this + 12) + 120LL))(
                  *((_QWORD *)this + 12),
                  v53);
          if ( v31 >= 0 && v53[0] )
          {
            if ( WindowsUpdate::Internal::InstallItem::UserRetryCount(this) > 1
              || (v32 = WindowsUpdate::Internal::InstallItem::SystemAttemptCount(this), LOBYTE(v56) = 0, v32) )
            {
              LOBYTE(v56) = 1;
            }
            WindowsDeleteString(v51[1]);
            v51[1] = 0;
            (*(void (__fastcall **)(_QWORD, HSTRING *))(**((_QWORD **)this + 12) + 56LL))(
              *((_QWORD *)this + 12),
              &v51[1]);
            WindowsDeleteString(v52[0]);
            v52[0] = 0;
            (*(void (__fastcall **)(_QWORD, HSTRING *))(**((_QWORD **)this + 12) + 72LL))(*((_QWORD *)this + 12), v52);
            v33 = *(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, HSTRING *))(*(_QWORD *)this + 112LL);
            WindowsDeleteString(v51[0]);
            v51[0] = 0;
            v34 = v33(this, v51);
            if ( v34 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x23D,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
                (const char *)(unsigned int)v34,
                ppv);
            CallerContext::ImpersonateUser((char *)this + 104, v58);
            v35 = NotificationHelper::ShowNotification(
                    *((NotificationHelper **)this + 40),
                    (struct NotificationMetadata *)&v48);
            if ( v35 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x241,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
                (const char *)(unsigned int)v35,
                ppv);
            TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v58);
            WindowsGetStringRawBuffer(v52[0], 0);
            WindowsGetStringRawBuffer(v51[1], 0);
            WindowsGetStringRawBuffer(v51[0], 0);
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
              0x247u,
              "WindowsUpdate::Internal::InstallItem::ShowNotification",
              -1,
              L"Notification shown for PFN: %s, SkuId: %s, CatalogId: %s, NotificationType: %d, Progress if needed: %d\n",
              0,
              0);
            if ( v49 == 4 )
            {
              if ( HIBYTE(v56) )
              {
                _m_prefetchw((char *)this + 312);
                if ( (_InterlockedOr((volatile signed __int32 *)this + 78, 0) & 0x2000000) != 0
                  || (_m_prefetchw((char *)this + 312),
                      (_InterlockedOr((volatile signed __int32 *)this + 78, 0) & 0x4000000) != 0)
                  || (_m_prefetchw((char *)this + 312),
                      (_InterlockedOr((volatile signed __int32 *)this + 78, 0) & 0x8000000) != 0) )
                {
                  v36 = (char *)this + 104;
                  if ( *((_QWORD *)this + 22) )
                    v36 = (char *)this + 176;
                  TokenForSid = TokenHelpers::GetTokenForSid(v58, *(_QWORD *)v36);
                  TokenHelpers::ImpersonateContext::ImpersonateContext(v60, TokenForSid);
                  v58[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
                  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v58);
                  v66 = 0;
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v66);
                  ppva = CoCreateInstance(
                           &GUID_082bc1fc_591a_4a9e_9d90_8ab689f49519,
                           0,
                           0x110004u,
                           &GUID_53dacab2_58a8_4483_8cba_30007cd7bb8d,
                           &v66);
                  if ( (int)TraceHR(
                              "onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
                              0x25Bu,
                              "WindowsUpdate::Internal::InstallItem::ShowNotification",
                              "CoCreateInstance(__uuidof(InstallServiceUserBroker), nullptr, CLSCTX_LOCAL_SERVER | CLSCTX"
                              "_ENABLE_CLOAKING | CLSCTX_ENABLE_AAA, IID_PPV_ARGS(&pinToHelper))",
                              ppva,
                              v45) >= 0 )
                  {
                    v64 = 0;
                    v38 = (*(__int64 (__fastcall **)(WindowsUpdate::Internal::InstallItem *, unsigned int *))(*(_QWORD *)this + 128LL))(
                            this,
                            &v64);
                    if ( (int)TraceHR(
                                "onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
                                0x25Eu,
                                "WindowsUpdate::Internal::InstallItem::ShowNotification",
                                "get_Flags(&pinFlags)",
                                v38,
                                v46) >= 0 )
                    {
                      v39 = v66;
                      v40 = *(void (__fastcall **)(LPVOID, PCWSTR, _QWORD))(*(_QWORD *)v66 + 24LL);
                      v41 = v64;
                      StringRawBuffer = WindowsGetStringRawBuffer(v51[0], 0);
                      v40(v39, StringRawBuffer, v41);
                    }
                  }
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v66);
                  TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v60);
                }
              }
            }
            goto LABEL_39;
          }
          v47 = WindowsGetStringRawBuffer(string[1], 0);
          LogMessage(
            4u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
            0x233u,
            "WindowsUpdate::Internal::InstallItem::ShowNotification",
            v31,
            L"Couldn't find product title for productId = %s. Not showing any notifications",
            0,
            0,
            v47);
          NotificationMetadata::~NotificationMetadata((NotificationMetadata *)&v48);
          return (unsigned int)v31;
        }
LABEL_39:
        NotificationMetadata::~NotificationMetadata((NotificationMetadata *)&v48);
        return 0;
      }
      v49 = 5;
LABEL_60:
      v14 = 1;
      goto LABEL_61;
    }
    if ( v15 )
    {
      v57 = v15 == 2;
      goto LABEL_60;
    }
    v20 = v10 - 2;
    if ( !v20 )
      goto LABEL_54;
    v21 = v20 - 1;
    if ( !v21 )
      goto LABEL_54;
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_54;
      v24 = v23 - 1;
      if ( !v24 )
        goto LABEL_54;
      v25 = v24 - 6;
      if ( v25 )
      {
        if ( v25 != 1 )
        {
          v14 = 0;
LABEL_55:
          _m_prefetchw((char *)this + 312);
          if ( (_InterlockedOr((volatile signed __int32 *)this + 78, 0) & 0x8000) != 0 && !v9 )
            v57 = 1;
          goto LABEL_61;
        }
        v57 = 1;
LABEL_54:
        InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0);
        v14 = dword_1802E4F60 == 3;
        goto LABEL_55;
      }
    }
    v14 = 1;
    goto LABEL_55;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x26A,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installitem.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800668c4  mov     [rsp+arg_18], rbx
0x1800668c9  push    rsi
0x1800668ca  push    rdi
0x1800668cb  push    r12
0x1800668cd  push    r14
0x1800668cf  push    r15
0x1800668d1  sub     rsp, 150h
0x1800668d8  mov     rsi, rcx
0x1800668db  lea     rbx, [rcx+68h]
0x1800668df  lea     rax, [rbx+48h]
0x1800668e3  xor     r12d, r12d
0x1800668e6  cmp     [rax], r12
0x1800668e9  cmovz   rax, rbx
0x1800668ed  cmp     [rax+18h], r12b
0x1800668f1  jnz     loc_1800671B5
0x1800668f7  call    ?IsDeviceXbox@@YAHXZ; IsDeviceXbox(void)
0x1800668fc  test    eax, eax
0x1800668fe  jnz     loc_1800671B5
0x180066904  xor     r9d, r9d; Context
0x180066907  xor     r8d, r8d; Parameter
0x18006690a  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x180066911  lea     rcx, InitOnce; InitOnce
0x180066918  call    cs:__imp_InitOnceExecuteOnce
0x18006691e  mov     eax, cs:dword_1802E4F60
0x180066924  add     eax, 0FFFFFFF7h
0x180066927  test    eax, 0FFFFFFFBh
0x18006692c  jz      loc_1800671B5
0x180066932  mov     rcx, rbx; this
0x180066935  call    ?IsUserLoggedIn@CallerContext@@QEBA_NXZ; CallerContext::IsUserLoggedIn(void)
0x18006693a  test    al, al
0x18006693c  jz      loc_1800671B5
0x180066942  mov     [rsp+178h+var_108], r12
0x180066947  xorps   xmm0, xmm0
0x18006694a  movdqa  xmmword ptr [rsp+178h+string], xmm0
0x180066953  xorps   xmm1, xmm1
0x180066956  movdqa  xmmword ptr [rsp+178h+var_E8], xmm1
0x18006695f  movdqa  xmmword ptr [rsp+178h+var_D8], xmm0
0x180066968  movdqa  xmmword ptr [rsp+178h+var_C8], xmm1
0x180066971  mov     [rsp+178h+var_B8], r12
0x180066979  mov     [rsp+178h+var_B0], r12d
0x180066981  mov     [rsp+178h+var_AC], 100h
0x18006698b  mov     [rsp+178h+var_AA], r12b
0x180066993  lea     rdx, [rsi+148h]
0x18006699a  lea     rcx, [rsp+178h+arg_10]
0x1800669a2  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800669a7  nop
0x1800669a8  cmp     [rsi+140h], r12
0x1800669af  jnz     short loc_180066A05
0x1800669b1  lea     rcx, [rsp+178h+arg_0]
0x1800669b9  call    ??$MakeAndInitializeOrThrow@VNotificationHelper@@AEAPEAUHINSTANCE__@@@wil@@YA?AV?$ComPtr@VNotificationHelper@@@WRL@Microsoft@@AEAPEAUHINSTANCE__@@@Z; wil::MakeAndInitializeOrThrow<NotificationHelper,HINSTANCE__ * &>(HINSTANCE__ * &)
0x1800669be  mov     ecx, r12d
0x1800669c1  lea     rdx, [rsp+178h+var_98]
0x1800669c9  cmp     rdx, rax
0x1800669cc  jz      short loc_1800669D4
0x1800669ce  mov     rcx, [rax]
0x1800669d1  mov     [rax], r12
0x1800669d4  mov     rax, [rsi+140h]
0x1800669db  mov     [rsp+178h+var_98], rax
0x1800669e3  mov     [rsi+140h], rcx
0x1800669ea  lea     rcx, [rsp+178h+var_98]
0x1800669f2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800669f7  lea     rcx, [rsp+178h+arg_0]
0x1800669ff  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180066a04  nop
0x180066a05  lea     rcx, [rsp+178h+arg_10]
0x180066a0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180066a12  lea     rdx, [rsp+178h+var_78]
0x180066a1a  mov     rcx, rsi
0x180066a1d  call    ?LastProgressStatus@InstallItem@Internal@WindowsUpdate@@QEAA?AUInstallWorkStatus@23@XZ; WindowsUpdate::Internal::InstallItem::LastProgressStatus(void)
0x180066a22  mov     r14b, 1
0x180066a25  mov     ebx, [rsp+178h+var_74]
0x180066a2c  mov     ecx, ebx
0x180066a2e  sub     ecx, 2
0x180066a31  jz      loc_180066ADF
0x180066a37  sub     ecx, 1
0x180066a3a  jz      loc_180066AD5
0x180066a40  sub     ecx, 1
0x180066a43  jz      short loc_180066A88
0x180066a45  sub     ecx, 1
0x180066a48  jz      short loc_180066A7E
0x180066a4a  sub     ecx, 1
0x180066a4d  jz      short loc_180066A74
0x180066a4f  sub     ecx, 6
0x180066a52  jz      short loc_180066A67
0x180066a54  cmp     ecx, 1
0x180066a57  jnz     loc_180066AE7
0x180066a5d  mov     [rsp+178h+var_100], r12d
0x180066a62  jmp     loc_180066AE7
0x180066a67  mov     [rsp+178h+var_100], 6
0x180066a6f  mov     r14b, r12b
0x180066a72  jmp     short loc_180066AE7
0x180066a74  mov     [rsp+178h+var_100], 3
0x180066a7c  jmp     short loc_180066AE7
0x180066a7e  mov     [rsp+178h+var_100], 7
0x180066a86  jmp     short loc_180066A6F
0x180066a88  mov     byte ptr [rsp+178h+arg_0], r12b
0x180066a90  mov     rax, [rsi]
0x180066a93  lea     rdx, [rsp+178h+arg_0]
0x180066a9b  mov     rcx, rsi
0x180066a9e  mov     rax, [rax+0D0h]
0x180066aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066aaa  test    eax, eax
0x180066aac  js      short loc_180066AC0
0x180066aae  cmp     byte ptr [rsp+178h+arg_0], r12b
0x180066ab6  mov     byte ptr [rsp+178h+var_AC+1], r12b
0x180066abe  jnz     short loc_180066AC8
0x180066ac0  mov     byte ptr [rsp+178h+var_AC+1], r14b
0x180066ac8  mov     r14b, r12b
0x180066acb  mov     [rsp+178h+var_100], 4
0x180066ad3  jmp     short loc_180066AE7
0x180066ad5  mov     [rsp+178h+var_100], 2
0x180066add  jmp     short loc_180066AE7
0x180066adf  mov     [rsp+178h+var_100], 1
0x180066ae7  mov     [rsp+178h+arg_8], r12d
0x180066aef  mov     rax, [rsi]
0x180066af2  lea     rdx, [rsp+178h+arg_8]
0x180066afa  mov     rcx, rsi
0x180066afd  test    r14b, r14b
0x180066b00  jz      short loc_180066B20
0x180066b02  mov     rax, [rax+130h]
0x180066b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b0e  mov     rcx, [rsp+178h]; this
0x180066b16  test    eax, eax
0x180066b18  js      loc_1800671D8
0x180066b1e  jmp     short loc_180066B3C
0x180066b20  mov     rax, [rax+120h]
0x180066b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b2c  mov     rcx, [rsp+178h]; this
0x180066b34  test    eax, eax
0x180066b36  js      loc_1800671EC
0x180066b3c  mov     dil, r12b
0x180066b3f  mov     eax, [rsp+178h+arg_8]
0x180066b46  cmp     eax, 3
0x180066b49  jnz     short loc_180066B93
0x180066b4b  mov     r15b, 1
0x180066b4e  mov     rax, [rsi]
0x180066b51  mov     rbx, [rax+30h]
0x180066b55  mov     rcx, [rsp+178h+string+8]; string
0x180066b5d  call    cs:__imp_WindowsDeleteString
0x180066b63  mov     [rsp+178h+string+8], r12
0x180066b6b  lea     rdx, [rsp+178h+string+8]
0x180066b73  mov     rcx, rsi
0x180066b76  mov     rax, rbx
0x180066b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b7e  mov     rcx, [rsp+178h]; this
0x180066b86  test    eax, eax
0x180066b88  js      loc_180067200
0x180066b8e  jmp     loc_180066D1D
0x180066b93  test    eax, eax
0x180066b95  jnz     short loc_180066BCF
0x180066b97  prefetchw byte ptr [rsi+138h]
0x180066b9e  mov     eax, [rsi+138h]
0x180066ba4  mov     ecx, eax
0x180066ba6  or      ecx, r12d
0x180066ba9  lock cmpxchg [rsi+138h], ecx
0x180066bb1  jnz     short loc_180066BA4
0x180066bb3  test    al, 1
0x180066bb5  jnz     short loc_180066BC8
0x180066bb7  lea     rcx, [rsp+178h+var_108]; this
0x180066bbc  call    ??1NotificationMetadata@@QEAA@XZ; NotificationMetadata::~NotificationMetadata(void)
0x180066bc1  xor     eax, eax
0x180066bc3  jmp     loc_1800671C0
0x180066bc8  mov     eax, [rsp+178h+arg_8]
0x180066bcf  mov     r15b, r12b
0x180066bd2  cmp     dword ptr [rsi+118h], 1
0x180066bd9  jnz     short loc_180066BF1
0x180066bdb  cmp     ebx, 4
0x180066bde  jnz     loc_180066C92
0x180066be4  mov     [rsp+178h+var_100], 5
0x180066bec  jmp     loc_180066C8F
0x180066bf1  test    eax, eax
0x180066bf3  jnz     loc_180066C84
0x180066bf9  sub     ebx, 2
0x180066bfc  jz      short loc_180066C29
0x180066bfe  sub     ebx, 1
0x180066c01  jz      short loc_180066C29
0x180066c03  sub     ebx, 1
0x180066c06  jz      short loc_180066C7F
0x180066c08  sub     ebx, 1
0x180066c0b  jz      short loc_180066C29
0x180066c0d  sub     ebx, 1
0x180066c10  jz      short loc_180066C29
0x180066c12  sub     ebx, 6
0x180066c15  jz      short loc_180066C7F
0x180066c17  cmp     ebx, 1
0x180066c1a  jz      short loc_180066C21
0x180066c1c  mov     dil, r12b
0x180066c1f  jmp     short loc_180066C4E
0x180066c21  mov     [rsp+178h+var_AA], 1
0x180066c29  xor     r9d, r9d; Context
0x180066c2c  xor     r8d, r8d; Parameter
0x180066c2f  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x180066c36  lea     rcx, InitOnce; InitOnce
0x180066c3d  call    cs:__imp_InitOnceExecuteOnce
0x180066c43  cmp     cs:dword_1802E4F60, 3
0x180066c4a  setz    dil
0x180066c4e  prefetchw byte ptr [rsi+138h]
0x180066c55  mov     eax, [rsi+138h]
0x180066c5b  mov     ecx, eax
0x180066c5d  or      ecx, r12d
0x180066c60  lock cmpxchg [rsi+138h], ecx
0x180066c68  jnz     short loc_180066C5B
0x180066c6a  bt      eax, 0Fh
0x180066c6e  jnb     short loc_180066C92
0x180066c70  test    r14b, r14b
0x180066c73  jnz     short loc_180066C92
0x180066c75  mov     [rsp+178h+var_AA], 1
0x180066c7d  jmp     short loc_180066C92
0x180066c7f  mov     dil, 1
0x180066c82  jmp     short loc_180066C4E
0x180066c84  cmp     eax, 2
0x180066c87  setz    [rsp+178h+var_AA]
0x180066c8f  mov     dil, 1
0x180066c92  mov     ecx, [rsp+178h+var_100]
0x180066c96  sub     ecx, 1
0x180066c99  jz      short loc_180066CF1
0x180066c9b  sub     ecx, 1
0x180066c9e  jz      short loc_180066CF1
0x180066ca0  sub     ecx, 1
0x180066ca3  jz      short loc_180066CF1
0x180066ca5  cmp     ecx, 1
0x180066ca8  jnz     loc_180066B4E
0x180066cae  mov     rcx, [rsp+178h+var_D8+8]; string
0x180066cb6  call    cs:__imp_WindowsDeleteString
0x180066cbc  mov     [rsp+178h+var_D8+8], r12
0x180066cc4  mov     rcx, [rsi+58h]
0x180066cc8  mov     rax, [rcx]
0x180066ccb  lea     rdx, [rsp+178h+var_D8+8]
0x180066cd3  mov     rax, [rax+48h]
0x180066cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cdc  mov     rcx, [rsp+178h]; this
0x180066ce4  test    eax, eax
0x180066ce6  js      loc_180067214
0x180066cec  jmp     loc_180066B4E
0x180066cf1  mov     rax, [rsi]
0x180066cf4  lea     rdx, [rsp+178h+var_B0]
0x180066cfc  mov     rcx, rsi
0x180066cff  mov     rax, [rax+60h]
0x180066d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d08  mov     rcx, [rsp+178h]; this
0x180066d10  test    eax, eax
0x180066d12  js      loc_180067228
0x180066d18  jmp     loc_180066B4E
0x180066d1d  lea     rcx, [rsp+178h+var_108]
0x180066d22  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180066d27  lea     rdx, [rsp+178h+var_108]; struct Windows::System::IUser **
0x180066d2c  mov     rcx, rsi; this
0x180066d2f  call    ?get_User@InstallItem@Internal@WindowsUpdate@@QEAAJPEAPEAUIUser@System@Windows@@@Z; WindowsUpdate::Internal::InstallItem::get_User(Windows::System::IUser * *)
0x180066d34  mov     rcx, [rsp+178h]; this
0x180066d3c  test    eax, eax
0x180066d3e  js      loc_18006723C
0x180066d44  test    r15b, r15b
0x180066d47  jz      short loc_180066D8D
0x180066d49  lea     rcx, [rsi+68h]
0x180066d4d  lea     rdx, [rsp+178h+var_A8]
0x180066d55  call    ?ImpersonateUser@CallerContext@@QEAA?AVImpersonateContext@TokenHelpers@@XZ; CallerContext::ImpersonateUser(void)
0x180066d5a  mov     r8, [rsp+178h+string+8]
0x180066d62  lea     rdx, [rsp+178h+var_108]
0x180066d67  call    ?RemoveNotification@NotificationHelper@@QEAAJAEBV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@PEAUHSTRING__@@@Z; NotificationHelper::RemoveNotification(Microsoft::WRL::ComPtr<Windows::System::IUser> const &,HSTRING__ *)
0x180066d6c  mov     ebx, eax
0x180066d6e  lea     rcx, [rsp+178h+var_A8]; this
0x180066d76  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x180066d7b  nop
0x180066d7c  lea     rcx, [rsp+178h+var_108]; this
0x180066d81  call    ??1NotificationMetadata@@QEAA@XZ; NotificationMetadata::~NotificationMetadata(void)
0x180066d86  mov     eax, ebx
0x180066d88  jmp     loc_1800671C0
0x180066d8d  test    dil, dil
0x180066d90  jz      loc_1800671A7
0x180066d96  mov     rcx, [rsp+178h+var_C8]; string
0x180066d9e  call    cs:__imp_WindowsDeleteString
0x180066da4  mov     [rsp+178h+var_C8], r12
0x180066dac  mov     rcx, [rsi+60h]
0x180066db0  mov     rax, [rcx]
0x180066db3  lea     rdx, [rsp+178h+var_C8]
0x180066dbb  mov     rax, [rax+78h]
0x180066dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dc4  mov     ebx, eax
0x180066dc6  test    eax, eax
0x180066dc8  js      loc_18006714B
0x180066dce  cmp     [rsp+178h+var_C8], r12
0x180066dd6  jz      loc_18006714B
0x180066ddc  mov     rcx, rsi; this
0x180066ddf  call    ?UserRetryCount@InstallItem@Internal@WindowsUpdate@@QEAAIXZ; WindowsUpdate::Internal::InstallItem::UserRetryCount(void)
0x180066de4  cmp     eax, 1
0x180066de7  ja      short loc_180066DFD
0x180066de9  mov     rcx, rsi; this
0x180066dec  call    ?SystemAttemptCount@InstallItem@Internal@WindowsUpdate@@QEAAIXZ; WindowsUpdate::Internal::InstallItem::SystemAttemptCount(void)
0x180066df1  test    eax, eax
0x180066df3  mov     byte ptr [rsp+178h+var_AC], r12b
0x180066dfb  jz      short loc_180066E05
0x180066dfd  mov     byte ptr [rsp+178h+var_AC], 1
0x180066e05  mov     rcx, [rsp+178h+var_E8+8]; string
0x180066e0d  call    cs:__imp_WindowsDeleteString
0x180066e13  mov     [rsp+178h+var_E8+8], r12
0x180066e1b  mov     rcx, [rsi+60h]
0x180066e1f  mov     rax, [rcx]
0x180066e22  lea     rdx, [rsp+178h+var_E8+8]
0x180066e2a  mov     rax, [rax+38h]
0x180066e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
