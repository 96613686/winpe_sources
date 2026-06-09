# Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180008270`
- end: `0x18000828d`
- name: `?GetRuntimeClassName@PlatformDiagnosticTraceRuntimeInfo@TraceReporting@Diagnostics@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180008286`

## pseudocode

```c
HRESULT __fastcall Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo::GetRuntimeClassName(
        Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceRuntimeInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.Diagnostics.TraceReporting.PlatformDiagnosticTraceRuntimeInfo", 0x4Cu, a2);
}

```

## disassembly

```asm
0x180008270  mov     qword ptr [rdx], 0
0x180008277  lea     rcx, ?RuntimeClass_Windows_System_Diagnostics_TraceReporting_PlatformDiagnosticTraceRuntimeInfo@@3QBGB; "Windows.System.Diagnostics.TraceReporti"...
0x18000827e  mov     r8, rdx
0x180008281  mov     edx, 4Ch ; 'L'
0x180008286  jmp     cs:__imp_WindowsCreateString
```
