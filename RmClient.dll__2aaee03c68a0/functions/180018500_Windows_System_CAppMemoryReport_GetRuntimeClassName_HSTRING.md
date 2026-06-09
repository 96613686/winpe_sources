# Windows::System::CAppMemoryReport::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180018500`
- end: `0x18001851d`
- name: `?GetRuntimeClassName@CAppMemoryReport@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::System::CAppMemoryReport *this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180018530`
- `0x180018540`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018516`

## pseudocode

```c
HRESULT __fastcall Windows::System::CAppMemoryReport::GetRuntimeClassName(
        Windows::System::CAppMemoryReport *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.AppMemoryReport", 0x1Eu, a2);
}

```

## disassembly

```asm
0x180018500  mov     qword ptr [rdx], 0
0x180018507  lea     rcx, ?RuntimeClass_Windows_System_AppMemoryReport@@3QBGB; "Windows.System.AppMemoryReport"
0x18001850e  mov     r8, rdx
0x180018511  mov     edx, 1Eh
0x180018516  jmp     cs:__imp_WindowsCreateString
```
