# NotificationQueueManager::FlushPastExpiries(void)

- ea: `0x180164ee4`
- end: `0x1801651fc`
- name: `?FlushPastExpiries@NotificationQueueManager@@AEAAJXZ`
- size: `792`
- prototype: `__int64 __fastcall(NotificationQueueManager *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180282e98`
- `0x180286ef0`

## callees

- `0x18000b5f0`
- `0x18001aca4`
- `0x1800dd908`
- `0x180147be8`
- `0x180159390`
- `0x180161204`
- `0x1801640ac`
- `0x180164394`
- `0x180164ea0`
- `0x180164ee4`
- `0x180165204`
- `0x18016529c`
- `0x1801c2520`
- `0x18027f520`
- `0x180283060`
- `0x180283590`
- `0x180288aa0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180164ff8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801651b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180164ff8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801651b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180164ef8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180164ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016503a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801650f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016517d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016518f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016503a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801650f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016517d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016518f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180165130`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180164f34`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180164f34`

## string_xrefs

- `0x180164f0c`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180164f5b`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801650ac`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801650dc`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180165167`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NotificationQueueManager::FlushPastExpiries(NotificationQueueManager *this)
{
  int v2; // ebx
  int v3; // eax
  unsigned int v4; // ebx
  _DWORD *v6; // rdi
  _DWORD *v7; // r14
  struct TileNotificationManager *v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-40h] BYREF
  __int64 v13; // [rsp+28h] [rbp-38h] BYREF
  PCWSTR StringRawBuffer; // [rsp+30h] [rbp-30h] BYREF
  PCWSTR v15; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v16; // [rsp+40h] [rbp-20h] BYREF
  _DWORD *v17; // [rsp+48h] [rbp-18h]
  __int64 v18; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HSTRING string; // [rsp+90h] [rbp+30h] BYREF
  HSTRING v21; // [rsp+98h] [rbp+38h] BYREF
  struct TileNotificationManager *v22; // [rsp+A0h] [rbp+40h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp+48h] BYREF

  v2 = *((_DWORD *)this + 18);
  if ( v2 != GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x4B9,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      SystemTimeAsFileTime.dwLowDateTime);
  std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(&v16);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = TileExpirationStatusMap::FlushExpiredNotifications(
         (NotificationQueueManager *)((char *)this + 312),
         &SystemTimeAsFileTime);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v6 = v16;
    v7 = v17;
    while ( v6 != v7 )
    {
      v22 = 0;
      Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 448);
      std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::find(
        (char *)this + 80,
        &v13,
        v6 + 2);
      if ( v13 == *((_QWORD *)this + 10) )
      {
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v22);
        break;
      }
      Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(&v22, v13 + 40);
      if ( SRWLock )
      {
        ReleaseSRWLockShared(SRWLock);
        SRWLock = 0;
      }
      v21 = 0;
      string = 0;
      WindowsDeleteString(0);
      v21 = 0;
      v8 = v22;
      TileNotificationManager::GetApplicationUserModelId(v22, &v21);
      WindowsDeleteString(string);
      string = 0;
      TileNotificationManager::GetTileID(v8, &string);
      if ( *((_DWORD *)v8 + 27) == *v6 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v15 = WindowsGetStringRawBuffer(v21, 0);
        NotificationTelemetry::DisplayedNotificationExpired<unsigned short const *,unsigned short const *,unsigned int const &>(
          &v15,
          &StringRawBuffer,
          v6);
        v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v8 + 9) + 48LL))(
               *((_QWORD *)v8 + 9),
               (unsigned int)*v6);
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4D9,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v9,
            SystemTimeAsFileTime.dwLowDateTime);
        v10 = NotificationQueueManager::ProcessNotificationsForTile(this, v8, 1);
        v4 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4DB,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v10,
            SystemTimeAsFileTime.dwLowDateTime);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v21);
          v21 = 0;
          Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v22);
          goto LABEL_5;
        }
      }
      else
      {
        v15 = WindowsGetStringRawBuffer(string, 0);
        StringRawBuffer = WindowsGetStringRawBuffer(v21, 0);
        NotificationTelemetry::NonDisplayedNotificationExpired<unsigned short const *,unsigned short const *,unsigned int const &>(
          &StringRawBuffer,
          &v15,
          v6);
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v8 + 9) + 48LL))(
                *((_QWORD *)v8 + 9),
                (unsigned int)*v6);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4E0,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v11,
            SystemTimeAsFileTime.dwLowDateTime);
      }
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v21);
      v21 = 0;
      Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v22);
      v6 += 4;
    }
    if ( v16 )
    {
      std::_Destroy_range<std::allocator<NotificationPair>>(v16, v17);
      std::_Deallocate<16>(v16, (v18 - (_QWORD)v16) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4BF,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)v3,
      SystemTimeAsFileTime.dwLowDateTime);
LABEL_5:
    if ( v16 )
    {
      std::_Destroy_range<std::allocator<NotificationPair>>(v16, v17);
      std::_Deallocate<16>(v16, (v18 - (_QWORD)v16) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return v4;
  }
}

```

## disassembly

```asm
0x180164ee4  push    rbp
0x180164ee6  push    rbx
0x180164ee7  push    rsi
0x180164ee8  push    rdi
0x180164ee9  push    r14
0x180164eeb  mov     rbp, rsp
0x180164eee  sub     rsp, 60h
0x180164ef2  mov     rsi, rcx
0x180164ef5  mov     ebx, [rcx+48h]
0x180164ef8  call    cs:__imp_GetCurrentThreadId
0x180164efe  cmp     ebx, eax
0x180164f00  jz      short loc_180164F1E
0x180164f02  mov     rcx, [rbp+28h]; this
0x180164f06  mov     r9d, 800705A4h; char *
0x180164f0c  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164f13  mov     edx, 4B9h; void *
0x180164f18  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180164f1e  lea     rcx, [rbp+var_20]
0x180164f22  call    ??0?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x180164f27  nop
0x180164f28  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180164f30  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180164f34  call    cs:__imp_GetSystemTimeAsFileTime
0x180164f3a  lea     rcx, [rsi+138h]; this
0x180164f41  lea     r8, [rbp+var_20]
0x180164f45  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180164f49  call    ?FlushExpiredNotifications@TileExpirationStatusMap@@QEAAJAEAU_FILETIME@@AEAV?$vector@UNotificationPair@@V?$allocator@UNotificationPair@@@std@@@std@@@Z; TileExpirationStatusMap::FlushExpiredNotifications(_FILETIME &,std::vector<NotificationPair> &)
0x180164f4e  mov     ebx, eax
0x180164f50  test    eax, eax
0x180164f52  jns     short loc_180164F9A
0x180164f54  mov     rcx, [rbp+28h]; this
0x180164f58  mov     r9d, eax; char *
0x180164f5b  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164f62  mov     edx, 4BFh; void *
0x180164f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164f6c  nop
0x180164f6d  mov     rcx, [rbp+var_20]
0x180164f71  test    rcx, rcx
0x180164f74  jz      short loc_180164F93
0x180164f76  mov     rdx, [rbp+var_18]
0x180164f7a  call    ??$_Destroy_range@V?$allocator@UNotificationPair@@@std@@@std@@YAXPEAUNotificationPair@@QEAU1@AEAV?$allocator@UNotificationPair@@@0@@Z; std::_Destroy_range<std::allocator<NotificationPair>>(NotificationPair *,NotificationPair * const,std::allocator<NotificationPair> &)
0x180164f7f  mov     rcx, [rbp+var_20]
0x180164f83  mov     rdx, [rbp+var_10]
0x180164f87  sub     rdx, rcx
0x180164f8a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180164f8e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180164f93  mov     eax, ebx
0x180164f95  jmp     loc_1801651F1
0x180164f9a  mov     rdi, [rbp+var_20]
0x180164f9e  mov     r14, [rbp+var_18]
0x180164fa2  cmp     rdi, r14
0x180164fa5  jz      loc_1801651C9
0x180164fab  mov     [rbp+arg_10], 0
0x180164fb3  lea     rdx, [rsi+1C0h]
0x180164fba  lea     rcx, [rbp+SRWLock]
0x180164fbe  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180164fc3  lea     r8, [rdi+8]
0x180164fc7  lea     rdx, [rbp+var_38]
0x180164fcb  lea     rcx, [rsi+50h]
0x180164fcf  call    ?find@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@@std@@@2@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::find(Microsoft::WRL::Wrappers::HString const &)
0x180164fd4  mov     rdx, [rbp+var_38]
0x180164fd8  cmp     rdx, [rsi+50h]
0x180164fdc  jz      loc_1801651AF
0x180164fe2  add     rdx, 28h ; '('
0x180164fe6  lea     rcx, [rbp+arg_10]
0x180164fea  call    ??4?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(Microsoft::WRL::ComPtr<TileNotificationManager> const &)
0x180164fef  mov     rcx, [rbp+SRWLock]; SRWLock
0x180164ff3  test    rcx, rcx
0x180164ff6  jz      short loc_180165006
0x180164ff8  call    cs:__imp_ReleaseSRWLockShared
0x180164ffe  mov     [rbp+SRWLock], 0
0x180165006  mov     [rbp+arg_8], 0
0x18016500e  mov     [rbp+string], 0
0x180165016  xor     ecx, ecx; string
0x180165018  call    cs:__imp_WindowsDeleteString
0x18016501e  mov     [rbp+arg_8], 0
0x180165026  lea     rdx, [rbp+arg_8]; HSTRING *
0x18016502a  mov     rbx, [rbp+arg_10]
0x18016502e  mov     rcx, rbx; this
0x180165031  call    ?GetApplicationUserModelId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetApplicationUserModelId(HSTRING__ * *)
0x180165036  mov     rcx, [rbp+string]; string
0x18016503a  call    cs:__imp_WindowsDeleteString
0x180165040  mov     [rbp+string], 0
0x180165048  lea     rdx, [rbp+string]; HSTRING *
0x18016504c  mov     rcx, rbx; this
0x18016504f  call    ?GetTileID@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetTileID(HSTRING__ * *)
0x180165054  mov     eax, [rdi]
0x180165056  xor     edx, edx; length
0x180165058  mov     rcx, [rbp+string]; string
0x18016505c  cmp     [rbx+6Ch], eax
0x18016505f  jnz     loc_180165120
0x180165065  call    cs:__imp_WindowsGetStringRawBuffer
0x18016506b  mov     [rbp+var_30], rax
0x18016506f  xor     edx, edx; length
0x180165071  mov     rcx, [rbp+arg_8]; string
0x180165075  call    cs:__imp_WindowsGetStringRawBuffer
0x18016507b  mov     [rbp+var_28], rax
0x18016507f  mov     r8, rdi
0x180165082  lea     rdx, [rbp+var_30]
0x180165086  lea     rcx, [rbp+var_28]
0x18016508a  call    ??$DisplayedNotificationExpired@PEBGPEBGAEBI@NotificationTelemetry@@SAX$$QEAPEBG0AEBI@Z; NotificationTelemetry::DisplayedNotificationExpired<ushort const *,ushort const *,uint const &>(ushort const * &&,ushort const * &&,uint const &)
0x18016508f  mov     rcx, [rbx+48h]
0x180165093  mov     rax, [rcx]
0x180165096  mov     edx, [rdi]
0x180165098  mov     rax, [rax+30h]
0x18016509c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801650a1  mov     rcx, [rbp+28h]; this
0x1801650a5  test    eax, eax
0x1801650a7  jns     short loc_1801650BD
0x1801650a9  mov     r9d, eax; char *
0x1801650ac  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801650b3  mov     edx, 4D9h; void *
0x1801650b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801650bd  mov     r8b, 1; bool
0x1801650c0  mov     rdx, rbx; struct TileNotificationManager *
0x1801650c3  mov     rcx, rsi; this
0x1801650c6  call    ?ProcessNotificationsForTile@NotificationQueueManager@@QEAAJPEAVTileNotificationManager@@_N@Z; NotificationQueueManager::ProcessNotificationsForTile(TileNotificationManager *,bool)
0x1801650cb  mov     ebx, eax
0x1801650cd  test    eax, eax
0x1801650cf  jns     loc_180165179
0x1801650d5  mov     rcx, [rbp+28h]; this
0x1801650d9  mov     r9d, eax; char *
0x1801650dc  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801650e3  mov     edx, 4DBh; void *
0x1801650e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801650ed  nop
0x1801650ee  mov     rcx, [rbp+string]; string
0x1801650f2  call    cs:__imp_WindowsDeleteString
0x1801650f8  mov     [rbp+string], 0
0x180165100  mov     rcx, [rbp+arg_8]; string
0x180165104  call    cs:__imp_WindowsDeleteString
0x18016510a  mov     [rbp+arg_8], 0
0x180165112  lea     rcx, [rbp+arg_10]
0x180165116  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x18016511b  jmp     loc_180164F6D
0x180165120  call    cs:__imp_WindowsGetStringRawBuffer
0x180165126  mov     [rbp+var_28], rax
0x18016512a  xor     edx, edx; length
0x18016512c  mov     rcx, [rbp+arg_8]; string
0x180165130  call    cs:__imp_WindowsGetStringRawBuffer
0x180165136  mov     [rbp+var_30], rax
0x18016513a  mov     r8, rdi
0x18016513d  lea     rdx, [rbp+var_28]
0x180165141  lea     rcx, [rbp+var_30]
0x180165145  call    ??$NonDisplayedNotificationExpired@PEBGPEBGAEBI@NotificationTelemetry@@SAX$$QEAPEBG0AEBI@Z; NotificationTelemetry::NonDisplayedNotificationExpired<ushort const *,ushort const *,uint const &>(ushort const * &&,ushort const * &&,uint const &)
0x18016514a  mov     rcx, [rbx+48h]
0x18016514e  mov     rax, [rcx]
0x180165151  mov     edx, [rdi]
0x180165153  mov     rax, [rax+30h]
0x180165157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016515c  mov     rcx, [rbp+28h]; this
0x180165160  test    eax, eax
0x180165162  jns     short loc_180165179
0x180165164  mov     r9d, eax; char *
0x180165167  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18016516e  mov     edx, 4E0h; void *
0x180165173  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180165178  nop
0x180165179  mov     rcx, [rbp+string]; string
0x18016517d  call    cs:__imp_WindowsDeleteString
0x180165183  mov     [rbp+string], 0
0x18016518b  mov     rcx, [rbp+arg_8]; string
0x18016518f  call    cs:__imp_WindowsDeleteString
0x180165195  mov     [rbp+arg_8], 0
0x18016519d  lea     rcx, [rbp+arg_10]
0x1801651a1  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801651a6  add     rdi, 10h
0x1801651aa  jmp     loc_180164FA2
0x1801651af  mov     rcx, [rbp+SRWLock]; SRWLock
0x1801651b3  test    rcx, rcx
0x1801651b6  jz      short loc_1801651BF
0x1801651b8  call    cs:__imp_ReleaseSRWLockShared
0x1801651be  nop
0x1801651bf  lea     rcx, [rbp+arg_10]
0x1801651c3  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801651c8  nop
0x1801651c9  mov     rcx, [rbp+var_20]
0x1801651cd  test    rcx, rcx
0x1801651d0  jz      short loc_1801651EF
0x1801651d2  mov     rdx, [rbp+var_18]
0x1801651d6  call    ??$_Destroy_range@V?$allocator@UNotificationPair@@@std@@@std@@YAXPEAUNotificationPair@@QEAU1@AEAV?$allocator@UNotificationPair@@@0@@Z; std::_Destroy_range<std::allocator<NotificationPair>>(NotificationPair *,NotificationPair * const,std::allocator<NotificationPair> &)
0x1801651db  mov     rcx, [rbp+var_20]
0x1801651df  mov     rdx, [rbp+var_10]
0x1801651e3  sub     rdx, rcx
0x1801651e6  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801651ea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801651ef  xor     eax, eax
0x1801651f1  add     rsp, 60h
0x1801651f5  pop     r14
0x1801651f7  pop     rdi
0x1801651f8  pop     rsi
0x1801651f9  pop     rbx
0x1801651fa  pop     rbp
0x1801651fb  retn
```
