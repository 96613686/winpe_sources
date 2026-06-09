# Windows::System::Diagnostics::DiagnosticInvoker::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000c410`
- end: `0x18000c42d`
- name: `?GetRuntimeClassName@DiagnosticInvoker@Diagnostics@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::Diagnostics::DiagnosticInvoker *this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c440`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c426`

## pseudocode

```c
HRESULT __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetRuntimeClassName(
        Windows::System::Diagnostics::DiagnosticInvoker *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.Diagnostics.DiagnosticInvoker", 0x2Cu, a2);
}

```

## disassembly

```asm
0x18000c410  mov     qword ptr [rdx], 0
0x18000c417  lea     rcx, ?RuntimeClass_Windows_System_Diagnostics_DiagnosticInvoker@@3QBGB; "Windows.System.Diagnostics.DiagnosticIn"...
0x18000c41e  mov     r8, rdx
0x18000c421  mov     edx, 2Ch ; ','
0x18000c426  jmp     cs:__imp_WindowsCreateString
```
