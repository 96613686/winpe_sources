# ProcessLauncherResultImpl::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18001c410`
- end: `0x18001c42d`
- name: `?GetRuntimeClassName@ProcessLauncherResultImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(ProcessLauncherResultImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001c426`

## pseudocode

```c
HRESULT __fastcall ProcessLauncherResultImpl::GetRuntimeClassName(ProcessLauncherResultImpl *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.ProcessLauncherResult", 0x24u, a2);
}

```

## disassembly

```asm
0x18001c410  mov     qword ptr [rdx], 0
0x18001c417  lea     rcx, ?RuntimeClass_Windows_System_ProcessLauncherResult@@3QBGB; "Windows.System.ProcessLauncherResult"
0x18001c41e  mov     r8, rdx
0x18001c421  mov     edx, 24h ; '$'
0x18001c426  jmp     cs:__imp_WindowsCreateString
```
