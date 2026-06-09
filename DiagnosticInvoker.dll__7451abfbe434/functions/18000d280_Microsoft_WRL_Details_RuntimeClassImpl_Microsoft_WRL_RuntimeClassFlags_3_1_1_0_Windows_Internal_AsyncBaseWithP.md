# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000d280`
- end: `0x18000d3d9`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `345`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d3e0`
- `0x18000d3f0`
- `0x18000d410`
- `0x18000d430`
- `0x18000d450`
- `0x18000d470`
- `0x18000d490`

## callees

- `0x18000a0e4`
- `0x18000d280`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int CanCastTo; // ebx
  int v5; // eax

  *a3 = 0;
  if ( !*a2 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_15;
    }
    v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
LABEL_9:
    if ( a2[3] == v3 )
    {
      *a3 = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      return 0;
    }
    goto LABEL_15;
  }
  if ( *a2 == -1350114592 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_15;
    }
    v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
    goto LABEL_9;
  }
  if ( *a2 == 54
    && a2[1] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000036_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data4[4] )
  {
LABEL_31:
    *a3 = a1;
    CanCastTo = 0;
    goto LABEL_33;
  }
LABEL_15:
  if ( *a2 == -1796592748 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
    {
      goto LABEL_25;
    }
    v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
  }
  else
  {
    if ( *a2 != 3
      || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_25;
    }
    v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] == v5 )
  {
    *a3 = a1 + 80;
    CanCastTo = 0;
    goto LABEL_26;
  }
LABEL_25:
  CanCastTo = -2147467262;
LABEL_26:
  if ( CanCastTo != -2147467262 )
    goto LABEL_33;
  a1 += 168;
  if ( *a2 == 56
    && a2[1] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_31;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(
                a1 + 8,
                a2,
                a3);
LABEL_33:
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x18000d280  push    rbx
0x18000d282  sub     rsp, 20h
0x18000d286  mov     qword ptr [r8], 0
0x18000d28d  cmp     dword ptr [rdx], 0
0x18000d290  jnz     short loc_18000D2B0
0x18000d292  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000d298  cmp     [rdx+4], eax
0x18000d29b  jnz     short loc_18000D319
0x18000d29d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000d2a3  cmp     [rdx+8], eax
0x18000d2a6  jnz     short loc_18000D319
0x18000d2a8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000d2ae  jmp     short loc_18000D2D4
0x18000d2b0  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000d2b6  jnz     short loc_18000D2EF
0x18000d2b8  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000d2be  cmp     [rdx+4], eax
0x18000d2c1  jnz     short loc_18000D319
0x18000d2c3  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000d2c9  cmp     [rdx+8], eax
0x18000d2cc  jnz     short loc_18000D319
0x18000d2ce  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000d2d4  cmp     [rdx+0Ch], eax
0x18000d2d7  jnz     short loc_18000D319
0x18000d2d9  mov     [r8], rcx
0x18000d2dc  mov     rax, [rcx]
0x18000d2df  mov     rax, [rax+8]
0x18000d2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2e8  xor     ebx, ebx
0x18000d2ea  jmp     loc_18000D3D1
0x18000d2ef  cmp     dword ptr [rdx], 36h ; '6'
0x18000d2f2  jnz     short loc_18000D319
0x18000d2f4  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x18000d2fa  cmp     [rdx+4], eax
0x18000d2fd  jnz     short loc_18000D319
0x18000d2ff  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x18000d305  cmp     [rdx+8], eax
0x18000d308  jnz     short loc_18000D319
0x18000d30a  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x18000d310  cmp     [rdx+0Ch], eax
0x18000d313  jz      loc_18000D3AB
0x18000d319  lea     r9, [rcx+50h]
0x18000d31d  mov     r10d, 80004002h
0x18000d323  cmp     dword ptr [rdx], 94EA2B94h
0x18000d329  jnz     short loc_18000D349
0x18000d32b  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x18000d331  cmp     [rdx+4], eax
0x18000d334  jnz     short loc_18000D376
0x18000d336  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x18000d33c  cmp     [rdx+8], eax
0x18000d33f  jnz     short loc_18000D376
0x18000d341  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000d347  jmp     short loc_18000D36A
0x18000d349  cmp     dword ptr [rdx], 3
0x18000d34c  jnz     short loc_18000D376
0x18000d34e  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x18000d354  cmp     [rdx+4], eax
0x18000d357  jnz     short loc_18000D376
0x18000d359  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x18000d35f  cmp     [rdx+8], eax
0x18000d362  jnz     short loc_18000D376
0x18000d364  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000d36a  cmp     [rdx+0Ch], eax
0x18000d36d  jnz     short loc_18000D376
0x18000d36f  mov     [r8], r9
0x18000d372  xor     ebx, ebx
0x18000d374  jmp     short loc_18000D379
0x18000d376  mov     ebx, r10d
0x18000d379  cmp     ebx, r10d
0x18000d37c  jnz     short loc_18000D3BD
0x18000d37e  add     rcx, 0A8h
0x18000d385  cmp     dword ptr [rdx], 38h ; '8'
0x18000d388  jnz     short loc_18000D3B2
0x18000d38a  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x18000d390  cmp     [rdx+4], eax
0x18000d393  jnz     short loc_18000D3B2
0x18000d395  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x18000d39b  cmp     [rdx+8], eax
0x18000d39e  jnz     short loc_18000D3B2
0x18000d3a0  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x18000d3a6  cmp     [rdx+0Ch], eax
0x18000d3a9  jnz     short loc_18000D3B2
0x18000d3ab  mov     [r8], rcx
0x18000d3ae  xor     ebx, ebx
0x18000d3b0  jmp     short loc_18000D3BD
0x18000d3b2  add     rcx, 8
0x18000d3b6  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@UIAsyncOperationLocal@Internal@6@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)
0x18000d3bb  mov     ebx, eax
0x18000d3bd  test    ebx, ebx
0x18000d3bf  js      short loc_18000D3D1
0x18000d3c1  mov     rcx, [r8]
0x18000d3c4  mov     rdx, [rcx]
0x18000d3c7  mov     rax, [rdx+8]
0x18000d3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d0  nop
0x18000d3d1  mov     eax, ebx
0x18000d3d3  add     rsp, 20h
0x18000d3d7  pop     rbx
0x18000d3d8  retn
```
