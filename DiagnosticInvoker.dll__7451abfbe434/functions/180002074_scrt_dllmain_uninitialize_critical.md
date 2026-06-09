# __scrt_dllmain_uninitialize_critical

- ea: `0x180002074`
- end: `0x180002088`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c08`

## callees

- `0x18000ed70`

## pseudocode

```c
char _scrt_dllmain_uninitialize_critical()
{
  Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_ShouldSetNoWake();
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_ShouldSetNoWake();
}

```

## disassembly

```asm
0x180002074  sub     rsp, 28h
0x180002078  xor     ecx, ecx
0x18000207a  call    ?v_ShouldSetNoWake@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@MEAA_NXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_ShouldSetNoWake(void)
0x18000207f  add     rsp, 28h
0x180002083  jmp     ?v_ShouldSetNoWake@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@MEAA_NXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::v_ShouldSetNoWake(void)
```
