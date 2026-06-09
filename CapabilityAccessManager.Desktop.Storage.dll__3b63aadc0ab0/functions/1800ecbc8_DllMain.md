# DllMain

- ea: `0x1800ecbc8`
- end: `0x1800ecc23`
- name: `DllMain`
- size: `91`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ed4`

## callees

- `0x180003a40`
- `0x1800ec390`
- `0x1800ecbc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800ecbd4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800ecbd4`

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
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x1800ecbc8  sub     rsp, 0C8h
0x1800ecbcf  cmp     edx, 1
0x1800ecbd2  jnz     short loc_1800ECBF9
0x1800ecbd4  call    cs:__imp_DisableThreadLibraryCalls
0x1800ecbda  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800ecbe1  lea     rcx, ?FallbackTelemetryCallback@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAX_NAEBUFailureInfo@wil@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x1800ecbe8  test    rax, rax
0x1800ecbeb  jz      short loc_1800ECBF2
0x1800ecbed  cmp     rax, rcx
0x1800ecbf0  jnz     short loc_1800ECC06
0x1800ecbf2  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x1800ecbf9  mov     eax, 1
0x1800ecbfe  add     rsp, 0C8h
0x1800ecc05  retn
0x1800ecc06  xor     edx, edx; Val
0x1800ecc08  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800ecc0d  mov     r8d, 98h; Size
0x1800ecc13  call    memset_0
0x1800ecc18  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800ecc1d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
