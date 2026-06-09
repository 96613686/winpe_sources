# DllMain

- ea: `0x18000bc08`
- end: `0x18000bc5d`
- name: `DllMain`
- size: `85`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800021c4`

## callees

- `0x180002ed4`
- `0x18000a2c0`
- `0x18000bc08`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)RecoverySettingsErrorTelemetryProvider::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))RecoverySettingsErrorTelemetryProvider::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x18000bc08  sub     rsp, 0C8h
0x18000bc0f  cmp     edx, 1
0x18000bc12  jnz     short loc_18000BC33
0x18000bc14  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000bc1b  lea     rcx, ?FallbackTelemetryCallback@RecoverySettingsErrorTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; RecoverySettingsErrorTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000bc22  test    rax, rax
0x18000bc25  jz      short loc_18000BC2C
0x18000bc27  cmp     rax, rcx
0x18000bc2a  jnz     short loc_18000BC40
0x18000bc2c  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000bc33  mov     eax, 1
0x18000bc38  add     rsp, 0C8h
0x18000bc3f  retn
0x18000bc40  xor     edx, edx; Val
0x18000bc42  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000bc47  mov     r8d, 98h; Size
0x18000bc4d  call    memset_0
0x18000bc52  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000bc57  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
