# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18000c780`
- end: `0x18000c7f8`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `120`
- prototype: `_BOOL8 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e20`
- `0x18000c780`
- `0x18000d4f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c7b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c7cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c7cf`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
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
    JUMPOUT(0x18000C7F7LL);
  }
  return (int)RoGetActivationFactory(string, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x18000c780  sub     rsp, 58h
0x18000c784  mov     rax, cs:__security_cookie
0x18000c78b  xor     rax, rsp
0x18000c78e  mov     [rsp+58h+var_18], rax
0x18000c793  lea     r9, [rsp+58h+string]; string
0x18000c798  mov     [rsp+58h+string], 0
0x18000c7a1  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18000c7a6  mov     edx, 33h ; '3'; length
0x18000c7ab  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x18000c7b2  call    cs:__imp_WindowsCreateStringReference
0x18000c7b8  test    eax, eax
0x18000c7ba  js      short loc_18000C7F0
0x18000c7bc  mov     rcx, [rsp+58h+string]
0x18000c7c1  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000c7c8  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x18000c7cf  call    cs:__imp_RoGetActivationFactory
0x18000c7d5  xor     ecx, ecx
0x18000c7d7  test    eax, eax
0x18000c7d9  setns   cl
0x18000c7dc  mov     eax, ecx
0x18000c7de  mov     rcx, [rsp+58h+var_18]
0x18000c7e3  xor     rcx, rsp; StackCookie
0x18000c7e6  call    __security_check_cookie
0x18000c7eb  add     rsp, 58h
0x18000c7ef  retn
0x18000c7f0  mov     ecx, eax; this
0x18000c7f2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
