# _Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncOptions__1_0_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion_::_1_::dtor$1

- ea: `0x18001037d`
- end: `0x180010389`
- name: `_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncOptions__1_0_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800086d0`

## pseudocode

```c
void __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncOptions__1_0__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>((__int64 *)(a2 + 120));
}

```

## disassembly

```asm
0x18001037d  lea     rcx, [rdx+78h]; void *
0x180010384  jmp     ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
```
