# _Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f__&__::_1_::dtor$1

- ea: `0x1800102a1`
- end: `0x1800102ad`
- name: `_Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f__&__::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800084b0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f_____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return Windows::Internal::AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>>::~AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>>(*(_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x1800102a1  mov     rcx, [rdx+60h]
0x1800102a8  jmp     ??1?$AsyncCallbackBase@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>>::~AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>>(void)
```
