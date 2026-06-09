# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Cancel

- ea: `0x1800089f0`
- end: `0x180008a61`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Cancel`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800089f0`
- `0x18000f698`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Cancel(
        __int64 a1)
{
  void (__fastcall *v2)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  GUID v4; // [rsp+40h] [rbp-18h] BYREF

  if ( Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState(
         a1,
         2) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1);
    if ( Microsoft::WRL::gCausality )
    {
      v2 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL);
      v4 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v2(Microsoft::WRL::gCausality, 1, 2, &v4, a1, 3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800089f0  push    rbx
0x1800089f2  sub     rsp, 50h
0x1800089f6  mov     edx, 2
0x1800089fb  mov     rbx, rcx
0x1800089fe  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TransitionToState
0x180008a03  test    al, al
0x180008a05  jz      short loc_180008A59
0x180008a07  mov     rax, [rbx]
0x180008a0a  mov     rcx, rbx
0x180008a0d  mov     rax, [rax+98h]
0x180008a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a19  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180008a20  test    rcx, rcx
0x180008a23  jz      short loc_180008A59
0x180008a25  mov     rax, [rcx]
0x180008a28  lea     r9, [rsp+58h+var_18]
0x180008a2d  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180008a34  mov     edx, 1
0x180008a39  mov     [rsp+58h+var_30], 3
0x180008a41  mov     [rsp+58h+var_38], rbx
0x180008a46  mov     rax, [rax+40h]
0x180008a4a  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180008a50  lea     r8d, [rdx+1]
0x180008a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a59  xor     eax, eax
0x180008a5b  add     rsp, 50h
0x180008a5f  pop     rbx
0x180008a60  retn
```
