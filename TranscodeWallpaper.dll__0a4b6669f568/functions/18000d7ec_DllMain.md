# DllMain

- ea: `0x18000d7ec`
- end: `0x18000d841`
- name: `DllMain`
- size: `85`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001fe4`

## callees

- `0x180002cb4`
- `0x1800068a0`
- `0x18000d7ec`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)WallpaperTranscoderLogging::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))WallpaperTranscoderLogging::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d7ec  sub     rsp, 0C8h
0x18000d7f3  cmp     edx, 1
0x18000d7f6  jnz     short loc_18000D817
0x18000d7f8  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d7ff  lea     rcx, ?FallbackTelemetryCallback@WallpaperTranscoderLogging@@SAX_NAEBUFailureInfo@wil@@@Z; WallpaperTranscoderLogging::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000d806  test    rax, rax
0x18000d809  jz      short loc_18000D810
0x18000d80b  cmp     rax, rcx
0x18000d80e  jnz     short loc_18000D824
0x18000d810  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000d817  mov     eax, 1
0x18000d81c  add     rsp, 0C8h
0x18000d823  retn
0x18000d824  xor     edx, edx; Val
0x18000d826  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000d82b  mov     r8d, 98h; Size
0x18000d831  call    memset_0
0x18000d836  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000d83b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
