# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18000c850`
- end: `0x18000c8d9`
- name: `?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `137`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000c850`
- `0x18000e284`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c893`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c8b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c8b0`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  HSTRING_HEADER v7; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+38h] [rbp-20h] BYREF

  memset(&v7, 0, sizeof(v7));
  v8 = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Diagnostics.AsyncCausalityTracer", 0x33u, &v7, &v8);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18000C8D8LL);
  }
  return (int)RoGetActivationFactory(v8, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x18000c850  mov     r11, rsp
0x18000c853  sub     rsp, 58h
0x18000c857  mov     rax, cs:__security_cookie
0x18000c85e  xor     rax, rsp
0x18000c861  mov     [rsp+58h+var_18], rax
0x18000c866  xorps   xmm0, xmm0
0x18000c869  mov     qword ptr [r11-38h], 0
0x18000c871  movdqu  [rsp+58h+var_30], xmm0
0x18000c877  lea     r9, [r11-20h]; string
0x18000c87b  mov     qword ptr [r11-20h], 0
0x18000c883  lea     r8, [r11-38h]; hstringHeader
0x18000c887  mov     edx, 33h ; '3'; length
0x18000c88c  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x18000c893  call    cs:__imp_WindowsCreateStringReference
0x18000c899  test    eax, eax
0x18000c89b  js      short loc_18000C8D1
0x18000c89d  mov     rcx, [rsp+58h+var_20]
0x18000c8a2  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000c8a9  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x18000c8b0  call    cs:__imp_RoGetActivationFactory
0x18000c8b6  xor     ecx, ecx
0x18000c8b8  test    eax, eax
0x18000c8ba  setns   cl
0x18000c8bd  mov     eax, ecx
0x18000c8bf  mov     rcx, [rsp+58h+var_18]
0x18000c8c4  xor     rcx, rsp; StackCookie
0x18000c8c7  call    __security_check_cookie
0x18000c8cc  add     rsp, 58h
0x18000c8d0  retn
0x18000c8d1  mov     ecx, eax; this
0x18000c8d3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
