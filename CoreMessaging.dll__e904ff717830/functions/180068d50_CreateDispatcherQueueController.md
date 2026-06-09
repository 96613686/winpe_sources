# CreateDispatcherQueueController

- ea: `0x180068d50`
- end: `0x180068e68`
- name: `CreateDispatcherQueueController`
- size: `280`
- prototype: `HRESULT __stdcall(DispatcherQueueOptions *__struct_ptr options, void **dispatcherQueueController)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180068d50`
- `0x180068e70`
- `0x180069310`
- `0x180086130`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068e28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068e28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068e3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068e0b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180068dc2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180068dc2`

## string_xrefs

- `0x180068e51`: `Invalid options threadType.`

## pseudocode

```c
HRESULT __stdcall CreateDispatcherQueueController(DispatcherQueueOptions *options, void **dispatcherQueueController)
{
  __int32 v3; // ecx
  int DispatcherQueueControllerHelper; // eax
  unsigned int v5; // ebx
  HRESULT v6; // eax
  HRESULT v8; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  if ( !dispatcherQueueController )
  {
    string = 0;
    v6 = WindowsCreateStringReference(
           L"Out parameter (DispatcherQueueController) is null.",
           0x32u,
           &hstringHeader,
           &string);
    if ( v6 < 0 )
    {
      RaiseException(v6, 1u, 0, 0);
      __debugbreak();
    }
    v5 = -2147467261;
    goto LABEL_9;
  }
  if ( options->dwSize != 12 )
  {
    string = 0;
    v8 = WindowsCreateStringReference(
           L"options dwSize should match the size of the struct.",
           0x33u,
           &hstringHeader,
           &string);
    if ( v8 < 0 )
    {
      RaiseException(v8, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_14;
  }
  v3 = options->threadType - 1;
  if ( !v3 )
  {
    DispatcherQueueControllerHelper = Windows::System::DispatcherQueueController::CreateOnNewThread(
                                        options->apartmentType,
                                        (struct Windows::System::IDispatcherQueueController **)dispatcherQueueController);
    goto LABEL_5;
  }
  if ( v3 != 1 )
  {
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Invalid options threadType.",
      0x1Cu,
      0x1Bu);
LABEL_14:
    v5 = -2147024809;
LABEL_9:
    RoOriginateError(v5, string);
    return v5;
  }
  DispatcherQueueControllerHelper = Windows::System::DispatcherQueueController::CreateDispatcherQueueControllerHelper((struct Windows::System::IDispatcherQueueController **)dispatcherQueueController);
LABEL_5:
  v5 = DispatcherQueueControllerHelper;
  if ( DispatcherQueueControllerHelper >= 0 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x180068d50  push    rbx
0x180068d52  sub     rsp, 50h
0x180068d56  mov     rax, cs:__security_cookie
0x180068d5d  xor     rax, rsp
0x180068d60  mov     [rsp+58h+var_18], rax
0x180068d65  mov     r8, rcx
0x180068d68  test    rdx, rdx
0x180068d6b  jz      short loc_180068D8D
0x180068d6d  cmp     dword ptr [rcx], 0Ch
0x180068d70  jnz     short loc_180068DEC
0x180068d72  mov     ecx, [rcx+4]
0x180068d75  sub     ecx, 1
0x180068d78  jnz     short loc_180068DDD
0x180068d7a  mov     ecx, [r8+8]; enum DISPATCHERQUEUE_THREAD_APARTMENTTYPE
0x180068d7e  call    ?CreateOnNewThread@DispatcherQueueController@System@Windows@@SAJW4DISPATCHERQUEUE_THREAD_APARTMENTTYPE@@PEAPEAUIDispatcherQueueController@23@@Z; Windows::System::DispatcherQueueController::CreateOnNewThread(DISPATCHERQUEUE_THREAD_APARTMENTTYPE,Windows::System::IDispatcherQueueController * *)
0x180068d83  mov     ebx, eax
0x180068d85  test    eax, eax
0x180068d87  js      short loc_180068DC8
0x180068d89  xor     ebx, ebx
0x180068d8b  jmp     short loc_180068DC8
0x180068d8d  lea     r9, [rsp+58h+string]; string
0x180068d92  mov     [rsp+58h+string], 0
0x180068d9b  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180068da0  mov     edx, 32h ; '2'; length
0x180068da5  lea     rcx, aOutParameterDi; "Out parameter (DispatcherQueueControlle"...
0x180068dac  call    cs:__imp_WindowsCreateStringReference
0x180068db2  test    eax, eax
0x180068db4  js      short loc_180068E1C
0x180068db6  mov     ebx, 80004003h
0x180068dbb  mov     rdx, [rsp+58h+string]
0x180068dc0  mov     ecx, ebx
0x180068dc2  call    cs:__imp_RoOriginateError
0x180068dc8  mov     eax, ebx
0x180068dca  mov     rcx, [rsp+58h+var_18]
0x180068dcf  xor     rcx, rsp; StackCookie
0x180068dd2  call    __security_check_cookie
0x180068dd7  add     rsp, 50h
0x180068ddb  pop     rbx
0x180068ddc  retn
0x180068ddd  cmp     ecx, 1
0x180068de0  jnz     short loc_180068E42
0x180068de2  mov     rcx, rdx; struct Windows::System::IDispatcherQueueController **
0x180068de5  call    ?CreateDispatcherQueueControllerHelper@DispatcherQueueController@System@Windows@@SAJPEAPEAUIDispatcherQueueController@23@@Z; Windows::System::DispatcherQueueController::CreateDispatcherQueueControllerHelper(Windows::System::IDispatcherQueueController * *)
0x180068dea  jmp     short loc_180068D83
0x180068dec  lea     r9, [rsp+58h+string]; string
0x180068df1  mov     [rsp+58h+string], 0
0x180068dfa  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180068dff  mov     edx, 33h ; '3'; length
0x180068e04  lea     rcx, aOptionsDwsizeS; "options dwSize should match the size of"...
0x180068e0b  call    cs:__imp_WindowsCreateStringReference
0x180068e11  test    eax, eax
0x180068e13  js      short loc_180068E2F
0x180068e15  mov     ebx, 80070057h
0x180068e1a  jmp     short loc_180068DBB
0x180068e1c  xor     r9d, r9d; lpArguments
0x180068e1f  xor     r8d, r8d; nNumberOfArguments
0x180068e22  mov     ecx, eax; dwExceptionCode
0x180068e24  lea     edx, [r9+1]; dwExceptionFlags
0x180068e28  call    cs:__imp_RaiseException
0x180068e2e  int     3; Trap to Debugger
0x180068e2f  xor     r9d, r9d; lpArguments
0x180068e32  xor     r8d, r8d; nNumberOfArguments
0x180068e35  mov     ecx, eax; dwExceptionCode
0x180068e37  lea     edx, [r9+1]; dwExceptionFlags
0x180068e3b  call    cs:__imp_RaiseException
0x180068e41  int     3; Trap to Debugger
0x180068e42  mov     r9d, 1Bh; unsigned int
0x180068e48  mov     [rsp+58h+string], 0
0x180068e51  lea     rdx, aInvalidOptions; "Invalid options threadType."
0x180068e58  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x180068e5d  lea     r8d, [r9+1]; unsigned int
0x180068e61  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180068e66  jmp     short loc_180068E15
```
