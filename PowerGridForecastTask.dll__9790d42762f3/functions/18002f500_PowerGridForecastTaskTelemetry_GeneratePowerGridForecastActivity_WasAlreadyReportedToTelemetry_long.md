# PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x18002f500`
- end: `0x18002f50e`
- name: `?WasAlreadyReportedToTelemetry@GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
bool __fastcall PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::WasAlreadyReportedToTelemetry(
        PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18002f500  mov     eax, edx
0x18002f502  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18002f508  cmp     eax, edx
0x18002f50a  setz    al
0x18002f50d  retn
```
