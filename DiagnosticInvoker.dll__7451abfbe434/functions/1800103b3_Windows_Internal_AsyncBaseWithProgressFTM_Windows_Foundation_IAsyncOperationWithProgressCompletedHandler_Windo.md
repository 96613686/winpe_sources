# _Windows::Internal::AsyncBaseWithProgressFTM_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::Foundation::IAsyncOperationProgressHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__1_Microsoft::WRL::AsyncOptions__1_0_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireProgress_::_1_::dtor$3

- ea: `0x1800103b3`
- end: `0x1800103bf`
- name: `_Windows::Internal::AsyncBaseWithProgressFTM_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::Foundation::IAsyncOperationProgressHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__1_Microsoft::WRL::AsyncOptions__1_0_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireProgress_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800086d0`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncBaseWithProgressFTM_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::Foundation::IAsyncOperationProgressHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__1_Microsoft::WRL::AsyncOptions__1_0__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireProgress_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((__int64 *)(a2 + 200));
}

```

## disassembly

```asm
0x1800103b3  lea     rcx, [rdx+0C8h]; void *
0x1800103ba  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
