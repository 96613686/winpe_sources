# TileNotificationManager::SetNotifications(IObjectCollection *)

- ea: `0x1801f5ce0`
- end: `0x1801f6584`
- name: `?SetNotifications@TileNotificationManager@@UEAAJPEAUIObjectCollection@@@Z`
- size: `2212`
- prototype: `__int64 __fastcall(TileNotificationManager *__hidden this, struct IObjectCollection *)`
- caller_count: `4`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180163920`
- `0x180165ac0`
- `0x180282778`
- `0x18028a320`

## callees

- `0x18000b5f0`
- `0x18000ce94`
- `0x18001aca4`
- `0x18008d550`
- `0x1800c5b3c`
- `0x18010c45c`
- `0x180161204`
- `0x1801cd234`
- `0x1801d8f44`
- `0x1801ed034`
- `0x1801f5ce0`
- `0x1801f658c`
- `0x180201e50`
- `0x180280c38`
- `0x180280d7c`
- `0x180283060`
- `0x180283590`
- `0x180285a5c`
- `0x1802896b0`
- `0x180289790`
- `0x18028994c`
- `0x180289e3c`
- `0x18028b8a0`
- `0x18028bed8`
- `0x18028bf18`
- `0x18028fc00`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801f5e0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801f5e0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801f612b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801f612b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f64a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f64b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f64a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f64b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f62a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f62a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6366`

## string_xrefs

- `0x1801f5d7b`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f5dc8`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f5e4b`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f5f49`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f5f6f`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f6018`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f63d8`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`
- `0x1801f6476`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotificationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall TileNotificationManager::SetNotifications(RTL_SRWLOCK *this, struct IObjectCollection *a2)
{
  int (__fastcall ***Ptr)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // edi
  bool v14; // si
  HRESULT (__stdcall *GetAt)(IObjectCollection *, UINT, const IID *const, void **); // rbx
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdx
  unsigned int v20; // r12d
  int v21; // eax
  int v22; // eax
  int v23; // eax
  RTL_SRWLOCK *v24; // r15
  __int64 *v25; // rbx
  __int64 v26; // r8
  RTL_SRWLOCK *v27; // rdi
  _DWORD *v28; // rdi
  __int64 **v29; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  PVOID v32; // rbx
  RTL_SRWLOCK *v33; // rcx
  PVOID v34; // rcx
  PVOID v35; // rdx
  PVOID v36; // r12
  __int64 v37; // rsi
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v39; // rbx
  int *v40; // rbx
  int *v41; // rdi
  int Manager; // eax
  unsigned int v43; // ebx
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // [rsp+20h] [rbp-238h]
  int v47; // [rsp+20h] [rbp-238h]
  int v48; // [rsp+30h] [rbp-228h] BYREF
  int v49; // [rsp+34h] [rbp-224h] BYREF
  HSTRING v50; // [rsp+38h] [rbp-220h] BYREF
  HSTRING string; // [rsp+40h] [rbp-218h] BYREF
  struct IRefreshTileNotifications *v52; // [rsp+48h] [rbp-210h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-208h] BYREF
  __int64 v54; // [rsp+58h] [rbp-200h] BYREF
  RTL_SRWLOCK *v55; // [rsp+60h] [rbp-1F8h] BYREF
  RTL_SRWLOCK *v56; // [rsp+68h] [rbp-1F0h] BYREF
  void *v57; // [rsp+70h] [rbp-1E8h]
  void *v58; // [rsp+78h] [rbp-1E0h] BYREF
  int *v59; // [rsp+80h] [rbp-1D8h] BYREF
  int *v60; // [rsp+88h] [rbp-1D0h]
  int *v61; // [rsp+90h] [rbp-1C8h]
  PCWSTR v62; // [rsp+98h] [rbp-1C0h] BYREF
  char v63[16]; // [rsp+A0h] [rbp-1B8h] BYREF
  char v64[16]; // [rsp+B0h] [rbp-1A8h] BYREF
  __int128 v65; // [rsp+C0h] [rbp-198h] BYREF
  _QWORD v66[42]; // [rsp+D0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v54 = 0;
  Ptr = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))this[18].Ptr;
  v5 = **Ptr;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  if ( v5(Ptr, &GUID_147ee093_216f_4968_b900_df824ebc791c, &v54) >= 0 )
  {
    SRWLock = 0;
    v6 = (*(__int64 (__fastcall **)(PVOID, PSRWLOCK *))(*(_QWORD *)this[9].Ptr + 96LL))(this[9].Ptr, &SRWLock);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x117,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)v6,
        v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      return v7;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, PSRWLOCK, struct IObjectCollection *))(*(_QWORD *)v54 + 64LL))(
           v54,
           SRWLock,
           a2);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)v9,
        v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      return v10;
    }
  }
  std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(&v59);
  std::map<unsigned long,Microsoft::WRL::ComPtr<TileNotification>>::map<unsigned long,Microsoft::WRL::ComPtr<TileNotification>>(&v56);
  AcquireSRWLockExclusive(this + 29);
  *(_QWORD *)&v65 = this + 29;
  LODWORD(string) = 0;
  if ( a2 )
  {
    v11 = ((__int64 (__fastcall *)(struct IObjectCollection *, HSTRING *))a2->lpVtbl->GetCount)(a2, &string);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)v11,
        v46);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v65);
      std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>(&v56);
      std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionOfficeSKU>::_Tidy(&v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      return v12;
    }
  }
  v13 = 0;
  v14 = 1;
  while ( v13 < (unsigned int)string )
  {
    v52 = 0;
    GetAt = a2->lpVtbl->GetAt;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    v16 = ((__int64 (__fastcall *)(struct IObjectCollection *, _QWORD, GUID *, struct IRefreshTileNotifications **))GetAt)(
            a2,
            v13,
            &GUID_7dfd5457_d5c5_484d_87ba_fc91ff338de6,
            &v52);
    v17 = retaddr;
    if ( v16 < 0 )
    {
      v18 = (unsigned int)v16;
      v19 = 299;
LABEL_21:
      wil::details::in1diag3::_Log_Hr(
        v17,
        (void *)v19,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)v18,
        v46);
      goto LABEL_30;
    }
    v20 = (*(__int64 (__fastcall **)(struct IRefreshTileNotifications *))(*(_QWORD *)v52 + 40LL))(v52);
    LODWORD(v50) = v20;
    v48 = 0;
    v21 = (*(__int64 (__fastcall **)(struct IRefreshTileNotifications *))(*(_QWORD *)v52 + 56LL))(v52) & 0xF;
    if ( v21 == 1 )
    {
      v22 = 0;
LABEL_17:
      v48 = v22;
      v18 = 0;
      goto LABEL_19;
    }
    if ( v21 == 2 )
    {
      v22 = 1;
      goto LABEL_17;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
      (const char *)0x80070057LL,
      v46);
    v18 = 2147942487LL;
LABEL_19:
    v17 = retaddr;
    if ( (int)v18 < 0 )
    {
      v19 = 303;
      goto LABEL_21;
    }
    SRWLock = 0;
    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(
      &this[26],
      &v62,
      &v50);
    if ( v62 == this[26].Ptr )
    {
      LOBYTE(v49) = TileNotificationManager::HasNotificationBeenPreviouslyPresented(
                      (TileNotificationManager *)this,
                      v20);
      v58 = v52;
      v55 = this;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
      v23 = Microsoft::WRL::Details::MakeAndInitialize<TileNotification,TileNotification,unsigned __int64 &,TileNotificationManager *,INotificationDetailsWrapper *,bool,enum _SharedModelTileNotificationType &>(
              (unsigned int)&SRWLock,
              (int)this + 136,
              (unsigned int)&v55,
              (unsigned int)&v58,
              (__int64)&v49,
              (__int64)&v48);
      if ( v23 >= 0 )
      {
        std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::emplace<unsigned long &,Microsoft::WRL::ComPtr<TileNotification> &>(
          &v56,
          v63,
          &v50,
          &SRWLock);
        v48 = (int)v50;
        if ( v60 == v61 )
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v59, v60, &v48);
        else
          *v60++ = (int)v50;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x13C,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
          (const char *)(unsigned int)v23,
          v46);
      }
    }
    else
    {
      std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::emplace<unsigned long &,Microsoft::WRL::ComPtr<TileNotification> &>(
        &v56,
        v64,
        &v50,
        v62 + 20);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    ++v13;
  }
  v24 = this + 26;
  v25 = *(__int64 **)this[26].Ptr;
  while ( !*((_BYTE *)v25 + 25) )
  {
    v58 = 0;
    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(
      &v56,
      &v55,
      v25 + 4);
    v27 = v55;
    if ( v55 != v56 && !TileNotification::IsValid(*(TileNotification **)(v26 + 8)) )
    {
      v28 = v27[5].Ptr;
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v28 + 56);
      v28[42] = 4;
      if ( SRWLock )
      {
        ReleaseSRWLockExclusive(SRWLock);
        SRWLock = 0;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    v29 = (__int64 **)v25[2];
    if ( *((_BYTE *)v29 + 25) )
    {
      for ( i = (__int64 *)v25[1]; !*((_BYTE *)i + 25) && v25 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v25 = i;
      v25 = i;
    }
    else
    {
      v25 = (__int64 *)v25[2];
      for ( j = *v29; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v25 = j;
    }
  }
  v32 = this[27].Ptr;
  std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::clear(&this[26]);
  if ( v24 != (RTL_SRWLOCK *)&v56 )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::clear(&this[26]);
    v33 = (RTL_SRWLOCK *)v24->Ptr;
    v24->Ptr = v56;
    v56 = v33;
    v34 = this[27].Ptr;
    this[27].Ptr = v57;
    v57 = v34;
  }
  v55 = 0;
  if ( !(v60 - v59) )
  {
    v35 = this[27].Ptr;
    if ( !HIDWORD(this[13].Ptr) || v35 )
      v14 = v32 != v35;
  }
  v36 = this[27].Ptr;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v65);
  if ( v14 )
  {
    v50 = 0;
    string = 0;
    WindowsDeleteString(0);
    v50 = 0;
    TileNotificationManager::GetApplicationUserModelId((TileNotificationManager *)this, &v50);
    WindowsDeleteString(string);
    string = 0;
    TileNotificationManager::GetTileID((TileNotificationManager *)this, &string);
    v37 = v60 - v59;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v39 = WindowsGetStringRawBuffer(v50, 0);
    wil::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v66);
    v66[0] = &NotificationTelemetry::NotificationsArrived::`vftable';
    NotificationTelemetry::NotificationsArrived::StartActivity(
      (NotificationTelemetry::NotificationsArrived *)v66,
      v39,
      StringRawBuffer,
      v37,
      (unsigned int)v36);
    v40 = v59;
    v41 = v60;
    while ( v40 != v41 )
    {
      v48 = *v40;
      std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(
        &this[26],
        &v55,
        &v48);
      if ( v55 != v24->Ptr )
      {
        v65 = 0;
        (*(void (__fastcall **)(__int64, __int128 *))(*((_QWORD *)v55[5].Ptr + 8) + 64LL))(
          (__int64)v55[5].Ptr + 64,
          &v65);
        v58 = (void *)WindowsGetStringRawBuffer(string, 0);
        v62 = WindowsGetStringRawBuffer(v50, 0);
        NotificationTelemetry::NotificationsArrived::NotificationArrival<unsigned short const *,unsigned short const *,unsigned int const &,_GUID &>(
          (unsigned int)v66,
          (unsigned int)&v62,
          (unsigned int)&v58,
          (_DWORD)v40,
          (__int64)&v65);
      }
      ++v40;
    }
    v52 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Manager = TileNotificationManager::GetManager((TileNotificationManager *)this, &v52);
    v43 = Manager;
    if ( Manager < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x190,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)Manager,
        v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      NotificationTelemetry::NotificationsArrived::~NotificationsArrived((NotificationTelemetry::NotificationsArrived *)v66);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v50);
      v50 = 0;
      std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>(&v56);
      std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionOfficeSKU>::_Tidy(&v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      return v43;
    }
    v44 = (*(__int64 (__fastcall **)(struct IRefreshTileNotifications *, PVOID))(*(_QWORD *)v52 + 32LL))(
            v52,
            this[18].Ptr);
    v45 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x191,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotificationmanager.cpp",
        (const char *)(unsigned int)v44,
        v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      NotificationTelemetry::NotificationsArrived::~NotificationsArrived((NotificationTelemetry::NotificationsArrived *)v66);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v50);
      v50 = 0;
      std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>(&v56);
      std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionOfficeSKU>::_Tidy(&v59);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      return v45;
    }
    wil::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    NotificationTelemetry::NotificationsArrived::~NotificationsArrived((NotificationTelemetry::NotificationsArrived *)v66);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v50);
  }
  std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<TileNotification>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>(&v56);
  std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionOfficeSKU>::_Tidy(&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  return 0;
}

```

## disassembly

```asm
0x1801f5ce0  mov     [rsp+arg_10], rbx
0x1801f5ce5  mov     [rsp+arg_18], rsi
0x1801f5cea  push    rdi
0x1801f5ceb  push    r12
0x1801f5ced  push    r13
0x1801f5cef  push    r14
0x1801f5cf1  push    r15
0x1801f5cf3  sub     rsp, 230h
0x1801f5cfa  mov     rax, cs:__security_cookie
0x1801f5d01  xor     rax, rsp
0x1801f5d04  mov     [rsp+258h+var_38], rax
0x1801f5d0c  mov     r15, rdx
0x1801f5d0f  mov     r14, rcx
0x1801f5d12  xor     r13d, r13d
0x1801f5d15  mov     [rsp+258h+var_200], r13
0x1801f5d1a  mov     rdi, [rcx+90h]
0x1801f5d21  mov     rax, [rdi]
0x1801f5d24  mov     rbx, [rax]
0x1801f5d27  lea     rcx, [rsp+258h+var_200]
0x1801f5d2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f5d31  lea     r8, [rsp+258h+var_200]
0x1801f5d36  lea     rdx, _GUID_147ee093_216f_4968_b900_df824ebc791c
0x1801f5d3d  mov     rcx, rdi
0x1801f5d40  mov     rax, rbx
0x1801f5d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5d48  test    eax, eax
0x1801f5d4a  js      loc_1801F5DEB
0x1801f5d50  mov     [rsp+258h+SRWLock], r13
0x1801f5d55  mov     rcx, [r14+48h]
0x1801f5d59  mov     rax, [rcx]
0x1801f5d5c  lea     rdx, [rsp+258h+SRWLock]
0x1801f5d61  mov     rax, [rax+60h]
0x1801f5d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5d6a  mov     ebx, eax
0x1801f5d6c  test    eax, eax
0x1801f5d6e  jns     short loc_1801F5D9E
0x1801f5d70  mov     rcx, [rsp+258h]; this
0x1801f5d78  mov     r9d, eax; char *
0x1801f5d7b  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801f5d82  mov     edx, 117h; void *
0x1801f5d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5d8c  nop
0x1801f5d8d  lea     rcx, [rsp+258h+var_200]
0x1801f5d92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f5d97  mov     eax, ebx
0x1801f5d99  jmp     loc_1801F6556
0x1801f5d9e  mov     rcx, [rsp+258h+var_200]
0x1801f5da3  mov     rax, [rcx]
0x1801f5da6  mov     r8, r15
0x1801f5da9  mov     rdx, [rsp+258h+SRWLock]
0x1801f5dae  mov     rax, [rax+40h]
0x1801f5db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5db7  mov     ebx, eax
0x1801f5db9  test    eax, eax
0x1801f5dbb  jns     short loc_1801F5DEB
0x1801f5dbd  mov     rcx, [rsp+258h]; this
0x1801f5dc5  mov     r9d, eax; char *
0x1801f5dc8  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801f5dcf  mov     edx, 118h; void *
0x1801f5dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5dd9  nop
0x1801f5dda  lea     rcx, [rsp+258h+var_200]
0x1801f5ddf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f5de4  mov     eax, ebx
0x1801f5de6  jmp     loc_1801F6556
0x1801f5deb  lea     rcx, [rsp+258h+var_1D8]
0x1801f5df3  call    ??0?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x1801f5df8  nop
0x1801f5df9  lea     rcx, [rsp+258h+var_1F0]
0x1801f5dfe  call    ??0?$map@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@@std@@QEAA@XZ; std::map<ulong,Microsoft::WRL::ComPtr<TileNotification>>::map<ulong,Microsoft::WRL::ComPtr<TileNotification>>(void)
0x1801f5e03  nop
0x1801f5e04  lea     rbx, [r14+0E8h]
0x1801f5e0b  mov     rcx, rbx; SRWLock
0x1801f5e0e  call    cs:__imp_AcquireSRWLockExclusive
0x1801f5e14  mov     qword ptr [rsp+258h+var_198], rbx
0x1801f5e1c  mov     dword ptr [rsp+258h+string], r13d
0x1801f5e21  test    r15, r15
0x1801f5e24  jz      short loc_1801F5E95
0x1801f5e26  mov     rax, [r15]
0x1801f5e29  lea     rdx, [rsp+258h+string]
0x1801f5e2e  mov     rcx, r15
0x1801f5e31  mov     rax, [rax+18h]
0x1801f5e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5e3a  mov     ebx, eax
0x1801f5e3c  test    eax, eax
0x1801f5e3e  jns     short loc_1801F5E95
0x1801f5e40  mov     rcx, [rsp+258h]; this
0x1801f5e48  mov     r9d, eax; char *
0x1801f5e4b  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801f5e52  mov     edx, 126h; void *
0x1801f5e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5e5c  nop
0x1801f5e5d  lea     rcx, [rsp+258h+var_198]
0x1801f5e65  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1801f5e6a  nop
0x1801f5e6b  lea     rcx, [rsp+258h+var_1F0]
0x1801f5e70  call    ??1?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::~_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>(void)
0x1801f5e75  nop
0x1801f5e76  lea     rcx, [rsp+258h+var_1D8]
0x1801f5e7e  call    ?_Tidy@?$vector@W4CollectionOfficeSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@V?$allocator@W4CollectionOfficeSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@AEAAXXZ; std::vector<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionOfficeSKU>::_Tidy(void)
0x1801f5e83  nop
0x1801f5e84  lea     rcx, [rsp+258h+var_200]
0x1801f5e89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f5e8e  mov     eax, ebx
0x1801f5e90  jmp     loc_1801F6556
0x1801f5e95  mov     edi, r13d
0x1801f5e98  mov     esi, 1
0x1801f5e9d  cmp     edi, dword ptr [rsp+258h+string]
0x1801f5ea1  jnb     loc_1801F60BA
0x1801f5ea7  mov     [rsp+258h+var_210], r13
0x1801f5eac  mov     rax, [r15]
0x1801f5eaf  mov     rbx, [rax+20h]
0x1801f5eb3  lea     rcx, [rsp+258h+var_210]
0x1801f5eb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f5ebd  lea     r9, [rsp+258h+var_210]
0x1801f5ec2  lea     r8, _GUID_7dfd5457_d5c5_484d_87ba_fc91ff338de6
0x1801f5ec9  mov     edx, edi
0x1801f5ecb  mov     rcx, r15
0x1801f5ece  mov     rax, rbx
0x1801f5ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5ed6  mov     rcx, [rsp+258h]
0x1801f5ede  test    eax, eax
0x1801f5ee0  jns     short loc_1801F5EEF
0x1801f5ee2  mov     r9d, eax
0x1801f5ee5  mov     edx, 12Bh
0x1801f5eea  jmp     loc_1801F5F6F
0x1801f5eef  mov     rcx, [rsp+258h+var_210]
0x1801f5ef4  mov     rax, [rcx]
0x1801f5ef7  mov     rax, [rax+28h]
0x1801f5efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5f00  mov     r12d, eax
0x1801f5f03  mov     dword ptr [rsp+258h+var_220], eax
0x1801f5f07  mov     [rsp+258h+var_228], r13d
0x1801f5f0c  mov     rcx, [rsp+258h+var_210]
0x1801f5f11  mov     rax, [rcx]
0x1801f5f14  mov     rax, [rax+38h]
0x1801f5f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5f1d  and     eax, 0Fh
0x1801f5f20  cmp     eax, esi
0x1801f5f22  jnz     short loc_1801F5F29
0x1801f5f24  mov     eax, r13d
0x1801f5f27  jmp     short loc_1801F5F30
0x1801f5f29  cmp     eax, 2
0x1801f5f2c  jnz     short loc_1801F5F39
0x1801f5f2e  mov     eax, esi
0x1801f5f30  mov     [rsp+258h+var_228], eax
0x1801f5f34  mov     r9d, r13d
0x1801f5f37  jmp     short loc_1801F5F5D
0x1801f5f39  mov     rcx, [rsp+258h]; this
0x1801f5f41  mov     ebx, 80070057h
0x1801f5f46  mov     r9d, ebx; char *
0x1801f5f49  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801f5f50  mov     edx, 1B4h; void *
0x1801f5f55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f5f5a  mov     r9d, ebx; char *
0x1801f5f5d  mov     rcx, [rsp+258h]; this
0x1801f5f65  test    r9d, r9d
0x1801f5f68  jns     short loc_1801F5F80
0x1801f5f6a  mov     edx, 12Fh; void *
0x1801f5f6f  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801f5f76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801f5f7b  jmp     loc_1801F60A9
0x1801f5f80  mov     [rsp+258h+SRWLock], r13
0x1801f5f85  lea     rbx, [r14+0D0h]
0x1801f5f8c  lea     r8, [rsp+258h+var_220]
0x1801f5f91  lea     rdx, [rsp+258h+var_1C0]
0x1801f5f99  mov     rcx, rbx
0x1801f5f9c  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(ulong const &)
0x1801f5fa1  mov     r9, [rsp+258h+var_1C0]
0x1801f5fa9  cmp     r9, [rbx]
0x1801f5fac  jnz     loc_1801F6082
0x1801f5fb2  mov     edx, r12d; unsigned int
0x1801f5fb5  mov     rcx, r14; this
0x1801f5fb8  call    ?HasNotificationBeenPreviouslyPresented@TileNotificationManager@@AEAA_NI@Z; TileNotificationManager::HasNotificationBeenPreviouslyPresented(uint)
0x1801f5fbd  mov     byte ptr [rsp+258h+var_224], al
0x1801f5fc1  mov     rax, [rsp+258h+var_210]
0x1801f5fc6  mov     [rsp+258h+var_1E0], rax
0x1801f5fcb  mov     [rsp+258h+var_1F8], r14
0x1801f5fd0  lea     rcx, [rsp+258h+SRWLock]
0x1801f5fd5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f5fda  lea     rdx, [r14+88h]
0x1801f5fe1  lea     rax, [rsp+258h+var_228]
0x1801f5fe6  mov     [rsp+258h+var_230], rax
0x1801f5feb  lea     rax, [rsp+258h+var_224]
0x1801f5ff0  mov     qword ptr [rsp+258h+var_238], rax; int
0x1801f5ff5  lea     r9, [rsp+258h+var_1E0]
0x1801f5ffa  lea     r8, [rsp+258h+var_1F8]
0x1801f5fff  lea     rcx, [rsp+258h+SRWLock]
0x1801f6004  call    ??$MakeAndInitialize@VTileNotification@@V1@AEA_KPEAVTileNotificationManager@@PEAUINotificationDetailsWrapper@@_NAEAW4_SharedModelTileNotificationType@@@Details@WRL@Microsoft@@YAJPEAPEAVTileNotification@@AEA_K$$QEAPEAVTileNotificationManager@@$$QEAPEAUINotificationDetailsWrapper@@$$QEA_NAEAW4_SharedModelTileNotificationType@@@Z; Microsoft::WRL::Details::MakeAndInitialize<TileNotification,TileNotification,unsigned __int64 &,TileNotificationManager *,INotificationDetailsWrapper *,bool,_SharedModelTileNotificationType &>(TileNotification * *,unsigned __int64 &,TileNotificationManager * &&,INotificationDetailsWrapper * &&,bool &&,_SharedModelTileNotificationType &)
0x1801f6009  mov     rcx, [rsp+258h]; this
0x1801f6011  test    eax, eax
0x1801f6013  jns     short loc_1801F602B
0x1801f6015  mov     r9d, eax; char *
0x1801f6018  lea     r8, aShellcommonShe_60; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801f601f  mov     edx, 13Ch; void *
0x1801f6024  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801f6029  jmp     short loc_1801F609E
0x1801f602b  lea     r9, [rsp+258h+SRWLock]
0x1801f6030  lea     r8, [rsp+258h+var_220]
0x1801f6035  lea     rdx, [rsp+258h+var_1B8]
0x1801f603d  lea     rcx, [rsp+258h+var_1F0]
0x1801f6042  call    ??$emplace@AEAKAEAV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEAKAEAV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::emplace<ulong &,Microsoft::WRL::ComPtr<TileNotification> &>(ulong &,Microsoft::WRL::ComPtr<TileNotification> &)
0x1801f6047  mov     eax, dword ptr [rsp+258h+var_220]
0x1801f604b  mov     [rsp+258h+var_228], eax
0x1801f604f  mov     rdx, [rsp+258h+var_1D0]
0x1801f6057  cmp     rdx, [rsp+258h+var_1C8]
0x1801f605f  jz      short loc_1801F606E
0x1801f6061  mov     [rdx], eax
0x1801f6063  add     [rsp+258h+var_1D0], 4
0x1801f606c  jmp     short loc_1801F609E
0x1801f606e  lea     r8, [rsp+258h+var_228]
0x1801f6073  lea     rcx, [rsp+258h+var_1D8]
0x1801f607b  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1801f6080  jmp     short loc_1801F609E
0x1801f6082  add     r9, 28h ; '('
0x1801f6086  lea     r8, [rsp+258h+var_220]
0x1801f608b  lea     rdx, [rsp+258h+var_1A8]
0x1801f6093  lea     rcx, [rsp+258h+var_1F0]
0x1801f6098  call    ??$emplace@AEAKAEAV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEAKAEAV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::emplace<ulong &,Microsoft::WRL::ComPtr<TileNotification> &>(ulong &,Microsoft::WRL::ComPtr<TileNotification> &)
0x1801f609d  nop
0x1801f609e  lea     rcx, [rsp+258h+SRWLock]
0x1801f60a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f60a8  nop
0x1801f60a9  lea     rcx, [rsp+258h+var_210]
0x1801f60ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f60b3  add     edi, esi
0x1801f60b5  jmp     loc_1801F5E9D
0x1801f60ba  lea     r15, [r14+0D0h]
0x1801f60c1  mov     rbx, [r15]
0x1801f60c4  mov     rbx, [rbx]
0x1801f60c7  cmp     [rbx+19h], r13b
0x1801f60cb  jnz     loc_1801F618F
0x1801f60d1  lea     r8, [rbx+20h]
0x1801f60d5  mov     [rsp+258h+var_1E0], r13
0x1801f60da  lea     rdx, [rsp+258h+var_1F8]
0x1801f60df  lea     rcx, [rsp+258h+var_1F0]
0x1801f60e4  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::find(ulong const &)
0x1801f60e9  mov     rdi, [rsp+258h+var_1F8]
0x1801f60ee  cmp     rdi, [rsp+258h+var_1F0]
0x1801f60f3  jz      short loc_1801F6136
0x1801f60f5  mov     rcx, [r8+8]; this
0x1801f60f9  call    ?IsValid@TileNotification@@QEAA_NXZ; TileNotification::IsValid(void)
0x1801f60fe  test    al, al
0x1801f6100  jnz     short loc_1801F6136
0x1801f6102  mov     rdi, [rdi+28h]
0x1801f6106  lea     rdx, [rdi+0E0h]
0x1801f610d  lea     rcx, [rsp+258h+SRWLock]
0x1801f6112  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1801f6117  mov     dword ptr [rdi+0A8h], 4
0x1801f6121  mov     rcx, [rsp+258h+SRWLock]; SRWLock
0x1801f6126  test    rcx, rcx
0x1801f6129  jz      short loc_1801F6136
0x1801f612b  call    cs:__imp_ReleaseSRWLockExclusive
0x1801f6131  mov     [rsp+258h+SRWLock], r13
0x1801f6136  lea     rcx, [rsp+258h+var_1E0]
0x1801f613b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f6140  mov     rcx, [rbx+10h]
0x1801f6144  cmp     [rcx+19h], r13b
0x1801f6148  jz      short loc_1801F616B
0x1801f614a  mov     rax, [rbx+8]
0x1801f614e  jmp     short loc_1801F615D
0x1801f6150  cmp     rbx, [rax+10h]
0x1801f6154  jnz     short loc_1801F6163
0x1801f6156  mov     rbx, rax
0x1801f6159  mov     rax, [rax+8]
0x1801f615d  cmp     [rax+19h], r13b
0x1801f6161  jz      short loc_1801F6150
0x1801f6163  mov     rbx, rax
0x1801f6166  jmp     loc_1801F60C7
0x1801f616b  mov     rbx, rcx
0x1801f616e  mov     rcx, [rcx]
0x1801f6171  cmp     [rcx+19h], r13b
0x1801f6175  jnz     loc_1801F60C7
0x1801f617b  mov     rbx, rcx
0x1801f617e  mov     rax, [rcx]
0x1801f6181  mov     rcx, rax
0x1801f6184  cmp     [rax+19h], r13b
0x1801f6188  jz      short loc_1801F617B
0x1801f618a  jmp     loc_1801F60C7
0x1801f618f  mov     rbx, [r14+0D8h]
0x1801f6196  mov     rcx, r15
0x1801f6199  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::clear(void)
0x1801f619e  lea     rax, [rsp+258h+var_1F0]
0x1801f61a3  cmp     r15, rax
0x1801f61a6  jz      short loc_1801F61D2
0x1801f61a8  mov     rcx, r15
0x1801f61ab  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VTileNotification@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VTileNotification@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<TileNotification>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<TileNotification>>>,0>>::clear(void)
0x1801f61b0  mov     rcx, [r15]
0x1801f61b3  mov     rax, [rsp+258h+var_1F0]
0x1801f61b8  mov     [r15], rax
0x1801f61bb  mov     [rsp+258h+var_1F0], rcx
0x1801f61c0  mov     rcx, [r15+8]
0x1801f61c4  mov     rax, [rsp+258h+var_1E8]
0x1801f61c9  mov     [r15+8], rax
0x1801f61cd  mov     [rsp+258h+var_1E8], rcx
0x1801f61d2  mov     [rsp+258h+var_1F8], r13
0x1801f61d7  mov     rax, [rsp+258h+var_1D0]
0x1801f61df  sub     rax, [rsp+258h+var_1D8]
0x1801f61e7  sar     rax, 2
0x1801f61eb  test    rax, rax
  ... truncated ...
```
