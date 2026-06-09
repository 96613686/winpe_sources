# _Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject_::_1_::dtor$0

- ea: `0x1800103e9`
- end: `0x1800103f5`
- name: `_Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800086d0`

## pseudocode

```c
void __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x1800103e9  lea     rcx, [rdx+68h]; void *
0x1800103f0  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
