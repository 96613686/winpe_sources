# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180069b04`
- end: `0x180069bd3`
- name: `?TraceOperationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069970`

## callees

- `0x180069b04`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069bcc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069bcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069b57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069b57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  HRESULT v5; // eax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+68h] [rbp-20h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    v8 = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = WindowsCreateStringReference(L"Windows.System.DispatcherQueueAsyncHelper", 0x29u, &v7, &v8);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x180069BD2LL);
    }
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v3 + 48))(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      v8,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x180069b04  mov     r11, rsp
0x180069b07  mov     [r11+10h], rbx
0x180069b0b  mov     [r11+18h], rsi
0x180069b0f  push    rdi
0x180069b10  sub     rsp, 80h
0x180069b17  mov     rax, cs:__security_cookie
0x180069b1e  xor     rax, rsp
0x180069b21  mov     [rsp+88h+var_18], rax
0x180069b26  mov     rbx, rcx
0x180069b29  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180069b30  test    rax, rax
0x180069b33  jz      short loc_180069B9E
0x180069b35  mov     rdi, [rax]
0x180069b38  mov     qword ptr [r11-20h], 0
0x180069b40  mov     esi, [rcx+40h]
0x180069b43  lea     r9, [r11-20h]; string
0x180069b47  lea     r8, [r11-38h]; hstringHeader
0x180069b4b  mov     edx, 29h ; ')'; length
0x180069b50  lea     rcx, ?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB; "Windows.System.DispatcherQueueAsyncHelp"...
0x180069b57  call    cs:__imp_WindowsCreateStringReference
0x180069b5d  test    eax, eax
0x180069b5f  js      short loc_180069BC0
0x180069b61  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180069b68  movdqu  [rsp+88h+var_48], xmm0
0x180069b6e  mov     [rsp+88h+var_58], rsi
0x180069b73  mov     rcx, [rsp+88h+var_20]
0x180069b78  mov     [rsp+88h+var_60], rcx
0x180069b7d  mov     [rsp+88h+var_68], rbx
0x180069b82  lea     r9, [rsp+88h+var_48]
0x180069b87  xor     edx, edx
0x180069b89  lea     r8d, [rdx+2]
0x180069b8d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180069b94  mov     rax, [rdi+30h]
0x180069b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b9d  nop
0x180069b9e  mov     rcx, [rsp+88h+var_18]
0x180069ba3  xor     rcx, rsp; StackCookie
0x180069ba6  call    __security_check_cookie
0x180069bab  lea     r11, [rsp+88h+var_8]
0x180069bb3  mov     rbx, [r11+18h]
0x180069bb7  mov     rsi, [r11+20h]
0x180069bbb  mov     rsp, r11
0x180069bbe  pop     rdi
0x180069bbf  retn
0x180069bc0  xor     r9d, r9d; lpArguments
0x180069bc3  xor     r8d, r8d; nNumberOfArguments
0x180069bc6  lea     edx, [r9+1]; dwExceptionFlags
0x180069bca  mov     ecx, eax; dwExceptionCode
0x180069bcc  call    cs:__imp_RaiseException
```
