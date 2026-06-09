# PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::~TriggerWNF(void)

- ea: `0x180007f00`
- end: `0x180008019`
- name: `??1TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@UEAA@XZ`
- size: `281`
- prototype: `void __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180007f00`
- `0x180008020`

## import_xrefs

- `msvcrt!free` at `0x180007f99`
- `msvcrt!free` at `0x180007f99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fe4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fe4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ff6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007ff6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008003`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008003`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007f92`
- `ntdll!NtDeleteWnfStateName` at `0x180007fcb`
- `ntdll!NtDeleteWnfStateName` at `0x180007fcb`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180007fb3`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180007fb3`

## pseudocode

```c
void __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::~TriggerWNF(PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *this)
{
  struct CSchedule *v2; // rdx
  struct _WNF_USER_SUBSCRIPTION *v3; // r8
  struct _TP_TIMER *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::`vftable';
  v2 = (struct CSchedule *)*((_QWORD *)this + 22);
  if ( v2 )
  {
    v3 = (struct _WNF_USER_SUBSCRIPTION *)*((_QWORD *)this + 25);
    if ( v3 )
    {
      CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletion(
        this,
        v2,
        v3,
        *(struct _WNF_STATE_NAME *)((char *)this + 208));
      *((_QWORD *)this + 25) = 0;
    }
  }
  if ( *((_QWORD *)this + 35) )
  {
    CSebDeleteEvent(*((_QWORD *)this + 35));
    *((_QWORD *)this + 35) = 0;
  }
  if ( *((_QWORD *)this + 34) )
  {
    NtDeleteWnfStateName((char *)this + 272);
    *((_QWORD *)this + 34) = 0;
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 32);
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 32), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 32));
    *((_QWORD *)this + 32) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 28);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 28) = 0;
  }
  *(_QWORD *)this = &Trigger::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
}

```

## disassembly

```asm
0x180007f00  mov     [rsp+arg_8], rbx
0x180007f05  push    rdi
0x180007f06  sub     rsp, 20h
0x180007f0a  mov     rbx, rcx
0x180007f0d  lea     rax, ??_7TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::`vftable'
0x180007f14  mov     [rcx], rax
0x180007f17  mov     rdx, [rcx+0B0h]; struct CSchedule *
0x180007f1e  test    rdx, rdx
0x180007f21  jz      short loc_180007F46
0x180007f23  mov     r8, [rcx+0C8h]; struct _WNF_USER_SUBSCRIPTION *
0x180007f2a  test    r8, r8
0x180007f2d  jz      short loc_180007F46
0x180007f2f  mov     r9, [rcx+0D0h]; struct _WNF_STATE_NAME
0x180007f36  call    ?UnsubscribeWnfNotificationWaitForCompletion@CScheduleMgr@@QEAAJPEAVCSchedule@@PEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@@Z; CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletion(CSchedule *,_WNF_USER_SUBSCRIPTION *,_WNF_STATE_NAME)
0x180007f3b  mov     qword ptr [rbx+0C8h], 0
0x180007f46  mov     eax, [rbx+11Ch]
0x180007f4c  or      eax, [rbx+118h]
0x180007f52  jnz     short loc_180007FAC
0x180007f54  mov     eax, [rbx+114h]
0x180007f5a  or      eax, [rbx+110h]
0x180007f60  jnz     short loc_180007FC4
0x180007f62  mov     rcx, [rbx+100h]; pti
0x180007f69  test    rcx, rcx
0x180007f6c  jnz     short loc_180007FDC
0x180007f6e  mov     rcx, [rbx+0E0h]; Block
0x180007f75  test    rcx, rcx
0x180007f78  jnz     short loc_180007F99
0x180007f7a  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x180007f81  mov     [rbx], rax
0x180007f84  lea     rcx, [rbx+78h]
0x180007f88  mov     rbx, [rsp+28h+arg_8]
0x180007f8d  add     rsp, 20h
0x180007f91  pop     rdi
0x180007f92  jmp     cs:__imp_DeleteCriticalSection
0x180007f99  call    cs:__imp_free
0x180007f9f  mov     qword ptr [rbx+0E0h], 0
0x180007faa  jmp     short loc_180007F7A
0x180007fac  mov     rcx, [rbx+118h]
0x180007fb3  call    cs:__imp_CSebDeleteEvent
0x180007fb9  xor     eax, eax
0x180007fbb  mov     [rbx+118h], rax
0x180007fc2  jmp     short loc_180007F54
0x180007fc4  lea     rcx, [rbx+110h]
0x180007fcb  call    cs:__imp_NtDeleteWnfStateName
0x180007fd1  xor     eax, eax
0x180007fd3  mov     [rbx+110h], rax
0x180007fda  jmp     short loc_180007F62
0x180007fdc  xor     r9d, r9d; msWindowLength
0x180007fdf  xor     r8d, r8d; msPeriod
0x180007fe2  xor     edx, edx; pftDueTime
0x180007fe4  call    cs:__imp_SetThreadpoolTimer
0x180007fea  mov     edx, 1; fCancelPendingCallbacks
0x180007fef  mov     rcx, [rbx+100h]; pti
0x180007ff6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007ffc  mov     rcx, [rbx+100h]; pti
0x180008003  call    cs:__imp_CloseThreadpoolTimer
0x180008009  mov     qword ptr [rbx+100h], 0
0x180008014  jmp     loc_180007F6E
```
