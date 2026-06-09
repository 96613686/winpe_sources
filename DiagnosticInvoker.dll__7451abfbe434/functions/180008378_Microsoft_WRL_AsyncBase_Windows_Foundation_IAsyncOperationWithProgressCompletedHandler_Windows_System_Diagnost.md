# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::~AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)

- ea: `0x180008378`
- end: `0x18000842b`
- name: `??1?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAA@XZ`
- size: `179`
- prototype: `void **__fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008434`
- `0x180009c00`
- `0x180009c40`

## callees

- `0x180008378`
- `0x180011010`

## pseudocode

```c
void **__fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::~AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        __int64 a1)
{
  void **result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  GUID v5; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v6; // [rsp+60h] [rbp+8h] BYREF

  result = &Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)a1 = &Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  if ( !*(_DWORD *)(a1 + 16) && Microsoft::WRL::gCausality )
  {
    v6 = 0;
    _InterlockedCompareExchange(&v6, *(_DWORD *)(a1 + 56), 0);
    v5 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    result = (void **)(*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, signed __int32))(*(_QWORD *)Microsoft::WRL::gCausality + 56LL))(
                        Microsoft::WRL::gCausality,
                        0,
                        2,
                        &v5,
                        a1,
                        v6);
  }
  v3 = *(_QWORD *)(a1 + 48);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 48) = 0;
    result = (void **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *(_QWORD *)(a1 + 24);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 24) = 0;
    return (void **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return result;
}

```

## disassembly

```asm
0x180008378  push    rbx
0x18000837a  sub     rsp, 50h
0x18000837e  mov     rbx, rcx
0x180008381  lea     rax, ??_7?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@6B@; const Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x180008388  mov     [rcx], rax
0x18000838b  cmp     dword ptr [rcx+10h], 0
0x18000838f  jnz     short loc_1800083E9
0x180008391  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, 0; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180008399  jz      short loc_1800083E9
0x18000839b  mov     [rsp+58h+arg_0], 0
0x1800083a3  mov     edx, [rcx+38h]
0x1800083a6  mov     eax, [rsp+58h+arg_0]
0x1800083aa  lock cmpxchg [rsp+58h+arg_0], edx
0x1800083b0  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800083b7  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x1800083bd  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800083c4  mov     rax, [rcx]
0x1800083c7  mov     edx, [rsp+58h+arg_0]
0x1800083cb  mov     [rsp+58h+var_30], edx
0x1800083cf  mov     [rsp+58h+var_38], rbx
0x1800083d4  lea     r9, [rsp+58h+var_18]
0x1800083d9  xor     edx, edx
0x1800083db  lea     r8d, [rdx+2]
0x1800083df  mov     rax, [rax+38h]
0x1800083e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e8  nop
0x1800083e9  mov     rcx, [rbx+30h]
0x1800083ed  test    rcx, rcx
0x1800083f0  jz      short loc_180008407
0x1800083f2  mov     qword ptr [rbx+30h], 0
0x1800083fa  mov     rax, [rcx]
0x1800083fd  mov     rax, [rax+10h]
0x180008401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008406  nop
0x180008407  mov     rcx, [rbx+18h]
0x18000840b  test    rcx, rcx
0x18000840e  jz      short loc_180008425
0x180008410  mov     qword ptr [rbx+18h], 0
0x180008418  mov     rax, [rcx]
0x18000841b  mov     rax, [rax+10h]
0x18000841f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008424  nop
0x180008425  add     rsp, 50h
0x180008429  pop     rbx
0x18000842a  retn
```
