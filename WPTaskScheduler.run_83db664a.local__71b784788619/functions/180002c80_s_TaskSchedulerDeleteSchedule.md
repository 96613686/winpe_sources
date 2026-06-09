# s_TaskSchedulerDeleteSchedule

- ea: `0x180002c80`
- end: `0x180002d84`
- name: `s_TaskSchedulerDeleteSchedule`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002c80`
- `0x180002d90`
- `0x180002f00`
- `0x18000e970`
- `0x180017370`
- `0x18001ffc0`

## pseudocode

```c
__int64 __fastcall s_TaskSchedulerDeleteSchedule(__int64 a1, struct _GUID *a2)
{
  __int64 **i; // rax
  unsigned int v4; // ebx
  unsigned __int16 *v6; // rcx
  RPC_STATUS v7; // eax

  if ( (byte_180030D03 & 0x10) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)APIDeleteSchedule, (__int64)a2);
  for ( i = (__int64 **)g_ScheduleMgr; ; i = (__int64 **)*i )
  {
    if ( i == (__int64 **)&g_ScheduleMgr )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
        McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)ScheduleNotFoundWarning, (__int64)a2);
      goto LABEL_11;
    }
    a1 = (__int64)i[2] - *(_QWORD *)&a2->Data1;
    if ( !a1 )
      a1 = (__int64)i[3] - *(_QWORD *)a2->Data4;
    if ( !a1 )
      break;
  }
  if ( !i )
  {
LABEL_11:
    v4 = -2100362994;
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
      McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)ScheduleNotFoundWarning, (__int64)a2);
    return v4;
  }
  if ( (int)CScheduleMgr::IsCallerScheduleOwner(0, a2) < 0 && TsiCheckCallerCapabilities(v6) < 0 )
  {
    v7 = TsiCheckCallerCapabilities(v6);
    v4 = v7;
    if ( v7 < 0 )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer((__int64)v6, (const EVENT_DESCRIPTOR *)SecurityError, (unsigned int)v7);
      return v4;
    }
  }
  return CScheduleMgr::DeleteSchedule((CScheduleMgr *)v6, a2);
}

```

## disassembly

```asm
0x180002c80  push    rdi
0x180002c82  sub     rsp, 20h
0x180002c86  test    cs:byte_180030D03, 10h
0x180002c8d  mov     rdi, rdx
0x180002c90  jnz     loc_180002D3D
0x180002c96  mov     rax, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180002c9d  lea     rdx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180002ca4  mov     [rsp+28h+arg_0], rbx
0x180002ca9  cmp     rax, rdx
0x180002cac  jz      short loc_180002CC9
0x180002cae  mov     rcx, [rax+10h]
0x180002cb2  sub     rcx, [rdi]
0x180002cb5  jnz     short loc_180002CBF
0x180002cb7  mov     rcx, [rax+18h]
0x180002cbb  sub     rcx, [rdi+8]; this
0x180002cbf  test    rcx, rcx
0x180002cc2  jz      short loc_180002CF5
0x180002cc4  mov     rax, [rax]
0x180002cc7  jmp     short loc_180002CA9
0x180002cc9  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180002cd0  jnz     loc_180002D5C
0x180002cd6  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180002cdd  mov     ebx, 82CF010Eh
0x180002ce2  jnz     loc_180002D70
0x180002ce8  mov     eax, ebx
0x180002cea  mov     rbx, [rsp+28h+arg_0]
0x180002cef  add     rsp, 20h
0x180002cf3  pop     rdi
0x180002cf4  retn
0x180002cf5  test    rax, rax
0x180002cf8  jz      short loc_180002CD6
0x180002cfa  mov     rdx, rdi; struct _GUID *
0x180002cfd  call    ?IsCallerScheduleOwner@CScheduleMgr@@QEAA?BJPEBU_GUID@@@Z; CScheduleMgr::IsCallerScheduleOwner(_GUID const *)
0x180002d02  test    eax, eax
0x180002d04  js      short loc_180002D51
0x180002d06  mov     rdx, rdi; struct _GUID *
0x180002d09  mov     rbx, [rsp+28h+arg_0]
0x180002d0e  add     rsp, 20h
0x180002d12  pop     rdi
0x180002d13  jmp     ?DeleteSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@@Z; CScheduleMgr::DeleteSchedule(_GUID const *)
0x180002d18  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180002d1d  mov     ebx, eax
0x180002d1f  test    eax, eax
0x180002d21  jns     short loc_180002D06
0x180002d23  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 1
0x180002d2a  jz      short loc_180002CE8
0x180002d2c  mov     r8d, eax
0x180002d2f  lea     rdx, SecurityError
0x180002d36  call    McTemplateU0q_EventWriteTransfer
0x180002d3b  jmp     short loc_180002CE8
0x180002d3d  mov     r8, rdi
0x180002d40  lea     rdx, APIDeleteSchedule
0x180002d47  call    McTemplateU0j_EventWriteTransfer
0x180002d4c  jmp     loc_180002C96
0x180002d51  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180002d56  test    eax, eax
0x180002d58  jns     short loc_180002D06
0x180002d5a  jmp     short loc_180002D18
0x180002d5c  mov     r8, rdi
0x180002d5f  lea     rdx, ScheduleNotFoundWarning
0x180002d66  call    McTemplateU0j_EventWriteTransfer
0x180002d6b  jmp     loc_180002CD6
0x180002d70  mov     r8, rdi
0x180002d73  lea     rdx, ScheduleNotFoundWarning
0x180002d7a  call    McTemplateU0j_EventWriteTransfer
0x180002d7f  jmp     loc_180002CE8
```
