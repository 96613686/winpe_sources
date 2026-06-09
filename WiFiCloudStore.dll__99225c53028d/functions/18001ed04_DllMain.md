# DllMain

- ea: `0x18001ed04`
- end: `0x18001ed5e`
- name: `DllMain`
- size: `90`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180029ea4`

## callees

- `0x18001ed04`
- `0x1800241c4`
- `0x18002aad0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001ed1a`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001ed1a`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    result = wil::details::g_pfnTelemetryCallback;
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != WiFiCloudStoreTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)WiFiCloudStoreTelemetry::FallbackTelemetryCallback;
  }
  LOBYTE(result) = 1;
  return result;
}

```

## disassembly

```asm
0x18001ed04  sub     rsp, 0C8h
0x18001ed0b  cmp     edx, 1
0x18001ed0e  jz      short loc_18001ED1A
0x18001ed10  mov     al, 1
0x18001ed12  add     rsp, 0C8h
0x18001ed19  retn
0x18001ed1a  call    cs:__imp_DisableThreadLibraryCalls
0x18001ed20  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001ed27  lea     rcx, ?FallbackTelemetryCallback@WiFiCloudStoreTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; WiFiCloudStoreTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18001ed2e  test    rax, rax
0x18001ed31  jz      short loc_18001ED55
0x18001ed33  cmp     rax, rcx
0x18001ed36  jz      short loc_18001ED55
0x18001ed38  xor     edx, edx; Val
0x18001ed3a  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001ed3f  mov     r8d, 98h; Size
0x18001ed45  call    memset_0
0x18001ed4a  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001ed4f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001ed55  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18001ed5c  jmp     short loc_18001ED10
```
