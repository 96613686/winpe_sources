# NotificationQueueManager::SetTileNotificationEnabled(IUnknown *,int)

- ea: `0x1801653b0`
- end: `0x180165841`
- name: `?SetTileNotificationEnabled@NotificationQueueManager@@UEAAJPEAUIUnknown@@H@Z`
- size: `1169`
- prototype: `__int64 __fastcall(NotificationQueueManager *__hidden this, struct IUnknown *, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ce94`
- `0x180015960`
- `0x18001aca4`
- `0x18003d040`
- `0x1800dd908`
- `0x180159390`
- `0x180161204`
- `0x1801640ac`
- `0x180164ea0`
- `0x1801653b0`
- `0x180165a18`
- `0x180165ac0`
- `0x18020c05c`
- `0x18020c0c4`
- `0x18027eb04`
- `0x1802808e8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18016565e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18016565e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801653ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801653ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801654ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016555c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801657b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801657c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801657f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165805`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801654ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016555c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801657b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801657c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801657f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165805`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1801656a5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1801656a5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18016572b`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18016572b`

## string_xrefs

- `0x1801653e8`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180165443`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801654b4`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180165532`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801655e9`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180165761`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x18016578e`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NotificationQueueManager::SetTileNotificationEnabled(
        NotificationQueueManager *this,
        struct IUnknown *a2,
        int a3)
{
  NotificationQueueManager *v6; // r14
  __int64 (*QueryInterface)(void); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  int RoamedTileProperties; // eax
  __int64 v21; // rdx
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  struct TileNotificationManager *v24; // rbx
  __int64 v25; // rdi
  unsigned int v26; // esi
  __int64 *v27; // rax
  __int64 v28; // rdi
  int v29; // esi
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // [rsp+20h] [rbp-78h]
  int v33; // [rsp+20h] [rbp-78h]
  HSTRING v34; // [rsp+30h] [rbp-68h] BYREF
  struct WindowsInternal::Shell::CDSProperties::ICDSRoamedTileProperties *v35; // [rsp+38h] [rbp-60h] BYREF
  HSTRING v36; // [rsp+40h] [rbp-58h] BYREF
  __int64 v37; // [rsp+48h] [rbp-50h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v39[2]; // [rsp+58h] [rbp-40h] BYREF
  int v40; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HSTRING string; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v43; // [rsp+B8h] [rbp+20h] BYREF

  v6 = (NotificationQueueManager *)((char *)this - 8);
  if ( *((_DWORD *)this + 16) != GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      v32);
  v43 = 0;
  QueryInterface = (__int64 (*)(void))a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  try
  {
    v8 = QueryInterface();
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v8,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      return v9;
    }
    string = 0;
    v12 = v43;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v14,
        v32);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      return v15;
    }
    v34 = 0;
    v16 = v43;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 64LL);
    WindowsDeleteString(0);
    v34 = 0;
    v18 = v17(v16, &v34);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v18,
        v32);
      WindowsDeleteString(v34);
      v34 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      return v19;
    }
    if ( !*((_QWORD *)this + 41) )
      goto LABEL_17;
    v35 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    RoamedTileProperties = NotificationQueueManager::GetRoamedTileProperties(
                             (NotificationQueueManager *)((char *)this - 8),
                             string,
                             &v35);
    v22 = retaddr;
    if ( RoamedTileProperties >= 0 )
    {
      LOBYTE(v21) = a3 == 0;
      RoamedTileProperties = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::CDSProperties::ICDSRoamedTileProperties *, __int64))(*(_QWORD *)v35 + 104LL))(
                               v35,
                               v21);
      v22 = retaddr;
      if ( RoamedTileProperties >= 0 )
      {
LABEL_16:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
LABEL_17:
        v24 = 0;
        v35 = 0;
        Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 440);
        v36 = v34;
        std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,std::unique_ptr<TileExpiryStatus>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,std::unique_ptr<TileExpiryStatus>>>,0>>::find<HSTRING__ *,wil::hstring_insensitive_less,0>(
          (char *)this + 72,
          &v37,
          &v36);
        if ( v37 != *((_QWORD *)this + 9) )
        {
          Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(&v35, v37 + 40);
          v24 = v35;
        }
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        if ( !v24 )
          goto LABEL_33;
        if ( dword_1804DC7B8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                           + (unsigned int)tls_index)
                                         + 12LL) )
        {
          Init_thread_header(&dword_1804DC7B8);
          if ( dword_1804DC7B8 == -1 )
          {
            dword_1804DC7BC = SHTaskPoolGetUniqueContext();
            Init_thread_footer(&dword_1804DC7B8);
          }
        }
        v25 = *((_QWORD *)this + 54);
        v39[0] = v43;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v39);
        v39[1] = v25;
        v40 = a3;
        v26 = dword_1804DC7BC;
        v27 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_bc5d5c72ea9e3bebe6d538dd17ccdb99_____lambda_bc5d5c72ea9e3bebe6d538dd17ccdb99___(
                           &v36,
                           v39);
        v28 = *v27;
        *v27 = 0;
        if ( v36 )
        {
          v36 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ISelectionDataParser>::Release();
        }
        v29 = SHTaskPoolQueueTask(3, 2, v26, 0, v28, 0);
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1AB,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v29,
            v33);
        v30 = NotificationQueueManager::RequestNotifications(v6, v24);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AF,
            (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
            (const char *)(unsigned int)v30,
            v33);
          Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v35);
          WindowsDeleteString(v34);
          v34 = 0;
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
          return v31;
        }
        else
        {
LABEL_33:
          Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v35);
          WindowsDeleteString(v34);
          v34 = 0;
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
          return 0;
        }
      }
      v23 = 403;
    }
    else
    {
      v23 = 399;
    }
    wil::details::in1diag3::_Log_Hr(
      v22,
      (void *)v23,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)RoamedTileProperties,
      v32);
    goto LABEL_16;
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1B4,
                        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificatio"
                                      "nqueuemanager.cpp",
                        v10);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x1801653b0  mov     [rsp+arg_8], rbx
0x1801653b5  push    rsi
0x1801653b6  push    rdi
0x1801653b7  push    r12
0x1801653b9  push    r14
0x1801653bb  push    r15
0x1801653bd  sub     rsp, 70h
0x1801653c1  mov     r15d, r8d
0x1801653c4  mov     rdi, rdx
0x1801653c7  mov     rsi, rcx
0x1801653ca  call    cs:__imp_GetCurrentThreadId
0x1801653d0  lea     r14, [rsi-8]
0x1801653d4  cmp     [r14+48h], eax
0x1801653d8  jz      short loc_1801653FA
0x1801653da  mov     rcx, [rsp+98h]; this
0x1801653e2  mov     r9d, 800705A4h; char *
0x1801653e8  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801653ef  mov     edx, 183h; void *
0x1801653f4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801653fa  xor     r12d, r12d
0x1801653fd  mov     [rsp+98h+arg_18], r12
0x180165405  mov     rax, [rdi]
0x180165408  mov     rbx, [rax]
0x18016540b  lea     rcx, [rsp+98h+arg_18]
0x180165413  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165418  lea     r8, [rsp+98h+arg_18]
0x180165420  lea     rdx, _GUID_d3653510_4fff_4bfa_905b_ea038b142fa5
0x180165427  mov     rcx, rdi
0x18016542a  mov     rax, rbx
0x18016542d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165432  mov     ebx, eax
0x180165434  test    eax, eax
0x180165436  jns     short loc_180165469
0x180165438  mov     rcx, [rsp+98h]; this
0x180165440  mov     r9d, eax; char *
0x180165443  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18016544a  mov     edx, 186h; void *
0x18016544f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165454  nop
0x180165455  lea     rcx, [rsp+98h+arg_18]
0x18016545d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165462  mov     eax, ebx
0x180165464  jmp     loc_18016582B
0x180165469  mov     [rsp+98h+string], r12
0x180165471  mov     rdi, [rsp+98h+arg_18]
0x180165479  mov     rax, [rdi]
0x18016547c  mov     rbx, [rax+38h]
0x180165480  xor     ecx, ecx; string
0x180165482  call    cs:__imp_WindowsDeleteString
0x180165488  mov     [rsp+98h+string], r12
0x180165490  lea     rdx, [rsp+98h+string]
0x180165498  mov     rcx, rdi
0x18016549b  mov     rax, rbx
0x18016549e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801654a3  mov     ebx, eax
0x1801654a5  test    eax, eax
0x1801654a7  jns     short loc_1801654F0
0x1801654a9  mov     rcx, [rsp+98h]; this
0x1801654b1  mov     r9d, eax; char *
0x1801654b4  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801654bb  mov     edx, 188h; void *
0x1801654c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801654c5  nop
0x1801654c6  mov     rcx, [rsp+98h+string]; string
0x1801654ce  call    cs:__imp_WindowsDeleteString
0x1801654d4  mov     [rsp+98h+string], r12
0x1801654dc  lea     rcx, [rsp+98h+arg_18]
0x1801654e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801654e9  mov     eax, ebx
0x1801654eb  jmp     loc_18016582B
0x1801654f0  mov     [rsp+98h+var_68], r12
0x1801654f5  mov     rdi, [rsp+98h+arg_18]
0x1801654fd  mov     rax, [rdi]
0x180165500  mov     rbx, [rax+40h]
0x180165504  xor     ecx, ecx; string
0x180165506  call    cs:__imp_WindowsDeleteString
0x18016550c  mov     [rsp+98h+var_68], r12
0x180165511  lea     rdx, [rsp+98h+var_68]
0x180165516  mov     rcx, rdi
0x180165519  mov     rax, rbx
0x18016551c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165521  mov     ebx, eax
0x180165523  test    eax, eax
0x180165525  jns     short loc_18016557E
0x180165527  mov     rcx, [rsp+98h]; this
0x18016552f  mov     r9d, eax; char *
0x180165532  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180165539  mov     edx, 18Ah; void *
0x18016553e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165543  nop
0x180165544  mov     rcx, [rsp+98h+var_68]; string
0x180165549  call    cs:__imp_WindowsDeleteString
0x18016554f  mov     [rsp+98h+var_68], r12
0x180165554  mov     rcx, [rsp+98h+string]; string
0x18016555c  call    cs:__imp_WindowsDeleteString
0x180165562  mov     [rsp+98h+string], r12
0x18016556a  lea     rcx, [rsp+98h+arg_18]
0x180165572  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165577  mov     eax, ebx
0x180165579  jmp     loc_18016582B
0x18016557e  cmp     [rsi+148h], r12
0x180165585  jz      short loc_180165600
0x180165587  mov     [rsp+98h+var_60], r12
0x18016558c  lea     rcx, [rsp+98h+var_60]
0x180165591  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165596  lea     r8, [rsp+98h+var_60]; struct WindowsInternal::Shell::CDSProperties::ICDSRoamedTileProperties **
0x18016559b  mov     rdx, [rsp+98h+string]; HSTRING
0x1801655a3  mov     rcx, r14; this
0x1801655a6  call    ?GetRoamedTileProperties@NotificationQueueManager@@AEAAJPEAUHSTRING__@@PEAPEAUICDSRoamedTileProperties@CDSProperties@Shell@WindowsInternal@@@Z; NotificationQueueManager::GetRoamedTileProperties(HSTRING__ *,WindowsInternal::Shell::CDSProperties::ICDSRoamedTileProperties * *)
0x1801655ab  mov     rcx, [rsp+98h]
0x1801655b3  test    eax, eax
0x1801655b5  jns     short loc_1801655BE
0x1801655b7  mov     edx, 18Fh
0x1801655bc  jmp     short loc_1801655E6
0x1801655be  mov     rcx, [rsp+98h+var_60]
0x1801655c3  mov     rax, [rcx]
0x1801655c6  test    r15d, r15d
0x1801655c9  setz    dl
0x1801655cc  mov     rax, [rax+68h]
0x1801655d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801655d5  mov     rcx, [rsp+98h]; this
0x1801655dd  test    eax, eax
0x1801655df  jns     short loc_1801655F6
0x1801655e1  mov     edx, 193h; void *
0x1801655e6  mov     r9d, eax; char *
0x1801655e9  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801655f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801655f5  nop
0x1801655f6  lea     rcx, [rsp+98h+var_60]
0x1801655fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165600  mov     rbx, r12
0x180165603  mov     [rsp+98h+var_60], rbx
0x180165608  lea     rdx, [rsi+1B8h]
0x18016560f  lea     rcx, [rsp+98h+SRWLock]
0x180165614  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180165619  mov     rax, [rsp+98h+var_68]
0x18016561e  mov     [rsp+98h+var_58], rax
0x180165623  lea     r8, [rsp+98h+var_58]
0x180165628  lea     rdx, [rsp+98h+var_50]
0x18016562d  lea     rcx, [rsi+48h]
0x180165631  call    ??$find@PEAUHSTRING__@@Uhstring_insensitive_less@wil@@$0A@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$unique_ptr@VTileExpiryStatus@@U?$default_delete@VTileExpiryStatus@@@std@@@std@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$unique_ptr@VTileExpiryStatus@@U?$default_delete@VTileExpiryStatus@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$unique_ptr@VTileExpiryStatus@@U?$default_delete@VTileExpiryStatus@@@std@@@std@@@std@@@std@@@std@@@1@AEBQEAUHSTRING__@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,std::unique_ptr<TileExpiryStatus>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,std::unique_ptr<TileExpiryStatus>>>,0>>::find<HSTRING__ *,wil::hstring_insensitive_less,0>(HSTRING__ * const &)
0x180165636  mov     rdx, [rsp+98h+var_50]
0x18016563b  cmp     rdx, [rsi+48h]
0x18016563f  jz      short loc_180165654
0x180165641  add     rdx, 28h ; '('
0x180165645  lea     rcx, [rsp+98h+var_60]
0x18016564a  call    ??4?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<TileNotificationManager>::operator=(Microsoft::WRL::ComPtr<TileNotificationManager> const &)
0x18016564f  mov     rbx, [rsp+98h+var_60]
0x180165654  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x180165659  test    rcx, rcx
0x18016565c  jz      short loc_180165664
0x18016565e  call    cs:__imp_ReleaseSRWLockShared
0x180165664  test    rbx, rbx
0x180165667  jz      loc_1801657E2
0x18016566d  mov     ecx, cs:_tls_index
0x180165673  mov     rax, gs:58h
0x18016567c  mov     edx, 0Ch
0x180165681  mov     rax, [rax+rcx*8]
0x180165685  mov     eax, [rdx+rax]
0x180165688  cmp     cs:dword_1804DC7B8, eax
0x18016568e  jle     short loc_1801656BD
0x180165690  lea     rcx, dword_1804DC7B8
0x180165697  call    _Init_thread_header
0x18016569c  cmp     cs:dword_1804DC7B8, 0FFFFFFFFh
0x1801656a3  jnz     short loc_1801656BD
0x1801656a5  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1801656ab  mov     cs:dword_1804DC7BC, eax
0x1801656b1  lea     rcx, dword_1804DC7B8
0x1801656b8  call    _Init_thread_footer
0x1801656bd  mov     rdi, [rsi+1B0h]
0x1801656c4  mov     rax, [rsp+98h+arg_18]
0x1801656cc  mov     [rsp+98h+var_40], rax
0x1801656d1  lea     rcx, [rsp+98h+var_40]
0x1801656d6  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1801656db  mov     [rsp+98h+var_38], rdi
0x1801656e0  mov     [rsp+98h+var_30], r15d
0x1801656e5  mov     esi, cs:dword_1804DC7BC
0x1801656eb  lea     rdx, [rsp+98h+var_40]
0x1801656f0  lea     rcx, [rsp+98h+var_58]
0x1801656f5  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_bc5d5c72ea9e3bebe6d538dd17ccdb99_____lambda_bc5d5c72ea9e3bebe6d538dd17ccdb99___
0x1801656fa  mov     rdi, [rax]
0x1801656fd  mov     [rax], r12
0x180165700  mov     rcx, [rsp+98h+var_58]
0x180165705  test    rcx, rcx
0x180165708  jz      short loc_180165714
0x18016570a  mov     [rsp+98h+var_58], r12
0x18016570f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISelectionDataParser@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ISelectionDataParser>::Release(void)
0x180165714  mov     [rsp+98h+var_70], r12
0x180165719  mov     qword ptr [rsp+98h+var_78], rdi; int
0x18016571e  xor     r9d, r9d
0x180165721  mov     r8d, esi
0x180165724  lea     edx, [r9+2]
0x180165728  lea     ecx, [rdx+1]
0x18016572b  call    cs:__imp_SHTaskPoolQueueTask
0x180165731  mov     esi, eax
0x180165733  test    rdi, rdi
0x180165736  jz      short loc_180165748
0x180165738  mov     rdx, [rdi]
0x18016573b  mov     rcx, rdi
0x18016573e  mov     rax, [rdx+10h]
0x180165742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165747  nop
0x180165748  lea     rcx, [rsp+98h+var_40]
0x18016574d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165752  mov     rcx, [rsp+98h]; this
0x18016575a  test    esi, esi
0x18016575c  jns     short loc_180165772
0x18016575e  mov     r9d, esi; char *
0x180165761  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180165768  mov     edx, 1ABh; void *
0x18016576d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180165772  mov     rdx, rbx; struct TileNotificationManager *
0x180165775  mov     rcx, r14; this
0x180165778  call    ?RequestNotifications@NotificationQueueManager@@QEAAJPEAVTileNotificationManager@@@Z; NotificationQueueManager::RequestNotifications(TileNotificationManager *)
0x18016577d  mov     ebx, eax
0x18016577f  test    eax, eax
0x180165781  jns     short loc_1801657E2
0x180165783  mov     rcx, [rsp+98h]; this
0x18016578b  mov     r9d, eax; char *
0x18016578e  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180165795  mov     edx, 1AFh; void *
0x18016579a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016579f  nop
0x1801657a0  lea     rcx, [rsp+98h+var_60]
0x1801657a5  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801657aa  nop
0x1801657ab  mov     rcx, [rsp+98h+var_68]; string
0x1801657b0  call    cs:__imp_WindowsDeleteString
0x1801657b6  mov     [rsp+98h+var_68], r12
0x1801657bb  mov     rcx, [rsp+98h+string]; string
0x1801657c3  call    cs:__imp_WindowsDeleteString
0x1801657c9  mov     [rsp+98h+string], r12
0x1801657d1  lea     rcx, [rsp+98h+arg_18]
0x1801657d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801657de  mov     eax, ebx
0x1801657e0  jmp     short loc_18016582B
0x1801657e2  lea     rcx, [rsp+98h+var_60]
0x1801657e7  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801657ec  nop
0x1801657ed  mov     rcx, [rsp+98h+var_68]; string
0x1801657f2  call    cs:__imp_WindowsDeleteString
0x1801657f8  mov     [rsp+98h+var_68], r12
0x1801657fd  mov     rcx, [rsp+98h+string]; string
0x180165805  call    cs:__imp_WindowsDeleteString
0x18016580b  mov     [rsp+98h+string], r12
0x180165813  lea     rcx, [rsp+98h+arg_18]
0x18016581b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180165820  xor     eax, eax
0x180165822  jmp     short loc_18016582B
0x180165824  mov     eax, dword ptr [rsp+98h+string]
0x18016582b  mov     rbx, [rsp+98h+arg_8]
0x180165833  add     rsp, 70h
0x180165837  pop     r15
0x180165839  pop     r14
0x18016583b  pop     r12
0x18016583d  pop     rdi
0x18016583e  pop     rsi
0x18016583f  retn
```
