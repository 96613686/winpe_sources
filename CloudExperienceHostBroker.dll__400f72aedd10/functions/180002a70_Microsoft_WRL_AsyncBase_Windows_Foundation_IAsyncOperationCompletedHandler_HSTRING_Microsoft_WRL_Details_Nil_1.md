# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180002a70`
- end: `0x180002b48`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002460`
- `0x180002520`

## callees

- `0x180002a70`
- `0x180009f30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002b41`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002b41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002ae7`

## string_xrefs

- `0x180002ae0`: `Windows.Foundation.AsyncOperationCompletedHandler`1<String>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  signed int v5; // eax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-38h] BYREF
  HSTRING string; // [rsp+68h] [rbp-20h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(_QWORD *)Microsoft::WRL::gCausality;
    string = 0;
    v4 = *(unsigned int *)(a1 + 64);
    v5 = WindowsCreateStringReference(
           L"Windows.Foundation.AsyncOperationCompletedHandler`1<String>",
           0x3Bu,
           &hstringHeader,
           &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      JUMPOUT(0x180002B47LL);
    }
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v3 + 48))(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      string,
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x180002a70  mov     [rsp+arg_8], rbx
0x180002a75  mov     [rsp+arg_10], rsi
0x180002a7a  push    rdi
0x180002a7b  sub     rsp, 80h
0x180002a82  mov     rax, cs:__security_cookie
0x180002a89  xor     rax, rsp
0x180002a8c  mov     [rsp+88h+var_18], rax
0x180002a91  mov     rbx, rcx
0x180002a94  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180002a9b  test    rax, rax
0x180002a9e  jnz     short loc_180002AC2
0x180002aa0  mov     rcx, [rsp+88h+var_18]
0x180002aa5  xor     rcx, rsp; StackCookie
0x180002aa8  call    __security_check_cookie
0x180002aad  lea     r11, [rsp+88h+var_8]
0x180002ab5  mov     rbx, [r11+18h]
0x180002ab9  mov     rsi, [r11+20h]
0x180002abd  mov     rsp, r11
0x180002ac0  pop     rdi
0x180002ac1  retn
0x180002ac2  mov     rdi, [rax]
0x180002ac5  mov     [rsp+88h+string], 0
0x180002ace  mov     esi, [rcx+40h]
0x180002ad1  lea     r9, [rsp+88h+string]; string
0x180002ad6  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x180002adb  mov     edx, 3Bh ; ';'; length
0x180002ae0  lea     rcx, sourceString; "Windows.Foundation.AsyncOperationComple"...
0x180002ae7  call    cs:__imp_WindowsCreateStringReference
0x180002aed  test    eax, eax
0x180002aef  js      short loc_180002B34
0x180002af1  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180002af8  movaps  [rsp+88h+var_48], xmm0
0x180002afd  mov     [rsp+88h+var_58], rsi
0x180002b02  mov     rcx, [rsp+88h+string]
0x180002b07  mov     [rsp+88h+var_60], rcx
0x180002b0c  mov     [rsp+88h+var_68], rbx
0x180002b11  lea     r9, [rsp+88h+var_48]
0x180002b16  xor     edx, edx
0x180002b18  mov     r8d, 2
0x180002b1e  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180002b25  mov     rax, [rdi+30h]
0x180002b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b2e  nop
0x180002b2f  jmp     loc_180002AA0
0x180002b34  xor     r9d, r9d; lpArguments
0x180002b37  xor     r8d, r8d; nNumberOfArguments
0x180002b3a  mov     edx, 1; dwExceptionFlags
0x180002b3f  mov     ecx, eax; dwExceptionCode
0x180002b41  call    cs:__imp_RaiseException
```
