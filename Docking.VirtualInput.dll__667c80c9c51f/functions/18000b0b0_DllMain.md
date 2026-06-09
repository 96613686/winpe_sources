# DllMain

- ea: `0x18000b0b0`
- end: `0x18000b10b`
- name: `DllMain`
- size: `91`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003514`

## callees

- `0x180004054`
- `0x180007148`
- `0x18000b0b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b0bc`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000b0bc`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != ControllerHostLogging::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)ControllerHostLogging::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x18000b0b0  sub     rsp, 0C8h
0x18000b0b7  cmp     edx, 1
0x18000b0ba  jnz     short loc_18000B0E1
0x18000b0bc  call    cs:__imp_DisableThreadLibraryCalls
0x18000b0c2  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b0c9  lea     rcx, ?FallbackTelemetryCallback@ControllerHostLogging@@SAX_NAEBUFailureInfo@wil@@@Z; ControllerHostLogging::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000b0d0  test    rax, rax
0x18000b0d3  jz      short loc_18000B0DA
0x18000b0d5  cmp     rax, rcx
0x18000b0d8  jnz     short loc_18000B0EE
0x18000b0da  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000b0e1  mov     eax, 1
0x18000b0e6  add     rsp, 0C8h
0x18000b0ed  retn
0x18000b0ee  xor     edx, edx; Val
0x18000b0f0  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000b0f5  mov     r8d, 98h; Size
0x18000b0fb  call    memset_0
0x18000b100  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000b105  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
