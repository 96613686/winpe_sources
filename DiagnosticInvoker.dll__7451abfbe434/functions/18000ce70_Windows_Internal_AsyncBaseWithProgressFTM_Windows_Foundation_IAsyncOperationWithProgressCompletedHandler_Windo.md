# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnProgress(Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> *)

- ea: `0x18000ce70`
- end: `0x18000cfb8`
- name: `?PutOnProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@3@@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed40`

## callees

- `0x18000ce70`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ceab`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ceab`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000cf21`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000cf21`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnProgress(
        __int64 a1,
        __int64 a2)
{
  unsigned int AgileReference; // ebx
  __int64 *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed __int32 v9[8]; // [rsp+0h] [rbp-58h] BYREF
  GUID v10; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = -2;
  _InterlockedCompareExchange(&v11, *(_DWORD *)(a1 + 56), -2);
  if ( v11 == 4 )
  {
    AgileReference = -2147483634;
    RoOriginateError(2147483662LL, 0);
  }
  else if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 164)) == 1 )
  {
    v5 = (__int64 *)(a1 + 144);
    v6 = *(_QWORD *)(a1 + 144);
    *v5 = 0;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v7 = *v5;
    if ( a2 )
    {
      if ( v7 )
      {
        *v5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      AgileReference = RoGetAgileReference(0, &GUID_a0422898_b50a_52e3_b461_53989308be12, a2, v5);
      *(_QWORD *)(a1 + 152) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 160));
    }
    else
    {
      *v5 = 0;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      AgileReference = 0;
    }
    _InterlockedOr(v9, 0);
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
  }
  else
  {
    return (unsigned int)-2147483624;
  }
  return AgileReference;
}

```

## disassembly

```asm
0x18000ce70  mov     rax, rsp
0x18000ce73  mov     [rax+10h], rbx
0x18000ce77  mov     [rax+18h], rsi
0x18000ce7b  push    rdi
0x18000ce7c  sub     rsp, 50h
0x18000ce80  mov     rsi, rdx
0x18000ce83  mov     rdi, rcx
0x18000ce86  mov     dword ptr [rax+8], 0FFFFFFFEh
0x18000ce8d  mov     r8d, [rcx+38h]
0x18000ce91  mov     eax, [rax+8]
0x18000ce94  lock cmpxchg [rsp+58h+arg_0], r8d
0x18000ce9b  cmp     [rsp+58h+arg_0], 4
0x18000cea0  jnz     short loc_18000CEB6
0x18000cea2  xor     edx, edx
0x18000cea4  mov     ebx, 8000000Eh
0x18000cea9  mov     ecx, ebx
0x18000ceab  call    cs:__imp_RoOriginateError
0x18000ceb1  jmp     loc_18000CFA6
0x18000ceb6  mov     eax, 1
0x18000cebb  lock xadd [rcx+0A4h], eax
0x18000cec3  inc     eax
0x18000cec5  cmp     eax, 1
0x18000cec8  jnz     loc_18000CFA1
0x18000cece  lea     rbx, [rcx+90h]
0x18000ced5  mov     rcx, [rbx]
0x18000ced8  mov     qword ptr [rbx], 0
0x18000cedf  test    rcx, rcx
0x18000cee2  jz      short loc_18000CEF1
0x18000cee4  mov     rax, [rcx]
0x18000cee7  mov     rax, [rax+10h]
0x18000ceeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cef0  nop
0x18000cef1  mov     rcx, [rbx]
0x18000cef4  test    rsi, rsi
0x18000cef7  jz      short loc_18000CF40
0x18000cef9  test    rcx, rcx
0x18000cefc  jz      short loc_18000CF12
0x18000cefe  mov     qword ptr [rbx], 0
0x18000cf05  mov     rax, [rcx]
0x18000cf08  mov     rax, [rax+10h]
0x18000cf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf11  nop
0x18000cf12  mov     r9, rbx
0x18000cf15  mov     r8, rsi
0x18000cf18  lea     rdx, _GUID_a0422898_b50a_52e3_b461_53989308be12
0x18000cf1f  xor     ecx, ecx
0x18000cf21  call    cs:__imp_RoGetAgileReference
0x18000cf27  mov     ebx, eax
0x18000cf29  mov     rax, [rsi]
0x18000cf2c  mov     rcx, [rax+18h]
0x18000cf30  mov     [rdi+98h], rcx
0x18000cf37  lock inc dword ptr [rdi+0A0h]
0x18000cf3e  jmp     short loc_18000CF5B
0x18000cf40  mov     qword ptr [rbx], 0
0x18000cf47  test    rcx, rcx
0x18000cf4a  jz      short loc_18000CF59
0x18000cf4c  mov     rax, [rcx]
0x18000cf4f  mov     rax, [rax+10h]
0x18000cf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf58  nop
0x18000cf59  xor     ebx, ebx
0x18000cf5b  lock or [rsp+58h+var_58], 0
0x18000cf60  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000cf67  test    rcx, rcx
0x18000cf6a  jz      short loc_18000CFA6
0x18000cf6c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000cf73  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18000cf79  mov     rax, [rcx]
0x18000cf7c  mov     [rsp+58h+var_30], 0
0x18000cf84  mov     [rsp+58h+var_38], rdi
0x18000cf89  lea     r9, [rsp+58h+var_18]
0x18000cf8e  mov     edx, 2
0x18000cf93  mov     r8d, edx
0x18000cf96  mov     rax, [rax+40h]
0x18000cf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf9f  jmp     short loc_18000CFA6
0x18000cfa1  mov     ebx, 80000018h
0x18000cfa6  mov     eax, ebx
0x18000cfa8  mov     rbx, [rsp+58h+arg_8]
0x18000cfad  mov     rsi, [rsp+58h+arg_10]
0x18000cfb2  add     rsp, 50h
0x18000cfb6  pop     rdi
0x18000cfb7  retn
```
