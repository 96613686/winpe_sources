# Windows::System::Diagnostics::DiagnosticActionResult::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000f0a0`
- end: `0x18000f0bd`
- name: `?GetRuntimeClassName@DiagnosticActionResult@Diagnostics@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::Diagnostics::DiagnosticActionResult *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f0b6`

## pseudocode

```c
HRESULT __fastcall Windows::System::Diagnostics::DiagnosticActionResult::GetRuntimeClassName(
        Windows::System::Diagnostics::DiagnosticActionResult *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.Diagnostics.DiagnosticActionResult", 0x31u, a2);
}

```

## disassembly

```asm
0x18000f0a0  mov     qword ptr [rdx], 0
0x18000f0a7  lea     rcx, ?RuntimeClass_Windows_System_Diagnostics_DiagnosticActionResult@@3QBGB; "Windows.System.Diagnostics.DiagnosticAc"...
0x18000f0ae  mov     r8, rdx
0x18000f0b1  mov     edx, 31h ; '1'
0x18000f0b6  jmp     cs:__imp_WindowsCreateString
```
