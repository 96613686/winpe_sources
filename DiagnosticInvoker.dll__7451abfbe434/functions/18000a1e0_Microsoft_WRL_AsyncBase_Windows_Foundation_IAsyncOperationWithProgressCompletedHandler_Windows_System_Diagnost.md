# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Cancel(void)

- ea: `0x18000a1e0`
- end: `0x18000a274`
- name: `?Cancel@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a1e0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Cancel(
        volatile signed __int32 *a1)
{
  signed __int32 v1; // edx
  signed __int32 v3; // eax
  void (__fastcall *v4)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, volatile signed __int32 *, int); // rax
  GUID v6; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v7; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_DWORD *)a1 + 14);
  v7 = -2;
  _InterlockedCompareExchange(&v7, v1, -2);
  if ( !v7 )
  {
    v3 = _InterlockedCompareExchange(a1 + 14, 2, 0);
    if ( v3 == v7 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 152LL))(a1);
      if ( Microsoft::WRL::gCausality )
      {
        v4 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, volatile signed __int32 *, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL);
        v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        v4(Microsoft::WRL::gCausality, 1, 2, &v6, a1, 3);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a1e0  mov     [rsp+arg_8], rbx
0x18000a1e5  push    rdi
0x18000a1e6  sub     rsp, 50h
0x18000a1ea  mov     edx, [rcx+38h]
0x18000a1ed  mov     rbx, rcx
0x18000a1f0  mov     [rsp+58h+arg_0], 0FFFFFFFEh
0x18000a1f8  mov     eax, [rsp+58h+arg_0]
0x18000a1fc  lock cmpxchg [rsp+58h+arg_0], edx
0x18000a202  cmp     [rsp+58h+arg_0], 0
0x18000a207  jnz     short loc_18000A267
0x18000a209  mov     edi, 2
0x18000a20e  xor     eax, eax
0x18000a210  lock cmpxchg [rcx+38h], edi
0x18000a215  cmp     eax, [rsp+58h+arg_0]
0x18000a219  jnz     short loc_18000A267
0x18000a21b  mov     rax, [rcx]
0x18000a21e  mov     rax, [rax+98h]
0x18000a225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a22a  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a231  test    rcx, rcx
0x18000a234  jz      short loc_18000A267
0x18000a236  mov     rax, [rcx]
0x18000a239  lea     r9, [rsp+58h+var_18]
0x18000a23e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000a245  mov     [rsp+58h+var_30], 3
0x18000a24d  lea     edx, [rdi-1]
0x18000a250  mov     r8d, edi
0x18000a253  mov     [rsp+58h+var_38], rbx
0x18000a258  mov     rax, [rax+40h]
0x18000a25c  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18000a262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a267  mov     rbx, [rsp+58h+arg_8]
0x18000a26c  xor     eax, eax
0x18000a26e  add     rsp, 50h
0x18000a272  pop     rdi
0x18000a273  retn
```
