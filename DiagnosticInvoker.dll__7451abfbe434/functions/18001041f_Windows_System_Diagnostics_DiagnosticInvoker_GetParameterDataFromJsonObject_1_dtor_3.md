# _Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject_::_1_::dtor$3

- ea: `0x18001041f`
- end: `0x18001042b`
- name: `_Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800087e4`

## pseudocode

```c
void __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 120));
}

```

## disassembly

```asm
0x18001041f  lea     rcx, [rdx+78h]; this
0x180010426  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
