# DllMain

- ea: `0x18000bb78`
- end: `0x18000bbe0`
- name: `DllMain`
- size: `104`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002034`

## callees

- `0x180002c04`
- `0x18000a7b0`
- `0x18000bb78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bb89`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bb89`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v5; // rdx
  _BYTE v6[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)FirewallUxTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v6, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v6, v5);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))FirewallUxTelemetry::FallbackTelemetryCallback;
    g_FirewallUXHInstance = hinstDLL;
  }
  return 1;
}

```

## disassembly

```asm
0x18000bb78  push    rbx
0x18000bb7a  sub     rsp, 0C0h
0x18000bb81  mov     rbx, rcx
0x18000bb84  cmp     edx, 1
0x18000bb87  jnz     short loc_18000BBB5
0x18000bb89  call    cs:__imp_DisableThreadLibraryCalls
0x18000bb8f  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000bb96  lea     rcx, ?FallbackTelemetryCallback@FirewallUxTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; FirewallUxTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000bb9d  test    rax, rax
0x18000bba0  jz      short loc_18000BBA7
0x18000bba2  cmp     rax, rcx
0x18000bba5  jnz     short loc_18000BBC3
0x18000bba7  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000bbae  mov     cs:?g_FirewallUXHInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_FirewallUXHInstance
0x18000bbb5  mov     eax, 1
0x18000bbba  add     rsp, 0C0h
0x18000bbc1  pop     rbx
0x18000bbc2  retn
0x18000bbc3  xor     edx, edx; Val
0x18000bbc5  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000bbca  mov     r8d, 98h; Size
0x18000bbd0  call    memset_0
0x18000bbd5  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000bbda  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
