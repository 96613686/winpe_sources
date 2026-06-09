# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::SyncEngine::WriteTargetingIdentifierAsyncActionActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180007570`
- end: `0x1800075e4`
- name: `?InitCausality@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?WriteTargetingIdentifierAsyncActionActionName@SyncEngine@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `116`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007570`
- `0x1800075ec`
- `0x180009f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800075b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800075b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800075a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800075a2`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::SyncEngine::WriteTargetingIdentifierAsyncActionActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  signed int v3; // eax
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
    __debugbreak();
  }
  return (int)Windows::Foundation::GetActivationFactory<Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics>(string) >= 0;
}

```

## disassembly

```asm
0x180007570  sub     rsp, 58h
0x180007574  mov     rax, cs:__security_cookie
0x18000757b  xor     rax, rsp
0x18000757e  mov     [rsp+58h+var_18], rax
0x180007583  lea     r9, [rsp+58h+string]; string
0x180007588  mov     [rsp+58h+string], 0
0x180007591  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180007596  mov     edx, 33h ; '3'; length
0x18000759b  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x1800075a2  call    cs:__imp_WindowsCreateStringReference
0x1800075a8  test    eax, eax
0x1800075aa  jns     short loc_1800075BF
0x1800075ac  xor     r9d, r9d; lpArguments
0x1800075af  xor     r8d, r8d; nNumberOfArguments
0x1800075b2  mov     ecx, eax; dwExceptionCode
0x1800075b4  lea     edx, [r9+1]; dwExceptionFlags
0x1800075b8  call    cs:__imp_RaiseException
0x1800075be  int     3; Trap to Debugger
0x1800075bf  mov     rcx, [rsp+58h+string]
0x1800075c4  call    ??$GetActivationFactory@UIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAsyncCausalityTracerStatics@Diagnostics@01@@Z; Windows::Foundation::GetActivationFactory<Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics>(HSTRING__ *,Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * *)
0x1800075c9  xor     ecx, ecx
0x1800075cb  test    eax, eax
0x1800075cd  setns   cl
0x1800075d0  mov     eax, ecx
0x1800075d2  mov     rcx, [rsp+58h+var_18]
0x1800075d7  xor     rcx, rsp; StackCookie
0x1800075da  call    __security_check_cookie
0x1800075df  add     rsp, 58h
0x1800075e3  retn
```
