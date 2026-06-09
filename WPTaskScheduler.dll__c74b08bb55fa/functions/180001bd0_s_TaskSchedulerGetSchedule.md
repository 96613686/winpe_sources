# s_TaskSchedulerGetSchedule

- ea: `0x180001bd0`
- end: `0x180001cc7`
- name: `s_TaskSchedulerGetSchedule`
- size: `247`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, struct _TASK_SCHEDULE **, struct _TASK_STATISTICS **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001bd0`
- `0x180002f00`
- `0x18000e970`
- `0x180017370`
- `0x1800192ec`
- `0x18001ffc0`

## pseudocode

```c
__int64 __fastcall s_TaskSchedulerGetSchedule(
        __int64 a1,
        const struct _GUID *a2,
        struct _TASK_SCHEDULE **a3,
        struct _TASK_STATISTICS **a4)
{
  __int64 **i; // rax
  const unsigned __int16 *v8; // rcx
  const unsigned __int16 *v9; // rcx
  RPC_STATUS v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx

  if ( (byte_180030D03 & 0x10) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, APIGetSchedule, a2);
  for ( i = (__int64 **)g_ScheduleMgr; ; i = (__int64 **)*i )
  {
    if ( i == (__int64 **)&g_ScheduleMgr )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
        McTemplateU0j_EventWriteTransfer(a1, ScheduleNotFoundWarning, a2);
      goto LABEL_18;
    }
    a1 = (__int64)i[2] - *(_QWORD *)&a2->Data1;
    if ( !a1 )
      a1 = (__int64)i[3] - *(_QWORD *)a2->Data4;
    if ( !a1 )
      break;
  }
  if ( !i )
  {
LABEL_18:
    v12 = -2100362994;
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
      McTemplateU0j_EventWriteTransfer(a1, ScheduleNotFoundWarning, a2);
    return v12;
  }
  if ( (int)CScheduleMgr::IsCallerScheduleOwner(0, a2) >= 0 )
    return CScheduleMgr::GetSchedule((CScheduleMgr *)&g_ScheduleMgr, a2, a3, a4, 0);
  if ( TsiCheckCallerCapabilities(v8) >= 0 )
    return CScheduleMgr::GetSchedule((CScheduleMgr *)&g_ScheduleMgr, a2, a3, a4, 0);
  v10 = TsiCheckCallerCapabilities(v9);
  v12 = v10;
  if ( v10 >= 0 )
    return CScheduleMgr::GetSchedule((CScheduleMgr *)&g_ScheduleMgr, a2, a3, a4, 0);
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v11, SecurityError, (unsigned int)v10);
  return v12;
}

```

## disassembly

```asm
0x180001bd0  push    rbx
0x180001bd2  push    rbp
0x180001bd3  push    rsi
0x180001bd4  push    rdi
0x180001bd5  push    r14
0x180001bd7  sub     rsp, 30h
0x180001bdb  test    cs:byte_180030D03, 10h
0x180001be2  mov     rsi, r9
0x180001be5  mov     rbp, r8
0x180001be8  mov     rdi, rdx
0x180001beb  jz      short loc_180001BFC
0x180001bed  mov     r8, rdx
0x180001bf0  lea     rdx, APIGetSchedule
0x180001bf7  call    McTemplateU0j_EventWriteTransfer
0x180001bfc  mov     rax, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180001c03  lea     r14, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180001c0a  cmp     rax, r14
0x180001c0d  jz      short loc_180001C85
0x180001c0f  mov     rcx, [rax+10h]
0x180001c13  sub     rcx, [rdi]
0x180001c16  jnz     short loc_180001C20
0x180001c18  mov     rcx, [rax+18h]
0x180001c1c  sub     rcx, [rdi+8]; this
0x180001c20  test    rcx, rcx
0x180001c23  jz      short loc_180001C2A
0x180001c25  mov     rax, [rax]
0x180001c28  jmp     short loc_180001C0A
0x180001c2a  test    rax, rax
0x180001c2d  jz      short loc_180001C9D
0x180001c2f  mov     rdx, rdi; struct _GUID *
0x180001c32  call    ?IsCallerScheduleOwner@CScheduleMgr@@QEAA?BJPEBU_GUID@@@Z; CScheduleMgr::IsCallerScheduleOwner(_GUID const *)
0x180001c37  test    eax, eax
0x180001c39  jns     short loc_180001C69
0x180001c3b  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180001c40  test    eax, eax
0x180001c42  jns     short loc_180001C69
0x180001c44  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180001c49  mov     ebx, eax
0x180001c4b  test    eax, eax
0x180001c4d  jns     short loc_180001C69
0x180001c4f  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 1
0x180001c56  jz      short loc_180001CBA
0x180001c58  mov     r8d, eax
0x180001c5b  lea     rdx, SecurityError
0x180001c62  call    McTemplateU0q_EventWriteTransfer
0x180001c67  jmp     short loc_180001CBA
0x180001c69  mov     r9, rsi; struct _TASK_STATISTICS **
0x180001c6c  mov     [rsp+58h+var_38], 0; struct _TASK_RUNTIME_DATA **
0x180001c75  mov     r8, rbp; struct _TASK_SCHEDULE **
0x180001c78  mov     rdx, rdi; struct _GUID *
0x180001c7b  mov     rcx, r14; this
0x180001c7e  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x180001c83  jmp     short loc_180001CBC
0x180001c85  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180001c8c  jz      short loc_180001C9D
0x180001c8e  mov     r8, rdi
0x180001c91  lea     rdx, ScheduleNotFoundWarning
0x180001c98  call    McTemplateU0j_EventWriteTransfer
0x180001c9d  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180001ca4  mov     ebx, 82CF010Eh
0x180001ca9  jz      short loc_180001CBA
0x180001cab  mov     r8, rdi
0x180001cae  lea     rdx, ScheduleNotFoundWarning
0x180001cb5  call    McTemplateU0j_EventWriteTransfer
0x180001cba  mov     eax, ebx
0x180001cbc  add     rsp, 30h
0x180001cc0  pop     r14
0x180001cc2  pop     rdi
0x180001cc3  pop     rsi
0x180001cc4  pop     rbp
0x180001cc5  pop     rbx
0x180001cc6  retn
```
