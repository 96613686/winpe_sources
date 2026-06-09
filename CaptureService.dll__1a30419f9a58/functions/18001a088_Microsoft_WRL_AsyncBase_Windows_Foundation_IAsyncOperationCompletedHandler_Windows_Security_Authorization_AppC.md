# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18001a088`
- end: `0x18001a139`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a010`

## callees

- `0x180002e60`
- `0x18000b894`
- `0x18001a088`
- `0x180022010`

## string_xrefs

- `0x18001a0c3`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>`

## pseudocode

```c
struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
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
    *(_QWORD *)&v6.Data1 = L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Security.Authorization.AppCapabil"
                            "ityAccess.AppCapabilityAccessStatus>";
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
0x18001a088  mov     r11, rsp
0x18001a08b  mov     [r11+10h], rbx
0x18001a08f  mov     [r11+18h], rsi
0x18001a093  push    rdi
0x18001a094  sub     rsp, 80h
0x18001a09b  mov     rax, cs:__security_cookie
0x18001a0a2  xor     rax, rsp
0x18001a0a5  mov     [rsp+88h+var_18], rax
0x18001a0aa  mov     rsi, rcx
0x18001a0ad  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001a0b4  test    rax, rax
0x18001a0b7  jz      short loc_18001A117
0x18001a0b9  mov     rax, [rax]
0x18001a0bc  mov     rdi, [rax+30h]
0x18001a0c0  mov     ebx, [rcx+40h]
0x18001a0c3  lea     rax, aWindowsFoundat_1; "Windows.Foundation.AsyncOperationComple"...
0x18001a0ca  mov     [r11-48h], rax
0x18001a0ce  lea     rdx, [r11-48h]
0x18001a0d2  lea     rcx, [r11-38h]
0x18001a0d6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001a0db  nop
0x18001a0dc  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18001a0e3  movdqu  [rsp+88h+var_48], xmm0
0x18001a0e9  mov     [rsp+88h+var_58], rbx
0x18001a0ee  mov     rcx, [rax+18h]
0x18001a0f2  mov     [rsp+88h+var_60], rcx
0x18001a0f7  mov     [rsp+88h+var_68], rsi
0x18001a0fc  lea     r9, [rsp+88h+var_48]
0x18001a101  xor     edx, edx
0x18001a103  lea     r8d, [rdx+2]
0x18001a107  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001a10e  mov     rax, rdi
0x18001a111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a116  nop
0x18001a117  mov     rcx, [rsp+88h+var_18]
0x18001a11c  xor     rcx, rsp; StackCookie
0x18001a11f  call    __security_check_cookie
0x18001a124  lea     r11, [rsp+88h+var_8]
0x18001a12c  mov     rbx, [r11+18h]
0x18001a130  mov     rsi, [r11+20h]
0x18001a134  mov     rsp, r11
0x18001a137  pop     rdi
0x18001a138  retn
```
