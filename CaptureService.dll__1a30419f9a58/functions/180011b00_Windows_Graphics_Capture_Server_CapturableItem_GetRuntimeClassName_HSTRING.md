# Windows::Graphics::Capture::Server::CapturableItem::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180011b00`
- end: `0x180011b1d`
- name: `?GetRuntimeClassName@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011b30`
- `0x180011b40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180011b16`

## pseudocode

```c
HRESULT __fastcall Windows::Graphics::Capture::Server::CapturableItem::GetRuntimeClassName(
        Windows::Graphics::Capture::Server::CapturableItem *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Graphics.Capture.Server.CapturableItem", 0x2Eu, a2);
}

```

## disassembly

```asm
0x180011b00  mov     qword ptr [rdx], 0
0x180011b07  lea     rcx, ?RuntimeClass_Windows_Graphics_Capture_Server_CapturableItem@@3QBGB; "Windows.Graphics.Capture.Server.Captura"...
0x180011b0e  mov     r8, rdx
0x180011b11  mov     edx, 2Eh ; '.'
0x180011b16  jmp     cs:__imp_WindowsCreateString
```
