# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(ulong *,_GUID * *)

- ea: `0x18000b300`
- end: `0x18000b379`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b380`

## callees

- `0x18000b300`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b322`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000036_0000_0000_c000_000000000046;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b;
  v5[3] = GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000b300  mov     [rsp+arg_0], rbx
0x18000b305  push    rdi
0x18000b306  sub     rsp, 20h
0x18000b30a  mov     qword ptr [r8], 0
0x18000b311  mov     ecx, 40h ; '@'; cb
0x18000b316  mov     dword ptr [rdx], 0
0x18000b31c  mov     rbx, r8
0x18000b31f  mov     rdi, rdx
0x18000b322  call    cs:__imp_CoTaskMemAlloc
0x18000b328  test    rax, rax
0x18000b32b  jnz     short loc_18000B334
0x18000b32d  mov     eax, 8007000Eh
0x18000b332  jmp     short loc_18000B36E
0x18000b334  movups  xmm0, xmmword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data1
0x18000b33b  movdqu  xmmword ptr [rax], xmm0
0x18000b33f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000b346  movdqu  xmmword ptr [rax+10h], xmm1
0x18000b34b  movups  xmm0, xmmword ptr cs:_GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b.Data1
0x18000b352  movdqu  xmmword ptr [rax+20h], xmm0
0x18000b357  movups  xmm1, xmmword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data1
0x18000b35e  movdqu  xmmword ptr [rax+30h], xmm1
0x18000b363  mov     dword ptr [rdi], 4
0x18000b369  mov     [rbx], rax
0x18000b36c  xor     eax, eax
0x18000b36e  mov     rbx, [rsp+28h+arg_0]
0x18000b373  add     rsp, 20h
0x18000b377  pop     rdi
0x18000b378  retn
```
