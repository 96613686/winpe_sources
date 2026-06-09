# s_TaskSchedulerGetPublishStateName

- ea: `0x1800177a0`
- end: `0x18001782d`
- name: `s_TaskSchedulerGetPublishStateName`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001dd0`
- `0x18000d7f0`
- `0x180017370`
- `0x1800177a0`
- `0x180017dac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017815`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017815`

## pseudocode

```c
RPC_STATUS __fastcall s_TaskSchedulerGetPublishStateName(__int64 a1, struct _GUID *a2, struct _WNF_STATE_NAME *a3)
{
  RPC_STATUS result; // eax
  int PublishStateName; // edi
  CSchedule *Schedule; // rax

  if ( (byte_180030D03 & 0x20) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)APIGetPublishStateName, (__int64)a2);
  result = CallerHasAccess(a2, 0);
  if ( result >= 0 )
  {
    PublishStateName = -2100362994;
    EnterCriticalSection(&CriticalSection);
    Schedule = CScheduleMgr::FindSchedule((CScheduleMgr *)&g_ScheduleMgr, a2);
    if ( Schedule )
      PublishStateName = CSchedule::GetPublishStateName(Schedule, a3);
    LeaveCriticalSection(&CriticalSection);
    return PublishStateName;
  }
  return result;
}

```

## disassembly

```asm
0x1800177a0  mov     [rsp+arg_0], rbx
0x1800177a5  mov     [rsp+arg_8], rsi
0x1800177aa  push    rdi
0x1800177ab  sub     rsp, 20h
0x1800177af  test    cs:byte_180030D03, 20h
0x1800177b6  mov     rsi, r8
0x1800177b9  mov     rbx, rdx
0x1800177bc  jz      short loc_1800177CD
0x1800177be  mov     r8, rdx
0x1800177c1  lea     rdx, APIGetPublishStateName
0x1800177c8  call    McTemplateU0j_EventWriteTransfer
0x1800177cd  xor     edx, edx
0x1800177cf  mov     rcx, rbx; struct _GUID *
0x1800177d2  call    CallerHasAccess
0x1800177d7  test    eax, eax
0x1800177d9  js      short loc_18001781D
0x1800177db  lea     rcx, CriticalSection; lpCriticalSection
0x1800177e2  mov     edi, 82CF010Eh
0x1800177e7  call    cs:__imp_EnterCriticalSection
0x1800177ed  mov     rdx, rbx; struct _GUID *
0x1800177f0  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x1800177f7  call    ?FindSchedule@CScheduleMgr@@QEAAPEAVCSchedule@@PEBU_GUID@@@Z; CScheduleMgr::FindSchedule(_GUID const *)
0x1800177fc  test    rax, rax
0x1800177ff  jz      short loc_18001780E
0x180017801  mov     rdx, rsi; struct _WNF_STATE_NAME *
0x180017804  mov     rcx, rax; this
0x180017807  call    ?GetPublishStateName@CSchedule@@QEAAJPEAU_WNF_STATE_NAME@@@Z; CSchedule::GetPublishStateName(_WNF_STATE_NAME *)
0x18001780c  mov     edi, eax
0x18001780e  lea     rcx, CriticalSection; lpCriticalSection
0x180017815  call    cs:__imp_LeaveCriticalSection
0x18001781b  mov     eax, edi
0x18001781d  mov     rbx, [rsp+28h+arg_0]
0x180017822  mov     rsi, [rsp+28h+arg_8]
0x180017827  add     rsp, 20h
0x18001782b  pop     rdi
0x18001782c  retn
```
