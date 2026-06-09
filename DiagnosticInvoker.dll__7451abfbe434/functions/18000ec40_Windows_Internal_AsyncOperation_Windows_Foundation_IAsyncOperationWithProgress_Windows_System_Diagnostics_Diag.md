# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Completed(Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> *)

- ea: `0x18000ec40`
- end: `0x18000ec98`
- name: `?put_Completed@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@3@@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x18000ec40`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Completed(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  unsigned int v4; // edi

  v3 = a1 - 176;
  if ( a1 != 176 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(a1 - 176);
  v4 = Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
         v3,
         a2);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return v4;
}

```

## disassembly

```asm
0x18000ec40  mov     [rsp+arg_0], rbx
0x18000ec45  push    rdi
0x18000ec46  sub     rsp, 20h
0x18000ec4a  mov     rdi, rdx
0x18000ec4d  lea     rbx, [rcx-0B0h]
0x18000ec54  test    rbx, rbx
0x18000ec57  jz      short loc_18000EC69
0x18000ec59  mov     rax, [rbx]
0x18000ec5c  mov     rcx, rbx
0x18000ec5f  mov     rax, [rax+8]
0x18000ec63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec68  nop
0x18000ec69  mov     rdx, rdi
0x18000ec6c  mov     rcx, rbx
0x18000ec6f  call    ?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@3@@Z; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> *)
0x18000ec74  mov     edi, eax
0x18000ec76  test    rbx, rbx
0x18000ec79  jz      short loc_18000EC8B
0x18000ec7b  mov     rdx, [rbx]
0x18000ec7e  mov     rcx, rbx
0x18000ec81  mov     rax, [rdx+10h]
0x18000ec85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8a  nop
0x18000ec8b  mov     eax, edi
0x18000ec8d  mov     rbx, [rsp+28h+arg_0]
0x18000ec92  add     rsp, 20h
0x18000ec96  pop     rdi
0x18000ec97  retn
```
