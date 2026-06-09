# NotificationQueueManager::SendSingleBadgeNotification(HSTRING__ *,IStartTileNotification *)

- ea: `0x180161e50`
- end: `0x180162289`
- name: `?SendSingleBadgeNotification@NotificationQueueManager@@AEAA_NPEAUHSTRING__@@PEAUIStartTileNotification@@@Z`
- size: `1081`
- prototype: `bool __fastcall(NotificationQueueManager *__hidden this, HSTRING, struct IStartTileNotification *)`
- caller_count: `3`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180164394`
- `0x1802843ac`
- `0x1802850fc`

## callees

- `0x1800385d0`
- `0x1800dd908`
- `0x180161204`
- `0x180161e50`
- `0x180162950`
- `0x1801640ac`
- `0x180164ea0`
- `0x1801ee5c0`
- `0x1801ee734`
- `0x180201e50`
- `0x18027e60c`
- `0x18027e6e4`
- `0x18028087c`
- `0x1802808e8`
- `0x180280c38`
- `0x180281744`
- `0x180283060`
- `0x180283590`
- `0x18028553c`
- `0x180285a5c`
- `0x180286ef0`
- `0x18028a1bc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180161ebe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180161eee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180161ebe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180161eee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801620a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801620b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016227c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180161f2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801620a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801620b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016227c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180161f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180161f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016203b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016204d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016213f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180162151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180161f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180161f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016203b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016204d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016213f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180162151`

## string_xrefs

- `0x180162021`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180162123`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801621e4`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180162219`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180162251`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall NotificationQueueManager::SendSingleBadgeNotification(
        NotificationQueueManager *this,
        HSTRING a2,
        struct IStartTileNotification *a3)
{
  bool result; // al
  TileNotificationManager *v6; // rbx
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v8; // rdi
  int v9; // eax
  bool v10; // bl
  const char *v11; // r9
  int v12; // eax
  int v13; // edi
  HSTRING v14; // rbx
  int ready; // eax
  int updated; // eax
  int v17; // eax
  int v18; // [rsp+20h] [rbp-208h]
  int v19; // [rsp+20h] [rbp-208h]
  unsigned int v20; // [rsp+30h] [rbp-1F8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-1F0h] BYREF
  HSTRING v22; // [rsp+40h] [rbp-1E8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-1E0h] BYREF
  int v24; // [rsp+50h] [rbp-1D8h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-1D0h] BYREF
  TileNotificationManager *v26; // [rsp+60h] [rbp-1C8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-1C0h] BYREF
  PCWSTR v28; // [rsp+70h] [rbp-1B8h] BYREF
  _QWORD v29[2]; // [rsp+78h] [rbp-1B0h] BYREF
  struct _GUID v30; // [rsp+88h] [rbp-1A0h] BYREF
  _QWORD v31[42]; // [rsp+A0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v25 = a2;
  v26 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 448);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,std::unique_ptr<TileExpiryStatus>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,std::unique_ptr<TileExpiryStatus>>>,0>>::find<HSTRING__ *,wil::hstring_insensitive_less,0>(
    (char *)this + 80,
    &v27,
    &v25);
  if ( v27 == *((_QWORD *)this + 10) )
  {
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v26);
    return 0;
  }
  Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(&v26, v27 + 40);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  WindowsDeleteString(0);
  v22 = 0;
  v6 = v26;
  TileNotificationManager::GetApplicationUserModelId(v26, &v22);
  WindowsDeleteString(0);
  string = 0;
  TileNotificationManager::GetTileID(v6, &string);
  v20 = 0;
  v30 = 0;
  try
  {
    (*(void (**)(void))(*(_QWORD *)a3 + 56LL))();
    (*(void (__fastcall **)(struct IStartTileNotification *, struct _GUID *))(*(_QWORD *)a3 + 64LL))(a3, &v30);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = WindowsGetStringRawBuffer(v22, 0);
    wil::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v31);
    v31[0] = &NotificationTelemetry::SendSingleBadgeNotification::`vftable';
    NotificationTelemetry::SendSingleBadgeNotification::StartActivity(
      (NotificationTelemetry::SendSingleBadgeNotification *)v31,
      v8,
      StringRawBuffer,
      v20,
      &v30);
    v24 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v6 + 9) + 24LL))(*((_QWORD *)v6 + 9), &v24);
    if ( v9 >= 0 )
    {
      if ( v24 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, struct IStartTileNotification *))(**((_QWORD **)v6 + 9) + 64LL))(
                *((_QWORD *)v6 + 9),
                a3);
        v13 = v12;
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6EE,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v12,
            v18);
        LODWORD(v27) = v13;
        v28 = WindowsGetStringRawBuffer(string, 0);
        v29[0] = WindowsGetStringRawBuffer(v22, 0);
        NotificationTelemetry::SendSingleBadgeNotification::BadgeSentToUI<unsigned short const *,unsigned short const *,unsigned int &,_GUID &,long &>(
          (unsigned int)v31,
          (unsigned int)v29,
          (unsigned int)&v28,
          (unsigned int)&v20,
          (__int64)&v30,
          (__int64)&v27);
        std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<IObjectCollection>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<IObjectCollection>>>,0>>::_Eqrange<HSTRING__ *>(
          (char *)this + 112,
          v29,
          &v25);
        if ( std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>>,std::_Iterator_base0>>(
               v29[0],
               v29[1])
          && TileNotificationManager::EligibleToAnimateAgain(v6) )
        {
          v14 = v25;
          ready = NotificationQueueManager::SendSingleReadyNotification(this, v25);
          if ( ready < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6F4,
              (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
              (const char *)(unsigned int)ready,
              v19);
        }
        else
        {
          v14 = v25;
        }
        updated = NotificationQueueManager::UpdateExpiry(this, v14, a3);
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6F6,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)updated,
            v19);
        SRWLock = 0;
        v17 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)&SRWLock, &v25);
        if ( v17 >= 0 )
          std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<IStartTileNotification>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<IStartTileNotification>>>,0>>::erase(
            (char *)this + 144,
            &SRWLock);
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6F9,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v17,
            v19);
        v10 = 1;
        WindowsDeleteString((HSTRING)SRWLock);
        goto LABEL_11;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6EC,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v9,
        v18);
    }
    v10 = 0;
    v29[0] = WindowsGetStringRawBuffer(string, 0);
    v28 = WindowsGetStringRawBuffer(v22, 0);
    NotificationTelemetry::SendSingleBadgeNotification::BadgeUpdateBlockedByUI<unsigned short const *,unsigned short const *,unsigned int &,_GUID &>(
      (unsigned int)v31,
      (unsigned int)&v28,
      (unsigned int)v29,
      (unsigned int)&v20,
      (__int64)&v30);
LABEL_11:
    wil::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
    NotificationTelemetry::SendSingleBadgeNotification::~SendSingleBadgeNotification((NotificationTelemetry::SendSingleBadgeNotification *)v31);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v22);
    v22 = 0;
    Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v26);
    result = v10;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x708,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      v11);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180161e50  push    rbx
0x180161e52  push    rsi
0x180161e53  push    rdi
0x180161e54  push    r14
0x180161e56  push    r15
0x180161e58  sub     rsp, 200h
0x180161e5f  mov     rax, cs:__security_cookie
0x180161e66  xor     rax, rsp
0x180161e69  mov     [rsp+228h+var_38], rax
0x180161e71  mov     r15, r8
0x180161e74  mov     r14, rcx
0x180161e77  mov     [rsp+228h+var_1D0], rdx
0x180161e7c  mov     [rsp+228h+var_1C8], 0
0x180161e85  lea     rdx, [rcx+1C0h]
0x180161e8c  lea     rcx, [rsp+228h+SRWLock]
0x180161e91  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180161e96  lea     r8, [rsp+228h+var_1D0]
0x180161e9b  lea     rdx, [rsp+228h+var_1C0]
0x180161ea0  lea     rcx, [r14+50h]
0x180161ea4  call    ??$find@PEAUHSTRING__@@Uhstring_insensitive_less@wil@@$0A@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$unique_ptr@VTileExpiryStatus@@U?$default_delete@VTileExpiryStatus@@@std@@@std@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$unique_ptr@VTileExpiryStatus@@U?$default_delete@VTileExpiryStatus@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$unique_ptr@VTileExpiryStatus@@U?$default_delete@VTileExpiryStatus@@@std@@@std@@@std@@@std@@@std@@@1@AEBQEAUHSTRING__@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,std::unique_ptr<TileExpiryStatus>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,std::unique_ptr<TileExpiryStatus>>>,0>>::find<HSTRING__ *,wil::hstring_insensitive_less,0>(HSTRING__ * const &)
0x180161ea9  mov     rdx, [rsp+228h+var_1C0]
0x180161eae  cmp     rdx, [r14+50h]
0x180161eb2  jnz     short loc_180161ED6
0x180161eb4  mov     rcx, [rsp+228h+SRWLock]; SRWLock
0x180161eb9  test    rcx, rcx
0x180161ebc  jz      short loc_180161EC5
0x180161ebe  call    cs:__imp_ReleaseSRWLockShared
0x180161ec4  nop
0x180161ec5  lea     rcx, [rsp+228h+var_1C8]
0x180161eca  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180161ecf  xor     al, al
0x180161ed1  jmp     loc_1801620D5
0x180161ed6  add     rdx, 28h ; '('
0x180161eda  lea     rcx, [rsp+228h+var_1C8]
0x180161edf  call    ??4?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(Microsoft::WRL::ComPtr<TileNotificationManager> const &)
0x180161ee4  mov     rcx, [rsp+228h+SRWLock]; SRWLock
0x180161ee9  test    rcx, rcx
0x180161eec  jz      short loc_180161EF4
0x180161eee  call    cs:__imp_ReleaseSRWLockShared
0x180161ef4  mov     [rsp+228h+var_1E8], 0
0x180161efd  mov     [rsp+228h+string], 0
0x180161f06  xor     ecx, ecx; string
0x180161f08  call    cs:__imp_WindowsDeleteString
0x180161f0e  mov     [rsp+228h+var_1E8], 0
0x180161f17  lea     rdx, [rsp+228h+var_1E8]; HSTRING *
0x180161f1c  mov     rbx, [rsp+228h+var_1C8]
0x180161f21  mov     rcx, rbx; this
0x180161f24  call    ?GetApplicationUserModelId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetApplicationUserModelId(HSTRING__ * *)
0x180161f29  mov     rcx, [rsp+228h+string]; string
0x180161f2e  call    cs:__imp_WindowsDeleteString
0x180161f34  mov     [rsp+228h+string], 0
0x180161f3d  lea     rdx, [rsp+228h+string]; HSTRING *
0x180161f42  mov     rcx, rbx; this
0x180161f45  call    ?GetTileID@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetTileID(HSTRING__ * *)
0x180161f4a  mov     [rsp+228h+var_1F8], 0
0x180161f52  xorps   xmm0, xmm0
0x180161f55  movups  xmmword ptr [rsp+228h+var_1A0.Data1], xmm0
0x180161f5d  mov     rax, [r15]
0x180161f60  lea     rdx, [rsp+228h+var_1F8]
0x180161f65  mov     rcx, r15
0x180161f68  mov     rax, [rax+38h]
0x180161f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161f71  mov     rax, [r15]
0x180161f74  lea     rdx, [rsp+228h+var_1A0]
0x180161f7c  mov     rcx, r15
0x180161f7f  mov     rax, [rax+40h]
0x180161f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161f88  xor     edx, edx; length
0x180161f8a  mov     rcx, [rsp+228h+string]; string
0x180161f8f  call    cs:__imp_WindowsGetStringRawBuffer
0x180161f95  mov     rsi, rax
0x180161f98  xor     edx, edx; length
0x180161f9a  mov     rcx, [rsp+228h+var_1E8]; string
0x180161f9f  call    cs:__imp_WindowsGetStringRawBuffer
0x180161fa5  mov     rdi, rax
0x180161fa8  lea     rdx, aSendsinglebadg; "SendSingleBadgeNotification"
0x180161faf  lea     rcx, [rsp+228h+var_188]; struct wil::details::IFailureCallback *
0x180161fb7  call    ??0?$ActivityBase@VNotificationLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180161fbc  lea     rax, ??_7SendSingleBadgeNotification@NotificationTelemetry@@6B@; const NotificationTelemetry::SendSingleBadgeNotification::`vftable'
0x180161fc3  mov     [rsp+228h+var_188], rax
0x180161fcb  lea     rax, [rsp+228h+var_1A0]
0x180161fd3  mov     [rsp+228h+var_208], rax; int
0x180161fd8  mov     r9d, [rsp+228h+var_1F8]; unsigned int
0x180161fdd  mov     r8, rsi; unsigned __int16 *
0x180161fe0  mov     rdx, rdi; unsigned __int16 *
0x180161fe3  lea     rcx, [rsp+228h+var_188]; this
0x180161feb  call    ?StartActivity@SendSingleBadgeNotification@NotificationTelemetry@@QEAAXPEBG0IAEBU_GUID@@@Z; NotificationTelemetry::SendSingleBadgeNotification::StartActivity(ushort const *,ushort const *,uint,_GUID const &)
0x180161ff0  nop
0x180161ff1  mov     [rsp+228h+var_1D8], 0
0x180161ff9  mov     rcx, [rbx+48h]
0x180161ffd  mov     rax, [rcx]
0x180162000  lea     rdx, [rsp+228h+var_1D8]
0x180162005  mov     rax, [rax+18h]
0x180162009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016200e  mov     rcx, [rsp+228h]; this
0x180162016  test    eax, eax
0x180162018  jns     loc_1801620F4
0x18016201e  mov     r9d, eax; char *
0x180162021  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180162028  mov     edx, 6ECh; void *
0x18016202d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180162032  xor     bl, bl
0x180162034  xor     edx, edx; length
0x180162036  mov     rcx, [rsp+228h+string]; string
0x18016203b  call    cs:__imp_WindowsGetStringRawBuffer
0x180162041  mov     [rsp+228h+var_1B0], rax
0x180162046  xor     edx, edx; length
0x180162048  mov     rcx, [rsp+228h+var_1E8]; string
0x18016204d  call    cs:__imp_WindowsGetStringRawBuffer
0x180162053  mov     [rsp+228h+var_1B8], rax
0x180162058  lea     rax, [rsp+228h+var_1A0]
0x180162060  mov     [rsp+228h+var_208], rax
0x180162065  lea     r9, [rsp+228h+var_1F8]
0x18016206a  lea     r8, [rsp+228h+var_1B0]
0x18016206f  lea     rdx, [rsp+228h+var_1B8]
0x180162074  lea     rcx, [rsp+228h+var_188]
0x18016207c  call    ??$BadgeUpdateBlockedByUI@PEBGPEBGAEAIAEAU_GUID@@@SendSingleBadgeNotification@NotificationTelemetry@@QEAAX$$QEAPEBG0AEAIAEAU_GUID@@@Z; NotificationTelemetry::SendSingleBadgeNotification::BadgeUpdateBlockedByUI<ushort const *,ushort const *,uint &,_GUID &>(ushort const * &&,ushort const * &&,uint &,_GUID &)
0x180162081  lea     rcx, [rsp+228h+var_188]
0x180162089  call    ?Stop@?$ActivityBase@VNotificationLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NotificationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18016208e  nop
0x18016208f  lea     rcx, [rsp+228h+var_188]; this
0x180162097  call    ??1SendSingleBadgeNotification@NotificationTelemetry@@QEAA@XZ; NotificationTelemetry::SendSingleBadgeNotification::~SendSingleBadgeNotification(void)
0x18016209c  nop
0x18016209d  mov     rcx, [rsp+228h+string]; string
0x1801620a2  call    cs:__imp_WindowsDeleteString
0x1801620a8  mov     [rsp+228h+string], 0
0x1801620b1  mov     rcx, [rsp+228h+var_1E8]; string
0x1801620b6  call    cs:__imp_WindowsDeleteString
0x1801620bc  mov     [rsp+228h+var_1E8], 0
0x1801620c5  lea     rcx, [rsp+228h+var_1C8]
0x1801620ca  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801620cf  mov     al, bl
0x1801620d1  jmp     short loc_1801620D5
0x1801620d3  xor     al, al
0x1801620d5  mov     rcx, [rsp+228h+var_38]
0x1801620dd  xor     rcx, rsp; StackCookie
0x1801620e0  call    __security_check_cookie
0x1801620e5  add     rsp, 200h
0x1801620ec  pop     r15
0x1801620ee  pop     r14
0x1801620f0  pop     rdi
0x1801620f1  pop     rsi
0x1801620f2  pop     rbx
0x1801620f3  retn
0x1801620f4  cmp     [rsp+228h+var_1D8], 0
0x1801620f9  jz      loc_180162032
0x1801620ff  mov     rcx, [rbx+48h]
0x180162103  mov     rax, [rcx]
0x180162106  mov     rdx, r15
0x180162109  mov     rax, [rax+40h]
0x18016210d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162112  mov     edi, eax
0x180162114  mov     rcx, [rsp+228h]; this
0x18016211c  test    eax, eax
0x18016211e  jns     short loc_180162134
0x180162120  mov     r9d, eax; char *
0x180162123  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18016212a  mov     edx, 6EEh; void *
0x18016212f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180162134  mov     dword ptr [rsp+228h+var_1C0], edi
0x180162138  xor     edx, edx; length
0x18016213a  mov     rcx, [rsp+228h+string]; string
0x18016213f  call    cs:__imp_WindowsGetStringRawBuffer
0x180162145  mov     [rsp+228h+var_1B8], rax
0x18016214a  xor     edx, edx; length
0x18016214c  mov     rcx, [rsp+228h+var_1E8]; string
0x180162151  call    cs:__imp_WindowsGetStringRawBuffer
0x180162157  mov     [rsp+228h+var_1B0], rax
0x18016215c  lea     rax, [rsp+228h+var_1C0]
0x180162161  mov     [rsp+228h+var_200], rax
0x180162166  lea     rax, [rsp+228h+var_1A0]
0x18016216e  mov     [rsp+228h+var_208], rax; int
0x180162173  lea     r9, [rsp+228h+var_1F8]
0x180162178  lea     r8, [rsp+228h+var_1B8]
0x18016217d  lea     rdx, [rsp+228h+var_1B0]
0x180162182  lea     rcx, [rsp+228h+var_188]
0x18016218a  call    ??$BadgeSentToUI@PEBGPEBGAEAIAEAU_GUID@@AEAJ@SendSingleBadgeNotification@NotificationTelemetry@@QEAAX$$QEAPEBG0AEAIAEAU_GUID@@AEAJ@Z; NotificationTelemetry::SendSingleBadgeNotification::BadgeSentToUI<ushort const *,ushort const *,uint &,_GUID &,long &>(ushort const * &&,ushort const * &&,uint &,_GUID &,long &)
0x18016218f  lea     rcx, [r14+70h]
0x180162193  lea     r8, [rsp+228h+var_1D0]
0x180162198  lea     rdx, [rsp+228h+var_1B0]
0x18016219d  call    ??$_Eqrange@PEAUHSTRING__@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@UIObjectCollection@@@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@UIObjectCollection@@@34@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@UIObjectCollection@@@34@@std@@PEAX@std@@PEAU12@@1@AEBQEAUHSTRING__@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<IObjectCollection>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<IObjectCollection>>>,0>>::_Eqrange<HSTRING__ *>(HSTRING__ * const &)
0x1801621a2  mov     rdx, [rsp+228h+var_1A8]
0x1801621aa  mov     rcx, [rsp+228h+var_1B0]
0x1801621af  call    ??$distance@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@YA_JV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@std@@@std@@U_Iterator_base0@2@@0@0@Z; std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>>,std::_Iterator_base0>)
0x1801621b4  test    rax, rax
0x1801621b7  jz      short loc_1801621F7
0x1801621b9  mov     rcx, rbx; this
0x1801621bc  call    ?EligibleToAnimateAgain@TileNotificationManager@@QEBA_NXZ; TileNotificationManager::EligibleToAnimateAgain(void)
0x1801621c1  test    al, al
0x1801621c3  jz      short loc_1801621F7
0x1801621c5  mov     rbx, [rsp+228h+var_1D0]
0x1801621ca  mov     rdx, rbx; HSTRING
0x1801621cd  mov     rcx, r14; this
0x1801621d0  call    ?SendSingleReadyNotification@NotificationQueueManager@@AEAAJPEAUHSTRING__@@@Z; NotificationQueueManager::SendSingleReadyNotification(HSTRING__ *)
0x1801621d5  mov     rcx, [rsp+228h]; this
0x1801621dd  test    eax, eax
0x1801621df  jns     short loc_1801621FC
0x1801621e1  mov     r9d, eax; char *
0x1801621e4  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801621eb  mov     edx, 6F4h; void *
0x1801621f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801621f5  jmp     short loc_1801621FC
0x1801621f7  mov     rbx, [rsp+228h+var_1D0]
0x1801621fc  mov     r8, r15; struct IStartTileNotification *
0x1801621ff  mov     rdx, rbx; HSTRING
0x180162202  mov     rcx, r14; this
0x180162205  call    ?UpdateExpiry@NotificationQueueManager@@AEAAJPEAUHSTRING__@@PEAUIStartTileNotification@@@Z; NotificationQueueManager::UpdateExpiry(HSTRING__ *,IStartTileNotification *)
0x18016220a  mov     rcx, [rsp+228h]; this
0x180162212  test    eax, eax
0x180162214  jns     short loc_18016222A
0x180162216  mov     r9d, eax; char *
0x180162219  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180162220  mov     edx, 6F6h; void *
0x180162225  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18016222a  mov     [rsp+228h+SRWLock], 0
0x180162233  lea     rdx, [rsp+228h+var_1D0]; HSTRING *
0x180162238  lea     rcx, [rsp+228h+SRWLock]; newString
0x18016223d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180162242  mov     rcx, [rsp+228h]; this
0x18016224a  test    eax, eax
0x18016224c  jns     short loc_180162264
0x18016224e  mov     r9d, eax; char *
0x180162251  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180162258  mov     edx, 6F9h; void *
0x18016225d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180162262  jmp     short loc_180162275
0x180162264  lea     rcx, [r14+90h]
0x18016226b  lea     rdx, [rsp+228h+SRWLock]
0x180162270  call    ?erase@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@UIStartTileNotification@@@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@UIStartTileNotification@@@34@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<IStartTileNotification>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<IStartTileNotification>>>,0>>::erase(Microsoft::WRL::Wrappers::HString const &)
0x180162275  mov     bl, 1
0x180162277  mov     rcx, [rsp+228h+SRWLock]; string
0x18016227c  call    cs:__imp_WindowsDeleteString
0x180162282  jmp     loc_180162081
```
