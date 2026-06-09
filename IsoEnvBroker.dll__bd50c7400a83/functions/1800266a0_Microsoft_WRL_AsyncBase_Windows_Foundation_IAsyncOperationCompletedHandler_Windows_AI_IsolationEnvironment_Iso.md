# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800266a0`
- end: `0x180026718`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `120`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002520`
- `0x1800266a0`
- `0x180028aa0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800266ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800266ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800266d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800266d2`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
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
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x180026717LL);
  }
  return (int)RoGetActivationFactory(string, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x1800266a0  sub     rsp, 58h
0x1800266a4  mov     rax, cs:__security_cookie
0x1800266ab  xor     rax, rsp
0x1800266ae  mov     [rsp+58h+var_18], rax
0x1800266b3  lea     r9, [rsp+58h+string]; string
0x1800266b8  mov     [rsp+58h+string], 0
0x1800266c1  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800266c6  mov     edx, 33h ; '3'; length
0x1800266cb  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QB_WB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x1800266d2  call    cs:__imp_WindowsCreateStringReference
0x1800266d8  test    eax, eax
0x1800266da  js      short loc_180026710
0x1800266dc  mov     rcx, [rsp+58h+string]
0x1800266e1  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800266e8  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x1800266ef  call    cs:__imp_RoGetActivationFactory
0x1800266f5  xor     ecx, ecx
0x1800266f7  test    eax, eax
0x1800266f9  setns   cl
0x1800266fc  mov     eax, ecx
0x1800266fe  mov     rcx, [rsp+58h+var_18]
0x180026703  xor     rcx, rsp; StackCookie
0x180026706  call    __security_check_cookie
0x18002670b  add     rsp, 58h
0x18002670f  retn
0x180026710  mov     ecx, eax; this
0x180026712  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
