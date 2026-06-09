# NotificationQueueManager::NewNotificationsAvailable(IUnknown *)

- ea: `0x180164d30`
- end: `0x180164e97`
- name: `?NewNotificationsAvailable@NotificationQueueManager@@UEAAJPEAUIUnknown@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(NotificationQueueManager *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001aca4`
- `0x1800dd908`
- `0x180159390`
- `0x1801640ac`
- `0x180164394`
- `0x180164d30`
- `0x180164ea0`
- `0x180288aa0`
- `0x18028a8d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180164e0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180164e2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180164e0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180164e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180164d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180164d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164e6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164e82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164e6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164e82`

## string_xrefs

- `0x180164d5a`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180164d9d`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180164df2`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180164e4d`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
__int64 __fastcall NotificationQueueManager::NewNotificationsAvailable(
        NotificationQueueManager *this,
        struct IUnknown *a2)
{
  int WNSId; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  struct TileNotificationManager *v10; // [rsp+50h] [rbp+20h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+38h] BYREF

  if ( *((_DWORD *)this + 12) != GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xA9B,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      v8);
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  WNSId = TileNotificationManager::GetWNSId(a2, &string);
  v5 = WNSId;
  if ( WNSId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9E,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)WNSId,
      v8);
LABEL_13:
    WindowsDeleteString(string);
    return v5;
  }
  v10 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 424);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::find(
    (char *)this + 56,
    &v8,
    &string);
  if ( v8 == *((_QWORD *)this + 7) )
  {
    v5 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA5,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x80070490LL,
      v8);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    goto LABEL_12;
  }
  Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(&v10, v8 + 40);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v6 = NotificationQueueManager::ProcessNotificationsForTile((NotificationQueueManager *)((char *)this - 24), v10, 1);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAAA,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)v6,
      v8);
LABEL_12:
    Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v10);
    goto LABEL_13;
  }
  Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v10);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180164d30  mov     [rsp-18h+arg_8], rbx
0x180164d35  push    rbp
0x180164d36  push    rsi
0x180164d37  push    rdi
0x180164d38  mov     rbp, rsp
0x180164d3b  sub     rsp, 30h
0x180164d3f  mov     rbx, rdx
0x180164d42  mov     rdi, rcx
0x180164d45  call    cs:__imp_GetCurrentThreadId
0x180164d4b  cmp     [rdi+30h], eax
0x180164d4e  jz      short loc_180164D6C
0x180164d50  mov     rcx, [rbp+18h]; this
0x180164d54  mov     r9d, 800705A4h; char *
0x180164d5a  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164d61  mov     edx, 0A9Bh; void *
0x180164d66  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180164d6c  mov     [rbp+string], 0
0x180164d74  xor     ecx, ecx; string
0x180164d76  call    cs:__imp_WindowsDeleteString
0x180164d7c  mov     [rbp+string], 0
0x180164d84  lea     rdx, [rbp+string]; HSTRING *
0x180164d88  mov     rcx, rbx; struct IUnknown *
0x180164d8b  call    ?GetWNSId@TileNotificationManager@@SAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; TileNotificationManager::GetWNSId(IUnknown *,HSTRING__ * *)
0x180164d90  mov     ebx, eax
0x180164d92  test    eax, eax
0x180164d94  jns     short loc_180164DB3
0x180164d96  mov     rcx, [rbp+18h]; this
0x180164d9a  mov     r9d, eax; char *
0x180164d9d  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164da4  mov     edx, 0A9Eh; void *
0x180164da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164dae  jmp     loc_180164E67
0x180164db3  mov     [rbp+arg_0], 0
0x180164dbb  lea     rdx, [rdi+1A8h]
0x180164dc2  lea     rcx, [rbp+SRWLock]
0x180164dc6  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180164dcb  lea     r8, [rbp+string]
0x180164dcf  lea     rdx, [rbp+var_10]
0x180164dd3  lea     rcx, [rdi+38h]
0x180164dd7  call    ?find@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@@std@@@2@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::find(Microsoft::WRL::Wrappers::HString const &)
0x180164ddc  mov     rdx, [rbp+var_10]
0x180164de0  cmp     rdx, [rdi+38h]
0x180164de4  jnz     short loc_180164E14
0x180164de6  mov     rcx, [rbp+18h]; this
0x180164dea  mov     ebx, 80070490h
0x180164def  mov     r9d, ebx; char *
0x180164df2  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164df9  mov     edx, 0AA5h; void *
0x180164dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164e03  mov     rcx, [rbp+SRWLock]; SRWLock
0x180164e07  test    rcx, rcx
0x180164e0a  jz      short loc_180164E5E
0x180164e0c  call    cs:__imp_ReleaseSRWLockShared
0x180164e12  jmp     short loc_180164E5E
0x180164e14  add     rdx, 28h ; '('
0x180164e18  lea     rcx, [rbp+arg_0]
0x180164e1c  call    ??4?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(Microsoft::WRL::ComPtr<TileNotificationManager> const &)
0x180164e21  mov     rcx, [rbp+SRWLock]; SRWLock
0x180164e25  test    rcx, rcx
0x180164e28  jz      short loc_180164E30
0x180164e2a  call    cs:__imp_ReleaseSRWLockShared
0x180164e30  mov     r8b, 1; bool
0x180164e33  mov     rdx, [rbp+arg_0]; struct TileNotificationManager *
0x180164e37  lea     rcx, [rdi-18h]; this
0x180164e3b  call    ?ProcessNotificationsForTile@NotificationQueueManager@@QEAAJPEAVTileNotificationManager@@_N@Z; NotificationQueueManager::ProcessNotificationsForTile(TileNotificationManager *,bool)
0x180164e40  mov     ebx, eax
0x180164e42  test    eax, eax
0x180164e44  jns     short loc_180164E75
0x180164e46  mov     rcx, [rbp+18h]; this
0x180164e4a  mov     r9d, eax; char *
0x180164e4d  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164e54  mov     edx, 0AAAh; void *
0x180164e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164e5e  lea     rcx, [rbp+arg_0]
0x180164e62  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180164e67  mov     rcx, [rbp+string]; string
0x180164e6b  call    cs:__imp_WindowsDeleteString
0x180164e71  mov     eax, ebx
0x180164e73  jmp     short loc_180164E8A
0x180164e75  lea     rcx, [rbp+arg_0]
0x180164e79  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180164e7e  mov     rcx, [rbp+string]; string
0x180164e82  call    cs:__imp_WindowsDeleteString
0x180164e88  xor     eax, eax
0x180164e8a  mov     rbx, [rsp+30h+arg_8]
0x180164e8f  add     rsp, 30h
0x180164e93  pop     rdi
0x180164e94  pop     rsi
0x180164e95  pop     rbp
0x180164e96  retn
```
