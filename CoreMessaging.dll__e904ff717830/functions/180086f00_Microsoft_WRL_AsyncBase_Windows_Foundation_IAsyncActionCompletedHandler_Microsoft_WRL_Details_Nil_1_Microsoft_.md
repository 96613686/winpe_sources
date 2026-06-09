# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180086f00`
- end: `0x180086f83`
- name: `?InitCausality@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `131`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180086f00`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180086f7c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180086f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180086f32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180086f32`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180086f4f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180086f4f`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  HRESULT v3; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Diagnostics.AsyncCausalityTracer",
         0x33u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    JUMPOUT(0x180086F82LL);
  }
  return (int)RoGetActivationFactory(string, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x180086f00  sub     rsp, 58h
0x180086f04  mov     rax, cs:__security_cookie
0x180086f0b  xor     rax, rsp
0x180086f0e  mov     [rsp+58h+var_18], rax
0x180086f13  lea     r9, [rsp+58h+string]; string
0x180086f18  mov     [rsp+58h+string], 0
0x180086f21  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180086f26  mov     edx, 33h ; '3'; length
0x180086f2b  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QB_WB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x180086f32  call    cs:__imp_WindowsCreateStringReference
0x180086f38  test    eax, eax
0x180086f3a  js      short loc_180086F70
0x180086f3c  mov     rcx, [rsp+58h+string]
0x180086f41  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180086f48  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x180086f4f  call    cs:__imp_RoGetActivationFactory
0x180086f55  xor     ecx, ecx
0x180086f57  test    eax, eax
0x180086f59  setns   cl
0x180086f5c  mov     eax, ecx
0x180086f5e  mov     rcx, [rsp+58h+var_18]
0x180086f63  xor     rcx, rsp; StackCookie
0x180086f66  call    __security_check_cookie
0x180086f6b  add     rsp, 58h
0x180086f6f  retn
0x180086f70  xor     r9d, r9d; lpArguments
0x180086f73  xor     r8d, r8d; nNumberOfArguments
0x180086f76  mov     ecx, eax; dwExceptionCode
0x180086f78  lea     edx, [r9+1]; dwExceptionFlags
0x180086f7c  call    cs:__imp_RaiseException
```
