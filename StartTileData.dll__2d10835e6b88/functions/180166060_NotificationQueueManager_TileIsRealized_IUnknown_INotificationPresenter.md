# NotificationQueueManager::TileIsRealized(IUnknown *,INotificationPresenter *)

- ea: `0x180166060`
- end: `0x180166449`
- name: `?TileIsRealized@NotificationQueueManager@@UEAAJPEAUIUnknown@@PEAUINotificationPresenter@@@Z`
- size: `1001`
- prototype: `__int64 __fastcall(NotificationQueueManager *__hidden this, struct IUnknown *, struct INotificationPresenter *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800c5b3c`
- `0x180159390`
- `0x1801640ac`
- `0x180164394`
- `0x180166060`
- `0x1801d9a00`
- `0x18027ee9c`
- `0x18027f664`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180166385`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180166385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18016607c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18016607c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801662d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180166317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801663c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801663fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801662d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180166317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801663c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801663fe`

## string_xrefs

- `0x18016609a`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801660f9`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180166162`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801661c8`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180166287`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x180166300`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`
- `0x1801663ac`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NotificationQueueManager::TileIsRealized(
        NotificationQueueManager *this,
        struct IUnknown *a2,
        struct INotificationPresenter *a3)
{
  int (*QueryInterface)(void); // rbx
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  TileNotificationManager *v16; // rbx
  int NotificationId; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-88h]
  int v22; // [rsp+20h] [rbp-88h]
  HSTRING string; // [rsp+40h] [rbp-68h] BYREF
  struct TileNotificationManager *v24; // [rsp+48h] [rbp-60h] BYREF
  __int64 v25; // [rsp+50h] [rbp-58h] BYREF
  __int64 v26; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp-48h] BYREF
  PSRWLOCK SRWLock[7]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v30; // [rsp+B0h] [rbp+8h] BYREF
  struct IUnknown *v31; // [rsp+B8h] [rbp+10h] BYREF
  struct INotificationPresenter *v32; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v33; // [rsp+C8h] [rbp+20h] BYREF

  v32 = a3;
  v31 = a2;
  if ( *((_DWORD *)this + 16) != GetCurrentThreadId() )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)0x800705A4LL,
      v21);
  v33 = 0;
  QueryInterface = (int (*)(void))a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  try
  {
    if ( QueryInterface() < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)0x80070057LL,
        v21);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      return 2147942487LL;
    }
    v25 = 0;
    v8 = v33;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    v10 = v9(v8, &v25);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v10,
        v21);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      return v11;
    }
    v30 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 48LL))(v25, &v30);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
        (const char *)(unsigned int)v12,
        v21);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      return v13;
    }
    if ( v30 == 1 )
    {
      v24 = 0;
      v26 = *((_QWORD *)this + 41);
      v27[0] = *((_QWORD *)this + 42);
      SRWLock[0] = (PSRWLOCK)((char *)this - 8);
      Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v24);
      v14 = Microsoft::WRL::Details::MakeAndInitialize<TileNotificationManager,TileNotificationManager,unsigned __int64 &,NotificationQueueManager *,IImageQueueManager *,IUnknown * &,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesBatched *,INotificationPresenter * &>(
              (unsigned int)&v24,
              (int)this + 432,
              (unsigned int)SRWLock,
              (unsigned int)v27,
              (__int64)&v31,
              (__int64)&v26,
              (__int64)&v32);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)(unsigned int)v14,
          v22);
        Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        return v15;
      }
      v16 = v24;
      WindowsDeleteString(0);
      string = 0;
      NotificationId = TileNotificationManager::GetNotificationId(v16, &string);
      v18 = NotificationId;
      if ( NotificationId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)(unsigned int)NotificationId,
          v22);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        return v18;
      }
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 440);
      std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager> &>(
        (char *)this + 72,
        v27,
        &string,
        &v24);
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
      v19 = NotificationQueueManager::ProcessNotificationsForTile(
              (NotificationQueueManager *)((char *)this - 8),
              v24,
              1);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x106,
          (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
          (const char *)(unsigned int)v19,
          v22);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        return v20;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(&v24);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x10B,
                           (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notifica"
                                         "tionqueuemanager.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180166060  mov     [rsp+arg_10], r8
0x180166065  mov     [rsp+arg_8], rdx
0x18016606a  push    rbx
0x18016606b  push    rsi
0x18016606c  push    rdi
0x18016606d  push    r14
0x18016606f  sub     rsp, 88h
0x180166076  mov     rdi, rdx
0x180166079  mov     rsi, rcx
0x18016607c  call    cs:__imp_GetCurrentThreadId
0x180166082  lea     r14, [rsi-8]
0x180166086  cmp     [r14+48h], eax
0x18016608a  jz      short loc_1801660AC
0x18016608c  mov     rcx, [rsp+0A8h]; this
0x180166094  mov     r9d, 800705A4h; char *
0x18016609a  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801660a1  mov     edx, 0ECh; void *
0x1801660a6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1801660ac  mov     [rsp+0A8h+arg_18], 0
0x1801660b8  mov     rax, [rdi]
0x1801660bb  mov     rbx, [rax]
0x1801660be  lea     rcx, [rsp+0A8h+arg_18]
0x1801660c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801660cb  lea     r8, [rsp+0A8h+arg_18]
0x1801660d3  lea     rdx, _GUID_65b4e03e_a32e_40cf_8bab_b2d9c5287307
0x1801660da  mov     rcx, rdi
0x1801660dd  mov     rax, rbx
0x1801660e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801660e5  test    eax, eax
0x1801660e7  jns     short loc_18016611F
0x1801660e9  mov     rcx, [rsp+0A8h]; this
0x1801660f1  mov     ebx, 80070057h
0x1801660f6  mov     r9d, ebx; char *
0x1801660f9  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180166100  mov     edx, 0EFh; void *
0x180166105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016610a  nop
0x18016610b  lea     rcx, [rsp+0A8h+arg_18]
0x180166113  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166118  mov     eax, ebx
0x18016611a  jmp     loc_18016643B
0x18016611f  mov     [rsp+0A8h+var_58], 0
0x180166128  mov     rdi, [rsp+0A8h+arg_18]
0x180166130  mov     rax, [rdi]
0x180166133  mov     rbx, [rax+30h]
0x180166137  lea     rcx, [rsp+0A8h+var_58]
0x18016613c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166141  lea     rdx, [rsp+0A8h+var_58]
0x180166146  mov     rcx, rdi
0x180166149  mov     rax, rbx
0x18016614c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166151  mov     ebx, eax
0x180166153  test    eax, eax
0x180166155  jns     short loc_180166193
0x180166157  mov     rcx, [rsp+0A8h]; this
0x18016615f  mov     r9d, eax; char *
0x180166162  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180166169  mov     edx, 0F2h; void *
0x18016616e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180166173  nop
0x180166174  lea     rcx, [rsp+0A8h+var_58]
0x180166179  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016617e  nop
0x18016617f  lea     rcx, [rsp+0A8h+arg_18]
0x180166187  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016618c  mov     eax, ebx
0x18016618e  jmp     loc_18016643B
0x180166193  mov     [rsp+0A8h+arg_0], 0
0x18016619e  mov     rcx, [rsp+0A8h+var_58]
0x1801661a3  mov     rax, [rcx]
0x1801661a6  lea     rdx, [rsp+0A8h+arg_0]
0x1801661ae  mov     rax, [rax+30h]
0x1801661b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801661b7  mov     ebx, eax
0x1801661b9  test    eax, eax
0x1801661bb  jns     short loc_1801661F9
0x1801661bd  mov     rcx, [rsp+0A8h]; this
0x1801661c5  mov     r9d, eax; char *
0x1801661c8  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801661cf  mov     edx, 0F5h; void *
0x1801661d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801661d9  nop
0x1801661da  lea     rcx, [rsp+0A8h+var_58]
0x1801661df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801661e4  nop
0x1801661e5  lea     rcx, [rsp+0A8h+arg_18]
0x1801661ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801661f2  mov     eax, ebx
0x1801661f4  jmp     loc_18016643B
0x1801661f9  cmp     [rsp+0A8h+arg_0], 1
0x180166201  jnz     loc_180166418
0x180166207  mov     [rsp+0A8h+var_60], 0
0x180166210  mov     rax, [rsi+148h]
0x180166217  mov     [rsp+0A8h+var_50], rax
0x18016621c  mov     rax, [rsi+150h]
0x180166223  mov     [rsp+0A8h+var_48], rax
0x180166228  mov     [rsp+0A8h+SRWLock], r14
0x18016622d  lea     rcx, [rsp+0A8h+var_60]
0x180166232  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180166237  lea     rdx, [rsi+1B0h]
0x18016623e  lea     rax, [rsp+0A8h+arg_10]
0x180166246  mov     [rsp+0A8h+var_78], rax
0x18016624b  lea     rax, [rsp+0A8h+var_50]
0x180166250  mov     [rsp+0A8h+var_80], rax
0x180166255  lea     rax, [rsp+0A8h+arg_8]
0x18016625d  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180166262  lea     r9, [rsp+0A8h+var_48]
0x180166267  lea     r8, [rsp+0A8h+SRWLock]
0x18016626c  lea     rcx, [rsp+0A8h+var_60]
0x180166271  call    ??$MakeAndInitialize@VTileNotificationManager@@V1@AEA_KPEAVNotificationQueueManager@@PEAUIImageQueueManager@@AEAPEAUIUnknown@@PEAUICDSTilePropertiesBatched@CDSProperties@Shell@WindowsInternal@@AEAPEAUINotificationPresenter@@@Details@WRL@Microsoft@@YAJPEAPEAVTileNotificationManager@@AEA_K$$QEAPEAVNotificationQueueManager@@$$QEAPEAUIImageQueueManager@@AEAPEAUIUnknown@@$$QEAPEAUICDSTilePropertiesBatched@CDSProperties@Shell@WindowsInternal@@AEAPEAUINotificationPresenter@@@Z; Microsoft::WRL::Details::MakeAndInitialize<TileNotificationManager,TileNotificationManager,unsigned __int64 &,NotificationQueueManager *,IImageQueueManager *,IUnknown * &,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesBatched *,INotificationPresenter * &>(TileNotificationManager * *,unsigned __int64 &,NotificationQueueManager * &&,IImageQueueManager * &&,IUnknown * &,WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesBatched * &&,INotificationPresenter * &)
0x180166276  mov     ebx, eax
0x180166278  test    eax, eax
0x18016627a  jns     short loc_1801662C3
0x18016627c  mov     rcx, [rsp+0A8h]; this
0x180166284  mov     r9d, eax; char *
0x180166287  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x18016628e  mov     edx, 0FAh; void *
0x180166293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180166298  nop
0x180166299  lea     rcx, [rsp+0A8h+var_60]
0x18016629e  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801662a3  nop
0x1801662a4  lea     rcx, [rsp+0A8h+var_58]
0x1801662a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801662ae  nop
0x1801662af  lea     rcx, [rsp+0A8h+arg_18]
0x1801662b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801662bc  mov     eax, ebx
0x1801662be  jmp     loc_18016643B
0x1801662c3  mov     [rsp+0A8h+string], 0
0x1801662cc  mov     rbx, [rsp+0A8h+var_60]
0x1801662d1  xor     ecx, ecx; string
0x1801662d3  call    cs:__imp_WindowsDeleteString
0x1801662d9  mov     [rsp+0A8h+string], 0
0x1801662e2  lea     rdx, [rsp+0A8h+string]; HSTRING *
0x1801662e7  mov     rcx, rbx; this
0x1801662ea  call    ?GetNotificationId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetNotificationId(HSTRING__ * *)
0x1801662ef  mov     ebx, eax
0x1801662f1  test    eax, eax
0x1801662f3  jns     short loc_180166350
0x1801662f5  mov     rcx, [rsp+0A8h]; this
0x1801662fd  mov     r9d, eax; char *
0x180166300  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180166307  mov     edx, 0FDh; void *
0x18016630c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180166311  nop
0x180166312  mov     rcx, [rsp+0A8h+string]; string
0x180166317  call    cs:__imp_WindowsDeleteString
0x18016631d  mov     [rsp+0A8h+string], 0
0x180166326  lea     rcx, [rsp+0A8h+var_60]
0x18016632b  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180166330  nop
0x180166331  lea     rcx, [rsp+0A8h+var_58]
0x180166336  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016633b  nop
0x18016633c  lea     rcx, [rsp+0A8h+arg_18]
0x180166344  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166349  mov     eax, ebx
0x18016634b  jmp     loc_18016643B
0x180166350  lea     rdx, [rsi+1B8h]
0x180166357  lea     rcx, [rsp+0A8h+SRWLock]
0x18016635c  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180166361  nop
0x180166362  lea     rcx, [rsi+48h]
0x180166366  lea     r9, [rsp+0A8h+var_60]
0x18016636b  lea     r8, [rsp+0A8h+string]
0x180166370  lea     rdx, [rsp+0A8h+var_48]
0x180166375  call    ??$_Emplace@VHString@Wrappers@WRL@Microsoft@@AEAV?$ComPtr@VTileNotificationManager@@@34@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@VTileNotificationManager@@@34@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@AEAV?$ComPtr@VTileNotificationManager@@@56@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<TileNotificationManager>>>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<TileNotificationManager> &>(Microsoft::WRL::Wrappers::HString &&,Microsoft::WRL::ComPtr<TileNotificationManager> &)
0x18016637a  nop
0x18016637b  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x180166380  test    rcx, rcx
0x180166383  jz      short loc_18016638B
0x180166385  call    cs:__imp_ReleaseSRWLockExclusive
0x18016638b  mov     r8b, 1; bool
0x18016638e  mov     rdx, [rsp+0A8h+var_60]; struct TileNotificationManager *
0x180166393  mov     rcx, r14; this
0x180166396  call    ?ProcessNotificationsForTile@NotificationQueueManager@@QEAAJPEAVTileNotificationManager@@_N@Z; NotificationQueueManager::ProcessNotificationsForTile(TileNotificationManager *,bool)
0x18016639b  mov     ebx, eax
0x18016639d  test    eax, eax
0x18016639f  jns     short loc_1801663F9
0x1801663a1  mov     rcx, [rsp+0A8h]; this
0x1801663a9  mov     r9d, eax; char *
0x1801663ac  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801663b3  mov     edx, 106h; void *
0x1801663b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801663bd  nop
0x1801663be  mov     rcx, [rsp+0A8h+string]; string
0x1801663c3  call    cs:__imp_WindowsDeleteString
0x1801663c9  mov     [rsp+0A8h+string], 0
0x1801663d2  lea     rcx, [rsp+0A8h+var_60]
0x1801663d7  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x1801663dc  nop
0x1801663dd  lea     rcx, [rsp+0A8h+var_58]
0x1801663e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801663e7  nop
0x1801663e8  lea     rcx, [rsp+0A8h+arg_18]
0x1801663f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801663f5  mov     eax, ebx
0x1801663f7  jmp     short loc_18016643B
0x1801663f9  mov     rcx, [rsp+0A8h+string]; string
0x1801663fe  call    cs:__imp_WindowsDeleteString
0x180166404  mov     [rsp+0A8h+string], 0
0x18016640d  lea     rcx, [rsp+0A8h+var_60]
0x180166412  call    ?InternalRelease@?$ComPtr@VTileNotificationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TileNotificationManager>::InternalRelease(void)
0x180166417  nop
0x180166418  lea     rcx, [rsp+0A8h+var_58]
0x18016641d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166422  nop
0x180166423  lea     rcx, [rsp+0A8h+arg_18]
0x18016642b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166430  xor     eax, eax
0x180166432  jmp     short loc_18016643B
0x180166434  mov     eax, [rsp+0A8h+arg_0]
0x18016643b  add     rsp, 88h
0x180166442  pop     r14
0x180166444  pop     rdi
0x180166445  pop     rsi
0x180166446  pop     rbx
0x180166447  retn
```
