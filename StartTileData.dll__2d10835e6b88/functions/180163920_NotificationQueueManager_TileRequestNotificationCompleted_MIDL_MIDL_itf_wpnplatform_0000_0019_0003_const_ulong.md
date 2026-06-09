# NotificationQueueManager::TileRequestNotificationCompleted(__MIDL___MIDL_itf_wpnplatform_0000_0019_0003 const *,ulong)

- ea: `0x180163920`
- end: `0x180163fde`
- name: `?TileRequestNotificationCompleted@NotificationQueueManager@@UEAAJPEBU__MIDL___MIDL_itf_wpnplatform_0000_0019_0003@@K@Z`
- size: `1726`
- prototype: `int(NotificationQueueManager *__hidden this, const struct __MIDL___MIDL_itf_wpnplatform_0000_0019_0003 *, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800c5b3c`
- `0x180159390`
- `0x180161204`
- `0x180163920`
- `0x180163fe4`
- `0x1801640ac`
- `0x1801640d0`
- `0x180165320`
- `0x1801d98b0`
- `0x1801f5ce0`
- `0x180201e50`
- `0x18027ec50`
- `0x18027f050`
- `0x180280b80`
- `0x180283060`
- `0x1802834e4`
- `0x180283590`
- `0x1802856ec`
- `0x18028a790`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180163c30`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180163c30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180163a9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180163f99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180163a9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180163f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180163998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180163998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163b2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163bbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163c0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163f0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163b2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163b81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163bbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163c0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163f0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180163f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180163c22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180163e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180163e83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180163c22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180163e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180163e83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180163ace`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180163ace`

## string_xrefs

- `0x1801639b0`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801639d5`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180163ada`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180163b10`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x18016396d`: `TileRequestNotificationCompleted_Final`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NotificationQueueManager::TileRequestNotificationCompleted(
        NotificationQueueManager *this,
        const unsigned __int16 **a2,
        unsigned int a3)
{
  const unsigned __int16 *v6; // rbx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  struct TileNotificationManager *v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  HRESULT Instance; // eax
  __int64 v14; // rdx
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // eax
  TileNotificationManager *v18; // rbx
  int ApplicationUserModelId; // eax
  TileNotificationManager *v20; // rbx
  int TileID; // eax
  TileNotificationManager *v22; // rbx
  int PackageFullName; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  const wchar_t *StringRawBuffer; // rax
  unsigned int i; // r12d
  const WCHAR *v28; // r14
  const char *v29; // r9
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING, _QWORD, _QWORD); // rbx
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rbx
  __int64 (__fastcall *v36)(__int64, HSTRING, __int64, _QWORD); // rdi
  __int64 v37; // r8
  int v38; // eax
  int v39; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  struct TileNotificationManager *v42; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v44; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v45; // [rsp+58h] [rbp-A8h] BYREF
  struct IObjectCollection *v46; // [rsp+60h] [rbp-A0h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v51; // [rsp+88h] [rbp-78h] BYREF
  NotificationQueueManager *v52; // [rsp+90h] [rbp-70h]
  PCWSTR v53; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v54[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v52 = this;
  if ( a3 )
    v6 = *a2;
  else
    v6 = 0;
  wil::ActivityBase<NotificationLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
  v54[0] = &NotificationTelemetry::TileRequestNotificationCompleted_Final::`vftable';
  NotificationTelemetry::TileRequestNotificationCompleted_Final::StartActivity(
    (NotificationTelemetry::TileRequestNotificationCompleted_Final *)v54,
    a3,
    v6);
  if ( *((_DWORD *)this + 8) == GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x9C7,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      ppv);
  if ( a3 < 2 )
  {
    v7 = 2508;
LABEL_8:
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
LABEL_9:
    NotificationTelemetry::TileRequestNotificationCompleted_Final::~TileRequestNotificationCompleted_Final((NotificationTelemetry::TileRequestNotificationCompleted_Final *)v54);
    return v8;
  }
  if ( a3 > 6 )
  {
    v7 = 2509;
    goto LABEL_8;
  }
  v42 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 408);
  --*((_DWORD *)this + 94);
  Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v42);
  NotificationQueueManager::GetTileFromNotificationId((NotificationQueueManager *)((char *)this - 40), *a2, &v42);
  if ( !v42 )
  {
    v12 = 2147943568LL;
LABEL_76:
    wil::ActivityBase<NotificationLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54, v12);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_78;
  }
  *((_BYTE *)v42 + 117) = 1;
  v10 = v42;
  v11 = *((_DWORD *)v42 + 26);
  if ( v11 )
  {
    *((_DWORD *)v42 + 26) = v11 - 1;
    v10 = v42;
  }
  if ( *((_DWORD *)v10 + 26) )
  {
    NotificationTelemetry::ProcessingThrottled<unsigned short const * const &,unsigned int &,unsigned int &>(
      a2,
      (char *)v10 + 104,
      (char *)this + 376);
LABEL_17:
    v12 = 0;
    goto LABEL_76;
  }
  if ( NotificationQueueManager::NotificationProcessingShouldBeDeferred(
         (NotificationQueueManager *)((char *)this - 40),
         v10) )
  {
    goto LABEL_17;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v46 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  Instance = CoCreateInstance(
               &GUID_2d3468c1_36a7_43b6_ac24_d3f02fd9607a,
               0,
               1u,
               &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
               (LPVOID *)&v46);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v14 = 2558;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)Instance,
      (int)ppva);
    goto LABEL_73;
  }
  v15 = 0;
  v16 = 0;
  do
  {
    v17 = v15 + 1;
    if ( SLODWORD(a2[10 * v16 + 2]) < 0 )
      v17 = v15;
    v15 = v17;
    ++v16;
  }
  while ( v16 < a3 );
  if ( v17 )
  {
    string = 0;
    v18 = v42;
    WindowsDeleteString(0);
    string = 0;
    ApplicationUserModelId = TileNotificationManager::GetApplicationUserModelId(v18, &string);
    v8 = ApplicationUserModelId;
    if ( ApplicationUserModelId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0D,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)ApplicationUserModelId,
        (int)ppva);
LABEL_30:
      WindowsDeleteString(string);
      string = 0;
LABEL_73:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v42);
      goto LABEL_9;
    }
    v44 = 0;
    v20 = v42;
    WindowsDeleteString(0);
    v44 = 0;
    TileID = TileNotificationManager::GetTileID(v20, &v44);
    v8 = TileID;
    if ( TileID < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0F,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)TileID,
        (int)ppva);
LABEL_33:
      WindowsDeleteString(v44);
      v44 = 0;
      goto LABEL_30;
    }
    v45 = 0;
    v22 = v42;
    WindowsDeleteString(0);
    v45 = 0;
    PackageFullName = TileNotificationManager::GetPackageFullName(v22, &v45);
    v8 = PackageFullName;
    if ( PackageFullName < 0 )
    {
      v24 = 2577;
LABEL_36:
      v25 = (unsigned int)PackageFullName;
      goto LABEL_37;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !wcschr(StringRawBuffer, 0x21u) )
    {
      v8 = -2147418113;
      v25 = 2147549183LL;
      v24 = 2580;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)v25,
        (int)ppva);
LABEL_38:
      WindowsDeleteString(v45);
      v45 = 0;
      goto LABEL_33;
    }
    v50 = 0;
    PackageFullName = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v42 + 9) + 96LL))(
                        *((_QWORD *)v42 + 9),
                        &v50);
    v8 = PackageFullName;
    if ( PackageFullName < 0 )
    {
      v24 = 2584;
      goto LABEL_36;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= a3 )
      {
        WindowsDeleteString(v45);
        v45 = 0;
        WindowsDeleteString(v44);
        v44 = 0;
        WindowsDeleteString(string);
        goto LABEL_70;
      }
      v28 = (const WCHAR *)&a2[10 * i];
      v51 = v28;
      v29 = (const char *)*((unsigned int *)v28 + 4);
      if ( (int)v29 < 0 )
      {
        if ( (_DWORD)v29 != -2147023728 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA1F,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            v29,
            (int)ppva);
        continue;
      }
      LODWORD(v49) = -2147467259;
      v30 = *((_DWORD *)v28 + 3) & 0xF;
      v48 = 0;
      if ( v30 != 2 )
        break;
      v31 = *((_QWORD *)v52 + 46);
      v32 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, _QWORD))(*(_QWORD *)v31 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      ppva = (LPVOID *)&v48;
      v33 = v32(v31, v45, *((unsigned int *)v28 + 12), *((_QWORD *)v28 + 5));
LABEL_59:
      v34 = (unsigned int)v33;
      LODWORD(v49) = v33;
      if ( v33 < 0 )
      {
LABEL_66:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA3E,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)v34,
          (int)ppva);
        v51 = WindowsGetStringRawBuffer(v44, 0);
        v53 = WindowsGetStringRawBuffer(string, 0);
        NotificationTelemetry::TileRequestNotificationCompleted_Final::NotificationObjFactoryFailure<unsigned short const *,unsigned short const *,unsigned long &,_GUID &,long &>(
          (unsigned int)v54,
          (unsigned int)&v53,
          (unsigned int)&v51,
          (_DWORD)v28 + 8,
          (__int64)(v28 + 32),
          (__int64)&v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        continue;
      }
      SRWLock = 0;
      v49 = v48;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
      v38 = Microsoft::WRL::Details::MakeAndInitialize<NotificationDetailsWrapper,INotificationDetailsWrapper,__MIDL___MIDL_itf_wpnplatform_0000_0019_0003 * &,Windows::Internal::Notifications::INotificationValueSet *>(
              &SRWLock,
              &v51,
              &v49);
      v8 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA45,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)(unsigned int)v38,
          (int)ppva);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        goto LABEL_38;
      }
      v39 = ((__int64 (__fastcall *)(struct IObjectCollection *, PSRWLOCK))v46->lpVtbl->AddObject)(v46, SRWLock);
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA46,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)(unsigned int)v39,
          (int)ppva);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    }
    v34 = 2147500037LL;
    if ( v30 != 1 )
      goto LABEL_66;
    v35 = *((_QWORD *)v52 + 46);
    v36 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _QWORD))(*(_QWORD *)v35 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    if ( (_DWORD)v50 == 1 )
    {
      if ( HIDWORD(v50) == 1 )
      {
        v37 = (unsigned int)v50;
LABEL_58:
        LODWORD(ppva) = *((_QWORD *)v28 + 5);
        v33 = v36(v35, v45, v37, *((unsigned int *)v28 + 12));
        goto LABEL_59;
      }
    }
    else
    {
      v37 = 2;
      if ( (_DWORD)v50 == 2 )
      {
        if ( HIDWORD(v50) == 2 )
          goto LABEL_58;
      }
      else if ( v50 == 0x200000004LL )
      {
        v37 = 3;
        goto LABEL_58;
      }
    }
    v37 = 0;
    if ( v50 == 0x400000004LL )
      v37 = 4;
    goto LABEL_58;
  }
LABEL_70:
  Instance = TileNotificationManager::SetNotifications(v42, v46);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v14 = 2634;
    goto LABEL_72;
  }
  wil::ActivityBase<NotificationLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_78:
  Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v42);
  NotificationTelemetry::TileRequestNotificationCompleted_Final::~TileRequestNotificationCompleted_Final((NotificationTelemetry::TileRequestNotificationCompleted_Final *)v54);
  return 0;
}

```

## disassembly

```asm
0x180163920  mov     [rsp-8+arg_18], rbx
0x180163925  push    rbp
0x180163926  push    rsi
0x180163927  push    rdi
0x180163928  push    r12
0x18016392a  push    r13
0x18016392c  push    r14
0x18016392e  push    r15
0x180163930  lea     rbp, [rsp-100h]
0x180163938  sub     rsp, 200h
0x18016393f  mov     rax, cs:__security_cookie
0x180163946  xor     rax, rsp
0x180163949  mov     [rbp+130h+var_40], rax
0x180163950  mov     r15d, r8d
0x180163953  mov     r13, rdx
0x180163956  mov     rsi, rcx
0x180163959  mov     [rbp+130h+var_1A0], rcx
0x18016395d  xor     r14d, r14d
0x180163960  test    r8d, r8d
0x180163963  jz      short loc_18016396A
0x180163965  mov     rbx, [rdx]
0x180163968  jmp     short loc_18016396D
0x18016396a  mov     rbx, r14
0x18016396d  lea     rdx, aTilerequestnot_1; "TileRequestNotificationCompleted_Final"
0x180163974  lea     rcx, [rbp+130h+var_190]; struct wil::details::IFailureCallback *
0x180163978  call    ??0?$ActivityBase@VNotificationLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NotificationLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18016397d  lea     rax, ??_7TileRequestNotificationCompleted_Final@NotificationTelemetry@@6B@; const NotificationTelemetry::TileRequestNotificationCompleted_Final::`vftable'
0x180163984  mov     [rbp+130h+var_190], rax
0x180163988  mov     r8, rbx; unsigned __int16 *
0x18016398b  mov     edx, r15d; unsigned int
0x18016398e  lea     rcx, [rbp+130h+var_190]; this
0x180163992  call    ?StartActivity@TileRequestNotificationCompleted_Final@NotificationTelemetry@@QEAAXIPEBG@Z; NotificationTelemetry::TileRequestNotificationCompleted_Final::StartActivity(uint,ushort const *)
0x180163997  nop
0x180163998  call    cs:__imp_GetCurrentThreadId
0x18016399e  cmp     [rsi+20h], eax
0x1801639a1  jnz     short loc_1801639C2
0x1801639a3  mov     rcx, [rbp+138h]; this
0x1801639aa  mov     r9d, 800705A4h; char *
0x1801639b0  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801639b7  mov     edx, 9C7h; void *
0x1801639bc  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801639c2  cmp     r15d, 2
0x1801639c6  jnb     short loc_1801639F8
0x1801639c8  mov     edx, 9CCh; void *
0x1801639cd  mov     ebx, 8000FFFFh
0x1801639d2  mov     r9d, ebx; char *
0x1801639d5  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801639dc  mov     rcx, [rbp+138h]; this
0x1801639e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801639e8  lea     rcx, [rbp+130h+var_190]; this
0x1801639ec  call    ??1TileRequestNotificationCompleted_Final@NotificationTelemetry@@QEAA@XZ; NotificationTelemetry::TileRequestNotificationCompleted_Final::~TileRequestNotificationCompleted_Final(void)
0x1801639f1  mov     eax, ebx
0x1801639f3  jmp     loc_180163FB4
0x1801639f8  cmp     r15d, 6
0x1801639fc  jbe     short loc_180163A05
0x1801639fe  mov     edx, 9CDh
0x180163a03  jmp     short loc_1801639CD
0x180163a05  mov     [rsp+230h+var_1F0], r14
0x180163a0a  lea     rdx, [rsi+198h]
0x180163a11  lea     rcx, [rsp+230h+SRWLock]
0x180163a16  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180163a1b  lea     rbx, [rsi+178h]
0x180163a22  dec     dword ptr [rbx]
0x180163a24  lea     rcx, [rsp+230h+var_1F0]
0x180163a29  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180163a2e  lea     r8, [rsp+230h+var_1F0]; struct TileNotificationManager **
0x180163a33  mov     rdx, [r13+0]; unsigned __int16 *
0x180163a37  lea     rcx, [rsi-28h]; this
0x180163a3b  call    ?GetTileFromNotificationId@NotificationQueueManager@@AEAAJPEBGPEAPEAVTileNotificationManager@@@Z; NotificationQueueManager::GetTileFromNotificationId(ushort const *,TileNotificationManager * *)
0x180163a40  mov     rax, [rsp+230h+var_1F0]
0x180163a45  test    rax, rax
0x180163a48  jz      loc_180163F81
0x180163a4e  mov     byte ptr [rax+75h], 1
0x180163a52  mov     rdx, [rsp+230h+var_1F0]
0x180163a57  mov     eax, [rdx+68h]
0x180163a5a  test    eax, eax
0x180163a5c  jz      short loc_180163A68
0x180163a5e  dec     eax
0x180163a60  mov     [rdx+68h], eax
0x180163a63  mov     rdx, [rsp+230h+var_1F0]; struct TileNotificationManager *
0x180163a68  cmp     [rdx+68h], r14d
0x180163a6c  jz      short loc_180163A84
0x180163a6e  mov     r8, rbx
0x180163a71  add     rdx, 68h ; 'h'
0x180163a75  mov     rcx, r13
0x180163a78  call    ??$ProcessingThrottled@AEBQEBGAEAIAEAI@NotificationTelemetry@@SAXAEBQEBGAEAI1@Z; NotificationTelemetry::ProcessingThrottled<ushort const * const &,uint &,uint &>(ushort const * const &,uint &,uint &)
0x180163a7d  xor     edx, edx
0x180163a7f  jmp     loc_180163F86
0x180163a84  lea     rcx, [rsi-28h]; this
0x180163a88  call    ?NotificationProcessingShouldBeDeferred@NotificationQueueManager@@AEAA_NPEAVTileNotificationManager@@@Z; NotificationQueueManager::NotificationProcessingShouldBeDeferred(TileNotificationManager *)
0x180163a8d  test    al, al
0x180163a8f  jnz     short loc_180163A7D
0x180163a91  mov     rcx, [rsp+230h+SRWLock]; SRWLock
0x180163a96  test    rcx, rcx
0x180163a99  jz      short loc_180163AA1
0x180163a9b  call    cs:__imp_ReleaseSRWLockExclusive
0x180163aa1  mov     [rsp+230h+var_1D0], r14
0x180163aa6  lea     rcx, [rsp+230h+var_1D0]
0x180163aab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180163ab0  lea     rax, [rsp+230h+var_1D0]
0x180163ab5  mov     [rsp+230h+ppv], rax; int
0x180163aba  lea     r9, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; riid
0x180163ac1  xor     edx, edx; pUnkOuter
0x180163ac3  lea     r8d, [rdx+1]; dwClsContext
0x180163ac7  lea     rcx, _GUID_2d3468c1_36a7_43b6_ac24_d3f02fd9607a; rclsid
0x180163ace  call    cs:__imp_CoCreateInstance
0x180163ad4  mov     ebx, eax
0x180163ad6  test    eax, eax
0x180163ad8  jns     short loc_180163AEB
0x180163ada  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180163ae1  mov     edx, 9FEh
0x180163ae6  jmp     loc_180163F42
0x180163aeb  mov     edx, r14d
0x180163aee  mov     r8d, r14d
0x180163af1  mov     eax, r8d
0x180163af4  lea     rcx, [rax+rax*4]
0x180163af8  add     rcx, rcx
0x180163afb  lea     eax, [rdx+1]
0x180163afe  cmp     [r13+rcx*8+10h], r14d
0x180163b03  cmovl   eax, edx
0x180163b06  mov     edx, eax
0x180163b08  inc     r8d
0x180163b0b  cmp     r8d, r15d
0x180163b0e  jb      short loc_180163AF1
0x180163b10  lea     rsi, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180163b17  test    eax, eax
0x180163b19  jz      loc_180163F25
0x180163b1f  mov     [rsp+230h+string], r14
0x180163b24  mov     rbx, [rsp+230h+var_1F0]
0x180163b29  xor     ecx, ecx; string
0x180163b2b  call    cs:__imp_WindowsDeleteString
0x180163b31  mov     [rsp+230h+string], r14
0x180163b36  lea     rdx, [rsp+230h+string]; HSTRING *
0x180163b3b  mov     rcx, rbx; this
0x180163b3e  call    ?GetApplicationUserModelId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetApplicationUserModelId(HSTRING__ * *)
0x180163b43  mov     ebx, eax
0x180163b45  test    eax, eax
0x180163b47  jns     short loc_180163B75
0x180163b49  mov     rcx, [rbp+138h]; this
0x180163b50  mov     r9d, eax; char *
0x180163b53  mov     r8, rsi; unsigned int
0x180163b56  mov     edx, 0A0Dh; void *
0x180163b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163b60  mov     rcx, [rsp+230h+string]; string
0x180163b65  call    cs:__imp_WindowsDeleteString
0x180163b6b  mov     [rsp+230h+string], r14
0x180163b70  jmp     loc_180163F51
0x180163b75  mov     [rsp+230h+var_1E0], r14
0x180163b7a  mov     rbx, [rsp+230h+var_1F0]
0x180163b7f  xor     ecx, ecx; string
0x180163b81  call    cs:__imp_WindowsDeleteString
0x180163b87  mov     [rsp+230h+var_1E0], r14
0x180163b8c  lea     rdx, [rsp+230h+var_1E0]; HSTRING *
0x180163b91  mov     rcx, rbx; this
0x180163b94  call    ?GetTileID@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetTileID(HSTRING__ * *)
0x180163b99  mov     ebx, eax
0x180163b9b  test    eax, eax
0x180163b9d  jns     short loc_180163BC8
0x180163b9f  mov     rcx, [rbp+138h]; this
0x180163ba6  mov     r9d, eax; char *
0x180163ba9  mov     r8, rsi; unsigned int
0x180163bac  mov     edx, 0A0Fh; void *
0x180163bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163bb6  mov     rcx, [rsp+230h+var_1E0]; string
0x180163bbb  call    cs:__imp_WindowsDeleteString
0x180163bc1  mov     [rsp+230h+var_1E0], r14
0x180163bc6  jmp     short loc_180163B60
0x180163bc8  mov     [rsp+230h+var_1D8], r14
0x180163bcd  mov     rbx, [rsp+230h+var_1F0]
0x180163bd2  xor     ecx, ecx; string
0x180163bd4  call    cs:__imp_WindowsDeleteString
0x180163bda  mov     [rsp+230h+var_1D8], r14
0x180163bdf  lea     rdx, [rsp+230h+var_1D8]; HSTRING *
0x180163be4  mov     rcx, rbx; this
0x180163be7  call    ?GetPackageFullName@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetPackageFullName(HSTRING__ * *)
0x180163bec  mov     ebx, eax
0x180163bee  test    eax, eax
0x180163bf0  jns     short loc_180163C1B
0x180163bf2  mov     edx, 0A11h; void *
0x180163bf7  mov     r9d, eax; char *
0x180163bfa  mov     rcx, [rbp+138h]; this
0x180163c01  mov     r8, rsi; unsigned int
0x180163c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163c09  mov     rcx, [rsp+230h+var_1D8]; string
0x180163c0e  call    cs:__imp_WindowsDeleteString
0x180163c14  mov     [rsp+230h+var_1D8], r14
0x180163c19  jmp     short loc_180163BB6
0x180163c1b  xor     edx, edx; length
0x180163c1d  mov     rcx, [rsp+230h+string]; string
0x180163c22  call    cs:__imp_WindowsGetStringRawBuffer
0x180163c28  mov     edx, 21h ; '!'; Ch
0x180163c2d  mov     rcx, rax; Str
0x180163c30  call    cs:__imp_wcschr
0x180163c36  test    rax, rax
0x180163c39  jnz     short loc_180163C4A
0x180163c3b  mov     ebx, 8000FFFFh
0x180163c40  mov     r9d, ebx
0x180163c43  mov     edx, 0A14h
0x180163c48  jmp     short loc_180163BFA
0x180163c4a  mov     [rbp+130h+var_1B0], r14
0x180163c4e  mov     rax, [rsp+230h+var_1F0]
0x180163c53  mov     rcx, [rax+48h]
0x180163c57  mov     rax, [rcx]
0x180163c5a  lea     rdx, [rbp+130h+var_1B0]
0x180163c5e  mov     rax, [rax+60h]
0x180163c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163c67  mov     ebx, eax
0x180163c69  test    eax, eax
0x180163c6b  jns     short loc_180163C74
0x180163c6d  mov     edx, 0A18h
0x180163c72  jmp     short loc_180163BF7
0x180163c74  mov     r12d, r14d
0x180163c77  cmp     r12d, r15d
0x180163c7a  jnb     loc_180163EFA
0x180163c80  mov     eax, r12d
0x180163c83  lea     r14, [rax+rax*4]
0x180163c87  shl     r14, 4
0x180163c8b  add     r14, r13
0x180163c8e  mov     [rbp+130h+var_1A8], r14
0x180163c92  mov     r9d, [r14+10h]; char *
0x180163c96  test    r9d, r9d
0x180163c99  jns     short loc_180163CC1
0x180163c9b  cmp     r9d, 80070490h
0x180163ca2  jz      loc_180163EBF
0x180163ca8  mov     rcx, [rbp+138h]; this
0x180163caf  mov     r8, rsi; unsigned int
0x180163cb2  mov     edx, 0A1Fh; void *
0x180163cb7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180163cbc  jmp     loc_180163EBF
0x180163cc1  mov     dword ptr [rsp+230h+var_1B8], 80004005h
0x180163cc9  mov     eax, [r14+0Ch]
0x180163ccd  and     eax, 0Fh
0x180163cd0  mov     [rsp+230h+var_1C0], 0
0x180163cd9  cmp     eax, 2
0x180163cdc  jnz     short loc_180163D21
0x180163cde  mov     rax, [rbp+130h+var_1A0]
0x180163ce2  mov     rdi, [rax+170h]
0x180163ce9  mov     rax, [rdi]
0x180163cec  mov     rbx, [rax+38h]
0x180163cf0  lea     rcx, [rsp+230h+var_1C0]
0x180163cf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180163cfa  lea     rax, [rsp+230h+var_1C0]
0x180163cff  mov     [rsp+230h+ppv], rax
0x180163d04  mov     r9, [r14+28h]
0x180163d08  mov     r8d, [r14+30h]
0x180163d0c  mov     rdx, [rsp+230h+var_1D8]
0x180163d11  mov     rcx, rdi
0x180163d14  mov     rax, rbx
0x180163d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163d1c  jmp     loc_180163DAA
0x180163d21  mov     r9d, 80004005h; char *
0x180163d27  cmp     eax, 1
0x180163d2a  jnz     loc_180163E57
0x180163d30  mov     rax, [rbp+130h+var_1A0]
0x180163d34  mov     rbx, [rax+170h]
0x180163d3b  mov     rax, [rbx]
0x180163d3e  mov     rdi, [rax+30h]
0x180163d42  lea     rcx, [rsp+230h+var_1C0]
0x180163d47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180163d4c  mov     rdx, [r14+28h]
0x180163d50  mov     ecx, dword ptr [rbp+130h+var_1B0+4]
0x180163d53  mov     rax, [rbp+130h+var_1B0]
0x180163d57  cmp     eax, 1
0x180163d5a  jnz     short loc_180163D65
0x180163d5c  cmp     ecx, eax
0x180163d5e  jnz     short loc_180163D79
0x180163d60  mov     r8d, eax
0x180163d63  jmp     short loc_180163D87
0x180163d65  mov     r8d, 2
0x180163d6b  cmp     eax, r8d
0x180163d6e  jnz     loc_180163E3C
0x180163d74  cmp     ecx, r8d
0x180163d77  jz      short loc_180163D87
0x180163d79  xor     r8d, r8d
0x180163d7c  cmp     eax, 4
0x180163d7f  jnz     short loc_180163D87
0x180163d81  cmp     ecx, eax
0x180163d83  cmovz   r8d, eax
0x180163d87  lea     rax, [rsp+230h+var_1C0]
0x180163d8c  mov     [rsp+230h+var_208], rax
0x180163d91  mov     [rsp+230h+ppv], rdx; int
0x180163d96  mov     r9d, [r14+30h]
0x180163d9a  mov     rdx, [rsp+230h+var_1D8]
0x180163d9f  mov     rcx, rbx
0x180163da2  mov     rax, rdi
0x180163da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163daa  mov     r9d, eax
0x180163dad  mov     dword ptr [rsp+230h+var_1B8], eax
0x180163db1  test    eax, eax
0x180163db3  js      loc_180163E57
0x180163db9  xor     r14d, r14d
0x180163dbc  mov     [rsp+230h+SRWLock], r14
0x180163dc1  mov     rax, [rsp+230h+var_1C0]
0x180163dc6  mov     [rsp+230h+var_1B8], rax
0x180163dcb  lea     rcx, [rsp+230h+SRWLock]
0x180163dd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180163dd5  lea     r8, [rsp+230h+var_1B8]
0x180163dda  lea     rdx, [rbp+130h+var_1A8]
0x180163dde  lea     rcx, [rsp+230h+SRWLock]
0x180163de3  call    ??$MakeAndInitialize@VNotificationDetailsWrapper@@UINotificationDetailsWrapper@@AEAPEAU__MIDL___MIDL_itf_wpnplatform_0000_0019_0003@@PEAUINotificationValueSet@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAUINotificationDetailsWrapper@@AEAPEAU__MIDL___MIDL_itf_wpnplatform_0000_0019_0003@@$$QEAPEAUINotificationValueSet@Notifications@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NotificationDetailsWrapper,INotificationDetailsWrapper,__MIDL___MIDL_itf_wpnplatform_0000_0019_0003 * &,Windows::Internal::Notifications::INotificationValueSet *>(INotificationDetailsWrapper * *,__MIDL___MIDL_itf_wpnplatform_0000_0019_0003 * &,Windows::Internal::Notifications::INotificationValueSet * &&)
  ... truncated ...
```
