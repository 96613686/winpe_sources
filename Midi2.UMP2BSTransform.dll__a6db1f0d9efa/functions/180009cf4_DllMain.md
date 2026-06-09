# DllMain

- ea: `0x180009cf4`
- end: `0x180009d53`
- name: `DllMain`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001d54`

## callees

- `0x180002958`
- `0x1800087f0`
- `0x180009cf4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  result = 1;
  if ( fdwReason == 1 )
  {
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)MidiUMP2BSTransformTelemetryProvider::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))MidiUMP2BSTransformTelemetryProvider::FallbackTelemetryCallback;
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009cf4  sub     rsp, 0C8h
0x180009cfb  mov     eax, 1
0x180009d00  cmp     edx, eax
0x180009d02  jnz     short loc_180009D2E
0x180009d04  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009d0b  lea     rdx, ?FallbackTelemetryCallback@MidiUMP2BSTransformTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; MidiUMP2BSTransformTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180009d12  test    rcx, rcx
0x180009d15  jz      short loc_180009D1C
0x180009d17  cmp     rcx, rdx
0x180009d1a  jnz     short loc_180009D36
0x180009d1c  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180009d23  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x180009d2a  jz      short loc_180009D2E
0x180009d2c  xor     eax, eax
0x180009d2e  add     rsp, 0C8h
0x180009d35  retn
0x180009d36  xor     edx, edx; Val
0x180009d38  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180009d3d  mov     r8d, 98h; Size
0x180009d43  call    memset_0
0x180009d48  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009d4d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
