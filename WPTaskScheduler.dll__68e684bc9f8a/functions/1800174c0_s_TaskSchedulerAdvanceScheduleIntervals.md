# s_TaskSchedulerAdvanceScheduleIntervals

- ea: `0x1800174c0`
- end: `0x18001751c`
- name: `s_TaskSchedulerAdvanceScheduleIntervals`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180001dd0`
- `0x180017370`
- `0x1800174c0`
- `0x1800185d4`

## pseudocode

```c
int __fastcall s_TaskSchedulerAdvanceScheduleIntervals(__int64 a1, struct _GUID *a2, unsigned int a3, int a4)
{
  int result; // eax
  CScheduleMgr *v8; // rcx

  if ( (byte_180030D03 & 0x10) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)APIAdvanceScheduleIntervals, (__int64)a2);
  result = CallerHasAccess(a2, 0);
  if ( result >= 0 )
    return CScheduleMgr::AdvanceSchedule(v8, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x1800174c0  mov     [rsp+arg_0], rbx
0x1800174c5  mov     [rsp+arg_8], rsi
0x1800174ca  push    rdi
0x1800174cb  sub     rsp, 20h
0x1800174cf  test    cs:byte_180030D03, 10h
0x1800174d6  mov     edi, r9d
0x1800174d9  mov     esi, r8d
0x1800174dc  mov     rbx, rdx
0x1800174df  jz      short loc_1800174F0
0x1800174e1  mov     r8, rdx
0x1800174e4  lea     rdx, APIAdvanceScheduleIntervals
0x1800174eb  call    McTemplateU0j_EventWriteTransfer
0x1800174f0  xor     edx, edx
0x1800174f2  mov     rcx, rbx; struct _GUID *
0x1800174f5  call    CallerHasAccess
0x1800174fa  test    eax, eax
0x1800174fc  js      short loc_18001750C
0x1800174fe  mov     r9d, edi; int
0x180017501  mov     r8d, esi; unsigned int
0x180017504  mov     rdx, rbx; struct _GUID *
0x180017507  call    ?AdvanceSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@KH@Z; CScheduleMgr::AdvanceSchedule(_GUID const *,ulong,int)
0x18001750c  mov     rbx, [rsp+28h+arg_0]
0x180017511  mov     rsi, [rsp+28h+arg_8]
0x180017516  add     rsp, 20h
0x18001751a  pop     rdi
0x18001751b  retn
```
