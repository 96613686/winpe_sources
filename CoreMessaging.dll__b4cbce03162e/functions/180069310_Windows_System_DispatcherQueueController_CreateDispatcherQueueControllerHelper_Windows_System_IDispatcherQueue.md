# Windows::System::DispatcherQueueController::CreateDispatcherQueueControllerHelper(Windows::System::IDispatcherQueueController * *)

- ea: `0x180069310`
- end: `0x180069463`
- name: `?CreateDispatcherQueueControllerHelper@DispatcherQueueController@System@Windows@@SAJPEAPEAUIDispatcherQueueController@23@@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct Windows::System::IDispatcherQueueController **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180068d50`

## callees

- `0x18001df58`
- `0x18001e0dc`
- `0x180069310`
- `0x18006946c`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069441`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069415`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006942a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006942a`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18006944a`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180069457`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18006944a`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180069457`

## string_xrefs

- `0x18006940e`: `DispatcherQueueController is already created on this thread.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::System::DispatcherQueueController::CreateDispatcherQueueControllerHelper(
        struct Windows::System::IDispatcherQueueController **a1)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, struct Windows::System::IDispatcherQueueController **); // rcx
  struct Windows::System::DispatcherQueue *v6; // rcx
  HRESULT v8; // eax
  _BYTE v9[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, struct Windows::System::IDispatcherQueueController **); // [rsp+28h] [rbp-38h] BYREF
  struct Windows::System::DispatcherQueue *v11; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  v11 = 0;
  v10 = 0;
  *a1 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  if ( Windows::System::DispatcherQueue::GetDispatcherQueueForThread(&v11) )
  {
    string = 0;
    v8 = WindowsCreateStringReference(
           L"DispatcherQueueController is already created on this thread.",
           0x3Cu,
           &hstringHeader,
           &string);
    if ( v8 < 0 )
    {
      RaiseException(v8, 1u, 0, 0);
      __debugbreak();
    }
    v4 = -2147417842;
    RoOriginateError(2147549454LL, string);
  }
  else
  {
    v9[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v2 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::DispatcherQueueController,Windows::System::DispatcherQueueController,bool>(
           &v10,
           v9);
    if ( v2 < 0 )
      RoFailFastWithErrorContext((unsigned int)v2);
    v3 = (**v10)(v10, &GUID_22f34e66_50db_4e36_a98d_61c01b384d20, a1);
    if ( v3 < 0 )
      RoFailFastWithErrorContext((unsigned int)v3);
    v4 = 0;
  }
  v5 = v10;
  if ( v10 )
  {
    v10 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::System::IDispatcherQueueController **)))(*v5)[2])(v5);
  }
  v6 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(struct Windows::System::DispatcherQueue *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180069310  mov     [rsp-8+arg_8], rbx
0x180069315  push    rbp
0x180069316  mov     rbp, rsp
0x180069319  sub     rsp, 60h
0x18006931d  mov     rax, cs:__security_cookie
0x180069324  xor     rax, rsp
0x180069327  mov     [rbp+var_8], rax
0x18006932b  mov     rbx, rcx
0x18006932e  mov     [rbp+var_30], 0
0x180069336  mov     [rbp+var_38], 0
0x18006933e  mov     qword ptr [rcx], 0
0x180069345  lea     rcx, [rbp+var_30]
0x180069349  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006934e  lea     rcx, [rbp+var_30]; struct Windows::System::DispatcherQueue **
0x180069352  call    ?GetDispatcherQueueForThread@DispatcherQueue@System@Windows@@SA_NPEAPEAV123@@Z; Windows::System::DispatcherQueue::GetDispatcherQueueForThread(Windows::System::DispatcherQueue * *)
0x180069357  test    al, al
0x180069359  jnz     loc_1800693F9
0x18006935f  mov     [rbp+var_40], al
0x180069362  lea     rcx, [rbp+var_38]
0x180069366  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006936b  lea     rdx, [rbp+var_40]
0x18006936f  lea     rcx, [rbp+var_38]
0x180069373  call    ??$MakeAndInitialize@VDispatcherQueueController@System@Windows@@V123@_N@Details@WRL@Microsoft@@YAJPEAPEAVDispatcherQueueController@System@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::DispatcherQueueController,Windows::System::DispatcherQueueController,bool>(Windows::System::DispatcherQueueController * *,bool &&)
0x180069378  test    eax, eax
0x18006937a  js      loc_180069448
0x180069380  mov     rcx, [rbp+var_38]
0x180069384  mov     rax, [rcx]
0x180069387  mov     r8, rbx
0x18006938a  lea     rdx, _GUID_22f34e66_50db_4e36_a98d_61c01b384d20
0x180069391  mov     rax, [rax]
0x180069394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069399  nop
0x18006939a  test    eax, eax
0x18006939c  js      loc_180069455
0x1800693a2  xor     ebx, ebx
0x1800693a4  mov     rcx, [rbp+var_38]
0x1800693a8  test    rcx, rcx
0x1800693ab  jz      short loc_1800693C2
0x1800693ad  mov     [rbp+var_38], 0
0x1800693b5  mov     rax, [rcx]
0x1800693b8  mov     rax, [rax+10h]
0x1800693bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800693c1  nop
0x1800693c2  mov     rcx, [rbp+var_30]
0x1800693c6  test    rcx, rcx
0x1800693c9  jz      short loc_1800693E0
0x1800693cb  mov     [rbp+var_30], 0
0x1800693d3  mov     rdx, [rcx]
0x1800693d6  mov     rax, [rdx+10h]
0x1800693da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800693df  nop
0x1800693e0  mov     eax, ebx
0x1800693e2  mov     rcx, [rbp+var_8]
0x1800693e6  xor     rcx, rsp; StackCookie
0x1800693e9  call    __security_check_cookie
0x1800693ee  mov     rbx, [rsp+60h+arg_8]
0x1800693f3  add     rsp, 60h
0x1800693f7  pop     rbp
0x1800693f8  retn
0x1800693f9  mov     [rbp+string], 0
0x180069401  lea     r9, [rbp+string]; string
0x180069405  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180069409  mov     edx, 3Ch ; '<'; length
0x18006940e  lea     rcx, aDispatcherqueu_0; "DispatcherQueueController is already cr"...
0x180069415  call    cs:__imp_WindowsCreateStringReference
0x18006941b  test    eax, eax
0x18006941d  js      short loc_180069435
0x18006941f  mov     rdx, [rbp+string]
0x180069423  mov     ebx, 8001010Eh
0x180069428  mov     ecx, ebx
0x18006942a  call    cs:__imp_RoOriginateError
0x180069430  jmp     loc_1800693A4
0x180069435  xor     r9d, r9d; lpArguments
0x180069438  xor     r8d, r8d; nNumberOfArguments
0x18006943b  lea     edx, [r9+1]; dwExceptionFlags
0x18006943f  mov     ecx, eax; dwExceptionCode
0x180069441  call    cs:__imp_RaiseException
0x180069447  int     3; Trap to Debugger
0x180069448  mov     ecx, eax
0x18006944a  call    cs:__imp_RoFailFastWithErrorContext
0x180069450  jmp     loc_180069380
0x180069455  mov     ecx, eax
0x180069457  call    cs:__imp_RoFailFastWithErrorContext
0x18006945d  jmp     loc_1800693A2
```
