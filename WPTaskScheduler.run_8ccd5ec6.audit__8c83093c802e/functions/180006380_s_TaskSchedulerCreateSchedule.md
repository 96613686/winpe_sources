# s_TaskSchedulerCreateSchedule

- ea: `0x180006380`
- end: `0x1800063fe`
- name: `s_TaskSchedulerCreateSchedule`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180006380`
- `0x180006410`
- `0x18000ea40`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall s_TaskSchedulerCreateSchedule(__int64 a1, const struct _TASK_SCHEDULE *a2, __int64 a3)
{
  signed int v3; // ebx
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-28h] BYREF

  v3 = a3;
  if ( (byte_180030D03 & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)APICreateSchedule, a3, 1u, &v6);
  if ( v3 < 0 )
    return 2147942487LL;
  else
    return CScheduleMgr::CreateSchedule((CScheduleMgr *)&g_ScheduleMgr, a2, 0, v3);
}

```

## disassembly

```asm
0x180006380  mov     [rsp+arg_0], rbx
0x180006385  push    rdi
0x180006386  sub     rsp, 50h
0x18000638a  mov     rax, cs:__security_cookie
0x180006391  xor     rax, rsp
0x180006394  mov     [rsp+58h+var_18], rax
0x180006399  test    cs:byte_180030D03, 10h
0x1800063a0  mov     ebx, r8d
0x1800063a3  mov     rdi, rdx
0x1800063a6  jnz     short loc_1800063E0
0x1800063a8  test    ebx, ebx
0x1800063aa  js      short loc_1800063D9
0x1800063ac  mov     r9d, ebx; unsigned int
0x1800063af  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x1800063b6  xor     r8d, r8d; struct _TASK_RUNTIME_DATA *
0x1800063b9  mov     rdx, rdi; struct _TASK_SCHEDULE *
0x1800063bc  call    ?CreateSchedule@CScheduleMgr@@QEAAJPEBU_TASK_SCHEDULE@@PEBU_TASK_RUNTIME_DATA@@K@Z; CScheduleMgr::CreateSchedule(_TASK_SCHEDULE const *,_TASK_RUNTIME_DATA const *,ulong)
0x1800063c1  mov     rcx, [rsp+58h+var_18]
0x1800063c6  xor     rcx, rsp; StackCookie
0x1800063c9  call    __security_check_cookie
0x1800063ce  mov     rbx, [rsp+58h+arg_0]
0x1800063d3  add     rsp, 50h
0x1800063d7  pop     rdi
0x1800063d8  retn
0x1800063d9  mov     eax, 80070057h
0x1800063de  jmp     short loc_1800063C1
0x1800063e0  lea     rax, [rsp+58h+var_28]
0x1800063e5  mov     r9d, 1
0x1800063eb  lea     rdx, APICreateSchedule
0x1800063f2  mov     [rsp+58h+var_38], rax
0x1800063f7  call    McGenEventWrite_EventWriteTransfer
0x1800063fc  jmp     short loc_1800063A8
```
