# Windows::System::CProcessMemoryReport::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180018550`
- end: `0x18001856d`
- name: `?GetRuntimeClassName@CProcessMemoryReport@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::CProcessMemoryReport *this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180018580`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018566`

## pseudocode

```c
HRESULT __fastcall Windows::System::CProcessMemoryReport::GetRuntimeClassName(
        Windows::System::CProcessMemoryReport *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.ProcessMemoryReport", 0x22u, a2);
}

```

## disassembly

```asm
0x180018550  mov     qword ptr [rdx], 0
0x180018557  lea     rcx, ?RuntimeClass_Windows_System_ProcessMemoryReport@@3QBGB; "Windows.System.ProcessMemoryReport"
0x18001855e  mov     r8, rdx
0x180018561  mov     edx, 22h ; '"'
0x180018566  jmp     cs:__imp_WindowsCreateString
```
