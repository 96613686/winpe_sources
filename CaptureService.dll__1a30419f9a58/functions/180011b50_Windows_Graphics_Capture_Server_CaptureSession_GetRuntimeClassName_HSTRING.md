# Windows::Graphics::Capture::Server::CaptureSession::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180011b50`
- end: `0x180011b6d`
- name: `?GetRuntimeClassName@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180011b80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180011b66`

## pseudocode

```c
HRESULT __fastcall Windows::Graphics::Capture::Server::CaptureSession::GetRuntimeClassName(
        Windows::Graphics::Capture::Server::CaptureSession *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Graphics.Capture.Server.CaptureSession", 0x2Eu, a2);
}

```

## disassembly

```asm
0x180011b50  mov     qword ptr [rdx], 0
0x180011b57  lea     rcx, ?RuntimeClass_Windows_Graphics_Capture_Server_CaptureSession@@3QBGB; "Windows.Graphics.Capture.Server.Capture"...
0x180011b5e  mov     r8, rdx
0x180011b61  mov     edx, 2Eh ; '.'
0x180011b66  jmp     cs:__imp_WindowsCreateString
```
