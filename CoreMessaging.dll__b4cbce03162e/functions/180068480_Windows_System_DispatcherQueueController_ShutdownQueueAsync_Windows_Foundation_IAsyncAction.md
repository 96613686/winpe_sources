# Windows::System::DispatcherQueueController::ShutdownQueueAsync(Windows::Foundation::IAsyncAction * *)

- ea: `0x180068480`
- end: `0x180068622`
- name: `?ShutdownQueueAsync@DispatcherQueueController@System@Windows@@UEAAJPEAPEAUIAsyncAction@Foundation@3@@Z`
- size: `418`
- prototype: `__int64 __fastcall(Windows::System::DispatcherQueueController *__hidden this, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001df58`
- `0x180068480`
- `0x180068b44`
- `0x180069870`
- `0x180069a54`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068546`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068546`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800684ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800684ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800685ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006861b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800685ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006861b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006858b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800685d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006858b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800685d1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800685a1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800685a1`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800685f7`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068604`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800685f7`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180068604`

## string_xrefs

- `0x1800685ca`: `Cannot shut down again as it is already in progress.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::DispatcherQueueController::ShutdownQueueAsync(
        Windows::System::DispatcherQueueController *this,
        struct Windows::Foundation::IAsyncAction **a2)
{
  RTL_SRWLOCK *v4; // rsi
  Windows::System::DispatcherQueueAsyncHelper **v5; // r14
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  HRESULT v10; // eax
  HRESULT v11; // eax
  char v12[8]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-28h] BYREF

  v4 = (RTL_SRWLOCK *)(*((_QWORD *)this + 8) + 96LL);
  AcquireSRWLockExclusive(v4);
  if ( !a2 )
  {
    string = 0;
    v10 = WindowsCreateStringReference(L"Out parameter (IAsyncAction) is null.", 0x25u, &hstringHeader, &string);
    if ( v10 < 0 )
    {
      RaiseException(v10, 1u, 0, 0);
      __debugbreak();
    }
    v8 = -2147467261;
    goto LABEL_13;
  }
  *a2 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 8) + 176LL) )
  {
    string = 0;
    v11 = WindowsCreateStringReference(
            L"Cannot shut down again as it is already in progress.",
            0x34u,
            &hstringHeader,
            &string);
    if ( v11 < 0 )
    {
      RaiseException(v11, 1u, 0, 0);
      JUMPOUT(0x180068621LL);
    }
    v8 = -2147418113;
LABEL_13:
    RoOriginateError(v8, string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
    goto LABEL_8;
  }
  v12[0] = 1;
  v5 = (Windows::System::DispatcherQueueAsyncHelper **)((char *)this + 72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
  v6 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::DispatcherQueueAsyncHelper,Windows::System::DispatcherQueueAsyncHelper,bool>(
         (char *)this + 72,
         v12);
  if ( v6 < 0 )
    RoFailFastWithErrorContext((unsigned int)v6);
  Windows::System::DispatcherQueueAsyncHelper::StartOperation(*v5);
  v7 = (**(__int64 (__fastcall ***)(Windows::System::DispatcherQueueAsyncHelper *, GUID *, struct Windows::Foundation::IAsyncAction **))*v5)(
         *v5,
         &GUID_5a648006_843a_4da9_865b_9d26e5dfad7b,
         a2);
  if ( v7 < 0 )
    RoFailFastWithErrorContext((unsigned int)v7);
  (*(void (__fastcall **)(Windows::System::DispatcherQueueController *))(*(_QWORD *)this + 8LL))(this);
  Windows::System::DispatcherQueue::StartShutdownAsync(*((Windows::System::DispatcherQueue **)this + 8));
  v8 = 0;
LABEL_8:
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  return v8;
}

```

## disassembly

```asm
0x180068480  mov     [rsp+arg_10], rbx
0x180068485  push    rsi
0x180068486  push    rdi
0x180068487  push    r14
0x180068489  sub     rsp, 50h
0x18006848d  mov     rax, cs:__security_cookie
0x180068494  xor     rax, rsp
0x180068497  mov     [rsp+68h+var_20], rax
0x18006849c  mov     rbx, rdx
0x18006849f  mov     rdi, rcx
0x1800684a2  mov     rsi, [rcx+40h]
0x1800684a6  add     rsi, 60h ; '`'
0x1800684aa  mov     rcx, rsi; SRWLock
0x1800684ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800684b3  test    rbx, rbx
0x1800684b6  jz      loc_18006856C
0x1800684bc  mov     qword ptr [rbx], 0
0x1800684c3  mov     rax, [rdi+40h]
0x1800684c7  cmp     dword ptr [rax+0B0h], 0
0x1800684ce  jnz     loc_1800685B2
0x1800684d4  mov     [rsp+68h+var_48], 1
0x1800684d9  lea     r14, [rdi+48h]
0x1800684dd  mov     rcx, r14
0x1800684e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800684e5  lea     rdx, [rsp+68h+var_48]
0x1800684ea  mov     rcx, r14
0x1800684ed  call    ??$MakeAndInitialize@VDispatcherQueueAsyncHelper@System@Windows@@V123@_N@Details@WRL@Microsoft@@YAJPEAPEAVDispatcherQueueAsyncHelper@System@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::DispatcherQueueAsyncHelper,Windows::System::DispatcherQueueAsyncHelper,bool>(Windows::System::DispatcherQueueAsyncHelper * *,bool &&)
0x1800684f2  test    eax, eax
0x1800684f4  js      loc_1800685F5
0x1800684fa  mov     rcx, [r14]; this
0x1800684fd  call    ?StartOperation@DispatcherQueueAsyncHelper@System@Windows@@QEAAXXZ; Windows::System::DispatcherQueueAsyncHelper::StartOperation(void)
0x180068502  nop
0x180068503  mov     rcx, [r14]
0x180068506  mov     rax, [rcx]
0x180068509  mov     r8, rbx
0x18006850c  lea     rdx, _GUID_5a648006_843a_4da9_865b_9d26e5dfad7b
0x180068513  mov     rax, [rax]
0x180068516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006851b  nop
0x18006851c  test    eax, eax
0x18006851e  js      loc_180068602
0x180068524  mov     rax, [rdi]
0x180068527  mov     rcx, rdi
0x18006852a  mov     rax, [rax+8]
0x18006852e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068533  mov     rcx, [rdi+40h]; this
0x180068537  call    ?StartShutdownAsync@DispatcherQueue@System@Windows@@QEAAXXZ; Windows::System::DispatcherQueue::StartShutdownAsync(void)
0x18006853c  xor     ebx, ebx
0x18006853e  test    rsi, rsi
0x180068541  jz      short loc_18006854C
0x180068543  mov     rcx, rsi; SRWLock
0x180068546  call    cs:__imp_ReleaseSRWLockExclusive
0x18006854c  mov     eax, ebx
0x18006854e  mov     rcx, [rsp+68h+var_20]
0x180068553  xor     rcx, rsp; StackCookie
0x180068556  call    __security_check_cookie
0x18006855b  mov     rbx, [rsp+68h+arg_10]
0x180068563  add     rsp, 50h
0x180068567  pop     r14
0x180068569  pop     rdi
0x18006856a  pop     rsi
0x18006856b  retn
0x18006856c  mov     [rsp+68h+string], 0
0x180068575  lea     r9, [rsp+68h+string]; string
0x18006857a  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18006857f  mov     edx, 25h ; '%'; length
0x180068584  lea     rcx, aOutParameterIa; "Out parameter (IAsyncAction) is null."
0x18006858b  call    cs:__imp_WindowsCreateStringReference
0x180068591  test    eax, eax
0x180068593  js      short loc_1800685E2
0x180068595  mov     ebx, 80004003h
0x18006859a  mov     rdx, [rsp+68h+string]
0x18006859f  mov     ecx, ebx
0x1800685a1  call    cs:__imp_RoOriginateError
0x1800685a7  lea     rcx, [rdi+48h]
0x1800685ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800685b0  jmp     short loc_18006853E
0x1800685b2  mov     [rsp+68h+string], 0
0x1800685bb  lea     r9, [rsp+68h+string]; string
0x1800685c0  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x1800685c5  mov     edx, 34h ; '4'; length
0x1800685ca  lea     rcx, aCannotShutDown; "Cannot shut down again as it is already"...
0x1800685d1  call    cs:__imp_WindowsCreateStringReference
0x1800685d7  test    eax, eax
0x1800685d9  js      short loc_18006860F
0x1800685db  mov     ebx, 8000FFFFh
0x1800685e0  jmp     short loc_18006859A
0x1800685e2  xor     r9d, r9d; lpArguments
0x1800685e5  xor     r8d, r8d; nNumberOfArguments
0x1800685e8  lea     edx, [r9+1]; dwExceptionFlags
0x1800685ec  mov     ecx, eax; dwExceptionCode
0x1800685ee  call    cs:__imp_RaiseException
0x1800685f4  int     3; Trap to Debugger
0x1800685f5  mov     ecx, eax
0x1800685f7  call    cs:__imp_RoFailFastWithErrorContext
0x1800685fd  jmp     loc_1800684FA
0x180068602  mov     ecx, eax
0x180068604  call    cs:__imp_RoFailFastWithErrorContext
0x18006860a  jmp     loc_180068524
0x18006860f  xor     r9d, r9d; lpArguments
0x180068612  xor     r8d, r8d; nNumberOfArguments
0x180068615  lea     edx, [r9+1]; dwExceptionFlags
0x180068619  mov     ecx, eax; dwExceptionCode
0x18006861b  call    cs:__imp_RaiseException
```
