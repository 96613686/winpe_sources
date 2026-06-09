# _Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f__&__::_1_::dtor$0

- ea: `0x18001027c`
- end: `0x18001029b`
- name: `_Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f__&__::_1_::dtor$0`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022c0`

## pseudocode

```c
void __fastcall Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 96), (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x18001027c  push    rbp
0x18001027e  sub     rsp, 20h
0x180010282  mov     rbp, rdx
0x180010285  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001028c  mov     rcx, [rbp+60h]; void *
0x180010290  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010295  add     rsp, 20h
0x180010299  pop     rbp
0x18001029a  retn
```
