# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete

- ea: `0x18000f588`
- end: `0x18000f607`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete`
- size: `127`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007264`
- `0x180007800`
- `0x180009570`
- `0x1800098d0`

## callees

- `0x180001dc0`
- `0x18000f588`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete(
        __int64 a1)
{
  signed __int32 v1; // edx
  __int64 v2; // rax
  __int64 result; // rax
  GUID v4; // [rsp+40h] [rbp-28h] BYREF
  signed __int32 v5; // [rsp+50h] [rbp-18h] BYREF

  if ( Microsoft::WRL::gCausality )
  {
    v1 = *(_DWORD *)(a1 + 56);
    v5 = 0;
    _InterlockedCompareExchange(&v5, v1, 0);
    v2 = *(_QWORD *)Microsoft::WRL::gCausality;
    v4 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, signed __int32))(v2 + 56))(
             Microsoft::WRL::gCausality,
             0,
             2,
             &v4,
             a1,
             v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000f588  sub     rsp, 68h
0x18000f58c  mov     rax, cs:__security_cookie
0x18000f593  xor     rax, rsp
0x18000f596  mov     [rsp+68h+var_10], rax
0x18000f59b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, 0; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f5a3  mov     r8, rcx
0x18000f5a6  jz      short loc_18000F5F5
0x18000f5a8  mov     edx, [rcx+38h]
0x18000f5ab  mov     [rsp+68h+var_18], 0
0x18000f5b3  mov     eax, [rsp+68h+var_18]
0x18000f5b7  lock cmpxchg [rsp+68h+var_18], edx
0x18000f5bd  mov     edx, [rsp+68h+var_18]
0x18000f5c1  lea     r9, [rsp+68h+var_28]
0x18000f5c6  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f5cd  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000f5d4  mov     [rsp+68h+var_40], edx
0x18000f5d8  xor     edx, edx
0x18000f5da  mov     [rsp+68h+var_48], r8
0x18000f5df  mov     rax, [rcx]
0x18000f5e2  movdqu  [rsp+68h+var_28], xmm0
0x18000f5e8  lea     r8d, [rdx+2]
0x18000f5ec  mov     rax, [rax+38h]
0x18000f5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5f5  mov     rcx, [rsp+68h+var_10]
0x18000f5fa  xor     rcx, rsp; StackCookie
0x18000f5fd  call    __security_check_cookie
0x18000f602  add     rsp, 68h
0x18000f606  retn
```
