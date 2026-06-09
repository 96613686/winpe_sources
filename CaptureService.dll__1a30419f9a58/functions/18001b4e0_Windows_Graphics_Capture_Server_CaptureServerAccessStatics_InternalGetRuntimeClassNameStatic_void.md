# Windows::Graphics::Capture::Server::CaptureServerAccessStatics::InternalGetRuntimeClassNameStatic(void)

- ea: `0x18001b4e0`
- end: `0x18001b4e8`
- name: `?InternalGetRuntimeClassNameStatic@CaptureServerAccessStatics@Server@Capture@Graphics@Windows@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x18001b4e0`: `Windows.Graphics.Capture.Server.CaptureServerAccess`

## pseudocode

```c
const unsigned __int16 *Windows::Graphics::Capture::Server::CaptureServerAccessStatics::InternalGetRuntimeClassNameStatic(
        void)
{
  return L"Windows.Graphics.Capture.Server.CaptureServerAccess";
}

```

## disassembly

```asm
0x18001b4e0  lea     rax, ?RuntimeClass_Windows_Graphics_Capture_Server_CaptureServerAccess@@3QBGB; "Windows.Graphics.Capture.Server.Capture"...
0x18001b4e7  retn
```
