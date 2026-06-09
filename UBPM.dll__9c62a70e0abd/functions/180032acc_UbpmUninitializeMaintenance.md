# UbpmUninitializeMaintenance

- ea: `0x180032acc`
- end: `0x180032bc9`
- name: `UbpmUninitializeMaintenance`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001a3c`

## callees

- `0x1800103c0`
- `0x18002c32c`
- `0x18002c638`
- `0x180032acc`
- `0x180032bd0`
- `0x180032c90`
- `0x180036d44`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180032af9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180032af9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180032bbd`
- `EventAggregation!EADeleteAggregateEvent` at `0x180032b11`
- `EventAggregation!EADeleteAggregateEvent` at `0x180032b32`
- `EventAggregation!EADeleteAggregateEvent` at `0x180032b11`
- `EventAggregation!EADeleteAggregateEvent` at `0x180032b32`
- `UMPDC!SleepstudyHelperDestroyLibrary` at `0x180032b97`
- `UMPDC!SleepstudyHelperDestroyLibrary` at `0x180032b97`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180032b60`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180032b60`

## pseudocode

```c
__int64 UbpmUninitializeMaintenance()
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  __int64 v2; // rcx

  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenancePilotLock);
  byte_18004FC30 = 0;
  UbpmpUninitializeWakeTimer();
  dword_180050000 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenancePilotLock);
  if ( qword_18004FC18 && (unsigned int)EADeleteAggregateEvent() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v0);
  if ( qword_18004FC28 && (unsigned int)EADeleteAggregateEvent() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v1);
  if ( qword_18004FC20 && (int)TbDeleteCEvent(qword_18004FC20) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  UbpmMaintenanceUninitializeTaskTriggers();
  UbpmpUninitializeMaintenanceLevels();
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_MaintenanceLaunchLock);
  if ( qword_18004FC48 )
    SleepstudyHelperDestroyLibrary();
  UbpmpUnregisterPdcClient();
  dword_18004FFE8 = 0;
  return RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
}

```

## disassembly

```asm
0x180032acc  sub     rsp, 28h
0x180032ad0  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x180032ad7  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180032adc  mov     cs:byte_18004FC30, 0
0x180032ae3  call    ?UbpmpUninitializeWakeTimer@@YAXXZ; UbpmpUninitializeWakeTimer(void)
0x180032ae8  lea     rcx, ?g_MaintenancePilotLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_MaintenancePilotLock
0x180032aef  mov     cs:dword_180050000, 0
0x180032af9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180032b00  nop     dword ptr [rax+rax+00h]
0x180032b05  mov     rcx, cs:qword_18004FC18
0x180032b0c  test    rcx, rcx
0x180032b0f  jz      short loc_180032B26
0x180032b11  call    cs:__imp_EADeleteAggregateEvent
0x180032b18  nop     dword ptr [rax+rax+00h]
0x180032b1d  test    eax, eax
0x180032b1f  jz      short loc_180032B26
0x180032b21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032b26  mov     rcx, cs:qword_18004FC28
0x180032b2d  test    rcx, rcx
0x180032b30  jz      short loc_180032B47
0x180032b32  call    cs:__imp_EADeleteAggregateEvent
0x180032b39  nop     dword ptr [rax+rax+00h]
0x180032b3e  test    eax, eax
0x180032b40  jz      short loc_180032B47
0x180032b42  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032b47  cmp     dword ptr cs:qword_18004FC20, 0
0x180032b4e  jnz     short loc_180032B59
0x180032b50  cmp     dword ptr cs:qword_18004FC20+4, 0
0x180032b57  jz      short loc_180032B75
0x180032b59  mov     rcx, cs:qword_18004FC20
0x180032b60  call    cs:__imp_TbDeleteCEvent
0x180032b67  nop     dword ptr [rax+rax+00h]
0x180032b6c  test    eax, eax
0x180032b6e  jns     short loc_180032B75
0x180032b70  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032b75  call    UbpmMaintenanceUninitializeTaskTriggers
0x180032b7a  call    ?UbpmpUninitializeMaintenanceLevels@@YAXXZ; UbpmpUninitializeMaintenanceLevels(void)
0x180032b7f  lea     rcx, g_MaintenanceLaunchLock; struct _UBPM_SRWLOCK *
0x180032b86  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180032b8b  mov     rcx, cs:qword_18004FC48
0x180032b92  test    rcx, rcx
0x180032b95  jz      short loc_180032BA3
0x180032b97  call    cs:__imp_SleepstudyHelperDestroyLibrary
0x180032b9e  nop     dword ptr [rax+rax+00h]
0x180032ba3  call    ?UbpmpUnregisterPdcClient@@YAXXZ; UbpmpUnregisterPdcClient(void)
0x180032ba8  lea     rcx, g_MaintenanceLaunchLock
0x180032baf  mov     cs:dword_18004FFE8, 0
0x180032bb9  add     rsp, 28h
0x180032bbd  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
