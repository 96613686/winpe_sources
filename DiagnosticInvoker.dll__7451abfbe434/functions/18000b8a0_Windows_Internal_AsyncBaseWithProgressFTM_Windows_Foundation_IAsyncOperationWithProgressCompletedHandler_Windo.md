# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnProgress(Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> * *)

- ea: `0x18000b8a0`
- end: `0x18000b98d`
- name: `?GetOnProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAU?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@3@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ebb0`

## callees

- `0x18000b8a0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b8db`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b8db`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnProgress(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // edi
  signed __int32 i; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed __int32 v9[10]; // [rsp+0h] [rbp-28h] BYREF
  signed __int32 v10; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v10 = -2;
  _InterlockedCompareExchange(&v10, *(_DWORD *)(a1 + 56), -2);
  if ( v10 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL, 0);
  }
  else
  {
    v3 = 0;
    for ( i = *(_DWORD *)(a1 + 160); i > 0; i = *(_DWORD *)(a1 + 160) )
    {
      if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 160), i + 1, i) )
      {
        v5 = *(_QWORD *)(a1 + 144);
        *a2 = 0;
        if ( v5 )
        {
          v6 = *(_QWORD *)(a1 + 144);
          if ( v6 )
            v3 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v6 + 24LL))(
                   v6,
                   &GUID_a0422898_b50a_52e3_b461_53989308be12,
                   a2);
          else
            v3 = 0;
        }
        else
        {
          v3 = -2147024809;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 160), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v9, 0);
          v7 = *(_QWORD *)(a1 + 144);
          *(_QWORD *)(a1 + 144) = 0;
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        return v3;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000b8a0  mov     [rsp+arg_8], rbx
0x18000b8a5  push    rdi
0x18000b8a6  sub     rsp, 20h
0x18000b8aa  mov     rbx, rcx
0x18000b8ad  mov     qword ptr [rdx], 0
0x18000b8b4  mov     [rsp+28h+arg_0], 0FFFFFFFEh
0x18000b8bc  mov     r8d, [rcx+38h]
0x18000b8c0  mov     eax, [rsp+28h+arg_0]
0x18000b8c4  lock cmpxchg [rsp+28h+arg_0], r8d
0x18000b8cb  cmp     [rsp+28h+arg_0], 4
0x18000b8d0  jnz     short loc_18000B8E6
0x18000b8d2  xor     edx, edx
0x18000b8d4  mov     edi, 8000000Eh
0x18000b8d9  mov     ecx, edi
0x18000b8db  call    cs:__imp_RoOriginateError
0x18000b8e1  jmp     loc_18000B980
0x18000b8e6  xor     edi, edi
0x18000b8e8  mov     eax, [rcx+0A0h]
0x18000b8ee  jmp     short loc_18000B903
0x18000b8f0  lea     ecx, [rax+1]
0x18000b8f3  lock cmpxchg [rbx+0A0h], ecx
0x18000b8fb  jz      short loc_18000B909
0x18000b8fd  mov     eax, [rbx+0A0h]
0x18000b903  test    eax, eax
0x18000b905  jg      short loc_18000B8F0
0x18000b907  jmp     short loc_18000B980
0x18000b909  mov     rax, [rbx+90h]
0x18000b910  mov     [rdx], rdi
0x18000b913  test    rax, rax
0x18000b916  jz      short loc_18000B942
0x18000b918  mov     rcx, [rbx+90h]
0x18000b91f  test    rcx, rcx
0x18000b922  jnz     short loc_18000B928
0x18000b924  xor     edi, edi
0x18000b926  jmp     short loc_18000B940
0x18000b928  mov     rax, [rcx]
0x18000b92b  mov     r8, rdx
0x18000b92e  lea     rdx, _GUID_a0422898_b50a_52e3_b461_53989308be12
0x18000b935  mov     rax, [rax+18h]
0x18000b939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b93e  mov     edi, eax
0x18000b940  jmp     short loc_18000B947
0x18000b942  mov     edi, 80070057h
0x18000b947  or      eax, 0FFFFFFFFh
0x18000b94a  lock xadd [rbx+0A0h], eax
0x18000b952  cmp     eax, 1
0x18000b955  jnz     short loc_18000B980
0x18000b957  lock or [rsp+28h+var_28], 0
0x18000b95c  mov     rcx, [rbx+90h]
0x18000b963  mov     qword ptr [rbx+90h], 0
0x18000b96e  test    rcx, rcx
0x18000b971  jz      short loc_18000B980
0x18000b973  mov     rdx, [rcx]
0x18000b976  mov     rax, [rdx+10h]
0x18000b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97f  nop
0x18000b980  mov     eax, edi
0x18000b982  mov     rbx, [rsp+28h+arg_8]
0x18000b987  add     rsp, 20h
0x18000b98b  pop     rdi
0x18000b98c  retn
```
