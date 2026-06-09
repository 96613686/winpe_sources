# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetRuntimeClassName`adjustor{176}' (HSTRING__ * *)

- ea: `0x18000c3f0`
- end: `0x18000c3fc`
- name: `?GetRuntimeClassName@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@WLA@EAAJPEAPEAUHSTRING__@@@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007250`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetRuntimeClassName(
        __int64 a1)
{
  return Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ActivateInstance(a1 - 176);
}

```

## disassembly

```asm
0x18000c3f0  sub     rcx, 0B0h
0x18000c3f7  jmp     ?ActivateInstance@?$ActivationFactory@UIDiagnosticInvokerStatics@Diagnostics@System@Windows@@VNil@Details@WRL@Microsoft@@V5678@$0A@@WRL@Microsoft@@UEAAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ActivateInstance(IInspectable * *)
```
