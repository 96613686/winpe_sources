# _Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject_::_1_::dtor$1

- ea: `0x1800103fb`
- end: `0x180010407`
- name: `_Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800087e4`

## pseudocode

```c
void __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 88));
}

```

## disassembly

```asm
0x1800103fb  lea     rcx, [rdx+58h]; this
0x180010402  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
