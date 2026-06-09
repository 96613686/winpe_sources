# Windows::System::ProcessLauncherOptionsImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000c0e0`
- end: `0x18000c0fd`
- name: `?GetRuntimeClassName@ProcessLauncherOptionsImpl@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::System::ProcessLauncherOptionsImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c0f6`

## pseudocode

```c
HRESULT __fastcall Windows::System::ProcessLauncherOptionsImpl::GetRuntimeClassName(
        Windows::System::ProcessLauncherOptionsImpl *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.ProcessLauncherOptions", 0x25u, a2);
}

```

## disassembly

```asm
0x18000c0e0  mov     qword ptr [rdx], 0
0x18000c0e7  lea     rcx, ?RuntimeClass_Windows_System_ProcessLauncherOptions@@3QBGB; "Windows.System.ProcessLauncherOptions"
0x18000c0ee  mov     r8, rdx
0x18000c0f1  mov     edx, 25h ; '%'
0x18000c0f6  jmp     cs:__imp_WindowsCreateString
```
