# DllMain

- ea: `0x18000c0b0`
- end: `0x18000c10f`
- name: `DllMain`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002554`

## callees

- `0x18000329c`
- `0x180009d30`
- `0x18000c0b0`

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
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)SearchIndexerTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))SearchIndexerTelemetry::FallbackTelemetryCallback;
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c0b0  sub     rsp, 0C8h
0x18000c0b7  mov     eax, 1
0x18000c0bc  cmp     edx, eax
0x18000c0be  jnz     short loc_18000C0EA
0x18000c0c0  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000c0c7  lea     rdx, ?FallbackTelemetryCallback@SearchIndexerTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; SearchIndexerTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000c0ce  test    rcx, rcx
0x18000c0d1  jz      short loc_18000C0D8
0x18000c0d3  cmp     rcx, rdx
0x18000c0d6  jnz     short loc_18000C0F2
0x18000c0d8  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000c0df  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x18000c0e6  jz      short loc_18000C0EA
0x18000c0e8  xor     eax, eax
0x18000c0ea  add     rsp, 0C8h
0x18000c0f1  retn
0x18000c0f2  xor     edx, edx; Val
0x18000c0f4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000c0f9  mov     r8d, 98h; Size
0x18000c0ff  call    memset_0
0x18000c104  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000c109  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
