# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x180015bec`
- end: `0x180015c9d`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014d10`

## callees

- `0x180002e60`
- `0x18000b894`
- `0x180015bec`
- `0x180022010`

## string_xrefs

- `0x180015c27`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Graphics.Capture.Server.CapturableItem>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    *(_QWORD *)&v6.Data1 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Graphics.Capture.Server.CapturableItem>";
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
0x180015bec  mov     r11, rsp
0x180015bef  mov     [r11+10h], rbx
0x180015bf3  mov     [r11+18h], rsi
0x180015bf7  push    rdi
0x180015bf8  sub     rsp, 80h
0x180015bff  mov     rax, cs:__security_cookie
0x180015c06  xor     rax, rsp
0x180015c09  mov     [rsp+88h+var_18], rax
0x180015c0e  mov     rsi, rcx
0x180015c11  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180015c18  test    rax, rax
0x180015c1b  jz      short loc_180015C7B
0x180015c1d  mov     rax, [rax]
0x180015c20  mov     rdi, [rax+30h]
0x180015c24  mov     ebx, [rcx+40h]
0x180015c27  lea     rax, aWindowsFoundat_2; "Windows.Foundation.AsyncOperationComple"...
0x180015c2e  mov     [r11-48h], rax
0x180015c32  lea     rdx, [r11-48h]
0x180015c36  lea     rcx, [r11-38h]
0x180015c3a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015c3f  nop
0x180015c40  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180015c47  movdqu  [rsp+88h+var_48], xmm0
0x180015c4d  mov     [rsp+88h+var_58], rbx
0x180015c52  mov     rcx, [rax+18h]
0x180015c56  mov     [rsp+88h+var_60], rcx
0x180015c5b  mov     [rsp+88h+var_68], rsi
0x180015c60  lea     r9, [rsp+88h+var_48]
0x180015c65  xor     edx, edx
0x180015c67  lea     r8d, [rdx+2]
0x180015c6b  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180015c72  mov     rax, rdi
0x180015c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c7a  nop
0x180015c7b  mov     rcx, [rsp+88h+var_18]
0x180015c80  xor     rcx, rsp; StackCookie
0x180015c83  call    __security_check_cookie
0x180015c88  lea     r11, [rsp+88h+var_8]
0x180015c90  mov     rbx, [r11+18h]
0x180015c94  mov     rsi, [r11+20h]
0x180015c98  mov     rsp, r11
0x180015c9b  pop     rdi
0x180015c9c  retn
```
