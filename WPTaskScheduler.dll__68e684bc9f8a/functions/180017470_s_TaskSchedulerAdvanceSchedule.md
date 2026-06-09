# s_TaskSchedulerAdvanceSchedule

- ea: `0x180017470`
- end: `0x1800174b4`
- name: `s_TaskSchedulerAdvanceSchedule`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180001dd0`
- `0x180017370`
- `0x180017470`
- `0x1800185d4`

## pseudocode

```c
int __fastcall s_TaskSchedulerAdvanceSchedule(__int64 a1, struct _GUID *a2)
{
  int result; // eax
  CScheduleMgr *v4; // rcx

  if ( (byte_180030D03 & 0x10) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)APIAdvanceSchedule, (__int64)a2);
  result = CallerHasAccess(a2, 0);
  if ( result >= 0 )
    return CScheduleMgr::AdvanceSchedule(v4, a2, 1u, 0);
  return result;
}

```

## disassembly

```asm
0x180017470  push    rbx
0x180017472  sub     rsp, 20h
0x180017476  test    cs:byte_180030D03, 10h
0x18001747d  mov     rbx, rdx
0x180017480  jz      short loc_180017491
0x180017482  mov     r8, rdx
0x180017485  lea     rdx, APIAdvanceSchedule
0x18001748c  call    McTemplateU0j_EventWriteTransfer
0x180017491  xor     edx, edx
0x180017493  mov     rcx, rbx; struct _GUID *
0x180017496  call    CallerHasAccess
0x18001749b  test    eax, eax
0x18001749d  js      short loc_1800174AE
0x18001749f  xor     r9d, r9d; int
0x1800174a2  mov     rdx, rbx; struct _GUID *
0x1800174a5  lea     r8d, [r9+1]; unsigned int
0x1800174a9  call    ?AdvanceSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@KH@Z; CScheduleMgr::AdvanceSchedule(_GUID const *,ulong,int)
0x1800174ae  add     rsp, 20h
0x1800174b2  pop     rbx
0x1800174b3  retn
```
