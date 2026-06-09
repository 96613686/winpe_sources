# CRemoteTextConnection::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800362a0`
- end: `0x1800362bd`
- name: `?GetRuntimeClassName@CRemoteTextConnection@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CRemoteTextConnection *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800362d0`
- `0x1800362e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800362b6`

## pseudocode

```c
HRESULT __fastcall CRemoteTextConnection::GetRuntimeClassName(CRemoteTextConnection *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.System.RemoteDesktop.Input.RemoteTextConnection", 0x37u, a2);
}

```

## disassembly

```asm
0x1800362a0  mov     qword ptr [rdx], 0
0x1800362a7  lea     rcx, ?RuntimeClass_Windows_System_RemoteDesktop_Input_RemoteTextConnection@@3QBGB; "Windows.System.RemoteDesktop.Input.Remo"...
0x1800362ae  mov     r8, rdx
0x1800362b1  mov     edx, 37h ; '7'
0x1800362b6  jmp     cs:__imp_WindowsCreateString
```
