# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::~TriggerPeriodicBase(void)

- ea: `0x18000ee18`
- end: `0x18000ee8e`
- name: `??1TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@UEAA@XZ`
- size: `118`
- prototype: `void __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e350`
- `0x18001b9c0`
- `0x18001ba00`

## callees

- `0x18000cbb0`
- `0x18000ee18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee56`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ee63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ee63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee87`

## pseudocode

```c
void __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::~TriggerPeriodicBase(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this)
{
  struct _TP_TIMER *v2; // rcx

  *(_QWORD *)this = &PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::`vftable';
  PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent(this);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 55);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 55), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 55));
    *((_QWORD *)this + 55) = 0;
  }
  *(_QWORD *)this = &Trigger::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
}

```

## disassembly

```asm
0x18000ee18  push    rbx
0x18000ee1a  sub     rsp, 20h
0x18000ee1e  lea     rax, ??_7TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::`vftable'
0x18000ee25  mov     rbx, rcx
0x18000ee28  mov     [rcx], rax
0x18000ee2b  call    ?UnregisterPeriodicEvent@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent(void)
0x18000ee30  mov     rcx, [rbx+1B8h]; pti
0x18000ee37  test    rcx, rcx
0x18000ee3a  jz      short loc_18000EE74
0x18000ee3c  xor     r9d, r9d; msWindowLength
0x18000ee3f  xor     r8d, r8d; msPeriod
0x18000ee42  xor     edx, edx; pftDueTime
0x18000ee44  call    cs:__imp_SetThreadpoolTimer
0x18000ee4a  mov     rcx, [rbx+1B8h]; pti
0x18000ee51  mov     edx, 1; fCancelPendingCallbacks
0x18000ee56  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ee5c  mov     rcx, [rbx+1B8h]; pti
0x18000ee63  call    cs:__imp_CloseThreadpoolTimer
0x18000ee69  mov     qword ptr [rbx+1B8h], 0
0x18000ee74  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x18000ee7b  lea     rcx, [rbx+78h]
0x18000ee7f  mov     [rbx], rax
0x18000ee82  add     rsp, 20h
0x18000ee86  pop     rbx
0x18000ee87  jmp     cs:__imp_DeleteCriticalSection
```
