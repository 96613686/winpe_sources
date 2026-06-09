# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::PutOnComplete

- ea: `0x18000d1c0`
- end: `0x18000d306`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::PutOnComplete`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000d1c0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d2dd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d2dd`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // rax
  void (__fastcall *v7)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD); // rax
  signed __int32 v8; // edx
  signed __int32 v10[8]; // [rsp+0h] [rbp-60h] BYREF
  __int64 v11; // [rsp+20h] [rbp-40h]
  int v12; // [rsp+28h] [rbp-38h]
  GUID v13; // [rsp+40h] [rbp-20h] BYREF
  signed __int32 v14; // [rsp+50h] [rbp-10h] BYREF

  v14 = -2;
  _InterlockedCompareExchange(&v14, *(_DWORD *)(a1 + 56), -2);
  if ( v14 == 4 )
  {
    v4 = -2147483634;
LABEL_16:
    RoOriginateError(v4);
    return v4;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), 1, 0) )
  {
    v4 = -2147483624;
    goto LABEL_16;
  }
  v4 = 0;
  if ( a2 )
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
  if ( *(_QWORD *)(a1 + 24) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = a2;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  _InterlockedOr(v10, 0);
  _InterlockedAdd((volatile signed __int32 *)(a1 + 32), 1u);
  if ( Microsoft::WRL::gCausality )
  {
    v6 = *(_QWORD *)Microsoft::WRL::gCausality;
    v12 = 0;
    v11 = a1;
    v7 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD))(v6 + 64);
    v13 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    v7(Microsoft::WRL::gCausality, 2, 2, &v13, a1, 0);
  }
  v8 = *(_DWORD *)(a1 + 56);
  v14 = -2;
  _InterlockedCompareExchange(&v14, v8, -2);
  if ( (unsigned int)(v14 - 1) <= 3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x18000d1c0  mov     [rsp-18h+arg_8], rbx
0x18000d1c5  mov     [rsp-18h+arg_10], rsi
0x18000d1ca  push    rbp
0x18000d1cb  push    rdi
0x18000d1cc  push    r14
0x18000d1ce  mov     rbp, rsp
0x18000d1d1  sub     rsp, 60h
0x18000d1d5  mov     rax, cs:__security_cookie
0x18000d1dc  xor     rax, rsp
0x18000d1df  mov     [rbp+var_8], rax
0x18000d1e3  mov     rbx, rcx
0x18000d1e6  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d1ed  mov     ecx, [rcx+38h]
0x18000d1f0  mov     rdi, rdx
0x18000d1f3  mov     eax, [rbp+var_10]
0x18000d1f6  lock cmpxchg [rbp+var_10], ecx
0x18000d1fb  cmp     [rbp+var_10], 4
0x18000d1ff  jnz     short loc_18000D20B
0x18000d201  mov     esi, 8000000Eh
0x18000d206  jmp     loc_18000D2D9
0x18000d20b  xor     eax, eax
0x18000d20d  lea     r14d, [rax+1]
0x18000d211  lock cmpxchg [rbx+14h], r14d
0x18000d217  jnz     loc_18000D2D4
0x18000d21d  xor     esi, esi
0x18000d21f  test    rdi, rdi
0x18000d222  jz      short loc_18000D22F
0x18000d224  mov     rax, [rdx]
0x18000d227  mov     rcx, [rax+18h]
0x18000d22b  mov     [rbx+28h], rcx
0x18000d22f  cmp     [rbx+18h], rdi
0x18000d233  jz      short loc_18000D262
0x18000d235  test    rdi, rdi
0x18000d238  jz      short loc_18000D249
0x18000d23a  mov     rax, [rdx]
0x18000d23d  mov     rcx, rdi
0x18000d240  mov     rax, [rax+8]
0x18000d244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d249  mov     rcx, [rbx+18h]
0x18000d24d  mov     [rbx+18h], rdi
0x18000d251  test    rcx, rcx
0x18000d254  jz      short loc_18000D262
0x18000d256  mov     rax, [rcx]
0x18000d259  mov     rax, [rax+10h]
0x18000d25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d262  lock or [rsp+60h+var_60], esi
0x18000d266  lock add [rbx+20h], r14d
0x18000d26b  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000d272  test    rcx, rcx
0x18000d275  jz      short loc_18000D2A4
0x18000d277  mov     rax, [rcx]
0x18000d27a  lea     r9, [rbp+var_20]
0x18000d27e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000d285  mov     edx, 2
0x18000d28a  mov     [rsp+60h+var_38], esi
0x18000d28e  mov     r8d, edx
0x18000d291  mov     [rsp+60h+var_40], rbx
0x18000d296  mov     rax, [rax+40h]
0x18000d29a  movdqu  [rbp+var_20], xmm0
0x18000d29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2a4  mov     edx, [rbx+38h]
0x18000d2a7  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d2ae  mov     eax, [rbp+var_10]
0x18000d2b1  lock cmpxchg [rbp+var_10], edx
0x18000d2b6  mov     edx, [rbp+var_10]
0x18000d2b9  dec     edx
0x18000d2bb  cmp     edx, 3
0x18000d2be  ja      short loc_18000D2E3
0x18000d2c0  mov     rax, [rbx]
0x18000d2c3  mov     rcx, rbx
0x18000d2c6  mov     rax, [rax+80h]
0x18000d2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2d2  jmp     short loc_18000D2E3
0x18000d2d4  mov     esi, 80000018h
0x18000d2d9  xor     edx, edx
0x18000d2db  mov     ecx, esi
0x18000d2dd  call    cs:__imp_RoOriginateError
0x18000d2e3  mov     eax, esi
0x18000d2e5  mov     rcx, [rbp+var_8]
0x18000d2e9  xor     rcx, rsp; StackCookie
0x18000d2ec  call    __security_check_cookie
0x18000d2f1  lea     r11, [rsp+60h+var_s0]
0x18000d2f6  mov     rbx, [r11+28h]
0x18000d2fa  mov     rsi, [r11+30h]
0x18000d2fe  mov     rsp, r11
0x18000d301  pop     r14
0x18000d303  pop     rdi
0x18000d304  pop     rbp
0x18000d305  retn
```
