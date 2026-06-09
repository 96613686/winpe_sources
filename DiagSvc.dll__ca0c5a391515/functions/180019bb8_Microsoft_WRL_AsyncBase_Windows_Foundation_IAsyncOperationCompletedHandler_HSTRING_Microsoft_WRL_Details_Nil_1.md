# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180019bb8`
- end: `0x180019c69`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019a00`

## callees

- `0x180003fc0`
- `0x180014044`
- `0x180019bb8`
- `0x180027010`

## string_xrefs

- `0x180019bf3`: `Windows.Foundation.AsyncOperationCompletedHandler`1<String>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        __int64 a1)
{
  struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *result; // rax
  __int64 (__fastcall *v3)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, _QWORD, __int64); // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  __int64 v7; // [rsp+50h] [rbp-38h] BYREF

  result = Microsoft::WRL::gCausality;
  if ( Microsoft::WRL::gCausality )
  {
    v3 = *(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, _QWORD, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 48LL);
    v4 = *(unsigned int *)(a1 + 64);
    *(_QWORD *)&v6.Data1 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<String>";
    v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6);
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *)v3(
                                                                                      Microsoft::WRL::gCausality,
                                                                                      0,
                                                                                      2,
                                                                                      &v6,
                                                                                      a1,
                                                                                      *(_QWORD *)(v5 + 24),
                                                                                      v4);
  }
  return result;
}

```

## disassembly

```asm
0x180019bb8  mov     r11, rsp
0x180019bbb  mov     [r11+10h], rbx
0x180019bbf  mov     [r11+18h], rsi
0x180019bc3  push    rdi
0x180019bc4  sub     rsp, 80h
0x180019bcb  mov     rax, cs:__security_cookie
0x180019bd2  xor     rax, rsp
0x180019bd5  mov     [rsp+88h+var_18], rax
0x180019bda  mov     rsi, rcx
0x180019bdd  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180019be4  test    rax, rax
0x180019be7  jz      short loc_180019C47
0x180019be9  mov     rax, [rax]
0x180019bec  mov     rdi, [rax+30h]
0x180019bf0  mov     ebx, [rcx+40h]
0x180019bf3  lea     rax, aWindowsFoundat; "Windows.Foundation.AsyncOperationComple"...
0x180019bfa  mov     [r11-48h], rax
0x180019bfe  lea     rdx, [r11-48h]
0x180019c02  lea     rcx, [r11-38h]
0x180019c06  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180019c0b  nop
0x180019c0c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180019c13  movdqu  [rsp+88h+var_48], xmm0
0x180019c19  mov     [rsp+88h+var_58], rbx
0x180019c1e  mov     rcx, [rax+18h]
0x180019c22  mov     [rsp+88h+var_60], rcx
0x180019c27  mov     [rsp+88h+var_68], rsi
0x180019c2c  lea     r9, [rsp+88h+var_48]
0x180019c31  xor     edx, edx
0x180019c33  lea     r8d, [rdx+2]
0x180019c37  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180019c3e  mov     rax, rdi
0x180019c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c46  nop
0x180019c47  mov     rcx, [rsp+88h+var_18]
0x180019c4c  xor     rcx, rsp; StackCookie
0x180019c4f  call    __security_check_cookie
0x180019c54  lea     r11, [rsp+88h+var_8]
0x180019c5c  mov     rbx, [r11+18h]
0x180019c60  mov     rsi, [r11+20h]
0x180019c64  mov     rsp, r11
0x180019c67  pop     rdi
0x180019c68  retn
```
