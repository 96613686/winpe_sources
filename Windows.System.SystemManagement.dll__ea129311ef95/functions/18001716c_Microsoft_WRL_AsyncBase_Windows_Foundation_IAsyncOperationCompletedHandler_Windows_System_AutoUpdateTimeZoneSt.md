# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18001716c`
- end: `0x18001721d`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016cc0`

## callees

- `0x180002dc0`
- `0x1800132f8`
- `0x18001716c`
- `0x18002b010`

## string_xrefs

- `0x1800171a7`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.System.AutoUpdateTimeZoneStatus>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    *(_QWORD *)&v6.Data1 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.System.AutoUpdateTimeZoneStatus>";
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
0x18001716c  mov     r11, rsp
0x18001716f  mov     [r11+10h], rbx
0x180017173  mov     [r11+18h], rsi
0x180017177  push    rdi
0x180017178  sub     rsp, 80h
0x18001717f  mov     rax, cs:__security_cookie
0x180017186  xor     rax, rsp
0x180017189  mov     [rsp+88h+var_18], rax
0x18001718e  mov     rsi, rcx
0x180017191  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180017198  test    rax, rax
0x18001719b  jz      short loc_1800171FB
0x18001719d  mov     rax, [rax]
0x1800171a0  mov     rdi, [rax+30h]
0x1800171a4  mov     ebx, [rcx+40h]
0x1800171a7  lea     rax, aWindowsFoundat; "Windows.Foundation.AsyncOperationComple"...
0x1800171ae  mov     [r11-48h], rax
0x1800171b2  lea     rdx, [r11-48h]
0x1800171b6  lea     rcx, [r11-38h]
0x1800171ba  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800171bf  nop
0x1800171c0  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800171c7  movdqu  [rsp+88h+var_48], xmm0
0x1800171cd  mov     [rsp+88h+var_58], rbx
0x1800171d2  mov     rcx, [rax+18h]
0x1800171d6  mov     [rsp+88h+var_60], rcx
0x1800171db  mov     [rsp+88h+var_68], rsi
0x1800171e0  lea     r9, [rsp+88h+var_48]
0x1800171e5  xor     edx, edx
0x1800171e7  lea     r8d, [rdx+2]
0x1800171eb  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800171f2  mov     rax, rdi
0x1800171f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171fa  nop
0x1800171fb  mov     rcx, [rsp+88h+var_18]
0x180017200  xor     rcx, rsp; StackCookie
0x180017203  call    __security_check_cookie
0x180017208  lea     r11, [rsp+88h+var_8]
0x180017210  mov     rbx, [r11+18h]
0x180017214  mov     rsi, [r11+20h]
0x180017218  mov     rsp, r11
0x18001721b  pop     rdi
0x18001721c  retn
```
