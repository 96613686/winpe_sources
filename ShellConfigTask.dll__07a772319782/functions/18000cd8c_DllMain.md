# DllMain

- ea: `0x18000cd8c`
- end: `0x18000cde7`
- name: `DllMain`
- size: `91`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002404`

## callees

- `0x180002f98`
- `0x18000c380`
- `0x18000cd8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000cdb7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000cdb7`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)AIXTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))AIXTelemetry::FallbackTelemetryCallback;
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18000cd8c  sub     rsp, 0C8h
0x18000cd93  cmp     edx, 1
0x18000cd96  jnz     short loc_18000CDBD
0x18000cd98  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000cd9f  lea     rdx, ?FallbackTelemetryCallback@AIXTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; AIXTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000cda6  test    rax, rax
0x18000cda9  jz      short loc_18000CDB0
0x18000cdab  cmp     rax, rdx
0x18000cdae  jnz     short loc_18000CDCA
0x18000cdb0  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x18000cdb7  call    cs:__imp_DisableThreadLibraryCalls
0x18000cdbd  mov     eax, 1
0x18000cdc2  add     rsp, 0C8h
0x18000cdc9  retn
0x18000cdca  xor     edx, edx; Val
0x18000cdcc  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000cdd1  mov     r8d, 98h; Size
0x18000cdd7  call    memset_0
0x18000cddc  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000cde1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
