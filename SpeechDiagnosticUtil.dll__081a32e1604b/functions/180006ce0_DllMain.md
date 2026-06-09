# DllMain

- ea: `0x180006ce0`
- end: `0x180006d4e`
- name: `DllMain`
- size: `110`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002784`

## callees

- `0x180003290`
- `0x1800062cc`
- `0x1800068cc`
- `0x180006ce0`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180006cec`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180006cec`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    *((_DWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 5) = 2;
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)SpeechMicDiagnostic::SmdTraceProvider::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))SpeechMicDiagnostic::SmdTraceProvider::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x180006ce0  sub     rsp, 0C8h
0x180006ce7  cmp     edx, 1
0x180006cea  jnz     short loc_180006D23
0x180006cec  call    cs:__imp_DisableThreadLibraryCalls
0x180006cf3  nop     dword ptr [rax+rax+00h]
0x180006cf8  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x180006cfd  lea     rcx, ?FallbackTelemetryCallback@SmdTraceProvider@SpeechMicDiagnostic@@SAX_NAEBUFailureInfo@wil@@@Z; SpeechMicDiagnostic::SmdTraceProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180006d04  mov     dword ptr [rax+14h], 2
0x180006d0b  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006d12  test    rax, rax
0x180006d15  jz      short loc_180006D1C
0x180006d17  cmp     rax, rcx
0x180006d1a  jnz     short loc_180006D31
0x180006d1c  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180006d23  mov     eax, 1
0x180006d28  add     rsp, 0C8h
0x180006d2f  retn
0x180006d31  xor     edx, edx; Val
0x180006d33  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180006d38  mov     r8d, 98h; Size
0x180006d3e  call    memset_0
0x180006d43  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006d48  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
