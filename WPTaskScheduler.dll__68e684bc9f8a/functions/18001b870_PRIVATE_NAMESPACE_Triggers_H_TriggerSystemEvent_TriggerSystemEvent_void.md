# PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::~TriggerSystemEvent(void)

- ea: `0x18001b870`
- end: `0x18001b8de`
- name: `??1TriggerSystemEvent@PRIVATE_NAMESPACE_Triggers_H@@UEAA@XZ`
- size: `110`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ba40`

## callees

- `0x18001b870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b8d7`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18001b8b5`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18001b8b5`
- `EventAggregation!EADeleteAggregateEvent` at `0x18001b88f`
- `EventAggregation!EADeleteAggregateEvent` at `0x18001b88f`

## pseudocode

```c
void __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::~TriggerSystemEvent(
        struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::`vftable';
  if ( *(_QWORD *)&this[5].LockCount )
  {
    EADeleteAggregateEvent();
    *(_QWORD *)&this[5].LockCount = 0;
  }
  if ( this[5].DebugInfo )
  {
    CSebDeleteEvent(this[5].DebugInfo);
    this[5].DebugInfo = 0;
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Trigger::`vftable';
  DeleteCriticalSection(this + 3);
}

```

## disassembly

```asm
0x18001b870  push    rbx
0x18001b872  sub     rsp, 20h
0x18001b876  lea     rax, ??_7TriggerSystemEvent@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::`vftable'
0x18001b87d  mov     rbx, rcx
0x18001b880  mov     [rcx], rax
0x18001b883  mov     rcx, [rcx+0D0h]
0x18001b88a  test    rcx, rcx
0x18001b88d  jz      short loc_18001B8A0
0x18001b88f  call    cs:__imp_EADeleteAggregateEvent
0x18001b895  mov     qword ptr [rbx+0D0h], 0
0x18001b8a0  mov     eax, [rbx+0CCh]
0x18001b8a6  or      eax, [rbx+0C8h]
0x18001b8ac  jz      short loc_18001B8C4
0x18001b8ae  mov     rcx, [rbx+0C8h]
0x18001b8b5  call    cs:__imp_CSebDeleteEvent
0x18001b8bb  xor     eax, eax
0x18001b8bd  mov     [rbx+0C8h], rax
0x18001b8c4  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x18001b8cb  lea     rcx, [rbx+78h]
0x18001b8cf  mov     [rbx], rax
0x18001b8d2  add     rsp, 20h
0x18001b8d6  pop     rbx
0x18001b8d7  jmp     cs:__imp_DeleteCriticalSection
```
