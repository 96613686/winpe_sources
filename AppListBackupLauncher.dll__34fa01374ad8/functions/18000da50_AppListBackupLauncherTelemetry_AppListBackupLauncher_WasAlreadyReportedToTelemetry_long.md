# AppListBackupLauncherTelemetry::AppListBackupLauncher::WasAlreadyReportedToTelemetry(long)

- ea: `0x18000da50`
- end: `0x18000da5e`
- name: `?WasAlreadyReportedToTelemetry@AppListBackupLauncher@AppListBackupLauncherTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(AppListBackupLauncherTelemetry::AppListBackupLauncher *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall AppListBackupLauncherTelemetry::AppListBackupLauncher::WasAlreadyReportedToTelemetry(
        AppListBackupLauncherTelemetry::AppListBackupLauncher *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x18000da50  mov     eax, edx
0x18000da52  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x18000da58  cmp     eax, edx
0x18000da5a  setz    al
0x18000da5d  retn
```
