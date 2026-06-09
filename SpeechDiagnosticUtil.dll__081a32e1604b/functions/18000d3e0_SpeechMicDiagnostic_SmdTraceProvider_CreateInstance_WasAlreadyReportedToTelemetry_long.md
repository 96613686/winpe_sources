# SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000d3e0`
- end: `0x18000d3ee`
- name: `?WasAlreadyReportedToTelemetry@CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::WasAlreadyReportedToTelemetry(
        SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000d3e0  mov     eax, edx
0x18000d3e2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000d3e8  cmp     eax, edx
0x18000d3ea  setz    al
0x18000d3ed  retn
```
