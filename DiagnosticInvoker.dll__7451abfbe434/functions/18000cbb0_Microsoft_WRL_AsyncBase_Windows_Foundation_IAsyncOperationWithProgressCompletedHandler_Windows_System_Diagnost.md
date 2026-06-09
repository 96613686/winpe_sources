# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> *)

- ea: `0x18000cbb0`
- end: `0x18000cce5`
- name: `?PutOnComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cbb0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ccc8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ccc8`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  signed __int32 v7[8]; // [rsp+0h] [rbp-50h] BYREF
  GUID v8; // [rsp+40h] [rbp-10h] BYREF
  signed __int32 v9; // [rsp+70h] [rbp+20h] BYREF

  v9 = -2;
  _InterlockedCompareExchange(&v9, *(_DWORD *)(a1 + 56), -2);
  if ( v9 == 4 )
  {
    v4 = -2147483634;
LABEL_16:
    RoOriginateError(v4, 0);
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
  _InterlockedOr(v7, 0);
  _InterlockedAdd((volatile signed __int32 *)(a1 + 32), 1u);
  if ( Microsoft::WRL::gCausality )
  {
    v8 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL))(
      Microsoft::WRL::gCausality,
      2,
      2,
      &v8,
      a1,
      0);
  }
  v9 = -2;
  _InterlockedCompareExchange(&v9, *(_DWORD *)(a1 + 56), -2);
  if ( (unsigned int)(v9 - 1) <= 3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x18000cbb0  mov     [rsp-18h+arg_8], rbx
0x18000cbb5  mov     [rsp-18h+arg_10], rsi
0x18000cbba  push    rbp
0x18000cbbb  push    rdi
0x18000cbbc  push    r14
0x18000cbbe  mov     rbp, rsp
0x18000cbc1  sub     rsp, 50h
0x18000cbc5  mov     rdi, rdx
0x18000cbc8  mov     rbx, rcx
0x18000cbcb  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000cbd2  mov     r8d, [rcx+38h]
0x18000cbd6  mov     eax, [rbp+arg_0]
0x18000cbd9  lock cmpxchg [rbp+arg_0], r8d
0x18000cbdf  cmp     [rbp+arg_0], 4
0x18000cbe3  jnz     short loc_18000CBEF
0x18000cbe5  mov     esi, 8000000Eh
0x18000cbea  jmp     loc_18000CCC4
0x18000cbef  xor     eax, eax
0x18000cbf1  lea     r14d, [rax+1]
0x18000cbf5  lock cmpxchg [rcx+14h], r14d
0x18000cbfb  jnz     loc_18000CCBF
0x18000cc01  xor     esi, esi
0x18000cc03  test    rdi, rdi
0x18000cc06  jz      short loc_18000CC13
0x18000cc08  mov     rax, [rdx]
0x18000cc0b  mov     rcx, [rax+18h]
0x18000cc0f  mov     [rbx+28h], rcx
0x18000cc13  cmp     [rbx+18h], rdi
0x18000cc17  jz      short loc_18000CC48
0x18000cc19  test    rdi, rdi
0x18000cc1c  jz      short loc_18000CC2E
0x18000cc1e  mov     rax, [rdx]
0x18000cc21  mov     rcx, rdi
0x18000cc24  mov     rax, [rax+8]
0x18000cc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc2d  nop
0x18000cc2e  mov     rcx, [rbx+18h]
0x18000cc32  mov     [rbx+18h], rdi
0x18000cc36  test    rcx, rcx
0x18000cc39  jz      short loc_18000CC48
0x18000cc3b  mov     rax, [rcx]
0x18000cc3e  mov     rax, [rax+10h]
0x18000cc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc47  nop
0x18000cc48  lock or [rsp+50h+var_50], 0
0x18000cc4d  lock add [rbx+20h], r14d
0x18000cc52  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000cc59  test    rcx, rcx
0x18000cc5c  jz      short loc_18000CC8F
0x18000cc5e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000cc65  movdqu  [rbp+var_10], xmm0
0x18000cc6a  mov     rax, [rcx]
0x18000cc6d  mov     [rsp+50h+var_28], 0
0x18000cc75  mov     [rsp+50h+var_30], rbx
0x18000cc7a  lea     r9, [rbp+var_10]
0x18000cc7e  mov     edx, 2
0x18000cc83  mov     r8d, edx
0x18000cc86  mov     rax, [rax+40h]
0x18000cc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc8f  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000cc96  mov     ecx, [rbx+38h]
0x18000cc99  mov     eax, [rbp+arg_0]
0x18000cc9c  lock cmpxchg [rbp+arg_0], ecx
0x18000cca1  mov     ecx, [rbp+arg_0]
0x18000cca4  dec     ecx
0x18000cca6  cmp     ecx, 3
0x18000cca9  ja      short loc_18000CCCE
0x18000ccab  mov     rax, [rbx]
0x18000ccae  mov     rcx, rbx
0x18000ccb1  mov     rax, [rax+80h]
0x18000ccb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccbd  jmp     short loc_18000CCCE
0x18000ccbf  mov     esi, 80000018h
0x18000ccc4  xor     edx, edx
0x18000ccc6  mov     ecx, esi
0x18000ccc8  call    cs:__imp_RoOriginateError
0x18000ccce  mov     eax, esi
0x18000ccd0  lea     r11, [rsp+50h+var_s0]
0x18000ccd5  mov     rbx, [r11+28h]
0x18000ccd9  mov     rsi, [r11+30h]
0x18000ccdd  mov     rsp, r11
0x18000cce0  pop     r14
0x18000cce2  pop     rdi
0x18000cce3  pop     rbp
0x18000cce4  retn
```
