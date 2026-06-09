# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18001ba18`
- end: `0x18001bac9`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b9a0`

## callees

- `0x180002dc0`
- `0x1800132f8`
- `0x18001ba18`
- `0x18002b010`

## string_xrefs

- `0x18001ba53`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.System.ProcessLauncherResult>`

## pseudocode

```c
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    *(_QWORD *)&v6.Data1 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.System.ProcessLauncherResult>";
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
0x18001ba18  mov     r11, rsp
0x18001ba1b  mov     [r11+10h], rbx
0x18001ba1f  mov     [r11+18h], rsi
0x18001ba23  push    rdi
0x18001ba24  sub     rsp, 80h
0x18001ba2b  mov     rax, cs:__security_cookie
0x18001ba32  xor     rax, rsp
0x18001ba35  mov     [rsp+88h+var_18], rax
0x18001ba3a  mov     rsi, rcx
0x18001ba3d  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001ba44  test    rax, rax
0x18001ba47  jz      short loc_18001BAA7
0x18001ba49  mov     rax, [rax]
0x18001ba4c  mov     rdi, [rax+30h]
0x18001ba50  mov     ebx, [rcx+40h]
0x18001ba53  lea     rax, aWindowsFoundat_1; "Windows.Foundation.AsyncOperationComple"...
0x18001ba5a  mov     [r11-48h], rax
0x18001ba5e  lea     rdx, [r11-48h]
0x18001ba62  lea     rcx, [r11-38h]
0x18001ba66  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ba6b  nop
0x18001ba6c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18001ba73  movdqu  [rsp+88h+var_48], xmm0
0x18001ba79  mov     [rsp+88h+var_58], rbx
0x18001ba7e  mov     rcx, [rax+18h]
0x18001ba82  mov     [rsp+88h+var_60], rcx
0x18001ba87  mov     [rsp+88h+var_68], rsi
0x18001ba8c  lea     r9, [rsp+88h+var_48]
0x18001ba91  xor     edx, edx
0x18001ba93  lea     r8d, [rdx+2]
0x18001ba97  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001ba9e  mov     rax, rdi
0x18001baa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa6  nop
0x18001baa7  mov     rcx, [rsp+88h+var_18]
0x18001baac  xor     rcx, rsp; StackCookie
0x18001baaf  call    __security_check_cookie
0x18001bab4  lea     r11, [rsp+88h+var_8]
0x18001babc  mov     rbx, [r11+18h]
0x18001bac0  mov     rsi, [r11+20h]
0x18001bac4  mov     rsp, r11
0x18001bac7  pop     rdi
0x18001bac8  retn
```
