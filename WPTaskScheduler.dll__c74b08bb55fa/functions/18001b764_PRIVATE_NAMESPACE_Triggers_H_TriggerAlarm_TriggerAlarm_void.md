# PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::~TriggerAlarm(void)

- ea: `0x18001b764`
- end: `0x18001b796`
- name: `??1TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b940`

## callees

- `0x18001d954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b78f`

## pseudocode

```c
void __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::~TriggerAlarm(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        __int64 a3)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::`vftable';
  PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UnregisterAlarmEvent(
    (PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *)this,
    a2,
    a3);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Trigger::`vftable';
  DeleteCriticalSection(this + 3);
}

```

## disassembly

```asm
0x18001b764  push    rbx
0x18001b766  sub     rsp, 20h
0x18001b76a  lea     rax, ??_7TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::`vftable'
0x18001b771  mov     rbx, rcx
0x18001b774  mov     [rcx], rax
0x18001b777  call    ?UnregisterAlarmEvent@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UnregisterAlarmEvent(void)
0x18001b77c  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x18001b783  lea     rcx, [rbx+78h]
0x18001b787  mov     [rbx], rax
0x18001b78a  add     rsp, 20h
0x18001b78e  pop     rbx
0x18001b78f  jmp     cs:__imp_DeleteCriticalSection
```
