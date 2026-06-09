# Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180008240`
- end: `0x18000825d`
- name: `?GetRuntimeClassName@PlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180008256`

## pseudocode

```c
HRESULT __fastcall Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo::GetRuntimeClassName(
        Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.Diagnostics.TraceReporting.PlatformDiagnosticTraceInfo", 0x45u, a2);
}

```

## disassembly

```asm
0x180008240  mov     qword ptr [rdx], 0
0x180008247  lea     rcx, ?RuntimeClass_Windows_System_Diagnostics_TraceReporting_PlatformDiagnosticTraceInfo@@3QBGB; "Windows.System.Diagnostics.TraceReporti"...
0x18000824e  mov     r8, rdx
0x180008251  mov     edx, 45h ; 'E'
0x180008256  jmp     cs:__imp_WindowsCreateString
```
