# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> *)

- ea: `0x18000ccf0`
- end: `0x18000ce5e`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@3@@Z`
- size: `366`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec40`

## callees

- `0x18000ccf0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cd25`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cd25`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000cd95`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000cd95`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  int AgileReference; // edi
  __int64 *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed __int32 v9[8]; // [rsp+0h] [rbp-58h] BYREF
  GUID v10; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v11; // [rsp+80h] [rbp+28h] BYREF

  v11 = -2;
  _InterlockedCompareExchange(&v11, *(_DWORD *)(a1 + 56), -2);
  if ( v11 == 4 )
  {
    AgileReference = -2147483634;
    RoOriginateError(2147483662LL, 0);
    return (unsigned int)AgileReference;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 20)) != 1 )
    return (unsigned int)-2147483624;
  v5 = (__int64 *)(a1 + 120);
  v6 = *(_QWORD *)(a1 + 120);
  *v5 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *v5;
  if ( !a2 )
  {
    *v5 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    AgileReference = 0;
    goto LABEL_14;
  }
  if ( v7 )
  {
    *v5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  AgileReference = RoGetAgileReference(0, &GUID_390b0091_caf7_5b64_839d_4990ae7f753c, a2, v5);
  if ( AgileReference >= 0 )
  {
LABEL_14:
    if ( Microsoft::WRL::gCausality )
    {
      v10 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL))(
        Microsoft::WRL::gCausality,
        2,
        2,
        &v10,
        a1,
        0);
    }
    if ( a2 )
    {
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 136));
    }
    _InterlockedOr(v9, 0);
    v11 = -2;
    _InterlockedCompareExchange(&v11, *(_DWORD *)(a1 + 56), -2);
    if ( (unsigned int)(v11 - 1) <= 3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x18000ccf0  push    rbp
0x18000ccf2  push    rbx
0x18000ccf3  push    rsi
0x18000ccf4  push    rdi
0x18000ccf5  mov     rbp, rsp
0x18000ccf8  sub     rsp, 58h
0x18000ccfc  mov     rsi, rdx
0x18000ccff  mov     rbx, rcx
0x18000cd02  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000cd09  mov     r8d, [rcx+38h]
0x18000cd0d  mov     eax, [rbp+arg_0]
0x18000cd10  lock cmpxchg [rbp+arg_0], r8d
0x18000cd16  cmp     [rbp+arg_0], 4
0x18000cd1a  jnz     short loc_18000CD30
0x18000cd1c  xor     edx, edx
0x18000cd1e  mov     edi, 8000000Eh
0x18000cd23  mov     ecx, edi
0x18000cd25  call    cs:__imp_RoOriginateError
0x18000cd2b  jmp     loc_18000CE53
0x18000cd30  mov     eax, 1
0x18000cd35  lock xadd [rcx+14h], eax
0x18000cd3a  inc     eax
0x18000cd3c  cmp     eax, 1
0x18000cd3f  jnz     loc_18000CE4E
0x18000cd45  lea     rdi, [rcx+78h]
0x18000cd49  mov     rcx, [rdi]
0x18000cd4c  mov     qword ptr [rdi], 0
0x18000cd53  test    rcx, rcx
0x18000cd56  jz      short loc_18000CD65
0x18000cd58  mov     rax, [rcx]
0x18000cd5b  mov     rax, [rax+10h]
0x18000cd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd64  nop
0x18000cd65  mov     rcx, [rdi]
0x18000cd68  test    rsi, rsi
0x18000cd6b  jz      short loc_18000CDA7
0x18000cd6d  test    rcx, rcx
0x18000cd70  jz      short loc_18000CD86
0x18000cd72  mov     qword ptr [rdi], 0
0x18000cd79  mov     rax, [rcx]
0x18000cd7c  mov     rax, [rax+10h]
0x18000cd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd85  nop
0x18000cd86  mov     r9, rdi
0x18000cd89  mov     r8, rsi
0x18000cd8c  lea     rdx, _GUID_390b0091_caf7_5b64_839d_4990ae7f753c
0x18000cd93  xor     ecx, ecx
0x18000cd95  call    cs:__imp_RoGetAgileReference
0x18000cd9b  mov     edi, eax
0x18000cd9d  test    eax, eax
0x18000cd9f  js      loc_18000CE53
0x18000cda5  jmp     short loc_18000CDC2
0x18000cda7  mov     qword ptr [rdi], 0
0x18000cdae  test    rcx, rcx
0x18000cdb1  jz      short loc_18000CDC0
0x18000cdb3  mov     rax, [rcx]
0x18000cdb6  mov     rax, [rax+10h]
0x18000cdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdbf  nop
0x18000cdc0  xor     edi, edi
0x18000cdc2  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000cdc9  test    rcx, rcx
0x18000cdcc  jz      short loc_18000CDFF
0x18000cdce  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000cdd5  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000cdda  mov     rax, [rcx]
0x18000cddd  mov     [rsp+58h+var_30], 0
0x18000cde5  mov     [rsp+58h+var_38], rbx
0x18000cdea  lea     r9, [rbp+var_18]
0x18000cdee  mov     edx, 2
0x18000cdf3  mov     r8d, edx
0x18000cdf6  mov     rax, [rax+40h]
0x18000cdfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdff  test    rsi, rsi
0x18000ce02  jz      short loc_18000CE19
0x18000ce04  mov     rax, [rsi]
0x18000ce07  mov     rcx, [rax+18h]
0x18000ce0b  mov     [rbx+80h], rcx
0x18000ce12  lock inc dword ptr [rbx+88h]
0x18000ce19  lock or [rsp+58h+var_58], 0
0x18000ce1e  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000ce25  mov     ecx, [rbx+38h]
0x18000ce28  mov     eax, [rbp+arg_0]
0x18000ce2b  lock cmpxchg [rbp+arg_0], ecx
0x18000ce30  mov     ecx, [rbp+arg_0]
0x18000ce33  dec     ecx
0x18000ce35  cmp     ecx, 3
0x18000ce38  ja      short loc_18000CE53
0x18000ce3a  mov     rax, [rbx]
0x18000ce3d  mov     rcx, rbx
0x18000ce40  mov     rax, [rax+80h]
0x18000ce47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce4c  jmp     short loc_18000CE53
0x18000ce4e  mov     edi, 80000018h
0x18000ce53  mov     eax, edi
0x18000ce55  add     rsp, 58h
0x18000ce59  pop     rdi
0x18000ce5a  pop     rsi
0x18000ce5b  pop     rbx
0x18000ce5c  pop     rbp
0x18000ce5d  retn
```
