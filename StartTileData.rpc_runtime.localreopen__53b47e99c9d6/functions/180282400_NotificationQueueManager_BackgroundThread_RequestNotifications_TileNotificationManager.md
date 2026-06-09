# NotificationQueueManager::BackgroundThread_RequestNotifications(TileNotificationManager *)

- ea: `0x180282400`
- end: `0x180282772`
- name: `?BackgroundThread_RequestNotifications@NotificationQueueManager@@AEAAJPEAVTileNotificationManager@@@Z`
- size: `882`
- prototype: `int(NotificationQueueManager *__hidden this, struct TileNotificationManager *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180284d90`

## callees

- `0x18000ce94`
- `0x1800137dc`
- `0x180015960`
- `0x18001aca4`
- `0x1800a2c4c`
- `0x1800c5b3c`
- `0x1800dd908`
- `0x180159390`
- `0x180161204`
- `0x1801b80a8`
- `0x1801d9a00`
- `0x18027f444`
- `0x180282400`
- `0x180283230`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282515`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282607`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282748`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282515`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282607`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180282748`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18028249f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18028249f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180282420`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180282420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802824d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802825d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180282711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802824d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802825d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180282711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180282571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180282628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18028268d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180282571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180282628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18028268d`

## string_xrefs

- `0x180282434`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1802824f7`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1802825bf`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180282663`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1802826f6`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NotificationQueueManager::BackgroundThread_RequestNotifications(
        NotificationQueueManager *this,
        struct TileNotificationManager *a2)
{
  int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // r15
  char v8; // r15
  int NotificationId; // eax
  const struct _FILETIME *v10; // rdx
  wil::filetime *v11; // rcx
  unsigned int v12; // ebx
  struct _FILETIME *v13; // r13
  unsigned __int64 v14; // rbx
  wil::filetime *v15; // rcx
  const struct _FILETIME *v16; // rdx
  int v17; // eax
  int v18; // eax
  struct tagSIZE v20; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int TileCycleEnabled; // eax
  int v23; // ebx
  bool v24; // zf
  char v25; // al
  int v26; // ebx
  char v27; // al
  int v28; // eax
  __int64 v29; // [rsp+20h] [rbp-50h] BYREF
  struct tagSIZE v30; // [rsp+28h] [rbp-48h] BYREF
  PSRWLOCK SRWLock[3]; // [rsp+30h] [rbp-40h] BYREF
  char v32; // [rsp+48h] [rbp-28h]
  __int128 v33; // [rsp+50h] [rbp-20h] BYREF
  __int128 v34; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v36; // [rsp+B0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+C0h] [rbp+50h] BYREF
  PSRWLOCK v38; // [rsp+C8h] [rbp+58h] BYREF

  v4 = *((_DWORD *)this + 18);
  if ( v4 == GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x2E3,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      v29);
  v5 = 0;
  v29 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(SRWLock, (char *)this + 448);
  v6 = *((_QWORD *)this + 45);
  v7 = 0;
  if ( v6 )
  {
    v38 = (PSRWLOCK)*((_QWORD *)this + 45);
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v38);
    v38 = 0;
    v5 = v6;
    v29 = v6;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v7 = v6;
  }
  if ( SRWLock[0] )
    ReleaseSRWLockShared(SRWLock[0]);
  if ( !v7 )
    goto LABEL_43;
  SRWLock[1] = (PSRWLOCK)this;
  SRWLock[2] = (PSRWLOCK)a2;
  v8 = 1;
  v32 = 1;
  string = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v38, (char *)this + 448);
  WindowsDeleteString(string);
  string = 0;
  NotificationId = TileNotificationManager::GetNotificationId(a2, &string);
  v12 = NotificationId;
  if ( NotificationId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30C,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)NotificationId,
      v29);
    if ( v38 )
      ReleaseSRWLockExclusive(v38);
    goto LABEL_19;
  }
  ++*((_DWORD *)this + 104);
  ++*((_DWORD *)a2 + 26);
  v13 = (struct _FILETIME *)((char *)a2 + 96);
  if ( *((_DWORD *)a2 + 26) == 1 )
  {
    *v13 = wil::filetime::get_system_time(v11);
  }
  else
  {
    v14 = wil::FileTime::ToInt64((struct TileNotificationManager *)((char *)a2 + 96), v10);
    *v13 = wil::filetime::get_system_time(v15);
    if ( wil::FileTime::ToInt64((struct TileNotificationManager *)((char *)a2 + 96), v16) - v14 >= 0x68E7780 )
    {
      *((_DWORD *)a2 + 26) = 1;
      SRWLock[0] = (PSRWLOCK)WindowsGetStringRawBuffer(string, 0);
      NotificationTelemetry::ThrottlingResetDueToTimeout<unsigned short const *>(SRWLock);
    }
  }
  if ( v38 )
    ReleaseSRWLockExclusive(v38);
  v36 = 0;
  v30 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, struct tagSIZE *))(**((_QWORD **)a2 + 9) + 96LL))(*((_QWORD *)a2 + 9), &v30);
  v12 = v17;
  if ( v17 >= 0 )
  {
    v20 = v30;
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a2 + 10), 0);
    TileCycleEnabled = NotificationQueueManager::GetTileCycleEnabled(
                         (NotificationQueueManager *)((char *)this + 8),
                         StringRawBuffer,
                         v20,
                         &v36);
    v23 = TileCycleEnabled;
    if ( TileCycleEnabled >= 0 || (v24 = !IsServerFailedError(TileCycleEnabled), v25 = 1, !v24) )
      v25 = 0;
    if ( v25 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x32F,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v23,
        v29);
    if ( v23 >= 0 )
    {
      v33 = 0;
      v34 = 0;
      *(_QWORD *)&v33 = WindowsGetStringRawBuffer(string, 0);
      DWORD2(v33) = v36 != 0 ? 5 : 1;
      DWORD2(v34) = 3;
      v26 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v5 + 48LL))(v5, &v33, 1);
      if ( (int)(v26 + 0x80000000) < 0 || v26 == -2147024809 || (v24 = !IsServerFailedError(v26), v27 = 1, !v24) )
        v27 = 0;
      if ( v27 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x33B,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)(unsigned int)v26,
          v29);
      if ( v26 >= 0 )
        v8 = 0;
    }
    WindowsDeleteString(string);
    string = 0;
    if ( v8 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v38, (char *)this + 448);
      --*((_DWORD *)this + 104);
      v28 = *((_DWORD *)a2 + 26);
      if ( v28 )
        *((_DWORD *)a2 + 26) = v28 - 1;
      if ( v38 )
        ReleaseSRWLockExclusive(v38);
    }
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x32D,
    (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
    (const char *)(unsigned int)v17,
    v29);
LABEL_19:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v38, (char *)this + 448);
  --*((_DWORD *)this + 104);
  v18 = *((_DWORD *)a2 + 26);
  if ( v18 )
    *((_DWORD *)a2 + 26) = v18 - 1;
  if ( v38 )
    ReleaseSRWLockExclusive(v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  return v12;
}

```

## disassembly

```asm
0x180282400  mov     [rsp-38h+arg_8], rbx
0x180282405  push    rbp
0x180282406  push    rsi
0x180282407  push    rdi
0x180282408  push    r12
0x18028240a  push    r13
0x18028240c  push    r14
0x18028240e  push    r15
0x180282410  mov     rbp, rsp
0x180282413  sub     rsp, 70h
0x180282417  mov     rsi, rdx
0x18028241a  mov     r14, rcx
0x18028241d  mov     ebx, [rcx+48h]
0x180282420  call    cs:__imp_GetCurrentThreadId
0x180282426  cmp     ebx, eax
0x180282428  jnz     short loc_180282446
0x18028242a  mov     rcx, [rbp+38h]; this
0x18028242e  mov     r9d, 800705A4h; char *
0x180282434  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028243b  mov     edx, 2E3h; void *
0x180282440  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180282446  xor     r13d, r13d
0x180282449  mov     edi, r13d
0x18028244c  mov     [rbp+var_50], r13
0x180282450  lea     r12, [r14+1C0h]
0x180282457  mov     rdx, r12
0x18028245a  lea     rcx, [rbp+SRWLock]
0x18028245e  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180282463  mov     rbx, [r14+168h]
0x18028246a  mov     r15d, r13d
0x18028246d  test    rbx, rbx
0x180282470  jz      short loc_180282496
0x180282472  mov     [rbp+arg_18], rbx
0x180282476  lea     rcx, [rbp+arg_18]
0x18028247a  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18028247f  mov     [rbp+arg_18], r13
0x180282483  mov     rdi, rbx
0x180282486  mov     [rbp+var_50], rbx
0x18028248a  lea     rcx, [rbp+arg_18]
0x18028248e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180282493  mov     r15, rbx
0x180282496  mov     rcx, [rbp+SRWLock]; SRWLock
0x18028249a  test    rcx, rcx
0x18028249d  jz      short loc_1802824A5
0x18028249f  call    cs:__imp_ReleaseSRWLockShared
0x1802824a5  test    r15, r15
0x1802824a8  jz      loc_18028274F
0x1802824ae  mov     [rbp+var_38], r14
0x1802824b2  mov     [rbp+var_30], rsi
0x1802824b6  mov     r15d, 1
0x1802824bc  mov     [rbp+var_28], r15b
0x1802824c0  mov     [rbp+string], r13
0x1802824c4  mov     rdx, r12
0x1802824c7  lea     rcx, [rbp+arg_18]
0x1802824cb  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1802824d0  mov     rcx, [rbp+string]; string
0x1802824d4  call    cs:__imp_WindowsDeleteString
0x1802824da  mov     [rbp+string], r13
0x1802824de  lea     rdx, [rbp+string]; HSTRING *
0x1802824e2  mov     rcx, rsi; this
0x1802824e5  call    ?GetNotificationId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetNotificationId(HSTRING__ * *)
0x1802824ea  mov     ebx, eax
0x1802824ec  test    eax, eax
0x1802824ee  jns     short loc_180282520
0x1802824f0  mov     rcx, [rbp+38h]; this
0x1802824f4  mov     r9d, eax; char *
0x1802824f7  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1802824fe  mov     edx, 30Ch; void *
0x180282503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282508  mov     rcx, [rbp+arg_18]; SRWLock
0x18028250c  test    rcx, rcx
0x18028250f  jz      loc_1802825D1
0x180282515  call    cs:__imp_ReleaseSRWLockExclusive
0x18028251b  jmp     loc_1802825D1
0x180282520  add     [r14+1A0h], r15d
0x180282527  add     [rsi+68h], r15d
0x18028252b  lea     r13, [rsi+60h]
0x18028252f  cmp     [rsi+68h], r15d
0x180282533  jnz     short loc_180282540
0x180282535  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x18028253a  mov     [r13+0], rax
0x18028253e  jmp     short loc_180282584
0x180282540  mov     rcx, r13; this
0x180282543  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x180282548  mov     rbx, rax
0x18028254b  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x180282550  mov     [r13+0], rax
0x180282554  mov     rcx, r13; this
0x180282557  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18028255c  sub     rax, rbx
0x18028255f  cmp     rax, 68E7780h
0x180282565  jb      short loc_180282584
0x180282567  mov     [rsi+68h], r15d
0x18028256b  xor     edx, edx; length
0x18028256d  mov     rcx, [rbp+string]; string
0x180282571  call    cs:__imp_WindowsGetStringRawBuffer
0x180282577  mov     [rbp+SRWLock], rax
0x18028257b  lea     rcx, [rbp+SRWLock]
0x18028257f  call    ??$ThrottlingResetDueToTimeout@PEBG@NotificationTelemetry@@SAX$$QEAPEBG@Z; NotificationTelemetry::ThrottlingResetDueToTimeout<ushort const *>(ushort const * &&)
0x180282584  mov     rcx, [rbp+arg_18]; SRWLock
0x180282588  xor     r13d, r13d
0x18028258b  test    rcx, rcx
0x18028258e  jz      short loc_180282596
0x180282590  call    cs:__imp_ReleaseSRWLockExclusive
0x180282596  mov     [rbp+arg_0], r13d
0x18028259a  mov     qword ptr [rbp+var_48.cx], r13
0x18028259e  mov     rcx, [rsi+48h]
0x1802825a2  mov     rax, [rcx]
0x1802825a5  lea     rdx, [rbp+var_48]
0x1802825a9  mov     rax, [rax+60h]
0x1802825ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802825b2  mov     ebx, eax
0x1802825b4  test    eax, eax
0x1802825b6  jns     short loc_18028261E
0x1802825b8  mov     rcx, [rbp+38h]; this
0x1802825bc  mov     r9d, eax; char *
0x1802825bf  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1802825c6  mov     edx, 32Dh; void *
0x1802825cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802825d0  nop
0x1802825d1  mov     rcx, [rbp+string]; string
0x1802825d5  call    cs:__imp_WindowsDeleteString
0x1802825db  mov     [rbp+string], r13
0x1802825df  mov     rdx, r12
0x1802825e2  lea     rcx, [rbp+arg_18]
0x1802825e6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1802825eb  dec     dword ptr [r14+1A0h]
0x1802825f2  mov     eax, [rsi+68h]
0x1802825f5  test    eax, eax
0x1802825f7  jz      short loc_1802825FE
0x1802825f9  dec     eax
0x1802825fb  mov     [rsi+68h], eax
0x1802825fe  mov     rcx, [rbp+arg_18]; SRWLock
0x180282602  test    rcx, rcx
0x180282605  jz      short loc_18028260E
0x180282607  call    cs:__imp_ReleaseSRWLockExclusive
0x18028260d  nop
0x18028260e  lea     rcx, [rbp+var_50]
0x180282612  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180282617  mov     eax, ebx
0x180282619  jmp     loc_18028275A
0x18028261e  mov     rbx, qword ptr [rbp+var_48.cx]
0x180282622  xor     edx, edx; length
0x180282624  mov     rcx, [rsi+50h]; string
0x180282628  call    cs:__imp_WindowsGetStringRawBuffer
0x18028262e  lea     rcx, [r14+8]; this
0x180282632  lea     r9, [rbp+arg_0]; int *
0x180282636  mov     r8, rbx; struct tagSIZE
0x180282639  mov     rdx, rax; unsigned __int16 *
0x18028263c  call    ?GetTileCycleEnabled@NotificationQueueManager@@UEAAJPEBGUtagSIZE@@PEAH@Z; NotificationQueueManager::GetTileCycleEnabled(ushort const *,tagSIZE,int *)
0x180282641  mov     ebx, eax
0x180282643  test    eax, eax
0x180282645  jns     short loc_180282655
0x180282647  mov     ecx, eax; int
0x180282649  call    ?IsServerFailedError@@YA_NJ@Z; IsServerFailedError(long)
0x18028264e  test    al, al
0x180282650  mov     al, r15b
0x180282653  jz      short loc_180282658
0x180282655  mov     al, r13b
0x180282658  mov     rcx, [rbp+38h]; this
0x18028265c  test    al, al
0x18028265e  jz      short loc_180282674
0x180282660  mov     r9d, ebx; char *
0x180282663  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18028266a  mov     edx, 32Fh; void *
0x18028266f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180282674  test    ebx, ebx
0x180282676  js      loc_18028270D
0x18028267c  xorps   xmm0, xmm0
0x18028267f  movups  [rbp+var_20], xmm0
0x180282683  movups  [rbp+var_10], xmm0
0x180282687  xor     edx, edx; length
0x180282689  mov     rcx, [rbp+string]; string
0x18028268d  call    cs:__imp_WindowsGetStringRawBuffer
0x180282693  mov     qword ptr [rbp+var_20], rax
0x180282697  mov     eax, [rbp+arg_0]
0x18028269a  neg     eax
0x18028269c  sbb     ecx, ecx
0x18028269e  and     ecx, 4
0x1802826a1  add     ecx, r15d
0x1802826a4  mov     dword ptr [rbp+var_20+8], ecx
0x1802826a7  mov     dword ptr [rbp+var_10+8], 3
0x1802826ae  mov     rax, [rdi]
0x1802826b1  mov     r8d, r15d
0x1802826b4  lea     rdx, [rbp+var_20]
0x1802826b8  mov     rcx, rdi
0x1802826bb  mov     rax, [rax+30h]
0x1802826bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802826c4  mov     ebx, eax
0x1802826c6  mov     eax, 80000000h
0x1802826cb  lea     ecx, [rbx+rax]
0x1802826ce  test    eax, ecx
0x1802826d0  jnz     short loc_1802826E8
0x1802826d2  cmp     ebx, 80070057h
0x1802826d8  jz      short loc_1802826E8
0x1802826da  mov     ecx, ebx; int
0x1802826dc  call    ?IsServerFailedError@@YA_NJ@Z; IsServerFailedError(long)
0x1802826e1  test    al, al
0x1802826e3  mov     al, r15b
0x1802826e6  jz      short loc_1802826EB
0x1802826e8  mov     al, r13b
0x1802826eb  mov     rcx, [rbp+38h]; this
0x1802826ef  test    al, al
0x1802826f1  jz      short loc_180282707
0x1802826f3  mov     r9d, ebx; char *
0x1802826f6  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1802826fd  mov     edx, 33Bh; void *
0x180282702  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180282707  test    ebx, ebx
0x180282709  cmovns  r15d, r13d
0x18028270d  mov     rcx, [rbp+string]; string
0x180282711  call    cs:__imp_WindowsDeleteString
0x180282717  mov     [rbp+string], r13
0x18028271b  test    r15b, r15b
0x18028271e  jz      short loc_18028274F
0x180282720  mov     rdx, r12
0x180282723  lea     rcx, [rbp+arg_18]
0x180282727  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18028272c  dec     dword ptr [r14+1A0h]
0x180282733  mov     eax, [rsi+68h]
0x180282736  test    eax, eax
0x180282738  jz      short loc_18028273F
0x18028273a  dec     eax
0x18028273c  mov     [rsi+68h], eax
0x18028273f  mov     rcx, [rbp+arg_18]; SRWLock
0x180282743  test    rcx, rcx
0x180282746  jz      short loc_18028274F
0x180282748  call    cs:__imp_ReleaseSRWLockExclusive
0x18028274e  nop
0x18028274f  lea     rcx, [rbp+var_50]
0x180282753  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180282758  xor     eax, eax
0x18028275a  mov     rbx, [rsp+70h+arg_8]
0x180282762  add     rsp, 70h
0x180282766  pop     r15
0x180282768  pop     r14
0x18028276a  pop     r13
0x18028276c  pop     r12
0x18028276e  pop     rdi
0x18028276f  pop     rsi
0x180282770  pop     rbp
0x180282771  retn
```
