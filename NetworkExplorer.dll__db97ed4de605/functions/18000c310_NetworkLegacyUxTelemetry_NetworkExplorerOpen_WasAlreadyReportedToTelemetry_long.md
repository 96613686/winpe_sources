# NetworkLegacyUxTelemetry::NetworkExplorerOpen::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000c310`
- end: `0x18000c31e`
- name: `?WasAlreadyReportedToTelemetry@NetworkExplorerOpen@NetworkLegacyUxTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(NetworkLegacyUxTelemetry::NetworkExplorerOpen *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall NetworkLegacyUxTelemetry::NetworkExplorerOpen::WasAlreadyReportedToTelemetry(
        NetworkLegacyUxTelemetry::NetworkExplorerOpen *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000c310  mov     eax, edx
0x18000c312  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000c318  cmp     eax, edx
0x18000c31a  setz    al
0x18000c31d  retn
```
