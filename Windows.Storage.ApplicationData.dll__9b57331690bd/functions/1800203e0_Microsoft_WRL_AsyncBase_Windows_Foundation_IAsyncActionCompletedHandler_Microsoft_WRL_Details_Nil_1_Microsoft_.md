# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Storage::StateABIImplementation::ClearOperationDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800203e0`
- end: `0x180020463`
- name: `?InitCausality@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?ClearOperationDefaultName@StateABIImplementation@Storage@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `131`
- prototype: `int __fastcall(_RTL_RUN_ONCE *InitOnce, void *Parameter, void **Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800203e0`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020428`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020412`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020442`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020442`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Storage::StateABIImplementation::ClearOperationDefaultName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        _RTL_RUN_ONCE *InitOnce,
        void *Parameter,
        void **Context)
{
  signed int StringReference; // eax
  Microsoft::WRL::Wrappers::HStringReference hstrCausalityTraceName; // [rsp+20h] [rbp-38h] BYREF

  hstrCausalityTraceName.hstr_ = 0;
  StringReference = WindowsCreateStringReference(
                      RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer,
                      0x33u,
                      &hstrCausalityTraceName.header_,
                      &hstrCausalityTraceName.hstr_);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  return (int)RoGetActivationFactory(
                hstrCausalityTraceName.hstr_,
                &GUID_50850b26_267e_451b_a890_ab6a370245ee,
                &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x1800203e0  sub     rsp, 58h
0x1800203e4  mov     rax, cs:__security_cookie
0x1800203eb  xor     rax, rsp
0x1800203ee  mov     [rsp+58h+var_18], rax
0x1800203f3  lea     r9, [rsp+58h+hstrCausalityTraceName.hstr_]; string
0x1800203f8  mov     [rsp+58h+hstrCausalityTraceName.hstr_], 0
0x180020401  lea     Context, [rsp+58h+hstrCausalityTraceName]; hstringHeader
0x180020406  mov     edx, 33h ; '3'; length
0x18002040b  lea     InitOnce, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; sourceString
0x180020412  call    cs:__imp_WindowsCreateStringReference
0x180020418  test    eax, eax
0x18002041a  jns     short loc_18002042F
0x18002041c  xor     r9d, r9d; lpArguments
0x18002041f  xor     r8d, r8d; nNumberOfArguments
0x180020422  mov     ecx, eax; dwExceptionCode
0x180020424  lea     edx, [r9+1]; dwExceptionFlags
0x180020428  call    cs:__imp_RaiseException
0x18002042e  int     3; Trap to Debugger
0x18002042f  mov     InitOnce, [rsp+58h+hstrCausalityTraceName.hstr_]
0x180020434  lea     Context, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002043b  lea     Parameter, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x180020442  call    cs:__imp_RoGetActivationFactory
0x180020448  xor     ecx, ecx
0x18002044a  test    eax, eax
0x18002044c  setns   cl
0x18002044f  mov     eax, ecx
0x180020451  mov     InitOnce, [rsp+58h+var_18]
0x180020456  xor     InitOnce, rsp; StackCookie
0x180020459  call    __security_check_cookie
0x18002045e  add     rsp, 58h
0x180020462  retn
```
