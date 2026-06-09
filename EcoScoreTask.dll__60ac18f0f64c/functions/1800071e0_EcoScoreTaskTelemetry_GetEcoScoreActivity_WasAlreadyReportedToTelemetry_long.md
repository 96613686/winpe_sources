# EcoScoreTaskTelemetry::GetEcoScoreActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x1800071e0`
- end: `0x1800071ee`
- name: `?WasAlreadyReportedToTelemetry@GetEcoScoreActivity@EcoScoreTaskTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(EcoScoreTaskTelemetry::GetEcoScoreActivity *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
bool __fastcall EcoScoreTaskTelemetry::GetEcoScoreActivity::WasAlreadyReportedToTelemetry(
        EcoScoreTaskTelemetry::GetEcoScoreActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x1800071e0  mov     eax, edx
0x1800071e2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x1800071e8  cmp     eax, edx
0x1800071ea  setz    al
0x1800071ed  retn
```
