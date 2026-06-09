# NotificationQueueManager::SetLastVisibleNotification(IUnknown *,uint,ushort const *,TilePresentedFlags)

- ea: `0x180164180`
- end: `0x18016438c`
- name: `?SetLastVisibleNotification@NotificationQueueManager@@UEAAJPEAUIUnknown@@IPEBGW4TilePresentedFlags@@@Z`
- size: `524`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001aca4`
- `0x1800c5b3c`
- `0x180159390`
- `0x1801640ac`
- `0x180164180`
- `0x180164394`
- `0x180164ea0`
- `0x180288aa0`
- `0x18028a8d0`
- `0x18028b690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180164262`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801642c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180164262`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801642c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18016419f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18016419f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801641d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016434f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801641d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016434f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180164369`

## string_xrefs

- `0x1801641b5`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801641fc`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801642e5`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x18016432d`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NotificationQueueManager::SetLastVisibleNotification(
        __int64 a1,
        struct IUnknown *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        char a5)
{
  int WNSId; // eax
  unsigned int v10; // ebx
  __int64 result; // rax
  struct TileNotificationManager *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  int DisplayedNotification; // eax
  unsigned int v17; // ebx
  struct TileNotificationManager *v18; // [rsp+20h] [rbp-38h] BYREF
  PSRWLOCK SRWLock; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v20[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HSTRING string; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 64) != GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      (int)v18);
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  WNSId = TileNotificationManager::GetWNSId(a2, &string);
  v10 = WNSId;
  if ( WNSId >= 0 )
  {
    v18 = 0;
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 440);
    std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::find(
      a1 + 72,
      v20,
      &string);
    if ( v20[0] == *(_QWORD *)(a1 + 72) )
    {
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v18);
      WindowsDeleteString(string);
      return 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(&v18, v20[0] + 40LL);
      v12 = v18;
      *((_DWORD *)v18 + 27) = a3;
      *((_BYTE *)v12 + 112) = a5 & 1;
      *((_BYTE *)v12 + 113) = 0;
      if ( !a3 )
        *((_QWORD *)v12 + 11) = 0;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      try
      {
        v13 = NotificationQueueManager::ProcessNotificationsForTile((NotificationQueueManager *)(a1 - 8), v12, 0);
        v14 = v13;
        if ( v13 >= 0 )
        {
          DisplayedNotification = TileNotificationManager::SetLastDisplayedNotification(
                                    (struct TileNotificationManager *)((char *)v12 + 16),
                                    a3,
                                    a4);
          v17 = DisplayedNotification;
          if ( DisplayedNotification >= 0 )
          {
            Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v18);
            WindowsDeleteString(string);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x158,
              (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
              (const char *)(unsigned int)DisplayedNotification,
              (int)v18);
            Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v18);
            WindowsDeleteString(string);
            result = v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x155,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v13,
            (int)v18);
          Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v18);
          WindowsDeleteString(string);
          result = v14;
        }
      }
      catch ( ... )
      {
        LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0x15C,
                            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notific"
                                          "ationqueuemanager.cpp",
                            v15);
        return (unsigned int)string;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)WNSId,
      (int)v18);
    WindowsDeleteString(string);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180164180  mov     [rsp+arg_8], rbx
0x180164185  mov     [rsp+arg_10], rsi
0x18016418a  push    rdi
0x18016418b  push    r14
0x18016418d  push    r15
0x18016418f  sub     rsp, 40h
0x180164193  mov     r15, r9
0x180164196  mov     esi, r8d
0x180164199  mov     rbx, rdx
0x18016419c  mov     rdi, rcx
0x18016419f  call    cs:__imp_GetCurrentThreadId
0x1801641a5  cmp     [rdi+40h], eax
0x1801641a8  jz      short loc_1801641C7
0x1801641aa  mov     rcx, [rsp+58h]; this
0x1801641af  mov     r9d, 800705A4h; char *
0x1801641b5  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801641bc  mov     edx, 131h; void *
0x1801641c1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801641c7  mov     [rsp+58h+string], 0
0x1801641d0  xor     ecx, ecx; string
0x1801641d2  call    cs:__imp_WindowsDeleteString
0x1801641d8  mov     [rsp+58h+string], 0
0x1801641e1  lea     rdx, [rsp+58h+string]; HSTRING *
0x1801641e6  mov     rcx, rbx; struct IUnknown *
0x1801641e9  call    ?GetWNSId@TileNotificationManager@@SAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; TileNotificationManager::GetWNSId(IUnknown *,HSTRING__ * *)
0x1801641ee  mov     ebx, eax
0x1801641f0  test    eax, eax
0x1801641f2  jns     short loc_180164220
0x1801641f4  mov     rcx, [rsp+58h]; this
0x1801641f9  mov     r9d, eax; char *
0x1801641fc  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164203  mov     edx, 134h; void *
0x180164208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016420d  nop
0x18016420e  mov     rcx, [rsp+58h+string]; string
0x180164213  call    cs:__imp_WindowsDeleteString
0x180164219  mov     eax, ebx
0x18016421b  jmp     loc_180164377
0x180164220  mov     [rsp+58h+var_38], 0; int
0x180164229  lea     rdx, [rdi+1B8h]
0x180164230  lea     rcx, [rsp+58h+SRWLock]
0x180164235  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18016423a  lea     r8, [rsp+58h+string]
0x18016423f  lea     rdx, [rsp+58h+var_28]
0x180164244  lea     rcx, [rdi+48h]
0x180164248  call    ?find@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@@std@@@2@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::find(Microsoft::WRL::Wrappers::HString const &)
0x18016424d  mov     rdx, [rsp+58h+var_28]
0x180164252  cmp     rdx, [rdi+48h]
0x180164256  jnz     short loc_180164286
0x180164258  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x18016425d  test    rcx, rcx
0x180164260  jz      short loc_180164269
0x180164262  call    cs:__imp_ReleaseSRWLockExclusive
0x180164268  nop
0x180164269  lea     rcx, [rsp+58h+var_38]
0x18016426e  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180164273  nop
0x180164274  mov     rcx, [rsp+58h+string]; string
0x180164279  call    cs:__imp_WindowsDeleteString
0x18016427f  xor     eax, eax
0x180164281  jmp     loc_180164377
0x180164286  add     rdx, 28h ; '('
0x18016428a  lea     rcx, [rsp+58h+var_38]
0x18016428f  call    ??4?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(Microsoft::WRL::ComPtr<TileNotificationManager> const &)
0x180164294  mov     rbx, [rsp+58h+var_38]
0x180164299  mov     [rbx+6Ch], esi
0x18016429c  mov     eax, [rsp+58h+arg_20]
0x1801642a3  and     al, 1
0x1801642a5  mov     [rbx+70h], al
0x1801642a8  mov     byte ptr [rbx+71h], 0
0x1801642ac  test    esi, esi
0x1801642ae  jnz     short loc_1801642B8
0x1801642b0  mov     qword ptr [rbx+58h], 0
0x1801642b8  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x1801642bd  test    rcx, rcx
0x1801642c0  jz      short loc_1801642C8
0x1801642c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1801642c8  xor     r8d, r8d; bool
0x1801642cb  mov     rdx, rbx; struct TileNotificationManager *
0x1801642ce  lea     rcx, [rdi-8]; this
0x1801642d2  call    ?ProcessNotificationsForTile@NotificationQueueManager@@QEAAJPEAVTileNotificationManager@@_N@Z; NotificationQueueManager::ProcessNotificationsForTile(TileNotificationManager *,bool)
0x1801642d7  mov     edi, eax
0x1801642d9  test    eax, eax
0x1801642db  jns     short loc_180164311
0x1801642dd  mov     rcx, [rsp+58h]; this
0x1801642e2  mov     r9d, eax; char *
0x1801642e5  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801642ec  mov     edx, 155h; void *
0x1801642f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801642f6  nop
0x1801642f7  lea     rcx, [rsp+58h+var_38]
0x1801642fc  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180164301  nop
0x180164302  mov     rcx, [rsp+58h+string]; string
0x180164307  call    cs:__imp_WindowsDeleteString
0x18016430d  mov     eax, edi
0x18016430f  jmp     short loc_180164377
0x180164311  lea     rcx, [rbx+10h]; this
0x180164315  mov     r8, r15; unsigned __int16 *
0x180164318  mov     edx, esi; unsigned int
0x18016431a  call    ?SetLastDisplayedNotification@TileNotificationManager@@UEAAJIPEBG@Z; TileNotificationManager::SetLastDisplayedNotification(uint,ushort const *)
0x18016431f  mov     ebx, eax
0x180164321  test    eax, eax
0x180164323  jns     short loc_180164359
0x180164325  mov     rcx, [rsp+58h]; this
0x18016432a  mov     r9d, eax; char *
0x18016432d  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180164334  mov     edx, 158h; void *
0x180164339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016433e  nop
0x18016433f  lea     rcx, [rsp+58h+var_38]
0x180164344  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180164349  nop
0x18016434a  mov     rcx, [rsp+58h+string]; string
0x18016434f  call    cs:__imp_WindowsDeleteString
0x180164355  mov     eax, ebx
0x180164357  jmp     short loc_180164377
0x180164359  lea     rcx, [rsp+58h+var_38]
0x18016435e  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180164363  nop
0x180164364  mov     rcx, [rsp+58h+string]; string
0x180164369  call    cs:__imp_WindowsDeleteString
0x18016436f  xor     eax, eax
0x180164371  jmp     short loc_180164377
0x180164373  mov     eax, dword ptr [rsp+58h+string]
0x180164377  mov     rbx, [rsp+58h+arg_8]
0x18016437c  mov     rsi, [rsp+58h+arg_10]
0x180164381  add     rsp, 40h
0x180164385  pop     r15
0x180164387  pop     r14
0x180164389  pop     rdi
0x18016438a  retn
```
