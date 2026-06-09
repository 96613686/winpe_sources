# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000b5b0`
- end: `0x18000b5be`
- name: `?WasAlreadyReportedToTelemetry@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
bool __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::WasAlreadyReportedToTelemetry(
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000b5b0  mov     eax, edx
0x18000b5b2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000b5b8  cmp     eax, edx
0x18000b5ba  setz    al
0x18000b5bd  retn
```
