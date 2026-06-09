# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x18000e700`
- end: `0x18000e7ca`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `202`
- prototype: `char __fastcall(__int64, signed __int32, signed __int32)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ca80`
- `0x18000e8a8`

## callees

- `0x18000e700`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000e744`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000e744`

## pseudocode

```c
char __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        __int64 a1,
        signed __int32 a2,
        signed __int32 a3)
{
  char v4; // bl
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  signed __int32 v7; // eax
  GUID v9; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v10; // [rsp+70h] [rbp+18h] BYREF

  v10 = a3;
  v4 = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 60), a2, 0) )
  {
    v5 = (_QWORD *)(a1 + 48);
    v6 = *(_QWORD *)(a1 + 48);
    if ( v6 )
    {
      *v5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    GetRestrictedErrorInfo(v5);
    v10 = -2;
    _InterlockedCompareExchange(&v10, *(_DWORD *)(a1 + 56), -2);
    if ( !v10 && (v7 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), 3, 0), v7 == v10) )
    {
      v4 = 1;
      if ( Microsoft::WRL::gCausality )
      {
        v9 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL))(
          Microsoft::WRL::gCausality,
          2,
          2,
          &v9,
          a1,
          4);
      }
    }
    else
    {
      return 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000e700  mov     [rsp+arg_0], rbx
0x18000e705  mov     [rsp+arg_10], r8d
0x18000e70a  push    rdi
0x18000e70b  sub     rsp, 50h
0x18000e70f  mov     rdi, rcx
0x18000e712  xor     bl, bl
0x18000e714  xor     eax, eax
0x18000e716  lock cmpxchg [rcx+3Ch], edx
0x18000e71b  jnz     loc_18000E7BD
0x18000e721  lea     rbx, [rcx+30h]
0x18000e725  mov     rcx, [rbx]
0x18000e728  test    rcx, rcx
0x18000e72b  jz      short loc_18000E741
0x18000e72d  mov     qword ptr [rbx], 0
0x18000e734  mov     rax, [rcx]
0x18000e737  mov     rax, [rax+10h]
0x18000e73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e740  nop
0x18000e741  mov     rcx, rbx
0x18000e744  call    cs:__imp_GetRestrictedErrorInfo
0x18000e74a  mov     [rsp+58h+arg_10], 0FFFFFFFEh
0x18000e752  mov     ecx, [rdi+38h]
0x18000e755  mov     eax, [rsp+58h+arg_10]
0x18000e759  lock cmpxchg [rsp+58h+arg_10], ecx
0x18000e75f  cmp     [rsp+58h+arg_10], 0
0x18000e764  jnz     short loc_18000E778
0x18000e766  mov     ecx, 3
0x18000e76b  xor     eax, eax
0x18000e76d  lock cmpxchg [rdi+38h], ecx
0x18000e772  cmp     eax, [rsp+58h+arg_10]
0x18000e776  jz      short loc_18000E77C
0x18000e778  xor     bl, bl
0x18000e77a  jmp     short loc_18000E7BD
0x18000e77c  mov     bl, 1
0x18000e77e  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000e785  test    rcx, rcx
0x18000e788  jz      short loc_18000E7BD
0x18000e78a  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000e791  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18000e797  mov     rdx, [rcx]
0x18000e79a  mov     rax, [rdx+40h]
0x18000e79e  mov     [rsp+58h+var_30], 4
0x18000e7a6  mov     [rsp+58h+var_38], rdi
0x18000e7ab  lea     r9, [rsp+58h+var_18]
0x18000e7b0  mov     edx, 2
0x18000e7b5  mov     r8d, edx
0x18000e7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7bd  mov     al, bl
0x18000e7bf  mov     rbx, [rsp+58h+arg_0]
0x18000e7c4  add     rsp, 50h
0x18000e7c8  pop     rdi
0x18000e7c9  retn
```
