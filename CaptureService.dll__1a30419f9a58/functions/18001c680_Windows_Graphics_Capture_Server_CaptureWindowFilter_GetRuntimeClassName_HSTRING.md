# Windows::Graphics::Capture::Server::CaptureWindowFilter::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18001c680`
- end: `0x18001c69d`
- name: `?GetRuntimeClassName@CaptureWindowFilter@Server@Capture@Graphics@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CaptureWindowFilter *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c6b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001c696`

## pseudocode

```c
HRESULT __fastcall Windows::Graphics::Capture::Server::CaptureWindowFilter::GetRuntimeClassName(
        Windows::Graphics::Capture::Server::CaptureWindowFilter *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Graphics.Capture.Server.CaptureWindowFilter", 0x33u, a2);
}

```

## disassembly

```asm
0x18001c680  mov     qword ptr [rdx], 0
0x18001c687  lea     rcx, ?RuntimeClass_Windows_Graphics_Capture_Server_CaptureWindowFilter@@3QBGB; "Windows.Graphics.Capture.Server.Capture"...
0x18001c68e  mov     r8, rdx
0x18001c691  mov     edx, 33h ; '3'
0x18001c696  jmp     cs:__imp_WindowsCreateString
```
