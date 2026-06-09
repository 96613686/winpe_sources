# DllMain

- ea: `0x18000aed4`
- end: `0x18000af33`
- name: `DllMain`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002cd4`

## callees

- `0x180003a20`
- `0x1800099d0`
- `0x18000aed4`

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
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)MidiUmpProtocolDownscalerTransformTelemetryProvider::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))MidiUmpProtocolDownscalerTransformTelemetryProvider::FallbackTelemetryCallback;
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000aed4  sub     rsp, 0C8h
0x18000aedb  mov     eax, 1
0x18000aee0  cmp     edx, eax
0x18000aee2  jnz     short loc_18000AF0E
0x18000aee4  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000aeeb  lea     rdx, ?FallbackTelemetryCallback@MidiUmpProtocolDownscalerTransformTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; MidiUmpProtocolDownscalerTransformTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000aef2  test    rcx, rcx
0x18000aef5  jz      short loc_18000AEFC
0x18000aef7  cmp     rcx, rdx
0x18000aefa  jnz     short loc_18000AF16
0x18000aefc  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000af03  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x18000af0a  jz      short loc_18000AF0E
0x18000af0c  xor     eax, eax
0x18000af0e  add     rsp, 0C8h
0x18000af15  retn
0x18000af16  xor     edx, edx; Val
0x18000af18  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000af1d  mov     r8d, 98h; Size
0x18000af23  call    memset_0
0x18000af28  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000af2d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
