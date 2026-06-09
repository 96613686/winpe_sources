# _Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__1_Microsoft::WRL::AsyncOptions__1_0_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion_::_1_::dtor$4

- ea: `0x1800103c5`
- end: `0x1800103d1`
- name: `_Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__1_Microsoft::WRL::AsyncOptions__1_0_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800085f4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__1_Microsoft::WRL::AsyncOptions__1_0__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>>(a2 + 80);
}

```

## disassembly

```asm
0x1800103c5  lea     rcx, [rdx+50h]
0x1800103cc  jmp     ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>>(void)
```
