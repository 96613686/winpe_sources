# DllMain

- ea: `0x18000bd34`
- end: `0x18000bd93`
- name: `DllMain`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003754`

## callees

- `0x1800046a0`
- `0x18000a830`
- `0x18000bd34`

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
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)MidiVirtualMidiTransportTelemetryProvider::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))MidiVirtualMidiTransportTelemetryProvider::FallbackTelemetryCallback;
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bd34  sub     rsp, 0C8h
0x18000bd3b  mov     eax, 1
0x18000bd40  cmp     edx, eax
0x18000bd42  jnz     short loc_18000BD6E
0x18000bd44  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000bd4b  lea     rdx, ?FallbackTelemetryCallback@MidiVirtualMidiTransportTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; MidiVirtualMidiTransportTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000bd52  test    rcx, rcx
0x18000bd55  jz      short loc_18000BD5C
0x18000bd57  cmp     rcx, rdx
0x18000bd5a  jnz     short loc_18000BD76
0x18000bd5c  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000bd63  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x18000bd6a  jz      short loc_18000BD6E
0x18000bd6c  xor     eax, eax
0x18000bd6e  add     rsp, 0C8h
0x18000bd75  retn
0x18000bd76  xor     edx, edx; Val
0x18000bd78  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000bd7d  mov     r8d, 98h; Size
0x18000bd83  call    memset_0
0x18000bd88  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000bd8d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
