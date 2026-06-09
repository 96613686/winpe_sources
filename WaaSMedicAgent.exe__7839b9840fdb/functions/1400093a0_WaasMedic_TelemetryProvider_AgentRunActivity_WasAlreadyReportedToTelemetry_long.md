# WaasMedic::TelemetryProvider::AgentRunActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x1400093a0`
- end: `0x1400093ae`
- name: `?WasAlreadyReportedToTelemetry@AgentRunActivity@TelemetryProvider@WaasMedic@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(WaasMedic::TelemetryProvider::AgentRunActivity *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update`

## pseudocode

```c
bool __fastcall WaasMedic::TelemetryProvider::AgentRunActivity::WasAlreadyReportedToTelemetry(
        WaasMedic::TelemetryProvider::AgentRunActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x1400093a0  mov     eax, edx
0x1400093a2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x1400093a8  cmp     eax, edx
0x1400093aa  setz    al
0x1400093ad  retn
```
