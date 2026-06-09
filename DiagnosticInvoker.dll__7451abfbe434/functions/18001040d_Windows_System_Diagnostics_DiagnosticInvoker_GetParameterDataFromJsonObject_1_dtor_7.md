# _Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject_::_1_::dtor$7

- ea: `0x18001040d`
- end: `0x180010419`
- name: `_Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000880c`

## pseudocode

```c
void __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject_::_1_::dtor_7(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 200));
}

```

## disassembly

```asm
0x18001040d  lea     rcx, [rdx+0C8h]; this
0x180010414  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
