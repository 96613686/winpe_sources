# SsdmTelemetryProvider::PersonalizationDuration::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000bb90`
- end: `0x18000bb9e`
- name: `?WasAlreadyReportedToTelemetry@PersonalizationDuration@SsdmTelemetryProvider@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(SsdmTelemetryProvider::PersonalizationDuration *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall SsdmTelemetryProvider::PersonalizationDuration::WasAlreadyReportedToTelemetry(
        SsdmTelemetryProvider::PersonalizationDuration *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000bb90  mov     eax, edx
0x18000bb92  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000bb98  cmp     eax, edx
0x18000bb9a  setz    al
0x18000bb9d  retn
```
