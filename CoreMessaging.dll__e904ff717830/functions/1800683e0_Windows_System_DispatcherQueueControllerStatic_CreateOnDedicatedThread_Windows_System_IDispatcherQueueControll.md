# Windows::System::DispatcherQueueControllerStatic::CreateOnDedicatedThread(Windows::System::IDispatcherQueueController * *)

- ea: `0x1800683e0`
- end: `0x180068477`
- name: `?CreateOnDedicatedThread@DispatcherQueueControllerStatic@System@Windows@@UEAAJPEAPEAUIDispatcherQueueController@23@@Z`
- size: `151`
- prototype: `__int64 __fastcall(Windows::System::DispatcherQueueControllerStatic *__hidden this, struct Windows::System::IDispatcherQueueController **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800683e0`
- `0x180068e70`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068466`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068439`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006844d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006844d`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18006846f`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18006846f`

## pseudocode

```c
__int64 __fastcall Windows::System::DispatcherQueueControllerStatic::CreateOnDedicatedThread(
        Windows::System::DispatcherQueueControllerStatic *this,
        struct Windows::System::IDispatcherQueueController **a2)
{
  int v2; // eax
  HRESULT v4; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  if ( a2 )
  {
    v2 = Windows::System::DispatcherQueueController::CreateOnNewThread(DQTAT_COM_ASTA, a2);
    if ( v2 < 0 )
      RoFailFastWithErrorContext((unsigned int)v2);
    return 0;
  }
  else
  {
    string = 0;
    v4 = WindowsCreateStringReference(
           L"Out parameter (DispatcherQueueController) is null.",
           0x32u,
           &hstringHeader,
           &string);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
      __debugbreak();
    }
    RoOriginateError(2147500035LL, string);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800683e0  sub     rsp, 58h
0x1800683e4  mov     rax, cs:__security_cookie
0x1800683eb  xor     rax, rsp
0x1800683ee  mov     [rsp+58h+var_18], rax
0x1800683f3  test    rdx, rdx
0x1800683f6  jz      short loc_18006841A
0x1800683f8  mov     ecx, 1; enum DISPATCHERQUEUE_THREAD_APARTMENTTYPE
0x1800683fd  call    ?CreateOnNewThread@DispatcherQueueController@System@Windows@@SAJW4DISPATCHERQUEUE_THREAD_APARTMENTTYPE@@PEAPEAUIDispatcherQueueController@23@@Z; Windows::System::DispatcherQueueController::CreateOnNewThread(DISPATCHERQUEUE_THREAD_APARTMENTTYPE,Windows::System::IDispatcherQueueController * *)
0x180068402  test    eax, eax
0x180068404  js      short loc_18006846D
0x180068406  xor     eax, eax
0x180068408  mov     rcx, [rsp+58h+var_18]
0x18006840d  xor     rcx, rsp; StackCookie
0x180068410  call    __security_check_cookie
0x180068415  add     rsp, 58h
0x180068419  retn
0x18006841a  lea     r9, [rsp+58h+string]; string
0x18006841f  mov     [rsp+58h+string], 0
0x180068428  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18006842d  mov     edx, 32h ; '2'; length
0x180068432  lea     rcx, aOutParameterDi; "Out parameter (DispatcherQueueControlle"...
0x180068439  call    cs:__imp_WindowsCreateStringReference
0x18006843f  test    eax, eax
0x180068441  js      short loc_18006845A
0x180068443  mov     rdx, [rsp+58h+string]
0x180068448  mov     ecx, 80004003h
0x18006844d  call    cs:__imp_RoOriginateError
0x180068453  mov     eax, 80004003h
0x180068458  jmp     short loc_180068408
0x18006845a  xor     r9d, r9d; lpArguments
0x18006845d  xor     r8d, r8d; nNumberOfArguments
0x180068460  mov     ecx, eax; dwExceptionCode
0x180068462  lea     edx, [r9+1]; dwExceptionFlags
0x180068466  call    cs:__imp_RaiseException
0x18006846c  int     3; Trap to Debugger
0x18006846d  mov     ecx, eax
0x18006846f  call    cs:__imp_RoFailFastWithErrorContext
0x180068475  jmp     short loc_180068406
```
