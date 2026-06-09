# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::InitCausality

- ea: `0x18000c7c0`
- end: `0x18000c849`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::InitCausality`
- size: `137`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000c7c0`
- `0x18000e284`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c803`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c820`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c820`

## pseudocode

```c
_BOOL8 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::InitCausality(
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
    JUMPOUT(0x18000C848LL);
  }
  return (int)RoGetActivationFactory(v8, &GUID_50850b26_267e_451b_a890_ab6a370245ee, &Microsoft::WRL::gCausality) >= 0;
}

```

## disassembly

```asm
0x18000c7c0  mov     r11, rsp
0x18000c7c3  sub     rsp, 58h
0x18000c7c7  mov     rax, cs:__security_cookie
0x18000c7ce  xor     rax, rsp
0x18000c7d1  mov     [rsp+58h+var_18], rax
0x18000c7d6  xorps   xmm0, xmm0
0x18000c7d9  mov     qword ptr [r11-38h], 0
0x18000c7e1  movdqu  [rsp+58h+var_30], xmm0
0x18000c7e7  lea     r9, [r11-20h]; string
0x18000c7eb  mov     qword ptr [r11-20h], 0
0x18000c7f3  lea     r8, [r11-38h]; hstringHeader
0x18000c7f7  mov     edx, 33h ; '3'; length
0x18000c7fc  lea     rcx, ?RuntimeClass_Windows_Foundation_Diagnostics_AsyncCausalityTracer@@3QBGB; "Windows.Foundation.Diagnostics.AsyncCau"...
0x18000c803  call    cs:__imp_WindowsCreateStringReference
0x18000c809  test    eax, eax
0x18000c80b  js      short loc_18000C841
0x18000c80d  mov     rcx, [rsp+58h+var_20]
0x18000c812  lea     r8, ?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000c819  lea     rdx, _GUID_50850b26_267e_451b_a890_ab6a370245ee
0x18000c820  call    cs:__imp_RoGetActivationFactory
0x18000c826  xor     ecx, ecx
0x18000c828  test    eax, eax
0x18000c82a  setns   cl
0x18000c82d  mov     eax, ecx
0x18000c82f  mov     rcx, [rsp+58h+var_18]
0x18000c834  xor     rcx, rsp; StackCookie
0x18000c837  call    __security_check_cookie
0x18000c83c  add     rsp, 58h
0x18000c840  retn
0x18000c841  mov     ecx, eax; this
0x18000c843  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
